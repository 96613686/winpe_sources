# CGrepConditionEvaluator::v_DoesItemMatchLeafCondition(tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,ICondition *,int,TRIBIT *,int *)

- ea: `0x18004b8d0`
- end: `0x18004bc82`
- name: `?v_DoesItemMatchLeafCondition@CGrepConditionEvaluator@@MEAAJAEBUtagPROPVARIANT@@AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEAUICondition@@HPEAW4TRIBIT@@PEAH@Z`
- size: `946`
- prototype: `__int64 __usercall@<rax>(CGrepConditionEvaluator *__hidden this@<rcx>, PROPVARIANT *propvarIn@<rdx>, const struct _tagpropertykey *@<r8>, enum tagCONDITION_OPERATION@<r9d>, struct ICondition *, int, enum TRIBIT *, int *)`
- caller_count: `0`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callees

- `0x180043ff4`
- `0x180044210`
- `0x1800444d8`
- `0x180044b50`
- `0x1800475b8`
- `0x18004b4c0`
- `0x18004b8d0`
- `0x18004bdc8`
- `0x180076c50`
- `0x18007b010`

## import_xrefs

- `PROPSYS!PropVariantToUInt32` at `0x18004ba68`
- `PROPSYS!PropVariantToUInt32` at `0x18004ba68`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x18004bab1`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x18004bae5`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x18004bab1`
- `COMCTL32!__imp_DSA_GetItemPtr` at `0x18004bae5`
- `COMCTL32!__imp_DSA_InsertItem` at `0x18004bb21`
- `COMCTL32!__imp_DSA_InsertItem` at `0x18004bb21`

## pseudocode

```c
__int64 __fastcall CGrepConditionEvaluator::v_DoesItemMatchLeafCondition(
        CGrepConditionEvaluator *this,
        PROPVARIANT *propvarIn,
        const struct _tagpropertykey *a3,
        enum tagCONDITION_OPERATION a4,
        struct ICondition *a5,
        unsigned int a6,
        enum TRIBIT *a7,
        int *a8)
{
  const PROPVARIANT *v8; // r13
  int appended; // ebx
  __int64 v12; // rcx
  enum tagCONDITION_OPERATION v13; // r9d
  int v14; // r14d
  __int64 v15; // rcx
  __int64 v16; // rcx
  __int64 v17; // rcx
  HDSA *v18; // r13
  HDSA v19; // rax
  int i; // r14d
  const struct CONDITIONBITSSETCACHE *ItemPtr; // rax
  int v22; // ecx
  __int64 v23; // rcx
  int v24; // r9d
  ULONG pulRet; // [rsp+40h] [rbp-49h] BYREF
  int v27; // [rsp+44h] [rbp-45h] BYREF
  struct tagPROPVARIANT *v28; // [rsp+48h] [rbp-41h]
  enum tagCONDITION_OPERATION v29; // [rsp+50h] [rbp-39h]
  int *v30; // [rsp+58h] [rbp-31h]
  __int16 v31; // [rsp+60h] [rbp-29h] BYREF
  int v32; // [rsp+68h] [rbp-21h]
  struct ICondition *pitem; // [rsp+78h] [rbp-11h] BYREF
  __int64 v34; // [rsp+80h] [rbp-9h] BYREF

  v8 = propvarIn;
  v28 = (struct tagPROPVARIANT *)propvarIn;
  v30 = a8;
  v29 = a4;
  appended = 0;
  v14 = 1;
  if ( ((unsigned int)operator==(a3, PKEY_Generic_String)
     || *((_QWORD *)this + 5)
     && ((unsigned int)operator==(v12, &PKEY_FullText)
      || (unsigned int)operator==(v15, PKEY_ForceFullText)
      || (unsigned int)operator==(v16, &PKEY_Search_Contents)))
    && !*((_DWORD *)this + 17) )
  {
    if ( *((_DWORD *)this + 48)
      || ((unsigned int)operator==(a3, PKEY_ForceFullText) || (unsigned int)operator==(v17, &PKEY_Search_Contents))
      && *((_DWORD *)this + 49) )
    {
      *((_DWORD *)this + 15) = 1;
      appended = CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::AppendPtr((char *)this + 88, a5);
      if ( appended < 0 )
      {
LABEL_15:
        *(_DWORD *)a7 = 0;
        SetEvalStateEx(a5, (__int64)L"ES", 0);
        v13 = v29;
        goto LABEL_16;
      }
      ((void (__fastcall *)(struct ICondition *))a5->lpVtbl->AddRef)(a5);
    }
    appended = CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::AppendPtr((char *)this + 80, a5);
    if ( appended >= 0 )
    {
      ((void (__fastcall *)(struct ICondition *))a5->lpVtbl->AddRef)(a5);
      appended = SetEvalStateEx(a5, (__int64)L"Negate", 2 - (unsigned int)(a6 != 0));
    }
    goto LABEL_15;
  }
LABEL_16:
  if ( *((_QWORD *)this + 5) )
  {
    if ( v13 == COP_APPLICATION_SPECIFIC )
    {
      if ( (unsigned int)operator==(a3, &PKEY_SFGAOFlags) )
      {
        pulRet = 0;
        appended = PropVariantToUInt32(v8, &pulRet);
        if ( appended >= 0 )
        {
          v18 = (HDSA *)*((_QWORD *)this + 26);
          if ( v18 )
          {
            v34 = 0;
            pitem = a5;
            v19 = *v18;
            if ( *v18 )
              LODWORD(v19) = *(_DWORD *)v19;
            v27 = (int)v19;
            for ( i = 0; i < (int)v19; ++i )
            {
              ItemPtr = (const struct CONDITIONBITSSETCACHE *)DSA_GetItemPtr(*v18, i);
              if ( !(unsigned int)DSACompareBitsCache((const struct CONDITIONBITSSETCACHE *)&pitem, ItemPtr, 0) )
              {
                if ( i != -1 )
                {
                  v22 = *((_DWORD *)DSA_GetItemPtr(**((HDSA **)this + 26), i) + 2);
                  LODWORD(v34) = v22;
                  goto LABEL_32;
                }
                break;
              }
              LODWORD(v19) = v27;
            }
            appended = IsConditionBitwiseOperation(a5, COP_APPLICATION_SPECIFIC, (enum BITSSET *)&v34);
            if ( appended < 0 )
              goto LABEL_44;
            appended = DSA_InsertItem(**((HDSA **)this + 26), 0x7FFFFFFF, &pitem);
            if ( appended < 0 )
              goto LABEL_44;
            v22 = v34;
LABEL_32:
            if ( !v22 )
              goto LABEL_44;
            v23 = *((_QWORD *)this + 5);
            v27 = 0;
            appended = (*(__int64 (__fastcall **)(__int64, _QWORD, int *))(*(_QWORD *)v23 + 48LL))(v23, pulRet, &v27);
            v8 = (const PROPVARIANT *)v28;
            if ( appended >= 0 )
            {
              pulRet = 0;
              v31 = 19;
              v32 = v27;
              appended = BitwiseCompareValues(v28, &v31, (unsigned int)v34, a6, &pulRet);
              if ( appended >= 0 )
              {
                *(_DWORD *)a7 = 2 - (pulRet != 0);
                return (unsigned int)appended;
              }
            }
            goto LABEL_45;
          }
          if ( pulRet && ((pulRet - 1LL) & pulRet) == 0 )
          {
            if ( (*(unsigned int (__fastcall **)(_QWORD, _QWORD, ULONG *))(**((_QWORD **)this + 5) + 48LL))(
                   *((_QWORD *)this + 5),
                   pulRet,
                   &pulRet) )
            {
              if ( !a6 )
LABEL_42:
                v14 = 2;
            }
            else if ( a6 )
            {
              goto LABEL_42;
            }
            *(_DWORD *)a7 = v14;
            return (unsigned int)appended;
          }
LABEL_44:
          v8 = (const PROPVARIANT *)v28;
        }
      }
    }
  }
LABEL_45:
  if ( !(unsigned int)operator==(a3, &PKEY_Search_Contents) )
  {
    appended = CConditionEvaluator::v_DoesItemMatchLeafCondition(
                 this,
                 (const struct tagPROPVARIANT *)v8,
                 a3,
                 v29,
                 a5,
                 v24,
                 a7,
                 v30);
    if ( appended >= 0 && *((_DWORD *)this + 17) && *(_DWORD *)a7 == 2 && *(_WORD *)v8 != 11 )
      *(_DWORD *)a7 = 0;
  }
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x18004b8d0  mov     [rsp-8+arg_18], rbx
0x18004b8d5  push    rbp
0x18004b8d6  push    rsi
0x18004b8d7  push    rdi
0x18004b8d8  push    r12
0x18004b8da  push    r13
0x18004b8dc  push    r14
0x18004b8de  push    r15
0x18004b8e0  lea     rbp, [rsp-7]
0x18004b8e5  sub     rsp, 90h
0x18004b8ec  mov     rax, cs:__security_cookie
0x18004b8f3  xor     rax, rsp
0x18004b8f6  mov     [rbp+37h+var_38], rax
0x18004b8fa  mov     rax, [rbp+37h+arg_38]
0x18004b8fe  mov     r13, rdx
0x18004b901  mov     rsi, [rbp+37h+arg_20]
0x18004b905  mov     rdi, rcx
0x18004b908  mov     r15, [rbp+37h+arg_30]
0x18004b90c  mov     rcx, r8
0x18004b90f  mov     [rbp+37h+var_78], rdx
0x18004b913  mov     r12, r8
0x18004b916  lea     rdx, PKEY_Generic_String
0x18004b91d  mov     [rbp+37h+var_68], rax
0x18004b921  mov     [rbp+37h+var_70], r9d
0x18004b925  xor     ebx, ebx
0x18004b927  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18004b92c  lea     r14d, [rbx+1]
0x18004b930  test    eax, eax
0x18004b932  jnz     short loc_18004B972
0x18004b934  cmp     [rdi+28h], rbx
0x18004b938  jz      loc_18004BA2E
0x18004b93e  lea     rdx, PKEY_FullText
0x18004b945  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18004b94a  test    eax, eax
0x18004b94c  jnz     short loc_18004B972
0x18004b94e  lea     rdx, PKEY_ForceFullText
0x18004b955  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18004b95a  test    eax, eax
0x18004b95c  jnz     short loc_18004B972
0x18004b95e  lea     rdx, PKEY_Search_Contents
0x18004b965  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18004b96a  test    eax, eax
0x18004b96c  jz      loc_18004BA2E
0x18004b972  cmp     [rdi+44h], ebx
0x18004b975  jnz     loc_18004BA2E
0x18004b97b  cmp     [rdi+0C0h], ebx
0x18004b981  jnz     short loc_18004B9AE
0x18004b983  lea     rdx, PKEY_ForceFullText
0x18004b98a  mov     rcx, r12
0x18004b98d  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18004b992  test    eax, eax
0x18004b994  jnz     short loc_18004B9A6
0x18004b996  lea     rdx, PKEY_Search_Contents
0x18004b99d  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18004b9a2  test    eax, eax
0x18004b9a4  jz      short loc_18004B9D3
0x18004b9a6  cmp     [rdi+0C4h], ebx
0x18004b9ac  jz      short loc_18004B9D3
0x18004b9ae  lea     rcx, [rdi+58h]
0x18004b9b2  mov     [rdi+3Ch], r14d
0x18004b9b6  mov     rdx, rsi
0x18004b9b9  call    ?AppendPtr@?$CDPA_Base@UICondition@@V?$CTContainer_PolicyRelease@UICondition@@@@@@QEAAJPEAUICondition@@PEAH@Z; CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::AppendPtr(ICondition *,int *)
0x18004b9be  mov     ebx, eax
0x18004b9c0  test    eax, eax
0x18004b9c2  js      short loc_18004BA11
0x18004b9c4  mov     rax, [rsi]
0x18004b9c7  mov     rcx, rsi
0x18004b9ca  mov     rax, [rax+8]
0x18004b9ce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9d3  lea     rcx, [rdi+50h]
0x18004b9d7  mov     rdx, rsi
0x18004b9da  call    ?AppendPtr@?$CDPA_Base@UICondition@@V?$CTContainer_PolicyRelease@UICondition@@@@@@QEAAJPEAUICondition@@PEAH@Z; CDPA_Base<ICondition,CTContainer_PolicyRelease<ICondition>>::AppendPtr(ICondition *,int *)
0x18004b9df  mov     ebx, eax
0x18004b9e1  test    eax, eax
0x18004b9e3  js      short loc_18004BA11
0x18004b9e5  mov     rax, [rsi]
0x18004b9e8  mov     rcx, rsi
0x18004b9eb  mov     rax, [rax+8]
0x18004b9ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004b9f4  mov     eax, [rbp+37h+arg_28]
0x18004b9f7  lea     rdx, aNegate; "Negate"
0x18004b9fe  neg     eax
0x18004ba00  mov     rcx, rsi
0x18004ba03  sbb     r8d, r8d
0x18004ba06  add     r8d, 2
0x18004ba0a  call    SetEvalStateEx
0x18004ba0f  mov     ebx, eax
0x18004ba11  xor     r8d, r8d
0x18004ba14  mov     dword ptr [r15], 0
0x18004ba1b  lea     rdx, aEs; "ES"
0x18004ba22  mov     rcx, rsi
0x18004ba25  call    SetEvalStateEx
0x18004ba2a  mov     r9d, [rbp+37h+var_70]
0x18004ba2e  cmp     qword ptr [rdi+28h], 0
0x18004ba33  jz      loc_18004BBF7
0x18004ba39  cmp     r9d, 0Eh
0x18004ba3d  jnz     loc_18004BBF7
0x18004ba43  lea     rdx, PKEY_SFGAOFlags
0x18004ba4a  mov     rcx, r12
0x18004ba4d  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18004ba52  test    eax, eax
0x18004ba54  jz      loc_18004BBF7
0x18004ba5a  lea     rdx, [rbp+37h+pulRet]; pulRet
0x18004ba5e  mov     [rbp+37h+pulRet], 0
0x18004ba65  mov     rcx, r13; propvarIn
0x18004ba68  call    cs:__imp_PropVariantToUInt32
0x18004ba6e  mov     ebx, eax
0x18004ba70  test    eax, eax
0x18004ba72  js      loc_18004BBF7
0x18004ba78  mov     r13, [rdi+0D0h]
0x18004ba7f  test    r13, r13
0x18004ba82  jz      loc_18004BBB3
0x18004ba88  mov     [rbp+37h+var_40], 0
0x18004ba90  mov     [rbp+37h+pitem], rsi
0x18004ba94  mov     rax, [r13+0]
0x18004ba98  test    rax, rax
0x18004ba9b  jz      short loc_18004BA9F
0x18004ba9d  mov     eax, [rax]
0x18004ba9f  mov     [rbp+37h+var_7C], eax
0x18004baa2  xor     r14d, r14d
0x18004baa5  cmp     r14d, eax
0x18004baa8  jge     short loc_18004BAF3
0x18004baaa  mov     rcx, [r13+0]; hdsa
0x18004baae  mov     edx, r14d; i
0x18004bab1  call    cs:__imp_DSA_GetItemPtr
0x18004bab7  xor     r8d, r8d; __int64
0x18004baba  lea     rcx, [rbp+37h+pitem]; struct CONDITIONBITSSETCACHE *
0x18004babe  mov     rdx, rax; struct CONDITIONBITSSETCACHE *
0x18004bac1  call    ?DSACompareBitsCache@@YAHPEBUCONDITIONBITSSETCACHE@@0_J@Z; DSACompareBitsCache(CONDITIONBITSSETCACHE const *,CONDITIONBITSSETCACHE const *,__int64)
0x18004bac6  test    eax, eax
0x18004bac8  jz      short loc_18004BAD2
0x18004baca  mov     eax, [rbp+37h+var_7C]
0x18004bacd  inc     r14d
0x18004bad0  jmp     short loc_18004BAA5
0x18004bad2  cmp     r14d, 0FFFFFFFFh
0x18004bad6  jz      short loc_18004BAF3
0x18004bad8  mov     rcx, [rdi+0D0h]
0x18004badf  mov     edx, r14d; i
0x18004bae2  mov     rcx, [rcx]; hdsa
0x18004bae5  call    cs:__imp_DSA_GetItemPtr
0x18004baeb  mov     ecx, [rax+8]
0x18004baee  mov     dword ptr [rbp+37h+var_40], ecx
0x18004baf1  jmp     short loc_18004BB34
0x18004baf3  lea     r8, [rbp+37h+var_40]; enum BITSSET *
0x18004baf7  mov     edx, 0Eh; enum tagCONDITION_OPERATION
0x18004bafc  mov     rcx, rsi; struct ICondition *
0x18004baff  call    ?IsConditionBitwiseOperation@@YAJPEAUICondition@@W4tagCONDITION_OPERATION@@PEAW4BITSSET@@@Z; IsConditionBitwiseOperation(ICondition *,tagCONDITION_OPERATION,BITSSET *)
0x18004bb04  mov     ebx, eax
0x18004bb06  test    eax, eax
0x18004bb08  js      loc_18004BBF3
0x18004bb0e  mov     rcx, [rdi+0D0h]
0x18004bb15  lea     r8, [rbp+37h+pitem]; pitem
0x18004bb19  mov     edx, 7FFFFFFFh; i
0x18004bb1e  mov     rcx, [rcx]; hdsa
0x18004bb21  call    cs:__imp_DSA_InsertItem
0x18004bb27  mov     ebx, eax
0x18004bb29  test    eax, eax
0x18004bb2b  js      loc_18004BBF3
0x18004bb31  mov     ecx, dword ptr [rbp+37h+var_40]
0x18004bb34  test    ecx, ecx
0x18004bb36  jz      loc_18004BBF3
0x18004bb3c  mov     rcx, [rdi+28h]
0x18004bb40  lea     r8, [rbp+37h+var_7C]
0x18004bb44  mov     edx, [rbp+37h+pulRet]
0x18004bb47  mov     [rbp+37h+var_7C], 0
0x18004bb4e  mov     rax, [rcx]
0x18004bb51  mov     rax, [rax+30h]
0x18004bb55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bb5a  mov     r9d, [rbp+37h+arg_28]
0x18004bb5e  mov     ebx, eax
0x18004bb60  mov     r13, [rbp+37h+var_78]
0x18004bb64  test    eax, eax
0x18004bb66  js      loc_18004BBFB
0x18004bb6c  mov     r8d, dword ptr [rbp+37h+var_40]
0x18004bb70  lea     rdx, [rbp+37h+var_60]
0x18004bb74  mov     eax, 13h
0x18004bb79  mov     [rbp+37h+pulRet], 0
0x18004bb80  mov     [rbp+37h+var_60], ax
0x18004bb84  mov     rcx, r13
0x18004bb87  mov     eax, [rbp+37h+var_7C]
0x18004bb8a  mov     [rbp+37h+var_58], eax
0x18004bb8d  lea     rax, [rbp+37h+pulRet]
0x18004bb91  mov     [rsp+0C0h+var_A0], rax
0x18004bb96  call    ?BitwiseCompareValues@@YAJAEBUtagPROPVARIANT@@0W4BITSSET@@HPEAH@Z; BitwiseCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,BITSSET,int,int *)
0x18004bb9b  mov     ebx, eax
0x18004bb9d  test    eax, eax
0x18004bb9f  js      short loc_18004BBFB
0x18004bba1  mov     eax, [rbp+37h+pulRet]
0x18004bba4  neg     eax
0x18004bba6  sbb     ecx, ecx
0x18004bba8  add     ecx, 2
0x18004bbab  mov     [r15], ecx
0x18004bbae  jmp     loc_18004BC59
0x18004bbb3  mov     edx, [rbp+37h+pulRet]
0x18004bbb6  test    edx, edx
0x18004bbb8  jz      short loc_18004BBF3
0x18004bbba  lea     rax, [rdx-1]
0x18004bbbe  test    rdx, rax
0x18004bbc1  jnz     short loc_18004BBF3
0x18004bbc3  mov     rcx, [rdi+28h]
0x18004bbc7  lea     r8, [rbp+37h+pulRet]
0x18004bbcb  mov     rax, [rcx]
0x18004bbce  mov     rax, [rax+30h]
0x18004bbd2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004bbd7  test    eax, eax
0x18004bbd9  jnz     short loc_18004BBE2
0x18004bbdb  cmp     [rbp+37h+arg_28], eax
0x18004bbde  jz      short loc_18004BBEE
0x18004bbe0  jmp     short loc_18004BBE8
0x18004bbe2  cmp     [rbp+37h+arg_28], 0
0x18004bbe6  jnz     short loc_18004BBEE
0x18004bbe8  mov     r14d, 2
0x18004bbee  mov     [r15], r14d
0x18004bbf1  jmp     short loc_18004BC59
0x18004bbf3  mov     r13, [rbp+37h+var_78]
0x18004bbf7  mov     r9d, [rbp+37h+arg_28]
0x18004bbfb  lea     rdx, PKEY_Search_Contents
0x18004bc02  mov     rcx, r12
0x18004bc05  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x18004bc0a  test    eax, eax
0x18004bc0c  jnz     short loc_18004BC59
0x18004bc0e  mov     rax, [rbp+37h+var_68]
0x18004bc12  mov     r8, r12; struct _tagpropertykey *
0x18004bc15  mov     [rsp+0C0h+var_88], rax; int *
0x18004bc1a  mov     rdx, r13; struct tagPROPVARIANT *
0x18004bc1d  mov     [rsp+0C0h+var_90], r15; enum TRIBIT *
0x18004bc22  mov     rcx, rdi; this
0x18004bc25  mov     [rsp+0C0h+var_98], r9d; int
0x18004bc2a  mov     r9d, [rbp+37h+var_70]; enum tagCONDITION_OPERATION
0x18004bc2e  mov     [rsp+0C0h+var_A0], rsi; struct ICondition *
0x18004bc33  call    ?v_DoesItemMatchLeafCondition@CConditionEvaluator@@MEAAJAEBUtagPROPVARIANT@@AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEAUICondition@@HPEAW4TRIBIT@@PEAH@Z; CConditionEvaluator::v_DoesItemMatchLeafCondition(tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,ICondition *,int,TRIBIT *,int *)
0x18004bc38  mov     ebx, eax
0x18004bc3a  test    eax, eax
0x18004bc3c  js      short loc_18004BC59
0x18004bc3e  cmp     dword ptr [rdi+44h], 0
0x18004bc42  jz      short loc_18004BC59
0x18004bc44  cmp     dword ptr [r15], 2
0x18004bc48  jnz     short loc_18004BC59
0x18004bc4a  cmp     word ptr [r13+0], 0Bh
0x18004bc50  jz      short loc_18004BC59
0x18004bc52  mov     dword ptr [r15], 0
0x18004bc59  mov     eax, ebx
0x18004bc5b  mov     rcx, [rbp+37h+var_38]
0x18004bc5f  xor     rcx, rsp; StackCookie
0x18004bc62  call    __security_check_cookie
0x18004bc67  mov     rbx, [rsp+0C0h+arg_18]
0x18004bc6f  add     rsp, 90h
0x18004bc76  pop     r15
0x18004bc78  pop     r14
0x18004bc7a  pop     r13
0x18004bc7c  pop     r12
0x18004bc7e  pop     rdi
0x18004bc7f  pop     rsi
0x18004bc80  pop     rbp
0x18004bc81  retn
```
