# GetBestLcidMatch(HKEY__ *,ulong,ulong *)

- ea: `0x1801124d4`
- end: `0x1801126c4`
- name: `?GetBestLcidMatch@@YAJPEAUHKEY__@@KPEAK@Z`
- size: `496`
- prototype: `__int64 __fastcall(HKEY, unsigned int, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x1801158b0`
- `0x18011a904`

## callees

- `0x1801124d4`
- `0x1802127e8`
- `0x180379520`

## import_xrefs

- `MSVCR100!_ultoa_s` at `0x18011250e`
- `MSVCR100!_ultoa_s` at `0x1801125a3`
- `MSVCR100!_ultoa_s` at `0x18011250e`
- `MSVCR100!_ultoa_s` at `0x1801125a3`
- `ADVAPI32!RegOpenKeyA` at `0x180112523`
- `ADVAPI32!RegOpenKeyA` at `0x1801125b8`
- `ADVAPI32!RegOpenKeyA` at `0x180112636`
- `ADVAPI32!RegOpenKeyA` at `0x180112523`
- `ADVAPI32!RegOpenKeyA` at `0x1801125b8`
- `ADVAPI32!RegOpenKeyA` at `0x180112636`
- `ADVAPI32!RegCloseKey` at `0x18011257a`
- `ADVAPI32!RegCloseKey` at `0x18011260f`
- `ADVAPI32!RegCloseKey` at `0x180112681`
- `ADVAPI32!RegCloseKey` at `0x180112693`
- `ADVAPI32!RegCloseKey` at `0x18011269e`
- `ADVAPI32!RegCloseKey` at `0x18011257a`
- `ADVAPI32!RegCloseKey` at `0x18011260f`
- `ADVAPI32!RegCloseKey` at `0x180112681`
- `ADVAPI32!RegCloseKey` at `0x180112693`
- `ADVAPI32!RegCloseKey` at `0x18011269e`

## pseudocode

```c
__int64 __fastcall GetBestLcidMatch(HKEY a1, unsigned int a2, unsigned int *a3)
{
  HKEY phkResult; // [rsp+20h] [rbp-30h] BYREF
  HKEY v5; // [rsp+28h] [rbp-28h] BYREF
  char Buffer[16]; // [rsp+30h] [rbp-20h] BYREF
  unsigned int Value; // [rsp+68h] [rbp+18h]

  Value = a2;
  _ultoa_s(a2, Buffer, 0xAu, 16);
  if ( !RegOpenKeyA(a1, Buffer, &phkResult) )
  {
    if ( !oRegOpenKey(phkResult, L"win64", &v5) || !oRegOpenKey(phkResult, L"win32", &v5) )
      goto LABEL_14;
    RegCloseKey(phkResult);
  }
  Value &= 0x3FFu;
  _ultoa_s(Value, Buffer, 0xAu, 16);
  if ( !RegOpenKeyA(a1, Buffer, &phkResult) )
  {
    if ( !oRegOpenKey(phkResult, L"win64", &v5) || !oRegOpenKey(phkResult, L"win32", &v5) )
      goto LABEL_14;
    RegCloseKey(phkResult);
  }
  Value = 0;
  strcpy(Buffer, "0");
  if ( RegOpenKeyA(a1, Buffer, &phkResult) )
    return 2147647517LL;
  if ( oRegOpenKey(phkResult, L"win64", &v5) && oRegOpenKey(phkResult, L"win32", &v5) )
  {
    RegCloseKey(phkResult);
    return 2147647517LL;
  }
LABEL_14:
  RegCloseKey(v5);
  RegCloseKey(phkResult);
  *a3 = Value;
  return 0;
}

```

## disassembly

