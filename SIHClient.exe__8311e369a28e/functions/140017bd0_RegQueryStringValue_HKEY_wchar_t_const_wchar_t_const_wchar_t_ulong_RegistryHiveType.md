# RegQueryStringValue(HKEY__ *,wchar_t const *,wchar_t const *,wchar_t *,ulong,RegistryHiveType)

- ea: `0x140017bd0`
- end: `0x140017c97`
- name: `?RegQueryStringValue@@YAJPEAUHKEY__@@PEB_W1PEA_WKW4RegistryHiveType@@@Z`
- size: `199`
- prototype: `__int64 __fastcall(__int64, const WCHAR *, __int64, __int64, int)`
- caller_count: `10`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x14000add0`
- `0x1400254e8`
- `0x140032b84`
- `0x140032cc0`
- `0x140032fd0`
- `0x14003401c`
- `0x1400364ac`
- `0x14003689c`
- `0x1400370fc`
- `0x14003dcf8`

## callees

- `0x1400176fc`
- `0x140017bd0`
- `0x140044a34`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017c7a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017c7a`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140017c2b`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x140017c2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall RegQueryStringValue(__int64 a1, const WCHAR *a2, __int64 a3, __int64 a4, int a5)
{
  __int64 result; // rax
  LSTATUS v9; // eax
  int v10; // ecx
  unsigned int ValueCchHelper; // ebx
  REGSAM samDesired; // [rsp+40h] [rbp-38h] BYREF
  HKEY hKey; // [rsp+48h] [rbp-30h] BYREF

  hKey = 0;
  samDesired = 1;
  result = SetRegistryType(a1, &samDesired);
  if ( (int)result >= 0 )
  {
    v9 = RegOpenKeyExW(HKEY_LOCAL_MACHINE, a2, 0, samDesired, &hKey);
    v10 = v9;
    if ( v9 )
    {
      result = (unsigned __int16)v9 | 0x80070000;
      if ( v10 <= 0 )
        return (unsigned int)v10;
    }
    else
    {
      ValueCchHelper = SafeRegQueryValueCchHelper(0, hKey, a3, a4, a5, 0, 0);
      RegCloseKey(hKey);
      return ValueCchHelper;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140017bd0  push    rbx
0x140017bd2  push    rsi
0x140017bd3  push    rdi
0x140017bd4  sub     rsp, 60h
0x140017bd8  mov     rax, cs:__security_cookie
0x140017bdf  xor     rax, rsp
0x140017be2  mov     [rsp+78h+var_28], rax
0x140017be7  mov     rbx, rdx
0x140017bea  mov     [rsp+78h+hKey], 0
0x140017bf3  lea     rdx, [rsp+78h+samDesired]
0x140017bf8  mov     [rsp+78h+samDesired], 1
0x140017c00  mov     rsi, r9
0x140017c03  mov     rdi, r8
0x140017c06  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x140017c0b  test    eax, eax
0x140017c0d  js      short loc_140017C82
0x140017c0f  mov     r9d, [rsp+78h+samDesired]; samDesired
0x140017c14  lea     rax, [rsp+78h+hKey]
0x140017c19  xor     r8d, r8d; ulOptions
0x140017c1c  mov     [rsp+78h+phkResult], rax; phkResult
0x140017c21  mov     rdx, rbx; lpSubKey
0x140017c24  mov     rcx, 0FFFFFFFF80000002h; hKey
0x140017c2b  call    cs:__imp_RegOpenKeyExW
0x140017c31  mov     ecx, eax
0x140017c33  test    eax, eax
0x140017c35  jz      short loc_140017C46
0x140017c37  movzx   eax, cx
0x140017c3a  or      eax, 80070000h
0x140017c3f  test    ecx, ecx
0x140017c41  cmovle  eax, ecx
0x140017c44  jmp     short loc_140017C82
0x140017c46  mov     eax, [rsp+78h+arg_20]
0x140017c4d  mov     r9, rsi
0x140017c50  mov     rdx, [rsp+78h+hKey]
0x140017c55  mov     r8, rdi
0x140017c58  mov     [rsp+78h+var_48], 0
0x140017c61  mov     [rsp+78h+var_50], 0
0x140017c6a  mov     dword ptr [rsp+78h+phkResult], eax
0x140017c6e  call    SafeRegQueryValueCchHelper
0x140017c73  mov     rcx, [rsp+78h+hKey]; hKey
0x140017c78  mov     ebx, eax
0x140017c7a  call    cs:__imp_RegCloseKey
0x140017c80  mov     eax, ebx
0x140017c82  mov     rcx, [rsp+78h+var_28]
0x140017c87  xor     rcx, rsp; StackCookie
0x140017c8a  call    __security_check_cookie
0x140017c8f  add     rsp, 60h
0x140017c93  pop     rdi
0x140017c94  pop     rsi
0x140017c95  pop     rbx
0x140017c96  retn
```
