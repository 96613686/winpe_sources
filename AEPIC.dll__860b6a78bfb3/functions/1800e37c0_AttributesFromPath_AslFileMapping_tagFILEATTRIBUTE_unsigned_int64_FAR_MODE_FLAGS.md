# _AttributesFromPath(AslFileMapping &,tagFILEATTRIBUTE *,unsigned __int64,FAR_MODE_FLAGS)

- ea: `0x1800e37c0`
- end: `0x1800e3907`
- name: `?_AttributesFromPath@@YAJAEAVAslFileMapping@@PEAUtagFILEATTRIBUTE@@_KW4FAR_MODE_FLAGS@@@Z`
- size: `327`
- prototype: `__int64 __fastcall(LPCWSTR **, __int64, int)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, broker_com_uri`

## callees

- `0x180005890`
- `0x180006938`
- `0x18000cb30`
- `0x1800295dc`
- `0x1800e37c0`
- `0x1800e4084`
- `0x1800e4548`

## import_xrefs

- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800e38bc`
- `api-ms-win-core-path-l1-1-0!PathCchRemoveFileSpec` at `0x1800e38bc`

## string_xrefs

- `0x1800e3890`: `StringCchCopyW failed to copy full path [%x]`
- `0x1800e38a1`: `_AttributesFromPath`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall _AttributesFromPath(LPCWSTR **a1, __int64 a2, int a3)
{
  unsigned int v6; // ebx
  int v7; // eax
  size_t v8; // r11
  int IsOsComponent; // [rsp+30h] [rbp-238h] BYREF
  unsigned __int64 v11; // [rsp+38h] [rbp-230h] BYREF
  WCHAR pszPath[264]; // [rsp+40h] [rbp-228h] BYREF

  IsOsComponent = 0;
  memset_0(pszPath, 0, 0x208u);
  if ( a2 )
  {
    if ( (a3 & 4) != 0 )
    {
      IsOsComponent = _IsOsComponent(**a1);
      _SetFileAttributeValue(&IsOsComponent, 4, 2, a2);
    }
    if ( (*(_QWORD *)&a3 & 0x40000LL) != 0 )
    {
      v11 = 0xBAD0BAD0BAD0BAD0uLL;
      _SetFileAttributeValue(&v11, 8, 18, a2);
    }
    if ( (a3 & 2) != 0 )
    {
      v7 = StringCchCopyW(pszPath, 0x104u, **a1);
      v6 = v7;
      if ( v7 < 0 )
      {
        AslLogCallPrintf(1, "_AttributesFromPath", 1415, "StringCchCopyW failed to copy full path [%x]", v7);
        return v6;
      }
      if ( PathCchRemoveFileSpec(pszPath, v8) >= 0 )
        _SetFileAttributeValue(pszPath, 520, 1, a2);
    }
    return 0;
  }
  return (unsigned int)-2147024809;
}

```

## disassembly

```asm
0x1800e37c0  mov     [rsp+arg_10], rbx
0x1800e37c5  mov     [rsp+arg_18], rsi
0x1800e37ca  push    rdi
0x1800e37cb  sub     rsp, 260h
0x1800e37d2  mov     rax, cs:__security_cookie
0x1800e37d9  xor     rax, rsp
0x1800e37dc  mov     [rsp+268h+var_18], rax
0x1800e37e4  mov     rbx, r8
0x1800e37e7  mov     [rsp+268h+var_238], 0
0x1800e37ef  mov     rdi, rdx
0x1800e37f2  mov     rsi, rcx
0x1800e37f5  xor     edx, edx; Val
0x1800e37f7  lea     rcx, [rsp+268h+pszPath]; void *
0x1800e37fc  mov     r8d, 208h; Size
0x1800e3802  call    memset_0
0x1800e3807  test    rdi, rdi
0x1800e380a  jnz     short loc_1800E3816
0x1800e380c  mov     ebx, 80070057h
0x1800e3811  jmp     loc_1800E38E0
0x1800e3816  test    bl, 4
0x1800e3819  jz      short loc_1800E3840
0x1800e381b  mov     rcx, [rsi]
0x1800e381e  mov     rcx, [rcx]; lpFileName
0x1800e3821  call    ?_IsOsComponent@@YAHPEBG@Z; _IsOsComponent(ushort const *)
0x1800e3826  mov     edx, 4
0x1800e382b  mov     [rsp+268h+var_238], eax
0x1800e382f  mov     r9, rdi
0x1800e3832  lea     rcx, [rsp+268h+var_238]
0x1800e3837  lea     r8d, [rdx-2]
0x1800e383b  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e3840  bt      rbx, 12h
0x1800e3845  jnb     short loc_1800E386C
0x1800e3847  mov     edx, 8
0x1800e384c  lea     rcx, [rsp+268h+var_230]
0x1800e3851  mov     rax, 0BAD0BAD0BAD0BAD0h
0x1800e385b  mov     r9, rdi
0x1800e385e  mov     [rsp+268h+var_230], rax
0x1800e3863  lea     r8d, [rdx+0Ah]
0x1800e3867  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e386c  test    bl, 2
0x1800e386f  jz      short loc_1800E38DE
0x1800e3871  mov     r8, [rsi]
0x1800e3874  lea     rcx, [rsp+268h+pszPath]; unsigned __int16 *
0x1800e3879  mov     r11d, 104h
0x1800e387f  mov     edx, r11d; unsigned __int64
0x1800e3882  mov     r8, [r8]; unsigned __int16 *
0x1800e3885  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800e388a  mov     ebx, eax
0x1800e388c  test    eax, eax
0x1800e388e  jns     short loc_1800E38B4
0x1800e3890  lea     r9, aStringcchcopyw_1; "StringCchCopyW failed to copy full path"...
0x1800e3897  mov     [rsp+268h+var_248], eax
0x1800e389b  mov     r8d, 587h
0x1800e38a1  lea     rdx, aAttributesfrom; "_AttributesFromPath"
0x1800e38a8  mov     ecx, 1
0x1800e38ad  call    AslLogCallPrintf
0x1800e38b2  jmp     short loc_1800E38E0
0x1800e38b4  mov     rdx, r11; cchPath
0x1800e38b7  lea     rcx, [rsp+268h+pszPath]; pszPath
0x1800e38bc  call    cs:__imp_PathCchRemoveFileSpec
0x1800e38c2  test    eax, eax
0x1800e38c4  js      short loc_1800E38DE
0x1800e38c6  mov     r9, rdi
0x1800e38c9  lea     rcx, [rsp+268h+pszPath]
0x1800e38ce  mov     edx, 208h
0x1800e38d3  mov     r8d, 1
0x1800e38d9  call    ?_SetFileAttributeValue@@YAJPEBXKW4FILEATTRID@@PEAUtagFILEATTRIBUTE@@@Z; _SetFileAttributeValue(void const *,ulong,FILEATTRID,tagFILEATTRIBUTE *)
0x1800e38de  xor     ebx, ebx
0x1800e38e0  mov     eax, ebx
0x1800e38e2  mov     rcx, [rsp+268h+var_18]
0x1800e38ea  xor     rcx, rsp; StackCookie
0x1800e38ed  call    __security_check_cookie
0x1800e38f2  lea     r11, [rsp+268h+var_8]
0x1800e38fa  mov     rbx, [r11+20h]
0x1800e38fe  mov     rsi, [r11+28h]
0x1800e3902  mov     rsp, r11
0x1800e3905  pop     rdi
0x1800e3906  retn
```
