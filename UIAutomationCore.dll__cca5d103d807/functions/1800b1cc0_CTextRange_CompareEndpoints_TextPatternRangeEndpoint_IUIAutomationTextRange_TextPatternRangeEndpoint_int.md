# CTextRange::CompareEndpoints(TextPatternRangeEndpoint,IUIAutomationTextRange *,TextPatternRangeEndpoint,int *)

- ea: `0x1800b1cc0`
- end: `0x1800b23d8`
- name: `?CompareEndpoints@CTextRange@@UEAAJW4TextPatternRangeEndpoint@@PEAUIUIAutomationTextRange@@0PEAH@Z`
- size: `1816`
- prototype: `__int64 __usercall@<rax>(CTextRange *__hidden this@<rcx>, enum TextPatternRangeEndpoint@<edx>, struct IUIAutomationTextRange *@<r8>, enum TextPatternRangeEndpoint@<r9d>, int *)`
- caller_count: `0`
- callee_count: `24`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000f680`
- `0x18002f580`
- `0x18003ea38`
- `0x18004a5c0`
- `0x180061630`
- `0x180061aec`
- `0x180098180`
- `0x180098570`
- `0x180098590`
- `0x180099c50`
- `0x18009ab54`
- `0x1800ad62c`
- `0x1800b09d0`
- `0x1800b1120`
- `0x1800b1cc0`
- `0x1800b3338`
- `0x1800be9c8`
- `0x1800cfa40`
- `0x180133550`
- `0x180164980`
- `0x180186cd0`
- `0x1801e8320`
- `0x180234818`
- `0x1802dd010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b1da3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800b1da3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b1db1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800b1db1`

## string_xrefs

- `0x1800b1d20`: `CTextRange::CompareEndpoints`
- `0x1800b20c3`: `CTextRange::CompareEndpoints`
- `0x1800b217c`: `compValue`
- `0x1800b21b7`: `IUIAutomationTextRange::CompareEndpoints`
- `0x1800b2315`: `IUIAutomationTextRange::CompareEndpoints`
- `0x1800b2339`: `IUIAutomationTextRange::CompareEndpoints`
- `0x1800b229c`: `ITextRangeProvider::CompareEndpoints`
- `0x1800b22bc`: `ITextRangeProvider::CompareEndpoints`
- `0x1800b20ea`: `onecore\windows\accessibletech\uiautomationcore\ctextrange.cpp`
- `0x1800b21e6`: `onecore\windows\accessibletech\uiautomationcore\ctextrange.cpp`
- `0x1800b2227`: `onecore\windows\accessibletech\uiautomationcore\ctextrange.cpp`
- `0x1800b225c`: `onecore\windows\accessibletech\uiautomationcore\ctextrange.cpp`
- `0x1800b2395`: `onecore\windows\accessibletech\uiautomationcore\ctextrange.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CTextRange::CompareEndpoints(
        CTextRange *this,
        unsigned int a2,
        struct IUIAutomationTextRange *a3,
        unsigned int a4,
        int *a5)
{
  _OWORD *v9; // rbx
  char v10; // di
  HANDLE ProcessHeap; // rax
  unsigned __int16 *v12; // rbx
  int v13; // edi
  unsigned int (__fastcall ***v14)(_QWORD, GUID *, _QWORD *); // r9
  unsigned __int16 *v15; // rcx
  __int64 v16; // rsi
  __int64 v17; // rbx
  __int64 v18; // rax
  __int64 v19; // rbx
  int v20; // eax
  unsigned int v21; // ebx
  __int64 v22; // rcx
  __int64 v24; // rdi
  int v25; // ecx
  __int64 v26; // rcx
  int v27; // eax
  int v28; // edx
  unsigned __int16 *v29; // rbx
  const OLECHAR *v30; // rsi
  int v31; // ecx
  const OLECHAR *v32; // rax
  __int64 v33; // r9
  __int64 v34; // rdx
  int v35; // eax
  _QWORD *v36; // [rsp+20h] [rbp-E0h]
  int v37; // [rsp+20h] [rbp-E0h]
  int v38; // [rsp+20h] [rbp-E0h]
  unsigned __int16 *v39; // [rsp+40h] [rbp-C0h] BYREF
  int v40[2]; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v41[16]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v42; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v43; // [rsp+70h] [rbp-90h]
  _QWORD v44[3]; // [rsp+80h] [rbp-80h] BYREF
  int v45; // [rsp+98h] [rbp-68h]
  __int128 *v46; // [rsp+A0h] [rbp-60h]
  char v47; // [rsp+A8h] [rbp-58h]
  _OWORD v48[3]; // [rsp+B0h] [rbp-50h] BYREF
  __int64 v49; // [rsp+E0h] [rbp-20h]
  int v50; // [rsp+E8h] [rbp-18h]
  __int64 v51; // [rsp+F0h] [rbp-10h]
  char v52; // [rsp+F8h] [rbp-8h]
  _BYTE v53[80]; // [rsp+100h] [rbp+0h] BYREF
  _BYTE v54[272]; // [rsp+150h] [rbp+50h] BYREF
  _DWORD *v55; // [rsp+260h] [rbp+160h]
  _QWORD v56[2]; // [rsp+2A0h] [rbp+1A0h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+308h] [rbp+208h]

  v40[0] = 0;
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
  {
    v36 = v56;
    McGenEventWrite_EventWriteTransfer(this, CTextRange_CompareEndpoints_Start);
  }
  ClientApiCallTrace::ClientApiCallTrace(
    (ClientApiCallTrace *)v54,
    "CTextRange::CompareEndpoints",
    this,
    (HINSTANCE)retaddr);
  if ( retaddr < (wil::details::in1diag3 *)g_hInstance
    || retaddr > (wil::details::in1diag3 *)((char *)g_hInstance + g_ModuleSize) )
  {
    v9 = (_OWORD *)UiaImportantTraceLoggingProvider::WatchCurrentThread(
                     (__int64)v53,
                     (__int64)"CTextRange::CompareEndpoints",
                     "object=%p",
                     this);
    v10 = 1;
  }
  else
  {
    memset(v48, 0, sizeof(v48));
    v49 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
    v9 = v48;
    v10 = 2;
  }
  v42 = 0;
  v43 = 0;
  LODWORD(v42) = *(_DWORD *)v9;
  *((_QWORD *)&v42 + 1) = *((_QWORD *)v9 + 1);
  if ( (unsigned __int8)_mm_cvtsi128_si32(_mm_srli_si128((__m128i)0LL, 8)) )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, 0);
    BYTE8(v43) = 0;
  }
  *(_QWORD *)&v43 = 0;
  *(_QWORD *)&v43 = *((_QWORD *)v9 + 2);
  *((_QWORD *)v9 + 2) = 0;
  BYTE8(v43) = *((_BYTE *)v9 + 24);
  *((_BYTE *)v9 + 24) = 0;
  v44[0] = 0;
  v44[1] = *((_QWORD *)v9 + 5);
  v44[2] = 0;
  v45 = 0;
  v46 = (__int128 *)*((_QWORD *)v9 + 8);
  v47 = 0;
  if ( *((_DWORD *)v9 + 14) )
  {
    wil::details::ThreadFailureCallbackHolder::StopWatching((wil::details::ThreadFailureCallbackHolder *)(v9 + 2));
    wil::details::ThreadFailureCallbackHolder::StartWatching((wil::details::ThreadFailureCallbackHolder *)v44);
  }
  v46 = &v42;
  if ( (v10 & 2) != 0 )
  {
    v10 &= ~2u;
    ClientApiErrorTrace::~ClientApiErrorTrace((ClientApiErrorTrace *)v48);
  }
  if ( (v10 & 1) != 0 )
    ClientApiErrorTrace::~ClientApiErrorTrace((ClientApiErrorTrace *)v53);
  if ( !a5 )
  {
    v39 = 0;
    v27 = LoadResourceString(0x1F4u, &v39);
    v29 = v39;
    if ( v27 >= 0 )
      Error::SetError(v39, 0);
    v30 = &word_180313900;
    v13 = -2147467261;
    v31 = (int)WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
    {
      v32 = &word_180313900;
      if ( v29 )
        v32 = v29;
      WPP_SF_SdSS(*((_QWORD *)WPP_GLOBAL_Control + 2), 3, (__int64)L"compValue", (__int64)v32);
    }
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 1) != 0 )
    {
      if ( v29 )
        v30 = v29;
      McTemplateU0zzz_EventWriteTransfer(
        v31,
        v28,
        (unsigned int)L"IUIAutomationTextRange::CompareEndpoints",
        (unsigned int)L"compValue",
        (__int64)v30);
    }
    AutoCleanupInfo<unsigned short *>::SafeRelease(&v39);
    v33 = 2147500035LL;
    v34 = 112;
