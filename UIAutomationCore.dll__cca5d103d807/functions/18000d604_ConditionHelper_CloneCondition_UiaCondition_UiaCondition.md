# ConditionHelper::CloneCondition(UiaCondition *,UiaCondition * *)

- ea: `0x18000d604`
- end: `0x18000da18`
- name: `?CloneCondition@ConditionHelper@@SAJPEAUUiaCondition@@PEAPEAU2@@Z`
- size: `1044`
- prototype: `__int64 __fastcall(struct UiaCondition *, struct UiaCondition **)`
- caller_count: `2`
- callee_count: `12`
- tags: `file_ops`

## callers

- `0x18000d4a4`
- `0x18000d604`

## callees

- `0x18000d604`
- `0x18000dcbc`
- `0x18002f580`
- `0x1800be9c8`
- `0x1800c7aac`
- `0x1800d3fa8`
- `0x180149160`
- `0x18015c1ac`
- `0x180160eb0`
- `0x1801e8344`
- `0x1801e887c`
- `0x180266d10`

## import_xrefs

- `OLEAUT32!__imp_VariantInit` at `0x18000d632`
- `OLEAUT32!__imp_VariantInit` at `0x18000d6a9`
- `OLEAUT32!__imp_VariantInit` at `0x18000d632`
- `OLEAUT32!__imp_VariantInit` at `0x18000d6a9`
- `OLEAUT32!__imp_VariantClear` at `0x18000d6b7`
- `OLEAUT32!__imp_VariantClear` at `0x18000d748`
- `OLEAUT32!__imp_VariantClear` at `0x18000d6b7`
- `OLEAUT32!__imp_VariantClear` at `0x18000d748`
- `OLEAUT32!__imp_VariantCopy` at `0x18000d646`
- `OLEAUT32!__imp_VariantCopy` at `0x18000d646`

## string_xrefs

