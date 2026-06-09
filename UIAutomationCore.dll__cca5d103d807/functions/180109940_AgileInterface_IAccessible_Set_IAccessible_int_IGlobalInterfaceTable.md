# AgileInterface<IAccessible>::Set(IAccessible *,int,IGlobalInterfaceTable *)

- ea: `0x180109940`
- end: `0x180109d6b`
- name: `?Set@?$AgileInterface@UIAccessible@@@@QEAAXPEAUIAccessible@@HPEAUIGlobalInterfaceTable@@@Z`
- size: `1067`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x1801098d8`

## callees

- `0x18002f580`
- `0x180109940`
- `0x180109ee8`
- `0x18012b47c`
- `0x1801e887c`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180109a66`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x180109a66`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180109b2c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x180109b2c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109a6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109b7f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109a6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180109b7f`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180109d2b`
- `api-ms-win-core-com-l1-1-0!CoGetClassObject` at `0x180109d2b`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1801099ad`
- `api-ms-win-core-com-l1-1-0!CoGetApartmentType` at `0x1801099ad`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180109caa`
- `ext-ms-win-rtcore-ntuser-sysparams-l1-1-0!GetSystemMetrics` at `0x180109caa`

## string_xrefs

- `0x180109bdb`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`
- `0x180109c65`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`
- `0x180109cd2`: `onecore\windows\accessibletech\uiautomationcore\proxies\agileinterface.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall AgileInterface<IAccessible>::Set(__int64 a1, __int64 a2, int a3, __int64 a4)
{
  HRESULT ApartmentType; // eax
  APTTYPE v8; // eax
  volatile signed __int32 *v9; // rax
  volatile signed __int32 *v10; // rdi
  _QWORD *v11; // rbx
  DWORD CurrentThreadId; // r9d
  __int64 v13; // rdx
  unsigned __int64 i; // r8
  __int64 v15; // rdx
  __int64 v16; // rax
  __int64 v17; // r8
  __int64 v18; // rax
  HRESULT ClassObject; // esi
  _QWORD *v20; // rax
  int v21; // eax
  int ppv; // [rsp+20h] [rbp-20h]
  wil::details::in1diag3 *retaddr; // [rsp+78h] [rbp+38h]
  APTTYPE pAptType; // [rsp+80h] [rbp+40h] BYREF
  volatile signed __int32 *pAptQualifier; // [rsp+88h] [rbp+48h] BYREF

  *(_QWORD *)(a1 + 8) = 0;
  *(_DWORD *)(a1 + 24) = 0;
  *(_DWORD *)a1 = 0;
  if ( !a2 )
    return;
  pAptType = APTTYPE_MTA;
  if ( !a3 )
    goto LABEL_23;
  if ( !BasicUiaUtils::s_isDesktopDetermined )
  {
    BasicUiaUtils::s_isDesktop = GetSystemMetrics(6144) != 0;
    BasicUiaUtils::s_isDesktopDetermined = 1;
  }
  if ( !BasicUiaUtils::s_isDesktop )
    goto LABEL_8;
  LODWORD(pAptQualifier) = 0;
  ApartmentType = CoGetApartmentType(&pAptType, (APTTYPEQUALIFIER *)&pAptQualifier);
  if ( ApartmentType != -2147221008 )
  {
    if ( ApartmentType < 0 )
      goto LABEL_14;
LABEL_8:
    v8 = pAptType;
    goto LABEL_9;
  }
  v8 = APTTYPE_NA;
  pAptType = APTTYPE_NA;
LABEL_9:
  if ( v8 == APTTYPE_NA )
  {
    *(_QWORD *)(a1 + 8) = a2;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    return;
  }
  if ( v8 && v8 != APTTYPE_MAINSTA )
  {
    if ( v8 != APTTYPE_MTA )
      return;
LABEL_23:
    if ( a4
      && (*(int (__fastcall **)(__int64, __int64, GUID *, __int64))(*(_QWORD *)a4 + 24LL))(
           a4,
           a2,
           &GUID_618736e0_3c3d_11cf_810c_00aa00389b71,
           a1 + 24) >= 0 )
    {
      return;
    }
LABEL_14:
    *(_DWORD *)a1 = 1;
    return;
  }
  v9 = (volatile signed __int32 *)operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
  v10 = v9;
  pAptQualifier = v9;
  if ( v9 )
  {
    *((_QWORD *)v9 + 2) = 0;
    *((_QWORD *)v9 + 3) = 0;
    *(_QWORD *)v9 = &RefcountBase::`vftable';
    *((_DWORD *)v9 + 2) = 1;
    _InterlockedAdd(&dword_18039DE7C, 1u);
    *(_QWORD *)v9 = &CApartmentTracker::`vftable'{for `RefcountBase'};
    *((_QWORD *)v9 + 4) = 0;
    *((_DWORD *)v9 + 10) = 0;
  }
  else
  {
    v10 = 0;
  }
  *(_QWORD *)(a1 + 16) = v10;
  if ( !v10 )
    goto LABEL_14;
  if ( !g_ComMitigationDone && !`CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress )
  {
    `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 1;
    pAptQualifier = 0;
    ClassObject = CoGetClassObject(
                    &CLSID_CUIAutomation,
                    1u,
                    0,
                    &GUID_00000001_0000_0000_c000_000000000046,
                    (LPVOID *)&pAptQualifier);
    `CApartmentTracker::GetCurrentApartmentTracker'::`2'::isComMitigationInProgress = 0;
    if ( ClassObject < 0 )
      goto LABEL_43;
    if ( pAptQualifier )
      (*(void (__fastcall **)(volatile signed __int32 *))(*(_QWORD *)pAptQualifier + 16LL))(pAptQualifier);
    g_ComMitigationDone = 1;
  }
  v11 = 0;
  EnterCriticalSection(&CApartmentTracker::_classLock);
  CurrentThreadId = GetCurrentThreadId();
  LODWORD(pAptQualifier) = CurrentThreadId;
  v13 = 0xCBF29CE484222325uLL;
  for ( i = 0; i < 4; ++i )
    v13 = 0x100000001B3LL * (*((unsigned __int8 *)&pAptQualifier + i) ^ (unsigned __int64)v13);
  v15 = 2 * (qword_18039F790 & v13);
  v16 = *((_QWORD *)Block + v15 + 1);
  if ( v16 == qword_18039F768 )
  {
LABEL_26:
    v16 = 0;
  }
  else
  {
    while ( CurrentThreadId != *(_DWORD *)(v16 + 16) )
    {
      if ( v16 == *((_QWORD *)Block + v15) )
        goto LABEL_26;
      v16 = *(_QWORD *)(v16 + 8);
    }
  }
  v17 = qword_18039F768;
  if ( v16 )
    v17 = v16;
  if ( v17 != qword_18039F768 )
    v11 = *(_QWORD **)(v17 + 24);
  LeaveCriticalSection(&CApartmentTracker::_classLock);
  if ( !v11 )
  {
    v20 = operator new(0x30u, (const struct std::nothrow_t *)std::nothrow);
    v11 = v20;
    pAptQualifier = (volatile signed __int32 *)v20;
    if ( v20 )
    {
      *v20 = &RefcountBase::`vftable';
      *((_DWORD *)v20 + 2) = 1;
      _InterlockedAdd(&dword_18039DE7C, 1u);
      *v20 = &CApartmentTracker::`vftable'{for `RefcountBase'};
      v20[2] = &CApartmentTracker::`vftable'{for `IInitializeSpy'};
      *((_DWORD *)v20 + 6) = 0;
      v20[5] = 0;
      v20[4] = 0;
      pAptQualifier = (volatile signed __int32 *)v20;
      v21 = CApartmentTracker::Initialize((CApartmentTracker *)v20);
      ClassObject = v21;
      if ( v21 >= 0 )
        goto LABEL_34;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF9,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
        (const char *)(unsigned int)v21,
        ppv);
      AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(&pAptQualifier);
    }
    else
    {
      ClassObject = -2147024882;
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xF8,
        (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
        (const char *)0x8007000ELL,
        ppv);
    }
