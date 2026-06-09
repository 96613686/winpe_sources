# CAudStreamSink::DetermineAudioClientBufferDuration(tWAVEFORMATEX const *,AUDIOCLIENTTYPE,__int64 *)

- ea: `0x18021fb28`
- end: `0x18022034b`
- name: `?DetermineAudioClientBufferDuration@CAudStreamSink@@QEAAJPEBUtWAVEFORMATEX@@W4AUDIOCLIENTTYPE@@PEA_J@Z`
- size: `2083`
- prototype: ``
- caller_count: `1`
- callee_count: `16`
- tags: `registry_config, installer_update, broker_com_uri`

## callers

- `0x1800b33a0`

## callees

- `0x18000f278`
- `0x180025998`
- `0x18002dea0`
- `0x18002fee0`
- `0x18003ecb0`
- `0x1800402c0`
- `0x18004d118`
- `0x18004d16c`
- `0x180050d6c`
- `0x180063f00`
- `0x1800ec0e0`
- `0x180192b30`
- `0x18021fb28`
- `0x180258480`
- `0x18031dfc0`
- `0x180344d40`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18022027e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18022027e`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021fc37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021fd39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021fe37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021ff2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802200cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802201aa`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021fc37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021fd39`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021fe37`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x18021ff2c`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802200cf`
- `MFPlat!MFGetCallStackTracingWeakReference` at `0x1802201aa`

## string_xrefs

- `0x18021fb9b`: `CAudStreamSink::DetermineAudioClientBufferDuration`
- `0x18021fc95`: `CAudStreamSink::DetermineAudioClientBufferDuration`
- `0x18021fd97`: `CAudStreamSink::DetermineAudioClientBufferDuration`
- `0x18021fe95`: `CAudStreamSink::DetermineAudioClientBufferDuration`
- `0x18021ff8a`: `CAudStreamSink::DetermineAudioClientBufferDuration`
- `0x18022012d`: `CAudStreamSink::DetermineAudioClientBufferDuration`
- `0x180220208`: `CAudStreamSink::DetermineAudioClientBufferDuration`

## pseudocode

