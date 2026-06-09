# DriverEntry

- ea: `0x18000d8b4`
- end: `0x18000dbcf`
- name: `DriverEntry`
- size: `795`
- prototype: ``
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x180035eec`

## callees

- `0x180001010`
- `0x180007b38`
- `0x18000bbf0`
- `0x18000cf98`
- `0x18000d614`
- `0x18000d8b4`
- `0x18000dbd8`
- `0x18000df20`
- `0x18000e04c`
- `0x18003f010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d9be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db59`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000d9be`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThreadId` at `0x18000db59`
- `WppRecorderUM!WppAutoLogStart` at `0x18000d94d`
- `WppRecorderUM!WppAutoLogStart` at `0x18000d94d`

## string_xrefs

- `0x18000da96`: `WdfDriverCreate failed`

## pseudocode

```c
__int64 __fastcall DriverEntry(__int64 a1, __int64 a2)
{
  char v4; // bl
  bool v5; // di
  bool v6; // si
  char CurrentThreadId; // al
  int v8; // r8d
  int v9; // edx
  int v10; // edi
  _DWORD *v11; // r8
  int v12; // r9d
  bool v13; // si
  char v14; // al
  int v15; // r8d
  int v16; // edx
  const struct wil::FailureInfo *v18; // rdx
  int v19; // [rsp+20h] [rbp-E0h]
  int v20; // [rsp+28h] [rbp-D8h]
  const char *v21; // [rsp+50h] [rbp-B0h] BYREF
  const char *v22; // [rsp+58h] [rbp-A8h] BYREF
  const char *v23; // [rsp+60h] [rbp-A0h] BYREF
  __int128 v24; // [rsp+68h] [rbp-98h] BYREF
  __int128 v25; // [rsp+78h] [rbp-88h]
  __int128 v26; // [rsp+88h] [rbp-78h]
  __int64 v27; // [rsp+98h] [rbp-68h]
  int v28[4]; // [rsp+A0h] [rbp-60h] BYREF
  __int128 v29; // [rsp+B0h] [rbp-50h]
  _BYTE v30[160]; // [rsp+C0h] [rbp-40h] BYREF
  int v31; // [rsp+1A0h] [rbp+A0h] BYREF
  int v32; // [rsp+1A8h] [rbp+A8h] BYREF

  *(_OWORD *)v28 = 0;
  v27 = 0;
  v29 = 0;
  v24 = 0;
  v25 = 0;
  v26 = 0;
  v4 = 1;
  qword_180057F20 = 0;
  WPP_MAIN_CB = 0;
  qword_180057F38 = 0;
  dword_180057F40 = 0;
  WPP_REGISTRATION_GUIDS = (__int64)WPP_ThisDir_CTLGUID_RdpIddIfrGuid;
  WPP_GLOBAL_Control = &WPP_MAIN_CB;
  qword_180057F28 = 1;
  WppInitUm();
  WppAutoLogStart(WPP_GLOBAL_Control, a1, a2);
  if ( wil::details::g_pfnLoggingCallback
    && (void (__fastcall *)(const struct wil::FailureInfo *))wil::details::g_pfnLoggingCallback != RdpIddLoggingProvider::ResultLoggingCallback )
  {
    memset_0(v30, 0, 0x98u);
    wil::details::WilFailFast((wil::details *)v30, v18);
  }
  wil::details::g_pfnLoggingCallback = (__int64)RdpIddLoggingProvider::ResultLoggingCallback;
  v5 = WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 25) >= 4u;
  v6 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
  if ( v5 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
  {
    CurrentThreadId = GetCurrentThreadId();
    LOBYTE(v8) = v6;
    LOBYTE(v9) = v5;
    WPP_RECORDER_AND_TRACE_SF_D(
      *((_QWORD *)WPP_GLOBAL_Control + 2),
      v9,
      v8,
      *((_QWORD *)WPP_GLOBAL_Control + 5),
      v19,
      v20,
      10,
      &WPP_70c27897107932ddeed0a391b27b7ece_Traceguids,
      CurrentThreadId);
  }
  *(_QWORD *)v28 = 32;
  v27 = 0;
  *(_QWORD *)&v24 = 56;
  *((_QWORD *)&v24 + 1) = RdpIdEvtDriverContextCleanup;
  *(_QWORD *)&v25 = 0;
  *((_QWORD *)&v25 + 1) = 0x100000001LL;
  *(_QWORD *)&v28[2] = RdpIdEvtDeviceAdd;
  v26 = 0;
  v29 = 0;
  v10 = (*(__int64 (__fastcall **)(__int64, __int64, __int64, __int128 *))(WdfFunctions_02025 + 456))(
          WdfDriverGlobals,
          a1,
          a2,
          &v24);
  if ( v10 >= 0 )
  {
    ReadDebugCtlFromRegistry();
    if ( gDebugCtrl )
      __debugbreak();
    if ( WPP_GLOBAL_Control == &WPP_GLOBAL_Control
      || (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) == 0
      || *((_BYTE *)WPP_GLOBAL_Control + 25) < 4u )
    {
      v4 = 0;
    }
    v13 = WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED;
    if ( v4 || WPP_RECORDER_INITIALIZED != (_UNKNOWN *)&WPP_RECORDER_INITIALIZED )
    {
      v14 = GetCurrentThreadId();
      LOBYTE(v15) = v13;
      LOBYTE(v16) = v4;
      WPP_RECORDER_AND_TRACE_SF_D(
        *((_QWORD *)WPP_GLOBAL_Control + 2),
        v16,
        v15,
        *((_QWORD *)WPP_GLOBAL_Control + 5),
        (int)v28,
        0,
        11,
        &WPP_70c27897107932ddeed0a391b27b7ece_Traceguids,
        v14);
    }
  }
  else
  {
    v11 = *(_DWORD **)(wil::details::static_lazy<RdpIddLoggingProvider>::get() + 8);
    if ( *v11 > 2u )
    {
      v31 = v10;
      v21 = "WdfDriverCreate failed";
      v32 = 95;
      v22 = "DriverEntry";
      v23 = "onecoreuap\\termsrv\\rdp_bin\\win\\rdpidd\\driver.cpp";
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(
        (_DWORD)v11,
        (unsigned int)byte_18004BF31,
        (_DWORD)v11,
        v12,
        (__int64)&v23,
        (__int64)&v32,
        (__int64)&v22,
        (__int64)&v21,
        (__int64)&v31);
    }
    WppCleanupUm();
  }
  return (unsigned int)v10;
}