LABEL_43:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x128,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\proxies\\agileinterface.cpp",
      (const char *)(unsigned int)ClassObject,
      ppv);
    goto LABEL_14;
  }
  if ( !*((_DWORD *)v11 + 6) )
  {
    ClassObject = -2147467259;
    goto LABEL_43;
  }
  _InterlockedAdd((volatile signed __int32 *)v11 + 2, 1u);
LABEL_34:
  _InterlockedAdd(v10 + 2, 1u);
  *((_QWORD *)v10 + 2) = v11[5];
  v18 = v11[5];
  if ( v18 )
    *(_QWORD *)(v18 + 24) = v10;
  v11[5] = v10;
  *((_QWORD *)v10 + 4) = a2;
  (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
  *((_DWORD *)v10 + 10) = GetCurrentThreadId();
  if ( v11 )
  {
    if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 2, 0xFFFFFFFF) == 1 )
      (*(void (__fastcall **)(_QWORD *, __int64))*v11)(v11, 1);
  }
}

```

## disassembly

```asm
0x180109940  mov     [rsp-38h+arg_10], rbx
0x180109945  push    rbp
0x180109946  push    rsi
0x180109947  push    rdi
0x180109948  push    r12
0x18010994a  push    r13
0x18010994c  push    r14
0x18010994e  push    r15
0x180109950  mov     rbp, rsp
0x180109953  sub     rsp, 40h
0x180109957  mov     rbx, r9
0x18010995a  mov     r14, rdx
0x18010995d  mov     r15, rcx
0x180109960  xor     r12d, r12d
0x180109963  mov     [rcx+8], r12
0x180109967  mov     [rcx+18h], r12d
0x18010996b  mov     [rcx], r12d
0x18010996e  test    rdx, rdx
0x180109971  jz      loc_180109A33
0x180109977  lea     r13d, [r12+1]
0x18010997c  mov     [rbp+pAptType], r13d
0x180109980  test    r8d, r8d
0x180109983  jz      loc_180109ADC
0x180109989  mov     al, cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x18010998f  nop
0x180109990  test    al, al
0x180109992  jz      loc_180109CA5
0x180109998  cmp     cs:?s_isDesktop@BasicUiaUtils@@2_NA, r12b; bool BasicUiaUtils::s_isDesktop
0x18010999f  jz      short loc_1801099C2
0x1801099a1  mov     dword ptr [rbp+pAptQualifier], r12d
0x1801099a5  lea     rdx, [rbp+pAptQualifier]; pAptQualifier
0x1801099a9  lea     rcx, [rbp+pAptType]; pAptType
0x1801099ad  call    cs:__imp_CoGetApartmentType
0x1801099b3  cmp     eax, 800401F0h
0x1801099b8  jz      loc_180109CE9
0x1801099be  test    eax, eax
0x1801099c0  js      short loc_180109A30
0x1801099c2  mov     eax, [rbp+pAptType]
0x1801099c5  cmp     eax, 2
0x1801099c8  jz      loc_180109C85
0x1801099ce  test    eax, eax
0x1801099d0  jnz     loc_180109BB8
0x1801099d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801099dd  mov     ecx, 30h ; '0'; unsigned __int64
0x1801099e2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x1801099e7  mov     rdi, rax
0x1801099ea  mov     [rbp+pAptQualifier], rax
0x1801099ee  lea     rsi, ??_7RefcountBase@@6B@; const RefcountBase::`vftable'
0x1801099f5  test    rax, rax
0x1801099f8  jz      loc_180109C9D
0x1801099fe  mov     [rax+10h], r12
0x180109a02  mov     [rax+18h], r12
0x180109a06  mov     [rax], rsi
0x180109a09  mov     [rax+8], r13d
0x180109a0d  lock add cs:dword_18039DE7C, r13d
0x180109a15  lea     rax, ??_7CApartmentTracker@@6BRefcountBase@@@; const CApartmentTracker::`vftable'{for `RefcountBase'}
0x180109a1c  mov     [rdi], rax
0x180109a1f  mov     [rdi+20h], r12
0x180109a23  mov     [rdi+28h], r12d
0x180109a27  mov     [r15+10h], rdi
0x180109a2b  test    rdi, rdi
0x180109a2e  jnz     short loc_180109A4B
0x180109a30  mov     [r15], r13d
0x180109a33  mov     rbx, [rsp+40h+arg_10]
0x180109a3b  add     rsp, 40h
0x180109a3f  pop     r15
0x180109a41  pop     r14
0x180109a43  pop     r13
0x180109a45  pop     r12
0x180109a47  pop     rdi
0x180109a48  pop     rsi
0x180109a49  pop     rbp
0x180109a4a  retn
0x180109a4b  mov     [rbp+var_10], r12
0x180109a4f  cmp     cs:?g_ComMitigationDone@@3_NA, r12b; bool g_ComMitigationDone
0x180109a56  jz      loc_180109CF6
0x180109a5c  mov     rbx, r12
0x180109a5f  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180109a66  call    cs:__imp_EnterCriticalSection
0x180109a6c  call    cs:__imp_GetCurrentThreadId
0x180109a72  mov     r9d, eax
0x180109a75  mov     dword ptr [rbp+pAptQualifier], eax
0x180109a78  mov     rdx, 0CBF29CE484222325h
0x180109a82  mov     r8, r12
0x180109a85  movzx   ecx, byte ptr [rbp+r8+pAptQualifier]
0x180109a8b  xor     rdx, rcx
0x180109a8e  mov     rax, 100000001B3h
0x180109a98  imul    rdx, rax
0x180109a9c  add     r8, r13
0x180109a9f  cmp     r8, 4
0x180109aa3  jb      short loc_180109A85
0x180109aa5  and     rdx, cs:qword_18039F790
0x180109aac  add     rdx, rdx
0x180109aaf  mov     rcx, cs:Block
0x180109ab6  mov     rax, [rcx+rdx*8+8]
0x180109abb  mov     r10, cs:qword_18039F768
0x180109ac2  cmp     rax, r10
0x180109ac5  jz      short loc_180109B0F
0x180109ac7  mov     r8, [rcx+rdx*8]
0x180109acb  cmp     r9d, [rax+10h]
0x180109acf  jz      short loc_180109B12
0x180109ad1  cmp     rax, r8
0x180109ad4  jz      short loc_180109B0F
0x180109ad6  mov     rax, [rax+8]
0x180109ada  jmp     short loc_180109ACB
0x180109adc  test    rbx, rbx
0x180109adf  jz      loc_180109A30
0x180109ae5  mov     rax, [rbx]
0x180109ae8  lea     r9, [r15+18h]
0x180109aec  lea     r8, _GUID_618736e0_3c3d_11cf_810c_00aa00389b71
0x180109af3  mov     rdx, r14
0x180109af6  mov     rcx, rbx
0x180109af9  mov     rax, [rax+18h]
0x180109afd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109b02  test    eax, eax
0x180109b04  js      loc_180109A30
0x180109b0a  jmp     loc_180109A33
0x180109b0f  mov     rax, r12
0x180109b12  mov     r8, r10
0x180109b15  test    rax, rax
0x180109b18  cmovnz  r8, rax
0x180109b1c  cmp     r8, r10
0x180109b1f  jz      short loc_180109B25
0x180109b21  mov     rbx, [r8+18h]
0x180109b25  lea     rcx, ?_classLock@CApartmentTracker@@2U_RTL_CRITICAL_SECTION@@A; lpCriticalSection
0x180109b2c  call    cs:__imp_LeaveCriticalSection
0x180109b32  test    rbx, rbx
0x180109b35  jz      loc_180109BF2
0x180109b3b  cmp     [rbx+18h], r12d
0x180109b3f  jz      loc_180109BCF
0x180109b45  lock add [rbx+8], r13d
0x180109b4a  mov     [rbp+var_10], rbx
0x180109b4e  lock add [rdi+8], r13d
0x180109b53  mov     rax, [rbx+28h]
0x180109b57  mov     [rdi+10h], rax
0x180109b5b  mov     rax, [rbx+28h]
0x180109b5f  test    rax, rax
0x180109b62  jz      short loc_180109B68
0x180109b64  mov     [rax+18h], rdi
0x180109b68  mov     [rbx+28h], rdi
0x180109b6c  mov     [rdi+20h], r14
0x180109b70  mov     rax, [r14]
0x180109b73  mov     rcx, r14
0x180109b76  mov     rax, [rax+8]
0x180109b7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109b7f  call    cs:__imp_GetCurrentThreadId
0x180109b85  mov     [rdi+28h], eax
0x180109b88  test    rbx, rbx
0x180109b8b  jz      loc_180109A33
0x180109b91  or      eax, 0FFFFFFFFh
0x180109b94  lock xadd [rbx+8], eax
0x180109b99  cmp     eax, 1
0x180109b9c  jnz     loc_180109A33
0x180109ba2  mov     rax, [rbx]
0x180109ba5  mov     edx, r13d
0x180109ba8  mov     rcx, rbx
0x180109bab  mov     rax, [rax]
0x180109bae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109bb3  jmp     loc_180109A33
0x180109bb8  cmp     eax, 3
0x180109bbb  jz      loc_1801099D6
0x180109bc1  cmp     eax, r13d
0x180109bc4  jnz     loc_180109A33
0x180109bca  jmp     loc_180109ADC
0x180109bcf  mov     esi, 80004005h
0x180109bd4  mov     rcx, [rbp+38h]; this
0x180109bd8  mov     r9d, esi; char *
0x180109bdb  lea     r8, aOnecoreWindows_107; "onecore\\windows\\accessibletech\\uiaut"...
0x180109be2  mov     edx, 128h; void *
0x180109be7  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109bec  nop
0x180109bed  jmp     loc_180109A30
0x180109bf2  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180109bf9  mov     ecx, 30h ; '0'; unsigned __int64
0x180109bfe  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180109c03  mov     rbx, rax
0x180109c06  mov     [rbp+pAptQualifier], rax
0x180109c0a  test    rax, rax
0x180109c0d  jz      loc_180109CC6
0x180109c13  mov     [rax], rsi
0x180109c16  mov     [rax+8], r13d
0x180109c1a  lock add cs:dword_18039DE7C, r13d
0x180109c22  lea     rax, ??_7CApartmentTracker@@6BRefcountBase@@@; const CApartmentTracker::`vftable'{for `RefcountBase'}
0x180109c29  mov     [rbx], rax
0x180109c2c  lea     rax, ??_7CApartmentTracker@@6BIInitializeSpy@@@; const CApartmentTracker::`vftable'{for `IInitializeSpy'}
0x180109c33  mov     [rbx+10h], rax
0x180109c37  mov     [rbx+18h], r12d
0x180109c3b  mov     [rbx+28h], r12
0x180109c3f  mov     [rbx+20h], r12
0x180109c43  mov     [rbp+pAptQualifier], rbx
0x180109c47  test    rbx, rbx
0x180109c4a  jz      short loc_180109CC6
0x180109c4c  mov     rcx, rbx; this
0x180109c4f  call    ?Initialize@CApartmentTracker@@QEAAJXZ; CApartmentTracker::Initialize(void)
0x180109c54  mov     esi, eax
0x180109c56  test    eax, eax
0x180109c58  jns     loc_180109B4A
0x180109c5e  mov     rcx, [rbp+38h]; this
0x180109c62  mov     r9d, eax; char *
0x180109c65  lea     r8, aOnecoreWindows_107; "onecore\\windows\\accessibletech\\uiaut"...
0x180109c6c  mov     edx, 0F9h; void *
0x180109c71  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109c76  nop
0x180109c77  lea     rcx, [rbp+pAptQualifier]
0x180109c7b  call    ??1?$AutoRelease@PEAVEditTextRange@@@@QEAA@XZ; AutoRelease<EditTextRange *>::~AutoRelease<EditTextRange *>(void)
0x180109c80  jmp     loc_180109BD4
0x180109c85  mov     [r15+8], r14
0x180109c89  mov     rax, [r14]
0x180109c8c  mov     rcx, r14
0x180109c8f  mov     rax, [rax+8]
0x180109c93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109c98  jmp     loc_180109A33
0x180109c9d  mov     rdi, r12
0x180109ca0  jmp     loc_180109A27
0x180109ca5  mov     ecx, 1800h; nIndex
0x180109caa  call    cs:__imp_GetSystemMetrics
0x180109cb0  test    eax, eax
0x180109cb2  setnz   cs:?s_isDesktop@BasicUiaUtils@@2_NA; bool BasicUiaUtils::s_isDesktop
0x180109cb9  nop
0x180109cba  mov     cs:?s_isDesktopDetermined@BasicUiaUtils@@2U?$atomic@_N@std@@A, r13b; std::atomic<bool> BasicUiaUtils::s_isDesktopDetermined
0x180109cc1  jmp     loc_180109998
0x180109cc6  mov     rcx, [rbp+38h]; this
0x180109cca  mov     esi, 8007000Eh
0x180109ccf  mov     r9d, esi; char *
0x180109cd2  lea     r8, aOnecoreWindows_107; "onecore\\windows\\accessibletech\\uiaut"...
0x180109cd9  mov     edx, 0F8h; void *
0x180109cde  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180109ce3  nop
0x180109ce4  jmp     loc_180109BD4
0x180109ce9  mov     eax, 2
0x180109cee  mov     [rbp+pAptType], eax
0x180109cf1  jmp     loc_1801099C5
0x180109cf6  cmp     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, r12b; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x180109cfd  jnz     loc_180109A5C
0x180109d03  mov     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, r13b; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x180109d0a  mov     [rbp+pAptQualifier], r12
0x180109d0e  lea     rax, [rbp+pAptQualifier]
0x180109d12  mov     qword ptr [rsp+40h+ppv], rax; ppv
0x180109d17  lea     r9, _GUID_00000001_0000_0000_c000_000000000046; riid
0x180109d1e  xor     r8d, r8d; pvReserved
0x180109d21  mov     edx, r13d; dwClsContext
0x180109d24  lea     rcx, CLSID_CUIAutomation; rclsid
0x180109d2b  call    cs:__imp_CoGetClassObject
0x180109d31  mov     esi, eax
0x180109d33  mov     cs:?isComMitigationInProgress@?1??GetCurrentApartmentTracker@CApartmentTracker@@SAJHPEAPEAV2@@Z@4_NA, r12b; bool `CApartmentTracker::GetCurrentApartmentTracker(int,CApartmentTracker * *)'::`2'::isComMitigationInProgress
0x180109d3a  test    eax, eax
0x180109d3c  js      loc_180109BD4
0x180109d42  mov     rcx, [rbp+pAptQualifier]
0x180109d46  test    rcx, rcx
0x180109d49  jz      short loc_180109D57
0x180109d4b  mov     rax, [rcx]
0x180109d4e  mov     rax, [rax+10h]
0x180109d52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180109d57  mov     cs:?g_ComMitigationDone@@3_NA, r13b; bool g_ComMitigationDone
0x180109d5e  lea     rsi, ??_7RefcountBase@@6B@; const RefcountBase::`vftable'
0x180109d65  jmp     loc_180109A5C
```
