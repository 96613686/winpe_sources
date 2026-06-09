# StructuredQuery1::Solution::MakePredicate(_tagpropertykey const &,tagCONDITION_OPERATION,wchar_t const *,tagPROPVARIANT const &,wchar_t const *,StructuredQuery1::LANGUAGE_OVERRIDE_CHECK,IRichChunk *,IRichChunk *,IRichChunk *,bool,bool,_GUID const &,void * *)

- ea: `0x180009a40`
- end: `0x18000a32e`
- name: `?MakePredicate@Solution@StructuredQuery1@@QEAAJAEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEB_WAEBUtagPROPVARIANT@@2W4LANGUAGE_OVERRIDE_CHECK@2@PEAUIRichChunk@@55_N6AEBU_GUID@@PEAPEAX@Z`
- size: `2286`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `19`
- callee_count: `16`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x180006790`
- `0x18000888c`
- `0x180008a50`
- `0x180008eb0`
- `0x1800090c0`
- `0x180009640`
- `0x180009860`
- `0x18000e4ec`
- `0x18000ef3c`
- `0x18000f7cc`
- `0x180033078`
- `0x18005a874`
- `0x18005c79c`
- `0x18006dc70`
- `0x18006e220`
- `0x18006e2f0`
- `0x18006ec10`
- `0x18006efc0`
- `0x18006f300`

## callees

- `0x180009340`
- `0x1800094d4`
- `0x180009770`
- `0x1800097ac`
- `0x180009a40`
- `0x18000a340`
- `0x18000abd0`
- `0x18000b130`
- `0x18001b2b4`
- `0x18003716c`
- `0x18005a874`
- `0x18005daf0`
- `0x18005db64`
- `0x18005e740`
- `0x18006e830`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180009bfd`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionEx` at `0x180009bfd`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a26f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000a26f`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18000a24d`
- `api-ms-win-core-localization-l1-2-2!LCIDToLocaleName` at `0x18000a24d`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180009c25`
- `api-ms-win-core-com-l1-1-0!PropVariantCopy` at `0x180009c25`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f9e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009db0`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009c74`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009db0`
- `PROPSYS!PropVariantToStringAlloc` at `0x180009f70`
- `PROPSYS!PropVariantToStringAlloc` at `0x180009f70`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StructuredQuery1::Solution::MakePredicate(
        __int64 a1,
        const struct _tagpropertykey *a2,
        enum tagCONDITION_OPERATION a3,
        const wchar_t *a4,
        PROPVARIANT *pvarSrc,
        wchar_t *a6,
        int a7,
        struct IRichChunk *a8,
        struct IRichChunk *a9,
        struct IRichChunk *a10,
        char a11,
        bool a12,
        struct _GUID *a13,
        void **a14)
{
  const wchar_t *v14; // rdi
  struct tagPROPVARIANT *v18; // r12
  WCHAR *v19; // r14
  struct IRichChunk *v20; // rdx
  struct IRichChunk *v21; // rcx
  struct _GUID *v22; // r8
  __int64 v23; // r10
  unsigned int v24; // eax
  __int64 v25; // r15
  unsigned int v26; // esi
  __int64 v27; // r8
  unsigned __int64 v28; // rsi
  WCHAR *v29; // rax
  PWSTR v30; // r15
  PWSTR v31; // r13
  HRESULT Instance; // r12d
  unsigned __int64 v33; // rbx
  unsigned __int64 v34; // r15
  wchar_t *v35; // r10
  unsigned __int64 v36; // rcx
  wchar_t *v37; // rdx
  __int64 v38; // r8
  wchar_t v39; // ax
  __int64 v40; // r9
  wchar_t *v41; // rax
  unsigned __int64 v43; // rbx
  _WORD *v44; // rax
  _WORD *v45; // r10
  unsigned __int64 v46; // rcx
  WCHAR *v47; // rdx
  __int64 v48; // r8
  WCHAR v49; // ax
  __int64 v50; // r9
  WCHAR *v51; // rax
  __int64 v52; // rcx
  __int16 v53; // ax
  unsigned int v54; // edx
  __int64 v55; // rax
  StructuredQuery1::Solution *v56; // rcx
  unsigned int v57; // r9d
  unsigned int v58; // esi
  struct tagPROPVARIANT *v59; // r14
  __int64 v60; // r15
  bool v61; // cf
  __int64 v62; // rbx
  const wchar_t *v63; // r12
  unsigned int v64; // eax
  int i; // ebx
  char v66[8]; // [rsp+70h] [rbp-90h] BYREF
  PWSTR ppszOut; // [rsp+78h] [rbp-88h] BYREF
  void *v68; // [rsp+80h] [rbp-80h] BYREF
  struct IRichChunk *v69; // [rsp+88h] [rbp-78h]
  struct IRichChunk *v70; // [rsp+90h] [rbp-70h]
  struct tagPROPVARIANT *v71; // [rsp+98h] [rbp-68h]
  unsigned int v72; // [rsp+A0h] [rbp-60h] BYREF
  int v73; // [rsp+A4h] [rbp-5Ch] BYREF
  struct _GUID *v74; // [rsp+A8h] [rbp-58h]
  int v75; // [rsp+B0h] [rbp-50h] BYREF
  struct IRichChunk *v76; // [rsp+B8h] [rbp-48h]
  void **v77; // [rsp+C0h] [rbp-40h]
  struct ICondition2 *v78[2]; // [rsp+C8h] [rbp-38h] BYREF
  __int64 v79; // [rsp+D8h] [rbp-28h]
  WCHAR Name[88]; // [rsp+E0h] [rbp-20h] BYREF

  v14 = a4;
  v18 = (struct tagPROPVARIANT *)pvarSrc;
  v71 = (struct tagPROPVARIANT *)pvarSrc;
  v19 = a6;
  v76 = a8;
  v20 = a9;
  v69 = a9;
  v21 = a10;
  v70 = a10;
  v22 = a13;
  v74 = a13;
  v77 = a14;
  if ( (unsigned int)a3 <= COP_APPLICATION_SPECIFIC )
  {
    v23 = *(_QWORD *)(a1 + 32);
    if ( v23 )
    {
      v24 = 0;
      v25 = 0;
      v26 = 0;
      while ( v24 < *(_DWORD *)(v23 + 44) )
      {
        v27 = *(_QWORD *)(v23 + 32) + 40LL * v24;
        if ( a2->pid == *(_DWORD *)(v27 + 16) )
        {
          v52 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)v27;
          if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)v27 )
            v52 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)(v27 + 8);
          if ( !v52 )
          {
            v25 = *(_QWORD *)(v27 + 24);
            v26 = *(_DWORD *)(v27 + 32);
            break;
          }
        }
        ++v24;
      }
      v21 = v70;
      v20 = v69;
      v22 = v74;
    }
    else
    {
      v25 = 0;
      v26 = 0;
    }
    v68 = 0;
    if ( a11 && v26 )
    {
      Instance = StructuredQuery1::Solution::ExpandPredicate(
                   a1,
                   v25,
                   v26,
                   (unsigned int)a3,
                   a4,
                   pvarSrc,
                   a6,
                   a7,
                   v20,
                   v21,
                   a11,
                   a12,
                   v22,
                   &v68);
      goto LABEL_37;
    }
    v66[0] = 0;
    if ( a12 && (unsigned int)StructuredQuery1::Trivial((unsigned int)a3, pvarSrc, v66) )
    {
      Instance = StructuredQuery1::CompoundCondition::CreateInstance(
                   (enum tagCONDITION_TYPE)(v66[0] == 0),
                   0,
                   0,
                   v74,
                   &v68);
      goto LABEL_37;
    }
    v73 = 0;
    v28 = -1;
    if ( a7 == 1 )
    {
      v53 = *(_WORD *)pvarSrc & 0xFFF;
      if ( v53 == 8 || (unsigned __int16)(v53 - 30) <= 1u )
      {
        ppszOut = 0;
        if ( PropVariantToStringAlloc(pvarSrc, &ppszOut) >= 0 )
        {
          v55 = -1;
          do
            ++v55;
          while ( ppszOut[v55] );
          if ( v55 )
          {
            v63 = ppszOut;
            v64 = _LocaleNameToLCIDNoCustomLocales(a6, v54);
            if ( v64 )
            {
              v72 = 0;
              v75 = 0;
              if ( (int)CScriptAutoDetection::GetNonSpacedOverrideLocaleScripts(
                          (CScriptAutoDetection *)g_scriptAutoDetection,
                          v63,
                          v64,
                          &v72,
                          (enum AMBIGUOUS_CJK_TEXT *)&v73,
                          (enum SPECIAL_SCRIPTS_FOUND_FLAGS *)&v75) >= 0
                && (LCIDToLocaleName((unsigned __int16)v72, Name, 85, 0) > 0 || (GetLastError() & 0x80000000) == 0) )
              {
                v19 = Name;
              }
            }
            v18 = v71;
          }
          CoTaskMemFree(ppszOut);
          if ( v73 == 3 )
          {
            *(_OWORD *)v78 = 0;
            v79 = 0;
            v58 = 0;
            v59 = v71;
            while ( v58 < 3 )
            {
              Instance = StructuredQuery1::LeafCondition::CreateInstance(
                           a2,
                           a3,
                           v14,
                           v59,
                           (const wchar_t *)(&StructuredQuery1::g_rgpszAmbiguousHanCaseLocaleNames)[v58],
                           v76,
                           v69,
                           v70,
                           0,
                           v74,
                           (void **)&v78[v58]);
              ++v58;
              if ( Instance < 0 )
                goto LABEL_37;
            }
            Instance = StructuredQuery1::Solution::MakeCompound(v56, CT_AND_CONDITION, v78, v57, a12, v74, &v68);
            if ( Instance >= 0 )
            {
              for ( i = 0; (unsigned __int64)i < 3; ++i )
                IUnknown_SafeReleaseAndNullPtr<GrowableBuffer<tagHITRANGE>>(&v78[i]);
            }
            goto LABEL_37;
          }
        }
      }
    }
    v68 = 0;
    v29 = (WCHAR *)operator new(0xB0u, (const struct std::nothrow_t *)&std::nothrow);
    v30 = v29;
    ppszOut = v29;
    if ( !v29 )
    {
      Instance = -2147024882;
      goto LABEL_37;
    }
    StructuredQuery1::BaseCondition::BaseCondition((StructuredQuery1::BaseCondition *)v29);
    *(_QWORD *)v30 = &StructuredQuery1::LeafCondition::`vftable'{for `ICondition2'};
    *((_QWORD *)v30 + 1) = &StructuredQuery1::NegationCondition::`vftable'{for `IConditionAttributeContainer'};
    *((_QWORD *)v30 + 2) = &StructuredQuery1::LeafCondition::`vftable'{for `IPersistXML'};
    *(PROPERTYKEY *)(v30 + 24) = PKEY_Null;
    *((_DWORD *)v30 + 17) = a3;
    *((_QWORD *)v30 + 12) = 0;
    *((_QWORD *)v30 + 13) = 0;
    v31 = v30 + 56;
    *((_QWORD *)v30 + 14) = 0;
    *((_QWORD *)v30 + 15) = 0;
    *((_QWORD *)v30 + 16) = 0;
    InitializeCriticalSectionEx((LPCRITICAL_SECTION)(v30 + 68), 0, 0);
    *(_OWORD *)(v30 + 36) = 0;
    *((_QWORD *)v30 + 11) = 0;
    *((_OWORD *)v30 + 3) = a2->fmtid;
    *((_DWORD *)v30 + 16) = a2->pid;
    Instance = PropVariantCopy((PROPVARIANT *)v30 + 9, (const PROPVARIANT *)v18);
    if ( Instance >= 0 )
    {
      if ( v14 )
      {
        v33 = -1;
        do
          ++v33;
        while ( v14[v33] );
        *((_QWORD *)v30 + 12) = 0;
        v34 = v33 + 1;
        if ( v33 + 1 >= v33 && is_mul_ok(v34, 2u) )
        {
          v35 = (wchar_t *)CoTaskMemAlloc(2 * v34);
          *((_QWORD *)ppszOut + 12) = v35;
          Instance = -2147024882;
          if ( v35 )
            Instance = 0;
          if ( Instance < 0 )
            goto LABEL_35;
          if ( (v35 || v33 == -1) && v34 <= 0x7FFFFFFF )
          {
            if ( v33 >= 0x7FFFFFFF )
            {
              if ( v33 != -1 )
                *v35 = 0;
            }
            else
            {
              v36 = v33 + 1;
              v37 = v35;
              v38 = 0;
              do
              {
                if ( !v33 )
                  break;
                v39 = *v14;
                if ( !*v14 )
                  break;
                ++v14;
                *v37++ = v39;
                --v33;
                ++v38;
                --v36;
              }
              while ( v36 );
              v40 = v38 - 1;
              if ( v36 )
                v40 = v38;
              v41 = v37 - 1;
              if ( v36 )
                v41 = v37;
              *v41 = 0;
              if ( v36 )
              {
                v61 = v34 == v40;
                v60 = v34 - v40;
                if ( !v61 && v60 != 1 && (unsigned __int64)(2 * v60) > 2 )
                  memset_0(&v35[v40 + 1], 0, 2 * v60 - 2);
              }
            }
          }
          else
          {
            *v35 = 0;
          }
        }
        else
        {
          Instance = -2147024362;
        }
        if ( Instance < 0 )
        {
LABEL_35:
          v30 = ppszOut;
          goto LABEL_36;
        }
        v30 = ppszOut;
      }
      if ( !v19 )
        goto LABEL_119;
      do
        ++v28;
      while ( v19[v28] );
      *((_QWORD *)v30 + 13) = 0;
      v43 = v28 + 1;
      if ( v28 + 1 >= v28 && is_mul_ok(v43, 2u) )
      {
        v44 = CoTaskMemAlloc(2 * v43);
        v45 = v44;
        *((_QWORD *)v30 + 13) = v44;
        Instance = -2147024882;
        if ( v44 )
          Instance = 0;
        if ( Instance < 0 )
          goto LABEL_36;
        if ( (v44 || v28 == -1) && v43 <= 0x7FFFFFFF )
        {
          if ( v28 >= 0x7FFFFFFF )
          {
            if ( v28 != -1 )
              *v44 = 0;
          }
          else
          {
            v46 = v28 + 1;
            v47 = v44;
            v48 = 0;
            do
            {
              if ( !v28 )
                break;
              v49 = *v19;
              if ( !*v19 )
                break;
              ++v19;
              *v47++ = v49;
              --v28;
              ++v48;
              --v46;
            }
            while ( v46 );
            v50 = v48 - 1;
            if ( v46 )
              v50 = v48;
            v51 = v47 - 1;
            if ( v46 )
              v51 = v47;
            *v51 = 0;
            if ( v46 )
            {
              v61 = v43 == v50;
              v62 = v43 - v50;
              if ( !v61 && v62 != 1 && (unsigned __int64)(2 * v62) > 2 )
                memset_0(&v45[v50 + 1], 0, 2 * v62 - 2);
            }
          }
        }
        else
        {
          *v44 = 0;
        }
      }
      else
      {
        Instance = -2147024362;
      }
      if ( Instance >= 0 )
      {
LABEL_119:
        if ( !v76
          || (Instance = ((__int64 (__fastcall *)(struct IRichChunk *, GUID *, PWSTR))v76->lpVtbl->QueryInterface)(
                           v76,
                           &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510,
                           v31),
              Instance >= 0) )
        {
          if ( !v69
            || (Instance = ((__int64 (__fastcall *)(struct IRichChunk *, GUID *, PWSTR))v69->lpVtbl->QueryInterface)(
                             v69,
                             &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510,
                             v30 + 60),
                Instance >= 0) )
          {
            if ( !v70
              || (Instance = ((__int64 (__fastcall *)(struct IRichChunk *, GUID *, PWSTR))v70->lpVtbl->QueryInterface)(
                               v70,
                               &GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510,
                               v30 + 64),
                  Instance >= 0) )
            {
              v69 = 0;
              *((_QWORD *)v30 + 5) = 0;
              Instance = (**(__int64 (__fastcall ***)(PWSTR, struct _GUID *, void **))v30)(v30, v74, &v68);
            }
          }
        }
      }
    }
