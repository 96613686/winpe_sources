# CQueryResult::_ComparePropertyValues(_tagpropertykey const &,tagPROPVARIANT const &,tagPROPVARIANT const &,QR_CMP_FLAGS,int *)

- ea: `0x180038560`
- end: `0x18003868e`
- name: `?_ComparePropertyValues@CQueryResult@@AEAAJAEBU_tagpropertykey@@AEBUtagPROPVARIANT@@1W4QR_CMP_FLAGS@@PEAH@Z`
- size: `302`
- prototype: `int __high(const struct _tagpropertykey *, const struct tagPROPVARIANT *, const struct tagPROPVARIANT *, enum QR_CMP_FLAGS, int *)`
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x180036f14`

## callees

- `0x180038560`
- `0x180038694`
- `0x180063a68`

## import_xrefs

- `Windows.Storage!__imp_SHRestricted` at `0x180038597`
- `Windows.Storage!__imp_SHRestricted` at `0x180038597`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003864e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003865c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003864e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18003865c`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x18003860a`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180038629`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x18003860a`
- `PROPSYS!PSFormatForDisplayAlloc` at `0x180038629`
- `PROPSYS!PropVariantCompareEx` at `0x1800385b7`
- `PROPSYS!PropVariantCompareEx` at `0x1800385b7`

## pseudocode

```c
__int64 __fastcall CQueryResult::_ComparePropertyValues(
        WCHAR *a1,
        const PROPERTYKEY *a2,
        const PROPVARIANT *a3,
        const PROPVARIANT *a4,
        char a5,
        PWSTR ppszDisplay)
{
  PWSTR v6; // rdi
  bool v7; // zf
  DWORD v11; // eax
  PROPVAR_COMPARE_FLAGS v12; // r9d
  __int64 v14; // rax
  HRESULT v15; // ebx
  int v16; // eax
  PWSTR v17; // rcx
  int v18; // [rsp+20h] [rbp-38h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  PWSTR v20; // [rsp+60h] [rbp+8h] BYREF

  v20 = a1;
  v6 = ppszDisplay;
  v7 = (a5 & 1) == 0;
  *(_DWORD *)ppszDisplay = 0;
  if ( v7 || a2->pid != 100 )
    goto LABEL_2;
  v14 = *(_QWORD *)&a2->fmtid.Data1 - *(_QWORD *)&PKEY_ItemSearchLocation.fmtid.Data1;
  if ( *(_QWORD *)&a2->fmtid.Data1 == *(_QWORD *)&PKEY_ItemSearchLocation.fmtid.Data1 )
    v14 = *(_QWORD *)a2->fmtid.Data4 - *(_QWORD *)PKEY_ItemSearchLocation.fmtid.Data4;
  if ( v14 )
  {
LABEL_2:
    v11 = SHRestricted(REST_NOSTRCMPLOGICAL);
    v12 = 9;
    if ( !v11 )
      v12 = 1;
    *(_DWORD *)v6 = PropVariantCompareEx(a3, a4, PVCU_DEFAULT, v12);
    return 0;
  }
  else
  {
    ppszDisplay = 0;
    v15 = PSFormatForDisplayAlloc(a2, a3, PDFF_DEFAULT, &ppszDisplay);
    if ( v15 < 0 )
      goto LABEL_13;
    v20 = 0;
    v15 = PSFormatForDisplayAlloc(a2, a4, PDFF_DEFAULT, &v20);
    if ( v15 >= 0 )
    {
      v16 = StrCmpLogicalRestricted(ppszDisplay, v20);
      v17 = v20;
      *(_DWORD *)v6 = v16;
      CoTaskMemFree(v17);
    }
    CoTaskMemFree(ppszDisplay);
    if ( v15 < 0 )
LABEL_13:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x538,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
        (const char *)(unsigned int)v15,
        v18);
    return (unsigned int)v15;
  }
}

