# PhoneController::_SendDtmf(uint const &,ushort const *,int,ISecurityToken *,CallInfo * *)

- ea: `0x180047e54`
- end: `0x1800482b5`
- name: `?_SendDtmf@PhoneController@@AEAAJAEBIPEBGHPEAUISecurityToken@@PEAPEAVCallInfo@@@Z`
- size: `1121`
- prototype: `__int64 __usercall@<rax>(PhoneController *__hidden this@<rcx>, const unsigned int *@<rdx>, const unsigned __int16 *@<r8>, int@<r9d>, struct ISecurityToken *, struct CallInfo **)`
- caller_count: `2`
- callee_count: `18`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180030260`
- `0x180030350`

## callees

- `0x180005654`
- `0x180005660`
- `0x180006e94`
- `0x1800091a8`
- `0x18001f080`
- `0x1800208b4`
- `0x18002c574`
- `0x18002c580`
- `0x1800368d0`
- `0x180036b60`
- `0x18003a048`
- `0x18003ca40`
- `0x180047e54`
- `0x180053040`
- `0x18007f9ec`
- `0x18008d95a`
- `0x18008d9b0`
- `0x18008f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047e8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047eb1`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047e8d`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x180047eb1`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047f3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048219`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004825d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048286`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180047f3e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048219`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18004825d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180048286`
- `PhoneUtil!StripNonDtmfChars` at `0x180047f0d`
- `PhoneUtil!StripNonDtmfChars` at `0x180047f0d`

## string_xrefs

- `0x180047e93`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180047fd6`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180048089`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x1800480e6`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180048179`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x180048235`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`
- `0x18004826d`: `onecoreuap\net\phone\phoneservice\service\lib\controller.cpp`

## pseudocode

```c
__int64 __fastcall PhoneController::_SendDtmf(
        PhoneController *this,
        unsigned int *a2,
        const unsigned __int16 *a3,
        __int64 a4,
        struct ISecurityToken *a5,
        struct CallInfo **a6)
{
  __int64 v9; // rcx
  __int64 v10; // r9
  unsigned int v11; // edi
  int v12; // eax
  BackTraceCollection *v13; // rcx
  unsigned int v14; // ebx
  _WORD *v16; // rax
  __int64 v17; // rdx
  int v18; // ecx
  struct CallInfo *v19; // rbx
  int v20; // eax
  BackTraceCollection *v21; // rcx
  unsigned int v22; // eax
  struct CallInfo *v23; // rsi
  __int64 v24; // r9
  HLOCAL v25; // rcx
  int v26; // eax
  BackTraceCollection *v27; // rcx
  VerbParameters *v28; // rax
  BackTraceCollection *v29; // rcx
  VerbParameters *v30; // rdi
  VerbParameters *v31; // rax
  VerbParameters *v32; // rdi
  __int64 v33; // r8
  BackTraceCollection *v34; // rcx
  unsigned int v35; // esi
  __int64 v36; // r9
  __int64 v37; // rdx
  int v38; // eax
  BackTraceCollection *v39; // rcx
  struct CallInfo *v40; // rax
  struct CallInfo *v41; // [rsp+30h] [rbp-50h] BYREF
  _OWORD v42[3]; // [rsp+38h] [rbp-48h] BYREF
  HLOCAL hMem; // [rsp+68h] [rbp-18h] BYREF
  unsigned int v44; // [rsp+70h] [rbp-10h] BYREF