LABEL_36:
    (*(void (__fastcall **)(PWSTR))(*(_QWORD *)v30 + 16LL))(v30);
LABEL_37:
    *v77 = v68;
    return (unsigned int)Instance;
  }
  *a14 = 0;
  return 2147942487LL;
}

```

## disassembly

```asm
0x180009a40  mov     [rsp-8+arg_8], rbx
0x180009a45  push    rbp
0x180009a46  push    rsi
0x180009a47  push    rdi
0x180009a48  push    r12
0x180009a4a  push    r13
0x180009a4c  push    r14
0x180009a4e  push    r15
0x180009a50  lea     rbp, [rsp-0A0h]
0x180009a58  sub     rsp, 1A0h
0x180009a5f  mov     rax, cs:__security_cookie
0x180009a66  xor     rax, rsp
0x180009a69  mov     [rbp+0D0h+var_40], rax
0x180009a70  mov     rdi, r9
0x180009a73  mov     r13d, r8d
0x180009a76  mov     rbx, rdx
0x180009a79  mov     r11, rcx
0x180009a7c  mov     r12, [rbp+0D0h+pvarSrc]
0x180009a83  mov     [rbp+0D0h+var_138], r12
0x180009a87  mov     r14, [rbp+0D0h+arg_28]
0x180009a8e  mov     rax, [rbp+0D0h+arg_38]
0x180009a95  mov     [rbp+0D0h+var_118], rax
0x180009a99  mov     rdx, [rbp+0D0h+arg_40]
0x180009aa0  mov     [rbp+0D0h+var_148], rdx
0x180009aa4  mov     rcx, [rbp+0D0h+arg_48]
0x180009aab  mov     [rbp+0D0h+var_140], rcx
0x180009aaf  mov     r8, [rbp+0D0h+arg_60]
0x180009ab6  mov     [rbp+0D0h+var_128], r8
0x180009aba  mov     rax, [rbp+0D0h+arg_68]
0x180009ac1  mov     [rbp+0D0h+var_110], rax
0x180009ac5  cmp     r13d, 0Eh
0x180009ac9  ja      loc_18000A152
0x180009acf  mov     r10, [r11+20h]
0x180009ad3  test    r10, r10
0x180009ad6  jz      loc_18000A264
0x180009adc  xor     eax, eax
0x180009ade  mov     r15d, eax
0x180009ae1  mov     esi, eax
0x180009ae3  mov     r9d, [r10+2Ch]
0x180009ae7  cmp     eax, r9d
0x180009aea  jnb     short loc_180009B13
0x180009aec  mov     ecx, eax
0x180009aee  lea     rdx, [rcx+rcx*4]
0x180009af2  mov     rcx, [r10+20h]
0x180009af6  lea     r8, [rcx+rdx*8]
0x180009afa  mov     ecx, [r8+10h]
0x180009afe  cmp     [rbx+10h], ecx
0x180009b01  jz      loc_180009F22
0x180009b07  inc     eax
0x180009b09  jmp     short loc_180009AE7
0x180009b0b  mov     r15, [r8+18h]
0x180009b0f  mov     esi, [r8+20h]
0x180009b13  xor     r10d, r10d
0x180009b16  mov     rcx, [rbp+0D0h+var_140]
0x180009b1a  mov     rdx, [rbp+0D0h+var_148]
0x180009b1e  mov     r8, [rbp+0D0h+var_128]
0x180009b22  mov     [rbp+0D0h+var_150], r10
0x180009b26  movzx   r10d, [rbp+0D0h+arg_50]
0x180009b2e  test    r10b, r10b
0x180009b31  jnz     loc_18000A195
0x180009b37  mov     [rsp+1D0h+var_160], 0
0x180009b3c  movzx   r15d, [rbp+0D0h+arg_58]
0x180009b44  test    r15b, r15b
0x180009b47  jnz     loc_18000A07B
0x180009b4d  mov     [rbp+0D0h+var_12C], 0
0x180009b54  mov     rsi, 0FFFFFFFFFFFFFFFFh
0x180009b5b  cmp     [rbp+0D0h+arg_30], 1
0x180009b62  jz      loc_180009F4B
0x180009b68  mov     [rbp+0D0h+var_150], 0
0x180009b70  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180009b77  mov     ecx, 0B0h; unsigned __int64
0x180009b7c  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180009b81  mov     r15, rax
0x180009b84  mov     [rsp+1D0h+ppszOut], rax
0x180009b89  test    rax, rax
0x180009b8c  jz      loc_18000A323
0x180009b92  mov     rcx, rax; this
0x180009b95  call    ??0BaseCondition@StructuredQuery1@@IEAA@XZ; StructuredQuery1::BaseCondition::BaseCondition(void)
0x180009b9a  lea     rcx, ??_7LeafCondition@StructuredQuery1@@6BICondition2@@@; const StructuredQuery1::LeafCondition::`vftable'{for `ICondition2'}
0x180009ba1  mov     [r15], rcx
0x180009ba4  lea     rax, ??_7NegationCondition@StructuredQuery1@@6BIConditionAttributeContainer@@@; const StructuredQuery1::NegationCondition::`vftable'{for `IConditionAttributeContainer'}
0x180009bab  mov     [r15+8], rax
0x180009baf  lea     rax, ??_7LeafCondition@StructuredQuery1@@6BIPersistXML@@@; const StructuredQuery1::LeafCondition::`vftable'{for `IPersistXML'}
0x180009bb6  mov     [r15+10h], rax
0x180009bba  movups  xmm0, xmmword ptr cs:PKEY_Null.fmtid.Data1
0x180009bc1  movups  xmmword ptr [r15+30h], xmm0
0x180009bc6  mov     eax, cs:PKEY_Null.pid
0x180009bcc  mov     [r15+40h], eax
0x180009bd0  mov     [r15+44h], r13d
0x180009bd4  xor     eax, eax
0x180009bd6  mov     [r15+60h], rax
0x180009bda  mov     [r15+68h], rax
0x180009bde  lea     r13, [r15+70h]
0x180009be2  mov     [r13+0], rax
0x180009be6  mov     [r15+78h], rax
0x180009bea  mov     [r15+80h], rax
0x180009bf1  lea     rcx, [r15+88h]; lpCriticalSection
0x180009bf8  xor     r8d, r8d; Flags
0x180009bfb  xor     edx, edx; dwSpinCount
0x180009bfd  call    cs:__imp_InitializeCriticalSectionEx
0x180009c03  lea     rcx, [r15+48h]; pvarDest
0x180009c07  xorps   xmm0, xmm0
0x180009c0a  xor     eax, eax
0x180009c0c  movups  xmmword ptr [rcx], xmm0
0x180009c0f  mov     [rcx+10h], rax
0x180009c13  movups  xmm0, xmmword ptr [rbx]
0x180009c16  movups  xmmword ptr [r15+30h], xmm0
0x180009c1b  mov     eax, [rbx+10h]
0x180009c1e  mov     [r15+40h], eax
0x180009c22  mov     rdx, r12; pvarSrc
0x180009c25  call    cs:__imp_PropVariantCopy
0x180009c2b  mov     r12d, eax
0x180009c2e  test    eax, eax
0x180009c30  js      loc_180009D1B
0x180009c36  test    rdi, rdi
0x180009c39  jz      loc_18000A2EF
0x180009c3f  mov     rbx, rsi
0x180009c42  inc     rbx
0x180009c45  cmp     word ptr [rdi+rbx*2], 0
0x180009c4a  jnz     short loc_180009C42
0x180009c4c  xor     r11d, r11d
0x180009c4f  mov     [r15+60h], r11
0x180009c53  lea     r15, [rbx+1]
0x180009c57  cmp     r15, rbx
0x180009c5a  jb      loc_180009D6A
0x180009c60  mov     eax, 2
0x180009c65  mul     r15
0x180009c68  test    rdx, rdx
0x180009c6b  jnz     loc_180009D6A
0x180009c71  mov     rcx, rax; cb
0x180009c74  call    cs:__imp_CoTaskMemAlloc
0x180009c7a  mov     r10, rax
0x180009c7d  mov     rax, [rsp+1D0h+ppszOut]
0x180009c82  mov     [rax+60h], r10
0x180009c86  mov     r12d, 8007000Eh
0x180009c8c  test    r10, r10
0x180009c8f  mov     r11d, 0
0x180009c95  cmovnz  r12d, r11d
0x180009c99  test    r12d, r12d
0x180009c9c  js      short loc_180009D16
0x180009c9e  test    r10, r10
0x180009ca1  jz      loc_18000A2CB
0x180009ca7  cmp     r15, 7FFFFFFFh
0x180009cae  ja      loc_18000A2D4
0x180009cb4  cmp     rbx, 7FFFFFFFh
0x180009cbb  jnb     loc_18000A2DD
0x180009cc1  test    r15, r15
0x180009cc4  jz      short loc_180009D11
0x180009cc6  mov     rcx, r15
0x180009cc9  mov     rdx, r10
0x180009ccc  mov     r8, r11
0x180009ccf  nop
0x180009cd0  test    rbx, rbx
0x180009cd3  jz      short loc_180009CF4
0x180009cd5  movzx   eax, word ptr [rdi]
0x180009cd8  test    ax, ax
0x180009cdb  jz      short loc_180009CF4
0x180009cdd  add     rdi, 2
0x180009ce1  mov     [rdx], ax
0x180009ce4  add     rdx, 2
0x180009ce8  dec     rbx
0x180009ceb  inc     r8
0x180009cee  sub     rcx, 1
0x180009cf2  jnz     short loc_180009CD0
0x180009cf4  lea     r9, [r8-1]
0x180009cf8  test    rcx, rcx
0x180009cfb  cmovnz  r9, r8
0x180009cff  lea     rax, [rdx-2]
0x180009d03  cmovnz  rax, rdx
0x180009d07  mov     [rax], r11w
0x180009d0b  jnz     loc_18000A046
0x180009d11  test    r12d, r12d
0x180009d14  jns     short loc_180009D72
0x180009d16  mov     r15, [rsp+1D0h+ppszOut]
0x180009d1b  mov     rax, [r15]
0x180009d1e  mov     rcx, r15
0x180009d21  mov     rax, [rax+10h]
0x180009d25  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d2a  mov     rcx, [rbp+0D0h+var_150]
0x180009d2e  mov     [rbp+0D0h+var_150], rcx
0x180009d32  mov     rcx, [rbp+0D0h+var_150]
0x180009d36  mov     rax, [rbp+0D0h+var_110]
0x180009d3a  mov     [rax], rcx
0x180009d3d  mov     eax, r12d
0x180009d40  mov     rcx, [rbp+0D0h+var_40]
0x180009d47  xor     rcx, rsp; StackCookie
0x180009d4a  call    __security_check_cookie
0x180009d4f  mov     rbx, [rsp+1D0h+arg_8]
0x180009d57  add     rsp, 1A0h
0x180009d5e  pop     r15
0x180009d60  pop     r14
0x180009d62  pop     r13
0x180009d64  pop     r12
0x180009d66  pop     rdi
0x180009d67  pop     rsi
0x180009d68  pop     rbp
0x180009d69  retn
0x180009d6a  mov     r12d, 80070216h
0x180009d70  jmp     short loc_180009D11
0x180009d72  mov     r15, [rsp+1D0h+ppszOut]
0x180009d77  test    r14, r14
0x180009d7a  jz      loc_180009E5B
0x180009d80  inc     rsi
0x180009d83  cmp     word ptr [r14+rsi*2], 0
0x180009d89  jnz     short loc_180009D80
0x180009d8b  mov     [r15+68h], r11
0x180009d8f  lea     rbx, [rsi+1]
0x180009d93  cmp     rbx, rsi
0x180009d96  jb      loc_180009F40
0x180009d9c  mov     eax, 2
0x180009da1  mul     rbx
0x180009da4  test    rdx, rdx
0x180009da7  jnz     loc_180009F40
0x180009dad  mov     rcx, rax; cb
0x180009db0  call    cs:__imp_CoTaskMemAlloc
0x180009db6  mov     r10, rax
0x180009db9  mov     [r15+68h], rax
0x180009dbd  mov     r12d, 8007000Eh
0x180009dc3  test    rax, rax
0x180009dc6  mov     r11d, 0
0x180009dcc  cmovnz  r12d, r11d
0x180009dd0  test    r12d, r12d
0x180009dd3  js      loc_180009D1B
0x180009dd9  test    rax, rax
0x180009ddc  jz      loc_18000A2F7
0x180009de2  cmp     rbx, 7FFFFFFFh
0x180009de9  ja      loc_18000A300
0x180009def  cmp     rsi, 7FFFFFFFh
0x180009df6  jnb     loc_18000A309
0x180009dfc  test    rbx, rbx
0x180009dff  jz      short loc_180009E52
0x180009e01  mov     rcx, rbx
0x180009e04  mov     rdx, r10
0x180009e07  mov     r8, r11
0x180009e0a  nop     word ptr [rax+rax+00h]
0x180009e10  test    rsi, rsi
0x180009e13  jz      short loc_180009E35
0x180009e15  movzx   eax, word ptr [r14]
0x180009e19  test    ax, ax
0x180009e1c  jz      short loc_180009E35
0x180009e1e  add     r14, 2
0x180009e22  mov     [rdx], ax
0x180009e25  add     rdx, 2
0x180009e29  dec     rsi
0x180009e2c  inc     r8
0x180009e2f  sub     rcx, 1
0x180009e33  jnz     short loc_180009E10
0x180009e35  lea     r9, [r8-1]
0x180009e39  test    rcx, rcx
0x180009e3c  cmovnz  r9, r8
0x180009e40  lea     rax, [rdx-2]
0x180009e44  cmovnz  rax, rdx
0x180009e48  mov     [rax], r11w
0x180009e4c  jnz     loc_18000A163
0x180009e52  test    r12d, r12d
0x180009e55  js      loc_180009D1B
0x180009e5b  mov     rcx, [rbp+0D0h+var_118]
0x180009e5f  test    rcx, rcx
0x180009e62  jz      short loc_180009E84
0x180009e64  mov     rax, [rcx]
0x180009e67  mov     r8, r13
0x180009e6a  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x180009e71  mov     rax, [rax]
0x180009e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e79  mov     r12d, eax
0x180009e7c  test    eax, eax
0x180009e7e  js      loc_180009D1B
0x180009e84  mov     rcx, [rbp+0D0h+var_148]
0x180009e88  test    rcx, rcx
0x180009e8b  jz      short loc_180009EAE
0x180009e8d  mov     rax, [rcx]
0x180009e90  lea     r8, [r15+78h]
0x180009e94  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x180009e9b  mov     rax, [rax]
0x180009e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ea3  mov     r12d, eax
0x180009ea6  test    eax, eax
0x180009ea8  js      loc_180009D1B
0x180009eae  mov     rcx, [rbp+0D0h+var_140]
0x180009eb2  test    rcx, rcx
0x180009eb5  jz      short loc_180009EDB
0x180009eb7  mov     rax, [rcx]
0x180009eba  lea     r8, [r15+80h]
0x180009ec1  lea     rdx, _GUID_4fdef69c_dbc9_454e_9910_b34f3c64b510
0x180009ec8  mov     rax, [rax]
0x180009ecb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ed0  mov     r12d, eax
0x180009ed3  test    eax, eax
0x180009ed5  js      loc_180009D1B
0x180009edb  xor     esi, esi
0x180009edd  mov     ebx, esi
0x180009edf  mov     r12d, esi
0x180009ee2  mov     [rbp+0D0h+var_148], rsi
0x180009ee6  lea     rdi, [rbp+0D0h+var_148]
0x180009eea  test    rbx, rbx
0x180009eed  jnz     loc_18000A0C1
0x180009ef3  mov     rax, [rbp+0D0h+var_148]
0x180009ef7  mov     [r15+28h], rax
0x180009efb  test    r12d, r12d
0x180009efe  js      loc_180009D1B
  ... truncated ...
```
