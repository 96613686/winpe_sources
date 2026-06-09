# CARPFolder::_GetIconInfo(ushort const *,uint,ushort *,int *)

- ea: `0x18001a0f8`
- end: `0x18001a1ef`
- name: `?_GetIconInfo@CARPFolder@@AEAAJPEBGIPEAGPEAH@Z`
- size: `247`
- prototype: `int(CARPFolder *__hidden this, const unsigned __int16 *, unsigned int, unsigned __int16 *, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x1800158c0`

## callees

- `0x180007960`
- `0x18001a0f8`
- `0x1800582e0`

## import_xrefs

- `SHLWAPI!PathParseIconLocationW` at `0x18001a1be`
- `SHLWAPI!PathParseIconLocationW` at `0x18001a1be`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a19c`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001a19c`

## string_xrefs

- `0x18001a141`: `CLSID`

## pseudocode

```c
__int64 __fastcall CARPFolder::_GetIconInfo(
        CARPFolder *this,
        const unsigned __int16 *a2,
        __int64 a3,
        unsigned __int16 *a4,
        int *a5)
{
  int v6; // ebx
  LSTATUS ValueW; // eax
  bool v8; // sf
  DWORD pcbData[4]; // [rsp+40h] [rbp-238h] BYREF
  WCHAR SubKey[264]; // [rsp+50h] [rbp-228h] BYREF

  v6 = StringCchPrintfW(
         SubKey,
         0x104u,
         L"%s\\%s\\%s",
         L"CLSID",
         L"{d450a8a1-9568-45c7-9c0e-b4f9fb4537bd}",
         L"DefaultIcon");
  if ( v6 >= 0 )
  {
    pcbData[0] = 520;
    v6 = -2147467259;
    ValueW = RegGetValueW(HKEY_CLASSES_ROOT, SubKey, 0, 2u, 0, a4, pcbData);
    v8 = ValueW < 0;
    if ( ValueW )
    {
      *a4 = 0;
      v8 = ValueW < 0;
      if ( ValueW > 0 )
        v8 = 1;
    }
    if ( !v8 )
    {
      *a5 = PathParseIconLocationW(a4);
      return 0;
    }
  }
  return (unsigned int)v6;
}

```

## disassembly

```asm
0x18001a0f8  mov     [rsp+arg_0], rbx
0x18001a0fd  mov     [rsp+arg_8], rsi
0x18001a102  push    rdi
0x18001a103  sub     rsp, 270h
0x18001a10a  mov     rax, cs:__security_cookie
0x18001a111  xor     rax, rsp
0x18001a114  mov     [rsp+278h+var_18], rax
0x18001a11c  mov     rsi, [rsp+278h+arg_20]
0x18001a124  lea     rax, aDefaulticon; "DefaultIcon"
0x18001a12b  mov     [rsp+278h+pvData], rax
0x18001a130  lea     r8, aSSS; "%s\\%s\\%s"
0x18001a137  lea     rax, aD450a8a1956845; "{d450a8a1-9568-45c7-9c0e-b4f9fb4537bd}"
0x18001a13e  mov     rdi, r9
0x18001a141  lea     r9, aClsid; "CLSID"
0x18001a148  mov     [rsp+278h+pdwType], rax
0x18001a14d  mov     edx, 104h; unsigned __int64
0x18001a152  lea     rcx, [rsp+278h+SubKey]; unsigned __int16 *
0x18001a157  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18001a15c  mov     ebx, eax
0x18001a15e  test    eax, eax
0x18001a160  js      short loc_18001A1C8
0x18001a162  lea     rax, [rsp+278h+var_238]
0x18001a167  mov     [rsp+278h+var_238], 208h
0x18001a16f  mov     [rsp+278h+pcbData], rax; pcbData
0x18001a174  lea     rdx, [rsp+278h+SubKey]; lpSubKey
0x18001a179  mov     [rsp+278h+pvData], rdi; pvData
0x18001a17e  mov     r9d, 2; dwFlags
0x18001a184  xor     r8d, r8d; lpValue
0x18001a187  mov     [rsp+278h+pdwType], 0; pdwType
0x18001a190  mov     rcx, 0FFFFFFFF80000000h; hkey
0x18001a197  mov     ebx, 80004005h
0x18001a19c  call    cs:__imp_RegGetValueW
0x18001a1a2  test    eax, eax
0x18001a1a4  jz      short loc_18001A1B9
0x18001a1a6  xor     ecx, ecx
0x18001a1a8  mov     [rdi], cx
0x18001a1ab  test    eax, eax
0x18001a1ad  jle     short loc_18001A1B9
0x18001a1af  movzx   eax, ax
0x18001a1b2  or      eax, 80070000h
0x18001a1b7  test    eax, eax
0x18001a1b9  js      short loc_18001A1C8
0x18001a1bb  mov     rcx, rdi; pszIconFile
0x18001a1be  call    cs:__imp_PathParseIconLocationW
0x18001a1c4  mov     [rsi], eax
0x18001a1c6  xor     ebx, ebx
0x18001a1c8  mov     eax, ebx
0x18001a1ca  mov     rcx, [rsp+278h+var_18]
0x18001a1d2  xor     rcx, rsp; StackCookie
0x18001a1d5  call    __security_check_cookie
0x18001a1da  lea     r11, [rsp+278h+var_8]
0x18001a1e2  mov     rbx, [r11+10h]
0x18001a1e6  mov     rsi, [r11+18h]
0x18001a1ea  mov     rsp, r11
0x18001a1ed  pop     rdi
0x18001a1ee  retn
```
