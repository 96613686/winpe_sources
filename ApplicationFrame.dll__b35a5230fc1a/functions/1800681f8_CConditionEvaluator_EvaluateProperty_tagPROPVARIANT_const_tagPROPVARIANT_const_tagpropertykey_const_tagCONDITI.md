# CConditionEvaluator::_EvaluateProperty(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,ICondition *,int,int *,int *)

- ea: `0x1800681f8`
- end: `0x180068492`
- name: `?_EvaluateProperty@CConditionEvaluator@@AEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEAUICondition@@HPEAH4@Z`
- size: `666`
- prototype: `__int64 __usercall@<rax>(CConditionEvaluator *__hidden this@<rcx>, const struct tagPROPVARIANT *@<rdx>, const struct tagPROPVARIANT *@<r8>, const struct _tagpropertykey *@<r9>, enum tagCONDITION_OPERATION, struct ICondition *, int, int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18006a090`

## callees

- `0x180063358`
- `0x180064250`
- `0x180066198`
- `0x1800681f8`
- `0x18006881c`
- `0x18006abc0`
- `0x180072010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180068445`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180068445`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068469`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180068469`
- `PROPSYS!PropVariantGetElementCount` at `0x18006828c`
- `PROPSYS!PropVariantGetElementCount` at `0x18006828c`

## pseudocode

```c
__int64 __fastcall CConditionEvaluator::_EvaluateProperty(
        CConditionEvaluator *this,
        PROPVARIANT *a2,
        const PROPVARIANT *a3,
        struct _tagpropertykey *a4,
        enum tagCONDITION_OPERATION a5,
        struct ICondition *a6,
        unsigned int a7,
        int *a8,
        int *a9)
{
  int v12; // ebx
  LCID InputLocale; // r12d
  struct IConditionVtbl *lpVtbl; // rax
  const struct _GUID *v15; // r8
  PROPVARIANT *v16; // r8
  int v17; // r14d
  int v18; // esi
  int *v19; // rcx
  unsigned int v21; // [rsp+80h] [rbp-31h] BYREF
  int v22; // [rsp+84h] [rbp-2Dh] BYREF
  LPVOID pv; // [rsp+88h] [rbp-29h] BYREF
  void *v24; // [rsp+90h] [rbp-21h] BYREF
  PROPVARIANT pvar[2]; // [rsp+98h] [rbp-19h] BYREF
  __int64 v26; // [rsp+A8h] [rbp-9h]

  v21 = 0;
  v12 = IsConditionBitwiseOperation(a6, a5, (enum BITSSET *)&v21);
  if ( v12 >= 0 )
  {
    v22 = 0;
    if ( (int)GetLocaleFromCondition(a6, &v22) >= 0 )
      InputLocale = v22;
    else
      InputLocale = CConditionEvaluator::_GetInputLocale(this);
    lpVtbl = a6->lpVtbl;
    pv = 0;
    ((void (__fastcall *)(struct ICondition *, LPVOID *))lpVtbl->GetValueType)(a6, &pv);
    if ( !PropVariantGetElementCount(a3) )
    {
      v16 = pvar;
      *(_OWORD *)pvar = 0;
      v26 = 0;
LABEL_9:
      v12 = CConditionEvaluator::FilterConditionCompareValues(
              this,
              a2,
              v16,
              a4,
              a5,
              *((_DWORD *)this + 6),
              *((_DWORD *)this + 7),
              *((struct IPropertyInfoProvider **)this + 4),
              a7,
              *((_QWORD *)this + 6),
              v21,
              (const WCHAR *)pv,
              InputLocale,
              a8,
              a9);
LABEL_25:
      CoTaskMemFree(pv);
      return (unsigned int)v12;
    }
    if ( (*(_WORD *)a3 & 0x3000) == 0 )
    {
      v16 = (PROPVARIANT *)a3;
      goto LABEL_9;
    }
    v24 = 0;
    v12 = CMultipleValues_CreateInstance((const struct tagPROPVARIANT *)a3, a4, v15, &v24);
    if ( v12 < 0 )
      goto LABEL_25;
    v22 = 0;
    v12 = (*(__int64 (__fastcall **)(void *, int *))(*(_QWORD *)v24 + 96LL))(v24, &v22);
    if ( v12 < 0 )
    {
LABEL_24:
      (*(void (__fastcall **)(void *))(*(_QWORD *)v24 + 16LL))(v24);
      goto LABEL_25;
    }
    v17 = 0;
    v18 = 0;
    while ( 1 )
    {
      if ( v17 || v18 >= v22 )
        goto LABEL_24;
      v26 = 0;
      *(_OWORD *)pvar = 0;
      v12 = (*(__int64 (__fastcall **)(void *, _QWORD, PROPVARIANT *))(*(_QWORD *)v24 + 88LL))(
              v24,
              (unsigned int)v18,
              pvar);
      if ( v12 >= 0 )
        break;
LABEL_23:
      ++v18;
      if ( v12 < 0 )
        goto LABEL_24;
    }
    v19 = a9;
    if ( v18 )
      v19 = 0;
    v12 = CConditionEvaluator::FilterConditionCompareValues(
            this,
            a2,
            pvar,
            a4,
            a5,
            *((_DWORD *)this + 6),
            *((_DWORD *)this + 7),
            *((struct IPropertyInfoProvider **)this + 4),
            a7,
            *((_QWORD *)this + 6),
            v21,
            (const WCHAR *)pv,
            InputLocale,
            a8,
            v19);
    if ( v12 < 0 )
    {
LABEL_22:
      PropVariantClear(pvar);
      goto LABEL_23;
    }
    if ( *a8 )
    {
      if ( a7 )
      {
LABEL_21:
        v17 = 0;
        goto LABEL_22;
      }
    }
    else if ( !a7 )
    {
      goto LABEL_21;
    }
    v17 = 1;
    goto LABEL_22;
  }
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x1800681f8  mov     [rsp-8+arg_8], rdx
0x1800681fd  push    rbp
0x1800681fe  push    rbx
0x1800681ff  push    rsi
0x180068200  push    rdi
0x180068201  push    r12
0x180068203  push    r13
0x180068205  push    r14
0x180068207  push    r15
0x180068209  lea     rbp, [rsp-7]
0x18006820e  sub     rsp, 0B8h
0x180068215  mov     r14, [rbp+3Fh+arg_28]
0x180068219  mov     rsi, r8
0x18006821c  mov     r15d, [rbp+3Fh+arg_20]
0x180068220  lea     r8, [rbp+3Fh+var_70]; enum BITSSET *
0x180068224  mov     rdi, rcx
0x180068227  mov     [rbp+3Fh+var_70], 0
0x18006822e  mov     rcx, r14; struct ICondition *
0x180068231  mov     edx, r15d; enum tagCONDITION_OPERATION
0x180068234  mov     r13, r9
0x180068237  call    ?IsConditionBitwiseOperation@@YAJPEAUICondition@@W4tagCONDITION_OPERATION@@PEAW4BITSSET@@@Z; IsConditionBitwiseOperation(ICondition *,tagCONDITION_OPERATION,BITSSET *)
0x18006823c  mov     ebx, eax
0x18006823e  test    eax, eax
0x180068240  js      loc_18006846F
0x180068246  lea     rdx, [rbp+3Fh+var_6C]
0x18006824a  mov     [rbp+3Fh+var_6C], 0
0x180068251  mov     rcx, r14
0x180068254  call    GetLocaleFromCondition
0x180068259  test    eax, eax
0x18006825b  jns     short loc_18006826A
0x18006825d  mov     rcx, rdi; this
0x180068260  call    ?_GetInputLocale@CConditionEvaluator@@IEAAKXZ; CConditionEvaluator::_GetInputLocale(void)
0x180068265  mov     r12d, eax
0x180068268  jmp     short loc_18006826E
0x18006826a  mov     r12d, [rbp+3Fh+var_6C]
0x18006826e  mov     rax, [r14]
0x180068271  lea     rdx, [rbp+3Fh+pv]
0x180068275  mov     rcx, r14
0x180068278  mov     [rbp+3Fh+pv], 0
0x180068280  mov     rax, [rax+58h]
0x180068284  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068289  mov     rcx, rsi; propvar
0x18006828c  call    cs:__imp_PropVariantGetElementCount
0x180068292  test    eax, eax
0x180068294  jnz     short loc_1800682A9
0x180068296  xorps   xmm0, xmm0
0x180068299  lea     r8, [rbp+3Fh+pvar]
0x18006829d  xor     eax, eax
0x18006829f  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x1800682a3  mov     [rbp+3Fh+var_48], rax
0x1800682a7  jmp     short loc_1800682B6
0x1800682a9  mov     eax, 3000h
0x1800682ae  test    [rsi], ax
0x1800682b1  jnz     short loc_180068325
0x1800682b3  mov     r8, rsi
0x1800682b6  mov     rax, [rbp+3Fh+arg_40]
0x1800682bd  mov     r9, r13
0x1800682c0  mov     rdx, [rbp+3Fh+arg_8]
0x1800682c4  mov     rcx, rdi
0x1800682c7  mov     [rsp+0F0h+var_80], rax
0x1800682cc  mov     rax, [rbp+3Fh+arg_38]
0x1800682d3  mov     [rsp+0F0h+var_88], rax
0x1800682d8  mov     rax, [rbp+3Fh+pv]
0x1800682dc  mov     [rsp+0F0h+var_90], r12d
0x1800682e1  mov     [rsp+0F0h+var_98], rax
0x1800682e6  mov     eax, [rbp+3Fh+var_70]
0x1800682e9  mov     [rsp+0F0h+var_A0], eax
0x1800682ed  mov     rax, [rdi+30h]
0x1800682f1  mov     [rsp+0F0h+var_A8], rax
0x1800682f6  mov     eax, [rbp+3Fh+arg_30]
0x1800682f9  mov     [rsp+0F0h+var_B0], eax
0x1800682fd  mov     rax, [rdi+20h]
0x180068301  mov     [rsp+0F0h+var_B8], rax
0x180068306  mov     eax, [rdi+1Ch]
0x180068309  mov     [rsp+0F0h+var_C0], eax
0x18006830d  mov     eax, [rdi+18h]
0x180068310  mov     [rsp+0F0h+var_C8], eax
0x180068314  mov     [rsp+0F0h+var_D0], r15d
0x180068319  call    ?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z; CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)
0x18006831e  mov     ebx, eax
0x180068320  jmp     loc_180068465
0x180068325  lea     r9, [rbp+3Fh+var_60]; void **
0x180068329  mov     [rbp+3Fh+var_60], 0
0x180068331  mov     rdx, r13; struct _tagpropertykey *
0x180068334  mov     rcx, rsi; struct tagPROPVARIANT *
0x180068337  call    ?CMultipleValues_CreateInstance@@YAJPEBUtagPROPVARIANT@@AEBU_tagpropertykey@@AEBU_GUID@@PEAPEAX@Z; CMultipleValues_CreateInstance(tagPROPVARIANT const *,_tagpropertykey const &,_GUID const &,void * *)
0x18006833c  mov     ebx, eax
0x18006833e  test    eax, eax
0x180068340  js      loc_180068465
0x180068346  mov     rcx, [rbp+3Fh+var_60]
0x18006834a  lea     rdx, [rbp+3Fh+var_6C]
0x18006834e  mov     [rbp+3Fh+var_6C], 0
0x180068355  mov     rax, [rcx]
0x180068358  mov     rax, [rax+60h]
0x18006835c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068361  mov     ebx, eax
0x180068363  test    eax, eax
0x180068365  js      loc_180068455
0x18006836b  mov     r15d, [rbp+3Fh+arg_30]
0x18006836f  xor     r14d, r14d
0x180068372  xor     esi, esi
0x180068374  test    r14d, r14d
0x180068377  jnz     loc_180068455
0x18006837d  cmp     esi, [rbp+3Fh+var_6C]
0x180068380  jge     loc_180068455
0x180068386  mov     rcx, [rbp+3Fh+var_60]
0x18006838a  lea     r8, [rbp+3Fh+pvar]
0x18006838e  xor     eax, eax
0x180068390  xorps   xmm0, xmm0
0x180068393  mov     [rbp+3Fh+var_48], rax
0x180068397  mov     edx, esi
0x180068399  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x18006839d  mov     rax, [rcx]
0x1800683a0  mov     rax, [rax+58h]
0x1800683a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800683a9  mov     ebx, eax
0x1800683ab  test    eax, eax
0x1800683ad  js      loc_18006844B
0x1800683b3  mov     rcx, [rbp+3Fh+arg_40]
0x1800683ba  lea     r8, [rbp+3Fh+pvar]
0x1800683be  mov     rdx, [rbp+3Fh+arg_8]
0x1800683c2  xor     eax, eax
0x1800683c4  test    esi, esi
0x1800683c6  mov     r9, r13
0x1800683c9  cmovnz  rcx, rax
0x1800683cd  mov     rax, [rbp+3Fh+arg_38]
0x1800683d4  mov     [rsp+0F0h+var_80], rcx
0x1800683d9  mov     rcx, rdi
0x1800683dc  mov     [rsp+0F0h+var_88], rax
0x1800683e1  mov     rax, [rbp+3Fh+pv]
0x1800683e5  mov     [rsp+0F0h+var_90], r12d
0x1800683ea  mov     [rsp+0F0h+var_98], rax
0x1800683ef  mov     eax, [rbp+3Fh+var_70]
0x1800683f2  mov     [rsp+0F0h+var_A0], eax
0x1800683f6  mov     rax, [rdi+30h]
0x1800683fa  mov     [rsp+0F0h+var_A8], rax
0x1800683ff  mov     rax, [rdi+20h]
0x180068403  mov     [rsp+0F0h+var_B0], r15d
0x180068408  mov     [rsp+0F0h+var_B8], rax
0x18006840d  mov     eax, [rdi+1Ch]
0x180068410  mov     [rsp+0F0h+var_C0], eax
0x180068414  mov     eax, [rdi+18h]
0x180068417  mov     [rsp+0F0h+var_C8], eax
0x18006841b  mov     eax, [rbp+3Fh+arg_20]
0x18006841e  mov     [rsp+0F0h+var_D0], eax
0x180068422  call    ?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z; CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)
0x180068427  mov     ebx, eax
0x180068429  test    eax, eax
0x18006842b  js      short loc_180068441
0x18006842d  mov     rax, [rbp+3Fh+arg_38]
0x180068434  cmp     [rax], r14d
0x180068437  jz      short loc_180068485
0x180068439  test    r15d, r15d
0x18006843c  jz      short loc_18006848A
0x18006843e  xor     r14d, r14d
0x180068441  lea     rcx, [rbp+3Fh+pvar]; pvar
0x180068445  call    cs:__imp_PropVariantClear
0x18006844b  inc     esi
0x18006844d  test    ebx, ebx
0x18006844f  jns     loc_180068374
0x180068455  mov     rcx, [rbp+3Fh+var_60]
0x180068459  mov     rax, [rcx]
0x18006845c  mov     rax, [rax+10h]
0x180068460  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180068465  mov     rcx, [rbp+3Fh+pv]; pv
0x180068469  call    cs:__imp_CoTaskMemFree
0x18006846f  mov     eax, ebx
0x180068471  add     rsp, 0B8h
0x180068478  pop     r15
0x18006847a  pop     r14
0x18006847c  pop     r13
0x18006847e  pop     r12
0x180068480  pop     rdi
0x180068481  pop     rsi
0x180068482  pop     rbx
0x180068483  pop     rbp
0x180068484  retn
0x180068485  test    r15d, r15d
0x180068488  jz      short loc_18006843E
0x18006848a  mov     r14d, 1
0x180068490  jmp     short loc_180068441
```
