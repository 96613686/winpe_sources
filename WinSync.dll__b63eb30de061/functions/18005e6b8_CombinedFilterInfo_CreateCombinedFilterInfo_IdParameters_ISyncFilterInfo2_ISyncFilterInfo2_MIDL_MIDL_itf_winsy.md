# CombinedFilterInfo::CreateCombinedFilterInfo(IdParameters *,ISyncFilterInfo2 *,ISyncFilterInfo2 *,__MIDL___MIDL_itf_winsync_0000_0036_0001,_GUID const &,void * *)

- ea: `0x18005e6b8`
- end: `0x18005e82a`
- name: `?CreateCombinedFilterInfo@CombinedFilterInfo@@SAJPEAVIdParameters@@PEAUISyncFilterInfo2@@1W4__MIDL___MIDL_itf_winsync_0000_0036_0001@@AEBU_GUID@@PEAPEAX@Z`
- size: `370`
- prototype: `__int64 __fastcall(struct IdParameters *, struct ISyncFilterInfo2 *, struct ISyncFilterInfo2 *, enum __MIDL___MIDL_itf_winsync_0000_0036_0001, const struct _GUID *, void **)`
- caller_count: `2`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18002b3d0`
- `0x18005e830`

## callees

- `0x18000a0f0`
- `0x18001a038`
- `0x18001ae20`
- `0x18002addc`
- `0x18005e6b8`
- `0x180094010`

## string_xrefs

- `0x18005e6f4`: `CombinedFilterInfo::CreateCombinedFilterInfo`
- `0x18005e7ff`: `CombinedFilterInfo::CreateCombinedFilterInfo`

## pseudocode

```c
__int64 __fastcall CombinedFilterInfo::CreateCombinedFilterInfo(
        struct IdParameters *a1,
        struct ISyncFilterInfo2 *a2,
        struct ISyncFilterInfo2 *a3,
        enum __MIDL___MIDL_itf_winsync_0000_0036_0001 a4,
        const struct _GUID *a5,
        void **a6)
{
  PVOID *v10; // rcx
  unsigned int v11; // ebx
  FilterInfo *v12; // rax
  FilterInfo *v13; // rdi

  v10 = (PVOID *)WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 0x40) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      10,
      WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      "CombinedFilterInfo::CreateCombinedFilterInfo");
    v10 = (PVOID *)WPP_GLOBAL_Control;
  }
  if ( a1 && a2 && a3 && a6 )
  {
    if ( a4 )
    {
      v11 = -2147024809;
    }
    else
    {
      v12 = (FilterInfo *)SeAlloc(0x38u);
      v13 = v12;
      if ( v12 )
      {
        FilterInfo::FilterInfo(v12, a1, 8u);
        *((_QWORD *)v13 + 4) = &CombinedFilterInfo::`vftable'{for `ICombinedFilterInfo'};
        *(_QWORD *)v13 = &CombinedFilterInfo::`vftable'{for `FilterInfo'};
        ((void (__fastcall *)(struct ISyncFilterInfo2 *))a2->lpVtbl->AddRef)(a2);
        ((void (__fastcall *)(struct ISyncFilterInfo2 *))a3->lpVtbl->AddRef)(a3);
        *((_QWORD *)v13 + 5) = a2;
        *((_QWORD *)v13 + 6) = a3;
        v11 = (**(__int64 (__fastcall ***)(FilterInfo *, const struct _GUID *, void **))v13)(v13, a5, a6);
        (*(void (__fastcall **)(FilterInfo *))(*(_QWORD *)v13 + 16LL))(v13);
      }
      else
      {
        v11 = -2147024882;
      }
      v10 = (PVOID *)WPP_GLOBAL_Control;
    }
  }
  else
  {
    v11 = -2147467261;
  }
  if ( v10 != &WPP_GLOBAL_Control && (*((_BYTE *)v10 + 28) & 0x40) != 0 && *((_BYTE *)v10 + 25) >= 5u )
    WPP_SF_sD(
      (unsigned int)v10[2],
      11,
      (unsigned int)WPP_783f365b549b3562e36b34ccc92b6714_Traceguids,
      (unsigned int)"CombinedFilterInfo::CreateCombinedFilterInfo",
      v11);
  return v11;
}

