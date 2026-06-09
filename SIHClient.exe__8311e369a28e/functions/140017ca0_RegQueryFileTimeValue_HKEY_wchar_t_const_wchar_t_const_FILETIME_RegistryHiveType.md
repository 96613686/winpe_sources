# RegQueryFileTimeValue(HKEY__ *,wchar_t const *,wchar_t const *,_FILETIME *,RegistryHiveType)

- ea: `0x140017ca0`
- end: `0x140017d9d`
- name: `?RegQueryFileTimeValue@@YAJPEAUHKEY__@@PEB_W1PEAU_FILETIME@@W4RegistryHiveType@@@Z`
- size: `253`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x140027c50`

## callees

- `0x1400176fc`
- `0x140017ca0`
- `0x14001869c`
- `0x140044a34`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017d7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017d7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140017d16`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140017d16`

## pseudocode

```c
__int64 __fastcall RegQueryFileTimeValue(HKEY a1, __int64 a2, __int64 a3, _QWORD *a4)
{
  __int64 result; // rax
  LSTATUS v8; // eax
  int v9; // ecx
  int ValueCchHelper; // ebx
  REGSAM samDesired; // [rsp+40h] [rbp-68h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-60h] BYREF
  _BYTE v13[48]; // [rsp+50h] [rbp-58h] BYREF

  hKey = 0;
  samDesired = 1;
  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  result = SetRegistryType((int)a1, &samDesired);
  if ( (int)result >= 0 )
  {
    v8 = RegOpenKeyExW(a1, 0, 0, samDesired, &hKey);
    v9 = v8;
    if ( v8 )
    {
      result = (unsigned __int16)v8 | 0x80070000;
      if ( v9 <= 0 )
        return (unsigned int)v9;
    }
    else
    {
      ValueCchHelper = SafeRegQueryValueCchHelper(0, hKey, a3, v13, 21, 0, 0);
      if ( ValueCchHelper >= 0 )
        ValueCchHelper = StringToFileTime(v13, a4, 0);
      RegCloseKey(hKey);
      return (unsigned int)ValueCchHelper;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140017ca0  push    rbx
0x140017ca2  push    rsi
0x140017ca3  push    rdi
0x140017ca4  sub     rsp, 90h
0x140017cab  mov     rax, cs:__security_cookie
0x140017cb2  xor     rax, rsp
0x140017cb5  mov     [rsp+0A8h+var_28], rax
0x140017cbd  mov     [rsp+0A8h+hKey], 0
0x140017cc6  mov     rdi, r9
0x140017cc9  mov     [rsp+0A8h+samDesired], 1
0x140017cd1  mov     rbx, r8
0x140017cd4  mov     rsi, rcx
0x140017cd7  test    r9, r9
0x140017cda  jnz     short loc_140017CE6
0x140017cdc  mov     eax, 80070057h
0x140017ce1  jmp     loc_140017D82
0x140017ce6  lea     rdx, [rsp+0A8h+samDesired]
0x140017ceb  mov     qword ptr [r9], 0
0x140017cf2  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x140017cf7  test    eax, eax
0x140017cf9  js      loc_140017D82
0x140017cff  mov     r9d, [rsp+0A8h+samDesired]; samDesired
0x140017d04  lea     rax, [rsp+0A8h+hKey]
0x140017d09  xor     r8d, r8d; ulOptions
0x140017d0c  mov     [rsp+0A8h+phkResult], rax; phkResult
0x140017d11  xor     edx, edx; lpSubKey
0x140017d13  mov     rcx, rsi; hKey
0x140017d16  call    cs:__imp_RegOpenKeyExW
0x140017d1c  mov     ecx, eax
0x140017d1e  test    eax, eax
0x140017d20  jz      short loc_140017D31
0x140017d22  movzx   eax, cx
0x140017d25  or      eax, 80070000h
0x140017d2a  test    ecx, ecx
0x140017d2c  cmovle  eax, ecx
0x140017d2f  jmp     short loc_140017D82
0x140017d31  mov     rdx, [rsp+0A8h+hKey]
0x140017d36  lea     r9, [rsp+0A8h+var_58]
0x140017d3b  mov     [rsp+0A8h+var_78], 0
0x140017d44  mov     r8, rbx
0x140017d47  mov     [rsp+0A8h+var_80], 0
0x140017d50  mov     dword ptr [rsp+0A8h+phkResult], 15h
0x140017d58  call    SafeRegQueryValueCchHelper
0x140017d5d  mov     ebx, eax
0x140017d5f  test    eax, eax
0x140017d61  js      short loc_140017D75
0x140017d63  xor     r8d, r8d
0x140017d66  lea     rcx, [rsp+0A8h+var_58]
0x140017d6b  mov     rdx, rdi
0x140017d6e  call    StringToFileTime
0x140017d73  mov     ebx, eax
0x140017d75  mov     rcx, [rsp+0A8h+hKey]; hKey
0x140017d7a  call    cs:__imp_RegCloseKey
0x140017d80  mov     eax, ebx
0x140017d82  mov     rcx, [rsp+0A8h+var_28]
0x140017d8a  xor     rcx, rsp; StackCookie
0x140017d8d  call    __security_check_cookie
0x140017d92  add     rsp, 90h
0x140017d99  pop     rdi
0x140017d9a  pop     rsi
0x140017d9b  pop     rbx
0x140017d9c  retn
```
