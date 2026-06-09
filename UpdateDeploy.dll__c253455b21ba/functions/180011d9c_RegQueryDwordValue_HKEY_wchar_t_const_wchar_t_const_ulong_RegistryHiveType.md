# RegQueryDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,RegistryHiveType)

- ea: `0x180011d9c`
- end: `0x180011e5a`
- name: `?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_W1PEAKW4RegistryHiveType@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `6`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180046e50`
- `0x180047000`
- `0x18004ad6c`
- `0x18004b048`
- `0x18004b240`
- `0x18004ef48`

## callees

- `0x180011cb8`
- `0x180011d9c`
- `0x180011e60`
- `0x180061960`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e0a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x180011e0a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e3c`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180011e3c`

## pseudocode

```c
__int64 __fastcall RegQueryDwordValue(HKEY a1, const WCHAR *a2, const wchar_t *a3, unsigned int *a4)
{
  __int64 result; // rax
  LSTATUS v9; // ecx
  unsigned int DwordValue; // ebx
  REGSAM samDesired; // [rsp+30h] [rbp-48h] BYREF
  HKEY hKey; // [rsp+38h] [rbp-40h] BYREF

  hKey = 0;
  samDesired = 1;
  if ( !a4 )
    return 2147942487LL;
  *a4 = 0;
  result = SetRegistryType(a1, &samDesired);
  if ( (int)result >= 0 )
  {
    v9 = RegOpenKeyExW(a1, a2, 0, samDesired, &hKey);
    if ( v9 )
    {
      result = (unsigned __int16)v9 | 0x80070000;
      if ( v9 <= 0 )
        return (unsigned int)v9;
    }
    else
    {
      DwordValue = RegQueryDwordValue(hKey, a3, a4);
      RegCloseKey(hKey);
      return DwordValue;
    }
  }
  return result;
}

```

## disassembly

```asm
0x180011d9c  push    rbx
0x180011d9e  push    rbp
0x180011d9f  push    rsi
0x180011da0  push    rdi
0x180011da1  sub     rsp, 58h
0x180011da5  mov     rax, cs:__security_cookie
0x180011dac  xor     rax, rsp
0x180011daf  mov     [rsp+78h+var_38], rax
0x180011db4  mov     [rsp+78h+hKey], 0
0x180011dbd  mov     rbx, r9
0x180011dc0  mov     [rsp+78h+samDesired], 1
0x180011dc8  mov     rdi, r8
0x180011dcb  mov     rbp, rdx
0x180011dce  mov     rsi, rcx
0x180011dd1  test    r9, r9
0x180011dd4  jnz     short loc_180011DDD
0x180011dd6  mov     eax, 80070057h
0x180011ddb  jmp     short loc_180011E44
0x180011ddd  lea     rdx, [rsp+78h+samDesired]
0x180011de2  mov     dword ptr [r9], 0
0x180011de9  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x180011dee  test    eax, eax
0x180011df0  js      short loc_180011E44
0x180011df2  mov     r9d, [rsp+78h+samDesired]; samDesired
0x180011df7  lea     rax, [rsp+78h+hKey]
0x180011dfc  xor     r8d, r8d; ulOptions
0x180011dff  mov     [rsp+78h+phkResult], rax; phkResult
0x180011e04  mov     rdx, rbp; lpSubKey
0x180011e07  mov     rcx, rsi; hKey
0x180011e0a  call    cs:__imp_RegOpenKeyExW
0x180011e10  mov     ecx, eax
0x180011e12  test    eax, eax
0x180011e14  jz      short loc_180011E25
0x180011e16  movzx   eax, cx
0x180011e19  or      eax, 80070000h
0x180011e1e  test    ecx, ecx
0x180011e20  cmovle  eax, ecx
0x180011e23  jmp     short loc_180011E44
0x180011e25  mov     rcx, [rsp+78h+hKey]; HKEY
0x180011e2a  mov     r8, rbx; unsigned int *
0x180011e2d  mov     rdx, rdi; wchar_t *
0x180011e30  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x180011e35  mov     rcx, [rsp+78h+hKey]; hKey
0x180011e3a  mov     ebx, eax
0x180011e3c  call    cs:__imp_RegCloseKey
0x180011e42  mov     eax, ebx
0x180011e44  mov     rcx, [rsp+78h+var_38]
0x180011e49  xor     rcx, rsp; StackCookie
0x180011e4c  call    __security_check_cookie
0x180011e51  add     rsp, 58h
0x180011e55  pop     rdi
0x180011e56  pop     rsi
0x180011e57  pop     rbp
0x180011e58  pop     rbx
0x180011e59  retn
```