```c
__int64 __fastcall CAudStreamSink::DetermineAudioClientBufferDuration(__int64 a1, __int64 a2, int a3, _QWORD *a4)
{
  __int64 v4; // r13
  __int64 v9; // rdx
  __int64 v10; // r8
  __int64 *v11; // rcx
  struct CallStackContext *ThreadRelativeContext; // rdi
  int v13; // ebx
  __int128 *v14; // rax
  __int128 v15; // xmm0
  __int64 v16; // r9
  int Device; // ebx
  CallStackTracing *v18; // rax
  struct CallStackContext *v19; // rax
  __int64 v20; // rdx
  __int64 v21; // rdx
  __int64 v22; // r8
  CallStackTracing *v23; // rax
  struct CallStackContext *v24; // rax
  __int64 v25; // rdx
  __int64 v26; // r8
  CallStackTracing *v27; // rax
  struct CallStackContext *v28; // rax
  __int64 v29; // rdx
  __int64 v30; // r8
  CallStackTracing *v31; // rax
  struct CallStackContext *v32; // rax
  bool v33; // zf
  __int64 v34; // rdx
  __int64 v35; // r8
  __int64 v36; // rax
  unsigned int v37; // ecx
  __int64 *v38; // rcx
  CallStackTracing *v39; // rax
  struct CallStackContext *v40; // rax
  __int64 v41; // rdx
  __int64 v42; // rcx
  __int64 *v43; // rcx
  CallStackTracing *v44; // rax
  struct CallStackContext *v45; // rax
  int v46; // eax
  LPDWORD pdwType; // [rsp+20h] [rbp-49h]
  _BYTE v49[8]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v50; // [rsp+48h] [rbp-21h] BYREF
  int v51; // [rsp+50h] [rbp-19h] BYREF
  unsigned int pvData; // [rsp+54h] [rbp-15h] BYREF
  __int64 v53; // [rsp+58h] [rbp-11h] BYREF
  DWORD pcbData; // [rsp+60h] [rbp-9h] BYREF
  int v55; // [rsp+64h] [rbp-5h]
  struct IMMDevice *v56; // [rsp+68h] [rbp-1h] BYREF
  _BYTE v57[16]; // [rsp+70h] [rbp+7h] BYREF

  v4 = *(_QWORD *)(a1 + 6632);
  v51 = 0;
  v53 = 0;
  v50 = 0;
  v56 = 0;
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0p_EventWriteTransfer(
      &Microsoft_Windows_MediaFoundation_Performance_Core_Context,
      &AudStreamSink_DetermineAudioClientBufferDuration_Enter,
      a1);
  CallStackScopeTrace::CallStackScopeTrace(
    (CallStackScopeTrace *)v49,
    "CAudStreamSink::DetermineAudioClientBufferDuration",
    9330);
  v11 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( *((_BYTE *)CallStackTracing::s_wpInstance + 8) && *(_QWORD *)(a1 + 6600) )
  {
    ThreadRelativeContext = CallStackTracing::GetThreadRelativeContext(CallStackTracing::s_wpInstance);
    v13 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 6600) + 296LL))(*(_QWORD *)(a1 + 6600));
    v14 = (__int128 *)(*(__int64 (__fastcall **)(_QWORD, _BYTE *))(**(_QWORD **)(a1 + 6600) + 280LL))(
                        *(_QWORD *)(a1 + 6600),
                        v57);
    v11 = (__int64 *)CallStackTracing::s_wpInstance;
    v15 = *v14;
    *((_DWORD *)ThreadRelativeContext + 504) = v13;
    *((_OWORD *)ThreadRelativeContext + 125) = v15;
  }
  v16 = *(_QWORD *)(a1 + 6632);
  if ( !v16 )
  {
    Device = -1072875850;
    if ( !v11 )
    {
      v18 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v9, v10);
      CallStackTracing::s_wpInstance = v18;
      if ( v18 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v18 + 8LL))(v18, 2032) )
      {
        v11 = (__int64 *)CallStackTracing::s_wpInstance;
      }
      else
      {
        v11 = &qword_1803CE250;
        CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
      }
    }
    if ( *((_BYTE *)v11 + 8) )
    {
      v19 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
      if ( *((_DWORD *)v19 + 499) != -1072875850 )
        CallStackContext::TraceFailure(v19, "CAudStreamSink::DetermineAudioClientBufferDuration", 9330, -1072875850);
    }
    if ( g_wppLevels )
    {
      v20 = 577;
LABEL_17:
      WPP_SF_qD(*((_QWORD *)WPP_GLOBAL_Control + 2), v20, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, a1, Device);
      goto LABEL_104;
    }
    goto LABEL_104;
  }
  if ( a3 == 1 )
  {
    v11 = (__int64 *)((-(__int64)(*(_DWORD *)(a1 + 7252) != 0) & 0xFFFFFFFFFFE30220uLL) + 2000000);
LABEL_20:
    *a4 = v11;
    Device = 0;
    goto LABEL_104;
  }
  Device = (*(__int64 (__fastcall **)(_QWORD, _QWORD, int *))(*(_QWORD *)v16 + 120LL))(
             *(_QWORD *)(a1 + 6632),
             *(unsigned int *)(a1 + 6680),
             &v51);
  if ( Device >= 0 )
  {
    if ( a3 == 2 && !v51 )
    {
      v11 = (__int64 *)((-(__int64)(*(_DWORD *)(a1 + 7252) != 0) & 0xFFFFFFFFFFF24460uLL) + 1000000);
      goto LABEL_20;
    }
    v55 = *(_DWORD *)(a1 + 6676);
    *(_DWORD *)(a1 + 6676) = a3 == 0;
    Device = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 128LL))(v4, a1 + 6672);
    if ( Device < 0 )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v27 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v25, v26);
        CallStackTracing::s_wpInstance = v27;
        if ( v27 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v27 + 8LL))(v27, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v28 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v28 + 499) != Device )
          CallStackContext::TraceFailure(v28, "CAudStreamSink::DetermineAudioClientBufferDuration", 9355, Device);
      }
      if ( g_wppLevels )
      {
        v20 = 579;
        goto LABEL_17;
      }
      goto LABEL_104;
    }
    if ( (*(int (__fastcall **)(__int64, __int64, _QWORD, __int64 *, __int64 *))(*(_QWORD *)v4 + 136LL))(
           v4,
           a2,
           *(unsigned int *)(a1 + 6664),
           &v53,
           &v50) < 0 )
    {
      v53 = *(_QWORD *)(a1 + 6712);
      v50 = *(_QWORD *)(a1 + 6704);
    }
    Device = CAudioClientManager::GetDevice(*(CAudioClientManager **)(a1 + 6736), &v56);
    if ( Device < 0 )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
      if ( !CallStackTracing::s_wpInstance )
      {
        v31 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v29, v30);
        CallStackTracing::s_wpInstance = v31;
        if ( v31 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v31 + 8LL))(v31, 2032) )
        {
          v11 = (__int64 *)CallStackTracing::s_wpInstance;
        }
        else
        {
          v11 = &qword_1803CE250;
          CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
        }
      }
      if ( *((_BYTE *)v11 + 8) )
      {
        v32 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
        if ( *((_DWORD *)v32 + 499) != Device )
          CallStackContext::TraceFailure(v32, "CAudStreamSink::DetermineAudioClientBufferDuration", 9380, Device);
      }
      if ( g_wppLevels )
      {
        v20 = 580;
        goto LABEL_17;
      }
      goto LABEL_104;
    }
    v33 = IsKnownAudioDevice(v56, L"{1}.INTELAUDIO\\FUNC_01&VEN_10EC&DEV_0298") == 0;
    v36 = v50;
    if ( !v33 )
    {
      v35 = 10000000;
      if ( v50 == 10000000 )
      {
        if ( a2 && (v37 = *(_DWORD *)(a2 + 8), v37 < 0x40000) )
        {
          v36 = *(_QWORD *)(a1 + 6704);
          v50 = v36;
          if ( (unsigned __int8)byte_1803CECE9 < 0x10u )
            goto LABEL_70;
          LODWORD(pdwType) = v37;
          WPP_SF_qdq(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            581,
            &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
            a1,
            pdwType,
            v36);
        }
        else
        {
          if ( (unsigned __int8)byte_1803CECE9 < 0x10u )
            goto LABEL_70;
          WPP_SF_qq(
            *((_QWORD *)WPP_GLOBAL_Control + 7),
            582,
            &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
            a1,
            10000000);
        }
        v36 = v50;
      }
    }
    if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    {
      WPP_SF_qqq(
        *((_QWORD *)WPP_GLOBAL_Control + 7),
        583,
        &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
        a1,
        v53,
        v36);
      v36 = v50;
    }
LABEL_70:
    if ( *(_DWORD *)(a1 + 7252) )
    {
      if ( v53 > *(_QWORD *)(a1 + 6696) )
      {
        v38 = (__int64 *)CallStackTracing::s_wpInstance;
        Device = -1072869752;
        if ( !CallStackTracing::s_wpInstance )
        {
          v39 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35);
          CallStackTracing::s_wpInstance = v39;
          if ( v39 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v39 + 8LL))(v39, 2032) )
          {
            v38 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v38 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v38 + 8) )
        {
          v40 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v38);
          if ( *((_DWORD *)v40 + 499) != -1072869752 )
            CallStackContext::TraceFailure(v40, "CAudStreamSink::DetermineAudioClientBufferDuration", 9408, -1072869752);
        }
        if ( !g_wppLevels )
          goto LABEL_102;
        v41 = 584;
LABEL_82:
        WPP_SF_qD(
          *((_QWORD *)WPP_GLOBAL_Control + 2),
          v41,
          &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids,
          a1,
          -1072869752);
LABEL_102:
        *(_DWORD *)(a1 + 6676) = v55;
        v46 = (*(__int64 (__fastcall **)(__int64, __int64))(*(_QWORD *)v4 + 128LL))(v4, a1 + 6672);
        if ( v46 < 0 )
          Device = v46;
        goto LABEL_104;
      }
      v42 = *(_QWORD *)(a1 + 6712);
      if ( v53 > v42 )
        v42 = v53;
    }
    else
    {
      if ( v36 < *(_QWORD *)(a1 + 6712) )
      {
        v43 = (__int64 *)CallStackTracing::s_wpInstance;
        Device = -1072869752;
        if ( !CallStackTracing::s_wpInstance )
        {
          v44 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v34, v35);
          CallStackTracing::s_wpInstance = v44;
          if ( v44 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v44 + 8LL))(v44, 2032) )
          {
            v43 = (__int64 *)CallStackTracing::s_wpInstance;
          }
          else
          {
            v43 = &qword_1803CE250;
            CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
          }
        }
        if ( *((_BYTE *)v43 + 8) )
        {
          v45 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v43);
          if ( *((_DWORD *)v45 + 499) != -1072869752 )
            CallStackContext::TraceFailure(v45, "CAudStreamSink::DetermineAudioClientBufferDuration", 9422, -1072869752);
        }
        if ( !g_wppLevels )
          goto LABEL_102;
        v41 = 585;
        goto LABEL_82;
      }
      v42 = *(_QWORD *)(a1 + 6696);
      if ( v36 < v42 )
        v42 = v36;
    }
    *a4 = v42;
    pcbData = 4;
    pvData = 0;
    if ( !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"Software\\Microsoft\\Windows Media Foundation\\Platform\\SAR",
            L"PullModeBufferDuration",
            0x18u,
            0,
            &pvData,
            &pcbData)
      && pvData )
    {
      *a4 = pvData;
    }
    goto LABEL_102;
  }
  v11 = (__int64 *)CallStackTracing::s_wpInstance;
  if ( !CallStackTracing::s_wpInstance )
  {
    v23 = (CallStackTracing *)MFGetCallStackTracingWeakReference(0, v21, v22);
    CallStackTracing::s_wpInstance = v23;
    if ( v23 && (*(unsigned int (__fastcall **)(CallStackTracing *, __int64))(*(_QWORD *)v23 + 8LL))(v23, 2032) )
    {
      v11 = (__int64 *)CallStackTracing::s_wpInstance;
    }
    else
    {
      v11 = &qword_1803CE250;
      CallStackTracing::s_wpInstance = (CallStackTracing *)&qword_1803CE250;
    }
  }
  if ( *((_BYTE *)v11 + 8) )
  {
    v24 = CallStackTracing::GetThreadRelativeContext((CallStackTracing *)v11);
    if ( *((_DWORD *)v24 + 499) != Device )
      CallStackContext::TraceFailure(v24, "CAudStreamSink::DetermineAudioClientBufferDuration", 9341, Device);
  }
  if ( g_wppLevels )
  {
    v20 = 578;
    goto LABEL_17;
  }
LABEL_104:
  if ( (unsigned __int8)byte_1803CECE9 >= 0x10u )
    WPP_SF_qq(*((_QWORD *)WPP_GLOBAL_Control + 7), 586, &WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids, a1, *a4);
  if ( (Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits & 1) != 0 )
    McTemplateU0piq_EventWriteTransfer(
      (_DWORD)v11,
      (unsigned int)&AudStreamSink_DetermineAudioClientBufferDuration_Exit,
      a1,
      *a4,
      Device);
  CallStackScopeTrace::~CallStackScopeTrace((CallStackScopeTrace *)v49);
  ComSmartPtr<IMFTransform>::~ComSmartPtr<IMFTransform>(&v56);
  return (unsigned int)Device;
}

```

