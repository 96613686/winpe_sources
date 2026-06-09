# ATL::AtlLoadTypeLib(HINSTANCE__ *,ushort const *,ushort * *,ITypeLib * *)

- ea: `0x180002d14`
- end: `0x180002eb5`
- name: `?AtlLoadTypeLib@ATL@@YAJPEAUHINSTANCE__@@PEBGPEAPEAGPEAPEAUITypeLib@@@Z`
- size: `417`
- prototype: `int(HINSTANCE, const unsigned __int16 *, unsigned __int16 **, struct ITypeLib **)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180003378`
- `0x180004a74`

## callees

- `0x180002cd8`
- `0x180002d14`
- `0x180003558`
- `0x180005f60`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180002e22`
- `msvcrt!wcscpy_s` at `0x180002e22`
- `KERNEL32!GetModuleFileNameW` at `0x180002d5f`
- `KERNEL32!GetModuleFileNameW` at `0x180002d5f`
- `OLEAUT32!__imp_SysAllocString` at `0x180002e59`
- `OLEAUT32!__imp_SysAllocString` at `0x180002e59`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180002dcb`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180002e48`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180002dcb`
- `OLEAUT32!__imp_LoadTypeLib` at `0x180002e48`
- `USER32!CharNextW` at `0x180002daa`
- `USER32!CharNextW` at `0x180002daa`

## pseudocode

```c
__int64 __fastcall ATL::AtlLoadTypeLib(
        HINSTANCE a1,
        const unsigned __int16 *a2,
        unsigned __int16 **a3,
        struct ITypeLib **a4)
{
  DWORD ModuleFileNameW; // eax
  WCHAR v8; // ax
  WCHAR *v9; // rcx
  wchar_t *v10; // rdi
  HRESULT TypeLib; // ebx
  __int64 v12; // rcx
  errno_t v13; // eax
  unsigned __int16 *v14; // rax
  wchar_t Source[8]; // [rsp+20h] [rbp-268h] BYREF
  WCHAR Filename[272]; // [rsp+30h] [rbp-258h] BYREF

  if ( !a3 || !a4 )
    return 2147500035LL;
  *a3 = 0;
  *a4 = 0;
  ModuleFileNameW = GetModuleFileNameW(a1, Filename, 0x104u);
  if ( !ModuleFileNameW )
    return ATL::AtlHresultFromLastError();
  if ( ModuleFileNameW == 260 )
    return 2147942522LL;
  v8 = Filename[0];
  v9 = Filename;
  if ( !Filename[0] )
    goto LABEL_15;
  v10 = 0;
  do
  {
    if ( v8 == 46 )
    {
      v10 = v9;
    }
    else if ( v8 == 92 )
    {
      v10 = 0;
    }
    v9 = CharNextW(v9);
    v8 = *v9;
  }
  while ( *v9 );
  if ( !v10 )
LABEL_15:
    v10 = v9;
  TypeLib = LoadTypeLib(Filename, a4);
  if ( TypeLib >= 0 )
    goto LABEL_25;
  wcscpy(Source, L".tlb");
  v12 = v10 - Filename;
  if ( (unsigned __int64)(v12 + 5) > 0x104 )
    return 2147500037LL;
  v13 = wcscpy_s(v10, 270 - v12, Source);
  if ( v13 )
  {
    if ( v13 == 12 )
      ATL::AtlThrowImpl(-2147024882);
    if ( v13 == 22 || v13 == 34 )
      ATL::AtlThrowImpl(-2147024809);
    if ( v13 != 80 )
      ATL::AtlThrowImpl(-2147467259);
  }
  TypeLib = LoadTypeLib(Filename, a4);
  if ( TypeLib >= 0 )
  {
LABEL_25:
    v14 = SysAllocString(Filename);
    *a3 = v14;
    if ( !v14 )
      return (unsigned int)-2147024882;
  }
  return (unsigned int)TypeLib;
}

```

## disassembly

