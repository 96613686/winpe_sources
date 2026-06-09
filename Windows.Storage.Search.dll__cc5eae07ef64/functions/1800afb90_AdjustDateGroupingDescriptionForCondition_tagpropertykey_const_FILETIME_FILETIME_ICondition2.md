# _AdjustDateGroupingDescriptionForCondition(_tagpropertykey const &,_FILETIME *,_FILETIME *,ICondition2 *)

- ea: `0x1800afb90`
- end: `0x1800afde0`
- name: `?_AdjustDateGroupingDescriptionForCondition@@YAJAEBU_tagpropertykey@@PEAU_FILETIME@@1PEAUICondition2@@@Z`
- size: `592`
- prototype: `__int64 __fastcall(const struct _tagpropertykey *, struct _FILETIME *, struct _FILETIME *, struct ICondition2 *)`
- caller_count: `2`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x1800afaa8`
- `0x1800afb90`

## callees

- `0x18003bde0`
- `0x180063a68`
- `0x180071dc0`
- `0x1800afb90`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800afce2`
- `api-ms-win-core-com-l1-1-0!PropVariantClear` at `0x1800afce2`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800afc9c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800afccc`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800afc9c`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x1800afccc`
- `PROPSYS!PropVariantToFileTime` at `0x1800afc6f`
- `PROPSYS!PropVariantToFileTime` at `0x1800afc6f`

## pseudocode

```c
__int64 __fastcall _AdjustDateGroupingDescriptionForCondition(
        const struct _tagpropertykey *a1,
        struct _FILETIME *a2,
        struct _FILETIME *a3,
        struct ICondition2 *a4)
{
  int i; // ebx
  struct ICondition2Vtbl *lpVtbl; // rax
  struct ICondition2Vtbl *v10; // rax
  unsigned int v11; // ecx
  struct ICondition2Vtbl *v12; // rax
  unsigned int v13; // esi
  int v15; // [rsp+20h] [rbp-49h]
  unsigned int v16; // [rsp+30h] [rbp-39h] BYREF
  FILETIME pftOut; // [rsp+38h] [rbp-31h] BYREF
  unsigned int v18; // [rsp+40h] [rbp-29h] BYREF
  struct ICondition2 *v19; // [rsp+48h] [rbp-21h] BYREF
  PROPVARIANT propvar[2]; // [rsp+50h] [rbp-19h] BYREF
  __int64 v21; // [rsp+60h] [rbp-9h]
  __int128 v22; // [rsp+68h] [rbp-1h] BYREF
  int v23; // [rsp+78h] [rbp+Fh]
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+5Fh]

  i = 1;
  if ( a4 )
  {
    lpVtbl = a4->lpVtbl;
    v18 = 0;
    i = ((__int64 (__fastcall *)(struct ICondition2 *, unsigned int *))lpVtbl->GetConditionType)(a4, &v18);
    if ( i < 0 )
      goto LABEL_27;
    if ( v18 < 2 )
    {
      v12 = a4->lpVtbl;
      pftOut = 0;
      i = ((__int64 (__fastcall *)(struct ICondition2 *, GUID *, FILETIME *))v12->GetSubConditions)(
            a4,
            &GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9,
            &pftOut);
      if ( i < 0 )
        goto LABEL_27;
      v16 = 0;
      v13 = 0;
      for ( i = (*(__int64 (__fastcall **)(FILETIME, unsigned int *))(**(_QWORD **)&pftOut + 24LL))(pftOut, &v16);
            i >= 0;
            ++v13 )
      {
        if ( v13 >= v16 )
          break;
        v19 = 0;
        i = (*(__int64 (__fastcall **)(FILETIME, _QWORD, GUID *, struct ICondition2 **))(**(_QWORD **)&pftOut + 32LL))(
              pftOut,
              v13,
              &GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7,
              &v19);
        if ( i >= 0 )
        {
          i = _AdjustDateGroupingDescriptionForCondition(a1, a2, a3, v19);
          ((void (__fastcall *)(struct ICondition2 *))v19->lpVtbl->Release)(v19);
        }
      }
      (*(void (__fastcall **)(FILETIME))(**(_QWORD **)&pftOut + 16LL))(pftOut);
      if ( i < 0 )
        goto LABEL_27;
    }
    else if ( v18 == 3 )
    {
      v23 = 0;
      v16 = 0;
      v21 = 0;
      v10 = a4->lpVtbl;
      v22 = 0;
      *(_OWORD *)propvar = 0;
      i = ((__int64 (__fastcall *)(struct ICondition2 *, __int128 *, unsigned int *, PROPVARIANT *))v10->GetLeafConditionInfo)(
            a4,
            &v22,
            &v16,
            propvar);
      if ( i >= 0 )
      {
        pftOut = 0;
        if ( !(unsigned int)operator==(&v22, a1) || PropVariantToFileTime(propvar, 0, &pftOut) < 0 )
          goto LABEL_19;
        v11 = v16;
        if ( ((v16 - 4) & 0xFFFFFFFD) == 0 )
        {
          if ( !a2->dwLowDateTime && !a2->dwHighDateTime || CompareFileTime(&pftOut, a2) == -1 )
          {
            *a2 = pftOut;
LABEL_19:
            PropVariantClear(propvar);
            return (unsigned int)i;
          }
          v11 = v16;
        }
        if ( ((v11 - 3) & 0xFFFFFFFD) == 0
          && (!a3->dwLowDateTime && !a3->dwHighDateTime || CompareFileTime(&pftOut, a3) == 1) )
        {
          *a3 = pftOut;
        }
        goto LABEL_19;
      }
LABEL_27:
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2775,
        (unsigned int)"onecoreuap\\shell\\windows.storage.search\\resultsetfactory.cpp",
        (const char *)(unsigned int)i,
        v15);
    }
  }
  return (unsigned int)i;
}