- `0x18000d734`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x18000d75c`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x18000d79a`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x18000d7ba`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x18000d7e7`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x18000d80c`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x18000d835`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x18000d863`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x18000d88d`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`
- `0x18000d8cf`: `onecore\windows\accessibletech\uiautomationcore\conditionhelper.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall ConditionHelper::CloneCondition(struct UiaCondition *a1, struct UiaCondition **a2)
{
  ConditionType ConditionType; // ecx
  HRESULT v5; // eax
  int v6; // edi
  ConditionType v7; // edi
  ConditionType v8; // esi
  char *v9; // rax
  int v11; // eax
  int v12; // eax
  __int64 v13; // r9
  __int64 v14; // rdx
  unsigned int v15; // ebx
  BSTR bstrVal; // rdi
  __int64 v17; // rdx
  int v18; // eax
  unsigned int v19; // r15d
  ConditionType v20; // r15d
  struct UiaCondition **llVal; // rdi
  ConditionType v22; // edx
  int v23; // eax
  unsigned int v24; // r12d
  int v25; // eax
  unsigned int v26; // esi
  int v27; // eax
  VARIANTARG pvarg; // [rsp+20h] [rbp-20h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  struct UiaCondition *v30; // [rsp+70h] [rbp+30h] BYREF

  ConditionType = a1->ConditionType;
  if ( ConditionType == ConditionType_Property )
  {
    VariantInit(&pvarg);
    pvarg.llVal = 0;
    v5 = VariantCopy(&pvarg, (const VARIANTARG *)&a1[2]);
    v6 = v5;
    if ( v5 < 0 )
    {
      v13 = (unsigned int)v5;
      v14 = 82;
    }
    else
    {
      v7 = a1[8].ConditionType;
      v8 = a1[1].ConditionType;
      v9 = (char *)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
      if ( v9 )
      {
        *((_QWORD *)v9 + 1) = 0;
        *((_QWORD *)v9 + 2) = 0;
        *((_QWORD *)v9 + 3) = 0;
        *((_QWORD *)v9 + 4) = 0;
        *(_DWORD *)v9 = 2;
        *((_DWORD *)v9 + 1) = v8;
        *(VARIANTARG *)(v9 + 8) = pvarg;
        *((_DWORD *)v9 + 8) = v7;
        *a2 = (struct UiaCondition *)v9;
        VariantInit(&pvarg);
        pvarg.llVal = 0;
        VariantClear(&pvarg);
        return 0;
      }
      v6 = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x10,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
        (const char *)0x8007000ELL,
        *(int *)&pvarg.vt);
      v13 = 2147942414LL;
      v14 = 83;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v14,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
      (const char *)v13,
      *(int *)&pvarg.vt);
    VariantClear(&pvarg);
    return (unsigned int)v6;
  }
  if ( (unsigned int)(ConditionType - 3) > 1 )
  {
    if ( ConditionType == ConditionType_Not )
    {
      v30 = 0;
      v11 = ConditionHelper::CloneCondition(*(struct UiaCondition **)&a1[2].ConditionType, &v30);
      v6 = v11;
      if ( v11 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6E,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
          (const char *)(unsigned int)v11,
          *(int *)&pvarg.vt);
        AutoCleanupInfo<UiaCondition *>::SafeRelease(&v30);
      }
      else
      {
        v12 = ConditionHelper::NewNotCondition_TakeOwnership(v30, a2);
        v6 = v12;
        if ( v12 >= 0 )
        {
          v30 = 0;
          AutoCleanupInfo<UiaCondition *>::SafeRelease(&v30);
          return 0;
        }
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x6F,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
          (const char *)(unsigned int)v12,
          *(int *)&pvarg.vt);
        AutoCleanupInfo<UiaCondition *>::SafeRelease(&v30);
      }
    }
    else
    {
      if ( ConditionType )
      {
        if ( ConditionType != ConditionType_False )
          return Error::InternalErrorWorker(L"Unknown condition type");
        v6 = ConditionHelper::NewFalseCondition(a2);
        if ( v6 >= 0 )
          return 0;
        v17 = 120;
      }
      else
      {
        v6 = ConditionHelper::NewTrueCondition(a2);
        if ( v6 >= 0 )
          return 0;
        v17 = 116;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)v17,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
        (const char *)(unsigned int)v6,
        *(int *)&pvarg.vt);
    }
    return (unsigned int)v6;
  }
  v15 = 0;
  *(_DWORD *)&pvarg.vt = 0;
  pvarg.llVal = 0;
  if ( a1[4].ConditionType < ConditionType_True )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x5C,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
      (const char *)0x80070216LL,
      *(int *)&pvarg.vt);
    return 2147942934LL;
  }
  v18 = StructArrayPair<IUiaNode *>::AllocInit(&pvarg);
  v19 = v18;
  if ( v18 >= 0 )
  {
    v20 = ConditionType_True;
    llVal = (struct UiaCondition **)pvarg.llVal;
    while ( 1 )
    {
      v22 = a1[4].ConditionType;
      if ( v20 >= v22 )
        break;
      v23 = ConditionHelper::CloneCondition(
              *(struct UiaCondition **)(*(_QWORD *)&a1[2].ConditionType + 8LL * (int)v20),
              &llVal[v20]);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x61,
          (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
          (const char *)(unsigned int)v23,
          *(int *)&pvarg.vt);
        if ( llVal )
        {
          if ( *(_DWORD *)&pvarg.vt )
          {
            do
              AutoCleanupInfo<UiaCondition *>::SafeRelease(&llVal[v15++]);
            while ( v15 < *(_DWORD *)&pvarg.vt );
          }
          operator delete(llVal);
        }
        return v24;
      }
      ++v20;
    }
    if ( a1->ConditionType == ConditionType_And )
    {
      v25 = ConditionHelper::NewAndCondition_TakeOwnership(llVal, v22, a2);
      v26 = v25;
      if ( v25 >= 0 )
        return 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x65,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
        (const char *)(unsigned int)v25,
        *(int *)&pvarg.vt);
      if ( !llVal )
        return v26;
      if ( *(_DWORD *)&pvarg.vt )
      {
        do
          AutoCleanupInfo<UiaCondition *>::SafeRelease(&llVal[v15++]);
        while ( v15 < *(_DWORD *)&pvarg.vt );
      }
    }
    else
    {
      v27 = ConditionHelper::NewOrCondition_TakeOwnership(llVal, v22, a2);
      v26 = v27;
      if ( v27 >= 0 )
        return 0;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x67,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
        (const char *)(unsigned int)v27,
        *(int *)&pvarg.vt);
      if ( !llVal )
        return v26;
      if ( *(_DWORD *)&pvarg.vt )
      {
        do
          AutoCleanupInfo<UiaCondition *>::SafeRelease(&llVal[v15++]);
        while ( v15 < *(_DWORD *)&pvarg.vt );
      }
    }
    operator delete(llVal);
    return v26;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x5D,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\conditionhelper.cpp",
    (const char *)(unsigned int)v18,
    *(int *)&pvarg.vt);
  bstrVal = pvarg.bstrVal;
  if ( pvarg.llVal )
  {
    if ( *(_DWORD *)&pvarg.vt )
    {
      do
        AutoCleanupInfo<UiaCondition *>::SafeRelease(&bstrVal[4 * v15++]);
      while ( v15 < *(_DWORD *)&pvarg.vt );
    }
    operator delete(bstrVal);
  }
  return v19;
}

