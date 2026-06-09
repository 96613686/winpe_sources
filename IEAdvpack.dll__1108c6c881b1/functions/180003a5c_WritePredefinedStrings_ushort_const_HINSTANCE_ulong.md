# WritePredefinedStrings(ushort const *,HINSTANCE__ *,ulong)

- ea: `0x180003a5c`
- end: `0x180003b46`
- name: `?WritePredefinedStrings@@YAJPEBGPEAUHINSTANCE__@@K@Z`
- size: `234`
- prototype: `__int64 __fastcall(const unsigned __int16 *, HINSTANCE hModule, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: ``

## callers

- `0x180003be0`

## callees

- `0x18000279c`
- `0x180002eb0`
- `0x180003180`
- `0x180003a5c`
- `0x1800045e8`
- `0x18001b980`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180003aa6`
- `KERNEL32!GetModuleFileNameW` at `0x180003aa6`

## string_xrefs

- `0x180003ad4`: `_MOD_PATH`
- `0x180003b11`: `_SYS_MOD_PATH`

## pseudocode

```c
__int64 __fastcall WritePredefinedStrings(const unsigned __int16 *a1, HINSTANCE hModule, unsigned int a3)
{
  unsigned int v5; // ebx
  const unsigned __int16 *v6; // rcx
  const unsigned __int16 *v7; // rcx
  unsigned __int16 v9; // [rsp+30h] [rbp-228h] BYREF
  WCHAR Filename[263]; // [rsp+32h] [rbp-226h] BYREF

  v9 = 34;
  v5 = -2147467259;
  if ( GetModuleFileNameW(hModule, Filename, 0x104u) )
  {
    StringCchCatW(&v9, 262, L"\"");
    MySmartWrite(v6, L"_MOD_PATH", &v9, a1, a3);
    if ( (unsigned int)CheckOSVersion() && ctx >= 2u )
      AddEnvInPath(&v9, &v9, 0x106u);
    MySmartWrite(v7, L"_SYS_MOD_PATH", &v9, a1, a3);
    return 0;
  }
  return v5;
}

```

## disassembly

```asm
0x180003a5c  mov     [rsp+arg_10], rbx
0x180003a61  mov     [rsp+arg_18], rsi
0x180003a66  push    rdi
0x180003a67  sub     rsp, 250h
0x180003a6e  mov     rax, cs:__security_cookie
0x180003a75  xor     rax, rsp
0x180003a78  mov     [rsp+258h+var_18], rax
0x180003a80  mov     rsi, rcx
0x180003a83  mov     rax, rdx
0x180003a86  mov     ecx, 22h ; '"'
0x180003a8b  lea     rdx, [rsp+258h+Filename]; lpFilename
0x180003a90  mov     [rsp+258h+var_228], cx
0x180003a95  mov     edi, r8d
0x180003a98  mov     rcx, rax; hModule
0x180003a9b  mov     r8d, 104h; nSize
0x180003aa1  mov     ebx, 80004005h
0x180003aa6  call    cs:__imp_GetModuleFileNameW
0x180003aac  test    eax, eax
0x180003aae  jz      short loc_180003B1F
0x180003ab0  mov     ebx, 106h
0x180003ab5  lea     r8, asc_18001DCCC; "\""
0x180003abc  mov     edx, ebx; unsigned __int64
0x180003abe  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x180003ac3  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180003ac8  mov     r9, rsi; unsigned __int16 *
0x180003acb  mov     [rsp+258h+var_238], edi; unsigned int
0x180003acf  lea     r8, [rsp+258h+var_228]; unsigned __int16 *
0x180003ad4  lea     rdx, aModPath; "_MOD_PATH"
0x180003adb  call    ?MySmartWrite@@YAHPEBG000K@Z; MySmartWrite(ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x180003ae0  call    ?CheckOSVersion@@YAHXZ; CheckOSVersion(void)
0x180003ae5  test    eax, eax
0x180003ae7  jz      short loc_180003B05
0x180003ae9  cmp     cs:?ctx@@3UADVCONTEXTW@@A, 2; ADVCONTEXTW ctx
0x180003af1  jb      short loc_180003B05
0x180003af3  mov     r8d, ebx; unsigned int
0x180003af6  lea     rdx, [rsp+258h+var_228]; unsigned __int16 *
0x180003afb  lea     rcx, [rsp+258h+var_228]; unsigned __int16 *
0x180003b00  call    ?AddEnvInPath@@YAHPEBGPEAGK@Z; AddEnvInPath(ushort const *,ushort *,ulong)
0x180003b05  mov     r9, rsi; unsigned __int16 *
0x180003b08  mov     [rsp+258h+var_238], edi; unsigned int
0x180003b0c  lea     r8, [rsp+258h+var_228]; unsigned __int16 *
0x180003b11  lea     rdx, aSysModPath; "_SYS_MOD_PATH"
0x180003b18  call    ?MySmartWrite@@YAHPEBG000K@Z; MySmartWrite(ushort const *,ushort const *,ushort const *,ushort const *,ulong)
0x180003b1d  xor     ebx, ebx
0x180003b1f  mov     eax, ebx
0x180003b21  mov     rcx, [rsp+258h+var_18]
0x180003b29  xor     rcx, rsp; StackCookie
0x180003b2c  call    __security_check_cookie
0x180003b31  lea     r11, [rsp+258h+var_8]
0x180003b39  mov     rbx, [r11+20h]
0x180003b3d  mov     rsi, [r11+28h]
0x180003b41  mov     rsp, r11
0x180003b44  pop     rdi
0x180003b45  retn
```
