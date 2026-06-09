# CPolicyCheck::FindPolicyEntry(ushort const *,CPolicyEntry * *)

- ea: `0x1800038dc`
- end: `0x180003a81`
- name: `?FindPolicyEntry@CPolicyCheck@@QEAAJPEBGPEAPEAVCPolicyEntry@@@Z`
- size: `421`
- prototype: `int(CPolicyCheck *__hidden this, const unsigned __int16 *, struct CPolicyEntry **)`
- caller_count: `3`
- callee_count: `8`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000300c`
- `0x180003260`
- `0x18000401c`

## callees

- `0x1800017c0`
- `0x1800028f4`
- `0x180002978`
- `0x180002c00`
- `0x180003228`
- `0x1800038dc`
- `0x18000725c`
- `0x180015010`

## import_xrefs

- `urlmon!CreateUri` at `0x18000392e`
- `urlmon!CreateUri` at `0x18000392e`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall CPolicyCheck::FindPolicyEntry(
        CPolicyCheck *this,
        const unsigned __int16 *a2,
        struct CPolicyEntry **a3)
{
  _QWORD *v6; // rsi
  HRESULT v7; // eax
  unsigned int v8; // ebx
  _QWORD *v9; // rax
  IUri *v10; // rdx
  __int64 v11; // rbx
  __int64 v12; // rcx
  IUri *v14; // [rsp+30h] [rbp-58h] BYREF
  ATL::CAtlException *v15; // [rsp+38h] [rbp-50h] BYREF
  char v16[16]; // [rsp+40h] [rbp-48h] BYREF
  __int64 v17; // [rsp+50h] [rbp-38h]
  _QWORD *v18; // [rsp+A8h] [rbp+20h] BYREF

  v14 = 0;
  v6 = 0;
  v18 = 0;
  if ( a2 && *a2 && a3 )
  {
    *a3 = 0;
    v7 = CreateUri(a2, 0, 0, &v14);
    v8 = v7;
    if ( v7 < 0 )
    {
      AxISEvents::DebugMsg((AxISEvents *)&qword_180021AD8, 8u, 3u, L"Invalid URL %s Error %x", a2, v7);
    }
    else
    {
      v9 = operator new(0x30u, (const struct std::nothrow_t *)&std::nothrow);
      try
      {
        v6 = v9;
        if ( v9 )
        {
          v10 = v14;
          *v9 = &CPolicyEntry::`vftable';
          v9[1] = 0;
          v9[2] = 0;
          ATL::CComPtrBase<IUri>::Attach(v9 + 2, v10);
          ATL::CComBSTR::operator=(v6 + 1, a2);
          v6[3] = 1;
          v6[4] = 0;
          v6[5] = 0;
        }
        else
        {
          v6 = 0;
        }
        v18 = v6;
        if ( v6 )
        {
          v14 = 0;
          std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Find_lower_bound<CPolicyEntry *>(
            (char *)this + 112,
            v16,
            &v18);
          v11 = v17;
          if ( !(unsigned __int8)std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Lower_bound_duplicate<CPolicyEntry *>(
                                   v12,
                                   v17,
                                   &v18)
            || v11 == *((_QWORD *)this + 14) )
          {
            v8 = -2147023728;
          }
          else
          {
            *a3 = *(struct CPolicyEntry **)(v11 + 32);
            v8 = 0;
          }
        }
        else
        {
          v8 = -2147024882;
        }
      }
      catch ( ATL::CAtlException *v15 )
      {
        v8 = *(_DWORD *)v15;
        v6 = v18;
      }
      catch ( std::bad_alloc )
      {
        v8 = -2147024882;
        v6 = v18;
      }
    }
  }
  else
  {
    v8 = -2147024809;
  }
  if ( v14 )
    ((void (__fastcall *)(IUri *))v14->lpVtbl->Release)(v14);
  if ( v6 )
    (*(void (__fastcall **)(_QWORD *, __int64))*v6)(v6, 1);
  return v8;
}

