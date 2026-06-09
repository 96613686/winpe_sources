# RegQueryDwordValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *,RegistryHiveType)

- ea: `0x1400177e0`
- end: `0x14001789e`
- name: `?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_W1PEAKW4RegistryHiveType@@@Z`
- size: `190`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `8`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x140016108`
- `0x140027c50`
- `0x140030dd8`
- `0x14003261c`
- `0x1400356ac`
- `0x14003e2a4`
- `0x14003e34c`
- `0x14003f0d8`

## callees

- `0x1400176fc`
- `0x1400177e0`
- `0x1400178a4`
- `0x140045dc0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017880`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x140017880`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001784e`
- `api-ms-win-core-registry-l1-1-0!RegOpenKeyExW` at `0x14001784e`

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
  result = SetRegistryType((int)a1, &samDesired);
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
0x1400177e0  push    rbx
0x1400177e2  push    rbp
0x1400177e3  push    rsi
0x1400177e4  push    rdi
0x1400177e5  sub     rsp, 58h
0x1400177e9  mov     rax, cs:__security_cookie
0x1400177f0  xor     rax, rsp
0x1400177f3  mov     [rsp+78h+var_38], rax
0x1400177f8  mov     [rsp+78h+hKey], 0
0x140017801  mov     rbx, r9
0x140017804  mov     [rsp+78h+samDesired], 1
0x14001780c  mov     rdi, r8
0x14001780f  mov     rbp, rdx
0x140017812  mov     rsi, rcx
0x140017815  test    r9, r9
0x140017818  jnz     short loc_140017821
0x14001781a  mov     eax, 80070057h
0x14001781f  jmp     short loc_140017888
0x140017821  lea     rdx, [rsp+78h+samDesired]
0x140017826  mov     dword ptr [r9], 0
0x14001782d  call    ?SetRegistryType@@YAJW4RegistryHiveType@@PEAK@Z; SetRegistryType(RegistryHiveType,ulong *)
0x140017832  test    eax, eax
0x140017834  js      short loc_140017888
0x140017836  mov     r9d, [rsp+78h+samDesired]; samDesired
0x14001783b  lea     rax, [rsp+78h+hKey]
0x140017840  xor     r8d, r8d; ulOptions
0x140017843  mov     [rsp+78h+phkResult], rax; phkResult
0x140017848  mov     rdx, rbp; lpSubKey
0x14001784b  mov     rcx, rsi; hKey
0x14001784e  call    cs:__imp_RegOpenKeyExW
0x140017854  mov     ecx, eax
0x140017856  test    eax, eax
0x140017858  jz      short loc_140017869
0x14001785a  movzx   eax, cx
0x14001785d  or      eax, 80070000h
0x140017862  test    ecx, ecx
0x140017864  cmovle  eax, ecx
0x140017867  jmp     short loc_140017888
0x140017869  mov     rcx, [rsp+78h+hKey]; HKEY
0x14001786e  mov     r8, rbx; unsigned int *
0x140017871  mov     rdx, rdi; wchar_t *
0x140017874  call    ?RegQueryDwordValue@@YAJPEAUHKEY__@@PEB_WPEAK@Z; RegQueryDwordValue(HKEY__ *,wchar_t const *,ulong *)
0x140017879  mov     rcx, [rsp+78h+hKey]; hKey
0x14001787e  mov     ebx, eax
0x140017880  call    cs:__imp_RegCloseKey
0x140017886  mov     eax, ebx
0x140017888  mov     rcx, [rsp+78h+var_38]
0x14001788d  xor     rcx, rsp; StackCookie
0x140017890  call    __security_check_cookie
0x140017895  add     rsp, 58h
0x140017899  pop     rdi
0x14001789a  pop     rsi
0x14001789b  pop     rbp
0x14001789c  pop     rbx
0x14001789d  retn
```
