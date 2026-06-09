# RemoveStaleCardStatesFromCache(unsigned __int64,_RTL_CRITICAL_SECTION *,ulong,_LARGE_INTEGER)

- ea: `0x180025c8c`
- end: `0x180025fd7`
- name: `?RemoveStaleCardStatesFromCache@@YAK_KPEAU_RTL_CRITICAL_SECTION@@KT_LARGE_INTEGER@@@Z`
- size: `843`
- prototype: `unsigned int __fastcall(unsigned __int64, struct _RTL_CRITICAL_SECTION *, unsigned int, union _LARGE_INTEGER)`
- caller_count: `1`
- callee_count: `16`
- tags: `broker_com_uri`

## callers

- `0x180026fdc`

## callees

- `0x18000a766`
- `0x18000a772`
- `0x18000ccb0`
- `0x18000de80`
- `0x180017bac`
- `0x180019430`
- `0x180019650`
- `0x1800196ac`
- `0x180022754`
- `0x180022888`
- `0x1800229ac`
- `0x1800233e4`
- `0x180025c8c`
- `0x18002bf00`
- `0x18002bf84`
- `0x18002cfa0`

## pseudocode

```c
__int64 __fastcall RemoveStaleCardStatesFromCache(
        __int64 a1,
        struct _RTL_CRITICAL_SECTION *a2,
        int a3,
        union _LARGE_INTEGER a4)
{
  int v4; // r15d
  __int64 v6; // rsi
  __int64 v8; // rcx
  unsigned int v9; // eax
  PVOID v10; // rcx
  void **v11; // r13
  unsigned int CardLookupName; // edi
  unsigned int i; // r14d
  __int64 *v14; // rax
  __int64 v15; // rsi
  __int64 v16; // rcx
  __int64 v17; // rcx
  void *v18; // rax
  __int64 v19; // rcx
  void *v20; // r12
  unsigned int v23; // [rsp+38h] [rbp-C8h] BYREF
  void **v24; // [rsp+40h] [rbp-C0h] BYREF
  __int64 v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+50h] [rbp-B0h]
  struct _RTL_CRITICAL_SECTION *v27; // [rsp+58h] [rbp-A8h]
  unsigned __int16 v28[264]; // [rsp+60h] [rbp-A0h] BYREF

  v4 = a3;
  v26 = a3;
  v27 = a2;
  v6 = a1;
  v24 = 0;
  v23 = 0;
  memset_0(v28, 0, 0x208u);
  WppTraceIndent(v8, 0);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_s(*((_QWORD *)WPP_GLOBAL_Control + 2), 18, &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids, WPP_pszIndent);
  }
  v9 = ScCacheEnumCardStates(a2, v6, &v24, &v23);
  v11 = v24;
  CardLookupName = v9;
  if ( v9 )
    goto LABEL_30;
  for ( i = 0; ; ++i )
  {
    if ( i >= v23 )
      goto LABEL_29;
    v14 = (__int64 *)v11[2 * i + 1];
    v15 = *v14;
    if ( v4 != *(_DWORD *)(*v14 + 716) )
      continue;
    CardLookupName = CspEnterCriticalSection(v15 + 624);
    if ( CardLookupName )
      break;
    v24 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
    v25 = v15 + 624;
    if ( a4.QuadPart != *(_QWORD *)(v15 + 720) )
    {
      CardLookupName = GetCardLookupName((struct _CARD_STATE *)v15, v28);
      if ( CardLookupName )
      {
        WppTraceIndent(v17, 2u);
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_sD(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            20,
            (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
            (_DWORD)WPP_pszIndent,
            CardLookupName);
        }
        goto LABEL_20;
      }
      v18 = MIDL_user_allocate(*(unsigned int *)(v15 + 560));
      v20 = v18;
      if ( !v18 )
      {
        WppTraceIndent(v19, 2u);
        CardLookupName = 8;
        if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
          && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
          && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
        {
          WPP_SF_s(
            *((_QWORD *)WPP_GLOBAL_Control + 2),
            21,
            &WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
            WPP_pszIndent);
        }
LABEL_20:
        v24 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
        Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v24);
        goto LABEL_29;
      }
      memcpy_0(v18, *(const void **)(v15 + 552), *(unsigned int *)(v15 + 560));
      v25 = 0;
      CspLeaveCriticalSection(v15 + 624);
      ScCacheDeleteCardState(v27, a1, v20, v28);
      CspFreeH(v20);
      v24 = &Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable';
    }
    Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(&v24);
    v4 = v26;
  }
  WppTraceIndent(v16, 2u);
  v10 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 2u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      19,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardLookupName);
  }
LABEL_29:
  v6 = a1;
LABEL_30:
  if ( v11 )
    ScCacheFreeEnumCardStates(v6, v11, v23);
  WppTraceIndent((__int64)v10, 1u);
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 5u )
  {
    WPP_SF_sD(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      22,
      (unsigned int)&WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids,
      (_DWORD)WPP_pszIndent,
      CardLookupName);
  }
  return CardLookupName;
}

```