```

## disassembly

```asm
0x1800038dc  mov     rax, rsp
0x1800038df  mov     [rax+8], rbx
0x1800038e3  push    rsi
0x1800038e4  push    rdi
0x1800038e5  push    r13
0x1800038e7  push    r14
0x1800038e9  push    r15
0x1800038eb  sub     rsp, 60h
0x1800038ef  mov     r15, r8
0x1800038f2  mov     r14, rdx
0x1800038f5  mov     r13, rcx
0x1800038f8  xor     edi, edi
0x1800038fa  mov     [rax-58h], rdi
0x1800038fe  mov     esi, edi
0x180003900  mov     [rax+20h], rdi
0x180003904  test    rdx, rdx
0x180003907  jz      loc_180003A37
0x18000390d  cmp     di, [rdx]
0x180003910  jz      loc_180003A37
0x180003916  test    r8, r8
0x180003919  jz      loc_180003A37
0x18000391f  mov     [r8], rdi
0x180003922  lea     r9, [rax-58h]; ppURI
0x180003926  xor     r8d, r8d; dwReserved
0x180003929  xor     edx, edx; dwFlags
0x18000392b  mov     rcx, r14; pwzURI
0x18000392e  call    cs:__imp_CreateUri
0x180003934  mov     ebx, eax
0x180003936  test    eax, eax
0x180003938  js      loc_180003A10
0x18000393e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180003945  lea     ecx, [rdi+30h]; unsigned __int64
0x180003948  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000394d  mov     rsi, rax
0x180003950  mov     [rsp+88h+arg_8], rax
0x180003958  test    rax, rax
0x18000395b  jz      short loc_18000399A
0x18000395d  mov     rdx, [rsp+88h+var_58]
0x180003962  lea     rax, ??_7CPolicyEntry@@6B@; const CPolicyEntry::`vftable'
0x180003969  mov     [rsi], rax
0x18000396c  mov     [rsi+8], rdi
0x180003970  lea     rcx, [rsi+10h]
0x180003974  mov     [rcx], rdi
0x180003977  call    ?Attach@?$CComPtrBase@UIUri@@@ATL@@QEAAXPEAUIUri@@@Z; ATL::CComPtrBase<IUri>::Attach(IUri *)
0x18000397c  mov     rdx, r14
0x18000397f  lea     rcx, [rsi+8]
0x180003983  call    ??4CComBSTR@ATL@@QEAAAEAV01@PEBG@Z; ATL::CComBSTR::operator=(ushort const *)
0x180003988  mov     qword ptr [rsi+18h], 1
0x180003990  mov     [rsi+20h], rdi
0x180003994  mov     [rsi+28h], rdi
0x180003998  jmp     short loc_18000399D
0x18000399a  mov     rsi, rdi
0x18000399d  mov     [rsp+88h+arg_18], rsi
0x1800039a5  test    rsi, rsi
0x1800039a8  jz      short loc_1800039F6
0x1800039aa  mov     [rsp+88h+var_58], rdi
0x1800039af  lea     r8, [rsp+88h+arg_18]
0x1800039b7  lea     rdx, [rsp+88h+var_48]
0x1800039bc  lea     rcx, [r13+70h]
0x1800039c0  call    ??$_Find_lower_bound@PEAVCPolicyEntry@@@?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@std@@@1@AEBQEAVCPolicyEntry@@@Z; std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Find_lower_bound<CPolicyEntry *>(CPolicyEntry * const &)
0x1800039c5  lea     r8, [rsp+88h+arg_18]
0x1800039cd  mov     rbx, [rsp+88h+var_38]
0x1800039d2  mov     rdx, rbx
0x1800039d5  call    ??$_Lower_bound_duplicate@PEAVCPolicyEntry@@@?$_Tree@V?$_Tset_traits@PEAVCPolicyEntry@@UCPolicyEntryCompare@@V?$allocator@PEAVCPolicyEntry@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@PEAVCPolicyEntry@@PEAX@1@AEBQEAVCPolicyEntry@@@Z; std::_Tree<std::_Tset_traits<CPolicyEntry *,CPolicyEntryCompare,std::allocator<CPolicyEntry *>,0>>::_Lower_bound_duplicate<CPolicyEntry *>(std::_Tree_node<CPolicyEntry *,void *> * const,CPolicyEntry * const &)
0x1800039da  test    al, al
0x1800039dc  jz      short loc_1800039EF
0x1800039de  cmp     rbx, [r13+70h]
0x1800039e2  jz      short loc_1800039EF
0x1800039e4  mov     rax, [rbx+20h]
0x1800039e8  mov     [r15], rax
0x1800039eb  mov     ebx, edi
0x1800039ed  jmp     short loc_1800039FB
0x1800039ef  mov     ebx, 80070490h
0x1800039f4  jmp     short loc_1800039FB
0x1800039f6  mov     ebx, 8007000Eh
0x1800039fb  jmp     short loc_180003A3C
0x1800039fd  jmp     short $+2
0x1800039ff  mov     ebx, dword ptr [rsp+88h+arg_8]
0x180003a06  mov     rsi, [rsp+88h+arg_18]
0x180003a0e  jmp     short loc_180003A3C
0x180003a10  mov     [rsp+88h+var_60], eax
0x180003a14  mov     [rsp+88h+var_68], r14
0x180003a19  lea     r9, aInvalidUrlSErr; "Invalid URL %s Error %x"
0x180003a20  mov     edx, 8; unsigned int
0x180003a25  lea     r8d, [rdx-5]; unsigned __int8
0x180003a29  lea     rcx, qword_180021AD8; this
0x180003a30  call    ?DebugMsg@AxISEvents@@QEAAXKEPEAGZZ; AxISEvents::DebugMsg(ulong,uchar,ushort *,...)
0x180003a35  jmp     short loc_180003A3C
0x180003a37  mov     ebx, 80070057h
0x180003a3c  mov     rcx, [rsp+88h+var_58]
0x180003a41  test    rcx, rcx
0x180003a44  jz      short loc_180003A52
0x180003a46  mov     rax, [rcx]
0x180003a49  mov     rax, [rax+10h]
0x180003a4d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a52  test    rsi, rsi
0x180003a55  jz      short loc_180003A6A
0x180003a57  mov     rax, [rsi]
0x180003a5a  mov     edx, 1
0x180003a5f  mov     rcx, rsi
0x180003a62  mov     rax, [rax]
0x180003a65  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003a6a  mov     eax, ebx
0x180003a6c  mov     rbx, [rsp+88h+arg_0]
0x180003a74  add     rsp, 60h
0x180003a78  pop     r15
0x180003a7a  pop     r14
0x180003a7c  pop     r13
0x180003a7e  pop     rdi
0x180003a7f  pop     rsi
0x180003a80  retn
```
