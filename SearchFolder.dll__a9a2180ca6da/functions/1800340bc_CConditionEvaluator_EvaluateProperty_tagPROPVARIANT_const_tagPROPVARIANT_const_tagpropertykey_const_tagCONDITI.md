# CConditionEvaluator::_EvaluateProperty(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,ICondition *,int,int *,int *)

- ea: `0x1800340bc`
- end: `0x180034356`
- name: `?_EvaluateProperty@CConditionEvaluator@@AEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEAUICondition@@HPEAH4@Z`
- size: `666`
- prototype: `__int64 __fastcall(CConditionEvaluator *this, const struct tagPROPVARIANT *, const PROPVARIANT *, const struct _tagpropertykey *, enum tagCONDITION_OPERATION, struct ICondition *, int, int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18003ac60`

## callees

- `0x1800290c8`
- `0x18002a61c`
- `0x18002e190`
- `0x1800340bc`
- `0x180034c5c`
- `0x18003c324`
- `0x180051010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034309`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180034309`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003432d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003432d`
- `PROPSYS!PropVariantGetElementCount` at `0x180034150`
- `PROPSYS!PropVariantGetElementCount` at `0x180034150`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall CConditionEvaluator::_EvaluateProperty(
        CConditionEvaluator *this,
        const struct tagPROPVARIANT *a2,
        const PROPVARIANT *a3,
        const struct _tagpropertykey *a4,
        enum tagCONDITION_OPERATION a5,
        struct ICondition *a6,
        int a7,
        int *a8,
        int *a9)
{
  int v12; // ebx
  unsigned int InputLocale; // r12d
  struct IConditionVtbl *lpVtbl; // rax
  const struct _GUID *v15; // r8
  PROPVARIANT *v16; // r8
  int v17; // r14d
  signed int v18; // esi
  int *v19; // rcx
  int v21; // [rsp+80h] [rbp-31h] BYREF
  signed int v22; // [rsp+84h] [rbp-2Dh] BYREF
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
              *((_QWORD *)this + 4),
              a7,
              *((_QWORD *)this + 6),
              v21,
              pv,
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
    v12 = (*(__int64 (__fastcall **)(void *, signed int *))(*(_QWORD *)v24 + 96LL))(v24, &v22);
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
            *((_QWORD *)this + 4),
            a7,
            *((_QWORD *)this + 6),
            v21,
            pv,
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
0x1800340bc  mov     [rsp-8+arg_8], rdx
0x1800340c1  push    rbp
0x1800340c2  push    rbx
0x1800340c3  push    rsi
0x1800340c4  push    rdi
0x1800340c5  push    r12
0x1800340c7  push    r13
0x1800340c9  push    r14
0x1800340cb  push    r15
0x1800340cd  lea     rbp, [rsp-7]
0x1800340d2  sub     rsp, 0B8h
0x1800340d9  mov     r14, [rbp+3Fh+arg_28]
0x1800340dd  mov     rsi, r8
0x1800340e0  mov     r15d, [rbp+3Fh+arg_20]
0x1800340e4  lea     r8, [rbp+3Fh+var_70]; enum BITSSET *
0x1800340e8  mov     rdi, rcx
0x1800340eb  mov     [rbp+3Fh+var_70], 0
0x1800340f2  mov     rcx, r14; struct ICondition *
0x1800340f5  mov     edx, r15d; enum tagCONDITION_OPERATION
0x1800340f8  mov     r13, r9
0x1800340fb  call    ?IsConditionBitwiseOperation@@YAJPEAUICondition@@W4tagCONDITION_OPERATION@@PEAW4BITSSET@@@Z; IsConditionBitwiseOperation(ICondition *,tagCONDITION_OPERATION,BITSSET *)
0x180034100  mov     ebx, eax
0x180034102  test    eax, eax
0x180034104  js      loc_180034333
0x18003410a  lea     rdx, [rbp+3Fh+var_6C]
0x18003410e  mov     [rbp+3Fh+var_6C], 0
0x180034115  mov     rcx, r14
0x180034118  call    GetLocaleFromCondition
0x18003411d  test    eax, eax
0x18003411f  jns     short loc_18003412E
0x180034121  mov     rcx, rdi; this
0x180034124  call    ?_GetInputLocale@CConditionEvaluator@@IEAAKXZ; CConditionEvaluator::_GetInputLocale(void)
0x180034129  mov     r12d, eax
0x18003412c  jmp     short loc_180034132
0x18003412e  mov     r12d, [rbp+3Fh+var_6C]
0x180034132  mov     rax, [r14]
0x180034135  lea     rdx, [rbp+3Fh+pv]
0x180034139  mov     rcx, r14
0x18003413c  mov     [rbp+3Fh+pv], 0
0x180034144  mov     rax, [rax+58h]
0x180034148  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003414d  mov     rcx, rsi; propvar
0x180034150  call    cs:__imp_PropVariantGetElementCount
0x180034156  test    eax, eax
0x180034158  jnz     short loc_18003416D
0x18003415a  xorps   xmm0, xmm0
0x18003415d  lea     r8, [rbp+3Fh+pvar]
0x180034161  xor     eax, eax
0x180034163  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x180034167  mov     [rbp+3Fh+var_48], rax
0x18003416b  jmp     short loc_18003417A
0x18003416d  mov     eax, 3000h
0x180034172  test    [rsi], ax
0x180034175  jnz     short loc_1800341E9
0x180034177  mov     r8, rsi
0x18003417a  mov     rax, [rbp+3Fh+arg_40]
0x180034181  mov     r9, r13
0x180034184  mov     rdx, [rbp+3Fh+arg_8]
0x180034188  mov     rcx, rdi
0x18003418b  mov     [rsp+0F0h+var_80], rax
0x180034190  mov     rax, [rbp+3Fh+arg_38]
0x180034197  mov     [rsp+0F0h+var_88], rax
0x18003419c  mov     rax, [rbp+3Fh+pv]
0x1800341a0  mov     [rsp+0F0h+var_90], r12d
0x1800341a5  mov     [rsp+0F0h+var_98], rax
0x1800341aa  mov     eax, [rbp+3Fh+var_70]
0x1800341ad  mov     [rsp+0F0h+var_A0], eax
0x1800341b1  mov     rax, [rdi+30h]
0x1800341b5  mov     [rsp+0F0h+var_A8], rax
0x1800341ba  mov     eax, [rbp+3Fh+arg_30]
0x1800341bd  mov     [rsp+0F0h+var_B0], eax
0x1800341c1  mov     rax, [rdi+20h]
0x1800341c5  mov     [rsp+0F0h+var_B8], rax
0x1800341ca  mov     eax, [rdi+1Ch]
0x1800341cd  mov     [rsp+0F0h+var_C0], eax
0x1800341d1  mov     eax, [rdi+18h]
0x1800341d4  mov     [rsp+0F0h+var_C8], eax
0x1800341d8  mov     [rsp+0F0h+var_D0], r15d
0x1800341dd  call    ?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z; CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)
0x1800341e2  mov     ebx, eax
0x1800341e4  jmp     loc_180034329
0x1800341e9  lea     r9, [rbp+3Fh+var_60]; void **
0x1800341ed  mov     [rbp+3Fh+var_60], 0
0x1800341f5  mov     rdx, r13; struct _tagpropertykey *
0x1800341f8  mov     rcx, rsi; struct tagPROPVARIANT *
0x1800341fb  call    ?CMultipleValues_CreateInstance@@YAJPEBUtagPROPVARIANT@@AEBU_tagpropertykey@@AEBU_GUID@@PEAPEAX@Z; CMultipleValues_CreateInstance(tagPROPVARIANT const *,_tagpropertykey const &,_GUID const &,void * *)
0x180034200  mov     ebx, eax
0x180034202  test    eax, eax
0x180034204  js      loc_180034329
0x18003420a  mov     rcx, [rbp+3Fh+var_60]
0x18003420e  lea     rdx, [rbp+3Fh+var_6C]
0x180034212  mov     [rbp+3Fh+var_6C], 0
0x180034219  mov     rax, [rcx]
0x18003421c  mov     rax, [rax+60h]
0x180034220  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034225  mov     ebx, eax
0x180034227  test    eax, eax
0x180034229  js      loc_180034319
0x18003422f  mov     r15d, [rbp+3Fh+arg_30]
0x180034233  xor     r14d, r14d
0x180034236  xor     esi, esi
0x180034238  test    r14d, r14d
0x18003423b  jnz     loc_180034319
0x180034241  cmp     esi, [rbp+3Fh+var_6C]
0x180034244  jge     loc_180034319
0x18003424a  mov     rcx, [rbp+3Fh+var_60]
0x18003424e  lea     r8, [rbp+3Fh+pvar]
0x180034252  xor     eax, eax
0x180034254  xorps   xmm0, xmm0
0x180034257  mov     [rbp+3Fh+var_48], rax
0x18003425b  mov     edx, esi
0x18003425d  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x180034261  mov     rax, [rcx]
0x180034264  mov     rax, [rax+58h]
0x180034268  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003426d  mov     ebx, eax
0x18003426f  test    eax, eax
0x180034271  js      loc_18003430F
0x180034277  mov     rcx, [rbp+3Fh+arg_40]
0x18003427e  lea     r8, [rbp+3Fh+pvar]
0x180034282  mov     rdx, [rbp+3Fh+arg_8]
0x180034286  xor     eax, eax
0x180034288  test    esi, esi
0x18003428a  mov     r9, r13
0x18003428d  cmovnz  rcx, rax
0x180034291  mov     rax, [rbp+3Fh+arg_38]
0x180034298  mov     [rsp+0F0h+var_80], rcx
0x18003429d  mov     rcx, rdi
0x1800342a0  mov     [rsp+0F0h+var_88], rax
0x1800342a5  mov     rax, [rbp+3Fh+pv]
0x1800342a9  mov     [rsp+0F0h+var_90], r12d
0x1800342ae  mov     [rsp+0F0h+var_98], rax
0x1800342b3  mov     eax, [rbp+3Fh+var_70]
0x1800342b6  mov     [rsp+0F0h+var_A0], eax
0x1800342ba  mov     rax, [rdi+30h]
0x1800342be  mov     [rsp+0F0h+var_A8], rax
0x1800342c3  mov     rax, [rdi+20h]
0x1800342c7  mov     [rsp+0F0h+var_B0], r15d
0x1800342cc  mov     [rsp+0F0h+var_B8], rax
0x1800342d1  mov     eax, [rdi+1Ch]
0x1800342d4  mov     [rsp+0F0h+var_C0], eax
0x1800342d8  mov     eax, [rdi+18h]
0x1800342db  mov     [rsp+0F0h+var_C8], eax
0x1800342df  mov     eax, [rbp+3Fh+arg_20]
0x1800342e2  mov     [rsp+0F0h+var_D0], eax
0x1800342e6  call    ?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z; CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)
0x1800342eb  mov     ebx, eax
0x1800342ed  test    eax, eax
0x1800342ef  js      short loc_180034305
0x1800342f1  mov     rax, [rbp+3Fh+arg_38]
0x1800342f8  cmp     [rax], r14d
0x1800342fb  jz      short loc_180034349
0x1800342fd  test    r15d, r15d
0x180034300  jz      short loc_18003434E
0x180034302  xor     r14d, r14d
0x180034305  lea     rcx, [rbp+3Fh+pvar]; pvar
0x180034309  call    cs:__imp_PropVariantClear
0x18003430f  inc     esi
0x180034311  test    ebx, ebx
0x180034313  jns     loc_180034238
0x180034319  mov     rcx, [rbp+3Fh+var_60]
0x18003431d  mov     rax, [rcx]
0x180034320  mov     rax, [rax+10h]
0x180034324  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180034329  mov     rcx, [rbp+3Fh+pv]; pv
0x18003432d  call    cs:__imp_CoTaskMemFree
0x180034333  mov     eax, ebx
0x180034335  add     rsp, 0B8h
0x18003433c  pop     r15
0x18003433e  pop     r14
0x180034340  pop     r13
0x180034342  pop     r12
0x180034344  pop     rdi
0x180034345  pop     rsi
0x180034346  pop     rbx
0x180034347  pop     rbp
0x180034348  retn
0x180034349  test    r15d, r15d
0x18003434c  jz      short loc_180034302
0x18003434e  mov     r14d, 1
0x180034354  jmp     short loc_180034305
```
