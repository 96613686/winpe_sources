# AudioServerCreateStream

- ea: `0x1800821a0`
- end: `0x1800824a7`
- name: `AudioServerCreateStream`
- size: `775`
- prototype: `__int64 __fastcall(void *, unsigned int, __int64, int, unsigned int, unsigned __int16 *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, loader_planting, installer_update, broker_com_uri`

## callees

- `0x18000ae1c`
- `0x18001280c`
- `0x18001b520`
- `0x18004e780`
- `0x18004e7b0`
- `0x180051cf4`
- `0x180066550`
- `0x1800821a0`
- `0x1800cd8d0`
- `0x1800cddac`
- `0x1800d6468`
- `0x1800d6540`
- `0x1800d67f4`
- `0x1800d6810`
- `0x1800da3f4`
- `0x1800da614`
- `0x1800da638`
- `0x18011d480`
- `0x18011ef90`
- `0x18016c010`

## import_xrefs

- `ntdll!EtwEventActivityIdControl` at `0x180082478`
- `ntdll!EtwEventActivityIdControl` at `0x180082478`
- `RPCRT4!RpcImpersonateClient` at `0x180082346`
- `RPCRT4!RpcImpersonateClient` at `0x180082346`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800823b7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800823d8`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800823b7`
- `api-ms-win-security-base-l1-1-0!RevertToSelf` at `0x1800823d8`

## string_xrefs

- `0x18008225f`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x180082364`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800823a3`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800823c5`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800823e6`: `avcore\audiocore\server\audiosrv\dll\vadserver.cpp`
- `0x1800822c5`: `AudioServerCreateStream`
- `0x180082311`: `AudioServerCreateStream`

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
  void *v14; // rax
  void *v15; // rsi
  struct _FILETIME v16; // rbx
  void *v17; // rax
  void *v18; // rsi
  struct _FILETIME v19; // rbx
  RPC_STATUS v20; // ebx
  __int64 v21; // rdx
  unsigned __int64 v22; // r9
  int ThreadLogonSessionStringSid; // eax
  const char *v24; // r9
  const char *v25; // r9
  int Stream; // eax
  int pftDueTime; // [rsp+20h] [rbp-59h]
  unsigned __int16 *v29; // [rsp+40h] [rbp-39h] BYREF
  __int64 v30; // [rsp+48h] [rbp-31h] BYREF
  __int64 v31; // [rsp+50h] [rbp-29h] BYREF
  int v32; // [rsp+58h] [rbp-21h] BYREF
  __int64 v33; // [rsp+60h] [rbp-19h] BYREF
  _BYTE v34[16]; // [rsp+68h] [rbp-11h] BYREF
  _BYTE v35[16]; // [rsp+78h] [rbp-1h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+C8h] [rbp+4Fh]

  v29 = a6;
  SetActivityIdFromVadServer::SetActivityIdFromVadServer((SetActivityIdFromVadServer *)v34, a1);
  v33 = 0;
  v10 = *(__int64 (__fastcall **)(struct IAudioPolicyManager *, _QWORD, __int64 *))(*(_QWORD *)g_PolicyManager + 32LL);
  wil::com_ptr_t<IAudioProcess,wil::err_returncode_policy>::reset(&v33);
  v11 = v10(g_PolicyManager, 0, &v33);
  v12 = v11;
  if ( v11 >= 0 )
  {
    v32 = 0;
    v11 = (*(__int64 (__fastcall **)(__int64, bool, _QWORD, int *))(*(_QWORD *)v33 + 152LL))(v33, a2 == 1, a5, &v32);
    v12 = v11;
    if ( v11 < 0 )
    {
      v13 = 2951;
      goto LABEL_5;
    }
    if ( !v32 )
    {
      v12 = -2005139338;
      goto LABEL_29;
    }
    v31 = 0;
    v30 = 0;
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
    {
      v14 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v15 = v14;
      if ( v14 )
      {
        v16 = g_AudioHealthMonitor;
        AudioSrvTelemetryProvider::Instance();
        v14 = (void *)CWatchdogTimer<1>::CWatchdogTimer<1>(v15, v16);
      }
      std::unique_ptr<CWatchdogTimer<1>>::reset(&v31, v14);
    }
    else
    {
      v17 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
      v18 = v17;
      if ( v17 )
      {
        v19 = g_AudioHealthMonitor;
        AudioSrvTelemetryProvider::Instance();
        v17 = (void *)CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(v18, v19);
      }
      std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v30, v17);
    }
    v29 = 0;
    v20 = RpcImpersonateClient(0);
    if ( v20 )
    {
      v12 = v20 | 0x80010000;
      v21 = 2966;
      v22 = v12;
    }
    else
    {
      ThreadLogonSessionStringSid = GetThreadLogonSessionStringSid(&v29);
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
            v24);
        goto LABEL_18;
      }
      if ( !RevertToSelf() )
        wil::details::in1diag3::_Log_GetLastError(
          retaddr,
          (void *)0xB9B,
          (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
          v25);
      pftDueTime = a4;
      Stream = CVADServer::CreateStream(a1, v33, a2, a3);
      v12 = Stream;
      if ( Stream >= 0 )
      {
        wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
        std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v30);
        std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v31);
        v12 = 0;
        goto LABEL_29;
      }
      if ( (unsigned int)(Stream + 2005139335) <= 2 || Stream == -2005139370 )
        goto LABEL_18;
      v22 = (unsigned int)Stream;
      v21 = 2983;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)v21,
      (unsigned int)"avcore\\audiocore\\server\\audiosrv\\dll\\vadserver.cpp",
      (const char *)v22,
      pftDueTime);