LABEL_68:
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v34,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\ctextrange.cpp",
      (const char *)v33,
      (int)v36);
    goto LABEL_69;
  }
  if ( !a3 )
  {
    v35 = Error::ClientApiError(L"IUIAutomationTextRange::CompareEndpoints", L"range", -2147467261, 500);
    v13 = v35;
    if ( v35 >= 0 )
    {
      ClientApiCallTrace::Stop((ClientApiCallTrace *)v54);
      v13 = 0;
      goto LABEL_69;
    }
    v33 = (unsigned int)v35;
    v34 = 117;
    goto LABEL_68;
  }
  *(_QWORD *)v40 = 0;
  v39 = 0;
  if ( ((__int64 (__fastcall *)(struct IUIAutomationTextRange *, GUID *, unsigned __int16 **))a3->lpVtbl->QueryInterface)(
         a3,
         &GUID_af92b8a3_7cde_4c09_bd58_a936fa9749e0,
         &v39)
    || (v12 = v39) == 0 )
  {
    v13 = Error::InternalErrorWorker(L"IUIAutomationTextRange that does not implement IInternalTextRange");
  }
  else
  {
    v13 = (*(__int64 (__fastcall **)(unsigned __int16 *, int *))(*(_QWORD *)v39 + 24LL))(v39, v40);
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7A,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\ctextrange.cpp",
      (const char *)(unsigned int)v13,
      (int)v36);
    if ( *(_QWORD *)v40 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
    goto LABEL_69;
  }
  v14 = (unsigned int (__fastcall ***)(_QWORD, GUID *, _QWORD *))*((_QWORD *)this + 13);
  v15 = 0;
  v39 = 0;
  v16 = 0;
  if ( v14 )
  {
    v56[0] = 0;
    if ( (**v14)(v14, &GUID_0a87e528_22ba_4d49_9cd5_147526282441, v56) || (v17 = v56[0]) == 0 )
    {
      v13 = Error::InternalErrorWorker(L"IUIAutomationElement that does not implement IInternalAutomationElement");
    }
    else
    {
      v13 = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **))(*(_QWORD *)v56[0] + 24LL))(v56[0], &v39);
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
    }
    if ( v13 >= 0 )
    {
      v15 = v39;
      if ( !v39 )
        goto LABEL_29;
      v18 = (*(__int64 (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v39 + 32LL))(v39);
      if ( v18 )
        v16 = *(_QWORD *)(v18 + 264);
    }
    v15 = v39;
  }
  else
  {
    v13 = -2147467261;
  }
