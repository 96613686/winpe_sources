# AudioServerCreateStream

- ea: `0x1800826a0`
- end: `0x1800829a7`
- name: `AudioServerCreateStream`
- size: `775`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, int, __int64)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000accc`
- `0x1800126bc`
- `0x18001b3d0`
- `0x18004ec10`
- `0x18004ec40`
- `0x180052184`
- `0x1800669e0`
- `0x1800826a0`
- `0x1800cf8c0`
- `0x1800cfd9c`
- `0x1800d8458`
- `0x1800d8530`
- `0x1800d87e4`
- `0x1800d8800`
- `0x1800dc3e4`
- `0x1800dc604`
- `0x1800dc628`
- `0x18011d230`
- `0x18011ed40`
- `0x18016b010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180082978`
- `ntdll!EtwEventActivityIdControl` at `0x180082978`
- `RPCRT4!RpcImpersonateClient` at `0x180082846`
- `RPCRT4!RpcImpersonateClient` at `0x180082846`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800828b7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800828d8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800828b7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800828d8`

## string_xrefs

- `0x18008275f`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180082864`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800828a3`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800828c5`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800828e6`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800827c5`: `AudioServerCreateStream`
- `0x180082811`: `AudioServerCreateStream`

## pseudocode

```c
__int64 __fastcall AudioServerCreateStream(
        void *a1,
        unsigned int a2,
        __int64 a3,
        int a4,
        unsigned int a5,
        unsigned __int16 *a6)
{
  __int64 (__fastcall *v10)(struct IAudioPolicyManager *, _QWORD, __int64 *); // rbx
  int v11; // eax
  unsigned int v12; // ebx
  __int64 v13; // rdx
  struct _TP_TIMER **v14; // rax
  struct _TP_TIMER **v15; // rsi
  struct _TP_TIMER *v16; // rbx
  unsigned int v17; // edi
  struct AudioSrvTelemetryProvider *v18; // rax
  struct _TP_TIMER **v19; // rax
  struct _TP_TIMER **v20; // rsi
  struct _TP_TIMER *v21; // rbx
  unsigned int v22; // edi
  struct AudioSrvTelemetryProvider *v23; // rax
  RPC_STATUS v24; // ebx
  __int64 v25; // rdx
  unsigned __int64 v26; // r9
  int ThreadLogonSessionStringSid; // eax
  const char *v28; // r9
  const char *v29; // r9
  int Stream; // eax
  int pftDueTime; // [rsp+20h] [rbp-59h]
  unsigned __int16 *v33; // [rsp+40h] [rbp-39h] BYREF
  __int64 v34; // [rsp+48h] [rbp-31h] BYREF
  __int64 v35; // [rsp+50h] [rbp-29h] BYREF
  int v36; // [rsp+58h] [rbp-21h] BYREF
  __int64 v37; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v38[16]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v39[16]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  v33 = a6;
  SetActivityIdFromVadServer::SetActivityIdFromVadServer((SetActivityIdFromVadServer *)v38, a1);
  v37 = 0;
  v10 = *(__int64 (__fastcall **)(struct IAudioPolicyManager *, _QWORD, __int64 *))(*(_QWORD *)g_PolicyManager + 32LL);
  wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy>::reset(&v37);
  v11 = v10(g_PolicyManager, 0, &v37);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v36 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, bool, _QWORD, int *))(*(_QWORD *)v37 + 152LL))(v37, a2 == 1, a5, &v36);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = 2951;
      goto LABEL_5;
    }
    if ( !v36 )
    {
      v12 = -2005139338;
      goto LABEL_29;
    }
    v35 = 0;
    v34 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
    {
      v14 = (struct _TP_TIMER **)operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v15 = v14;
      if ( v14 )
      {
        v16 = (struct _TP_TIMER *)g_AudioHealthMonitor;
        v17 = g_AudioSrvWatchDogTimerInMs;
        v18 = AudioSrvTelemetryProvider::Instance();
        v14 = CWatchdogTimer<1>::CWatchdogTimer<1>(
                v15,
                *((struct _TP_TIMER **)v18 + 1),
                v17,
                (struct _TP_TIMER *)L"AudioServerCreateStream",
                v16);
      }
      std::unique_ptr<CWatchdogTimer<1>>::reset(&v35, v14);
    }
    else
    {
      v19 = (struct _TP_TIMER **)operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v20 = v19;
      if ( v19 )
      {
        v21 = (struct _TP_TIMER *)g_AudioHealthMonitor;
        v22 = g_AudioSrvWatchDogTimerInMs;
        v23 = AudioSrvTelemetryProvider::Instance();
        v19 = CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(
                v20,
                *((struct _TP_TIMER **)v23 + 1),
                v22,
                (struct _TP_TIMER *)L"AudioServerCreateStream",
                v21);
      }
      std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v34, v19);
    }
    v33 = 0;
    v24 = RpcImpersonateClient(0);
    if ( v24 )
    {
      v12 = v24 | 0x80010000;
      v25 = 2966;
      v26 = v12;
    }
    else
    {
      ThreadLogonSessionStringSid = GetThreadLogonSessionStringSid(&v33);
      v12 = ThreadLogonSessionStringSid;
      if ( ThreadLogonSessionStringSid < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0xB9E,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
          (const char *)(unsigned int)ThreadLogonSessionStringSid,
          pftDueTime);
        if ( !RevertToSelf() )
          wil::details::in1diag3::_Log_GetLastError(
            retaddr,
            (void *)0xB9B,
            (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
            v28);
        goto LABEL_18;
      }
      if ( !RevertToSelf() )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0xB9B,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
          v29);
      pftDueTime = a4;
      Stream = CVADServer::CreateStream(a1, v37, a2, a3);
      v12 = Stream;
      if ( Stream >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
        std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v34);
        std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v35);
        v12 = 0;
        goto LABEL_29;
      }
      if ( (unsigned int)(Stream + 2005139335) <= 2 || Stream == -2005139370 )
        goto LABEL_18;
      v26 = (unsigned int)Stream;
      v25 = 2983;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v25,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)v26,
      pftDueTime);
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v33);
    std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v34);
    std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v35);
    goto LABEL_29;
  }
  v13 = 2942;