  if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
  {
    Log_AssertionEvent_3(v9, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7224);
    if ( *((_DWORD *)this + 60) != GetCurrentThreadId() )
      MicrosoftTelemetryAssertTriggeredNoArgs();
  }
  if ( (*((_DWORD *)this + 20) & 0x800) == 0 )
  {
    v10 = 7227;
    v11 = -2147020579;
LABEL_6:
    Log_HREvent_7(v11, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v10);
    return v11;
  }
  if ( !a3 )
  {
    v10 = 7229;
    v11 = -2147024809;
    goto LABEL_6;
  }
  hMem = 0;
  v12 = StripNonDtmfChars(a3, (unsigned __int16 **)&hMem);
  v14 = v12;
  if ( v12 < 0 )
  {
    BackTraceCollection::Capture(v13, v12);
    Log_HREvent_7(v14, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7232);
LABEL_11:
    if ( hMem )
      LocalFree(hMem);
    return v14;
  }
  v16 = hMem;
  v11 = -2147024809;
  if ( !hMem )
    goto LABEL_61;
  v17 = 65;
  v18 = 0;
  while ( *v16 )
  {
    ++v16;
    if ( !--v17 )
    {
      v18 = -2147024809;
      break;
    }
  }
  if ( v18 < 0 )
  {
LABEL_61:
    v24 = 7236;
    goto LABEL_62;
  }
  memset(v42, 0, sizeof(v42));
  PhoneController::_ComputeCallCounts(this, 1, (struct PH_PHONE_CALL_COUNTS *)v42, 0);
  v44 = 0;
  v19 = 0;
  v41 = 0;
  if ( !*a2 )
  {
    v20 = PhoneCallStorage::FindRelevantCallForVerb(*((_QWORD *)this + 12), 2048, &v41, 0);
    v14 = v20;
    if ( v20 < 0 )
    {
      BackTraceCollection::Capture(v21, v20);
      Log_HREvent_7(v14, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7246);
      if ( v41 )
        (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v41 + 16LL))(v41);
      goto LABEL_11;
    }
    v19 = v41;
    v22 = *((_DWORD *)v41 + 768);
    if ( !v22 )
      v22 = *((_DWORD *)v41 + 767);
    goto LABEL_36;
  }
  v23 = *(struct CallInfo **)PhoneController::_GetInfoForCallOrRepresentativeConferenceMember(this, &v41, a2, 0);
  if ( v23 )
  {
    (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v23 + 8LL))(v23);
    v19 = v23;
  }
  else
  {
    v23 = 0;
  }
  if ( v41 )
    (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v41 + 16LL))(v41);
  if ( !v23 )
  {
    v24 = 7252;
LABEL_62:
    Log_HREvent_7(2147942487LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v24);
LABEL_63:
    if ( hMem )
      LocalFree(hMem);
    return v11;
  }
  if ( (*((_DWORD *)v23 + 1656) & 0x800) == 0 )
  {
    v11 = -2147020579;
    Log_HREvent_7(2147946717LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7254);
    (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v19 + 16LL))(v19);
    goto LABEL_63;
  }
  v22 = *a2;
LABEL_36:
  v25 = hMem;
  v44 = v22;
  if ( *(_WORD *)hMem )
  {
    v26 = PhoneController::_CheckLineOwnershipForCall((PhoneController *)hMem, v19, a5);
    v11 = v26;
    if ( v26 < 0 )
    {
      BackTraceCollection::Capture(v27, v26);
      Log_HREvent_7(v11, 1, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7262);
      (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v19 + 16LL))(v19);
      goto LABEL_63;
    }
    v28 = (VerbParameters *)operator new(0x118u);
    v30 = v28;
    if ( !v28 || (memset_0(v28, 0, 0x118u), v31 = VerbParameters::VerbParameters(v30), (v32 = v31) == 0) )
    {
      v35 = -2147024882;
      BackTraceCollection::Capture(v29, -2147024882);
      Log_HREvent_7(2147942414LL, 0, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", 7267);
      (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v19 + 16LL))(v19);
      goto LABEL_58;
    }
    if ( hMem )
    {
      v33 = -1;
      do
        ++v33;
      while ( *((_WORD *)hMem + v33) );
    }
    if ( !(unsigned __int8)utl::basic_string<unsigned short,utl::char_traits<unsigned short>,utl::allocator<unsigned short>>::assign(v31) )
    {
      v35 = -2147024882;
      BackTraceCollection::Capture(v34, -2147024882);
      v36 = 7268;
      v37 = 0;
LABEL_46:
      Log_HREvent_7(v35, v37, "onecoreuap\\net\\phone\\phoneservice\\service\\lib\\controller.cpp", v36);
      VerbParameters::~VerbParameters(v32);
      operator delete(v32);
      (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v19 + 16LL))(v19);