## disassembly

```asm
0x180025c8c  mov     [rsp-8+arg_10], rbx
0x180025c91  push    rbp
0x180025c92  push    rsi
0x180025c93  push    rdi
0x180025c94  push    r12
0x180025c96  push    r13
0x180025c98  push    r14
0x180025c9a  push    r15
0x180025c9c  lea     rbp, [rsp-180h]
0x180025ca4  sub     rsp, 280h
0x180025cab  mov     rax, cs:__security_cookie
0x180025cb2  xor     rax, rsp
0x180025cb5  mov     [rbp+1B0h+var_40], rax
0x180025cbc  mov     r15d, r8d
0x180025cbf  mov     [rsp+2B0h+var_260], r8d
0x180025cc4  mov     rdi, rdx
0x180025cc7  mov     [rsp+2B0h+var_258], rdx
0x180025ccc  mov     rsi, rcx
0x180025ccf  mov     [rsp+2B0h+var_280], rcx
0x180025cd4  xor     edx, edx; Val
0x180025cd6  mov     [rsp+2B0h+var_270], 0
0x180025cdf  mov     r8d, 208h; Size
0x180025ce5  mov     [rsp+2B0h+var_278], 0
0x180025ced  lea     rcx, [rsp+2B0h+var_250]; void *
0x180025cf2  mov     rbx, r9
0x180025cf5  call    memset_0
0x180025cfa  xor     edx, edx
0x180025cfc  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025d01  mov     rcx, cs:WPP_GLOBAL_Control
0x180025d08  lea     r12, WPP_GLOBAL_Control
0x180025d0f  cmp     rcx, r12
0x180025d12  jz      short loc_180025D3C
0x180025d14  test    byte ptr [rcx+1Ch], 2
0x180025d18  jz      short loc_180025D3C
0x180025d1a  cmp     byte ptr [rcx+19h], 5
0x180025d1e  jb      short loc_180025D3C
0x180025d20  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025d27  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025d2e  mov     rcx, [rcx+10h]
0x180025d32  mov     edx, 12h
0x180025d37  call    WPP_SF_s
0x180025d3c  lea     r9, [rsp+2B0h+var_278]
0x180025d41  mov     rdx, rsi
0x180025d44  lea     r8, [rsp+2B0h+var_270]
0x180025d49  mov     rcx, rdi
0x180025d4c  call    ScCacheEnumCardStates
0x180025d51  mov     r13, [rsp+2B0h+var_270]
0x180025d56  mov     edi, eax
0x180025d58  test    eax, eax
0x180025d5a  jnz     loc_180025F54
0x180025d60  xor     r14d, r14d
0x180025d63  lea     r12, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180025d6a  cmp     r14d, [rsp+2B0h+var_278]
0x180025d6f  jnb     loc_180025F48
0x180025d75  mov     eax, r14d
0x180025d78  add     rax, rax
0x180025d7b  mov     rax, [r13+rax*8+8]
0x180025d80  mov     rsi, [rax]
0x180025d83  cmp     r15d, [rsi+2CCh]
0x180025d8a  jnz     loc_180025E47
0x180025d90  lea     r15, [rsi+270h]
0x180025d97  mov     rcx, r15
0x180025d9a  call    CspEnterCriticalSection
0x180025d9f  mov     edi, eax
0x180025da1  test    eax, eax
0x180025da3  jnz     loc_180025EFD
0x180025da9  mov     [rsp+2B0h+var_270], r12
0x180025dae  mov     [rsp+2B0h+var_268], r15
0x180025db3  cmp     rbx, [rsi+2D0h]
0x180025dba  jz      short loc_180025E38
0x180025dbc  lea     rdx, [rsp+2B0h+var_250]; unsigned __int16 *
0x180025dc1  mov     rcx, rsi; struct _CARD_STATE *
0x180025dc4  call    ?GetCardLookupName@@YAKPEAU_CARD_STATE@@PEAGK@Z; GetCardLookupName(_CARD_STATE *,ushort *,ulong)
0x180025dc9  mov     edi, eax
0x180025dcb  test    eax, eax
0x180025dcd  jnz     loc_180025EB2
0x180025dd3  mov     ecx, [rsi+230h]; size
0x180025dd9  call    MIDL_user_allocate
0x180025dde  mov     r12, rax
0x180025de1  test    rax, rax
0x180025de4  jz      short loc_180025E4F
0x180025de6  mov     r8d, [rsi+230h]; Size
0x180025ded  mov     rcx, rax; void *
0x180025df0  mov     rdx, [rsi+228h]; Src
0x180025df7  call    memcpy_0
0x180025dfc  mov     rcx, r15
0x180025dff  mov     [rsp+2B0h+var_268], 0
0x180025e08  call    CspLeaveCriticalSection
0x180025e0d  mov     rdx, [rsp+2B0h+var_280]
0x180025e12  lea     r9, [rsp+2B0h+var_250]
0x180025e17  mov     rcx, [rsp+2B0h+var_258]
0x180025e1c  mov     r8, r12
0x180025e1f  call    ScCacheDeleteCardState
0x180025e24  mov     rcx, r12
0x180025e27  call    CspFreeH
0x180025e2c  lea     r12, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180025e33  mov     [rsp+2B0h+var_270], r12
0x180025e38  lea     rcx, [rsp+2B0h+var_270]
0x180025e3d  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180025e42  mov     r15d, [rsp+2B0h+var_260]
0x180025e47  inc     r14d
0x180025e4a  jmp     loc_180025D6A
0x180025e4f  mov     edx, 2
0x180025e54  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025e59  mov     edi, 8
0x180025e5e  mov     rcx, cs:WPP_GLOBAL_Control
0x180025e65  lea     r12, WPP_GLOBAL_Control
0x180025e6c  cmp     rcx, r12
0x180025e6f  jz      short loc_180025E97
0x180025e71  test    byte ptr [rcx+1Ch], 1
0x180025e75  jz      short loc_180025E97
0x180025e77  cmp     byte ptr [rcx+19h], 2
0x180025e7b  jb      short loc_180025E97
0x180025e7d  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025e84  lea     edx, [rdi+0Dh]
0x180025e87  mov     rcx, [rcx+10h]
0x180025e8b  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025e92  call    WPP_SF_s
0x180025e97  lea     rax, ??_7?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@6B@; const Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::`vftable'
0x180025e9e  lea     rcx, [rsp+2B0h+var_270]
0x180025ea3  mov     [rsp+2B0h+var_270], rax
0x180025ea8  call    ?Close@?$HandleT@UCriticalSectionTraits@@@Wrappers@WRL@Microsoft@@QEAAXXZ; Microsoft::WRL::Wrappers::HandleT<CriticalSectionTraits>::Close(void)
0x180025ead  jmp     loc_180025F4F
0x180025eb2  mov     edx, 2
0x180025eb7  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025ebc  mov     rcx, cs:WPP_GLOBAL_Control
0x180025ec3  lea     r12, WPP_GLOBAL_Control
0x180025eca  cmp     rcx, r12
0x180025ecd  jz      short loc_180025E97
0x180025ecf  test    byte ptr [rcx+1Ch], 1
0x180025ed3  jz      short loc_180025E97
0x180025ed5  cmp     byte ptr [rcx+19h], 2
0x180025ed9  jb      short loc_180025E97
0x180025edb  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025ee2  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025ee9  mov     rcx, [rcx+10h]
0x180025eed  mov     edx, 14h
0x180025ef2  mov     [rsp+2B0h+var_290], edi
0x180025ef6  call    WPP_SF_sD
0x180025efb  jmp     short loc_180025E97
0x180025efd  mov     edx, 2
0x180025f02  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025f07  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f0e  lea     r12, WPP_GLOBAL_Control
0x180025f15  cmp     rcx, r12
0x180025f18  jz      short loc_180025F4F
0x180025f1a  test    byte ptr [rcx+1Ch], 1
0x180025f1e  jz      short loc_180025F4F
0x180025f20  cmp     byte ptr [rcx+19h], 2
0x180025f24  jb      short loc_180025F4F
0x180025f26  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025f2d  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025f34  mov     rcx, [rcx+10h]
0x180025f38  mov     edx, 13h
0x180025f3d  mov     [rsp+2B0h+var_290], edi
0x180025f41  call    WPP_SF_sD
0x180025f46  jmp     short loc_180025F4F
0x180025f48  lea     r12, WPP_GLOBAL_Control
0x180025f4f  mov     rsi, [rsp+2B0h+var_280]
0x180025f54  test    r13, r13
0x180025f57  jz      short loc_180025F69
0x180025f59  mov     r8d, [rsp+2B0h+var_278]
0x180025f5e  mov     rdx, r13
0x180025f61  mov     rcx, rsi
0x180025f64  call    ScCacheFreeEnumCardStates
0x180025f69  mov     edx, 1
0x180025f6e  call    ?WppTraceIndent@@YAXPEAPEADW4_WppTraceIndentType@@@Z; WppTraceIndent(char * *,_WppTraceIndentType)
0x180025f73  mov     rcx, cs:WPP_GLOBAL_Control
0x180025f7a  cmp     rcx, r12
0x180025f7d  jz      short loc_180025FAB
0x180025f7f  test    byte ptr [rcx+1Ch], 2
0x180025f83  jz      short loc_180025FAB
0x180025f85  cmp     byte ptr [rcx+19h], 5
0x180025f89  jb      short loc_180025FAB
0x180025f8b  mov     r9, cs:?WPP_pszIndent@@3PEADEA; char * WPP_pszIndent
0x180025f92  lea     r8, WPP_c5ac05b21cb43f89b1a24bf7340db9d8_Traceguids
0x180025f99  mov     rcx, [rcx+10h]
0x180025f9d  mov     edx, 16h
0x180025fa2  mov     [rsp+2B0h+var_290], edi
0x180025fa6  call    WPP_SF_sD
0x180025fab  mov     eax, edi
0x180025fad  mov     rcx, [rbp+1B0h+var_40]
0x180025fb4  xor     rcx, rsp; StackCookie
0x180025fb7  call    __security_check_cookie
0x180025fbc  mov     rbx, [rsp+2B0h+arg_10]
0x180025fc4  add     rsp, 280h
0x180025fcb  pop     r15
0x180025fcd  pop     r14
0x180025fcf  pop     r13
0x180025fd1  pop     r12
0x180025fd3  pop     rdi
0x180025fd4  pop     rsi
0x180025fd5  pop     rbp
0x180025fd6  retn
```
