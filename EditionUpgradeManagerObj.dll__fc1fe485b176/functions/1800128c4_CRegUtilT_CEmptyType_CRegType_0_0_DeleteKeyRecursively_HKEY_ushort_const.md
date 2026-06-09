# CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY__ *,ushort const *)

- ea: `0x1800128c4`
- end: `0x180012abc`
- name: `?DeleteKeyRecursively@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBG@Z`
- size: `504`
- prototype: `__int64 __fastcall(HKEY, const WCHAR *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x1800128c4`
- `0x180016bcc`
- `0x180016d34`

## callees

- `0x180001ac0`
- `0x1800090dc`
- `0x180009480`
- `0x1800128c4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012960`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800129f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a76`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012960`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x1800129f7`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180012a76`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800129c7`
- `api-ms-win-core-registry-l1-1-0!RegQueryInfoKeyW` at `0x1800129c7`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001291a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x18001291a`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180012a41`
- `api-ms-win-core-registry-l2-1-0!RegEnumKeyW` at `0x180012a41`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180012a84`
- `api-ms-win-core-registry-l2-1-0!RegDeleteKeyW` at `0x180012a84`

## pseudocode

```c
__int64 __fastcall CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY a1, const WCHAR *a2)
{
  int v4; // edi
  HKEY v5; // rbx
  int v6; // ecx
  HKEY v8; // rcx
  HKEY v9; // rcx
  int v10; // eax
  DWORD v11; // eax
  DWORD cSubKeys; // [rsp+60h] [rbp-A0h] BYREF
  HKEY hKey; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+70h] [rbp-90h] BYREF

  cSubKeys = 0;
  hKey = 0;
  v4 = RegOpenKeyExW(a1, a2, 0, 0x2000000u, &hKey);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    v5 = 0;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  else
  {
    v5 = hKey;
    hKey = 0;
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  if ( hKey )
  {
    RegCloseKey(hKey);
    hKey = 0;
  }
  if ( v4 < 0 )
  {
LABEL_12:
    v6 = v4;
LABEL_13:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_14;
  }
  v4 = RegQueryInfoKeyW(v5, 0, 0, 0, &cSubKeys, 0, 0, 0, 0, 0, 0, 0);
  if ( v4 )
  {
LABEL_10:
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    goto LABEL_12;
  }
  while ( 1 )
  {
    v11 = cSubKeys;
    if ( !cSubKeys )
      break;
    v8 = 0;
    --cSubKeys;
    if ( v5 )
      v8 = v5;
    v4 = RegEnumKeyW(v8, v11 - 1, Name, 0x105u);
    if ( v4 )
      goto LABEL_10;
    v9 = 0;
    if ( v5 )
      v9 = v5;
    v10 = CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(v9, Name);
    v4 = v10;
    if ( v10 < 0 )
    {
      v6 = v10;
      goto LABEL_13;
    }
  }
  if ( v5 )
  {
    RegCloseKey(v5);
    v5 = 0;
  }
  v4 = RegDeleteKeyW(a1, a2);
  if ( v4 )
  {
    if ( v4 > 0 )
      v4 = (unsigned __int16)v4 | 0x80070000;
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v4);
  }
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  if ( v4 < 0 )
    goto LABEL_12;
LABEL_14:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent((unsigned int)v4);
  if ( v5 )
    RegCloseKey(v5);
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x1800128c4  mov     [rsp-8+arg_10], rbx
0x1800128c9  push    rbp
0x1800128ca  push    rsi
0x1800128cb  push    rdi
0x1800128cc  push    r12
0x1800128ce  push    r14
0x1800128d0  lea     rbp, [rsp-190h]
0x1800128d8  sub     rsp, 290h
0x1800128df  mov     rax, cs:__security_cookie
0x1800128e6  xor     rax, rsp
0x1800128e9  mov     [rbp+1B0h+var_30], rax
0x1800128f0  lea     rax, [rsp+2B0h+hKey]
0x1800128f5  mov     [rsp+2B0h+cSubKeys], 0
0x1800128fd  mov     r9d, 2000000h; samDesired
0x180012903  mov     [rsp+2B0h+phkResult], rax; phkResult
0x180012908  xor     r8d, r8d; ulOptions
0x18001290b  mov     [rsp+2B0h+hKey], 0
0x180012914  mov     r14, rdx
0x180012917  mov     rsi, rcx
0x18001291a  call    cs:__imp_RegOpenKeyExW
0x180012920  mov     edi, eax
0x180012922  mov     r12d, 80070000h
0x180012928  test    eax, eax
0x18001292a  jnz     short loc_18001293C
0x18001292c  mov     rbx, [rsp+2B0h+hKey]
0x180012931  mov     [rsp+2B0h+hKey], 0
0x18001293a  jmp     short loc_18001294F
0x18001293c  test    edi, edi
0x18001293e  jle     short loc_180012946
0x180012940  movzx   edi, di
0x180012943  or      edi, r12d
0x180012946  mov     ecx, edi
0x180012948  xor     ebx, ebx
0x18001294a  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18001294f  mov     ecx, edi
0x180012951  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180012956  mov     rcx, [rsp+2B0h+hKey]; hKey
0x18001295b  test    rcx, rcx
0x18001295e  jz      short loc_18001296F
0x180012960  call    cs:__imp_RegCloseKey
0x180012966  mov     [rsp+2B0h+hKey], 0
0x18001296f  test    edi, edi
0x180012971  js      short loc_1800129E1
0x180012973  mov     [rsp+2B0h+lpftLastWriteTime], 0; lpftLastWriteTime
0x18001297c  lea     rax, [rsp+2B0h+cSubKeys]
0x180012981  mov     [rsp+2B0h+lpcbSecurityDescriptor], 0; lpcbSecurityDescriptor
0x18001298a  xor     r9d, r9d; lpReserved
0x18001298d  mov     [rsp+2B0h+lpcbMaxValueLen], 0; lpcbMaxValueLen
0x180012996  xor     r8d, r8d; lpcchClass
0x180012999  mov     [rsp+2B0h+lpcbMaxValueNameLen], 0; lpcbMaxValueNameLen
0x1800129a2  xor     edx, edx; lpClass
0x1800129a4  mov     [rsp+2B0h+lpcValues], 0; lpcValues
0x1800129ad  mov     rcx, rbx; hKey
0x1800129b0  mov     [rsp+2B0h+lpcbMaxClassLen], 0; lpcbMaxClassLen
0x1800129b9  mov     [rsp+2B0h+lpcbMaxSubKeyLen], 0; lpcbMaxSubKeyLen
0x1800129c2  mov     [rsp+2B0h+phkResult], rax; lpcSubKeys
0x1800129c7  call    cs:__imp_RegQueryInfoKeyW
0x1800129cd  mov     edi, eax
0x1800129cf  test    eax, eax
0x1800129d1  jz      loc_180012A66
0x1800129d7  test    edi, edi
0x1800129d9  jle     short loc_1800129E1
0x1800129db  movzx   edi, di
0x1800129de  or      edi, r12d
0x1800129e1  mov     ecx, edi
0x1800129e3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800129e8  mov     ecx, edi
0x1800129ea  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800129ef  test    rbx, rbx
0x1800129f2  jz      short loc_1800129FD
0x1800129f4  mov     rcx, rbx; hKey
0x1800129f7  call    cs:__imp_RegCloseKey
0x1800129fd  mov     eax, edi
0x1800129ff  mov     rcx, [rbp+1B0h+var_30]
0x180012a06  xor     rcx, rsp; StackCookie
0x180012a09  call    __security_check_cookie
0x180012a0e  mov     rbx, [rsp+2B0h+arg_10]
0x180012a16  add     rsp, 290h
0x180012a1d  pop     r14
0x180012a1f  pop     r12
0x180012a21  pop     rdi
0x180012a22  pop     rsi
0x180012a23  pop     rbp
0x180012a24  retn
0x180012a25  dec     eax
0x180012a27  lea     r8, [rsp+2B0h+Name]; lpName
0x180012a2c  xor     ecx, ecx
0x180012a2e  mov     [rsp+2B0h+cSubKeys], eax
0x180012a32  test    rbx, rbx
0x180012a35  mov     r9d, 105h; cchName
0x180012a3b  mov     edx, eax; dwIndex
0x180012a3d  cmovnz  rcx, rbx; hKey
0x180012a41  call    cs:__imp_RegEnumKeyW
0x180012a47  mov     edi, eax
0x180012a49  test    eax, eax
0x180012a4b  jnz     short loc_1800129D7
0x180012a4d  xor     ecx, ecx
0x180012a4f  lea     rdx, [rsp+2B0h+Name]
0x180012a54  test    rbx, rbx
0x180012a57  cmovnz  rcx, rbx
0x180012a5b  call    ?DeleteKeyRecursively@?$CRegUtilT@VCEmptyType@@UCRegType@@$0A@$0A@@@CAJPEAUHKEY__@@PEBG@Z; CRegUtilT<CEmptyType,CRegType,0,0>::DeleteKeyRecursively(HKEY__ *,ushort const *)
0x180012a60  mov     edi, eax
0x180012a62  test    eax, eax
0x180012a64  js      short loc_180012AB5
0x180012a66  mov     eax, [rsp+2B0h+cSubKeys]
0x180012a6a  test    eax, eax
0x180012a6c  jnz     short loc_180012A25
0x180012a6e  test    rbx, rbx
0x180012a71  jz      short loc_180012A7E
0x180012a73  mov     rcx, rbx; hKey
0x180012a76  call    cs:__imp_RegCloseKey
0x180012a7c  xor     ebx, ebx
0x180012a7e  mov     rdx, r14; lpSubKey
0x180012a81  mov     rcx, rsi; hKey
0x180012a84  call    cs:__imp_RegDeleteKeyW
0x180012a8a  mov     edi, eax
0x180012a8c  test    eax, eax
0x180012a8e  jz      short loc_180012AA1
0x180012a90  test    edi, edi
0x180012a92  jle     short loc_180012A9A
0x180012a94  movzx   edi, di
0x180012a97  or      edi, r12d
0x180012a9a  mov     ecx, edi
0x180012a9c  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180012aa1  mov     ecx, edi
0x180012aa3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180012aa8  test    edi, edi
0x180012aaa  jns     loc_1800129E8
0x180012ab0  jmp     loc_1800129E1
0x180012ab5  mov     ecx, eax
0x180012ab7  jmp     loc_1800129E3
```
