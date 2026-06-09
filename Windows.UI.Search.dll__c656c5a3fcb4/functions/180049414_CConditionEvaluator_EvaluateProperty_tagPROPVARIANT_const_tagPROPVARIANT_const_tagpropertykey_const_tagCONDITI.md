# CConditionEvaluator::_EvaluateProperty(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,ICondition *,int,int *,int *)

- ea: `0x180049414`
- end: `0x1800496ae`
- name: `?_EvaluateProperty@CConditionEvaluator@@AEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@PEAUICondition@@HPEAH4@Z`
- size: `666`
- prototype: `__int64 __usercall@<rax>(CConditionEvaluator *__hidden this@<rcx>, const struct tagPROPVARIANT *@<rdx>, const struct tagPROPVARIANT *@<r8>, const struct _tagpropertykey *@<r9>, enum tagCONDITION_OPERATION, struct ICondition *, int, int *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004b4c0`

## callees

- `0x180044538`
- `0x180045360`
- `0x1800475b8`
- `0x180049414`
- `0x1800498b0`
- `0x180075f20`
- `0x18007b010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049685`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180049685`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049661`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x180049661`
- `PROPSYS!PropVariantGetElementCount` at `0x1800494a8`
- `PROPSYS!PropVariantGetElementCount` at `0x1800494a8`

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
  signed int v18; // esi
  int *v19; // rcx
  unsigned int v21; // [rsp+80h] [rbp-31h] BYREF
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
0x180049414  mov     [rsp-8+arg_8], rdx
0x180049419  push    rbp
0x18004941a  push    rbx
0x18004941b  push    rsi
0x18004941c  push    rdi
0x18004941d  push    r12
0x18004941f  push    r13
0x180049421  push    r14
0x180049423  push    r15
0x180049425  lea     rbp, [rsp-7]
0x18004942a  sub     rsp, 0B8h
0x180049431  mov     r14, [rbp+3Fh+arg_28]
0x180049435  mov     rsi, r8
0x180049438  mov     r15d, [rbp+3Fh+arg_20]
0x18004943c  lea     r8, [rbp+3Fh+var_70]; enum BITSSET *
0x180049440  mov     rdi, rcx
0x180049443  mov     [rbp+3Fh+var_70], 0
0x18004944a  mov     rcx, r14; struct ICondition *
0x18004944d  mov     edx, r15d; enum tagCONDITION_OPERATION
0x180049450  mov     r13, r9
0x180049453  call    ?IsConditionBitwiseOperation@@YAJPEAUICondition@@W4tagCONDITION_OPERATION@@PEAW4BITSSET@@@Z; IsConditionBitwiseOperation(ICondition *,tagCONDITION_OPERATION,BITSSET *)
0x180049458  mov     ebx, eax
0x18004945a  test    eax, eax
0x18004945c  js      loc_18004968B
0x180049462  lea     rdx, [rbp+3Fh+var_6C]
0x180049466  mov     [rbp+3Fh+var_6C], 0
0x18004946d  mov     rcx, r14
0x180049470  call    GetLocaleFromCondition
0x180049475  test    eax, eax
0x180049477  jns     short loc_180049486
0x180049479  mov     rcx, rdi; this
0x18004947c  call    ?_GetInputLocale@CConditionEvaluator@@IEAAKXZ; CConditionEvaluator::_GetInputLocale(void)
0x180049481  mov     r12d, eax
0x180049484  jmp     short loc_18004948A
0x180049486  mov     r12d, [rbp+3Fh+var_6C]
0x18004948a  mov     rax, [r14]
0x18004948d  lea     rdx, [rbp+3Fh+pv]
0x180049491  mov     rcx, r14
0x180049494  mov     [rbp+3Fh+pv], 0
0x18004949c  mov     rax, [rax+58h]
0x1800494a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800494a5  mov     rcx, rsi; propvar
0x1800494a8  call    cs:__imp_PropVariantGetElementCount
0x1800494ae  test    eax, eax
0x1800494b0  jnz     short loc_1800494C5
0x1800494b2  xorps   xmm0, xmm0
0x1800494b5  lea     r8, [rbp+3Fh+pvar]
0x1800494b9  xor     eax, eax
0x1800494bb  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x1800494bf  mov     [rbp+3Fh+var_48], rax
0x1800494c3  jmp     short loc_1800494D2
0x1800494c5  mov     eax, 3000h
0x1800494ca  test    [rsi], ax
0x1800494cd  jnz     short loc_180049541
0x1800494cf  mov     r8, rsi
0x1800494d2  mov     rax, [rbp+3Fh+arg_40]
0x1800494d9  mov     r9, r13
0x1800494dc  mov     rdx, [rbp+3Fh+arg_8]
0x1800494e0  mov     rcx, rdi
0x1800494e3  mov     [rsp+0F0h+var_80], rax
0x1800494e8  mov     rax, [rbp+3Fh+arg_38]
0x1800494ef  mov     [rsp+0F0h+var_88], rax
0x1800494f4  mov     rax, [rbp+3Fh+pv]
0x1800494f8  mov     [rsp+0F0h+var_90], r12d
0x1800494fd  mov     [rsp+0F0h+var_98], rax
0x180049502  mov     eax, [rbp+3Fh+var_70]
0x180049505  mov     [rsp+0F0h+var_A0], eax
0x180049509  mov     rax, [rdi+30h]
0x18004950d  mov     [rsp+0F0h+var_A8], rax
0x180049512  mov     eax, [rbp+3Fh+arg_30]
0x180049515  mov     [rsp+0F0h+var_B0], eax
0x180049519  mov     rax, [rdi+20h]
0x18004951d  mov     [rsp+0F0h+var_B8], rax
0x180049522  mov     eax, [rdi+1Ch]
0x180049525  mov     [rsp+0F0h+var_C0], eax
0x180049529  mov     eax, [rdi+18h]
0x18004952c  mov     [rsp+0F0h+var_C8], eax
0x180049530  mov     [rsp+0F0h+var_D0], r15d
0x180049535  call    ?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z; CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)
0x18004953a  mov     ebx, eax
0x18004953c  jmp     loc_180049681
0x180049541  lea     r9, [rbp+3Fh+var_60]; void **
0x180049545  mov     [rbp+3Fh+var_60], 0
0x18004954d  mov     rdx, r13; struct _tagpropertykey *
0x180049550  mov     rcx, rsi; struct tagPROPVARIANT *
0x180049553  call    ?CMultipleValues_CreateInstance@@YAJPEBUtagPROPVARIANT@@AEBU_tagpropertykey@@AEBU_GUID@@PEAPEAX@Z; CMultipleValues_CreateInstance(tagPROPVARIANT const *,_tagpropertykey const &,_GUID const &,void * *)
0x180049558  mov     ebx, eax
0x18004955a  test    eax, eax
0x18004955c  js      loc_180049681
0x180049562  mov     rcx, [rbp+3Fh+var_60]
0x180049566  lea     rdx, [rbp+3Fh+var_6C]
0x18004956a  mov     [rbp+3Fh+var_6C], 0
0x180049571  mov     rax, [rcx]
0x180049574  mov     rax, [rax+60h]
0x180049578  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004957d  mov     ebx, eax
0x18004957f  test    eax, eax
0x180049581  js      loc_180049671
0x180049587  mov     r15d, [rbp+3Fh+arg_30]
0x18004958b  xor     r14d, r14d
0x18004958e  xor     esi, esi
0x180049590  test    r14d, r14d
0x180049593  jnz     loc_180049671
0x180049599  cmp     esi, [rbp+3Fh+var_6C]
0x18004959c  jge     loc_180049671
0x1800495a2  mov     rcx, [rbp+3Fh+var_60]
0x1800495a6  lea     r8, [rbp+3Fh+pvar]
0x1800495aa  xor     eax, eax
0x1800495ac  xorps   xmm0, xmm0
0x1800495af  mov     [rbp+3Fh+var_48], rax
0x1800495b3  mov     edx, esi
0x1800495b5  movups  xmmword ptr [rbp+3Fh+pvar], xmm0
0x1800495b9  mov     rax, [rcx]
0x1800495bc  mov     rax, [rax+58h]
0x1800495c0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800495c5  mov     ebx, eax
0x1800495c7  test    eax, eax
0x1800495c9  js      loc_180049667
0x1800495cf  mov     rcx, [rbp+3Fh+arg_40]
0x1800495d6  lea     r8, [rbp+3Fh+pvar]
0x1800495da  mov     rdx, [rbp+3Fh+arg_8]
0x1800495de  xor     eax, eax
0x1800495e0  test    esi, esi
0x1800495e2  mov     r9, r13
0x1800495e5  cmovnz  rcx, rax
0x1800495e9  mov     rax, [rbp+3Fh+arg_38]
0x1800495f0  mov     [rsp+0F0h+var_80], rcx
0x1800495f5  mov     rcx, rdi
0x1800495f8  mov     [rsp+0F0h+var_88], rax
0x1800495fd  mov     rax, [rbp+3Fh+pv]
0x180049601  mov     [rsp+0F0h+var_90], r12d
0x180049606  mov     [rsp+0F0h+var_98], rax
0x18004960b  mov     eax, [rbp+3Fh+var_70]
0x18004960e  mov     [rsp+0F0h+var_A0], eax
0x180049612  mov     rax, [rdi+30h]
0x180049616  mov     [rsp+0F0h+var_A8], rax
0x18004961b  mov     rax, [rdi+20h]
0x18004961f  mov     [rsp+0F0h+var_B0], r15d
0x180049624  mov     [rsp+0F0h+var_B8], rax
0x180049629  mov     eax, [rdi+1Ch]
0x18004962c  mov     [rsp+0F0h+var_C0], eax
0x180049630  mov     eax, [rdi+18h]
0x180049633  mov     [rsp+0F0h+var_C8], eax
0x180049637  mov     eax, [rbp+3Fh+arg_20]
0x18004963a  mov     [rsp+0F0h+var_D0], eax
0x18004963e  call    ?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z; CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)
0x180049643  mov     ebx, eax
0x180049645  test    eax, eax
0x180049647  js      short loc_18004965D
0x180049649  mov     rax, [rbp+3Fh+arg_38]
0x180049650  cmp     [rax], r14d
0x180049653  jz      short loc_1800496A1
0x180049655  test    r15d, r15d
0x180049658  jz      short loc_1800496A6
0x18004965a  xor     r14d, r14d
0x18004965d  lea     rcx, [rbp+3Fh+pvar]; pvar
0x180049661  call    cs:__imp_PropVariantClear
0x180049667  inc     esi
0x180049669  test    ebx, ebx
0x18004966b  jns     loc_180049590
0x180049671  mov     rcx, [rbp+3Fh+var_60]
0x180049675  mov     rax, [rcx]
0x180049678  mov     rax, [rax+10h]
0x18004967c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180049681  mov     rcx, [rbp+3Fh+pv]; pv
0x180049685  call    cs:__imp_CoTaskMemFree
0x18004968b  mov     eax, ebx
0x18004968d  add     rsp, 0B8h
0x180049694  pop     r15
0x180049696  pop     r14
0x180049698  pop     r13
0x18004969a  pop     r12
0x18004969c  pop     rdi
0x18004969d  pop     rsi
0x18004969e  pop     rbx
0x18004969f  pop     rbp
0x1800496a0  retn
0x1800496a1  test    r15d, r15d
0x1800496a4  jz      short loc_18004965A
0x1800496a6  mov     r14d, 1
0x1800496ac  jmp     short loc_18004965D
```