## disassembly

```asm
0x18021fb28  mov     [rsp-8+arg_10], rbx
0x18021fb2d  push    rbp
0x18021fb2e  push    rsi
0x18021fb2f  push    rdi
0x18021fb30  push    r12
0x18021fb32  push    r13
0x18021fb34  push    r14
0x18021fb36  push    r15
0x18021fb38  lea     rbp, [rsp-27h]
0x18021fb3d  sub     rsp, 90h
0x18021fb44  mov     rax, cs:__security_cookie
0x18021fb4b  xor     rax, rsp
0x18021fb4e  mov     [rbp+57h+var_40], rax
0x18021fb52  mov     r13, [rcx+19E8h]
0x18021fb59  xor     edi, edi
0x18021fb5b  test    cs:Microsoft_Windows_MediaFoundation_Performance_CoreEnableBits, 1
0x18021fb62  mov     r12, r9
0x18021fb65  mov     r14d, r8d
0x18021fb68  mov     [rbp+57h+var_70], edi
0x18021fb6b  mov     r15, rdx
0x18021fb6e  mov     [rbp+57h+var_68], rdi
0x18021fb72  mov     rsi, rcx
0x18021fb75  mov     [rbp+57h+var_78], rdi
0x18021fb79  mov     [rbp+57h+var_58], rdi
0x18021fb7d  jz      short loc_18021FB95
0x18021fb7f  mov     r8, rcx
0x18021fb82  lea     rdx, AudStreamSink_DetermineAudioClientBufferDuration_Enter
0x18021fb89  lea     rcx, Microsoft_Windows_MediaFoundation_Performance_Core_Context
0x18021fb90  call    McTemplateU0p_EventWriteTransfer
0x18021fb95  mov     r8d, 2472h; int
0x18021fb9b  lea     rdx, aCaudstreamsink_12; "CAudStreamSink::DetermineAudioClientBuf"...
0x18021fba2  lea     rcx, [rbp+57h+var_80]; this
0x18021fba6  call    ??0CallStackScopeTrace@@QEAA@PEBDJ@Z; CallStackScopeTrace::CallStackScopeTrace(char const *,long)
0x18021fbab  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; this
0x18021fbb2  cmp     [rcx+8], dil
0x18021fbb6  jz      short loc_18021FC1D
0x18021fbb8  cmp     [rsi+19C8h], rdi
0x18021fbbf  jz      short loc_18021FC1D
0x18021fbc1  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18021fbc6  mov     rdx, [rsi+19C8h]
0x18021fbcd  mov     rdi, rax
0x18021fbd0  mov     rcx, [rdx]
0x18021fbd3  mov     rax, [rcx+128h]
0x18021fbda  mov     rcx, rdx
0x18021fbdd  call    cs:__guard_dispatch_icall_fptr
0x18021fbe3  mov     r8, [rsi+19C8h]
0x18021fbea  lea     rdx, [rbp+57h+var_50]
0x18021fbee  mov     ebx, eax
0x18021fbf0  mov     rcx, [r8]
0x18021fbf3  mov     rax, [rcx+118h]
0x18021fbfa  mov     rcx, r8
0x18021fbfd  call    cs:__guard_dispatch_icall_fptr
0x18021fc03  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fc0a  movups  xmm0, xmmword ptr [rax]
0x18021fc0d  mov     [rdi+7E0h], ebx
0x18021fc13  movdqu  xmmword ptr [rdi+7D0h], xmm0
0x18021fc1b  xor     edi, edi
0x18021fc1d  mov     r9, [rsi+19E8h]
0x18021fc24  test    r9, r9
0x18021fc27  jnz     loc_18021FCDF
0x18021fc2d  mov     ebx, 0C00D36B6h
0x18021fc32  test    rcx, rcx
0x18021fc35  jnz     short loc_18021FC7F
0x18021fc37  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18021fc3e  nop     dword ptr [rax+rax+00h]
0x18021fc43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fc4a  mov     rcx, rax
0x18021fc4d  test    rax, rax
0x18021fc50  jz      short loc_18021FC71
0x18021fc52  mov     rax, [rax]
0x18021fc55  mov     edx, 7F0h
0x18021fc5a  mov     rax, [rax+8]
0x18021fc5e  call    cs:__guard_dispatch_icall_fptr
0x18021fc64  test    eax, eax
0x18021fc66  jz      short loc_18021FC71
0x18021fc68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fc6f  jmp     short loc_18021FC7F
0x18021fc71  lea     rcx, qword_1803CE250; this
0x18021fc78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fc7f  cmp     [rcx+8], dil
0x18021fc83  jz      short loc_18021FCAA
0x18021fc85  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18021fc8a  cmp     [rax+7CCh], ebx
0x18021fc90  jz      short loc_18021FCAA
0x18021fc92  mov     r9d, ebx; int
0x18021fc95  lea     rdx, aCaudstreamsink_12; "CAudStreamSink::DetermineAudioClientBuf"...
0x18021fc9c  mov     r8d, 2472h; int
0x18021fca2  mov     rcx, rax; this
0x18021fca5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18021fcaa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18021fcb1  jb      loc_1802202BE
0x18021fcb7  mov     edx, 241h
0x18021fcbc  mov     rcx, cs:WPP_GLOBAL_Control
0x18021fcc3  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x18021fcca  mov     r9, rsi
0x18021fccd  mov     dword ptr [rsp+0C0h+pdwType], ebx
0x18021fcd1  mov     rcx, [rcx+10h]
0x18021fcd5  call    WPP_SF_qD
0x18021fcda  jmp     loc_1802202BE
0x18021fcdf  cmp     r14d, 1
0x18021fce3  jnz     short loc_18021FD09
0x18021fce5  mov     eax, [rsi+1C54h]
0x18021fceb  neg     eax
0x18021fced  sbb     rcx, rcx
0x18021fcf0  and     rcx, 0FFFFFFFFFFE30220h
0x18021fcf7  add     rcx, 1E8480h
0x18021fcfe  mov     [r12], rcx
0x18021fd02  mov     ebx, edi
0x18021fd04  jmp     loc_1802202BE
0x18021fd09  mov     rax, [r9]
0x18021fd0c  lea     r8, [rbp+57h+var_70]
0x18021fd10  mov     edx, [rsi+1A18h]
0x18021fd16  mov     rcx, r9
0x18021fd19  mov     rax, [rax+78h]
0x18021fd1d  call    cs:__guard_dispatch_icall_fptr
0x18021fd23  mov     ebx, eax
0x18021fd25  test    eax, eax
0x18021fd27  jns     loc_18021FDC3
0x18021fd2d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fd34  test    rcx, rcx
0x18021fd37  jnz     short loc_18021FD81
0x18021fd39  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18021fd40  nop     dword ptr [rax+rax+00h]
0x18021fd45  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fd4c  mov     rcx, rax
0x18021fd4f  test    rax, rax
0x18021fd52  jz      short loc_18021FD73
0x18021fd54  mov     rax, [rax]
0x18021fd57  mov     edx, 7F0h
0x18021fd5c  mov     rax, [rax+8]
0x18021fd60  call    cs:__guard_dispatch_icall_fptr
0x18021fd66  test    eax, eax
0x18021fd68  jz      short loc_18021FD73
0x18021fd6a  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fd71  jmp     short loc_18021FD81
0x18021fd73  lea     rcx, qword_1803CE250; this
0x18021fd7a  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fd81  cmp     [rcx+8], dil
0x18021fd85  jz      short loc_18021FDAC
0x18021fd87  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18021fd8c  cmp     [rax+7CCh], ebx
0x18021fd92  jz      short loc_18021FDAC
0x18021fd94  mov     r9d, ebx; int
0x18021fd97  lea     rdx, aCaudstreamsink_12; "CAudStreamSink::DetermineAudioClientBuf"...
0x18021fd9e  mov     r8d, 247Dh; int
0x18021fda4  mov     rcx, rax; this
0x18021fda7  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18021fdac  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18021fdb3  jb      loc_1802202BE
0x18021fdb9  mov     edx, 242h
0x18021fdbe  jmp     loc_18021FCBC
0x18021fdc3  cmp     r14d, 2
0x18021fdc7  jnz     short loc_18021FDEC
0x18021fdc9  cmp     [rbp+57h+var_70], edi
0x18021fdcc  jnz     short loc_18021FDEC
0x18021fdce  mov     eax, [rsi+1C54h]
0x18021fdd4  neg     eax
0x18021fdd6  sbb     rcx, rcx
0x18021fdd9  and     rcx, 0FFFFFFFFFFF24460h
0x18021fde0  add     rcx, 0F4240h
0x18021fde7  jmp     loc_18021FCFE
0x18021fdec  mov     eax, [rsi+1A14h]
0x18021fdf2  test    r14d, r14d
0x18021fdf5  mov     [rbp+57h+var_5C], eax
0x18021fdf8  lea     r14, [rsi+1A10h]
0x18021fdff  mov     eax, edi
0x18021fe01  mov     rdx, r14
0x18021fe04  setz    al
0x18021fe07  mov     rcx, r13
0x18021fe0a  mov     [rsi+1A14h], eax
0x18021fe10  mov     rax, [r13+0]
0x18021fe14  mov     rax, [rax+80h]
0x18021fe1b  call    cs:__guard_dispatch_icall_fptr
0x18021fe21  mov     ebx, eax
0x18021fe23  test    eax, eax
0x18021fe25  jns     loc_18021FEC1
0x18021fe2b  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fe32  test    rcx, rcx
0x18021fe35  jnz     short loc_18021FE7F
0x18021fe37  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18021fe3e  nop     dword ptr [rax+rax+00h]
0x18021fe43  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fe4a  mov     rcx, rax
0x18021fe4d  test    rax, rax
0x18021fe50  jz      short loc_18021FE71
0x18021fe52  mov     rax, [rax]
0x18021fe55  mov     edx, 7F0h
0x18021fe5a  mov     rax, [rax+8]
0x18021fe5e  call    cs:__guard_dispatch_icall_fptr
0x18021fe64  test    eax, eax
0x18021fe66  jz      short loc_18021FE71
0x18021fe68  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fe6f  jmp     short loc_18021FE7F
0x18021fe71  lea     rcx, qword_1803CE250; this
0x18021fe78  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18021fe7f  cmp     [rcx+8], dil
0x18021fe83  jz      short loc_18021FEAA
0x18021fe85  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18021fe8a  cmp     [rax+7CCh], ebx
0x18021fe90  jz      short loc_18021FEAA
0x18021fe92  mov     r9d, ebx; int
0x18021fe95  lea     rdx, aCaudstreamsink_12; "CAudStreamSink::DetermineAudioClientBuf"...
0x18021fe9c  mov     r8d, 248Bh; int
0x18021fea2  mov     rcx, rax; this
0x18021fea5  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18021feaa  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18021feb1  jb      loc_1802202BE
0x18021feb7  mov     edx, 243h
0x18021febc  jmp     loc_18021FCBC
0x18021fec1  mov     rax, [r13+0]
0x18021fec5  lea     rcx, [rbp+57h+var_78]
0x18021fec9  mov     r8d, [rsi+1A08h]
0x18021fed0  lea     r9, [rbp+57h+var_68]
0x18021fed4  mov     [rsp+0C0h+pdwType], rcx
0x18021fed9  mov     rdx, r15
0x18021fedc  mov     rcx, r13
0x18021fedf  mov     rax, [rax+88h]
0x18021fee6  call    cs:__guard_dispatch_icall_fptr
0x18021feec  test    eax, eax
0x18021feee  jns     short loc_18021FF06
0x18021fef0  mov     rax, [rsi+1A38h]
0x18021fef7  mov     [rbp+57h+var_68], rax
0x18021fefb  mov     rax, [rsi+1A30h]
0x18021ff02  mov     [rbp+57h+var_78], rax
0x18021ff06  mov     rcx, [rsi+1A50h]; this
0x18021ff0d  lea     rdx, [rbp+57h+var_58]; struct IMMDevice **
0x18021ff11  call    ?GetDevice@CAudioClientManager@@QEAAJPEAPEAUIMMDevice@@@Z; CAudioClientManager::GetDevice(IMMDevice * *)
0x18021ff16  mov     ebx, eax
0x18021ff18  test    eax, eax
0x18021ff1a  jns     loc_18021FFB6
0x18021ff20  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18021ff27  test    rcx, rcx
0x18021ff2a  jnz     short loc_18021FF74
0x18021ff2c  call    cs:__imp_MFGetCallStackTracingWeakReference
0x18021ff33  nop     dword ptr [rax+rax+00h]
0x18021ff38  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rax; CallStackTracing * CallStackTracing::s_wpInstance
0x18021ff3f  mov     rcx, rax
0x18021ff42  test    rax, rax
0x18021ff45  jz      short loc_18021FF66
0x18021ff47  mov     rax, [rax]
0x18021ff4a  mov     edx, 7F0h
0x18021ff4f  mov     rax, [rax+8]
0x18021ff53  call    cs:__guard_dispatch_icall_fptr
0x18021ff59  test    eax, eax
0x18021ff5b  jz      short loc_18021FF66
0x18021ff5d  mov     rcx, cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA; CallStackTracing * CallStackTracing::s_wpInstance
0x18021ff64  jmp     short loc_18021FF74
0x18021ff66  lea     rcx, qword_1803CE250; this
0x18021ff6d  mov     cs:?s_wpInstance@CallStackTracing@@0PEAV1@EA, rcx; CallStackTracing * CallStackTracing::s_wpInstance
0x18021ff74  cmp     [rcx+8], dil
0x18021ff78  jz      short loc_18021FF9F
0x18021ff7a  call    ?GetThreadRelativeContext@CallStackTracing@@IEAAAEAVCallStackContext@@XZ; CallStackTracing::GetThreadRelativeContext(void)
0x18021ff7f  cmp     [rax+7CCh], ebx
0x18021ff85  jz      short loc_18021FF9F
0x18021ff87  mov     r9d, ebx; int
0x18021ff8a  lea     rdx, aCaudstreamsink_12; "CAudStreamSink::DetermineAudioClientBuf"...
0x18021ff91  mov     r8d, 24A4h; int
0x18021ff97  mov     rcx, rax; this
0x18021ff9a  call    ?TraceFailure@CallStackContext@@AEAAXPEBDJJ@Z; CallStackContext::TraceFailure(char const *,long,long)
0x18021ff9f  cmp     cs:?g_wppLevels@@3UMFWppLevels@@A, 1; MFWppLevels g_wppLevels
0x18021ffa6  jb      loc_1802202BE
0x18021ffac  mov     edx, 244h
0x18021ffb1  jmp     loc_18021FCBC
0x18021ffb6  mov     rcx, [rbp+57h+var_58]; struct IMMDevice *
0x18021ffba  lea     rdx, a1IntelaudioFun; "{1}.INTELAUDIO\\FUNC_01&VEN_10EC&DEV_02"...
0x18021ffc1  call    ?IsKnownAudioDevice@@YAHPEAUIMMDevice@@PEBG@Z; IsKnownAudioDevice(IMMDevice *,ushort const *)
0x18021ffc6  test    eax, eax
0x18021ffc8  mov     rax, [rbp+57h+var_78]
0x18021ffcc  jz      loc_180220065
0x18021ffd2  mov     r8d, 989680h
0x18021ffd8  cmp     rax, r8
0x18021ffdb  jnz     loc_180220065
0x18021ffe1  test    r15, r15
0x18021ffe4  jz      short loc_180220034
0x18021ffe6  mov     ecx, [r15+8]
0x18021ffea  cmp     ecx, 40000h
0x18021fff0  jnb     short loc_180220034
0x18021fff2  mov     rax, [rsi+1A30h]
0x18021fff9  mov     [rbp+57h+var_78], rax
0x18021fffd  cmp     cs:byte_1803CECE9, 10h
0x180220004  jb      loc_18022009F
0x18022000a  mov     [rsp+0C0h+pvData], rax
0x18022000f  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x180220016  mov     dword ptr [rsp+0C0h+pdwType], ecx
0x18022001a  mov     edx, 245h
0x18022001f  mov     rcx, cs:WPP_GLOBAL_Control
0x180220026  mov     r9, rsi
0x180220029  mov     rcx, [rcx+38h]
0x18022002d  call    WPP_SF_qdq
0x180220032  jmp     short loc_180220061
0x180220034  cmp     cs:byte_1803CECE9, 10h
0x18022003b  jb      short loc_18022009F
0x18022003d  mov     rcx, cs:WPP_GLOBAL_Control
0x180220044  mov     edx, 246h
0x180220049  mov     [rsp+0C0h+pdwType], r8
0x18022004e  mov     r9, rsi
0x180220051  lea     r8, WPP_8e6dbb68bb473dec012b49037e0fe992_Traceguids
0x180220058  mov     rcx, [rcx+38h]
0x18022005c  call    WPP_SF_qq
0x180220061  mov     rax, [rbp+57h+var_78]
  ... truncated ...
```