LABEL_29:
  if ( v15 )
    (*(void (__fastcall **)(unsigned __int16 *))(*(_QWORD *)v15 + 16LL))(v15);
  if ( v13 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x7D,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\ctextrange.cpp",
      (const char *)(unsigned int)v13,
      (int)v36);
    if ( *(_QWORD *)v40 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
    goto LABEL_69;
  }
  v19 = *((_QWORD *)this + 14);
  if ( !v16 )
  {
    v24 = *(_QWORD *)v40;
    *a5 = 0;
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zqq_EventWriteTransfer(
        (_DWORD)v15,
        (unsigned int)UiaProviderCallout_Start,
        (unsigned int)L"ITextRangeProvider::CompareEndpoints",
        0,
        0);
    v38 = (int)a5;
    v13 = (*(__int64 (__fastcall **)(__int64, _QWORD, __int64, _QWORD))(*(_QWORD *)v19 + 40LL))(v19, a2, v24, a4);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McTemplateU0zqq_EventWriteTransfer(
        v25,
        (unsigned int)UiaProviderCallout_Stop,
        (unsigned int)L"ITextRangeProvider::CompareEndpoints",
        0,
        0);
    if ( v13 >= 0 )
    {
      if ( *v55 == 1 )
        wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54);
      if ( *(_QWORD *)v40 )
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
      goto LABEL_38;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x84,
      (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\ctextrange.cpp",
      (const char *)(unsigned int)v13,
      v38);
    wil::com_ptr_t<IAccessibleAction,wil::err_exception_policy>::~com_ptr_t<IAccessibleAction,wil::err_exception_policy>(v40);
LABEL_69:
    ClientApiErrorTrace::~ClientApiErrorTrace((ClientApiErrorTrace *)&v42);
    UiaProvider::ClientApiCallActivity::~ClientApiCallActivity((UiaProvider::ClientApiCallActivity *)v54);
    CTextRange::CompareEndpoints_::_2_::PerfMarkerTrace::_PerfMarkerTrace(v41);
    return (unsigned int)v13;
  }
  v37 = v40[0];
  v20 = InProcClientAPIStub::InvokeInProcAPI(v16, 96, v19, a2);
  v21 = v20;
  if ( v20 >= 0 )
  {
    if ( *v55 == 1 )
      wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(v54);
    if ( *(_QWORD *)v40 )
      (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
LABEL_38:
    ClientApiErrorTrace::~ClientApiErrorTrace((ClientApiErrorTrace *)&v42);
    UiaProvider::ClientApiCallActivity::~ClientApiCallActivity((UiaProvider::ClientApiCallActivity *)v54);
    if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
      McGenEventWrite_EventWriteTransfer(v22, CTextRange_CompareEndpoints_Stop);
    return 0;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x80,
    (unsigned int)"onecore\\windows\\accessibletech\\uiautomationcore\\ctextrange.cpp",
    (const char *)(unsigned int)v20,
    v37);
  if ( *(_QWORD *)v40 )
    (*(void (__fastcall **)(_QWORD))(**(_QWORD **)v40 + 16LL))(*(_QWORD *)v40);
  ClientApiErrorTrace::~ClientApiErrorTrace((ClientApiErrorTrace *)&v42);
  UiaProvider::ClientApiCallActivity::~ClientApiCallActivity((UiaProvider::ClientApiCallActivity *)v54);
  if ( (Microsoft_Windows_UIAutomationCoreEnableBits & 2) != 0 )
    McGenEventWrite_EventWriteTransfer(v26, CTextRange_CompareEndpoints_Stop);
  return v21;
}

