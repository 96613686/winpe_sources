# Csl::GetSystemDirectoryPath(Csl::Path &)

- ea: `0x18000cb58`
- end: `0x18000ccf7`
- name: `?GetSystemDirectoryPath@Csl@@YAJAEAVPath@1@@Z`
- size: `415`
- prototype: `__int64 __fastcall(Csl *__hidden this, struct Path *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops`

## callers

- `0x18000cd00`
- `0x18001edfc`
- `0x1800275a4`

## callees

- `0x180002534`
- `0x180002c48`
- `0x180002f1c`
- `0x1800045e4`
- `0x180007b2c`
- `0x180009e10`
- `0x18000bc38`
- `0x18000cb58`

## import_xrefs

- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000cb71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000cbe2`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000cb71`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000cbe2`

## pseudocode

```c
__int64 __fastcall Csl::GetSystemDirectoryPath(Csl *this, struct Path *a2)
{
  UINT SystemDirectoryW; // ebx
  const char *v4; // r9
  __int64 v6; // rsi
  unsigned __int64 v7; // r14
  WCHAR *v8; // rax
  WCHAR *v9; // rdi
  UINT v10; // eax
  const struct std::nothrow_t *v11; // rdx
  const char *v12; // r9
  unsigned int LastError; // ebx
  const struct std::nothrow_t *v14; // rdx
  const struct std::nothrow_t *v15; // rdx
  _QWORD v16[2]; // [rsp+20h] [rbp-30h] BYREF
  void *v17[2]; // [rsp+30h] [rbp-20h] BYREF
  _WORD v18[8]; // [rsp+40h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+38h]

  SystemDirectoryW = GetSystemDirectoryW(0, 0);
  if ( !SystemDirectoryW )
    return wil::details::in1diag3::Return_GetLastError(
             retaddr,
             (void *)0x523,
             (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
             v4);
  v6 = -1;
  while ( 1 )
  {
    v7 = 2LL * SystemDirectoryW;
    if ( !is_mul_ok(SystemDirectoryW, 2u) )
      v7 = -1;
    v8 = (WCHAR *)operator new[](v7, (const struct std::nothrow_t *)&std::nothrow);
    v9 = v8;
    if ( !v8 )
    {
      LastError = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x52A,
        (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
        (const char *)0x8007000ELL,
        v16[0]);
      return LastError;
    }
    memset_0(v8, 0, v7);
    v10 = GetSystemDirectoryW(v9, SystemDirectoryW);
    if ( !v10 )
    {
      LastError = wil::details::in1diag3::Return_GetLastError(
                    retaddr,
                    (void *)0x532,
                    (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
                    v12);
      goto LABEL_19;
    }
    if ( v10 <= SystemDirectoryW )
      break;
    SystemDirectoryW = v10;
    operator delete(v9, v11);
  }
  v18[0] = 0;
  v17[0] = v18;
  v17[1] = v18;
  v16[0] = v9;
  do
    ++v6;
  while ( v9[v6] );
  v16[1] = v6;
  if ( !Csl::Path::Assign((Csl::Path *)v17, (__int64)v16) )
  {
    LastError = -2147024882;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x53E,
      (unsigned int)"onecore\\base\\gendrv\\silos\\csl\\lib\\cslfilesystem.cpp",
      (const char *)0x8007000ELL,
      v16[0]);
    if ( v17[0] != v18 )
      operator delete(v17[0], (const struct std::nothrow_t *)&std::nothrow);
LABEL_19:
    operator delete(v9, v14);
    return LastError;
  }
  utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::operator=(
    (__int64)this,
    (__int64)v17);
  if ( v17[0] != v18 )
    operator delete(v17[0], (const struct std::nothrow_t *)&std::nothrow);
  operator delete(v9, v15);
  return 0;
}

```

## disassembly

```asm
0x18000cb58  push    rbp
0x18000cb5a  push    rbx
0x18000cb5b  push    rsi
0x18000cb5c  push    rdi
0x18000cb5d  push    r12
0x18000cb5f  push    r14
0x18000cb61  push    r15
0x18000cb63  mov     rbp, rsp
0x18000cb66  sub     rsp, 50h
0x18000cb6a  mov     r15, rcx
0x18000cb6d  xor     edx, edx; uSize
0x18000cb6f  xor     ecx, ecx; lpBuffer
0x18000cb71  call    cs:__imp_GetSystemDirectoryW
0x18000cb78  nop     dword ptr [rax+rax+00h]
0x18000cb7d  xor     r12d, r12d
0x18000cb80  mov     ebx, eax
0x18000cb82  test    eax, eax
0x18000cb84  jnz     short loc_18000CBA0
0x18000cb86  mov     rcx, [rbp+38h]; this
0x18000cb8a  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000cb91  mov     edx, 523h; void *
0x18000cb96  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000cb9b  jmp     loc_18000CCE7
0x18000cba0  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18000cba4  mov     ecx, ebx
0x18000cba6  mov     eax, 2
0x18000cbab  mul     rcx
0x18000cbae  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cbb5  mov     r14, rax
0x18000cbb8  cmovb   r14, rsi
0x18000cbbc  mov     rcx, r14; unsigned __int64
0x18000cbbf  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000cbc4  mov     rdi, rax
0x18000cbc7  test    rax, rax
0x18000cbca  jz      loc_18000CCC8
0x18000cbd0  mov     r8, r14; Size
0x18000cbd3  xor     edx, edx; Val
0x18000cbd5  mov     rcx, rax; void *
0x18000cbd8  call    memset_0
0x18000cbdd  mov     edx, ebx; uSize
0x18000cbdf  mov     rcx, rdi; lpBuffer
0x18000cbe2  call    cs:__imp_GetSystemDirectoryW
0x18000cbe9  nop     dword ptr [rax+rax+00h]
0x18000cbee  test    eax, eax
0x18000cbf0  jz      loc_18000CCA7
0x18000cbf6  cmp     eax, ebx
0x18000cbf8  jbe     short loc_18000CC06
0x18000cbfa  mov     rcx, rdi; void *
0x18000cbfd  mov     ebx, eax
0x18000cbff  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cc04  jmp     short loc_18000CBA4
0x18000cc06  lea     rax, [rbp+var_10]
0x18000cc0a  mov     [rbp+var_10], r12w
0x18000cc0f  mov     [rbp+var_20], rax
0x18000cc13  lea     rax, [rbp+var_10]
0x18000cc17  mov     [rbp+var_18], rax
0x18000cc1b  mov     [rbp+var_30], rdi
0x18000cc1f  inc     rsi
0x18000cc22  cmp     [rdi+rsi*2], r12w
0x18000cc27  jnz     short loc_18000CC1F
0x18000cc29  lea     rdx, [rbp+var_30]
0x18000cc2d  mov     [rbp+var_28], rsi
0x18000cc31  lea     rcx, [rbp+var_20]; this
0x18000cc35  call    ?Assign@Path@Csl@@QEAA_NAEBV?$basic_string_view@GU?$char_traits@G@utl@@@utl@@@Z; Csl::Path::Assign(utl::basic_string_view<ushort,utl::char_traits<ushort>> const &)
0x18000cc3a  test    al, al
0x18000cc3c  jnz     short loc_18000CC76
0x18000cc3e  mov     rcx, [rbp+38h]; this
0x18000cc42  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000cc49  mov     ebx, 8007000Eh
0x18000cc4e  mov     edx, 53Eh; void *
0x18000cc53  mov     r9d, ebx; char *
0x18000cc56  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cc5b  mov     rcx, [rbp+var_20]; void *
0x18000cc5f  lea     rax, [rbp+var_10]
0x18000cc63  cmp     rcx, rax
0x18000cc66  jz      short loc_18000CCBE
0x18000cc68  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cc6f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cc74  jmp     short loc_18000CCBE
0x18000cc76  lea     rdx, [rbp+var_20]
0x18000cc7a  mov     rcx, r15
0x18000cc7d  call    ??4?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAAAEAV01@$$QEAV01@@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::operator=(utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>> &&)
0x18000cc82  mov     rcx, [rbp+var_20]; void *
0x18000cc86  lea     rax, [rbp+var_10]
0x18000cc8a  cmp     rcx, rax
0x18000cc8d  jz      short loc_18000CC9B
0x18000cc8f  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000cc96  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cc9b  mov     rcx, rdi; void *
0x18000cc9e  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000cca3  xor     eax, eax
0x18000cca5  jmp     short loc_18000CCE7
0x18000cca7  mov     rcx, [rbp+38h]; this
0x18000ccab  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000ccb2  mov     edx, 532h; void *
0x18000ccb7  call    ?Return_GetLastError@in1diag3@details@wil@@YAJPEAXIPEBD@Z; wil::details::in1diag3::Return_GetLastError(void *,uint,char const *)
0x18000ccbc  mov     ebx, eax
0x18000ccbe  mov     rcx, rdi; void *
0x18000ccc1  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000ccc6  jmp     short loc_18000CCE5
0x18000ccc8  mov     rcx, [rbp+38h]; this
0x18000cccc  lea     r8, aOnecoreBaseGen_1; "onecore\\base\\gendrv\\silos\\csl\\lib"...
0x18000ccd3  mov     ebx, 8007000Eh
0x18000ccd8  mov     edx, 52Ah; void *
0x18000ccdd  mov     r9d, ebx; char *
0x18000cce0  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000cce5  mov     eax, ebx
0x18000cce7  add     rsp, 50h
0x18000cceb  pop     r15
0x18000cced  pop     r14
0x18000ccef  pop     r12
0x18000ccf1  pop     rdi
0x18000ccf2  pop     rsi
0x18000ccf3  pop     rbx
0x18000ccf4  pop     rbp
0x18000ccf5  retn
```
