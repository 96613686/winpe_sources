# CConditionEvaluator::FilterConditionCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,_tagpropertykey const &,tagCONDITION_OPERATION,int,int,IPropertyInfoProvider *,int,IPropertyChangeArray *,BITSSET,ushort *,ulong,int *,int *)

- ea: `0x18002a61c`
- end: `0x18002a81d`
- name: `?FilterConditionCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0AEBU_tagpropertykey@@W4tagCONDITION_OPERATION@@HHPEAUIPropertyInfoProvider@@HPEAUIPropertyChangeArray@@W4BITSSET@@PEAGKPEAH7@Z`
- size: `513`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD, _DWORD, _DWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _DWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `7`
- tags: `broker_com_uri`

## callers

- `0x18002a290`
- `0x1800340bc`

## callees

- `0x180029068`
- `0x18002a61c`
- `0x18002bc58`
- `0x18002e5cc`
- `0x1800308b8`
- `0x180038428`
- `0x180051010`

## import_xrefs

- `SHLWAPI!__imp_StrCmpICW` at `0x18002a6bb`
- `SHLWAPI!__imp_StrCmpICW` at `0x18002a6bb`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x18002a7ce`
- `PROPSYS!PSCreateSimplePropertyChange` at `0x18002a7ce`

## pseudocode

```c
__int64 __fastcall CConditionEvaluator::FilterConditionCompareValues(
        CConditionEvaluator *a1,
        PROPVARIANT *a2,
        PROPVARIANT *a3,
        struct _tagpropertykey *a4,
        enum tagCONDITION_OPERATION a5,
        int a6,
        int a7,
        struct IPropertyInfoProvider *a8,
        unsigned int a9,
        __int64 a10,
        unsigned int a11,
        const WCHAR *pszStr1,
        LCID Locale,
        int *a14,
        _DWORD *a15)
{
  HRESULT v18; // ebx
  PKA_FLAGS v20; // edi
  void *ppv; // [rsp+60h] [rbp-48h] BYREF

  if ( a5 == COP_IMPLICIT )
    return 1;
  if ( (unsigned int)(a5 - 7) <= 6 )
    return (unsigned int)CConditionEvaluator::LikeOpCompareValues(a1, a2, a3, a5, a4, a6, a7, a8, a9, Locale, a14);
  if ( pszStr1 && !StrCmpICW(pszStr1, L"System.StructuredQueryType.SortKeyDescription") )
    return (unsigned int)SortKeyCompareValues(
                           (const struct tagPROPVARIANT *)a2,
                           (const struct tagPROPVARIANT *)a3,
                           a5,
                           a9,
                           a14);
  if ( a11 )
    return (unsigned int)BitwiseCompareValues(a2, a3, a11, a9, a14);
  v18 = _SimpleOpCompareValues(a2, a3, a5, a9, a14);
  if ( v18 >= 0 && !*a14 && a15 && a10 && (GetPropertyTypeFlags(a4, PDTF_ISINNATE) & 2) == 0 )
  {
    v20 = PKA_APPEND;
    if ( a9 )
    {
      if ( a5 != COP_NOTEQUAL )
        return (unsigned int)v18;
    }
    else if ( a5 != COP_EQUAL )
    {
      return (unsigned int)v18;
    }
    ppv = 0;
    if ( (GetPropertyTypeFlags(a4, PDTF_MULTIPLEVALUES) & 1) == 0 || !*(_WORD *)a2 )
      v20 = PKA_SET;
    v18 = PSCreateSimplePropertyChange(v20, a4, a2, &GUID_f917bc8a_1bba_4478_a245_1bde03eb9431, &ppv);
    if ( v18 >= 0 )
    {
      v18 = (*(__int64 (__fastcall **)(__int64, void *))(*(_QWORD *)a10 + 48LL))(a10, ppv);
      (*(void (__fastcall **)(void *))(*(_QWORD *)ppv + 16LL))(ppv);
    }
    *a15 = v18 >= 0;
  }
  return (unsigned int)v18;
}