```

## disassembly

```asm
0x1800b1cc0  push    rbp
0x1800b1cc2  push    rbx
0x1800b1cc3  push    rsi
0x1800b1cc4  push    rdi
0x1800b1cc5  push    r12
0x1800b1cc7  push    r13
0x1800b1cc9  push    r14
0x1800b1ccb  push    r15
0x1800b1ccd  lea     rbp, [rsp-1C8h]
0x1800b1cd5  sub     rsp, 2C8h
0x1800b1cdc  mov     rax, cs:__security_cookie
0x1800b1ce3  xor     rax, rsp
0x1800b1ce6  mov     [rbp+200h+var_50], rax
0x1800b1ced  mov     r13d, r9d
0x1800b1cf0  mov     rsi, r8
0x1800b1cf3  mov     r12d, edx
0x1800b1cf6  mov     r14, rcx
0x1800b1cf9  mov     r15, [rbp+200h+arg_20]
0x1800b1d00  xor     edi, edi
0x1800b1d02  mov     [rsp+300h+var_2B8], edi
0x1800b1d06  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800b1d0d  jnz     loc_1800B22D4
0x1800b1d13  mov     rbx, [rbp+208h]
0x1800b1d1a  mov     r9, rbx; void *
0x1800b1d1d  mov     r8, r14; void *
0x1800b1d20  lea     rdx, aCtextrangeComp; "CTextRange::CompareEndpoints"
0x1800b1d27  lea     rcx, [rbp+200h+var_1B0]; this
0x1800b1d2b  call    ??0ClientApiCallTrace@@QEAA@PEBDPEBX1@Z; ClientApiCallTrace::ClientApiCallTrace(char const *,void const *,void const *)
0x1800b1d30  mov     rcx, cs:?g_hInstance@@3PEAUHINSTANCE__@@EA; HINSTANCE__ * g_hInstance
0x1800b1d37  cmp     rbx, rcx
0x1800b1d3a  jb      loc_1800B20B9
0x1800b1d40  mov     eax, cs:?g_ModuleSize@@3KA; ulong g_ModuleSize
0x1800b1d46  add     rax, rcx
0x1800b1d49  cmp     rbx, rax
0x1800b1d4c  ja      loc_1800B20B9
0x1800b1d52  xorps   xmm0, xmm0
0x1800b1d55  movups  [rbp+200h+var_250], xmm0
0x1800b1d59  movups  [rbp+200h+var_240], xmm0
0x1800b1d5d  movdqu  [rbp+200h+var_230], xmm0
0x1800b1d62  mov     [rbp+200h+var_220], rdi
0x1800b1d66  mov     [rbp+200h+var_218], edi
0x1800b1d69  mov     [rbp+200h+var_210], rdi
0x1800b1d6d  mov     [rbp+200h+var_208], dil
0x1800b1d71  lea     rbx, [rbp+200h+var_250]
0x1800b1d75  mov     edi, 2
0x1800b1d7a  xorps   xmm0, xmm0
0x1800b1d7d  movups  [rsp+300h+var_2A0], xmm0
0x1800b1d82  movaps  [rsp+300h+var_290], xmm0
0x1800b1d87  mov     ecx, [rbx]
0x1800b1d89  mov     dword ptr [rsp+300h+var_2A0], ecx
0x1800b1d8d  mov     rcx, [rbx+8]
0x1800b1d91  mov     qword ptr [rsp+300h+var_2A0+8], rcx
0x1800b1d96  psrldq  xmm0, 8
0x1800b1d9b  movd    ecx, xmm0
0x1800b1d9f  test    cl, cl
0x1800b1da1  jz      short loc_1800B1DBC
0x1800b1da3  call    cs:__imp_GetProcessHeap
0x1800b1da9  xor     r8d, r8d; lpMem
0x1800b1dac  xor     edx, edx; dwFlags
0x1800b1dae  mov     rcx, rax; hHeap
0x1800b1db1  call    cs:__imp_HeapFree
0x1800b1db7  mov     byte ptr [rsp+300h+var_290+8], 0
0x1800b1dbc  mov     qword ptr [rsp+300h+var_290], 0
0x1800b1dc5  mov     rax, [rbx+10h]
0x1800b1dc9  mov     qword ptr [rsp+300h+var_290], rax
0x1800b1dce  mov     qword ptr [rbx+10h], 0
0x1800b1dd6  mov     al, [rbx+18h]
0x1800b1dd9  mov     byte ptr [rsp+300h+var_290+8], al
0x1800b1ddd  mov     byte ptr [rbx+18h], 0
0x1800b1de1  lea     rcx, [rbx+20h]; this
0x1800b1de5  xor     ebx, ebx
0x1800b1de7  mov     [rbp+200h+var_280], rbx
0x1800b1deb  mov     rax, [rcx+8]
0x1800b1def  mov     [rbp+200h+var_278], rax
0x1800b1df3  mov     [rbp+200h+var_270], rbx
0x1800b1df7  mov     [rbp+200h+var_268], ebx
0x1800b1dfa  mov     rax, [rcx+20h]
0x1800b1dfe  mov     [rbp+200h+var_260], rax
0x1800b1e02  mov     [rbp+200h+var_258], bl
0x1800b1e05  cmp     [rcx+18h], ebx
0x1800b1e08  jz      short loc_1800B1E19
0x1800b1e0a  call    ?StopWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StopWatching(void)
0x1800b1e0f  lea     rcx, [rbp+200h+var_280]; this
0x1800b1e13  call    ?StartWatching@ThreadFailureCallbackHolder@details@wil@@QEAAXXZ; wil::details::ThreadFailureCallbackHolder::StartWatching(void)
0x1800b1e18  nop
0x1800b1e19  lea     rax, [rsp+300h+var_2A0]
0x1800b1e1e  mov     [rbp+200h+var_260], rax
0x1800b1e22  test    dil, 2
0x1800b1e26  jz      short loc_1800B1E34
0x1800b1e28  and     edi, 0FFFFFFFDh
0x1800b1e2b  lea     rcx, [rbp+200h+var_250]; this
0x1800b1e2f  call    ??1ClientApiErrorTrace@@QEAA@XZ; ClientApiErrorTrace::~ClientApiErrorTrace(void)
0x1800b1e34  test    dil, 1
0x1800b1e38  jz      short loc_1800B1E43
0x1800b1e3a  lea     rcx, [rbp+200h+var_200]; this
0x1800b1e3e  call    ??1ClientApiErrorTrace@@QEAA@XZ; ClientApiErrorTrace::~ClientApiErrorTrace(void)
0x1800b1e43  test    r15, r15
0x1800b1e46  jz      loc_1800B214D
0x1800b1e4c  test    rsi, rsi
0x1800b1e4f  jz      loc_1800B2326
0x1800b1e55  mov     qword ptr [rsp+300h+var_2B8], rbx
0x1800b1e5a  mov     [rsp+300h+var_2C0], rbx
0x1800b1e5f  mov     rax, [rsi]
0x1800b1e62  lea     r8, [rsp+300h+var_2C0]
0x1800b1e67  lea     rdx, _GUID_af92b8a3_7cde_4c09_bd58_a936fa9749e0
0x1800b1e6e  mov     rcx, rsi
0x1800b1e71  mov     rax, [rax]
0x1800b1e74  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1e79  test    eax, eax
0x1800b1e7b  jnz     loc_1800B202B
0x1800b1e81  mov     rbx, [rsp+300h+var_2C0]
0x1800b1e86  test    rbx, rbx
0x1800b1e89  jz      loc_1800B202B
0x1800b1e8f  mov     rax, [rbx]
0x1800b1e92  lea     rdx, [rsp+300h+var_2B8]
0x1800b1e97  mov     rcx, rbx
0x1800b1e9a  mov     rax, [rax+18h]
0x1800b1e9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1ea3  mov     edi, eax
0x1800b1ea5  mov     rax, [rbx]
0x1800b1ea8  mov     rcx, rbx
0x1800b1eab  mov     rax, [rax+10h]
0x1800b1eaf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1eb4  nop
0x1800b1eb5  test    edi, edi
0x1800b1eb7  js      loc_1800B221D
0x1800b1ebd  mov     r9, [r14+68h]
0x1800b1ec1  xor     ecx, ecx
0x1800b1ec3  mov     [rsp+300h+var_2C0], rcx
0x1800b1ec8  xor     esi, esi
0x1800b1eca  test    r9, r9
0x1800b1ecd  jz      loc_1800B228A
0x1800b1ed3  mov     [rbp+200h+var_60], rcx
0x1800b1eda  mov     rax, [r9]
0x1800b1edd  lea     r8, [rbp+200h+var_60]
0x1800b1ee4  lea     rdx, _GUID_0a87e528_22ba_4d49_9cd5_147526282441
0x1800b1eeb  mov     rcx, r9
0x1800b1eee  mov     rax, [rax]
0x1800b1ef1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1ef6  test    eax, eax
0x1800b1ef8  jnz     loc_1800B213A
0x1800b1efe  mov     rbx, [rbp+200h+var_60]
0x1800b1f05  test    rbx, rbx
0x1800b1f08  jz      loc_1800B213A
0x1800b1f0e  mov     rax, [rbx]
0x1800b1f11  lea     rdx, [rsp+300h+var_2C0]
0x1800b1f16  mov     rcx, rbx
0x1800b1f19  mov     rax, [rax+18h]
0x1800b1f1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1f22  mov     edi, eax
0x1800b1f24  mov     rax, [rbx]
0x1800b1f27  mov     rcx, rbx
0x1800b1f2a  mov     rax, [rax+10h]
0x1800b1f2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1f33  nop
0x1800b1f34  test    edi, edi
0x1800b1f36  js      short loc_1800B1F5A
0x1800b1f38  mov     rcx, [rsp+300h+var_2C0]
0x1800b1f3d  test    rcx, rcx
0x1800b1f40  jz      short loc_1800B1F5F
0x1800b1f42  mov     rax, [rcx]
0x1800b1f45  mov     rax, [rax+20h]
0x1800b1f49  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1f4e  test    rax, rax
0x1800b1f51  jz      short loc_1800B1F5A
0x1800b1f53  mov     rsi, [rax+108h]
0x1800b1f5a  mov     rcx, [rsp+300h+var_2C0]
0x1800b1f5f  test    rcx, rcx
0x1800b1f62  jz      short loc_1800B1F71
0x1800b1f64  mov     rax, [rcx]
0x1800b1f67  mov     rax, [rax+10h]
0x1800b1f6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1f70  nop
0x1800b1f71  test    edi, edi
0x1800b1f73  js      loc_1800B2252
0x1800b1f79  mov     rbx, [r14+70h]
0x1800b1f7d  xor     r14d, r14d
0x1800b1f80  test    rsi, rsi
0x1800b1f83  jz      loc_1800B203E
0x1800b1f89  mov     rax, qword ptr [rsp+300h+var_2B8]
0x1800b1f8e  mov     [rsp+300h+var_2D0], r15
0x1800b1f93  mov     dword ptr [rsp+300h+var_2D8], r13d
0x1800b1f98  mov     qword ptr [rsp+300h+var_2E0], rax; int
0x1800b1f9d  mov     r9d, r12d
0x1800b1fa0  mov     r8, rbx
0x1800b1fa3  lea     edx, [r14+60h]
0x1800b1fa7  mov     rcx, rsi
0x1800b1faa  call    ?InvokeInProcAPI@InProcClientAPIStub@@SAJPEAUITargetContextInvoker@@W4Protocol_MethodId@@ZZ; InProcClientAPIStub::InvokeInProcAPI(ITargetContextInvoker *,Protocol_MethodId,...)
0x1800b1faf  mov     ebx, eax
0x1800b1fb1  test    eax, eax
0x1800b1fb3  js      loc_1800B20E0
0x1800b1fb9  mov     rax, [rbp+200h+var_A0]
0x1800b1fc0  cmp     dword ptr [rax], 1
0x1800b1fc3  jnz     short loc_1800B1FCF
0x1800b1fc5  lea     rcx, [rbp+200h+var_1B0]
0x1800b1fc9  call    ?Stop@?$ActivityBase@VUiaProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800b1fce  nop
0x1800b1fcf  mov     rcx, qword ptr [rsp+300h+var_2B8]
0x1800b1fd4  test    rcx, rcx
0x1800b1fd7  jz      short loc_1800B1FE6
0x1800b1fd9  mov     rax, [rcx]
0x1800b1fdc  mov     rax, [rax+10h]
0x1800b1fe0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b1fe5  nop
0x1800b1fe6  lea     rcx, [rsp+300h+var_2A0]; this
0x1800b1feb  call    ??1ClientApiErrorTrace@@QEAA@XZ; ClientApiErrorTrace::~ClientApiErrorTrace(void)
0x1800b1ff0  lea     rcx, [rbp+200h+var_1B0]; this
0x1800b1ff4  call    ??1ClientApiCallActivity@UiaProvider@@QEAA@XZ; UiaProvider::ClientApiCallActivity::~ClientApiCallActivity(void)
0x1800b1ff9  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800b2000  jnz     loc_1800B23B5
0x1800b2006  xor     eax, eax
0x1800b2008  mov     rcx, [rbp+200h+var_50]
0x1800b200f  xor     rcx, rsp; StackCookie
0x1800b2012  call    __security_check_cookie
0x1800b2017  add     rsp, 2C8h
0x1800b201e  pop     r15
0x1800b2020  pop     r14
0x1800b2022  pop     r13
0x1800b2024  pop     r12
0x1800b2026  pop     rdi
0x1800b2027  pop     rsi
0x1800b2028  pop     rbx
0x1800b2029  pop     rbp
0x1800b202a  retn
0x1800b202b  lea     rcx, aIuiautomationt_10; "IUIAutomationTextRange that does not im"...
0x1800b2032  call    ?InternalErrorWorker@Error@@SAJPEBG@Z; Error::InternalErrorWorker(ushort const *)
0x1800b2037  mov     edi, eax
0x1800b2039  jmp     loc_1800B1EB5
0x1800b203e  mov     rdi, qword ptr [rsp+300h+var_2B8]
0x1800b2043  mov     [r15], r14d
0x1800b2046  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800b204d  jnz     loc_1800B2294
0x1800b2053  mov     rax, [rbx]
0x1800b2056  mov     qword ptr [rsp+300h+var_2E0], r15; int
0x1800b205b  mov     r9d, r13d
0x1800b205e  mov     r8, rdi
0x1800b2061  mov     edx, r12d
0x1800b2064  mov     rcx, rbx
0x1800b2067  mov     rax, [rax+28h]
0x1800b206b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2070  mov     edi, eax
0x1800b2072  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800b2079  jnz     loc_1800B22B4
0x1800b207f  test    edi, edi
0x1800b2081  js      loc_1800B238B
0x1800b2087  mov     rax, [rbp+200h+var_A0]
0x1800b208e  cmp     dword ptr [rax], 1
0x1800b2091  jnz     short loc_1800B209D
0x1800b2093  lea     rcx, [rbp+200h+var_1B0]
0x1800b2097  call    ?Stop@?$ActivityBase@VUiaProvider@@$0A@$0A@$04$0A@U_TlgReflectorTag_Param0IsProviderType@@@wil@@QEAAXJ@Z; wil::ActivityBase<UiaProvider,0,0,5,0,_TlgReflectorTag_Param0IsProviderType>::Stop(long)
0x1800b209c  nop
0x1800b209d  mov     rcx, qword ptr [rsp+300h+var_2B8]
0x1800b20a2  test    rcx, rcx
0x1800b20a5  jz      short loc_1800B20B4
0x1800b20a7  mov     rax, [rcx]
0x1800b20aa  mov     rax, [rax+10h]
0x1800b20ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b20b3  nop
0x1800b20b4  jmp     loc_1800B1FE6
0x1800b20b9  mov     r9, r14
0x1800b20bc  lea     r8, aObjectP; "object=%p"
0x1800b20c3  lea     rdx, aCtextrangeComp; "CTextRange::CompareEndpoints"
0x1800b20ca  lea     rcx, [rbp+200h+var_200]
0x1800b20ce  call    ?WatchCurrentThread@UiaImportantTraceLoggingProvider@@SA?AVActivityThreadWatcher@wil@@PEBD0ZZ; UiaImportantTraceLoggingProvider::WatchCurrentThread(char const *,char const *,...)
0x1800b20d3  mov     rbx, rax
0x1800b20d6  mov     edi, 1
0x1800b20db  jmp     loc_1800B1D7A
0x1800b20e0  mov     rcx, [rbp+208h]; this
0x1800b20e7  mov     r9d, ebx; char *
0x1800b20ea  lea     r8, aOnecoreWindows_169; "onecore\\windows\\accessibletech\\uiaut"...
0x1800b20f1  mov     edx, 80h; void *
0x1800b20f6  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800b20fb  nop
0x1800b20fc  mov     rcx, qword ptr [rsp+300h+var_2B8]
0x1800b2101  test    rcx, rcx
0x1800b2104  jz      short loc_1800B2113
0x1800b2106  mov     rax, [rcx]
0x1800b2109  mov     rax, [rax+10h]
0x1800b210d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b2112  nop
0x1800b2113  lea     rcx, [rsp+300h+var_2A0]; this
0x1800b2118  call    ??1ClientApiErrorTrace@@QEAA@XZ; ClientApiErrorTrace::~ClientApiErrorTrace(void)
0x1800b211d  lea     rcx, [rbp+200h+var_1B0]; this
0x1800b2121  call    ??1ClientApiCallActivity@UiaProvider@@QEAA@XZ; UiaProvider::ClientApiCallActivity::~ClientApiCallActivity(void)
0x1800b2126  test    cs:Microsoft_Windows_UIAutomationCoreEnableBits, 2
0x1800b212d  jnz     loc_1800B2368
0x1800b2133  mov     eax, ebx
0x1800b2135  jmp     loc_1800B2008
0x1800b213a  lea     rcx, aIuiautomatione_118; "IUIAutomationElement that does not impl"...
0x1800b2141  call    ?InternalErrorWorker@Error@@SAJPEBG@Z; Error::InternalErrorWorker(ushort const *)
0x1800b2146  mov     edi, eax
0x1800b2148  jmp     loc_1800B1F34
0x1800b214d  mov     [rsp+300h+var_2C0], rbx
0x1800b2152  lea     rdx, [rsp+300h+var_2C0]; unsigned __int16 **
0x1800b2157  mov     ecx, 1F4h; uID
0x1800b215c  call    ?LoadResourceString@@YAJHPEAPEAG@Z; LoadResourceString(int,ushort * *)
0x1800b2161  mov     rbx, [rsp+300h+var_2C0]
0x1800b2166  test    eax, eax
0x1800b2168  jns     loc_1800B22F7
0x1800b216e  lea     rax, WPP_GLOBAL_Control
  ... truncated ...
```