```

## disassembly

```asm
0x18000d8b4  mov     [rsp-8+arg_0], rbx
0x18000d8b9  mov     [rsp-8+arg_8], rsi
0x18000d8be  push    rbp
0x18000d8bf  push    rdi
0x18000d8c0  push    r13
0x18000d8c2  push    r14
0x18000d8c4  push    r15
0x18000d8c6  lea     rbp, [rsp-60h]
0x18000d8cb  sub     rsp, 160h
0x18000d8d2  xorps   xmm1, xmm1
0x18000d8d5  xorps   xmm0, xmm0
0x18000d8d8  xor     eax, eax
0x18000d8da  mov     r14, rdx
0x18000d8dd  movups  xmmword ptr [rbp+80h+var_E0], xmm0
0x18000d8e1  mov     [rbp+80h+var_E8], rax
0x18000d8e5  mov     r15, rcx
0x18000d8e8  movups  [rbp+80h+var_D0], xmm0
0x18000d8ec  movups  [rsp+180h+var_118], xmm1
0x18000d8f1  movups  [rsp+180h+var_108], xmm1
0x18000d8f6  movups  [rbp+80h+var_F8], xmm1
0x18000d8fa  lea     ebx, [rax+1]
0x18000d8fd  mov     cs:qword_180057F20, rax
0x18000d904  mov     cs:WPP_MAIN_CB, rax
0x18000d90b  mov     cs:qword_180057F38, rax
0x18000d912  mov     cs:dword_180057F40, eax
0x18000d918  lea     rax, WPP_ThisDir_CTLGUID_RdpIddIfrGuid
0x18000d91f  mov     cs:WPP_REGISTRATION_GUIDS, rax
0x18000d926  lea     rax, WPP_MAIN_CB
0x18000d92d  mov     cs:WPP_GLOBAL_Control, rax
0x18000d934  mov     cs:qword_180057F28, rbx
0x18000d93b  call    WppInitUm
0x18000d940  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d947  mov     r8, r14
0x18000d94a  mov     rdx, r15
0x18000d94d  call    cs:__imp_WppAutoLogStart
0x18000d954  nop     dword ptr [rax+rax+00h]
0x18000d959  mov     rax, cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA
0x18000d960  lea     rcx, ?ResultLoggingCallback@RdpIddLoggingProvider@@SAXAEBUFailureInfo@wil@@@Z; RdpIddLoggingProvider::ResultLoggingCallback(wil::FailureInfo const &)
0x18000d967  test    rax, rax
0x18000d96a  jz      short loc_18000D975
0x18000d96c  cmp     rax, rcx
0x18000d96f  jnz     loc_18000DBB4
0x18000d975  mov     cs:?g_pfnLoggingCallback@details@wil@@3P6AXAEBUFailureInfo@2@@_EEA, rcx
0x18000d97c  mov     rax, cs:WPP_GLOBAL_Control
0x18000d983  lea     r13, WPP_GLOBAL_Control
0x18000d98a  cmp     rax, r13
0x18000d98d  jz      short loc_18000D99F
0x18000d98f  test    [rax+1Ch], bl
0x18000d992  jz      short loc_18000D99F
0x18000d994  cmp     byte ptr [rax+19h], 4
0x18000d998  jb      short loc_18000D99F
0x18000d99a  mov     dil, bl
0x18000d99d  jmp     short loc_18000D9A2
0x18000d99f  xor     dil, dil
0x18000d9a2  lea     rax, WPP_RECORDER_INITIALIZED
0x18000d9a9  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000d9b0  setnz   sil
0x18000d9b4  test    dil, dil
0x18000d9b7  jnz     short loc_18000D9BE
0x18000d9b9  test    sil, sil
0x18000d9bc  jz      short loc_18000D9FB
0x18000d9be  call    cs:__imp_GetCurrentThreadId
0x18000d9c5  nop     dword ptr [rax+rax+00h]
0x18000d9ca  mov     rcx, cs:WPP_GLOBAL_Control
0x18000d9d1  mov     r8b, sil; int
0x18000d9d4  mov     dword ptr [rsp+180h+var_140], eax; char
0x18000d9d8  mov     dl, dil; int
0x18000d9db  lea     rax, WPP_70c27897107932ddeed0a391b27b7ece_Traceguids
0x18000d9e2  mov     [rsp+180h+MessageGuid], rax; MessageGuid
0x18000d9e7  mov     r9, [rcx+28h]; int
0x18000d9eb  mov     rcx, [rcx+10h]; int
0x18000d9ef  mov     [rsp+180h+var_150], 0Ah; __int16
0x18000d9f6  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000d9fb  xor     eax, eax
0x18000d9fd  mov     qword ptr [rbp+80h+var_E0], 20h ; ' '
0x18000da05  mov     [rbp+80h+var_E8], rax
0x18000da09  lea     rcx, [rbp+80h+var_E0]
0x18000da0d  xorps   xmm0, xmm0
0x18000da10  mov     qword ptr [rsp+180h+var_158], 0; int
0x18000da19  movups  [rsp+180h+var_118], xmm0
0x18000da1e  lea     rax, ?RdpIdEvtDriverContextCleanup@@YAXPEAX@Z; RdpIdEvtDriverContextCleanup(void *)
0x18000da25  mov     dword ptr [rsp+180h+var_118], 38h ; '8'
0x18000da2d  mov     qword ptr [rsp+180h+var_118+8], rax
0x18000da32  lea     r9, [rsp+180h+var_118]
0x18000da37  movups  [rsp+180h+var_108], xmm0
0x18000da3c  lea     rax, ?RdpIdEvtDeviceAdd@@YAJPEAUWDFDRIVER__@@PEAUWDFDEVICE_INIT@@@Z; RdpIdEvtDeviceAdd(WDFDRIVER__ *,WDFDEVICE_INIT *)
0x18000da43  mov     dword ptr [rbp+80h+var_108+8], ebx
0x18000da46  mov     qword ptr [rbp+80h+var_E0+8], rax
0x18000da4a  mov     r8, r14
0x18000da4d  mov     rax, cs:WdfFunctions_02025
0x18000da54  mov     rdx, r15
0x18000da57  movups  [rbp+80h+var_F8], xmm0
0x18000da5b  mov     dword ptr [rbp+80h+var_108+0Ch], ebx
0x18000da5e  movdqu  [rbp+80h+var_D0], xmm0
0x18000da63  mov     rax, [rax+1C8h]
0x18000da6a  mov     qword ptr [rsp+180h+var_160], rcx; int
0x18000da6f  mov     rcx, cs:WdfDriverGlobals
0x18000da76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da7b  mov     edi, eax
0x18000da7d  test    eax, eax
0x18000da7f  jns     loc_18000DB16
0x18000da85  call    ?get@?$static_lazy@VRdpIddLoggingProvider@@@details@wil@@QEAAPEAVRdpIddLoggingProvider@@P6AXXZ@Z; wil::details::static_lazy<RdpIddLoggingProvider>::get(void (*)(void))
0x18000da8a  mov     r8, [rax+8]
0x18000da8e  mov     ecx, [r8]
0x18000da91  cmp     ecx, 2
0x18000da94  jbe     short loc_18000DB0F
0x18000da96  lea     rax, aWdfdrivercreat; "WdfDriverCreate failed"
0x18000da9d  mov     [rbp+80h+arg_10], edi
0x18000daa3  mov     [rsp+180h+var_130], rax
0x18000daa8  lea     rdx, byte_18004BF31
0x18000daaf  lea     rax, aDriverentry; "DriverEntry"
0x18000dab6  mov     [rbp+80h+arg_18], 5Fh ; '_'
0x18000dac0  mov     [rsp+180h+var_128], rax
0x18000dac5  mov     rcx, r8
0x18000dac8  lea     rax, aOnecoreuapTerm_10; "onecoreuap\\termsrv\\rdp_bin\\win\\rdpi"...
0x18000dacf  mov     [rsp+180h+var_120], rax
0x18000dad4  lea     rax, [rbp+80h+arg_10]
0x18000dadb  mov     qword ptr [rsp+180h+var_140], rax
0x18000dae0  lea     rax, [rsp+180h+var_130]
0x18000dae5  mov     [rsp+180h+MessageGuid], rax
0x18000daea  lea     rax, [rsp+180h+var_128]
0x18000daef  mov     qword ptr [rsp+180h+var_150], rax
0x18000daf4  lea     rax, [rbp+80h+arg_18]
0x18000dafb  mov     qword ptr [rsp+180h+var_158], rax
0x18000db00  lea     rax, [rsp+180h+var_120]
0x18000db05  mov     qword ptr [rsp+180h+var_160], rax
0x18000db0a  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U1@U1@U2@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@334@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &)
0x18000db0f  call    WppCleanupUm
0x18000db14  jmp     short loc_18000DB95
0x18000db16  call    ?ReadDebugCtlFromRegistry@@YAXXZ; ReadDebugCtlFromRegistry(void)
0x18000db1b  cmp     cs:?gDebugCtrl@@3URDPIDD_DEBUG_CTRL@@A, 0; RDPIDD_DEBUG_CTRL gDebugCtrl
0x18000db22  jz      short loc_18000DB25
0x18000db24  int     3; Trap to Debugger
0x18000db25  mov     rax, cs:WPP_GLOBAL_Control
0x18000db2c  cmp     rax, r13
0x18000db2f  jz      short loc_18000DB3C
0x18000db31  test    [rax+1Ch], bl
0x18000db34  jz      short loc_18000DB3C
0x18000db36  cmp     byte ptr [rax+19h], 4
0x18000db3a  jnb     short loc_18000DB3E
0x18000db3c  xor     bl, bl
0x18000db3e  lea     rax, WPP_RECORDER_INITIALIZED
0x18000db45  cmp     cs:WPP_RECORDER_INITIALIZED, rax
0x18000db4c  setnz   sil
0x18000db50  test    bl, bl
0x18000db52  jnz     short loc_18000DB59
0x18000db54  test    sil, sil
0x18000db57  jz      short loc_18000DB95
0x18000db59  call    cs:__imp_GetCurrentThreadId
0x18000db60  nop     dword ptr [rax+rax+00h]
0x18000db65  mov     rcx, cs:WPP_GLOBAL_Control
0x18000db6c  mov     r8b, sil; int
0x18000db6f  mov     dword ptr [rsp+180h+var_140], eax; char
0x18000db73  mov     dl, bl; int
0x18000db75  lea     rax, WPP_70c27897107932ddeed0a391b27b7ece_Traceguids
0x18000db7c  mov     [rsp+180h+MessageGuid], rax; MessageGuid
0x18000db81  mov     r9, [rcx+28h]; int
0x18000db85  mov     rcx, [rcx+10h]; int
0x18000db89  mov     [rsp+180h+var_150], 0Bh; __int16
0x18000db90  call    WPP_RECORDER_AND_TRACE_SF_D
0x18000db95  lea     r11, [rsp+180h+var_20]
0x18000db9d  mov     eax, edi
0x18000db9f  mov     rbx, [r11+30h]
0x18000dba3  mov     rsi, [r11+38h]
0x18000dba7  mov     rsp, r11
0x18000dbaa  pop     r15
0x18000dbac  pop     r14
0x18000dbae  pop     r13
0x18000dbb0  pop     rdi
0x18000dbb1  pop     rbp
0x18000dbb2  retn
0x18000dbb4  xor     edx, edx; Val
0x18000dbb6  lea     rcx, [rbp+80h+var_C0]; void *
0x18000dbba  mov     r8d, 98h; Size
0x18000dbc0  call    memset_0
0x18000dbc5  lea     rcx, [rbp+80h+var_C0]; this
0x18000dbc9  call    ?WilFailFast@details@wil@@YAXAEBUFailureInfo@2@@Z; wil::details::WilFailFast(wil::FailureInfo const &)
```
