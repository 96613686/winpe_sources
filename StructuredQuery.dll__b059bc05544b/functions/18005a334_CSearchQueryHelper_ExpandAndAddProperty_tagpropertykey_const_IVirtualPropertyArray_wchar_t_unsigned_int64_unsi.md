# CSearchQueryHelper::_ExpandAndAddProperty(_tagpropertykey const &,IVirtualPropertyArray *,wchar_t * *,unsigned __int64,unsigned __int64 *)

- ea: `0x18005a334`
- end: `0x18005a479`
- name: `?_ExpandAndAddProperty@CSearchQueryHelper@@AEAAJAEBU_tagpropertykey@@PEAUIVirtualPropertyArray@@PEAPEA_W_KPEA_K@Z`
- size: `325`
- prototype: `__int64 __fastcall(CSearchQueryHelper *__hidden this, const struct _tagpropertykey *, struct IVirtualPropertyArray *, wchar_t **, unsigned __int64, unsigned __int64 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18005a248`
- `0x18005a334`

## callees

- `0x180010904`
- `0x180015a40`
- `0x18005a334`
- `0x18008b010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005a410`
- `api-ms-win-core-string-l1-1-0!CompareStringW` at `0x18005a410`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a460`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18005a460`

## pseudocode

```c
__int64 __fastcall CSearchQueryHelper::_ExpandAndAddProperty(
        CSearchQueryHelper *this,
        struct _tagpropertykey *a2,
        struct IVirtualPropertyArray *a3,
        wchar_t **a4,
        unsigned __int64 a5,
        unsigned __int64 *a6)
{
  __int64 (__fastcall *v9)(struct IVirtualPropertyArray *, struct _tagpropertykey *, struct _tagpropertykey **, unsigned int *); // rax
  int ConditionPropertyNameFromKey; // ebx
  wchar_t **v12; // r8
  unsigned __int64 v13; // r14
  unsigned int v14; // edi
  unsigned __int64 *v15; // rsi
  int v16; // eax
  WCHAR *v17; // rcx
  __int64 v18; // rdx
  __int64 v19; // rcx
  unsigned __int64 *v20; // rdi
  PCNZWCH *v21; // rsi
  const WCHAR *v22; // r14
  wchar_t **v23; // r12
  unsigned __int64 v24; // rcx
  struct _tagpropertykey *v26; // [rsp+30h] [rbp-18h] BYREF
  PCNZWCH lpString1[2]; // [rsp+38h] [rbp-10h] BYREF
  unsigned int v28; // [rsp+A0h] [rbp+58h] BYREF

  v9 = *(__int64 (__fastcall **)(struct IVirtualPropertyArray *, struct _tagpropertykey *, struct _tagpropertykey **, unsigned int *))(*(_QWORD *)a3 + 40LL);
  v26 = 0;
  v28 = 0;
  ConditionPropertyNameFromKey = v9(a3, a2, &v26, &v28);
  if ( ConditionPropertyNameFromKey >= 0 )
  {
    v13 = a5;
    v14 = 0;
    v15 = a6;
    do
    {
      if ( v14 >= v28 )
        break;
      v16 = CSearchQueryHelper::_ExpandAndAddProperty(this, &v26[v14++], a3, a4, v13, v15);
      ConditionPropertyNameFromKey = v16;
    }
    while ( v16 >= 0 );
    v17 = (WCHAR *)v26;
LABEL_16:
    CoTaskMemFree(v17);
    return (unsigned int)ConditionPropertyNameFromKey;
  }
  lpString1[0] = 0;
  ConditionPropertyNameFromKey = StructuredQuery1::GetConditionPropertyNameFromKey(
                                   a2,
                                   (const struct _tagpropertykey *)lpString1,
                                   v12);
  if ( ConditionPropertyNameFromKey >= 0 )
  {
    v20 = a6;
    v21 = (PCNZWCH *)a4;
    v22 = lpString1[0];
    v23 = &a4[*a6];
    while ( v21 < (PCNZWCH *)v23 )
    {
      if ( CompareStringW(0x7Fu, 1u, v22, -1, *v21, -1) == 2 )
        goto LABEL_15;
      ++v21;
    }
    if ( *v20 >= a5 )
    {
      ConditionPropertyNameFromKey = -2147024774;
    }
    else
    {
      lpString1[0] = 0;
      ConditionPropertyNameFromKey = _AllocString<CTCoAllocPolicy>(v19, v18, (const size_t *)v22, lpString1);
      if ( ConditionPropertyNameFromKey >= 0 )
      {
        v24 = *v20;
        a4[v24] = (wchar_t *)lpString1[0];
        *v20 = v24 + 1;
      }
    }
LABEL_15:
    v17 = (WCHAR *)v22;
    goto LABEL_16;
  }
  return (unsigned int)ConditionPropertyNameFromKey;
}

```

## disassembly

