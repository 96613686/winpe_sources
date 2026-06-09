# StructuredQuery1::LeafCondition::CreateInstance(_tagpropertykey const &,tagCONDITION_OPERATION,wchar_t const *,tagPROPVARIANT const &,wchar_t const *,IRichChunk *,IRichChunk *,IRichChunk *,StructuredQuery1::AttributeList *,_GUID const &,void * *)

- ea: `0x18000abd0`
- end: `0x18000b122`
- name: `?CreateInstance@LeafCondition@StructuredQuery1@@SAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEB_WAEBUtagPROPVARIANT@@2PEAUIRichChunk@@44PEAVAttributeList@2@AEBU_GUID@@PEAPEAX@Z`
- size: `1362`
- prototype: `static int(const struct _tagpropertykey *, enum tagCONDITION_OPERATION, const wchar_t *, const struct tagPROPVARIANT *, const wchar_t *, struct IRichChunk *, struct IRichChunk *, struct IRichChunk *, struct StructuredQuery1::AttributeList *, const struct _GUID *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180009a40`

## callees

- `0x18000abd0`
- `0x18000b130`
- `0x18003716c`
- `0x18005db64`
- `0x18005e740`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000ac82`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x18000ac82`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000acaa`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x18000acaa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ad07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ae24`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ad07`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000ae24`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StructuredQuery1::LeafCondition::CreateInstance(
        const struct _tagpropertykey *a1,
        enum tagCONDITION_OPERATION a2,
        const wchar_t *a3,
        const PROPVARIANT *a4,
        const wchar_t *a5,
        struct IRichChunk *a6,
        struct IRichChunk *a7,
        struct IRichChunk *a8,
        struct StructuredQuery1::AttributeList *a9,
        const struct _GUID *a10,
        void **a11)
{
  StructuredQuery1::AttributeList *v15; // rax
  StructuredQuery1::AttributeList *v16; // r15
  char *v17; // r14
  HRESULT v18; // ebp
  unsigned __int64 v19; // rsi
  unsigned __int64 v20; // rbx
  unsigned __int64 v21; // r14
  _WORD *v22; // rax
  _WORD *v23; // r10
  unsigned __int64 v24; // rdx
  _WORD *v25; // r8
  __int64 v26; // rcx
  __int16 v27; // ax
  __int64 v28; // r9
  _WORD *v29; // rcx
  const wchar_t *v31; // rbx
  unsigned __int64 v32; // rdi
  wchar_t *v33; // rax
  wchar_t *v34; // r10
  unsigned __int64 v35; // rdx
  __int64 v36; // r8
  wchar_t v37; // cx
  __int64 v38; // r9
  wchar_t *v39; // rcx
  StructuredQuery1::AttributeList **v41; // rsi
  __int64 v42; // r14
  bool v43; // cf
  StructuredQuery1::AttributeList **v44; // rax
  StructuredQuery1::AttributeList **v45; // rdi
  StructuredQuery1::AttributeList *v46; // rcx
  __int64 v47; // rdi
  StructuredQuery1::AttributeList *v48; // [rsp+20h] [rbp-68h] BYREF
  StructuredQuery1::AttributeList *v49; // [rsp+28h] [rbp-60h] BYREF
  _QWORD v50[11]; // [rsp+30h] [rbp-58h] BYREF

  v50[0] = 0;
  v15 = (StructuredQuery1::AttributeList *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
  v16 = v15;
  v49 = v15;
  if ( v15 )
  {
    StructuredQuery1::BaseCondition::BaseCondition(v15);
    *(_QWORD *)v16 = &StructuredQuery1::LeafCondition::`vftable'{for `ICondition2'};
    *((_QWORD *)v16 + 1) = &StructuredQuery1::NegationCondition::`vftable'{for `IConditionAttributeContainer'};
    *((_QWORD *)v16 + 2) = &StructuredQuery1::LeafCondition::`vftable'{for `IPersistXML'};
    *(PROPERTYKEY *)((char *)v16 + 48) = PKEY_Null;
    *((_DWORD *)v16 + 17) = a2;
    *((_QWORD *)v16 + 12) = 0;
    *((_QWORD *)v16 + 13) = 0;
    *((_QWORD *)v16 + 14) = 0;
    *((_QWORD *)v16 + 15) = 0;
    v17 = (char *)v16 + 128;
    *((_QWORD *)v16 + 16) = 0;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)((char *)v16 + 136), 0, 0);
    *(_OWORD *)((char *)v16 + 72) = 0;
    *((_QWORD *)v16 + 11) = 0;
    *((_OWORD *)v16 + 3) = a1->fmtid;
    *((_DWORD *)v16 + 16) = a1->pid;
    v18 = PropVariantCopy((PROPVARIANT *)v16 + 9, a4);
    if ( v18 < 0 )
      goto LABEL_24;
    v19 = -1;
    if ( a3 )
    {
      v20 = -1;
      do
        ++v20;
      while ( a3[v20] );
      *((_QWORD *)v16 + 12) = 0;
      v21 = v20 + 1;
      if ( v20 + 1 >= v20 && (v49 = 0, is_mul_ok(v21, 2u)) )
      {
        v22 = CoTaskMemAlloc(2 * v21);
        v23 = v22;
        *((_QWORD *)v16 + 12) = v22;
        v18 = -2147024882;
        if ( v22 )
          v18 = 0;
        if ( v18 < 0 )
          goto LABEL_24;
        if ( (v22 || v20 == -1) && v21 <= 0x7FFFFFFF )
        {
          if ( v20 >= 0x7FFFFFFF )
          {
            if ( v20 != -1 )
              *v22 = 0;
          }
          else
          {
            v24 = v20 + 1;
            v25 = v22;
            v26 = 0;
            do
            {
              if ( !v20 )
                break;
              v27 = *a3;
              if ( !*a3 )
                break;
              ++a3;
              *v25++ = v27;
              --v20;
              ++v26;
              --v24;
            }
            while ( v24 );
            v28 = v26 - 1;
            if ( v24 )
              v28 = v26;
            v29 = v25 - 1;
            if ( v24 )
              v29 = v25;
            *v29 = 0;
            if ( v24 )
            {
              v43 = v21 == v28;
              v42 = v21 - v28;
              if ( !v43 && v42 != 1 && (unsigned __int64)(2 * v42) > 2 )
                memset_0(&v23[v28 + 1], 0, 2 * v42 - 2);
            }
          }
        }
        else
        {
          *v22 = 0;
        }
      }
      else
      {
        v18 = -2147024362;
      }
      if ( v18 < 0 )
        goto LABEL_24;
      v17 = (char *)v16 + 128;
    }
    v31 = a5;
    if ( !a5 )
      goto LABEL_87;
    do
      ++v19;
    while ( a5[v19] );
    *((_QWORD *)v16 + 13) = 0;
    v32 = v19 + 1;
    if ( v19 + 1 >= v19 && (v49 = 0, is_mul_ok(v32, 2u)) )
    {
      v33 = (wchar_t *)CoTaskMemAlloc(2 * v32);
      v34 = v33;
      *((_QWORD *)v16 + 13) = v33;
      v18 = -2147024882;
      if ( v33 )
        v18 = 0;
      if ( v18 < 0 )
        goto LABEL_24;
      if ( (v33 || v19 == -1) && v32 <= 0x7FFFFFFF )
      {
        if ( v19 >= 0x7FFFFFFF )
        {
          if ( v19 != -1 )
            *v33 = 0;
        }
        else
        {
          v35 = v19 + 1;
          v36 = 0;
          do
          {
            if ( !v19 )
              break;
            v37 = *v31;
            if ( !*v31 )
              break;
            ++v31;
            *v33++ = v37;
            --v19;
            ++v36;
            --v35;
          }
          while ( v35 );
          v38 = v36 - 1;
          if ( v35 )
            v38 = v36;
          v39 = v33 - 1;
          if ( v35 )
            v39 = v33;
          *v39 = 0;
          if ( v35 )
          {
            v43 = v32 == v38;
            v47 = v32 - v38;
            if ( !v43 && v47 != 1 && (unsigned __int64)(2 * v47) > 2 )
              memset_0(&v34[v38 + 1], 0, 2 * v47 - 2);
          }
        }
      }
      else
      {
        *v33 = 0;
      }
    }
    else
    {
      v18 = -2147024362;
    }
    if ( v18 >= 0 )
    {
LABEL_87:
      if ( !a6
        || (v18 = ((__int64 (__fastcall *)(struct IRichChunk *, GUID *, char *))a6->lpVtbl->QueryInterface)(
                    a6,
                    &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510,
                    (char *)v16 + 112),
            v18 >= 0) )
      {
        if ( !a7
          || (v18 = ((__int64 (__fastcall *)(struct IRichChunk *, GUID *, char *))a7->lpVtbl->QueryInterface)(
                      a7,
                      &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510,
                      (char *)v16 + 120),
              v18 >= 0) )
        {
          if ( !a8
            || (v18 = ((__int64 (__fastcall *)(struct IRichChunk *, GUID *, char *))a8->lpVtbl->QueryInterface)(
                        a8,
                        &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510,
                        v17),
                v18 >= 0) )
          {
            v49 = 0;
            v41 = &v49;
            do
            {
              if ( !a9 )
              {
                *((_QWORD *)v16 + 5) = v49;
                v18 = (**(__int64 (__fastcall ***)(StructuredQuery1::AttributeList *, const struct _GUID *, _QWORD *))v16)(
                        v16,
                        a10,
                        v50);
                goto LABEL_24;
              }
              v48 = 0;
              v18 = (*(__int64 (__fastcall **)(_QWORD, StructuredQuery1::AttributeList **))(**((_QWORD **)a9 + 2) + 64LL))(
                      *((_QWORD *)a9 + 2),
                      &v48);
              if ( v18 >= 0 )
              {
                v44 = (StructuredQuery1::AttributeList **)operator new(
                                                            0x20u,
                                                            (const struct std::nothrow_t *)&std::nothrow);
                v45 = v44;
                v50[1] = v44;
                if ( v44 )
                {
                  v46 = v48;
                  *(_OWORD *)v44 = *(_OWORD *)a9;
                  v44[2] = v46;
                  v44[3] = 0;
                  (*(void (__fastcall **)(StructuredQuery1::AttributeList *))(*(_QWORD *)v46 + 8LL))(v46);
                }
                else
                {
                  v45 = 0;
                }
                if ( v45 )
                {
                  *v41 = (StructuredQuery1::AttributeList *)v45;
                  v41 = v45 + 3;
                }
                else
                {
                  v18 = -2147024882;
                }
                (*(void (__fastcall **)(StructuredQuery1::AttributeList *))(*(_QWORD *)v48 + 16LL))(v48);
              }
              a9 = (struct StructuredQuery1::AttributeList *)*((_QWORD *)a9 + 3);
            }
            while ( v18 >= 0 );
            if ( v49 )
              StructuredQuery1::AttributeList::`scalar deleting destructor'(v49);
            *((_QWORD *)v16 + 5) = 0;
          }
        }
      }
    }
LABEL_24:
    (*(void (__fastcall **)(StructuredQuery1::AttributeList *))(*(_QWORD *)v16 + 16LL))(v16);
    *a11 = (void *)v50[0];
    return (unsigned int)v18;
  }
  *a11 = (void *)v50[0];
  return 2147942414LL;
}

```

## disassembly

```asm
0x18000abd0  push    rbx
0x18000abd2  push    rbp
0x18000abd3  push    rsi
0x18000abd4  push    rdi
0x18000abd5  push    r12
0x18000abd7  push    r13
0x18000abd9  push    r14
0x18000abdb  push    r15
0x18000abdd  sub     rsp, 48h
0x18000abe1  mov     rsi, r9
0x18000abe4  mov     rdi, r8
0x18000abe7  mov     ebp, edx
0x18000abe9  mov     rbx, rcx
0x18000abec  xor     r14d, r14d
0x18000abef  mov     [rsp+88h+var_58], r14
0x18000abf4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000abfb  mov     ecx, 0B0h; unsigned __int64
0x18000ac00  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000ac05  mov     r15, rax
0x18000ac08  mov     [rsp+88h+var_60], rax
0x18000ac0d  test    rax, rax
0x18000ac10  jz      loc_18000B108
0x18000ac16  mov     rcx, rax; this
0x18000ac19  call    ??0BaseCondition@StructuredQuery1@@IEAA@XZ; StructuredQuery1::BaseCondition::BaseCondition(void)
0x18000ac1e  lea     rcx, ??_7LeafCondition@StructuredQuery1@@6BICondition2@@@; const StructuredQuery1::LeafCondition::`vftable'{for `ICondition2'}
0x18000ac25  mov     [r15], rcx
0x18000ac28  lea     rax, ??_7NegationCondition@StructuredQuery1@@6BIConditionAttributeContainer@@@; const StructuredQuery1::NegationCondition::`vftable'{for `IConditionAttributeContainer'}
0x18000ac2f  mov     [r15+8], rax
0x18000ac33  lea     rax, ??_7LeafCondition@StructuredQuery1@@6BIPersistXML@@@; const StructuredQuery1::LeafCondition::`vftable'{for `IPersistXML'}
0x18000ac3a  mov     [r15+10h], rax
0x18000ac3e  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x18000ac45  movups  xmmword ptr [r15+30h], xmm0
0x18000ac4a  mov     eax, cs:PKEY_Null.pid
0x18000ac50  mov     [r15+40h], eax
0x18000ac54  mov     [r15+44h], ebp
0x18000ac58  mov     [r15+60h], r14
0x18000ac5c  mov     [r15+68h], r14
0x18000ac60  mov     [r15+70h], r14
0x18000ac64  mov     [r15+78h], r14
0x18000ac68  lea     r14, [r15+80h]
0x18000ac6f  mov     qword ptr [r14], 0
0x18000ac76  lea     rcx, [r15+88h]; lpCriticalSection
0x18000ac7d  xor     r8d, r8d; Flags
0x18000ac80  xor     edx, edx; dwSpinCount
0x18000ac82  call    cs:__imp_InitializeCriticalSectionEx
0x18000ac88  lea     rcx, [r15+48h]; pvarDest
0x18000ac8c  xorps   xmm0, xmm0
0x18000ac8f  xor     eax, eax
0x18000ac91  movups  xmmword ptr [rcx], xmm0
0x18000ac94  mov     [rcx+10h], rax
0x18000ac98  movups  xmm0, xmmword ptr [rbx]
0x18000ac9b  movups  xmmword ptr [r15+30h], xmm0
0x18000aca0  mov     eax, [rbx+10h]
0x18000aca3  mov     [r15+40h], eax
0x18000aca7  mov     rdx, rsi; pvarSrc
0x18000acaa  call    cs:__imp_PropVariantCopy
0x18000acb0  mov     ebp, eax
0x18000acb2  test    eax, eax
0x18000acb4  js      loc_18000AD9E
0x18000acba  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x18000acc1  test    rdi, rdi
0x18000acc4  jz      loc_18000B0D4
0x18000acca  mov     rbx, rsi
0x18000accd  nop     dword ptr [rax]
0x18000acd0  inc     rbx
0x18000acd3  cmp     word ptr [rdi+rbx*2], 0
0x18000acd8  jnz     short loc_18000ACD0
0x18000acda  xor     r11d, r11d
0x18000acdd  mov     [r15+60h], r11
0x18000ace1  lea     r14, [rbx+1]
0x18000ace5  cmp     r14, rbx
0x18000ace8  jb      loc_18000ADD0
0x18000acee  mov     [rsp+88h+var_60], r11
0x18000acf3  mov     eax, 2
0x18000acf8  mul     r14
0x18000acfb  test    rdx, rdx
0x18000acfe  jnz     loc_18000ADD0
0x18000ad04  mov     rcx, rax; cb
0x18000ad07  call    cs:__imp_CoTaskMemAlloc
0x18000ad0d  mov     r10, rax
0x18000ad10  mov     [r15+60h], rax
0x18000ad14  xor     r11d, r11d
0x18000ad17  mov     ebp, 8007000Eh
0x18000ad1c  test    rax, rax
0x18000ad1f  cmovnz  ebp, r11d
0x18000ad23  test    ebp, ebp
0x18000ad25  js      short loc_18000AD9E
0x18000ad27  test    rax, rax
0x18000ad2a  jz      loc_18000B0B0
0x18000ad30  cmp     r14, 7FFFFFFFh
0x18000ad37  ja      loc_18000B0B9
0x18000ad3d  cmp     rbx, 7FFFFFFFh
0x18000ad44  jnb     loc_18000B0C2
0x18000ad4a  test    r14, r14
0x18000ad4d  jz      short loc_18000AD9A
0x18000ad4f  mov     rdx, r14
0x18000ad52  mov     r8, r10
0x18000ad55  mov     rcx, r11
0x18000ad58  test    rbx, rbx
0x18000ad5b  jz      short loc_18000AD7D
0x18000ad5d  movzx   eax, word ptr [rdi]
0x18000ad60  test    ax, ax
0x18000ad63  jz      short loc_18000AD7D
0x18000ad65  add     rdi, 2
0x18000ad69  mov     [r8], ax
0x18000ad6d  add     r8, 2
0x18000ad71  dec     rbx
0x18000ad74  inc     rcx
0x18000ad77  sub     rdx, 1
0x18000ad7b  jnz     short loc_18000AD58
0x18000ad7d  lea     r9, [rcx-1]
0x18000ad81  test    rdx, rdx
0x18000ad84  cmovnz  r9, rcx
0x18000ad88  lea     rcx, [r8-2]
0x18000ad8c  cmovnz  rcx, r8
0x18000ad90  mov     [rcx], r11w
0x18000ad94  jnz     loc_18000AF9F
0x18000ad9a  test    ebp, ebp
0x18000ad9c  jns     short loc_18000ADD7
0x18000ad9e  mov     rax, [r15]
0x18000ada1  mov     rcx, r15
0x18000ada4  mov     rax, [rax+10h]
0x18000ada8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adad  mov     rcx, [rsp+88h+arg_50]
0x18000adb5  mov     rax, [rsp+88h+var_58]
0x18000adba  mov     [rcx], rax
0x18000adbd  mov     eax, ebp
0x18000adbf  add     rsp, 48h
0x18000adc3  pop     r15
0x18000adc5  pop     r14
0x18000adc7  pop     r13
0x18000adc9  pop     r12
0x18000adcb  pop     rdi
0x18000adcc  pop     rsi
0x18000adcd  pop     rbp
0x18000adce  pop     rbx
0x18000adcf  retn
0x18000add0  mov     ebp, 80070216h
0x18000add5  jmp     short loc_18000AD9A
0x18000add7  lea     r14, [r15+80h]
0x18000adde  mov     rbx, [rsp+88h+arg_20]
0x18000ade6  test    rbx, rbx
0x18000ade9  jz      loc_18000AEBF
0x18000adef  nop
0x18000adf0  inc     rsi
0x18000adf3  cmp     word ptr [rbx+rsi*2], 0
0x18000adf8  jnz     short loc_18000ADF0
0x18000adfa  mov     [r15+68h], r11
0x18000adfe  lea     rdi, [rsi+1]
0x18000ae02  cmp     rdi, rsi
0x18000ae05  jb      loc_18000AF95
0x18000ae0b  mov     [rsp+88h+var_60], r11
0x18000ae10  mov     eax, 2
0x18000ae15  mul     rdi
0x18000ae18  test    rdx, rdx
0x18000ae1b  jnz     loc_18000AF95
0x18000ae21  mov     rcx, rax; cb
0x18000ae24  call    cs:__imp_CoTaskMemAlloc
0x18000ae2a  mov     r10, rax
0x18000ae2d  mov     [r15+68h], rax
0x18000ae31  xor     r11d, r11d
0x18000ae34  mov     ebp, 8007000Eh
0x18000ae39  test    rax, rax
0x18000ae3c  cmovnz  ebp, r11d
0x18000ae40  test    ebp, ebp
0x18000ae42  js      loc_18000AD9E
0x18000ae48  test    rax, rax
0x18000ae4b  jz      loc_18000B0DC
0x18000ae51  cmp     rdi, 7FFFFFFFh
0x18000ae58  ja      loc_18000B0E5
0x18000ae5e  cmp     rsi, 7FFFFFFFh
0x18000ae65  jnb     loc_18000B0EE
0x18000ae6b  test    rdi, rdi
0x18000ae6e  jz      short loc_18000AEB7
0x18000ae70  mov     rdx, rdi
0x18000ae73  mov     r8, r11
0x18000ae76  test    rsi, rsi
0x18000ae79  jz      short loc_18000AE9A
0x18000ae7b  movzx   ecx, word ptr [rbx]
0x18000ae7e  test    cx, cx
0x18000ae81  jz      short loc_18000AE9A
0x18000ae83  add     rbx, 2
0x18000ae87  mov     [rax], cx
0x18000ae8a  add     rax, 2
0x18000ae8e  dec     rsi
0x18000ae91  inc     r8
0x18000ae94  sub     rdx, 1
0x18000ae98  jnz     short loc_18000AE76
0x18000ae9a  lea     r9, [r8-1]
0x18000ae9e  test    rdx, rdx
0x18000aea1  cmovnz  r9, r8
0x18000aea5  lea     rcx, [rax-2]
0x18000aea9  cmovnz  rcx, rax
0x18000aead  mov     [rcx], r11w
0x18000aeb1  jnz     loc_18000B077
0x18000aeb7  test    ebp, ebp
0x18000aeb9  js      loc_18000AD9E
0x18000aebf  mov     rcx, [rsp+88h+arg_28]
0x18000aec7  test    rcx, rcx
0x18000aeca  jz      short loc_18000AEEC
0x18000aecc  mov     rax, [rcx]
0x18000aecf  lea     r8, [r15+70h]
0x18000aed3  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x18000aeda  mov     rax, [rax]
0x18000aedd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee2  mov     ebp, eax
0x18000aee4  test    eax, eax
0x18000aee6  js      loc_18000AD9E
0x18000aeec  mov     rcx, [rsp+88h+arg_30]
0x18000aef4  test    rcx, rcx
0x18000aef7  jz      short loc_18000AF19
0x18000aef9  mov     rax, [rcx]
0x18000aefc  lea     r8, [r15+78h]
0x18000af00  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x18000af07  mov     rax, [rax]
0x18000af0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af0f  mov     ebp, eax
0x18000af11  test    eax, eax
0x18000af13  js      loc_18000AD9E
0x18000af19  mov     rcx, [rsp+88h+arg_38]
0x18000af21  test    rcx, rcx
0x18000af24  jz      short loc_18000AF45
0x18000af26  mov     rax, [rcx]
0x18000af29  mov     r8, r14
0x18000af2c  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x18000af33  mov     rax, [rax]
0x18000af36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af3b  mov     ebp, eax
0x18000af3d  test    eax, eax
0x18000af3f  js      loc_18000AD9E
0x18000af45  mov     rbx, [rsp+88h+arg_40]
0x18000af4d  xor     r14d, r14d
0x18000af50  mov     ebp, r14d
0x18000af53  mov     [rsp+88h+var_60], r14
0x18000af58  lea     rsi, [rsp+88h+var_60]
0x18000af5d  test    rbx, rbx
0x18000af60  jnz     short loc_18000AFD4
0x18000af62  mov     rax, [rsp+88h+var_60]
0x18000af67  mov     [r15+28h], rax
0x18000af6b  test    ebp, ebp
0x18000af6d  js      loc_18000AD9E
0x18000af73  mov     rax, [r15]
0x18000af76  lea     r8, [rsp+88h+var_58]
0x18000af7b  mov     rdx, [rsp+88h+arg_48]
0x18000af83  mov     rcx, r15
0x18000af86  mov     rax, [rax]
0x18000af89  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af8e  mov     ebp, eax
0x18000af90  jmp     loc_18000AD9E
0x18000af95  mov     ebp, 80070216h
0x18000af9a  jmp     loc_18000AEB7
0x18000af9f  sub     r14, r9
0x18000afa2  cmp     r14, 1
0x18000afa6  jbe     loc_18000AD9A
0x18000afac  lea     r8, [r14+r14]
0x18000afb0  cmp     r8, 2
0x18000afb4  jbe     loc_18000AD9A
0x18000afba  add     r8, 0FFFFFFFFFFFFFFFEh; Size
0x18000afbe  inc     r9
0x18000afc1  lea     rcx, [r10+r9*2]; void *
0x18000afc5  xor     edx, edx; Val
0x18000afc7  call    memset_0
0x18000afcc  xor     r11d, r11d
0x18000afcf  jmp     loc_18000AD9A
0x18000afd4  mov     [rsp+88h+var_68], r14
0x18000afd9  mov     rcx, [rbx+10h]
0x18000afdd  mov     rax, [rcx]
0x18000afe0  lea     rdx, [rsp+88h+var_68]
0x18000afe5  mov     rax, [rax+40h]
0x18000afe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000afee  mov     ebp, eax
0x18000aff0  test    eax, eax
0x18000aff2  js      short loc_18000B053
0x18000aff4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000affb  mov     ecx, 20h ; ' '; unsigned __int64
0x18000b000  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000b005  mov     rdi, rax
0x18000b008  mov     [rsp+88h+var_50], rax
0x18000b00d  test    rax, rax
0x18000b010  jz      loc_18000B100
0x18000b016  mov     rcx, [rsp+88h+var_68]
0x18000b01b  movups  xmm0, xmmword ptr [rbx]
0x18000b01e  movups  xmmword ptr [rax], xmm0
0x18000b021  mov     [rax+10h], rcx
0x18000b025  mov     [rax+18h], r14
0x18000b029  mov     rdx, [rcx]
0x18000b02c  mov     rax, [rdx+8]
0x18000b030  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b035  nop
0x18000b036  test    rdi, rdi
0x18000b039  jz      short loc_18000B0A9
0x18000b03b  mov     [rsi], rdi
0x18000b03e  lea     rsi, [rdi+18h]
0x18000b042  mov     rcx, [rsp+88h+var_68]
0x18000b047  mov     rax, [rcx]
0x18000b04a  mov     rax, [rax+10h]
0x18000b04e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b053  mov     rbx, [rbx+18h]
0x18000b057  test    ebp, ebp
0x18000b059  jns     loc_18000AF5D
  ... truncated ...
```