```asm
0x180002d14  push    rbx
0x180002d16  push    rbp
0x180002d17  push    rsi
0x180002d18  push    rdi
0x180002d19  push    r14
0x180002d1b  sub     rsp, 260h
0x180002d22  mov     rax, cs:__security_cookie
0x180002d29  xor     rax, rsp
0x180002d2c  mov     [rsp+288h+var_38], rax
0x180002d34  xor     ebp, ebp
0x180002d36  mov     rsi, r9
0x180002d39  mov     r14, r8
0x180002d3c  test    r8, r8
0x180002d3f  jz      loc_180002E71
0x180002d45  test    r9, r9
0x180002d48  jz      loc_180002E71
0x180002d4e  mov     [r8], rbp
0x180002d51  lea     rdx, [rsp+288h+Filename]; lpFilename
0x180002d56  mov     r8d, 104h; nSize
0x180002d5c  mov     [r9], rbp
0x180002d5f  call    cs:__imp_GetModuleFileNameW
0x180002d65  test    eax, eax
0x180002d67  jnz     short loc_180002D73
0x180002d69  call    ?AtlHresultFromLastError@ATL@@YAJXZ; ATL::AtlHresultFromLastError(void)
0x180002d6e  jmp     loc_180002E76
0x180002d73  cmp     eax, 104h
0x180002d78  jnz     short loc_180002D84
0x180002d7a  mov     eax, 8007007Ah
0x180002d7f  jmp     loc_180002E76
0x180002d84  movzx   eax, [rsp+288h+Filename]
0x180002d89  lea     rcx, [rsp+288h+Filename]; lpsz
0x180002d8e  test    ax, ax
0x180002d91  jz      short loc_180002DC0
0x180002d93  mov     rdi, rbp
0x180002d96  cmp     ax, 2Eh ; '.'
0x180002d9a  jz      short loc_180002DA7
0x180002d9c  cmp     ax, 5Ch ; '\'
0x180002da0  jnz     short loc_180002DAA
0x180002da2  mov     rdi, rbp
0x180002da5  jmp     short loc_180002DAA
0x180002da7  mov     rdi, rcx
0x180002daa  call    cs:__imp_CharNextW
0x180002db0  mov     rcx, rax
0x180002db3  movzx   eax, word ptr [rax]
0x180002db6  test    ax, ax
0x180002db9  jnz     short loc_180002D96
0x180002dbb  test    rdi, rdi
0x180002dbe  jnz     short loc_180002DC3
0x180002dc0  mov     rdi, rcx
0x180002dc3  mov     rdx, rsi; pptlib
0x180002dc6  lea     rcx, [rsp+288h+Filename]; szFile
0x180002dcb  call    cs:__imp_LoadTypeLib
0x180002dd1  mov     ebx, eax
0x180002dd3  test    eax, eax
0x180002dd5  jns     short loc_180002E54
0x180002dd7  movzx   eax, word ptr cs:aTlb+8; ""
0x180002dde  mov     rcx, rdi
0x180002de1  movsd   xmm0, qword ptr cs:aTlb; ".tlb"
0x180002de9  mov     [rsp+288h+var_260], ax
0x180002dee  lea     rax, [rsp+288h+Filename]
0x180002df3  sub     rcx, rax
0x180002df6  movsd   qword ptr [rsp+288h+Source], xmm0
0x180002dfc  sar     rcx, 1
0x180002dff  lea     rax, [rcx+5]
0x180002e03  cmp     rax, 104h
0x180002e09  jbe     short loc_180002E12
0x180002e0b  mov     eax, 80004005h
0x180002e10  jmp     short loc_180002E76
0x180002e12  mov     edx, 10Eh
0x180002e17  lea     r8, [rsp+288h+Source]; Source
0x180002e1c  sub     rdx, rcx; SizeInWords
0x180002e1f  mov     rcx, rdi; Destination
0x180002e22  call    cs:__imp_wcscpy_s
0x180002e28  test    eax, eax
0x180002e2a  jz      short loc_180002E40
0x180002e2c  cmp     eax, 0Ch
0x180002e2f  jz      short loc_180002E94
0x180002e31  cmp     eax, 16h
0x180002e34  jz      short loc_180002EAA
0x180002e36  cmp     eax, 22h ; '"'
0x180002e39  jz      short loc_180002EAA
0x180002e3b  cmp     eax, 50h ; 'P'
0x180002e3e  jnz     short loc_180002E9F
0x180002e40  mov     rdx, rsi; pptlib
0x180002e43  lea     rcx, [rsp+288h+Filename]; szFile
0x180002e48  call    cs:__imp_LoadTypeLib
0x180002e4e  mov     ebx, eax
0x180002e50  test    eax, eax
0x180002e52  js      short loc_180002E6D
0x180002e54  lea     rcx, [rsp+288h+Filename]; psz
0x180002e59  call    cs:__imp_SysAllocString
0x180002e5f  test    rax, rax
0x180002e62  mov     [r14], rax
0x180002e65  mov     ecx, 8007000Eh
0x180002e6a  cmovz   ebx, ecx
0x180002e6d  mov     eax, ebx
0x180002e6f  jmp     short loc_180002E76
0x180002e71  mov     eax, 80004003h
0x180002e76  mov     rcx, [rsp+288h+var_38]
0x180002e7e  xor     rcx, rsp; StackCookie
0x180002e81  call    __security_check_cookie
0x180002e86  add     rsp, 260h
0x180002e8d  pop     r14
0x180002e8f  pop     rdi
0x180002e90  pop     rsi
0x180002e91  pop     rbp
0x180002e92  pop     rbx
0x180002e93  retn
0x180002e94  mov     ecx, 8007000Eh; int
0x180002e99  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002e9f  mov     ecx, 80004005h; int
0x180002ea4  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180002eaa  mov     ecx, 80070057h; int
0x180002eaf  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