LABEL_5:
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v13,
    (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
    (const char *)(unsigned int)v11,
    pftDueTime);
LABEL_29:
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v37);
  EtwEventActivityIdControl(4, v39);
  return v12;
}

```

## disassembly

```asm
0x1800826a0  mov     [rsp-8+arg_18], rbx
0x1800826a5  push    rbp
0x1800826a6  push    rsi
0x1800826a7  push    rdi
0x1800826a8  push    r12
0x1800826aa  push    r13
0x1800826ac  push    r14
0x1800826ae  push    r15
0x1800826b0  lea     rbp, [rsp-17h]
0x1800826b5  sub     rsp, 90h
0x1800826bc  mov     rax, cs:__security_cookie
0x1800826c3  xor     rax, rsp
0x1800826c6  mov     [rbp+47h+var_38], rax
0x1800826ca  mov     rdi, [rbp+47h+arg_28]
0x1800826ce  mov     r14d, edx
0x1800826d1  mov     rdx, rcx; void *
0x1800826d4  mov     [rbp+47h+var_80], rdi
0x1800826d8  mov     r15, rcx
0x1800826db  mov     r12, r9
0x1800826de  lea     rcx, [rbp+47h+var_58]; this
0x1800826e2  mov     r13, r8
0x1800826e5  call    ??0SetActivityIdFromVadServer@@QEAA@PEAX@Z
0x1800826ea  mov     rax, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA
0x1800826f1  xor     esi, esi
0x1800826f3  mov     [rbp+47h+var_60], rsi
0x1800826f7  mov     rcx, [rax]
0x1800826fa  mov     rbx, [rcx+20h]
0x1800826fe  lea     rcx, [rbp+47h+var_60]
0x180082702  call    ?reset@?$com_ptr_t@UIAudioProcess@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ
0x180082707  mov     rcx, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA
0x18008270e  lea     r8, [rbp+47h+var_60]
0x180082712  xor     edx, edx
0x180082714  mov     rax, rbx
0x180082717  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008271c  mov     ebx, eax
0x18008271e  test    eax, eax
0x180082720  jns     short loc_180082729
0x180082722  mov     edx, 0B7Eh
0x180082727  jmp     short loc_18008275B
0x180082729  mov     rcx, [rbp+47h+var_60]
0x18008272d  lea     r9, [rbp+47h+var_68]
0x180082731  mov     r8d, [rbp+47h+arg_20]
0x180082735  mov     edx, esi
0x180082737  mov     [rbp+47h+var_68], esi
0x18008273a  cmp     r14d, 1
0x18008273e  mov     rax, [rcx]
0x180082741  setz    dl
0x180082744  mov     rax, [rax+98h]
0x18008274b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082750  mov     ebx, eax
0x180082752  test    eax, eax
0x180082754  jns     short loc_180082773
0x180082756  mov     edx, 0B87h; void *
0x18008275b  mov     rcx, [rbp+4Fh]; this
0x18008275f  lea     r8, aAvcoreAudiocor_7
0x180082766  mov     r9d, eax; char *
0x180082769  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18008276e  jmp     loc_180082966
0x180082773  cmp     [rbp+47h+var_68], esi
0x180082776  jnz     short loc_180082782
0x180082778  mov     ebx, 887C0076h
0x18008277d  jmp     loc_180082966
0x180082782  mov     [rbp+47h+var_70], rsi
0x180082786  mov     [rbp+47h+var_78], rsi
0x18008278a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A
0x180082791  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ
0x180082796  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008279d  mov     ecx, 38h ; '8'; unsigned __int64
0x1800827a2  test    al, al
0x1800827a4  jz      short loc_1800827F2
0x1800827a6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z
0x1800827ab  mov     rsi, rax
0x1800827ae  test    rax, rax
0x1800827b1  jz      short loc_1800827E4
0x1800827b3  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime
0x1800827ba  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA
0x1800827c0  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ
0x1800827c5  lea     r9, aAudioservercre
0x1800827cc  mov     qword ptr [rsp+0C0h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x1800827d1  mov     r8d, edi
0x1800827d4  mov     rcx, rsi; pv
0x1800827d7  mov     rdx, [rax+8]
0x1800827db  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z
0x1800827e0  mov     rdi, [rbp+47h+var_80]
0x1800827e4  mov     rdx, rax
0x1800827e7  lea     rcx, [rbp+47h+var_70]
0x1800827eb  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z
0x1800827f0  jmp     short loc_18008283C
0x1800827f2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z
0x1800827f7  mov     rsi, rax
0x1800827fa  test    rax, rax
0x1800827fd  jz      short loc_180082830
0x1800827ff  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime
0x180082806  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA
0x18008280c  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ
0x180082811  lea     r9, aAudioservercre
0x180082818  mov     qword ptr [rsp+0C0h+pftDueTime.dwLowDateTime], rbx; int
0x18008281d  mov     r8d, edi
0x180082820  mov     rcx, rsi; pv
0x180082823  mov     rdx, [rax+8]
0x180082827  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z
0x18008282c  mov     rdi, [rbp+47h+var_80]
0x180082830  mov     rdx, rax
0x180082833  lea     rcx, [rbp+47h+var_78]
0x180082837  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z
0x18008283c  xor     ecx, ecx; BindingHandle
0x18008283e  mov     [rbp+47h+var_80], 0
0x180082846  call    cs:__imp_RpcImpersonateClient
0x18008284c  mov     ebx, eax
0x18008284e  test    eax, eax
0x180082850  jz      short loc_180082890
0x180082852  or      ebx, 80010000h
0x180082858  mov     edx, 0B96h; void *
0x18008285d  mov     r9d, ebx; char *
0x180082860  mov     rcx, [rbp+4Fh]; this
0x180082864  lea     r8, aAvcoreAudiocor_7
0x18008286b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180082870  lea     rcx, [rbp+47h+var_80]
0x180082874  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082879  lea     rcx, [rbp+47h+var_78]
0x18008287d  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ
0x180082882  lea     rcx, [rbp+47h+var_70]
0x180082886  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ
0x18008288b  jmp     loc_180082966
0x180082890  lea     rcx, [rbp+47h+var_80]; unsigned __int16 **
0x180082894  call    ?GetThreadLogonSessionStringSid@@YAJPEAPEAG@Z
0x180082899  mov     ebx, eax
0x18008289b  test    eax, eax
0x18008289d  jns     short loc_1800828D8
0x18008289f  mov     rcx, [rbp+4Fh]; this
0x1800828a3  lea     r8, aAvcoreAudiocor_7
0x1800828aa  mov     r9d, eax; char *
0x1800828ad  mov     edx, 0B9Eh; void *
0x1800828b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800828b7  call    cs:__imp_RevertToSelf
0x1800828bd  test    eax, eax
0x1800828bf  jnz     short loc_180082870
0x1800828c1  mov     rcx, [rbp+4Fh]; this
0x1800828c5  lea     r8, aAvcoreAudiocor_7
0x1800828cc  mov     edx, 0B9Bh; void *
0x1800828d1  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z
0x1800828d6  jmp     short loc_180082870
0x1800828d8  call    cs:__imp_RevertToSelf
0x1800828de  test    eax, eax
0x1800828e0  jnz     short loc_1800828F7
0x1800828e2  mov     rcx, [rbp+4Fh]; this
0x1800828e6  lea     r8, aAvcoreAudiocor_7
0x1800828ed  mov     edx, 0B9Bh; void *
0x1800828f2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z
0x1800828f7  mov     rax, [rbp+47h+var_80]
0x1800828fb  mov     r9, r13
0x1800828fe  mov     rdx, [rbp+47h+var_60]
0x180082902  mov     r8d, r14d
0x180082905  mov     [rsp+0C0h+var_90], rdi
0x18008290a  mov     rcx, r15
0x18008290d  mov     [rsp+0C0h+var_98], rax
0x180082912  mov     qword ptr [rsp+0C0h+pftDueTime.dwLowDateTime], r12
0x180082917  call    ?CreateStream@CVADServer@@UEAAJPEAUIAudioProcess@@W4SYSTEM_AUDIO_STREAM_TYPE@@_J2PEBGPEAUSYSTEM_AUDIO_STREAM@@@Z
0x18008291c  mov     ebx, eax
0x18008291e  test    eax, eax
0x180082920  jns     short loc_180082949
0x180082922  lea     ecx, [rax+7783FF87h]
0x180082928  cmp     ecx, 2
0x18008292b  jbe     loc_180082870
0x180082931  cmp     eax, 887C0056h
0x180082936  jz      loc_180082870
0x18008293c  mov     r9d, eax
0x18008293f  mov     edx, 0BA7h
0x180082944  jmp     loc_180082860
0x180082949  lea     rcx, [rbp+47h+var_80]
0x18008294d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082952  lea     rcx, [rbp+47h+var_78]
0x180082956  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ
0x18008295b  lea     rcx, [rbp+47h+var_70]
0x18008295f  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ
0x180082964  xor     ebx, ebx
0x180082966  lea     rcx, [rbp+47h+var_60]
0x18008296a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x18008296f  lea     rdx, [rbp+47h+var_48]
0x180082973  mov     ecx, 4
0x180082978  call    cs:__imp_EtwEventActivityIdControl
0x18008297e  mov     eax, ebx
0x180082980  mov     rcx, [rbp+47h+var_38]
0x180082984  xor     rcx, rsp; StackCookie
0x180082987  call    __security_check_cookie
0x18008298c  mov     rbx, [rsp+0C0h+arg_18]
0x180082994  add     rsp, 90h
0x18008299b  pop     r15
0x18008299d  pop     r14
0x18008299f  pop     r13
0x1800829a1  pop     r12
0x1800829a3  pop     rdi
0x1800829a4  pop     rsi
0x1800829a5  pop     rbp
0x1800829a6  retn
```