```

## disassembly

```asm
0x180038560  mov     [rsp+arg_0], rcx
0x180038565  push    rbx
0x180038566  push    rbp
0x180038567  push    rsi
0x180038568  push    rdi
0x180038569  push    r14
0x18003856b  push    r15
0x18003856d  sub     rsp, 28h
0x180038571  mov     rdi, [rsp+58h+ppszDisplay]
0x180038579  xor     r15d, r15d
0x18003857c  test    [rsp+58h+arg_20], 1
0x180038584  mov     r14, r9
0x180038587  mov     rbp, r8
0x18003858a  mov     rsi, rdx
0x18003858d  mov     [rdi], r15d
0x180038590  jnz     short loc_1800385CF
0x180038592  mov     ecx, 4000007Eh; rest
0x180038597  call    cs:__imp_SHRestricted
0x18003859d  mov     ecx, 1
0x1800385a2  mov     r9d, 9
0x1800385a8  test    eax, eax
0x1800385aa  mov     rdx, r14; propvar2
0x1800385ad  cmovz   r9d, ecx; flags
0x1800385b1  xor     r8d, r8d; unit
0x1800385b4  mov     rcx, rbp; propvar1
0x1800385b7  call    cs:__imp_PropVariantCompareEx
0x1800385bd  mov     [rdi], eax
0x1800385bf  mov     eax, r15d
0x1800385c2  add     rsp, 28h
0x1800385c6  pop     r15
0x1800385c8  pop     r14
0x1800385ca  pop     rdi
0x1800385cb  pop     rsi
0x1800385cc  pop     rbp
0x1800385cd  pop     rbx
0x1800385ce  retn
0x1800385cf  cmp     dword ptr [rdx+10h], 64h ; 'd'
0x1800385d3  jnz     short loc_180038592
0x1800385d5  mov     rax, [rdx]
0x1800385d8  sub     rax, qword ptr cs:PKEY_ItemSearchLocation.fmtid.Data1
0x1800385df  jnz     short loc_1800385EC
0x1800385e1  mov     rax, [rdx+8]
0x1800385e5  sub     rax, qword ptr cs:PKEY_ItemSearchLocation.fmtid.Data4
0x1800385ec  test    rax, rax
0x1800385ef  jnz     short loc_180038592
0x1800385f1  lea     r9, [rsp+58h+ppszDisplay]; ppszDisplay
0x1800385f9  mov     [rsp+58h+ppszDisplay], r15
0x180038601  xor     r8d, r8d; pdff
0x180038604  mov     rdx, rbp; propvar
0x180038607  mov     rcx, rsi; key
0x18003860a  call    cs:__imp_PSFormatForDisplayAlloc
0x180038610  mov     ebx, eax
0x180038612  test    eax, eax
0x180038614  js      short loc_180038666
0x180038616  lea     r9, [rsp+58h+arg_0]; ppszDisplay
0x18003861b  mov     [rsp+58h+arg_0], r15
0x180038620  xor     r8d, r8d; pdff
0x180038623  mov     rdx, r14; propvar
0x180038626  mov     rcx, rsi; key
0x180038629  call    cs:__imp_PSFormatForDisplayAlloc
0x18003862f  mov     ebx, eax
0x180038631  test    eax, eax
0x180038633  js      short loc_180038654
0x180038635  mov     rdx, [rsp+58h+arg_0]; psz2
0x18003863a  mov     rcx, [rsp+58h+ppszDisplay]; psz1
0x180038642  call    ?StrCmpLogicalRestricted@@YAHPEBG0@Z; StrCmpLogicalRestricted(ushort const *,ushort const *)
0x180038647  mov     rcx, [rsp+58h+arg_0]; pv
0x18003864c  mov     [rdi], eax
0x18003864e  call    cs:__imp_CoTaskMemFree
0x180038654  mov     rcx, [rsp+58h+ppszDisplay]; pv
0x18003865c  call    cs:__imp_CoTaskMemFree
0x180038662  test    ebx, ebx
0x180038664  jns     short loc_18003867F
0x180038666  mov     rcx, [rsp+58h]; this
0x18003866b  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x180038672  mov     r9d, ebx; char *
0x180038675  mov     edx, 538h; void *
0x18003867a  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18003867f  mov     eax, ebx
0x180038681  add     rsp, 28h
0x180038685  pop     r15
0x180038687  pop     r14
0x180038689  pop     rdi
0x18003868a  pop     rsi
0x18003868b  pop     rbp
0x18003868c  pop     rbx
0x18003868d  retn
```
