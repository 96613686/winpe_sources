# StructuredQuery1::LeafCondition::Clone(ICondition * *)

- ea: `0x18000a520`
- end: `0x18000ab33`
- name: `?Clone@LeafCondition@StructuredQuery1@@UEAAJPEAPEAUICondition@@@Z`
- size: `1555`
- prototype: `__int64 __fastcall(StructuredQuery1::LeafCondition *__hidden this, struct ICondition **)`
- caller_count: `0`
- callee_count: `7`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000a520`
- `0x18000b130`
- `0x18002a220`
- `0x18003716c`
- `0x18005db64`
- `0x18005e740`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a54f`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000a54f`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a77e`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000a77e`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a62c`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000a62c`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000a659`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000a659`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a6b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a7f9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a6b8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000a7f9`

## string_xrefs

- `0x18000aab6`: `onecoreuap\base\appmodel\search\structuredquery\dll\queryexpression.cpp`

## pseudocode

```c
__int64 __fastcall StructuredQuery1::LeafCondition::Clone(
        StructuredQuery1::LeafCondition *this,
        struct ICondition **a2)
{
  struct _RTL_CRITICAL_SECTION *v3; // r13
  __int64 (__fastcall ***v4)(_QWORD, GUID *, __int64); // r15
  __int16 *v5; // r14
  __int16 *v6; // rdi
  int v7; // esi
  StructuredQuery1::BaseCondition *v8; // rax
  StructuredQuery1::BaseCondition *v9; // r12
  HRESULT v10; // ebp
  unsigned __int64 v11; // rsi
  unsigned __int64 v12; // rbx
  unsigned __int64 v13; // r15
  _WORD *v14; // rax
  _WORD *v15; // r10
  unsigned __int64 v16; // rdx
  _WORD *v17; // r8
  __int64 v18; // rcx
  __int16 v19; // ax
  __int64 v20; // r9
  _WORD *v21; // rcx
  unsigned __int64 v23; // rbx
  _WORD *v24; // rax
  _WORD *v25; // r10
  unsigned __int64 v26; // rdx
  _WORD *v27; // r8
  __int64 v28; // rcx
  __int16 v29; // ax
  __int64 v30; // r9
  _WORD *v31; // rcx
  StructuredQuery1::AttributeList **v32; // rdi
  __int64 v33; // rsi
  __int64 v34; // r15
  bool v35; // cf
  StructuredQuery1::AttributeList **v36; // rax
  StructuredQuery1::AttributeList **v37; // rbx
  StructuredQuery1::AttributeList *v38; // rcx
  __int64 v39; // rbx
  struct ICondition *v40; // [rsp+20h] [rbp-68h] BYREF
  __int64 (__fastcall ***v41)(_QWORD, GUID *, __int64); // [rsp+28h] [rbp-60h]
  __int64 v42; // [rsp+30h] [rbp-58h]
  struct _RTL_CRITICAL_SECTION *v43; // [rsp+38h] [rbp-50h]
  StructuredQuery1::BaseCondition *v44; // [rsp+40h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+88h] [rbp+0h]
  __int64 (__fastcall ***v47)(_QWORD, GUID *, __int64); // [rsp+A0h] [rbp+18h] BYREF
  StructuredQuery1::AttributeList *v48; // [rsp+A8h] [rbp+20h] BYREF

  if ( !a2 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x989,
      (unsigned int)"onecoreuap\\base\\appmodel\\search\\structuredquery\\dll\\queryexpression.cpp",
      (const char *)0x80004003LL,
      (int)v40);
    return 2147500035LL;
  }
  v3 = (struct _RTL_CRITICAL_SECTION *)((char *)this + 136);
  EnterCriticalSection((LPCRITICAL_SECTION)((char *)this + 136));
  v43 = v3;
  v42 = *((_QWORD *)this + 5);
  v4 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)this + 16);
  v47 = v4;
  v41 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64))*((_QWORD *)this + 15);
  v48 = (StructuredQuery1::AttributeList *)*((_QWORD *)this + 14);
  v5 = (__int16 *)*((_QWORD *)this + 13);
  v6 = (__int16 *)*((_QWORD *)this + 12);
  v7 = *((_DWORD *)this + 17);
  v40 = 0;
  v8 = (StructuredQuery1::BaseCondition *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
  v9 = v8;
  v44 = v8;
  if ( !v8 )
  {
    v10 = -2147024882;
    goto LABEL_26;
  }
  StructuredQuery1::BaseCondition::BaseCondition(v8);
  *(_QWORD *)v9 = &StructuredQuery1::LeafCondition::`vftable'{for `ICondition2'};
  *((_QWORD *)v9 + 1) = &StructuredQuery1::NegationCondition::`vftable'{for `IConditionAttributeContainer'};
  *((_QWORD *)v9 + 2) = &StructuredQuery1::LeafCondition::`vftable'{for `IPersistXML'};
  *(PROPERTYKEY *)((char *)v9 + 48) = PKEY_Null;
  *((_DWORD *)v9 + 17) = v7;
  *((_QWORD *)v9 + 12) = 0;
  *((_QWORD *)v9 + 13) = 0;
  *((_QWORD *)v9 + 14) = 0;
  *((_QWORD *)v9 + 15) = 0;
  *((_QWORD *)v9 + 16) = 0;
  InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)v9 + 136), 0, 0);
  *(_OWORD *)((char *)v9 + 72) = 0;
  *((_QWORD *)v9 + 11) = 0;
  *((_OWORD *)v9 + 3) = *((_OWORD *)this + 3);
  *((_DWORD *)v9 + 16) = *((_DWORD *)this + 16);
  v10 = PropVariantCopy((PROPVARIANT *)v9 + 9, (const PROPVARIANT *)this + 9);
  if ( v10 < 0 )
    goto LABEL_25;
  v11 = -1;
  if ( v6 )
  {
    v12 = -1;
    do
      ++v12;
    while ( v6[v12] );
    *((_QWORD *)v9 + 12) = 0;
    v13 = v12 + 1;
    if ( v12 + 1 >= v12 && (v44 = 0, is_mul_ok(v13, 2u)) )
    {
      v14 = CoTaskMemAlloc(2 * v13);
      v15 = v14;
      *((_QWORD *)v9 + 12) = v14;
      v10 = -2147024882;
      if ( v14 )
        v10 = 0;
      if ( v10 < 0 )
        goto LABEL_25;
      if ( (v14 || v12 == -1) && v13 <= 0x7FFFFFFF )
      {
        if ( v12 >= 0x7FFFFFFF )
        {
          if ( v12 != -1 )
            *v14 = 0;
        }
        else
        {
          v16 = v12 + 1;
          v17 = v14;
          v18 = 0;
          do
          {
            if ( !v12 )
              break;
            v19 = *v6;
            if ( !*v6 )
              break;
            ++v6;
            *v17++ = v19;
            --v12;
            ++v18;
            --v16;
          }
          while ( v16 );
          v20 = v18 - 1;
          if ( v16 )
            v20 = v18;
          v21 = v17 - 1;
          if ( v16 )
            v21 = v17;
          *v21 = 0;
          if ( v16 )
          {
            v35 = v13 == v20;
            v34 = v13 - v20;
            if ( !v35 && v34 != 1 && (unsigned __int64)(2 * v34) > 2 )
              memset_0(&v15[v20 + 1], 0, 2 * v34 - 2);
          }
        }
      }
      else
      {
        *v14 = 0;
      }
    }
    else
    {
      v10 = -2147024362;
    }
    if ( v10 < 0 )
      goto LABEL_25;
    v4 = v47;
  }
  if ( !v5 )
    goto LABEL_92;
  do
    ++v11;
  while ( v5[v11] );
  *((_QWORD *)v9 + 13) = 0;
  v23 = v11 + 1;
  if ( v11 + 1 >= v11 && (v47 = 0, is_mul_ok(v23, 2u)) )
  {
    v24 = CoTaskMemAlloc(2 * v23);
    v25 = v24;
    *((_QWORD *)v9 + 13) = v24;
    v10 = -2147024882;
    if ( v24 )
      v10 = 0;
    if ( v10 < 0 )
      goto LABEL_25;
    if ( (v24 || v11 == -1) && v23 <= 0x7FFFFFFF )
    {
      if ( v11 >= 0x7FFFFFFF )
      {
        if ( v11 != -1 )
          *v24 = 0;
      }
      else
      {
        v26 = v11 + 1;
        v27 = v24;
        v28 = 0;
        do
        {
          if ( !v11 )
            break;
          v29 = *v5;
          if ( !*v5 )
            break;
          ++v5;
          *v27++ = v29;
          --v11;
          ++v28;
          --v26;
        }
        while ( v26 );
        v30 = v28 - 1;
        if ( v26 )
          v30 = v28;
        v31 = v27 - 1;
        if ( v26 )
          v31 = v27;
        *v31 = 0;
        if ( v26 )
        {
          v35 = v23 == v30;
          v39 = v23 - v30;
          if ( !v35 && v39 != 1 && (unsigned __int64)(2 * v39) > 2 )
            memset_0(&v25[v30 + 1], 0, 2 * v39 - 2);
        }
      }
    }
    else
    {
      *v24 = 0;
    }
  }
  else
  {
    v10 = -2147024362;
  }
  if ( v10 >= 0 )
  {
LABEL_92:
    if ( !v48
      || (v10 = (**(__int64 (__fastcall ***)(StructuredQuery1::AttributeList *, GUID *, __int64))v48)(
                  v48,
                  &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510,
                  (__int64)v9 + 112),
          v10 >= 0) )
    {
      if ( !v41 || (v10 = (**v41)(v41, &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510, (__int64)v9 + 120), v10 >= 0) )
      {
        if ( !v4 || (v10 = (**v4)(v4, &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510, (__int64)v9 + 128), v10 >= 0) )
        {
          v48 = 0;
          v32 = &v48;
          v33 = v42;
          do
          {
            if ( !v33 )
            {
              *((_QWORD *)v9 + 5) = v48;
              v10 = (**(__int64 (__fastcall ***)(StructuredQuery1::BaseCondition *, GUID *, struct ICondition **))v9)(
                      v9,
                      &GUID_0fc988d4_c935_4b97_a973_46282ea175c8,
                      &v40);
              goto LABEL_25;
            }
            v47 = 0;
            v10 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall ****)(_QWORD, GUID *, __int64)))(**(_QWORD **)(v33 + 16) + 64LL))(
                    *(_QWORD *)(v33 + 16),
                    &v47);
            if ( v10 >= 0 )
            {
              v36 = (StructuredQuery1::AttributeList **)operator new(
                                                          0x20u,
                                                          (const struct std::nothrow_t *)&std::nothrow);
              v37 = v36;
              v44 = (StructuredQuery1::BaseCondition *)v36;
              if ( v36 )
              {
                v38 = (StructuredQuery1::AttributeList *)v47;
                *(_OWORD *)v36 = *(_OWORD *)v33;
                v36[2] = v38;
                v36[3] = 0;
                (*(void (__fastcall **)(StructuredQuery1::AttributeList *))(*(_QWORD *)v38 + 8LL))(v38);
              }
              else
              {
                v37 = 0;
              }
              if ( v37 )
              {
                *v32 = (StructuredQuery1::AttributeList *)v37;
                v32 = v37 + 3;
              }
              else
              {
                v10 = -2147024882;
              }
              ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64)))(*v47)[2])(v47);
            }
            v33 = *(_QWORD *)(v33 + 24);
          }
          while ( v10 >= 0 );
          if ( v48 )
            StructuredQuery1::AttributeList::`scalar deleting destructor'(v48);
          *((_QWORD *)v9 + 5) = 0;
        }
      }
    }
  }
LABEL_25:
  (*(void (__fastcall **)(StructuredQuery1::BaseCondition *))(*(_QWORD *)v9 + 16LL))(v9);
LABEL_26:
  *a2 = v40;
  if ( v3 )
    LeaveCriticalSection(v3);
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000a520  mov     [rsp+arg_0], rbx
0x18000a525  mov     [rsp+arg_8], rdx
0x18000a52a  push    rbp
0x18000a52b  push    rsi
0x18000a52c  push    rdi
0x18000a52d  push    r12
0x18000a52f  push    r13
0x18000a531  push    r14
0x18000a533  push    r15
0x18000a535  sub     rsp, 50h
0x18000a539  mov     rbx, rcx
0x18000a53c  test    rdx, rdx
0x18000a53f  jz      loc_18000AAA8
0x18000a545  lea     r13, [rcx+88h]
0x18000a54c  mov     rcx, r13; lpCriticalSection
0x18000a54f  call    cs:__imp_EnterCriticalSection
0x18000a555  mov     [rsp+88h+var_50], r13
0x18000a55a  mov     rax, [rbx+28h]
0x18000a55e  mov     [rsp+88h+var_58], rax
0x18000a563  mov     r15, [rbx+80h]
0x18000a56a  mov     [rsp+88h+arg_10], r15
0x18000a572  mov     rax, [rbx+78h]
0x18000a576  mov     [rsp+88h+var_60], rax
0x18000a57b  mov     rax, [rbx+70h]
0x18000a57f  mov     [rsp+88h+arg_18], rax
0x18000a587  mov     r14, [rbx+68h]
0x18000a58b  mov     rdi, [rbx+60h]
0x18000a58f  mov     esi, [rbx+44h]
0x18000a592  xor     ebp, ebp
0x18000a594  mov     [rsp+88h+var_68], rbp
0x18000a599  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a5a0  mov     ecx, 0B0h; unsigned __int64
0x18000a5a5  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a5aa  mov     r12, rax
0x18000a5ad  mov     [rsp+88h+var_48], rax
0x18000a5b2  test    rax, rax
0x18000a5b5  jz      loc_18000AB28
0x18000a5bb  mov     rcx, rax; this
0x18000a5be  call    ??0BaseCondition@StructuredQuery1@@IEAA@XZ; StructuredQuery1::BaseCondition::BaseCondition(void)
0x18000a5c3  lea     rcx, ??_7LeafCondition@StructuredQuery1@@6BICondition2@@@; const StructuredQuery1::LeafCondition::`vftable'{for `ICondition2'}
0x18000a5ca  mov     [r12], rcx
0x18000a5ce  lea     rax, ??_7NegationCondition@StructuredQuery1@@6BIConditionAttributeContainer@@@; const StructuredQuery1::NegationCondition::`vftable'{for `IConditionAttributeContainer'}
0x18000a5d5  mov     [r12+8], rax
0x18000a5da  lea     rax, ??_7LeafCondition@StructuredQuery1@@6BIPersistXML@@@; const StructuredQuery1::LeafCondition::`vftable'{for `IPersistXML'}
0x18000a5e1  mov     [r12+10h], rax
0x18000a5e6  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x18000a5ed  movups  xmmword ptr [r12+30h], xmm0
0x18000a5f3  mov     eax, cs:PKEY_Null.pid
0x18000a5f9  mov     [r12+40h], eax
0x18000a5fe  mov     [r12+44h], esi
0x18000a603  mov     [r12+60h], rbp
0x18000a608  mov     [r12+68h], rbp
0x18000a60d  mov     [r12+70h], rbp
0x18000a612  mov     [r12+78h], rbp
0x18000a617  mov     [r12+80h], rbp
0x18000a61f  lea     rcx, [r12+88h]; lpCriticalSection
0x18000a627  xor     r8d, r8d; Flags
0x18000a62a  xor     edx, edx; dwSpinCount
0x18000a62c  call    cs:__imp_InitializeCriticalSectionEx
0x18000a632  lea     rcx, [r12+48h]; pvarDest
0x18000a637  xorps   xmm0, xmm0
0x18000a63a  xor     eax, eax
0x18000a63c  movups  xmmword ptr [rcx], xmm0
0x18000a63f  mov     [rcx+10h], rax
0x18000a643  movups  xmm0, xmmword ptr [rbx+30h]
0x18000a647  movups  xmmword ptr [r12+30h], xmm0
0x18000a64d  mov     eax, [rbx+40h]
0x18000a650  mov     [r12+40h], eax
0x18000a655  lea     rdx, [rbx+48h]; pvarSrc
0x18000a659  call    cs:__imp_PropVariantCopy
0x18000a65f  mov     ebp, eax
0x18000a661  test    eax, eax
0x18000a663  js      loc_18000A756
0x18000a669  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000a670  test    rdi, rdi
0x18000a673  jz      loc_18000AAF5
0x18000a679  mov     rbx, rsi
0x18000a67c  nop     dword ptr [rax+00h]
0x18000a680  inc     rbx
0x18000a683  cmp     word ptr [rdi+rbx*2], 0
0x18000a688  jnz     short loc_18000A680
0x18000a68a  xor     r11d, r11d
0x18000a68d  mov     [r12+60h], r11
0x18000a692  lea     r15, [rbx+1]
0x18000a696  cmp     r15, rbx
0x18000a699  jb      loc_18000A79E
0x18000a69f  mov     [rsp+88h+var_48], r11
0x18000a6a4  mov     eax, 2
0x18000a6a9  mul     r15
0x18000a6ac  test    rdx, rdx
0x18000a6af  jnz     loc_18000A79E
0x18000a6b5  mov     rcx, rax; cb
0x18000a6b8  call    cs:__imp_CoTaskMemAlloc
0x18000a6be  mov     r10, rax
0x18000a6c1  mov     [r12+60h], rax
0x18000a6c6  xor     r11d, r11d
0x18000a6c9  mov     ebp, 8007000Eh
0x18000a6ce  test    rax, rax
0x18000a6d1  cmovnz  ebp, r11d
0x18000a6d5  test    ebp, ebp
0x18000a6d7  js      short loc_18000A756
0x18000a6d9  test    rax, rax
0x18000a6dc  jz      loc_18000AAD1
0x18000a6e2  cmp     r15, 7FFFFFFFh
0x18000a6e9  ja      loc_18000AADA
0x18000a6ef  cmp     rbx, 7FFFFFFFh
0x18000a6f6  jnb     loc_18000AAE3
0x18000a6fc  test    r15, r15
0x18000a6ff  jz      short loc_18000A752
0x18000a701  mov     rdx, r15
0x18000a704  mov     r8, r10
0x18000a707  mov     rcx, r11
0x18000a70a  nop     word ptr [rax+rax+00h]
0x18000a710  test    rbx, rbx
0x18000a713  jz      short loc_18000A735
0x18000a715  movzx   eax, word ptr [rdi]
0x18000a718  test    ax, ax
0x18000a71b  jz      short loc_18000A735
0x18000a71d  add     rdi, 2
0x18000a721  mov     [r8], ax
0x18000a725  add     r8, 2
0x18000a729  dec     rbx
0x18000a72c  inc     rcx
0x18000a72f  sub     rdx, 1
0x18000a733  jnz     short loc_18000A710
0x18000a735  lea     r9, [rcx-1]
0x18000a739  test    rdx, rdx
0x18000a73c  cmovnz  r9, rcx
0x18000a740  lea     rcx, [r8-2]
0x18000a744  cmovnz  rcx, r8
0x18000a748  mov     [rcx], r11w
0x18000a74c  jnz     loc_18000A97D
0x18000a752  test    ebp, ebp
0x18000a754  jns     short loc_18000A7A5
0x18000a756  mov     rax, [r12]
0x18000a75a  mov     rcx, r12
0x18000a75d  mov     rax, [rax+10h]
0x18000a761  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a766  mov     rax, [rsp+88h+var_68]
0x18000a76b  mov     rcx, [rsp+88h+arg_8]
0x18000a773  mov     [rcx], rax
0x18000a776  test    r13, r13
0x18000a779  jz      short loc_18000A784
0x18000a77b  mov     rcx, r13; lpCriticalSection
0x18000a77e  call    cs:__imp_LeaveCriticalSection
0x18000a784  mov     eax, ebp
0x18000a786  mov     rbx, [rsp+88h+arg_0]
0x18000a78e  add     rsp, 50h
0x18000a792  pop     r15
0x18000a794  pop     r14
0x18000a796  pop     r13
0x18000a798  pop     r12
0x18000a79a  pop     rdi
0x18000a79b  pop     rsi
0x18000a79c  pop     rbp
0x18000a79d  retn
0x18000a79e  mov     ebp, 80070216h
0x18000a7a3  jmp     short loc_18000A752
0x18000a7a5  mov     r15, [rsp+88h+arg_10]
0x18000a7ad  test    r14, r14
0x18000a7b0  jz      loc_18000A89B
0x18000a7b6  nop     word ptr [rax+rax+00000000h]
0x18000a7c0  inc     rsi
0x18000a7c3  cmp     word ptr [r14+rsi*2], 0
0x18000a7c9  jnz     short loc_18000A7C0
0x18000a7cb  mov     [r12+68h], r11
0x18000a7d0  lea     rbx, [rsi+1]
0x18000a7d4  cmp     rbx, rsi
0x18000a7d7  jb      loc_18000A973
0x18000a7dd  mov     [rsp+88h+arg_10], r11
0x18000a7e5  mov     eax, 2
0x18000a7ea  mul     rbx
0x18000a7ed  test    rdx, rdx
0x18000a7f0  jnz     loc_18000A973
0x18000a7f6  mov     rcx, rax; cb
0x18000a7f9  call    cs:__imp_CoTaskMemAlloc
0x18000a7ff  mov     r10, rax
0x18000a802  mov     [r12+68h], rax
0x18000a807  xor     r11d, r11d
0x18000a80a  mov     ebp, 8007000Eh
0x18000a80f  test    rax, rax
0x18000a812  cmovnz  ebp, r11d
0x18000a816  test    ebp, ebp
0x18000a818  js      loc_18000A756
0x18000a81e  test    rax, rax
0x18000a821  jz      loc_18000AAFD
0x18000a827  cmp     rbx, 7FFFFFFFh
0x18000a82e  ja      loc_18000AB06
0x18000a834  cmp     rsi, 7FFFFFFFh
0x18000a83b  jnb     loc_18000AB0F
0x18000a841  test    rbx, rbx
0x18000a844  jz      short loc_18000A893
0x18000a846  mov     rdx, rbx
0x18000a849  mov     r8, r10
0x18000a84c  mov     rcx, r11
0x18000a84f  nop
0x18000a850  test    rsi, rsi
0x18000a853  jz      short loc_18000A876
0x18000a855  movzx   eax, word ptr [r14]
0x18000a859  test    ax, ax
0x18000a85c  jz      short loc_18000A876
0x18000a85e  add     r14, 2
0x18000a862  mov     [r8], ax
0x18000a866  add     r8, 2
0x18000a86a  dec     rsi
0x18000a86d  inc     rcx
0x18000a870  sub     rdx, 1
0x18000a874  jnz     short loc_18000A850
0x18000a876  lea     r9, [rcx-1]
0x18000a87a  test    rdx, rdx
0x18000a87d  cmovnz  r9, rcx
0x18000a881  lea     rcx, [r8-2]
0x18000a885  cmovnz  rcx, r8
0x18000a889  mov     [rcx], r11w
0x18000a88d  jnz     loc_18000AA6F
0x18000a893  test    ebp, ebp
0x18000a895  js      loc_18000A756
0x18000a89b  mov     rcx, [rsp+88h+arg_18]
0x18000a8a3  test    rcx, rcx
0x18000a8a6  jz      short loc_18000A8C9
0x18000a8a8  mov     rax, [rcx]
0x18000a8ab  lea     r8, [r12+70h]
0x18000a8b0  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x18000a8b7  mov     rax, [rax]
0x18000a8ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8bf  mov     ebp, eax
0x18000a8c1  test    eax, eax
0x18000a8c3  js      loc_18000A756
0x18000a8c9  mov     rcx, [rsp+88h+var_60]
0x18000a8ce  test    rcx, rcx
0x18000a8d1  jz      short loc_18000A8F4
0x18000a8d3  mov     rax, [rcx]
0x18000a8d6  lea     r8, [r12+78h]
0x18000a8db  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x18000a8e2  mov     rax, [rax]
0x18000a8e5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a8ea  mov     ebp, eax
0x18000a8ec  test    eax, eax
0x18000a8ee  js      loc_18000A756
0x18000a8f4  test    r15, r15
0x18000a8f7  jz      short loc_18000A920
0x18000a8f9  mov     rax, [r15]
0x18000a8fc  lea     r8, [r12+80h]
0x18000a904  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x18000a90b  mov     rcx, r15
0x18000a90e  mov     rax, [rax]
0x18000a911  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a916  mov     ebp, eax
0x18000a918  test    eax, eax
0x18000a91a  js      loc_18000A756
0x18000a920  xor     ebp, ebp
0x18000a922  mov     [rsp+88h+arg_18], rbp
0x18000a92a  lea     rdi, [rsp+88h+arg_18]
0x18000a932  mov     rsi, [rsp+88h+var_58]
0x18000a937  test    rsi, rsi
0x18000a93a  jnz     short loc_18000A9B2
0x18000a93c  mov     rax, [rsp+88h+arg_18]
0x18000a944  mov     [r12+28h], rax
0x18000a949  test    ebp, ebp
0x18000a94b  js      loc_18000A756
0x18000a951  mov     rax, [r12]
0x18000a955  lea     r8, [rsp+88h+var_68]
0x18000a95a  lea     rdx, _GUID_0fc988d4_c935_4b97_a973_46282ea175c8
0x18000a961  mov     rcx, r12
0x18000a964  mov     rax, [rax]
0x18000a967  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a96c  mov     ebp, eax
0x18000a96e  jmp     loc_18000A756
0x18000a973  mov     ebp, 80070216h
0x18000a978  jmp     loc_18000A893
0x18000a97d  sub     r15, r9
0x18000a980  cmp     r15, 1
0x18000a984  jbe     loc_18000A752
0x18000a98a  lea     r8, [r15+r15]
0x18000a98e  cmp     r8, 2
0x18000a992  jbe     loc_18000A752
0x18000a998  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000a99c  inc     r9
0x18000a99f  lea     rcx, [r10+r9*2]; void *
0x18000a9a3  xor     edx, edx; Val
0x18000a9a5  call    memset_0
0x18000a9aa  xor     r11d, r11d
0x18000a9ad  jmp     loc_18000A752
0x18000a9b2  mov     [rsp+88h+arg_10], 0
0x18000a9be  mov     rcx, [rsi+10h]
0x18000a9c2  mov     rax, [rcx]
0x18000a9c5  lea     rdx, [rsp+88h+arg_10]
0x18000a9cd  mov     rax, [rax+40h]
0x18000a9d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a9d6  mov     ebp, eax
0x18000a9d8  test    eax, eax
0x18000a9da  js      short loc_18000AA45
0x18000a9dc  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000a9e3  mov     ecx, 20h ; ' '; unsigned __int64
0x18000a9e8  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000a9ed  mov     rbx, rax
0x18000a9f0  mov     [rsp+88h+var_48], rax
0x18000a9f5  test    rax, rax
0x18000a9f8  jz      loc_18000AB21
0x18000a9fe  mov     rcx, [rsp+88h+arg_10]
  ... truncated ...
```
