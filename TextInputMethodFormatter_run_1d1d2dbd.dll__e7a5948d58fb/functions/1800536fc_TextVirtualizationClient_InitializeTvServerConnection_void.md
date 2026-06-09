# TextVirtualizationClient::InitializeTvServerConnection(void)

- ea: `0x1800536fc`
- end: `0x180053ae5`
- name: `?InitializeTvServerConnection@TextVirtualizationClient@@AEAAJXZ`
- size: `1001`
- prototype: `__int64 __fastcall(TextVirtualizationClient *__hidden this)`
- caller_count: `1`
- callee_count: `12`
- tags: `service_task, broker_com_uri`

## callers

- `0x180024fbc`

## callees

- `0x180002240`
- `0x180002db8`
- `0x18000c454`
- `0x180010540`
- `0x180012030`
- `0x1800148f0`
- `0x18002879c`
- `0x18005239c`
- `0x1800536fc`
- `0x180055460`
- `0x180055928`
- `0x180058010`

## import_xrefs

- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x180053825`
- `CoreMessaging!CoreUICallCreateEndpointHost` at `0x180053825`
- `CoreMessaging!CoreUICallSend` at `0x1800539dd`
- `CoreMessaging!CoreUICallSend` at `0x1800539dd`
- `CoreMessaging!CoreUICreate` at `0x18005375d`
- `CoreMessaging!CoreUICreate` at `0x18005375d`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall TextVirtualizationClient::InitializeTvServerConnection(TextVirtualizationClient *this)
{
  _QWORD *v2; // rdi
  __int64 v3; // rcx
  int v4; // eax
  __int64 v5; // rsi
  __int64 (__fastcall *v6)(__int64, __int64 *); // r14
  __int64 v7; // rcx
  int v8; // eax
  int v9; // eax
  __int64 v10; // rcx
  _QWORD *v11; // r14
  __int64 v12; // rcx
  int EndpointHost; // eax
  int v14; // eax
  char *v15; // rsi
  int v16; // eax
  unsigned int v17; // r8d
  ReconnectableEndpoint **v18; // rdi
  __int64 v19; // rcx
  int v20; // eax
  ReconnectableEndpoint *v21; // rbx
  char *v22; // rdx
  int v23; // eax
  int v25; // [rsp+20h] [rbp-E0h]
  int v26; // [rsp+20h] [rbp-E0h]
  int *v27; // [rsp+20h] [rbp-E0h]
  int v28[2]; // [rsp+40h] [rbp-C0h] BYREF
  char *v29; // [rsp+48h] [rbp-B8h] BYREF
  __int64 v30; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v31; // [rsp+60h] [rbp-A0h]
  __int128 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+80h] [rbp-80h]
  unsigned __int16 v34[264]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+2D8h] [rbp+1D8h]

  v30 = 0;
  v2 = (_QWORD *)((char *)this + 32);
  v3 = *((_QWORD *)this + 4);
  *v2 = 0;
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = CoreUICreate(v2);
  if ( v4 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x97,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textvirtualizationproxy\\TextVirtualizationClient.cpp",
      (const char *)(unsigned int)v4,
      v25);
  v5 = *v2;
  v6 = *(__int64 (__fastcall **)(__int64, __int64 *))(*(_QWORD *)*v2 + 24LL);
  v7 = v30;
  v30 = 0;
  if ( v7 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v7 + 16LL))(v7);
  v8 = v6(v5, &v30);
  if ( v8 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x98,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textvirtualizationproxy\\TextVirtualizationClient.cpp",
      (const char *)(unsigned int)v8,
      v25);
  v9 = SharedMessagePortRefPtr::Initialize((char *)this + 88, 1);
  if ( v9 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x9A,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textvirtualizationproxy\\TextVirtualizationClient.cpp",
      (const char *)(unsigned int)v9,
      v25);
  v10 = *((_QWORD *)this + 6);
  *((_QWORD *)this + 6) = 0;
  if ( v10 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v10 + 16LL))(v10);
  v11 = (_QWORD *)((char *)this + 40);
  v12 = *((_QWORD *)this + 5);
  *((_QWORD *)this + 5) = 0;
  if ( v12 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  EndpointHost = CoreUICallCreateEndpointHost(*v2, (char *)this + 40, (char *)this + 48);
  if ( EndpointHost < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textvirtualizationproxy\\TextVirtualizationClient.cpp",
      (const char *)(unsigned int)EndpointHost,
      v25);
  v26 = (_DWORD)this + 104;
  v14 = (*(__int64 (__fastcall **)(_QWORD, __int64 (__fastcall *)(_QWORD *, const void *, int), TextVirtualizationClient *, _QWORD))(*(_QWORD *)*v2 + 104LL))(
          *v2,
          TextVirtualizationClient::RawProc,
          this,
          *((_QWORD *)this + 12));
  if ( v14 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xA5,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textvirtualizationproxy\\TextVirtualizationClient.cpp",
      (const char *)(unsigned int)v14,
      v26);
  v15 = (char *)this + 112;
  v16 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, char *))(*(_QWORD *)*v2 + 136LL))(
          *v2,
          *((_QWORD *)this + 13),
          (char *)this + 112);
  if ( v16 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xA7,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textvirtualizationproxy\\TextVirtualizationClient.cpp",
      (const char *)(unsigned int)v16,
      v26);
  v17 = *(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor;
  if ( (*(_DWORD *)Feature_TextVirtPostNiBugFix__descriptor & 4) == 0 )
  {
    v29 = *(char **)wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(
                      retaddr,
                      &v29);
    v17 = (unsigned int)v29;
  }
  v28[0] = 0;
  LOWORD(v28[1]) = 3;
  v27 = v28;
  wil::details::ReportUsageToService(&unk_1800827F8, 42936120, (v17 >> 10) & 1, (v17 >> 11) & 1);
  memset_0(v34, 0, 0x208u);
  GetDesktopUniqueName(L"System\\TextVirtualizationProxy", v34);
  v29 = (char *)this + 16;
  *(_QWORD *)v28 = *v2;
  v18 = (ReconnectableEndpoint **)((char *)this + 72);
  v19 = *((_QWORD *)this + 9);
  *((_QWORD *)this + 9) = 0;
  if ( v19 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v19 + 16LL))(v19);
  v20 = Microsoft::WRL::Details::MakeAndInitialize<ReconnectableEndpoint,ReconnectableEndpoint,IMessageSession *,unsigned short (&)[260],IReconnectableEndpointOwner *>(
          (char *)this + 72,
          v28,
          v34,
          &v29);
  if ( v20 < 0 )
    wil::details::in1diag3::_FailFast_Hr(
      retaddr,
      (void *)0xB2,
      (unsigned int)"mincore\\textinput\\dev\\virtualization\\textvirtualizationproxy\\TextVirtualizationClient.cpp",
      (const char *)(unsigned int)v20,
      (int)v28);
  v21 = *v18;
  if ( (int)ReconnectableEndpoint::Connect(*v18) < 0 )
  {
    ReconnectableEndpoint::StartRetryTimer(v21);
  }
  else
  {
    v22 = (char *)*((_QWORD *)*v18 + 2);
    v31 = *(_OWORD *)v15;
    v32 = *((_OWORD *)v15 + 1);
    v33 = *((_QWORD *)v15 + 4);
    v29 = v22;
    LOWORD(v27) = 0;
    v23 = CoreUICallSend(*v11, &v29, 1, 1);
    if ( v23 < 0 )
      wil::details::in1diag3::_FailFast_Hr(
        retaddr,
        (void *)0xBC,
        (unsigned int)"mincore\\textinput\\dev\\virtualization\\textvirtualizationproxy\\TextVirtualizationClient.cpp",
        (const char *)(unsigned int)v23,
        (int)v27);
  }
  if ( v30 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v30 + 16LL))(v30);
  return 0;
}

```