```asm
0x18005a334  push    rbp
0x18005a336  push    rbx
0x18005a337  push    rsi
0x18005a338  push    rdi
0x18005a339  push    r12
0x18005a33b  push    r13
0x18005a33d  push    r14
0x18005a33f  push    r15
0x18005a341  mov     rbp, rsp
0x18005a344  sub     rsp, 48h
0x18005a348  mov     rax, [r8]
0x18005a34b  mov     r12, r8
0x18005a34e  mov     r15, r9
0x18005a351  lea     r8, [rbp+var_18]
0x18005a355  mov     r13, rcx
0x18005a358  lea     r9, [rbp+arg_10]
0x18005a35c  xor     esi, esi
0x18005a35e  mov     rcx, r12
0x18005a361  mov     rax, [rax+28h]
0x18005a365  mov     rdi, rdx
0x18005a368  mov     [rbp+var_18], rsi
0x18005a36c  mov     [rbp+arg_10], esi
0x18005a36f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005a374  mov     ebx, eax
0x18005a376  test    eax, eax
0x18005a378  js      short loc_18005A3C0
0x18005a37a  mov     r14, [rbp+arg_20]
0x18005a37e  mov     edi, esi
0x18005a380  mov     rsi, [rbp+arg_28]
0x18005a384  cmp     edi, [rbp+arg_10]
0x18005a387  jnb     short loc_18005A3B7
0x18005a389  mov     eax, edi
0x18005a38b  mov     r9, r15; wchar_t **
0x18005a38e  mov     qword ptr [rsp+48h+cchCount2], rsi; unsigned __int64 *
0x18005a393  mov     r8, r12; struct IVirtualPropertyArray *
0x18005a396  mov     [rsp+48h+lpString2], r14; unsigned __int64
0x18005a39b  lea     rcx, [rax+rax*4]
0x18005a39f  mov     rax, [rbp+var_18]
0x18005a3a3  lea     rdx, [rax+rcx*4]; struct _tagpropertykey *
0x18005a3a7  mov     rcx, r13; this
0x18005a3aa  call    ?_ExpandAndAddProperty@CSearchQueryHelper@@AEAAJAEBU_tagpropertykey@@PEAUIVirtualPropertyArray@@PEAPEA_W_KPEA_K@Z; CSearchQueryHelper::_ExpandAndAddProperty(_tagpropertykey const &,IVirtualPropertyArray *,wchar_t * *,unsigned __int64,unsigned __int64 *)
0x18005a3af  inc     edi
0x18005a3b1  mov     ebx, eax
0x18005a3b3  test    eax, eax
0x18005a3b5  jns     short loc_18005A384
0x18005a3b7  mov     rcx, [rbp+var_18]
0x18005a3bb  jmp     loc_18005A460
0x18005a3c0  lea     rdx, [rbp+lpString1]; struct _tagpropertykey *
0x18005a3c4  mov     [rbp+lpString1], rsi
0x18005a3c8  mov     rcx, rdi; propkey
0x18005a3cb  call    ?GetConditionPropertyNameFromKey@StructuredQuery1@@YAJAEBU_tagpropertykey@@PEAPEA_W@Z; StructuredQuery1::GetConditionPropertyNameFromKey(_tagpropertykey const &,wchar_t * *)
0x18005a3d0  mov     ebx, eax
0x18005a3d2  test    eax, eax
0x18005a3d4  js      loc_18005A466
0x18005a3da  mov     rdi, [rbp+arg_28]
0x18005a3de  mov     rsi, r15
0x18005a3e1  mov     r14, [rbp+lpString1]
0x18005a3e5  or      r13d, 0FFFFFFFFh
0x18005a3e9  mov     rax, [rdi]
0x18005a3ec  lea     r12, [r15+rax*8]
0x18005a3f0  cmp     rsi, r12
0x18005a3f3  jnb     short loc_18005A421
0x18005a3f5  mov     rax, [rsi]
0x18005a3f8  mov     edx, 1; dwCmpFlags
0x18005a3fd  mov     [rsp+48h+cchCount2], r13d; cchCount2
0x18005a402  mov     r9d, r13d; cchCount1
0x18005a405  mov     r8, r14; lpString1
0x18005a408  mov     [rsp+48h+lpString2], rax; lpString2
0x18005a40d  lea     ecx, [rdx+7Eh]; Locale
0x18005a410  call    cs:__imp_CompareStringW
0x18005a416  cmp     eax, 2
0x18005a419  jz      short loc_18005A45D
0x18005a41b  add     rsi, 8
0x18005a41f  jmp     short loc_18005A3F0
0x18005a421  mov     rax, [rbp+arg_20]
0x18005a425  cmp     [rdi], rax
0x18005a428  jnb     short loc_18005A458
0x18005a42a  lea     r9, [rbp+lpString1]
0x18005a42e  mov     [rbp+lpString1], 0
0x18005a436  mov     r8, r14
0x18005a439  call    ??$_AllocString@VCTCoAllocPolicy@@@@YAJPEAXKPEB_WPEAPEA_W@Z; _AllocString<CTCoAllocPolicy>(void *,ulong,wchar_t const *,wchar_t * *)
0x18005a43e  mov     ebx, eax
0x18005a440  test    eax, eax
0x18005a442  js      short loc_18005A45D
0x18005a444  mov     rcx, [rdi]
0x18005a447  mov     rax, [rbp+lpString1]
0x18005a44b  mov     [r15+rcx*8], rax
0x18005a44f  lea     rax, [rcx+1]
0x18005a453  mov     [rdi], rax
0x18005a456  jmp     short loc_18005A45D
0x18005a458  mov     ebx, 8007007Ah
0x18005a45d  mov     rcx, r14; pv
0x18005a460  call    cs:__imp_CoTaskMemFree
0x18005a466  mov     eax, ebx
0x18005a468  add     rsp, 48h
0x18005a46c  pop     r15
0x18005a46e  pop     r14
0x18005a470  pop     r13
0x18005a472  pop     r12
0x18005a474  pop     rdi
0x18005a475  pop     rsi
0x18005a476  pop     rbx
0x18005a477  pop     rbp
0x18005a478  retn
```