```

## disassembly

```asm
0x18002a61c  push    rbx
0x18002a61e  push    rbp
0x18002a61f  push    rsi
0x18002a620  push    rdi
0x18002a621  push    r12
0x18002a623  push    r14
0x18002a625  push    r15
0x18002a627  sub     rsp, 70h
0x18002a62b  mov     esi, [rsp+0A8h+arg_20]
0x18002a632  xor     r12d, r12d
0x18002a635  mov     r15, r9
0x18002a638  mov     rbx, r8
0x18002a63b  mov     rbp, rdx
0x18002a63e  test    esi, esi
0x18002a640  jnz     short loc_18002A64A
0x18002a642  lea     ebx, [rsi+1]
0x18002a645  jmp     loc_18002A80C
0x18002a64a  lea     eax, [rsi-7]
0x18002a64d  cmp     eax, 6
0x18002a650  ja      short loc_18002A6A7
0x18002a652  mov     rax, [rsp+0A8h+arg_68]
0x18002a65a  mov     r9d, esi; enum tagCONDITION_OPERATION
0x18002a65d  mov     [rsp+0A8h+var_58], rax; int *
0x18002a662  mov     eax, [rsp+0A8h+arg_60]
0x18002a669  mov     [rsp+0A8h+Locale], eax; Locale
0x18002a66d  mov     eax, [rsp+0A8h+arg_40]
0x18002a674  mov     [rsp+0A8h+var_68], eax; int
0x18002a678  mov     rax, [rsp+0A8h+arg_38]
0x18002a680  mov     [rsp+0A8h+var_70], rax; struct IPropertyInfoProvider *
0x18002a685  mov     eax, [rsp+0A8h+arg_30]
0x18002a68c  mov     [rsp+0A8h+var_78], eax; int
0x18002a690  mov     eax, [rsp+0A8h+arg_28]
0x18002a697  mov     [rsp+0A8h+var_80], eax; int
0x18002a69b  mov     [rsp+0A8h+ppv], r15; propkey
0x18002a6a0  call    ?LikeOpCompareValues@CConditionEvaluator@@QEAAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@AEBU_tagpropertykey@@HHPEAUIPropertyInfoProvider@@HKPEAH@Z; CConditionEvaluator::LikeOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,_tagpropertykey const &,int,int,IPropertyInfoProvider *,int,ulong,int *)
0x18002a6a5  jmp     short loc_18002A717
0x18002a6a7  mov     rcx, [rsp+0A8h+pszStr1]; pszStr1
0x18002a6af  test    rcx, rcx
0x18002a6b2  jz      short loc_18002A6EA
0x18002a6b4  lea     rdx, pszStr2; "System.StructuredQueryType.SortKeyDescr"...
0x18002a6bb  call    cs:__imp_StrCmpICW
0x18002a6c1  test    eax, eax
0x18002a6c3  jnz     short loc_18002A6EA
0x18002a6c5  mov     rax, [rsp+0A8h+arg_68]
0x18002a6cd  mov     r8d, esi; enum tagCONDITION_OPERATION
0x18002a6d0  mov     r9d, [rsp+0A8h+arg_40]; int
0x18002a6d8  mov     rdx, rbx; struct tagPROPVARIANT *
0x18002a6db  mov     rcx, rbp; struct tagPROPVARIANT *
0x18002a6de  mov     [rsp+0A8h+ppv], rax; int *
0x18002a6e3  call    ?SortKeyCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z; SortKeyCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)
0x18002a6e8  jmp     short loc_18002A717
0x18002a6ea  mov     r8d, [rsp+0A8h+arg_50]
0x18002a6f2  mov     rdx, rbx; propvar1
0x18002a6f5  mov     r9d, [rsp+0A8h+arg_40]; int
0x18002a6fd  mov     rcx, rbp; propvar2
0x18002a700  test    r8d, r8d
0x18002a703  jz      short loc_18002A71E
0x18002a705  mov     rax, [rsp+0A8h+arg_68]
0x18002a70d  mov     [rsp+0A8h+ppv], rax
0x18002a712  call    ?BitwiseCompareValues@@YAJAEBUtagPROPVARIANT@@0W4BITSSET@@HPEAH@Z; BitwiseCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,BITSSET,int,int *)
0x18002a717  mov     ebx, eax
0x18002a719  jmp     loc_18002A80C
0x18002a71e  mov     rdi, [rsp+0A8h+arg_68]
0x18002a726  mov     r8d, esi; enum tagCONDITION_OPERATION
0x18002a729  mov     [rsp+0A8h+ppv], rdi; int *
0x18002a72e  call    ?_SimpleOpCompareValues@@YAJAEBUtagPROPVARIANT@@0W4tagCONDITION_OPERATION@@HPEAH@Z; _SimpleOpCompareValues(tagPROPVARIANT const &,tagPROPVARIANT const &,tagCONDITION_OPERATION,int,int *)
0x18002a733  mov     ebx, eax
0x18002a735  test    eax, eax
0x18002a737  js      loc_18002A80C
0x18002a73d  cmp     [rdi], r12d
0x18002a740  jnz     loc_18002A80C
0x18002a746  mov     r14, [rsp+0A8h+arg_70]
0x18002a74e  test    r14, r14
0x18002a751  jz      loc_18002A80C
0x18002a757  mov     r12, [rsp+0A8h+arg_48]
0x18002a75f  test    r12, r12
0x18002a762  jz      loc_18002A80C
0x18002a768  mov     edx, 2; enum PROPDESC_TYPE_FLAGS
0x18002a76d  mov     rcx, r15; struct _tagpropertykey *
0x18002a770  call    ?GetPropertyTypeFlags@@YA?AW4PROPDESC_TYPE_FLAGS@@AEBU_tagpropertykey@@W41@@Z; GetPropertyTypeFlags(_tagpropertykey const &,PROPDESC_TYPE_FLAGS)
0x18002a775  test    al, 2
0x18002a777  jnz     loc_18002A80C
0x18002a77d  cmp     [rsp+0A8h+arg_40], 0
0x18002a785  mov     edi, 1
0x18002a78a  jz      short loc_18002A793
0x18002a78c  cmp     esi, 2
0x18002a78f  jz      short loc_18002A797
0x18002a791  jmp     short loc_18002A80C
0x18002a793  cmp     esi, edi
0x18002a795  jnz     short loc_18002A80C
0x18002a797  xor     esi, esi
0x18002a799  mov     edx, edi; enum PROPDESC_TYPE_FLAGS
0x18002a79b  mov     rcx, r15; struct _tagpropertykey *
0x18002a79e  mov     [rsp+0A8h+var_48], rsi
0x18002a7a3  call    ?GetPropertyTypeFlags@@YA?AW4PROPDESC_TYPE_FLAGS@@AEBU_tagpropertykey@@W41@@Z; GetPropertyTypeFlags(_tagpropertykey const &,PROPDESC_TYPE_FLAGS)
0x18002a7a8  test    dil, al
0x18002a7ab  jz      short loc_18002A7B3
0x18002a7ad  cmp     [rbp+0], si
0x18002a7b1  jnz     short loc_18002A7B5
0x18002a7b3  mov     edi, esi
0x18002a7b5  lea     rax, [rsp+0A8h+var_48]
0x18002a7ba  mov     r8, rbp; propvar
0x18002a7bd  lea     r9, _GUID_f917bc8a_1bba_4478_a245_1bde03eb9431; riid
0x18002a7c4  mov     [rsp+0A8h+ppv], rax; ppv
0x18002a7c9  mov     rdx, r15; key
0x18002a7cc  mov     ecx, edi; flags
0x18002a7ce  call    cs:__imp_PSCreateSimplePropertyChange
0x18002a7d4  mov     ebx, eax
0x18002a7d6  test    eax, eax
0x18002a7d8  js      short loc_18002A802
0x18002a7da  mov     rax, [r12]
0x18002a7de  mov     rcx, r12
0x18002a7e1  mov     rdx, [rsp+0A8h+var_48]
0x18002a7e6  mov     rax, [rax+30h]
0x18002a7ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a7ef  mov     rcx, [rsp+0A8h+var_48]
0x18002a7f4  mov     ebx, eax
0x18002a7f6  mov     rax, [rcx]
0x18002a7f9  mov     rax, [rax+10h]
0x18002a7fd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002a802  mov     eax, ebx
0x18002a804  not     eax
0x18002a806  shr     eax, 1Fh
0x18002a809  mov     [r14], eax
0x18002a80c  mov     eax, ebx
0x18002a80e  add     rsp, 70h
0x18002a812  pop     r15
0x18002a814  pop     r14
0x18002a816  pop     r12
0x18002a818  pop     rdi
0x18002a819  pop     rsi
0x18002a81a  pop     rbp
0x18002a81b  pop     rbx
0x18002a81c  retn
```