LABEL_18:
    wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void * (*)(void *),&void * LocalFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(&v29);
    std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v30);
    std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v31);
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
  wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v33);
  EtwEventActivityIdControl(4, v35);
  return v12;
}

```

## disassembly

```asm
0x1800821a0  mov     [rsp-8+arg_18], rbx
0x1800821a5  push    rbp
0x1800821a6  push    rsi
0x1800821a7  push    rdi
0x1800821a8  push    r12
0x1800821aa  push    r13
0x1800821ac  push    r14
0x1800821ae  push    r15
0x1800821b0  lea     rbp, [rsp-17h]
0x1800821b5  sub     rsp, 90h
0x1800821bc  mov     rax, cs:__security_cookie
0x1800821c3  xor     rax, rsp
0x1800821c6  mov     [rbp+47h+var_38], rax
0x1800821ca  mov     rdi, [rbp+47h+arg_28]
0x1800821ce  mov     r14d, edx
0x1800821d1  mov     rdx, rcx; void *
0x1800821d4  mov     [rbp+47h+var_80], rdi
0x1800821d8  mov     r15, rcx
0x1800821db  mov     r12, r9
0x1800821de  lea     rcx, [rbp+47h+var_58]; this
0x1800821e2  mov     r13, r8
0x1800821e5  call    ??0SetActivityIdFromVadServer@@QEAA@PEAX@Z
0x1800821ea  mov     rax, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA
0x1800821f1  xor     esi, esi
0x1800821f3  mov     [rbp+47h+var_60], rsi
0x1800821f7  mov     rcx, [rax]
0x1800821fa  mov     rbx, [rcx+20h]
0x1800821fe  lea     rcx, [rbp+47h+var_60]
0x180082202  call    ?reset@?$com_ptr_t@UIAudioProcess@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ
0x180082207  mov     rcx, cs:?g_PolicyManager@@3PEAUIAudioPolicyManager@@EA
0x18008220e  lea     r8, [rbp+47h+var_60]
0x180082212  xor     edx, edx
0x180082214  mov     rax, rbx
0x180082217  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18008221c  mov     ebx, eax
0x18008221e  test    eax, eax
0x180082220  jns     short loc_180082229
0x180082222  mov     edx, 0B7Eh
0x180082227  jmp     short loc_18008225B
0x180082229  mov     rcx, [rbp+47h+var_60]
0x18008222d  lea     r9, [rbp+47h+var_68]
0x180082231  mov     r8d, [rbp+47h+arg_20]
0x180082235  mov     edx, esi
0x180082237  mov     [rbp+47h+var_68], esi
0x18008223a  cmp     r14d, 1
0x18008223e  mov     rax, [rcx]
0x180082241  setz    dl
0x180082244  mov     rax, [rax+98h]
0x18008224b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180082250  mov     ebx, eax
0x180082252  test    eax, eax
0x180082254  jns     short loc_180082273
0x180082256  mov     edx, 0B87h; void *
0x18008225b  mov     rcx, [rbp+4Fh]; this
0x18008225f  lea     r8, aAvcoreAudiocor_7
0x180082266  mov     r9d, eax; char *
0x180082269  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x18008226e  jmp     loc_180082466
0x180082273  cmp     [rbp+47h+var_68], esi
0x180082276  jnz     short loc_180082282
0x180082278  mov     ebx, 887C0076h
0x18008227d  jmp     loc_180082466
0x180082282  mov     [rbp+47h+var_70], rsi
0x180082286  mov     [rbp+47h+var_78], rsi
0x18008228a  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A
0x180082291  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ
0x180082296  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18008229d  mov     ecx, 38h ; '8'; unsigned __int64
0x1800822a2  test    al, al
0x1800822a4  jz      short loc_1800822F2
0x1800822a6  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z
0x1800822ab  mov     rsi, rax
0x1800822ae  test    rax, rax
0x1800822b1  jz      short loc_1800822E4
0x1800822b3  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime
0x1800822ba  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA
0x1800822c0  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ
0x1800822c5  lea     r9, aAudioservercre
0x1800822cc  mov     qword ptr [rsp+0C0h+pftDueTime.dwLowDateTime], rbx; pftDueTime
0x1800822d1  mov     r8d, edi
0x1800822d4  mov     rcx, rsi; pv
0x1800822d7  mov     rdx, [rax+8]
0x1800822db  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z
0x1800822e0  mov     rdi, [rbp+47h+var_80]
0x1800822e4  mov     rdx, rax
0x1800822e7  lea     rcx, [rbp+47h+var_70]
0x1800822eb  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z
0x1800822f0  jmp     short loc_18008233C
0x1800822f2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z
0x1800822f7  mov     rsi, rax
0x1800822fa  test    rax, rax
0x1800822fd  jz      short loc_180082330
0x1800822ff  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime
0x180082306  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA
0x18008230c  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ
0x180082311  lea     r9, aAudioservercre
0x180082318  mov     qword ptr [rsp+0C0h+pftDueTime.dwLowDateTime], rbx; int
0x18008231d  mov     r8d, edi
0x180082320  mov     rcx, rsi; pv
0x180082323  mov     rdx, [rax+8]
0x180082327  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z
0x18008232c  mov     rdi, [rbp+47h+var_80]
0x180082330  mov     rdx, rax
0x180082333  lea     rcx, [rbp+47h+var_78]
0x180082337  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z
0x18008233c  xor     ecx, ecx; BindingHandle
0x18008233e  mov     [rbp+47h+var_80], 0
0x180082346  call    cs:__imp_RpcImpersonateClient
0x18008234c  mov     ebx, eax
0x18008234e  test    eax, eax
0x180082350  jz      short loc_180082390
0x180082352  or      ebx, 80010000h
0x180082358  mov     edx, 0B96h; void *
0x18008235d  mov     r9d, ebx; char *
0x180082360  mov     rcx, [rbp+4Fh]; this
0x180082364  lea     r8, aAvcoreAudiocor_7
0x18008236b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x180082370  lea     rcx, [rbp+47h+var_80]
0x180082374  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082379  lea     rcx, [rbp+47h+var_78]
0x18008237d  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ
0x180082382  lea     rcx, [rbp+47h+var_70]
0x180082386  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ
0x18008238b  jmp     loc_180082466
0x180082390  lea     rcx, [rbp+47h+var_80]; unsigned __int16 **
0x180082394  call    ?GetThreadLogonSessionStringSid@@YAJPEAPEAG@Z
0x180082399  mov     ebx, eax
0x18008239b  test    eax, eax
0x18008239d  jns     short loc_1800823D8
0x18008239f  mov     rcx, [rbp+4Fh]; this
0x1800823a3  lea     r8, aAvcoreAudiocor_7
0x1800823aa  mov     r9d, eax; char *
0x1800823ad  mov     edx, 0B9Eh; void *
0x1800823b2  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z
0x1800823b7  call    cs:__imp_RevertToSelf
0x1800823bd  test    eax, eax
0x1800823bf  jnz     short loc_180082370
0x1800823c1  mov     rcx, [rbp+4Fh]; this
0x1800823c5  lea     r8, aAvcoreAudiocor_7
0x1800823cc  mov     edx, 0B9Bh; void *
0x1800823d1  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z
0x1800823d6  jmp     short loc_180082370
0x1800823d8  call    cs:__imp_RevertToSelf
0x1800823de  test    eax, eax
0x1800823e0  jnz     short loc_1800823F7
0x1800823e2  mov     rcx, [rbp+4Fh]; this
0x1800823e6  lea     r8, aAvcoreAudiocor_7
0x1800823ed  mov     edx, 0B9Bh; void *
0x1800823f2  call    ?_Log_GetLastError@in1diag3@details@wil@@YAXPEAXIPEBD@Z
0x1800823f7  mov     rax, [rbp+47h+var_80]
0x1800823fb  mov     r9, r13
0x1800823fe  mov     rdx, [rbp+47h+var_60]
0x180082402  mov     r8d, r14d
0x180082405  mov     [rsp+0C0h+var_90], rdi
0x18008240a  mov     rcx, r15
0x18008240d  mov     [rsp+0C0h+var_98], rax
0x180082412  mov     qword ptr [rsp+0C0h+pftDueTime.dwLowDateTime], r12
0x180082417  call    ?CreateStream@CVADServer@@UEAAJPEAUIAudioProcess@@W4SYSTEM_AUDIO_STREAM_TYPE@@_J2PEBGPEAUSYSTEM_AUDIO_STREAM@@@Z
0x18008241c  mov     ebx, eax
0x18008241e  test    eax, eax
0x180082420  jns     short loc_180082449
0x180082422  lea     ecx, [rax+7783FF87h]
0x180082428  cmp     ecx, 2
0x18008242b  jbe     loc_180082370
0x180082431  cmp     eax, 887C0056h
0x180082436  jz      loc_180082370
0x18008243c  mov     r9d, eax
0x18008243f  mov     edx, 0BA7h
0x180082444  jmp     loc_180082360
0x180082449  lea     rcx, [rbp+47h+var_80]
0x18008244d  call    ??1?$unique_storage@U?$resource_policy@PEAGP6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ
0x180082452  lea     rcx, [rbp+47h+var_78]
0x180082456  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ
0x18008245b  lea     rcx, [rbp+47h+var_70]
0x18008245f  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ
0x180082464  xor     ebx, ebx
0x180082466  lea     rcx, [rbp+47h+var_60]
0x18008246a  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ
0x18008246f  lea     rdx, [rbp+47h+var_48]
0x180082473  mov     ecx, 4
0x180082478  call    cs:__imp_EtwEventActivityIdControl
0x18008247e  mov     eax, ebx
0x180082480  mov     rcx, [rbp+47h+var_38]
0x180082484  xor     rcx, rsp; StackCookie
0x180082487  call    __security_check_cookie
0x18008248c  mov     rbx, [rsp+0C0h+arg_18]
0x180082494  add     rsp, 90h
0x18008249b  pop     r15
0x18008249d  pop     r14
0x18008249f  pop     r13
0x1800824a1  pop     r12
0x1800824a3  pop     rdi
0x1800824a4  pop     rsi
0x1800824a5  pop     rbp
0x1800824a6  retn
```