```

## disassembly

```asm
0x18000d604  mov     [rsp-28h+arg_8], rbx
0x18000d609  mov     [rsp-28h+arg_10], rsi
0x18000d60e  push    rbp
0x18000d60f  push    rdi
0x18000d610  push    r12
0x18000d612  push    r14
0x18000d614  push    r15
0x18000d616  mov     rbp, rsp
0x18000d619  sub     rsp, 40h
0x18000d61d  mov     r14, rdx
0x18000d620  mov     rsi, rcx
0x18000d623  mov     ecx, [rcx]
0x18000d625  cmp     ecx, 2
0x18000d628  jnz     loc_18000D6D8
0x18000d62e  lea     rcx, [rbp+pvarg]; pvarg
0x18000d632  call    cs:__imp_VariantInit
0x18000d638  xor     ebx, ebx
0x18000d63a  mov     qword ptr [rbp+pvarg+8], rbx
0x18000d63e  lea     rdx, [rsi+8]; pvargSrc
0x18000d642  lea     rcx, [rbp+pvarg]; pvargDest
0x18000d646  call    cs:__imp_VariantCopy
0x18000d64c  mov     edi, eax
0x18000d64e  test    eax, eax
0x18000d650  js      loc_18000D72C
0x18000d656  mov     edi, [rsi+20h]
0x18000d659  mov     esi, [rsi+4]
0x18000d65c  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18000d663  lea     ecx, [rbx+28h]; unsigned __int64
0x18000d666  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18000d66b  test    rax, rax
0x18000d66e  jz      loc_18000D7DB
0x18000d674  mov     [rax+8], rbx
0x18000d678  mov     [rax+10h], rbx
0x18000d67c  mov     [rax+18h], rbx
0x18000d680  mov     [rax+20h], rbx
0x18000d684  mov     dword ptr [rax], 2
0x18000d68a  mov     [rax+4], esi
0x18000d68d  movups  xmm0, xmmword ptr [rbp+pvarg]
0x18000d691  movups  xmmword ptr [rax+8], xmm0
0x18000d695  movsd   xmm1, qword ptr [rbp+pvarg+10h]
0x18000d69a  movsd   qword ptr [rax+18h], xmm1
0x18000d69f  mov     [rax+20h], edi
0x18000d6a2  mov     [r14], rax
0x18000d6a5  lea     rcx, [rbp+pvarg]; pvarg
0x18000d6a9  call    cs:__imp_VariantInit
0x18000d6af  mov     qword ptr [rbp+pvarg+8], rbx
0x18000d6b3  lea     rcx, [rbp+pvarg]; pvarg
0x18000d6b7  call    cs:__imp_VariantClear
0x18000d6bd  xor     eax, eax
0x18000d6bf  lea     r11, [rsp+40h+var_s0]
0x18000d6c4  mov     rbx, [r11+38h]
0x18000d6c8  mov     rsi, [r11+40h]
0x18000d6cc  mov     rsp, r11
0x18000d6cf  pop     r15
0x18000d6d1  pop     r14
0x18000d6d3  pop     r12
0x18000d6d5  pop     rdi
0x18000d6d6  pop     rbp
0x18000d6d7  retn
0x18000d6d8  lea     eax, [rcx-3]
0x18000d6db  cmp     eax, 1
0x18000d6de  jbe     loc_18000D77A
0x18000d6e4  cmp     ecx, 5
0x18000d6e7  jnz     loc_18000D8AD
0x18000d6ed  xor     ebx, ebx
0x18000d6ef  mov     [rbp+arg_0], rbx
0x18000d6f3  lea     rdx, [rbp+arg_0]; struct UiaCondition **
0x18000d6f7  mov     rcx, [rsi+8]; struct UiaCondition *
0x18000d6fb  call    ?CloneCondition@ConditionHelper@@SAJPEAUUiaCondition@@PEAPEAU2@@Z; ConditionHelper::CloneCondition(UiaCondition *,UiaCondition * *)
0x18000d700  mov     edi, eax
0x18000d702  test    eax, eax
0x18000d704  js      short loc_18000D755
0x18000d706  mov     rdx, r14; struct UiaCondition **
0x18000d709  mov     rcx, [rbp+arg_0]; struct UiaCondition *
0x18000d70d  call    ?NewNotCondition_TakeOwnership@ConditionHelper@@SAJPEAUUiaCondition@@PEAPEAU2@@Z; ConditionHelper::NewNotCondition_TakeOwnership(UiaCondition *,UiaCondition * *)
0x18000d712  mov     edi, eax
0x18000d714  test    eax, eax
0x18000d716  js      loc_18000D7B3
0x18000d71c  mov     [rbp+arg_0], rbx
0x18000d720  lea     rcx, [rbp+arg_0]
0x18000d724  call    ?SafeRelease@?$AutoCleanupInfo@PEAUUiaCondition@@@@SAXAEAPEAUUiaCondition@@@Z; AutoCleanupInfo<UiaCondition *>::SafeRelease(UiaCondition * &)
0x18000d729  nop
0x18000d72a  jmp     short loc_18000D6BD
0x18000d72c  mov     r9d, eax; char *
0x18000d72f  mov     edx, 52h ; 'R'; void *
0x18000d734  lea     r8, aOnecoreWindows_135; "onecore\\windows\\accessibletech\\uiaut"...
0x18000d73b  mov     rcx, [rbp+28h]; this
0x18000d73f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d744  lea     rcx, [rbp+pvarg]; pvarg
0x18000d748  call    cs:__imp_VariantClear
0x18000d74e  mov     eax, edi
0x18000d750  jmp     loc_18000D6BF
0x18000d755  mov     rcx, [rbp+28h]; this
0x18000d759  mov     r9d, edi; char *
0x18000d75c  lea     r8, aOnecoreWindows_135; "onecore\\windows\\accessibletech\\uiaut"...
0x18000d763  mov     edx, 6Eh ; 'n'; void *
0x18000d768  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d76d  nop
0x18000d76e  lea     rcx, [rbp+arg_0]
0x18000d772  call    ?SafeRelease@?$AutoCleanupInfo@PEAUUiaCondition@@@@SAXAEAPEAUUiaCondition@@@Z; AutoCleanupInfo<UiaCondition *>::SafeRelease(UiaCondition * &)
0x18000d777  nop
0x18000d778  jmp     short loc_18000D74E
0x18000d77a  xor     ebx, ebx
0x18000d77c  mov     dword ptr [rbp+pvarg], ebx
0x18000d77f  mov     qword ptr [rbp+pvarg+8], rbx
0x18000d783  mov     edx, [rsi+10h]
0x18000d786  test    edx, edx
0x18000d788  jns     loc_18000D911
0x18000d78e  mov     rcx, [rbp+28h]; this
0x18000d792  mov     ebx, 80070216h
0x18000d797  mov     r9d, ebx; char *
0x18000d79a  lea     r8, aOnecoreWindows_135; "onecore\\windows\\accessibletech\\uiaut"...
0x18000d7a1  mov     edx, 5Ch ; '\'; void *
0x18000d7a6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7ab  nop
0x18000d7ac  mov     eax, ebx
0x18000d7ae  jmp     loc_18000D6BF
0x18000d7b3  mov     rcx, [rbp+28h]; this
0x18000d7b7  mov     r9d, edi; char *
0x18000d7ba  lea     r8, aOnecoreWindows_135; "onecore\\windows\\accessibletech\\uiaut"...
0x18000d7c1  mov     edx, 6Fh ; 'o'; void *
0x18000d7c6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7cb  nop
0x18000d7cc  lea     rcx, [rbp+arg_0]
0x18000d7d0  call    ?SafeRelease@?$AutoCleanupInfo@PEAUUiaCondition@@@@SAXAEAPEAUUiaCondition@@@Z; AutoCleanupInfo<UiaCondition *>::SafeRelease(UiaCondition * &)
0x18000d7d5  nop
0x18000d7d6  jmp     loc_18000D74E
0x18000d7db  mov     rcx, [rbp+28h]; this
0x18000d7df  mov     edi, 8007000Eh
0x18000d7e4  mov     r9d, edi; char *
0x18000d7e7  lea     r8, aOnecoreWindows_135; "onecore\\windows\\accessibletech\\uiaut"...
0x18000d7ee  mov     edx, 10h; void *
0x18000d7f3  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d7f8  mov     r9d, edi
0x18000d7fb  mov     edx, 53h ; 'S'
0x18000d800  jmp     loc_18000D734
0x18000d805  mov     rcx, [rbp+28h]; this
0x18000d809  mov     r9d, esi; char *
0x18000d80c  lea     r8, aOnecoreWindows_135; "onecore\\windows\\accessibletech\\uiaut"...
0x18000d813  mov     edx, 67h ; 'g'; void *
0x18000d818  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d81d  nop
0x18000d81e  test    rdi, rdi
0x18000d821  jnz     loc_18000D9F3
0x18000d827  mov     eax, esi
0x18000d829  jmp     loc_18000D6BF
0x18000d82e  mov     rcx, [rbp+28h]; this
0x18000d832  mov     r9d, r15d; char *
0x18000d835  lea     r8, aOnecoreWindows_135; "onecore\\windows\\accessibletech\\uiaut"...
0x18000d83c  mov     edx, 5Dh ; ']'; void *
0x18000d841  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d846  nop
0x18000d847  mov     rdi, qword ptr [rbp+pvarg+8]
0x18000d84b  test    rdi, rdi
0x18000d84e  jnz     loc_18000D958
0x18000d854  mov     eax, r15d
0x18000d857  jmp     loc_18000D6BF
0x18000d85c  mov     rcx, [rbp+28h]; this
0x18000d860  mov     r9d, r12d; char *
0x18000d863  lea     r8, aOnecoreWindows_135; "onecore\\windows\\accessibletech\\uiaut"...
0x18000d86a  mov     edx, 61h ; 'a'; void *
0x18000d86f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d874  nop
0x18000d875  test    rdi, rdi
0x18000d878  jnz     loc_18000D97C
0x18000d87e  mov     eax, r12d
0x18000d881  jmp     loc_18000D6BF
0x18000d886  mov     rcx, [rbp+28h]; this
0x18000d88a  mov     r9d, esi; char *
0x18000d88d  lea     r8, aOnecoreWindows_135; "onecore\\windows\\accessibletech\\uiaut"...
0x18000d894  mov     edx, 65h ; 'e'; void *
0x18000d899  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d89e  nop
0x18000d89f  test    rdi, rdi
0x18000d8a2  jnz     loc_18000D9BF
0x18000d8a8  jmp     loc_18000D827
0x18000d8ad  test    ecx, ecx
0x18000d8af  jnz     short loc_18000D8E7
0x18000d8b1  mov     rcx, r14; struct UiaCondition **
0x18000d8b4  call    ?NewTrueCondition@ConditionHelper@@SAJPEAPEAUUiaCondition@@@Z; ConditionHelper::NewTrueCondition(UiaCondition * *)
0x18000d8b9  mov     edi, eax
0x18000d8bb  test    eax, eax
0x18000d8bd  jns     loc_18000D6BD
0x18000d8c3  mov     edx, 74h ; 't'
0x18000d8c8  jmp     short loc_18000D8CF
0x18000d8ca  mov     edx, 78h ; 'x'; void *
0x18000d8cf  lea     r8, aOnecoreWindows_135; "onecore\\windows\\accessibletech\\uiaut"...
0x18000d8d6  mov     r9d, edi; char *
0x18000d8d9  mov     rcx, [rbp+28h]; this
0x18000d8dd  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18000d8e2  jmp     loc_18000D74E
0x18000d8e7  cmp     ecx, 1
0x18000d8ea  jnz     short loc_18000D900
0x18000d8ec  mov     rcx, r14; struct UiaCondition **
0x18000d8ef  call    ?NewFalseCondition@ConditionHelper@@SAJPEAPEAUUiaCondition@@@Z; ConditionHelper::NewFalseCondition(UiaCondition * *)
0x18000d8f4  mov     edi, eax
0x18000d8f6  test    eax, eax
0x18000d8f8  jns     loc_18000D6BD
0x18000d8fe  jmp     short loc_18000D8CA
0x18000d900  lea     rcx, aUnknownConditi; "Unknown condition type"
0x18000d907  call    ?InternalErrorWorker@Error@@SAJPEBG@Z; Error::InternalErrorWorker(ushort const *)
0x18000d90c  jmp     loc_18000D6BF
0x18000d911  lea     rcx, [rbp+pvarg]
0x18000d915  call    ?AllocInit@?$StructArrayPair@PEAVIUiaNode@@@@QEAAJI@Z; StructArrayPair<IUiaNode *>::AllocInit(uint)
0x18000d91a  mov     r15d, eax
0x18000d91d  test    eax, eax
0x18000d91f  js      loc_18000D82E
0x18000d925  mov     r15d, ebx
0x18000d928  mov     rdi, qword ptr [rbp+pvarg+8]
0x18000d92c  mov     edx, [rsi+10h]; int
0x18000d92f  cmp     r15d, edx
0x18000d932  jge     short loc_18000D9A0
0x18000d934  movsxd  rax, r15d
0x18000d937  lea     rdx, [rdi+rax*8]; struct UiaCondition **
0x18000d93b  mov     rcx, [rsi+8]
0x18000d93f  mov     rcx, [rcx+rax*8]; struct UiaCondition *
0x18000d943  call    ?CloneCondition@ConditionHelper@@SAJPEAUUiaCondition@@PEAPEAU2@@Z; ConditionHelper::CloneCondition(UiaCondition *,UiaCondition * *)
0x18000d948  mov     r12d, eax
0x18000d94b  test    eax, eax
0x18000d94d  js      loc_18000D85C
0x18000d953  inc     r15d
0x18000d956  jmp     short loc_18000D92C
0x18000d958  cmp     dword ptr [rbp+pvarg], ebx
0x18000d95b  jbe     short loc_18000D96F
0x18000d95d  mov     eax, ebx
0x18000d95f  lea     rcx, [rdi+rax*8]
0x18000d963  call    ?SafeRelease@?$AutoCleanupInfo@PEAUUiaCondition@@@@SAXAEAPEAUUiaCondition@@@Z; AutoCleanupInfo<UiaCondition *>::SafeRelease(UiaCondition * &)
0x18000d968  inc     ebx
0x18000d96a  cmp     ebx, dword ptr [rbp+pvarg]
0x18000d96d  jb      short loc_18000D95D
0x18000d96f  mov     rcx, rdi; Block
0x18000d972  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d977  jmp     loc_18000D854
0x18000d97c  cmp     dword ptr [rbp+pvarg], ebx
0x18000d97f  jbe     short loc_18000D993
0x18000d981  mov     eax, ebx
0x18000d983  lea     rcx, [rdi+rax*8]
0x18000d987  call    ?SafeRelease@?$AutoCleanupInfo@PEAUUiaCondition@@@@SAXAEAPEAUUiaCondition@@@Z; AutoCleanupInfo<UiaCondition *>::SafeRelease(UiaCondition * &)
0x18000d98c  inc     ebx
0x18000d98e  cmp     ebx, dword ptr [rbp+pvarg]
0x18000d991  jb      short loc_18000D981
0x18000d993  mov     rcx, rdi; Block
0x18000d996  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d99b  jmp     loc_18000D87E
0x18000d9a0  mov     r8, r14; struct UiaCondition **
0x18000d9a3  mov     rcx, rdi; struct UiaCondition **
0x18000d9a6  cmp     dword ptr [rsi], 3
0x18000d9a9  jnz     short loc_18000D9E3
0x18000d9ab  call    ?NewAndCondition_TakeOwnership@ConditionHelper@@SAJPEAPEAUUiaCondition@@H0@Z; ConditionHelper::NewAndCondition_TakeOwnership(UiaCondition * *,int,UiaCondition * *)
0x18000d9b0  mov     esi, eax
0x18000d9b2  test    eax, eax
0x18000d9b4  js      loc_18000D886
0x18000d9ba  jmp     loc_18000D6BD
0x18000d9bf  cmp     dword ptr [rbp+pvarg], ebx
0x18000d9c2  jbe     short loc_18000D9D6
0x18000d9c4  mov     eax, ebx
0x18000d9c6  lea     rcx, [rdi+rax*8]
0x18000d9ca  call    ?SafeRelease@?$AutoCleanupInfo@PEAUUiaCondition@@@@SAXAEAPEAUUiaCondition@@@Z; AutoCleanupInfo<UiaCondition *>::SafeRelease(UiaCondition * &)
0x18000d9cf  inc     ebx
0x18000d9d1  cmp     ebx, dword ptr [rbp+pvarg]
0x18000d9d4  jb      short loc_18000D9C4
0x18000d9d6  mov     rcx, rdi; Block
0x18000d9d9  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000d9de  jmp     loc_18000D8A8
0x18000d9e3  call    ?NewOrCondition_TakeOwnership@ConditionHelper@@SAJPEAPEAUUiaCondition@@H0@Z; ConditionHelper::NewOrCondition_TakeOwnership(UiaCondition * *,int,UiaCondition * *)
0x18000d9e8  mov     esi, eax
0x18000d9ea  test    eax, eax
0x18000d9ec  jns     short loc_18000D9BA
0x18000d9ee  jmp     loc_18000D805
0x18000d9f3  cmp     dword ptr [rbp+pvarg], ebx
0x18000d9f6  jbe     short loc_18000DA0A
0x18000d9f8  mov     eax, ebx
0x18000d9fa  lea     rcx, [rdi+rax*8]
0x18000d9fe  call    ?SafeRelease@?$AutoCleanupInfo@PEAUUiaCondition@@@@SAXAEAPEAUUiaCondition@@@Z; AutoCleanupInfo<UiaCondition *>::SafeRelease(UiaCondition * &)
0x18000da03  inc     ebx
0x18000da05  cmp     ebx, dword ptr [rbp+pvarg]
0x18000da08  jb      short loc_18000D9F8
0x18000da0a  mov     rcx, rdi; Block
0x18000da0d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18000da12  jmp     loc_18000D827
```