```asm
0x1801124d4  mov     [rsp-8+arg_10], r8
0x1801124d9  mov     [rsp-8+Value], edx
0x1801124dd  mov     [rsp-8+hKey], rcx
0x1801124e2  push    rbp
0x1801124e3  mov     rbp, rsp
0x1801124e6  sub     rsp, 50h
0x1801124ea  mov     rax, cs:__security_cookie
0x1801124f1  xor     rax, rsp
0x1801124f4  mov     [rsp+50h+var_10], rax
0x1801124f9  mov     r9d, 10h; Radix
0x1801124ff  mov     r8d, 0Ah; BufferCount
0x180112505  lea     rdx, [rsp+50h+Buffer]; Buffer
0x18011250a  mov     ecx, [rsp+50h+Value]; Value
0x18011250e  call    cs:__imp__ultoa_s
0x180112514  lea     r8, [rsp+50h+phkResult]; phkResult
0x180112519  lea     rdx, [rsp+50h+Buffer]; lpSubKey
0x18011251e  mov     rcx, [rsp+50h+hKey]; hKey
0x180112523  call    cs:__imp_RegOpenKeyA
0x180112529  test    eax, eax
0x18011252b  jnz     short loc_180112580
0x18011252d  lea     r8, [rsp+50h+var_28]; phkResult
0x180112532  lea     rdx, aWin64_0; "win64"
0x180112539  mov     rcx, [rsp+50h+phkResult]; hKey
0x18011253e  call    oRegOpenKey
0x180112543  test    eax, eax
0x180112545  jnz     short loc_180112551
0x180112547  jmp     loc_18011268E
0x18011254c  jmp     loc_18011268E
0x180112551  lea     r8, [rsp+50h+var_28]; phkResult
0x180112556  lea     rdx, aWin32_0; "win32"
0x18011255d  mov     rcx, [rsp+50h+phkResult]; hKey
0x180112562  call    oRegOpenKey
0x180112567  test    eax, eax
0x180112569  jnz     short loc_180112575
0x18011256b  jmp     loc_18011268E
0x180112570  jmp     loc_18011268E
0x180112575  mov     rcx, [rsp+50h+phkResult]; hKey
0x18011257a  call    cs:__imp_RegCloseKey
0x180112580  movzx   eax, word ptr [rsp+50h+Value]
0x180112585  and     eax, 3FFh
0x18011258a  mov     [rsp+50h+Value], eax
0x18011258e  mov     r9d, 10h; Radix
0x180112594  mov     r8d, 0Ah; BufferCount
0x18011259a  lea     rdx, [rsp+50h+Buffer]; Buffer
0x18011259f  mov     ecx, [rsp+50h+Value]; Value
0x1801125a3  call    cs:__imp__ultoa_s
0x1801125a9  lea     r8, [rsp+50h+phkResult]; phkResult
0x1801125ae  lea     rdx, [rsp+50h+Buffer]; lpSubKey
0x1801125b3  mov     rcx, [rsp+50h+hKey]; hKey
0x1801125b8  call    cs:__imp_RegOpenKeyA
0x1801125be  test    eax, eax
0x1801125c0  jnz     short loc_180112615
0x1801125c2  lea     r8, [rsp+50h+var_28]; phkResult
0x1801125c7  lea     rdx, aWin64_0; "win64"
0x1801125ce  mov     rcx, [rsp+50h+phkResult]; hKey
0x1801125d3  call    oRegOpenKey
0x1801125d8  test    eax, eax
0x1801125da  jnz     short loc_1801125E6
0x1801125dc  jmp     loc_18011268E
0x1801125e1  jmp     loc_18011268E
0x1801125e6  lea     r8, [rsp+50h+var_28]; phkResult
0x1801125eb  lea     rdx, aWin32_0; "win32"
0x1801125f2  mov     rcx, [rsp+50h+phkResult]; hKey
0x1801125f7  call    oRegOpenKey
0x1801125fc  test    eax, eax
0x1801125fe  jnz     short loc_18011260A
0x180112600  jmp     loc_18011268E
0x180112605  jmp     loc_18011268E
0x18011260a  mov     rcx, [rsp+50h+phkResult]; hKey
0x18011260f  call    cs:__imp_RegCloseKey
0x180112615  mov     [rsp+50h+Value], 0
0x18011261d  mov     [rsp+50h+Buffer], 30h ; '0'
0x180112622  mov     [rsp+50h+var_1F], 0
0x180112627  lea     r8, [rsp+50h+phkResult]; phkResult
0x18011262c  lea     rdx, [rsp+50h+Buffer]; lpSubKey
0x180112631  mov     rcx, [rsp+50h+hKey]; hKey
0x180112636  call    cs:__imp_RegOpenKeyA
0x18011263c  test    eax, eax
0x18011263e  jnz     short loc_180112687
0x180112640  lea     r8, [rsp+50h+var_28]; phkResult
0x180112645  lea     rdx, aWin64_0; "win64"
0x18011264c  mov     rcx, [rsp+50h+phkResult]; hKey
0x180112651  call    oRegOpenKey
0x180112656  test    eax, eax
0x180112658  jnz     short loc_18011265E
0x18011265a  jmp     short loc_18011268E
0x18011265c  jmp     short loc_18011268E
0x18011265e  lea     r8, [rsp+50h+var_28]; phkResult
0x180112663  lea     rdx, aWin32_0; "win32"
0x18011266a  mov     rcx, [rsp+50h+phkResult]; hKey
0x18011266f  call    oRegOpenKey
0x180112674  test    eax, eax
0x180112676  jnz     short loc_18011267C
0x180112678  jmp     short loc_18011268E
0x18011267a  jmp     short loc_18011268E
0x18011267c  mov     rcx, [rsp+50h+phkResult]; hKey
0x180112681  call    cs:__imp_RegCloseKey
0x180112687  mov     eax, 8002801Dh
0x18011268c  jmp     short loc_1801126B1
0x18011268e  mov     rcx, [rsp+50h+var_28]; hKey
0x180112693  call    cs:__imp_RegCloseKey
0x180112699  mov     rcx, [rsp+50h+phkResult]; hKey
0x18011269e  call    cs:__imp_RegCloseKey
0x1801126a4  mov     rax, [rsp+50h+arg_10]
0x1801126a9  mov     ecx, [rsp+50h+Value]
0x1801126ad  mov     [rax], ecx
0x1801126af  xor     eax, eax
0x1801126b1  mov     rcx, [rsp+50h+var_10]
0x1801126b6  xor     rcx, rsp; StackCookie
0x1801126b9  call    __security_check_cookie
0x1801126be  add     rsp, 50h
0x1801126c2  pop     rbp
0x1801126c3  retn
```