```

## disassembly

```asm
0x1800afb90  push    rbp
0x1800afb92  push    rbx
0x1800afb93  push    rsi
0x1800afb94  push    rdi
0x1800afb95  push    r14
0x1800afb97  push    r15
0x1800afb99  lea     rbp, [rsp-2Fh]
0x1800afb9e  sub     rsp, 98h
0x1800afba5  mov     rax, cs:__security_cookie
0x1800afbac  xor     rax, rsp
0x1800afbaf  mov     [rbp+57h+var_40], rax
0x1800afbb3  mov     rsi, r9
0x1800afbb6  mov     rdi, r8
0x1800afbb9  mov     r14, rdx
0x1800afbbc  mov     r15, rcx
0x1800afbbf  mov     ebx, 1
0x1800afbc4  test    r9, r9
0x1800afbc7  jz      loc_1800AFDC2
0x1800afbcd  mov     rax, [r9]
0x1800afbd0  lea     rdx, [rbp+57h+var_80]
0x1800afbd4  mov     rcx, r9
0x1800afbd7  mov     [rbp+57h+var_80], 0
0x1800afbde  mov     rax, [rax+40h]
0x1800afbe2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afbe7  mov     ebx, eax
0x1800afbe9  test    eax, eax
0x1800afbeb  js      loc_1800AFDAA
0x1800afbf1  mov     eax, [rbp+57h+var_80]
0x1800afbf4  test    eax, eax
0x1800afbf6  jz      loc_1800AFCED
0x1800afbfc  sub     eax, 1
0x1800afbff  jz      loc_1800AFCED
0x1800afc05  cmp     eax, 2
0x1800afc08  jnz     loc_1800AFDC2
0x1800afc0e  xor     eax, eax
0x1800afc10  lea     r9, [rbp+57h+propvar]
0x1800afc14  mov     [rbp+57h+var_48], eax
0x1800afc17  lea     r8, [rbp+57h+var_90]
0x1800afc1b  mov     [rbp+57h+var_90], eax
0x1800afc1e  lea     rdx, [rbp+57h+var_58]
0x1800afc22  mov     [rbp+57h+var_60], rax
0x1800afc26  xorps   xmm0, xmm0
0x1800afc29  mov     rax, [rsi]
0x1800afc2c  mov     rcx, rsi
0x1800afc2f  movups  [rbp+57h+var_58], xmm0
0x1800afc33  movups  xmmword ptr [rbp+57h+propvar], xmm0
0x1800afc37  mov     rax, [rax+80h]
0x1800afc3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afc43  mov     ebx, eax
0x1800afc45  test    eax, eax
0x1800afc47  js      loc_1800AFDAA
0x1800afc4d  mov     rdx, r15
0x1800afc50  mov     qword ptr [rbp+57h+pftOut.dwLowDateTime], 0
0x1800afc58  lea     rcx, [rbp+57h+var_58]
0x1800afc5c  call    ??8@YAHAEBU_tagpropertykey@@0@Z; operator==(_tagpropertykey const &,_tagpropertykey const &)
0x1800afc61  test    eax, eax
0x1800afc63  jz      short loc_1800AFCDE
0x1800afc65  lea     r8, [rbp+57h+pftOut]; pftOut
0x1800afc69  xor     edx, edx; pstfOut
0x1800afc6b  lea     rcx, [rbp+57h+propvar]; propvar
0x1800afc6f  call    cs:__imp_PropVariantToFileTime
0x1800afc75  test    eax, eax
0x1800afc77  js      short loc_1800AFCDE
0x1800afc79  mov     ecx, [rbp+57h+var_90]
0x1800afc7c  mov     esi, 0FFFFFFFDh
0x1800afc81  lea     eax, [rcx-4]
0x1800afc84  test    esi, eax
0x1800afc86  jnz     short loc_1800AFCB3
0x1800afc88  cmp     dword ptr [r14], 0
0x1800afc8c  jnz     short loc_1800AFC95
0x1800afc8e  cmp     dword ptr [r14+4], 0
0x1800afc93  jz      short loc_1800AFCA7
0x1800afc95  mov     rdx, r14; lpFileTime2
0x1800afc98  lea     rcx, [rbp+57h+pftOut]; lpFileTime1
0x1800afc9c  call    cs:__imp_CompareFileTime
0x1800afca2  cmp     eax, 0FFFFFFFFh
0x1800afca5  jnz     short loc_1800AFCB0
0x1800afca7  mov     rax, qword ptr [rbp+57h+pftOut.dwLowDateTime]
0x1800afcab  mov     [r14], rax
0x1800afcae  jmp     short loc_1800AFCDE
0x1800afcb0  mov     ecx, [rbp+57h+var_90]
0x1800afcb3  lea     eax, [rcx-3]
0x1800afcb6  test    esi, eax
0x1800afcb8  jnz     short loc_1800AFCDE
0x1800afcba  cmp     dword ptr [rdi], 0
0x1800afcbd  jnz     short loc_1800AFCC5
0x1800afcbf  cmp     dword ptr [rdi+4], 0
0x1800afcc3  jz      short loc_1800AFCD7
0x1800afcc5  mov     rdx, rdi; lpFileTime2
0x1800afcc8  lea     rcx, [rbp+57h+pftOut]; lpFileTime1
0x1800afccc  call    cs:__imp_CompareFileTime
0x1800afcd2  cmp     eax, 1
0x1800afcd5  jnz     short loc_1800AFCDE
0x1800afcd7  mov     rax, qword ptr [rbp+57h+pftOut.dwLowDateTime]
0x1800afcdb  mov     [rdi], rax
0x1800afcde  lea     rcx, [rbp+57h+propvar]; pvar
0x1800afce2  call    cs:__imp_PropVariantClear
0x1800afce8  jmp     loc_1800AFDC2
0x1800afced  mov     rax, [rsi]
0x1800afcf0  lea     r8, [rbp+57h+pftOut]
0x1800afcf4  lea     rdx, _GUID_92ca9dcd_5622_4bba_a805_5e9f541bd8c9
0x1800afcfb  mov     qword ptr [rbp+57h+pftOut.dwLowDateTime], 0
0x1800afd03  mov     rcx, rsi
0x1800afd06  mov     rax, [rax+48h]
0x1800afd0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afd0f  mov     ebx, eax
0x1800afd11  test    eax, eax
0x1800afd13  js      loc_1800AFDAA
0x1800afd19  mov     rcx, qword ptr [rbp+57h+pftOut.dwLowDateTime]
0x1800afd1d  lea     rdx, [rbp+57h+var_90]
0x1800afd21  mov     [rbp+57h+var_90], 0
0x1800afd28  mov     rax, [rcx]
0x1800afd2b  mov     rax, [rax+18h]
0x1800afd2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afd34  xor     esi, esi
0x1800afd36  mov     ebx, eax
0x1800afd38  test    eax, eax
0x1800afd3a  js      short loc_1800AFD96
0x1800afd3c  cmp     esi, [rbp+57h+var_90]
0x1800afd3f  jnb     short loc_1800AFD96
0x1800afd41  mov     rcx, qword ptr [rbp+57h+pftOut.dwLowDateTime]
0x1800afd45  lea     r9, [rbp+57h+var_78]
0x1800afd49  mov     [rbp+57h+var_78], 0
0x1800afd51  lea     r8, _GUID_0db8851d_2e5b_47eb_9208_d28c325a01d7
0x1800afd58  mov     edx, esi
0x1800afd5a  mov     rax, [rcx]
0x1800afd5d  mov     rax, [rax+20h]
0x1800afd61  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afd66  mov     ebx, eax
0x1800afd68  test    eax, eax
0x1800afd6a  js      short loc_1800AFD90
0x1800afd6c  mov     r9, [rbp+57h+var_78]; struct ICondition2 *
0x1800afd70  mov     r8, rdi; struct _FILETIME *
0x1800afd73  mov     rdx, r14; struct _FILETIME *
0x1800afd76  mov     rcx, r15; struct _tagpropertykey *
0x1800afd79  call    ?_AdjustDateGroupingDescriptionForCondition@@YAJAEBU_tagpropertykey@@PEAU_FILETIME@@1PEAUICondition2@@@Z; _AdjustDateGroupingDescriptionForCondition(_tagpropertykey const &,_FILETIME *,_FILETIME *,ICondition2 *)
0x1800afd7e  mov     rcx, [rbp+57h+var_78]
0x1800afd82  mov     ebx, eax
0x1800afd84  mov     rax, [rcx]
0x1800afd87  mov     rax, [rax+10h]
0x1800afd8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afd90  inc     esi
0x1800afd92  test    ebx, ebx
0x1800afd94  jns     short loc_1800AFD3C
0x1800afd96  mov     rcx, qword ptr [rbp+57h+pftOut.dwLowDateTime]
0x1800afd9a  mov     rax, [rcx]
0x1800afd9d  mov     rax, [rax+10h]
0x1800afda1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800afda6  test    ebx, ebx
0x1800afda8  jns     short loc_1800AFDC2
0x1800afdaa  mov     rcx, [rbp+5Fh]; this
0x1800afdae  lea     r8, aOnecoreuapShel_21; "onecoreuap\\shell\\windows.storage.sear"...
0x1800afdb5  mov     r9d, ebx; char *
0x1800afdb8  mov     edx, 2775h; void *
0x1800afdbd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800afdc2  mov     eax, ebx
0x1800afdc4  mov     rcx, [rbp+57h+var_40]
0x1800afdc8  xor     rcx, rsp; StackCookie
0x1800afdcb  call    __security_check_cookie
0x1800afdd0  add     rsp, 98h
0x1800afdd7  pop     r15
0x1800afdd9  pop     r14
0x1800afddb  pop     rdi
0x1800afddc  pop     rsi
0x1800afddd  pop     rbx
0x1800afdde  pop     rbp
0x1800afddf  retn
```
