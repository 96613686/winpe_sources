# PackageCollector::AddSearchPath(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x14000b250`
- end: `0x14000b44c`
- name: `?AddSearchPath@PackageCollector@@QEAA_NAEBV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `508`
- prototype: `bool __fastcall(_QWORD *, _QWORD *, int, int)`
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, reparse_path, loader_planting`

## callers

- `0x14000ad18`

## callees

- `0x140001008`
- `0x140001424`
- `0x1400033a8`
- `0x140008850`
- `0x140008b0c`
- `0x140008e50`
- `0x14000b250`
- `0x14000ded0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x14000b3ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b41c`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b3ae`
- `msvcrt!??3@YAXPEAX@Z` at `0x14000b41c`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x14000b2eb`
- `api-ms-win-core-path-l1-1-0!PathCchCanonicalizeEx` at `0x14000b2eb`

## pseudocode

```c
bool __fastcall PackageCollector::AddSearchPath(_QWORD *a1, _QWORD *a2, int a3, int a4)
{
  __int64 v6; // r15
  unsigned __int64 v7; // rbx
  HRESULT v8; // r14d
  WCHAR *v9; // rdi
  const WCHAR *v10; // r8
  _QWORD *v11; // rbx
  __int64 v12; // r8
  char v13; // al
  __int64 v14; // rcx
  unsigned __int64 v15; // rsi
  void **v16; // rdx
  int v17; // ecx
  int v18; // r8d
  int v19; // r9d
  bool v20; // r14
  WCHAR *v22; // [rsp+30h] [rbp-50h] BYREF
  WCHAR *v23; // [rsp+38h] [rbp-48h] BYREF
  PWSTR pszPathOut[2]; // [rsp+40h] [rbp-40h] BYREF
  __int64 v25; // [rsp+50h] [rbp-30h]
  void *v26[3]; // [rsp+58h] [rbp-28h] BYREF
  unsigned __int64 v27; // [rsp+70h] [rbp-10h]

  *(_OWORD *)pszPathOut = 0;
  v6 = 0;
  v25 = 0;
  v7 = 520;
  v8 = -2147024774;
  v9 = 0;
  do
  {
    if ( v7 >= 0xFFFFFFF )
      break;
    if ( (v6 - (__int64)v9) >> 1 < v7 )
    {
      std::vector<unsigned short>::_Reallocate(pszPathOut, v7);
      v6 = v25;
      v9 = pszPathOut[0];
    }
    v10 = a2[3] < 8u ? (const WCHAR *)a2 : (const WCHAR *)*a2;
    v8 = PathCchCanonicalizeEx(v9, (v6 - (__int64)v9) >> 1, v10, 1u);
    v7 *= 2LL;
  }
  while ( v8 == -2147024774 );
  if ( v8 < 0 )
  {
    if ( (unsigned int)dword_140017048 > 3 )
    {
      LODWORD(v22) = v8;
      v23 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        (_DWORD)a1,
        (unsigned int)&byte_14001367F,
        a3,
        a4,
        (__int64)&v23,
        (__int64)&v22);
    }
  }
  else
  {
    v11 = a1 + 1;
    v27 = 7;
    v26[2] = 0;
    LOWORD(v26[0]) = 0;
    if ( *v9 )
    {
      v12 = -1;
      do
        ++v12;
      while ( v9[v12] );
    }
    std::wstring::assign(v26, v9);
    if ( (unsigned __int64)v26 >= a1[2] || (v13 = 1, *v11 > (unsigned __int64)v26) )
      v13 = 0;
    v14 = a1[3];
    if ( v13 )
    {
      v15 = (unsigned __int64)v26 - *v11;
      if ( a1[2] == v14 )
        std::vector<std::wstring>::_Reserve(a1 + 1);
      v16 = (void **)(*v11 + (v15 & 0xFFFFFFFFFFFFFFE0uLL));
    }
    else
    {
      if ( a1[2] == v14 )
        std::vector<std::wstring>::_Reserve(a1 + 1);
      v16 = v26;
    }
    std::wstring::wstring(a1[2], v16);
    a1[2] += 32LL;
    if ( v27 >= 8 )
      operator delete(v26[0]);
    if ( (unsigned int)dword_140017048 > 5 )
    {
      v22 = v9;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<unsigned short>>(
        v17,
        (unsigned int)byte_1400136B5,
        v18,
        v19,
        (__int64)&v22);
    }
  }
  v20 = v8 >= 0;
  if ( v9 )
    operator delete(v9);
  return v20;
}

```