## disassembly

```asm
0x1800536fc  mov     [rsp-8+arg_8], rbx
0x180053701  mov     [rsp-8+arg_10], rsi
0x180053706  push    rbp
0x180053707  push    rdi
0x180053708  push    r13
0x18005370a  push    r14
0x18005370c  push    r15
0x18005370e  lea     rbp, [rsp-1B0h]
0x180053716  sub     rsp, 2B0h
0x18005371d  mov     rax, cs:__security_cookie
0x180053724  xor     rax, rsp
0x180053727  mov     [rbp+1D0h+var_30], rax
0x18005372e  mov     rbx, rcx
0x180053731  mov     [rsp+2D0h+var_280], 0
0x18005373a  lea     rdi, [rcx+20h]
0x18005373e  mov     rcx, [rdi]
0x180053741  mov     qword ptr [rdi], 0
0x180053748  test    rcx, rcx
0x18005374b  jz      short loc_18005375A
0x18005374d  mov     rax, [rcx]
0x180053750  mov     rax, [rax+10h]
0x180053754  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053759  nop
0x18005375a  mov     rcx, rdi
0x18005375d  call    cs:__imp_CoreUICreate
0x180053763  mov     rcx, [rbp+1D8h]; this
0x18005376a  test    eax, eax
0x18005376c  js      loc_180053A67
0x180053772  mov     rsi, [rdi]
0x180053775  mov     rax, [rsi]
0x180053778  mov     r14, [rax+18h]
0x18005377c  mov     rcx, [rsp+2D0h+var_280]
0x180053781  mov     [rsp+2D0h+var_280], 0
0x18005378a  test    rcx, rcx
0x18005378d  jz      short loc_18005379C
0x18005378f  mov     rdx, [rcx]
0x180053792  mov     rax, [rdx+10h]
0x180053796  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005379b  nop
0x18005379c  lea     rdx, [rsp+2D0h+var_280]
0x1800537a1  mov     rcx, rsi
0x1800537a4  mov     rax, r14
0x1800537a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537ac  mov     rcx, [rbp+1D8h]; this
0x1800537b3  test    eax, eax
0x1800537b5  js      loc_180053A7C
0x1800537bb  lea     rcx, [rbx+58h]
0x1800537bf  mov     r13d, 1
0x1800537c5  mov     edx, r13d
0x1800537c8  call    ?Initialize@SharedMessagePortRefPtr@@QEAAJW4InputCapability@@@Z; SharedMessagePortRefPtr::Initialize(InputCapability)
0x1800537cd  mov     rcx, [rbp+1D8h]; this
0x1800537d4  test    eax, eax
0x1800537d6  js      loc_180053A91
0x1800537dc  lea     rsi, [rbx+30h]
0x1800537e0  mov     rcx, [rsi]
0x1800537e3  mov     qword ptr [rsi], 0
0x1800537ea  test    rcx, rcx
0x1800537ed  jz      short loc_1800537FC
0x1800537ef  mov     rax, [rcx]
0x1800537f2  mov     rax, [rax+10h]
0x1800537f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800537fb  nop
0x1800537fc  lea     r14, [rbx+28h]
0x180053800  mov     rcx, [r14]
0x180053803  mov     qword ptr [r14], 0
0x18005380a  test    rcx, rcx
0x18005380d  jz      short loc_18005381C
0x18005380f  mov     rax, [rcx]
0x180053812  mov     rax, [rax+10h]
0x180053816  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005381b  nop
0x18005381c  mov     r8, rsi
0x18005381f  mov     rdx, r14
0x180053822  mov     rcx, [rdi]
0x180053825  call    cs:__imp_CoreUICallCreateEndpointHost
0x18005382b  mov     rcx, [rbp+1D8h]; this
0x180053832  test    eax, eax
0x180053834  js      loc_180053AA6
0x18005383a  mov     rcx, [rdi]
0x18005383d  lea     r15, [rbx+68h]
0x180053841  mov     rax, [rcx]
0x180053844  mov     qword ptr [rsp+2D0h+var_2B0], r15; int
0x180053849  mov     r9, [rbx+60h]
0x18005384d  mov     r8, rbx
0x180053850  lea     rdx, ?RawProc@TextVirtualizationClient@@SAJPEAXPEBXH@Z; TextVirtualizationClient::RawProc(void *,void const *,int)
0x180053857  mov     rax, [rax+68h]
0x18005385b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053860  mov     rcx, [rbp+1D8h]; this
0x180053867  test    eax, eax
0x180053869  js      loc_180053ABB
0x18005386f  mov     rcx, [rdi]
0x180053872  lea     rsi, [rbx+70h]
0x180053876  mov     rax, [rcx]
0x180053879  mov     r8, rsi
0x18005387c  mov     rdx, [r15]
0x18005387f  mov     rax, [rax+88h]
0x180053886  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005388b  mov     rcx, [rbp+1D8h]; this
0x180053892  test    eax, eax
0x180053894  js      loc_180053AD0
0x18005389a  mov     rax, cs:Feature_TextVirtPostNiBugFix__descriptor
0x1800538a1  mov     r8d, [rax]
0x1800538a4  test    r8b, 4
0x1800538a8  jnz     short loc_1800538BF
0x1800538aa  lea     rdx, [rsp+2D0h+var_288]
0x1800538af  call    ?GetCachedFeatureEnabledState@?$FeatureImpl@U__WilFeatureTraits_Feature_TextVirtPostNiBugFix@@@details@wil@@AEAA?ATwil_details_FeatureStateCache@@XZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_TextVirtPostNiBugFix>::GetCachedFeatureEnabledState(void)
0x1800538b4  mov     rcx, [rax]
0x1800538b7  mov     [rsp+2D0h+var_288], rcx
0x1800538bc  mov     r8d, ecx
0x1800538bf  xor     eax, eax
0x1800538c1  mov     [rsp+2D0h+var_290], eax
0x1800538c5  mov     word ptr [rsp+2D0h+var_290+4], 3
0x1800538cc  mov     r9d, r8d
0x1800538cf  shr     r9d, 0Bh
0x1800538d3  and     r9d, r13d
0x1800538d6  shr     r8d, 0Ah
0x1800538da  and     r8d, r13d
0x1800538dd  mov     dword ptr [rsp+2D0h+var_2A0], 3
0x1800538e5  mov     dword ptr [rsp+2D0h+var_2A8], r13d
0x1800538ea  lea     rax, [rsp+2D0h+var_290]
0x1800538ef  mov     qword ptr [rsp+2D0h+var_2B0], rax; int
0x1800538f4  mov     edx, 28F2738h
0x1800538f9  lea     rcx, unk_1800827F8
0x180053900  call    ?ReportUsageToService@details@wil@@YAXPEAUwil_details_FeatureReportingCache@@IHHPEBUFEATURE_LOGGED_TRAITS@@HW4wil_ReportingKind@@_K@Z; wil::details::ReportUsageToService(wil_details_FeatureReportingCache *,uint,int,int,FEATURE_LOGGED_TRAITS const *,int,wil_ReportingKind,unsigned __int64)
0x180053905  xor     edx, edx; Val
0x180053907  mov     r8d, 208h; Size
0x18005390d  lea     rcx, [rbp+1D0h+var_240]; void *
0x180053911  call    memset_0
0x180053916  lea     rdx, [rbp+1D0h+var_240]; unsigned __int16 *
0x18005391a  lea     rcx, aSystemTextvirt; "System\\TextVirtualizationProxy"
0x180053921  call    ?GetDesktopUniqueName@@YAXPEBGPEAGK@Z; GetDesktopUniqueName(ushort const *,ushort *,ulong)
0x180053926  lea     rax, [rbx+10h]
0x18005392a  mov     [rsp+2D0h+var_288], rax
0x18005392f  mov     rax, [rdi]
0x180053932  mov     qword ptr [rsp+2D0h+var_290], rax
0x180053937  lea     rdi, [rbx+48h]
0x18005393b  mov     rcx, [rdi]
0x18005393e  mov     qword ptr [rdi], 0
0x180053945  test    rcx, rcx
0x180053948  jz      short loc_180053957
0x18005394a  mov     rax, [rcx]
0x18005394d  mov     rax, [rax+10h]
0x180053951  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053956  nop
0x180053957  lea     r9, [rsp+2D0h+var_288]
0x18005395c  lea     r8, [rbp+1D0h+var_240]
0x180053960  lea     rdx, [rsp+2D0h+var_290]
0x180053965  mov     rcx, rdi
0x180053968  call    ??$MakeAndInitialize@VReconnectableEndpoint@@V1@PEAUIMessageSession@@AEAY0BAE@GPEAUIReconnectableEndpointOwner@@@Details@WRL@Microsoft@@YAJPEAPEAVReconnectableEndpoint@@$$QEAPEAUIMessageSession@@AEAY0BAE@G$$QEAPEAUIReconnectableEndpointOwner@@@Z; Microsoft::WRL::Details::MakeAndInitialize<ReconnectableEndpoint,ReconnectableEndpoint,IMessageSession *,ushort (&)[260],IReconnectableEndpointOwner *>(ReconnectableEndpoint * *,IMessageSession * &&,ushort (&)[260],IReconnectableEndpointOwner * &&)
0x18005396d  mov     rcx, [rbp+1D8h]; this
0x180053974  test    eax, eax
0x180053976  js      loc_180053A3D
0x18005397c  mov     rbx, [rdi]
0x18005397f  mov     rcx, rbx; this
0x180053982  call    ?Connect@ReconnectableEndpoint@@IEAAJXZ; ReconnectableEndpoint::Connect(void)
0x180053987  test    eax, eax
0x180053989  js      short loc_1800539F0
0x18005398b  mov     rax, [rdi]
0x18005398e  mov     rdx, [rax+10h]
0x180053992  movups  xmm0, xmmword ptr [rsi]
0x180053995  movaps  [rsp+2D0h+var_270], xmm0
0x18005399a  movups  xmm1, xmmword ptr [rsi+10h]
0x18005399e  movaps  [rsp+2D0h+var_260], xmm1
0x1800539a3  movsd   xmm0, qword ptr [rsi+20h]
0x1800539a8  movsd   [rbp+1D0h+var_250], xmm0
0x1800539ad  mov     [rsp+2D0h+var_288], rdx
0x1800539b2  xor     eax, eax
0x1800539b4  lea     rcx, [rsp+2D0h+var_270]
0x1800539b9  mov     [rsp+2D0h+var_2A0], rcx
0x1800539be  lea     rcx, unk_18006F5A7
0x1800539c5  mov     [rsp+2D0h+var_2A8], rcx
0x1800539ca  mov     word ptr [rsp+2D0h+var_2B0], ax; int
0x1800539cf  mov     r9d, r13d
0x1800539d2  mov     r8d, r13d
0x1800539d5  lea     rdx, [rsp+2D0h+var_288]
0x1800539da  mov     rcx, [r14]
0x1800539dd  call    cs:__imp_CoreUICallSend
0x1800539e3  mov     rcx, [rbp+1D8h]; this
0x1800539ea  test    eax, eax
0x1800539ec  js      short loc_180053A52
0x1800539ee  jmp     short loc_1800539F9
0x1800539f0  mov     rcx, rbx; this
0x1800539f3  call    ?StartRetryTimer@ReconnectableEndpoint@@IEAAJXZ; ReconnectableEndpoint::StartRetryTimer(void)
0x1800539f8  nop
0x1800539f9  mov     rcx, [rsp+2D0h+var_280]
0x1800539fe  test    rcx, rcx
0x180053a01  jz      short loc_180053A10
0x180053a03  mov     rax, [rcx]
0x180053a06  mov     rax, [rax+10h]
0x180053a0a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180053a0f  nop
0x180053a10  xor     eax, eax
0x180053a12  mov     rcx, [rbp+1D0h+var_30]
0x180053a19  xor     rcx, rsp; StackCookie
0x180053a1c  call    __security_check_cookie
0x180053a21  lea     r11, [rsp+2D0h+var_20]
0x180053a29  mov     rbx, [r11+38h]
0x180053a2d  mov     rsi, [r11+40h]
0x180053a31  mov     rsp, r11
0x180053a34  pop     r15
0x180053a36  pop     r14
0x180053a38  pop     r13
0x180053a3a  pop     rdi
0x180053a3b  pop     rbp
0x180053a3c  retn
0x180053a3d  mov     r9d, eax; char *
0x180053a40  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\virtualization"...
0x180053a47  mov     edx, 0B2h; void *
0x180053a4c  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180053a52  mov     r9d, eax; char *
0x180053a55  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\virtualization"...
0x180053a5c  mov     edx, 0BCh; void *
0x180053a61  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180053a67  mov     r9d, eax; char *
0x180053a6a  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\virtualization"...
0x180053a71  mov     edx, 97h; void *
0x180053a76  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180053a7c  mov     r9d, eax; char *
0x180053a7f  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\virtualization"...
0x180053a86  mov     edx, 98h; void *
0x180053a8b  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180053a91  mov     r9d, eax; char *
0x180053a94  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\virtualization"...
0x180053a9b  mov     edx, 9Ah; void *
0x180053aa0  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180053aa6  mov     r9d, eax; char *
0x180053aa9  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\virtualization"...
0x180053ab0  mov     edx, 9Fh; void *
0x180053ab5  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180053abb  mov     r9d, eax; char *
0x180053abe  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\virtualization"...
0x180053ac5  mov     edx, 0A5h; void *
0x180053aca  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
0x180053ad0  mov     r9d, eax; char *
0x180053ad3  lea     r8, aMincoreTextinp_10; "mincore\\textinput\\dev\\virtualization"...
0x180053ada  mov     edx, 0A7h; void *
0x180053adf  call    ?_FailFast_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_FailFast_Hr(void *,uint,char const *,long)
```