LABEL_58:
      if ( hMem )
        LocalFree(hMem);
      return v35;
    }
    v38 = PhoneController::_ExecuteVerb(this, v19, &v44, 2048, v32);
    v35 = v38;
    if ( v38 < 0 )
    {
      BackTraceCollection::Capture(v39, v38);
      v36 = 7269;
      v37 = 1;
      goto LABEL_46;
    }
    VerbParameters::~VerbParameters(v32);
    operator delete(v32);
    v25 = hMem;
  }
  if ( a6 )
  {
    v40 = v19;
    v19 = 0;
    *a6 = v40;
  }
  if ( v19 )
  {
    (*(void (__fastcall **)(struct CallInfo *))(*(_QWORD *)v19 + 16LL))(v19);
    v25 = hMem;
  }
  if ( v25 )
    LocalFree(v25);
  return 0;
}

```

## disassembly

```asm
0x180047e54  mov     [rsp-38h+arg_18], rbx
0x180047e59  push    rbp
0x180047e5a  push    rsi
0x180047e5b  push    rdi
0x180047e5c  push    r12
0x180047e5e  push    r13
0x180047e60  push    r14
0x180047e62  push    r15
0x180047e64  mov     rbp, rsp
0x180047e67  sub     rsp, 80h
0x180047e6e  mov     rax, cs:__security_cookie
0x180047e75  xor     rax, rsp
0x180047e78  mov     [rbp+var_8], rax
0x180047e7c  mov     r13, [rbp+arg_20]
0x180047e80  mov     rbx, r8
0x180047e83  mov     r12, [rbp+arg_28]
0x180047e87  mov     r15, rdx
0x180047e8a  mov     r14, rcx
0x180047e8d  call    cs:__imp_GetCurrentThreadId
0x180047e93  lea     rdi, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180047e9a  cmp     [r14+0F0h], eax
0x180047ea1  jz      short loc_180047EC5
0x180047ea3  mov     r8d, 1C38h
0x180047ea9  mov     rdx, rdi
0x180047eac  call    Log_AssertionEvent_3
0x180047eb1  call    cs:__imp_GetCurrentThreadId
0x180047eb7  cmp     [r14+0F0h], eax
0x180047ebe  jz      short loc_180047EC5
0x180047ec0  call    MicrosoftTelemetryAssertTriggeredNoArgs
0x180047ec5  test    dword ptr [r14+50h], 800h
0x180047ecd  jnz     short loc_180047EEB
0x180047ecf  mov     r8, rdi
0x180047ed2  mov     r9d, 1C3Bh
0x180047ed8  mov     edi, 800710DDh
0x180047edd  xor     edx, edx
0x180047edf  mov     ecx, edi
0x180047ee1  call    Log_HREvent_7
0x180047ee6  jmp     loc_18004828C
0x180047eeb  xor     esi, esi
0x180047eed  test    rbx, rbx
0x180047ef0  jnz     short loc_180047F02
0x180047ef2  mov     r8, rdi
0x180047ef5  mov     r9d, 1C3Dh
0x180047efb  mov     edi, 80070057h
0x180047f00  jmp     short loc_180047EDD
0x180047f02  lea     rdx, [rbp+hMem]
0x180047f06  mov     [rbp+hMem], rsi
0x180047f0a  mov     rcx, rbx
0x180047f0d  call    cs:__imp_?StripNonDtmfChars@@YAJPEBGPEAPEAG@Z; StripNonDtmfChars(ushort const *,ushort * *)
0x180047f13  mov     ebx, eax
0x180047f15  test    eax, eax
0x180047f17  jns     short loc_180047F4B
0x180047f19  mov     edx, eax; int
0x180047f1b  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180047f20  mov     r9d, 1C40h
0x180047f26  mov     r8, rdi
0x180047f29  mov     edx, 1
0x180047f2e  mov     ecx, ebx
0x180047f30  call    Log_HREvent_7
0x180047f35  mov     rcx, [rbp+hMem]; hMem
0x180047f39  test    rcx, rcx
0x180047f3c  jz      short loc_180047F44
0x180047f3e  call    cs:__imp_LocalFree
0x180047f44  mov     eax, ebx
0x180047f46  jmp     loc_18004828E
0x180047f4b  mov     rax, [rbp+hMem]
0x180047f4f  mov     edi, 80070057h
0x180047f54  test    rax, rax
0x180047f57  jz      loc_180048267
0x180047f5d  mov     edx, 41h ; 'A'
0x180047f62  mov     ecx, esi
0x180047f64  cmp     [rax], si
0x180047f67  jz      short loc_180047F75
0x180047f69  add     rax, 2
0x180047f6d  sub     rdx, 1
0x180047f71  jnz     short loc_180047F64
0x180047f73  mov     ecx, edi
0x180047f75  test    ecx, ecx
0x180047f77  js      loc_180048267
0x180047f7d  xorps   xmm0, xmm0
0x180047f80  lea     r8, [rbp+var_48]; struct PH_PHONE_CALL_COUNTS *
0x180047f84  xor     r9d, r9d; struct ISecurityToken *
0x180047f87  mov     rcx, r14; this
0x180047f8a  movups  [rbp+var_48], xmm0
0x180047f8e  movups  [rbp+var_38], xmm0
0x180047f92  lea     edx, [r9+1]; int
0x180047f96  movups  [rbp+var_28], xmm0
0x180047f9a  call    ?_ComputeCallCounts@PhoneController@@IEAAXHPEAUPH_PHONE_CALL_COUNTS@@PEAUISecurityToken@@@Z; PhoneController::_ComputeCallCounts(int,PH_PHONE_CALL_COUNTS *,ISecurityToken *)
0x180047f9f  xor     r9d, r9d
0x180047fa2  mov     [rbp+var_10], esi
0x180047fa5  mov     rbx, rsi
0x180047fa8  mov     [rbp+var_50], rbx
0x180047fac  cmp     [r15], esi
0x180047faf  jnz     short loc_180048024
0x180047fb1  mov     rcx, [r14+60h]
0x180047fb5  lea     r8, [rbp+var_50]
0x180047fb9  mov     edx, 800h
0x180047fbe  call    ?FindRelevantCallForVerb@PhoneCallStorage@@QEAAJW4CallVerbs@@PEAPEAVCallInfo@@PEAUISecurityToken@@@Z; PhoneCallStorage::FindRelevantCallForVerb(CallVerbs,CallInfo * *,ISecurityToken *)
0x180047fc3  mov     ebx, eax
0x180047fc5  test    eax, eax
0x180047fc7  jns     short loc_180048007
0x180047fc9  mov     edx, eax; int
0x180047fcb  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180047fd0  mov     r9d, 1C4Eh
0x180047fd6  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180047fdd  mov     edx, 1
0x180047fe2  mov     ecx, ebx
0x180047fe4  call    Log_HREvent_7
0x180047fe9  mov     rcx, [rbp+var_50]
0x180047fed  test    rcx, rcx
0x180047ff0  jz      loc_180047F35
0x180047ff6  mov     rax, [rcx]
0x180047ff9  mov     rax, [rax+10h]
0x180047ffd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048002  jmp     loc_180047F35
0x180048007  mov     rbx, [rbp+var_50]
0x18004800b  mov     eax, [rbx+0C00h]
0x180048011  test    eax, eax
0x180048013  jnz     loc_1800480B8
0x180048019  mov     eax, [rbx+0BFCh]
0x18004801f  jmp     loc_1800480B8
0x180048024  mov     r8, r15
0x180048027  lea     rdx, [rbp+var_50]
0x18004802b  mov     rcx, r14
0x18004802e  call    ?_GetInfoForCallOrRepresentativeConferenceMember@PhoneController@@IEAA?AV?$CComPtr@VCallInfo@@@ATL@@AEBIPEAUISecurityToken@@@Z; PhoneController::_GetInfoForCallOrRepresentativeConferenceMember(uint const &,ISecurityToken *)
0x180048033  mov     rsi, [rax]
0x180048036  xor     eax, eax
0x180048038  test    rsi, rsi
0x18004803b  jnz     short loc_180048041
0x18004803d  mov     esi, eax
0x18004803f  jmp     short loc_180048053
0x180048041  mov     rax, [rsi]
0x180048044  mov     rcx, rsi
0x180048047  mov     rax, [rax+8]
0x18004804b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048050  mov     rbx, rsi
0x180048053  mov     rcx, [rbp+var_50]
0x180048057  test    rcx, rcx
0x18004805a  jz      short loc_180048068
0x18004805c  mov     rax, [rcx]
0x18004805f  mov     rax, [rax+10h]
0x180048063  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048068  test    rsi, rsi
0x18004806b  jnz     short loc_180048078
0x18004806d  mov     r9d, 1C54h
0x180048073  jmp     loc_18004826D
0x180048078  test    dword ptr [rsi+19E0h], 800h
0x180048082  jnz     short loc_1800480B3
0x180048084  mov     edi, 800710DDh
0x180048089  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180048090  mov     ecx, edi
0x180048092  mov     r9d, 1C56h
0x180048098  xor     edx, edx
0x18004809a  call    Log_HREvent_7
0x18004809f  mov     rax, [rbx]
0x1800480a2  mov     rax, [rax+10h]
0x1800480a6  mov     rcx, rbx
0x1800480a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800480ae  jmp     loc_18004827D
0x1800480b3  mov     eax, [r15]
0x1800480b6  xor     esi, esi
0x1800480b8  mov     rcx, [rbp+hMem]; this
0x1800480bc  mov     [rbp+var_10], eax
0x1800480bf  cmp     [rcx], si
0x1800480c2  jz      loc_1800481ED
0x1800480c8  mov     r8, r13; struct ISecurityToken *
0x1800480cb  mov     rdx, rbx; struct CallInfo *
0x1800480ce  call    ?_CheckLineOwnershipForCall@PhoneController@@AEAAJPEAVCallInfo@@PEAUISecurityToken@@@Z; PhoneController::_CheckLineOwnershipForCall(CallInfo *,ISecurityToken *)
0x1800480d3  mov     edi, eax
0x1800480d5  test    eax, eax
0x1800480d7  jns     short loc_180048102
0x1800480d9  mov     edx, eax; int
0x1800480db  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800480e0  mov     r9d, 1C5Eh
0x1800480e6  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x1800480ed  mov     edx, 1
0x1800480f2  mov     ecx, edi
0x1800480f4  call    Log_HREvent_7
0x1800480f9  mov     rcx, [rbx]
0x1800480fc  mov     rax, [rcx+10h]
0x180048100  jmp     short loc_1800480A6
0x180048102  mov     r15d, 118h
0x180048108  mov     ecx, r15d; Size
0x18004810b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180048110  mov     rdi, rax
0x180048113  test    rax, rax
0x180048116  jz      loc_180048223
0x18004811c  mov     r8d, r15d; Size
0x18004811f  xor     edx, edx; Val
0x180048121  mov     rcx, rax; void *
0x180048124  call    memset_0
0x180048129  mov     rcx, rdi; this
0x18004812c  call    ??0VerbParameters@@QEAA@XZ; VerbParameters::VerbParameters(void)
0x180048131  mov     rdi, rax
0x180048134  test    rax, rax
0x180048137  jz      loc_180048223
0x18004813d  mov     rdx, [rbp+hMem]
0x180048141  test    rdx, rdx
0x180048144  jz      short loc_180048156
0x180048146  or      r8, 0FFFFFFFFFFFFFFFFh
0x18004814a  inc     r8
0x18004814d  cmp     [rdx+r8*2], si
0x180048152  jnz     short loc_18004814A
0x180048154  jmp     short loc_180048159
0x180048156  mov     r8, rsi
0x180048159  mov     rcx, rdi
0x18004815c  call    ?assign@?$basic_string@GU?$char_traits@G@utl@@V?$allocator@G@2@@utl@@QEAA_NPEBG_K@Z; utl::basic_string<ushort,utl::char_traits<ushort>,utl::allocator<ushort>>::assign(ushort const *,unsigned __int64)
0x180048161  test    al, al
0x180048163  jnz     short loc_1800481A3
0x180048165  mov     esi, 8007000Eh
0x18004816a  mov     edx, esi; int
0x18004816c  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x180048171  mov     r9d, 1C64h
0x180048177  xor     edx, edx
0x180048179  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180048180  mov     ecx, esi
0x180048182  call    Log_HREvent_7
0x180048187  mov     rcx, rdi; this
0x18004818a  call    ??1VerbParameters@@QEAA@XZ; VerbParameters::~VerbParameters(void)
0x18004818f  mov     rcx, rdi; Block
0x180048192  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180048197  mov     rax, [rbx]
0x18004819a  mov     rax, [rax+10h]
0x18004819e  jmp     loc_18004824C
0x1800481a3  mov     r9d, 800h
0x1800481a9  mov     [rsp+80h+var_60], rdi
0x1800481ae  lea     r8, [rbp+var_10]
0x1800481b2  mov     rdx, rbx
0x1800481b5  mov     rcx, r14
0x1800481b8  call    ?_ExecuteVerb@PhoneController@@IEAAJPEAVCallInfo@@AEBIW4CallVerbs@@PEAVVerbParameters@@H@Z; PhoneController::_ExecuteVerb(CallInfo *,uint const &,CallVerbs,VerbParameters *,int)
0x1800481bd  mov     esi, eax
0x1800481bf  test    eax, eax
0x1800481c1  jns     short loc_1800481D7
0x1800481c3  mov     edx, eax; int
0x1800481c5  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x1800481ca  mov     r9d, 1C65h
0x1800481d0  mov     edx, 1
0x1800481d5  jmp     short loc_180048179
0x1800481d7  mov     rcx, rdi; this
0x1800481da  call    ??1VerbParameters@@QEAA@XZ; VerbParameters::~VerbParameters(void)
0x1800481df  mov     rcx, rdi; Block
0x1800481e2  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800481e7  mov     rcx, [rbp+hMem]
0x1800481eb  xor     esi, esi
0x1800481ed  test    r12, r12
0x1800481f0  jz      short loc_1800481FC
0x1800481f2  mov     rax, rbx
0x1800481f5  mov     rbx, rsi
0x1800481f8  mov     [r12], rax
0x1800481fc  test    rbx, rbx
0x1800481ff  jz      short loc_180048214
0x180048201  mov     rax, [rbx]
0x180048204  mov     rcx, rbx
0x180048207  mov     rax, [rax+10h]
0x18004820b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048210  mov     rcx, [rbp+hMem]; hMem
0x180048214  test    rcx, rcx
0x180048217  jz      short loc_18004821F
0x180048219  call    cs:__imp_LocalFree
0x18004821f  xor     eax, eax
0x180048221  jmp     short loc_18004828E
0x180048223  mov     esi, 8007000Eh
0x180048228  mov     edx, esi; int
0x18004822a  call    ?Capture@BackTraceCollection@@QEAAXJ@Z; BackTraceCollection::Capture(long)
0x18004822f  mov     r9d, 1C63h
0x180048235  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x18004823c  xor     edx, edx
0x18004823e  mov     ecx, esi
0x180048240  call    Log_HREvent_7
0x180048245  mov     rcx, [rbx]
0x180048248  mov     rax, [rcx+10h]
0x18004824c  mov     rcx, rbx
0x18004824f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180048254  mov     rcx, [rbp+hMem]; hMem
0x180048258  test    rcx, rcx
0x18004825b  jz      short loc_180048263
0x18004825d  call    cs:__imp_LocalFree
0x180048263  mov     eax, esi
0x180048265  jmp     short loc_18004828E
0x180048267  mov     r9d, 1C44h
0x18004826d  lea     r8, aOnecoreuapNetP_8; "onecoreuap\\net\\phone\\phoneservice\\s"...
0x180048274  xor     edx, edx
0x180048276  mov     ecx, edi
0x180048278  call    Log_HREvent_7
0x18004827d  mov     rcx, [rbp+hMem]; hMem
0x180048281  test    rcx, rcx
0x180048284  jz      short loc_18004828C
0x180048286  call    cs:__imp_LocalFree
0x18004828c  mov     eax, edi
0x18004828e  mov     rcx, [rbp+var_8]
0x180048292  xor     rcx, rsp; StackCookie
0x180048295  call    __security_check_cookie
0x18004829a  mov     rbx, [rsp+80h+arg_18]
0x1800482a2  add     rsp, 80h
0x1800482a9  pop     r15
0x1800482ab  pop     r14
0x1800482ad  pop     r13
0x1800482af  pop     r12
0x1800482b1  pop     rdi
0x1800482b2  pop     rsi
  ... truncated ...
```
