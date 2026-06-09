# s_ccCreateHandsfreeHidFileFromAudioId

- ea: `0x180101740`
- end: `0x180101a40`
- name: `s_ccCreateHandsfreeHidFileFromAudioId`
- size: `768`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle)`
- caller_count: `0`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001b3d0`
- `0x180067ee0`
- `0x1800b365c`
- `0x1800b5564`
- `0x1800bfec8`
- `0x1800cfd9c`
- `0x1800d0764`
- `0x1800d8458`
- `0x1800d8530`
- `0x1800d87e4`
- `0x1800d8800`
- `0x1800dc3e4`
- `0x1800dc604`
- `0x1800dc628`
- `0x1801012f4`
- `0x18010142c`
- `0x180101740`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010190c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18010190c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180101923`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180101923`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010196b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180101982`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801019b0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18010196b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180101982`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1801019b0`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180101947`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180101947`
- `RPCRT4!RpcImpersonateClient` at `0x1801018e8`
- `RPCRT4!RpcImpersonateClient` at `0x1801018e8`
- `RPCRT4!RpcRevertToSelf` at `0x18010198d`
- `RPCRT4!RpcRevertToSelf` at `0x18010198d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1801018d5`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x1801018d5`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801018fe`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x1801018fe`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801019f3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801019f3`
- `HID!HidD_FreePreparsedData` at `0x18010199c`
- `HID!HidD_FreePreparsedData` at `0x18010199c`

## string_xrefs

- `0x1801017f1`: `s_ccCreateHandsfreeHidFileFromAudioId`
- `0x180101844`: `s_ccCreateHandsfreeHidFileFromAudioId`

## pseudocode

```c
__int64 __fastcall s_ccCreateHandsfreeHidFileFromAudioId(
        RPC_BINDING_HANDLE BindingHandle,
        const unsigned __int16 *a2,
        _DWORD *a3)
{
  const unsigned __int16 *v4; // rbx
  __int64 v6; // rsi
  char v7; // r13
  void *v8; // r14
  struct _FILETIME v9; // rbx
  __int64 v10; // rax
  void *v11; // r14
  struct _FILETIME v12; // rbx
  __int64 v13; // rax
  signed int ContainerId; // ebx
  int LastError; // eax
  HANDLE CurrentProcess; // rax
  __int64 v17; // rax
  void *v18; // rdi
  HANDLE hSourceHandle; // [rsp+40h] [rbp-79h] BYREF
  PHIDP_PREPARSED_DATA PreparsedData; // [rsp+48h] [rbp-71h] BYREF
  __int64 v22; // [rsp+50h] [rbp-69h] BYREF
  __int64 v23; // [rsp+58h] [rbp-61h] BYREF
  struct _GUID v24; // [rsp+60h] [rbp-59h] BYREF
  __int128 v25; // [rsp+70h] [rbp-49h] BYREF
  __int64 v26; // [rsp+80h] [rbp-39h]
  __int128 v27; // [rsp+88h] [rbp-31h]
  int v28; // [rsp+98h] [rbp-21h]
  _BYTE v29[112]; // [rsp+A0h] [rbp-19h] BYREF
  unsigned int Pid; // [rsp+130h] [rbp+77h] BYREF
  HANDLE TargetHandle; // [rsp+138h] [rbp+7Fh] BYREF

  v28 = 10;
  v4 = a2;
  v26 = 0;
  v24 = 0;
  v25 = 0;
  v27 = 0;
  memset_0(v29, 0, 0x40u);
  v6 = -1;
  PreparsedData = 0;
  hSourceHandle = (HANDLE)-1LL;
  v7 = 0;
  TargetHandle = (HANDLE)-1LL;
  Pid = 0;
  v23 = 0;
  v22 = 0;
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(&`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
  {
    v8 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v8 )
    {
      v9 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v10 = CWatchdogTimer<1>::CWatchdogTimer<1>(v8, v9);
      v4 = a2;
    }
    else
    {
      v10 = 0;
    }
    std::unique_ptr<CWatchdogTimer<1>>::reset(&v23, v10);
  }
  else
  {
    v11 = operator new[](0x38u, (const struct std::nothrow_t *)&std::nothrow);
    if ( v11 )
    {
      v12 = g_AudioHealthMonitor;
      AudioSrvTelemetryProvider::Instance();
      v13 = CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(v11, v12);
      v4 = a2;
    }
    else
    {
      v13 = 0;
    }
    std::unique_ptr<CWatchdogTimer_Old<1>>::reset(&v22, v13);
  }
  *a3 = 0;
  ContainerId = AudioDeviceInterfaceGetContainerId(v4, &v24);
  if ( ContainerId >= 0 )
  {
    ContainerId = GetHidCollectionsInContainer(&v24, &v25);
    if ( ContainerId >= 0 )
    {
      ContainerId = FindSupportedHidCollection(&v25, &hSourceHandle, v29, &PreparsedData);
      if ( ContainerId >= 0 )
      {
        LastError = I_RpcBindingInqLocalClientPID(BindingHandle, &Pid);
        if ( LastError )
        {
          if ( LastError <= 0 )
          {
            ContainerId = LastError;
            goto LABEL_22;
          }
LABEL_19:
          ContainerId = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_22;
        }
        if ( RpcImpersonateClient(BindingHandle) )
          goto LABEL_22;
        v7 = 1;
        v6 = (__int64)OpenProcess(0x40u, 0, Pid);
        if ( !v6
          || (CurrentProcess = GetCurrentProcess(),
              !DuplicateHandle(CurrentProcess, hSourceHandle, (HANDLE)v6, &TargetHandle, 0xC0000000, 0, 0)) )
        {
          LastError = GetLastError();
          ContainerId = LastError;
          if ( LastError <= 0 )
            goto LABEL_22;
          goto LABEL_19;
        }
        ContainerId = 0;
        *a3 = (_DWORD)TargetHandle;
        TargetHandle = 0;
      }
    }
  }
LABEL_22:
  if ( (char *)TargetHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    CloseHandle(TargetHandle);
    TargetHandle = 0;
  }
  if ( (unsigned __int64)(v6 - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)v6);
  if ( v7 )
    RpcRevertToSelf();
  if ( PreparsedData )
    HidD_FreePreparsedData(PreparsedData);
  if ( (char *)hSourceHandle - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hSourceHandle);
  while ( v26 )
  {
    if ( !(_QWORD)v25 )
      ATL::AtlThrowImpl(-2147467259);
    v17 = *(_QWORD *)v25;
    v18 = *(void **)(v25 + 16);
    *(_QWORD *)&v25 = v17;
    if ( v17 )
      *(_QWORD *)(v17 + 8) = 0;
    else
      v25 = 0u;
    ATL::CAtlList<unsigned short *,ATL::CElementTraits<unsigned short *>>::FreeNode(&v25);
    CoTaskMemFree(v18);
  }
  std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(&v22);
  std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(&v23);
  ATL::CAtlList<unsigned short *,ATL::CElementTraits<unsigned short *>>::RemoveAll(&v25);
  return (unsigned int)ContainerId;
}

```

## disassembly

```asm
0x180101740  mov     [rsp-8+arg_0], rbx
0x180101745  mov     [rsp-8+arg_8], rdx
0x18010174a  push    rbp
0x18010174b  push    rsi
0x18010174c  push    rdi
0x18010174d  push    r12
0x18010174f  push    r13
0x180101751  push    r14
0x180101753  push    r15
0x180101755  lea     rbp, [rsp-27h]
0x18010175a  sub     rsp, 0E0h
0x180101761  xorps   xmm0, xmm0
0x180101764  mov     [rbp+57h+var_78], 0Ah
0x18010176b  xor     edi, edi
0x18010176d  mov     r15, r8
0x180101770  mov     rbx, rdx
0x180101773  mov     [rbp+57h+var_90], rdi
0x180101777  mov     r12, rcx
0x18010177a  xorps   xmm1, xmm1
0x18010177d  xor     edx, edx; Val
0x18010177f  lea     rcx, [rbp+57h+var_70]; void *
0x180101783  lea     r8d, [rdi+40h]; Size
0x180101787  movups  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x18010178b  movdqu  [rbp+57h+var_A0], xmm1
0x180101790  movdqu  [rbp+57h+var_88], xmm0
0x180101795  call    memset_0
0x18010179a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x18010179e  mov     [rbp+57h+PreparsedData], rdi
0x1801017a2  mov     [rbp+57h+hSourceHandle], rsi
0x1801017a6  mov     r13b, dil
0x1801017a9  mov     [rbp+57h+TargetHandle], rsi
0x1801017ad  mov     [rbp+57h+Pid], edi
0x1801017b0  mov     [rbp+57h+var_B8], rdi
0x1801017b4  mov     [rbp+57h+var_C0], rdi
0x1801017b8  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x1801017bf  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x1801017c4  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1801017cb  lea     ecx, [rdi+38h]; unsigned __int64
0x1801017ce  test    al, al
0x1801017d0  jz      short loc_180101825
0x1801017d2  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x1801017d7  mov     r14, rax
0x1801017da  test    rax, rax
0x1801017dd  jz      short loc_180101814
0x1801017df  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x1801017e6  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x1801017ec  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x1801017f1  lea     r9, aSCccreatehands; "s_ccCreateHandsfreeHidFileFromAudioId"
0x1801017f8  mov     qword ptr [rsp+110h+dwDesiredAccess], rbx; pftDueTime
0x1801017fd  mov     r8d, edi
0x180101800  mov     rcx, r14; pv
0x180101803  mov     rdx, [rax+8]
0x180101807  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x18010180c  mov     rbx, [rbp+57h+arg_8]
0x180101810  xor     edi, edi
0x180101812  jmp     short loc_180101817
0x180101814  mov     rax, rdi
0x180101817  mov     rdx, rax
0x18010181a  lea     rcx, [rbp+57h+var_B8]
0x18010181e  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x180101823  jmp     short loc_180101876
0x180101825  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18010182a  mov     r14, rax
0x18010182d  test    rax, rax
0x180101830  jz      short loc_180101867
0x180101832  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180101839  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x18010183f  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180101844  lea     r9, aSCccreatehands; "s_ccCreateHandsfreeHidFileFromAudioId"
0x18010184b  mov     qword ptr [rsp+110h+dwDesiredAccess], rbx; pftDueTime
0x180101850  mov     r8d, edi
0x180101853  mov     rcx, r14; pv
0x180101856  mov     rdx, [rax+8]
0x18010185a  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x18010185f  mov     rbx, [rbp+57h+arg_8]
0x180101863  xor     edi, edi
0x180101865  jmp     short loc_18010186A
0x180101867  mov     rax, rdi
0x18010186a  mov     rdx, rax
0x18010186d  lea     rcx, [rbp+57h+var_C0]
0x180101871  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x180101876  lea     rdx, [rbp+57h+var_B0]; struct _GUID *
0x18010187a  mov     [r15], edi
0x18010187d  mov     rcx, rbx; unsigned __int16 *
0x180101880  call    ?AudioDeviceInterfaceGetContainerId@@YAJPEBGPEAU_GUID@@@Z; AudioDeviceInterfaceGetContainerId(ushort const *,_GUID *)
0x180101885  mov     ebx, eax
0x180101887  test    eax, eax
0x180101889  js      loc_18010195D
0x18010188f  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.Data1]
0x180101893  lea     rdx, [rbp+57h+var_A0]
0x180101897  lea     rcx, [rbp+57h+var_B0]
0x18010189b  movdqa  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x1801018a0  call    ?GetHidCollectionsInContainer@@YAJU_GUID@@PEAV?$CAtlList@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@@Z; GetHidCollectionsInContainer(_GUID,ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>> *)
0x1801018a5  mov     ebx, eax
0x1801018a7  test    eax, eax
0x1801018a9  js      loc_18010195D
0x1801018af  lea     r9, [rbp+57h+PreparsedData]
0x1801018b3  lea     r8, [rbp+57h+var_70]
0x1801018b7  lea     rdx, [rbp+57h+hSourceHandle]
0x1801018bb  lea     rcx, [rbp+57h+var_A0]
0x1801018bf  call    ?FindSupportedHidCollection@@YAJPEAV?$CAtlList@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@PEAPEAXPEAU_HIDP_CAPS@@PEAPEAU_HIDP_PREPARSED_DATA@@@Z; FindSupportedHidCollection(ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>> *,void * *,_HIDP_CAPS *,_HIDP_PREPARSED_DATA * *)
0x1801018c4  mov     ebx, eax
0x1801018c6  test    eax, eax
0x1801018c8  js      loc_18010195D
0x1801018ce  lea     rdx, [rbp+57h+Pid]; Pid
0x1801018d2  mov     rcx, r12; Binding
0x1801018d5  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x1801018db  test    eax, eax
0x1801018dd  jz      short loc_1801018E5
0x1801018df  jg      short loc_180101918
0x1801018e1  mov     ebx, eax
0x1801018e3  jmp     short loc_18010195D
0x1801018e5  mov     rcx, r12; BindingHandle
0x1801018e8  call    cs:__imp_RpcImpersonateClient
0x1801018ee  test    eax, eax
0x1801018f0  jnz     short loc_18010195D
0x1801018f2  mov     r8d, [rbp+57h+Pid]; dwProcessId
0x1801018f6  lea     ecx, [rax+40h]; dwDesiredAccess
0x1801018f9  xor     edx, edx; bInheritHandle
0x1801018fb  mov     r13b, 1
0x1801018fe  call    cs:__imp_OpenProcess
0x180101904  mov     rsi, rax
0x180101907  test    rax, rax
0x18010190a  jnz     short loc_180101923
0x18010190c  call    cs:__imp_GetLastError
0x180101912  mov     ebx, eax
0x180101914  test    eax, eax
0x180101916  jle     short loc_18010195D
0x180101918  movzx   ebx, ax
0x18010191b  or      ebx, 80070000h
0x180101921  jmp     short loc_18010195D
0x180101923  call    cs:__imp_GetCurrentProcess
0x180101929  mov     rdx, [rbp+57h+hSourceHandle]; hSourceHandle
0x18010192d  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x180101931  mov     [rsp+110h+dwOptions], edi; dwOptions
0x180101935  mov     rcx, rax; hSourceProcessHandle
0x180101938  mov     [rsp+110h+bInheritHandle], edi; bInheritHandle
0x18010193c  mov     r8, rsi; hTargetProcessHandle
0x18010193f  mov     [rsp+110h+dwDesiredAccess], 0C0000000h; dwDesiredAccess
0x180101947  call    cs:__imp_DuplicateHandle
0x18010194d  test    eax, eax
0x18010194f  jz      short loc_18010190C
0x180101951  mov     eax, dword ptr [rbp+57h+TargetHandle]
0x180101954  mov     ebx, edi
0x180101956  mov     [r15], eax
0x180101959  mov     [rbp+57h+TargetHandle], rdi
0x18010195d  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x180101961  lea     rax, [rcx-1]
0x180101965  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180101969  ja      short loc_180101975
0x18010196b  call    cs:__imp_CloseHandle
0x180101971  mov     [rbp+57h+TargetHandle], rdi
0x180101975  lea     rax, [rsi-1]
0x180101979  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18010197d  ja      short loc_180101988
0x18010197f  mov     rcx, rsi; hObject
0x180101982  call    cs:__imp_CloseHandle
0x180101988  test    r13b, r13b
0x18010198b  jz      short loc_180101993
0x18010198d  call    cs:__imp_RpcRevertToSelf
0x180101993  mov     rcx, [rbp+57h+PreparsedData]; PreparsedData
0x180101997  test    rcx, rcx
0x18010199a  jz      short loc_1801019A2
0x18010199c  call    cs:__imp_HidD_FreePreparsedData
0x1801019a2  mov     rcx, [rbp+57h+hSourceHandle]; hObject
0x1801019a6  lea     rax, [rcx-1]
0x1801019aa  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x1801019ae  ja      short loc_1801019B6
0x1801019b0  call    cs:__imp_CloseHandle
0x1801019b6  cmp     [rbp+57h+var_90], rdi
0x1801019ba  jz      short loc_1801019FD
0x1801019bc  mov     rdx, qword ptr [rbp+57h+var_A0]
0x1801019c0  test    rdx, rdx
0x1801019c3  jz      short loc_180101A35
0x1801019c5  mov     rax, [rdx]
0x1801019c8  mov     rdi, [rdx+10h]
0x1801019cc  mov     qword ptr [rbp+57h+var_A0], rax
0x1801019d0  test    rax, rax
0x1801019d3  jz      short loc_1801019DF
0x1801019d5  mov     qword ptr [rax+8], 0
0x1801019dd  jmp     short loc_1801019E7
0x1801019df  mov     qword ptr [rbp+57h+var_A0+8], 0
0x1801019e7  lea     rcx, [rbp+57h+var_A0]
0x1801019eb  call    ?FreeNode@?$CAtlList@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>>::FreeNode(ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>>::CNode *)
0x1801019f0  mov     rcx, rdi; pv
0x1801019f3  call    cs:__imp_CoTaskMemFree
0x1801019f9  xor     edi, edi
0x1801019fb  jmp     short loc_1801019B6
0x1801019fd  lea     rcx, [rbp+57h+var_C0]
0x180101a01  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x180101a06  lea     rcx, [rbp+57h+var_B8]
0x180101a0a  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180101a0f  lea     rcx, [rbp+57h+var_A0]
0x180101a13  call    ?RemoveAll@?$CAtlList@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>>::RemoveAll(void)
0x180101a18  mov     eax, ebx
0x180101a1a  mov     rbx, [rsp+110h+arg_0]
0x180101a22  add     rsp, 0E0h
0x180101a29  pop     r15
0x180101a2b  pop     r14
0x180101a2d  pop     r13
0x180101a2f  pop     r12
0x180101a31  pop     rdi
0x180101a32  pop     rsi
0x180101a33  pop     rbp
0x180101a34  retn
0x180101a35  mov     ecx, 80004005h; int
0x180101a3a  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
