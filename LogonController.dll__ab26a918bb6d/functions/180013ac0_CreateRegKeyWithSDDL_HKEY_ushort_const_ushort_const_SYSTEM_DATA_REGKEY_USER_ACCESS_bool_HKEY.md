# _CreateRegKeyWithSDDL(HKEY__ *,ushort const *,ushort const *,SYSTEM_DATA_REGKEY_USER_ACCESS,bool,HKEY__ * *)

- ea: `0x180013ac0`
- end: `0x180013c13`
- name: `?_CreateRegKeyWithSDDL@@YAJPEAUHKEY__@@PEBG1W4SYSTEM_DATA_REGKEY_USER_ACCESS@@_NPEAPEAU1@@Z`
- size: `339`
- prototype: `int __high(HKEY, const unsigned __int16 *, const unsigned __int16 *, enum SYSTEM_DATA_REGKEY_USER_ACCESS, bool, HKEY *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800143b0`

## callees

- `0x180004c00`
- `0x180013ac0`
- `0x18006c000`

## import_xrefs

- `KERNEL32!LocalFree` at `0x180013bf8`
- `KERNEL32!LocalFree` at `0x180013bf8`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013bde`
- `api-ms-win-core-registry-l1-1-0!RegCreateKeyExW` at `0x180013bde`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180013b88`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180013b88`

## pseudocode

```c
__int64 __fastcall _CreateRegKeyWithSDDL(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        __int64 a4,
        __int64 a5,
        PHKEY phkResult)
{
  WCHAR *v6; // r9
  __int64 v8; // rax
  __int64 v9; // r8
  const wchar_t *v10; // rdx
  WCHAR *v11; // rcx
  unsigned int v12; // edx
  __int64 result; // rax
  LSTATUS v14; // eax
  unsigned int v15; // ebx
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+50h] [rbp-248h] BYREF
  struct _SECURITY_ATTRIBUTES SecurityAttributes; // [rsp+58h] [rbp-240h] BYREF
  WCHAR StringSecurityDescriptor[264]; // [rsp+70h] [rbp-228h] BYREF

  v6 = StringSecurityDescriptor;
  v8 = 2147483646;
  v9 = 260;
  *phkResult = 0;
  v10 = L"D:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;LA)(A;CIOI;KR;;;WD)";
  do
  {
    if ( !v8 )
      break;
    if ( !*v10 )
      break;
    *v6++ = *v10++;
    --v8;
    --v9;
  }
  while ( v9 );
  v11 = v6 - 1;
  v12 = -2147024774;
  if ( v9 )
  {
    v11 = v6;
    v12 = 0;
  }
  *v11 = 0;
  if ( !v9 )
    return v12;
  SecurityDescriptor = 0;
  if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(StringSecurityDescriptor, 1u, &SecurityDescriptor, 0)
    || (result = ResultFromKnownLastError(), (int)result >= 0) )
  {
    SecurityAttributes.lpSecurityDescriptor = SecurityDescriptor;
    *(_QWORD *)&SecurityAttributes.nLength = 24;
    *(_QWORD *)&SecurityAttributes.bInheritHandle = 0;
    v14 = RegCreateKeyExW(
            HKEY_LOCAL_MACHINE,
            a3,
            0,
            (LPWSTR)&sourceString,
            0,
            0x2001Fu,
            &SecurityAttributes,
            phkResult,
            0);
    v15 = v14;
    if ( v14 > 0 )
      v15 = (unsigned __int16)v14 | 0x80070000;
    LocalFree(SecurityDescriptor);
    return v15;
  }
  return result;
}