```

## disassembly

```asm
0x18005e6b8  push    rbx
0x18005e6ba  push    rbp
0x18005e6bb  push    rsi
0x18005e6bc  push    rdi
0x18005e6bd  push    r14
0x18005e6bf  push    r15
0x18005e6c1  sub     rsp, 38h
0x18005e6c5  mov     edi, r9d
0x18005e6c8  mov     rsi, r8
0x18005e6cb  mov     r14, rdx
0x18005e6ce  mov     rbp, rcx
0x18005e6d1  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e6d8  lea     r15, WPP_GLOBAL_Control
0x18005e6df  cmp     rcx, r15
0x18005e6e2  jz      short loc_18005E713
0x18005e6e4  test    byte ptr [rcx+1Ch], 40h
0x18005e6e8  jz      short loc_18005E713
0x18005e6ea  cmp     byte ptr [rcx+19h], 5
0x18005e6ee  jb      short loc_18005E713
0x18005e6f0  mov     rcx, [rcx+10h]
0x18005e6f4  lea     r9, aCombinedfilter_5; "CombinedFilterInfo::CreateCombinedFilte"...
0x18005e6fb  mov     edx, 0Ah
0x18005e700  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005e707  call    WPP_SF_s
0x18005e70c  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e713  test    rbp, rbp
0x18005e716  jz      loc_18005E7E5
0x18005e71c  test    r14, r14
0x18005e71f  jz      loc_18005E7E5
0x18005e725  test    rsi, rsi
0x18005e728  jz      loc_18005E7E5
0x18005e72e  mov     rbx, [rsp+68h+arg_28]
0x18005e736  test    rbx, rbx
0x18005e739  jz      loc_18005E7E5
0x18005e73f  test    edi, edi
0x18005e741  jz      short loc_18005E74D
0x18005e743  mov     ebx, 80070057h
0x18005e748  jmp     loc_18005E7EA
0x18005e74d  mov     ecx, 38h ; '8'; unsigned __int64
0x18005e752  call    ?SeAlloc@@YAPEAX_K@Z; SeAlloc(unsigned __int64)
0x18005e757  mov     rdi, rax
0x18005e75a  test    rax, rax
0x18005e75d  jz      short loc_18005E7D7
0x18005e75f  mov     r8d, 8; unsigned int
0x18005e765  mov     rdx, rbp; struct IdParameters *
0x18005e768  mov     rcx, rax; this
0x18005e76b  call    ??0FilterInfo@@IEAA@PEAVIdParameters@@K@Z; FilterInfo::FilterInfo(IdParameters *,ulong)
0x18005e770  lea     rax, ??_7CombinedFilterInfo@@6BICombinedFilterInfo@@@; const CombinedFilterInfo::`vftable'{for `ICombinedFilterInfo'}
0x18005e777  mov     [rdi+20h], rax
0x18005e77b  lea     rcx, ??_7CombinedFilterInfo@@6BFilterInfo@@@; const CombinedFilterInfo::`vftable'{for `FilterInfo'}
0x18005e782  mov     [rdi], rcx
0x18005e785  mov     rcx, r14
0x18005e788  mov     rax, [r14]
0x18005e78b  mov     rax, [rax+8]
0x18005e78f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e794  mov     rax, [rsi]
0x18005e797  mov     rcx, rsi
0x18005e79a  mov     rax, [rax+8]
0x18005e79e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7a3  mov     rdx, [rsp+68h+arg_20]
0x18005e7ab  mov     r8, rbx
0x18005e7ae  mov     [rdi+28h], r14
0x18005e7b2  mov     rcx, rdi
0x18005e7b5  mov     [rdi+30h], rsi
0x18005e7b9  mov     rax, [rdi]
0x18005e7bc  mov     rax, [rax]
0x18005e7bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7c4  mov     rcx, [rdi]
0x18005e7c7  mov     ebx, eax
0x18005e7c9  mov     rax, [rcx+10h]
0x18005e7cd  mov     rcx, rdi
0x18005e7d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005e7d5  jmp     short loc_18005E7DC
0x18005e7d7  mov     ebx, 8007000Eh
0x18005e7dc  mov     rcx, cs:WPP_GLOBAL_Control
0x18005e7e3  jmp     short loc_18005E7EA
0x18005e7e5  mov     ebx, 80004003h
0x18005e7ea  cmp     rcx, r15
0x18005e7ed  jz      short loc_18005E81B
0x18005e7ef  test    byte ptr [rcx+1Ch], 40h
0x18005e7f3  jz      short loc_18005E81B
0x18005e7f5  cmp     byte ptr [rcx+19h], 5
0x18005e7f9  jb      short loc_18005E81B
0x18005e7fb  mov     rcx, [rcx+10h]
0x18005e7ff  lea     r9, aCombinedfilter_5; "CombinedFilterInfo::CreateCombinedFilte"...
0x18005e806  mov     edx, 0Bh
0x18005e80b  mov     [rsp+68h+var_48], ebx
0x18005e80f  lea     r8, WPP_783f365b549b3562e36b34ccc92b6714_Traceguids
0x18005e816  call    WPP_SF_sD
0x18005e81b  mov     eax, ebx
0x18005e81d  add     rsp, 38h
0x18005e821  pop     r15
0x18005e823  pop     r14
0x18005e825  pop     rdi
0x18005e826  pop     rsi
0x18005e827  pop     rbp
0x18005e828  pop     rbx
0x18005e829  retn
```