## disassembly

```asm
0x14000b250  mov     [rsp-38h+arg_10], rbx
0x14000b255  push    rbp
0x14000b256  push    rsi
0x14000b257  push    rdi
0x14000b258  push    r12
0x14000b25a  push    r13
0x14000b25c  push    r14
0x14000b25e  push    r15
0x14000b260  mov     rbp, rsp
0x14000b263  sub     rsp, 80h
0x14000b26a  mov     rax, cs:__security_cookie
0x14000b271  xor     rax, rsp
0x14000b274  mov     [rbp+var_8], rax
0x14000b278  mov     rsi, rdx
0x14000b27b  mov     r13, rcx
0x14000b27e  xorps   xmm0, xmm0
0x14000b281  movdqu  xmmword ptr [rbp+pszPathOut], xmm0
0x14000b286  xor     r12d, r12d
0x14000b289  mov     r15d, r12d
0x14000b28c  mov     [rbp+var_30], r12
0x14000b290  mov     ebx, 208h
0x14000b295  mov     r14d, 8007007Ah
0x14000b29b  mov     rdi, [rbp+pszPathOut]
0x14000b29f  cmp     rbx, 0FFFFFFFh
0x14000b2a6  jnb     short loc_14000B2FE
0x14000b2a8  mov     rax, r15
0x14000b2ab  sub     rax, rdi
0x14000b2ae  sar     rax, 1
0x14000b2b1  cmp     rax, rbx
0x14000b2b4  jnb     short loc_14000B2CA
0x14000b2b6  mov     rdx, rbx
0x14000b2b9  lea     rcx, [rbp+pszPathOut]
0x14000b2bd  call    ?_Reallocate@?$vector@GV?$allocator@G@std@@@std@@IEAAX_K@Z; std::vector<ushort>::_Reallocate(unsigned __int64)
0x14000b2c2  mov     r15, [rbp+var_30]
0x14000b2c6  mov     rdi, [rbp+pszPathOut]
0x14000b2ca  cmp     qword ptr [rsi+18h], 8
0x14000b2cf  jb      short loc_14000B2D6
0x14000b2d1  mov     r8, [rsi]
0x14000b2d4  jmp     short loc_14000B2D9
0x14000b2d6  mov     r8, rsi; pszPathIn
0x14000b2d9  mov     rdx, r15
0x14000b2dc  sub     rdx, rdi
0x14000b2df  sar     rdx, 1; cchPathOut
0x14000b2e2  mov     r9d, 1; dwFlags
0x14000b2e8  mov     rcx, rdi; pszPathOut
0x14000b2eb  call    cs:__imp_PathCchCanonicalizeEx
0x14000b2f1  mov     r14d, eax
0x14000b2f4  add     rbx, rbx
0x14000b2f7  cmp     eax, 8007007Ah
0x14000b2fc  jz      short loc_14000B29F
0x14000b2fe  test    r14d, r14d
0x14000b301  js      loc_14000B3DA
0x14000b307  lea     rbx, [r13+8]
0x14000b30b  mov     [rbp+var_10], 7
0x14000b313  mov     [rbp+var_18], r12
0x14000b317  mov     word ptr [rbp+var_28], r12w
0x14000b31c  cmp     [rdi], r12w
0x14000b320  jnz     short loc_14000B327
0x14000b322  mov     r8, r12
0x14000b325  jmp     short loc_14000B335
0x14000b327  or      r8, 0FFFFFFFFFFFFFFFFh
0x14000b32b  inc     r8
0x14000b32e  cmp     [rdi+r8*2], r12w
0x14000b333  jnz     short loc_14000B32B
0x14000b335  mov     rdx, rdi; Src
0x14000b338  lea     rcx, [rbp+var_28]; void *
0x14000b33c  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z; std::wstring::assign(ushort const *,unsigned __int64)
0x14000b341  nop
0x14000b342  lea     rax, [rbp+var_28]
0x14000b346  cmp     rax, [rbx+8]
0x14000b34a  jnb     short loc_14000B357
0x14000b34c  lea     rax, [rbp+var_28]
0x14000b350  cmp     [rbx], rax
0x14000b353  mov     al, 1
0x14000b355  jbe     short loc_14000B35A
0x14000b357  mov     al, r12b
0x14000b35a  mov     rcx, [rbx+10h]
0x14000b35e  test    al, al
0x14000b360  jz      short loc_14000B383
0x14000b362  lea     rsi, [rbp+var_28]
0x14000b366  sub     rsi, [rbx]
0x14000b369  cmp     [rbx+8], rcx
0x14000b36d  jnz     short loc_14000B377
0x14000b36f  mov     rcx, rbx
0x14000b372  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x14000b377  and     rsi, 0FFFFFFFFFFFFFFE0h
0x14000b37b  add     rsi, [rbx]
0x14000b37e  mov     rdx, rsi
0x14000b381  jmp     short loc_14000B395
0x14000b383  cmp     [rbx+8], rcx
0x14000b387  jnz     short loc_14000B391
0x14000b389  mov     rcx, rbx
0x14000b38c  call    ?_Reserve@?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@IEAAX_K@Z; std::vector<std::wstring>::_Reserve(unsigned __int64)
0x14000b391  lea     rdx, [rbp+var_28]
0x14000b395  mov     rcx, [rbx+8]
0x14000b399  call    ??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@$$QEAV01@@Z; std::wstring::wstring(std::wstring &&)
0x14000b39e  add     qword ptr [rbx+8], 20h ; ' '
0x14000b3a3  cmp     [rbp+var_10], 8
0x14000b3a8  jb      short loc_14000B3B4
0x14000b3aa  mov     rcx, [rbp+var_28]
0x14000b3ae  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000b3b4  mov     eax, cs:dword_140017048
0x14000b3ba  cmp     eax, 5
0x14000b3bd  jbe     short loc_14000B40C
0x14000b3bf  mov     [rbp+var_50], rdi
0x14000b3c3  lea     rax, [rbp+var_50]
0x14000b3c7  mov     [rsp+80h+var_60], rax
0x14000b3cc  lea     rdx, byte_1400136B5
0x14000b3d3  call    ??$Write@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &)
0x14000b3d8  jmp     short loc_14000B40C
0x14000b3da  mov     eax, cs:dword_140017048
0x14000b3e0  cmp     eax, 3
0x14000b3e3  jbe     short loc_14000B40C
0x14000b3e5  mov     dword ptr [rbp+var_50], r14d
0x14000b3e9  mov     [rbp+var_48], rdi
0x14000b3ed  lea     rax, [rbp+var_50]
0x14000b3f1  mov     [rsp+80h+var_58], rax
0x14000b3f6  lea     rax, [rbp+var_48]
0x14000b3fa  mov     [rsp+80h+var_60], rax
0x14000b3ff  lea     rdx, byte_14001367F
0x14000b406  call    ??$Write@U?$_tlgWrapSz@G@@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@G@@AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x14000b40b  nop
0x14000b40c  shr     r14d, 1Fh
0x14000b410  xor     r14b, 1
0x14000b414  test    rdi, rdi
0x14000b417  jz      short loc_14000B422
0x14000b419  mov     rcx, rdi
0x14000b41c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x14000b422  mov     al, r14b
0x14000b425  mov     rcx, [rbp+var_8]
0x14000b429  xor     rcx, rsp; StackCookie
0x14000b42c  call    __security_check_cookie
0x14000b431  mov     rbx, [rsp+80h+arg_10]
0x14000b439  add     rsp, 80h
0x14000b440  pop     r15
0x14000b442  pop     r14
0x14000b444  pop     r13
0x14000b446  pop     r12
0x14000b448  pop     rdi
0x14000b449  pop     rsi
0x14000b44a  pop     rbp
0x14000b44b  retn
```