```

## disassembly

```asm
0x180013ac0  mov     [rsp+arg_0], rbx
0x180013ac5  mov     [rsp+arg_8], rsi
0x180013aca  push    rdi
0x180013acb  sub     rsp, 290h
0x180013ad2  mov     rax, cs:__security_cookie
0x180013ad9  xor     rax, rsp
0x180013adc  mov     [rsp+298h+var_18], rax
0x180013ae4  mov     rbx, [rsp+298h+arg_28]
0x180013aec  lea     r9, [rsp+298h+StringSecurityDescriptor]
0x180013af1  xor     esi, esi
0x180013af3  mov     rdi, r8
0x180013af6  mov     eax, 7FFFFFFEh
0x180013afb  mov     r8d, 104h
0x180013b01  mov     [rbx], rsi
0x180013b04  mov     rdx, cs:off_1800A07D8; "D:(A;CIOI;KA;;;SY)(A;CIOI;KA;;;LA)(A;CI"...
0x180013b0b  nop     dword ptr [rax+rax+00h]
0x180013b10  test    rax, rax
0x180013b13  jz      short loc_180013B32
0x180013b15  movzx   ecx, word ptr [rdx]
0x180013b18  test    cx, cx
0x180013b1b  jz      short loc_180013B32
0x180013b1d  mov     [r9], cx
0x180013b21  add     rdx, 2
0x180013b25  add     r9, 2
0x180013b29  dec     rax
0x180013b2c  sub     r8, 1
0x180013b30  jnz     short loc_180013B10
0x180013b32  test    r8, r8
0x180013b35  lea     rcx, [r9-2]
0x180013b39  mov     edx, 8007007Ah
0x180013b3e  cmovnz  rcx, r9
0x180013b42  cmovnz  edx, esi
0x180013b45  mov     [rcx], si
0x180013b48  jnz     short loc_180013B71
0x180013b4a  mov     eax, edx
0x180013b4c  mov     rcx, [rsp+298h+var_18]
0x180013b54  xor     rcx, rsp; StackCookie
0x180013b57  call    __security_check_cookie
0x180013b5c  lea     r11, [rsp+298h+var_8]
0x180013b64  mov     rbx, [r11+10h]
0x180013b68  mov     rsi, [r11+18h]
0x180013b6c  mov     rsp, r11
0x180013b6f  pop     rdi
0x180013b70  retn
0x180013b71  xor     r9d, r9d; SecurityDescriptorSize
0x180013b74  mov     [rsp+298h+SecurityDescriptor], rsi
0x180013b79  lea     r8, [rsp+298h+SecurityDescriptor]; SecurityDescriptor
0x180013b7e  mov     edx, 1; StringSDRevision
0x180013b83  lea     rcx, [rsp+298h+StringSecurityDescriptor]; StringSecurityDescriptor
0x180013b88  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180013b8e  test    eax, eax
0x180013b90  jz      short loc_180013C05
0x180013b92  mov     rax, [rsp+298h+SecurityDescriptor]
0x180013b97  lea     r9, sourceString; lpClass
0x180013b9e  mov     [rsp+298h+lpdwDisposition], rsi; lpdwDisposition
0x180013ba3  xor     r8d, r8d; Reserved
0x180013ba6  mov     [rsp+298h+phkResult], rbx; phkResult
0x180013bab  mov     rdx, rdi; lpSubKey
0x180013bae  mov     [rsp+298h+SecurityAttributes.lpSecurityDescriptor], rax
0x180013bb3  mov     rcx, 0FFFFFFFF80000002h; hKey
0x180013bba  lea     rax, [rsp+298h+SecurityAttributes]
0x180013bbf  mov     qword ptr [rsp+298h+SecurityAttributes.nLength], 18h
0x180013bc8  mov     [rsp+298h+lpSecurityAttributes], rax; lpSecurityAttributes
0x180013bcd  mov     [rsp+298h+samDesired], 2001Fh; samDesired
0x180013bd5  mov     [rsp+298h+dwOptions], esi; dwOptions
0x180013bd9  mov     qword ptr [rsp+298h+SecurityAttributes.bInheritHandle], rsi
0x180013bde  call    cs:__imp_RegCreateKeyExW
0x180013be4  mov     ebx, eax
0x180013be6  test    eax, eax
0x180013be8  jle     short loc_180013BF3
0x180013bea  movzx   ebx, ax
0x180013bed  or      ebx, 80070000h
0x180013bf3  mov     rcx, [rsp+298h+SecurityDescriptor]; hMem
0x180013bf8  call    cs:__imp_LocalFree
0x180013bfe  mov     eax, ebx
0x180013c00  jmp     loc_180013B4C
0x180013c05  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x180013c0a  test    eax, eax
0x180013c0c  jns     short loc_180013B92
0x180013c0e  jmp     loc_180013B4C
```
