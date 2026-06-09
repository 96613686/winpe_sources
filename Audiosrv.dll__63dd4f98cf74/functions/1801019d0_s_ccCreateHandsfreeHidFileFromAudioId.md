# s_ccCreateHandsfreeHidFileFromAudioId

- ea: `0x1801019d0`
- end: `0x180101cd0`
- name: `s_ccCreateHandsfreeHidFileFromAudioId`
- size: `768`
- prototype: `__int64 __fastcall(RPC_BINDING_HANDLE BindingHandle, const unsigned __int16 *, _DWORD *)`
- caller_count: `0`
- callee_count: `17`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callees

- `0x18001b520`
- `0x180067a50`
- `0x1800b196c`
- `0x1800b3874`
- `0x1800be378`
- `0x1800cddac`
- `0x1800ce774`
- `0x1800d6468`
- `0x1800d6540`
- `0x1800d67f4`
- `0x1800d6810`
- `0x1800da3f4`
- `0x1800da614`
- `0x1800da638`
- `0x180101584`
- `0x1801016bc`
- `0x1801019d0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101b9c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180101b9c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180101bb3`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x180101bb3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180101bfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180101c12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180101c40`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180101bfb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180101c12`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180101c40`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180101bd7`
- `api-ms-win-core-handle-l1-1-0!DuplicateHandle` at `0x180101bd7`
- `RPCRT4!RpcImpersonateClient` at `0x180101b78`
- `RPCRT4!RpcImpersonateClient` at `0x180101b78`
- `RPCRT4!RpcRevertToSelf` at `0x180101c1d`
- `RPCRT4!RpcRevertToSelf` at `0x180101c1d`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180101b65`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x180101b65`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180101b8e`
- `api-ms-win-core-processthreads-l1-1-1!OpenProcess` at `0x180101b8e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180101c83`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180101c83`
- `HID!HidD_FreePreparsedData` at `0x180101c2c`
- `HID!HidD_FreePreparsedData` at `0x180101c2c`

## string_xrefs

- `0x180101a81`: `s_ccCreateHandsfreeHidFileFromAudioId`
- `0x180101ad4`: `s_ccCreateHandsfreeHidFileFromAudioId`

## pseudocode

```c
// Hidden C++ exception states: #wind=9
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
  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl'::`2'::impl) )
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
0x1801019d0  mov     [rsp-8+arg_0], rbx
0x1801019d5  mov     [rsp-8+arg_8], rdx
0x1801019da  push    rbp
0x1801019db  push    rsi
0x1801019dc  push    rdi
0x1801019dd  push    r12
0x1801019df  push    r13
0x1801019e1  push    r14
0x1801019e3  push    r15
0x1801019e5  lea     rbp, [rsp-27h]
0x1801019ea  sub     rsp, 0E0h
0x1801019f1  xorps   xmm0, xmm0
0x1801019f4  mov     [rbp+57h+var_78], 0Ah
0x1801019fb  xor     edi, edi
0x1801019fd  mov     r15, r8
0x180101a00  mov     rbx, rdx
0x180101a03  mov     [rbp+57h+var_90], rdi
0x180101a07  mov     r12, rcx
0x180101a0a  xorps   xmm1, xmm1
0x180101a0d  xor     edx, edx; Val
0x180101a0f  lea     rcx, [rbp+57h+var_70]; void *
0x180101a13  lea     r8d, [rdi+40h]; Size
0x180101a17  movups  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x180101a1b  movdqu  [rbp+57h+var_A0], xmm1
0x180101a20  movdqu  [rbp+57h+var_88], xmm0
0x180101a25  call    memset_0
0x180101a2a  or      rsi, 0FFFFFFFFFFFFFFFFh
0x180101a2e  mov     [rbp+57h+PreparsedData], rdi
0x180101a32  mov     [rbp+57h+hSourceHandle], rsi
0x180101a36  mov     r13b, dil
0x180101a39  mov     [rbp+57h+TargetHandle], rsi
0x180101a3d  mov     [rbp+57h+Pid], edi
0x180101a40  mov     [rbp+57h+var_B8], rdi
0x180101a44  mov     [rbp+57h+var_C0], rdi
0x180101a48  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio> `wil::Feature<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::GetImpl(void)'::`2'::impl
0x180101a4f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Servicing_EnableLKDForAudio>::__private_IsEnabled(void)
0x180101a54  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180101a5b  lea     ecx, [rdi+38h]; unsigned __int64
0x180101a5e  test    al, al
0x180101a60  jz      short loc_180101AB5
0x180101a62  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180101a67  mov     r14, rax
0x180101a6a  test    rax, rax
0x180101a6d  jz      short loc_180101AA4
0x180101a6f  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180101a76  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180101a7c  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180101a81  lea     r9, aSCccreatehands; "s_ccCreateHandsfreeHidFileFromAudioId"
0x180101a88  mov     qword ptr [rsp+110h+dwDesiredAccess], rbx; pftDueTime
0x180101a8d  mov     r8d, edi
0x180101a90  mov     rcx, r14; pv
0x180101a93  mov     rdx, [rax+8]
0x180101a97  call    ??0?$CWatchdogTimer@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@_N@Z; CWatchdogTimer<1>::CWatchdogTimer<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *,bool)
0x180101a9c  mov     rbx, [rbp+57h+arg_8]
0x180101aa0  xor     edi, edi
0x180101aa2  jmp     short loc_180101AA7
0x180101aa4  mov     rax, rdi
0x180101aa7  mov     rdx, rax
0x180101aaa  lea     rcx, [rbp+57h+var_B8]
0x180101aae  call    ?reset@?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer@$00@@@Z; std::unique_ptr<CWatchdogTimer<1>>::reset(CWatchdogTimer<1> *)
0x180101ab3  jmp     short loc_180101B06
0x180101ab5  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180101aba  mov     r14, rax
0x180101abd  test    rax, rax
0x180101ac0  jz      short loc_180101AF7
0x180101ac2  mov     rbx, qword ptr cs:?g_AudioHealthMonitor@@3PEAVCAudioHealthMonitor@@EA.dwLowDateTime; CAudioHealthMonitor * g_AudioHealthMonitor ...
0x180101ac9  mov     edi, cs:?g_AudioSrvWatchDogTimerInMs@@3KA; ulong g_AudioSrvWatchDogTimerInMs
0x180101acf  call    ?Instance@AudioSrvTelemetryProvider@@KAPEAV1@XZ; AudioSrvTelemetryProvider::Instance(void)
0x180101ad4  lea     r9, aSCccreatehands; "s_ccCreateHandsfreeHidFileFromAudioId"
0x180101adb  mov     qword ptr [rsp+110h+dwDesiredAccess], rbx; pftDueTime
0x180101ae0  mov     r8d, edi
0x180101ae3  mov     rcx, r14; pv
0x180101ae6  mov     rdx, [rax+8]
0x180101aea  call    ??0?$CWatchdogTimer_Old@$00@@QEAA@PEBU_tlgProvider_t@@KPEBGPEAUIAudioHealthMonitor@@@Z; CWatchdogTimer_Old<1>::CWatchdogTimer_Old<1>(_tlgProvider_t const *,ulong,ushort const *,IAudioHealthMonitor *)
0x180101aef  mov     rbx, [rbp+57h+arg_8]
0x180101af3  xor     edi, edi
0x180101af5  jmp     short loc_180101AFA
0x180101af7  mov     rax, rdi
0x180101afa  mov     rdx, rax
0x180101afd  lea     rcx, [rbp+57h+var_C0]
0x180101b01  call    ?reset@?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAAXPEAV?$CWatchdogTimer_Old@$00@@@Z; std::unique_ptr<CWatchdogTimer_Old<1>>::reset(CWatchdogTimer_Old<1> *)
0x180101b06  lea     rdx, [rbp+57h+var_B0]; struct _GUID *
0x180101b0a  mov     [r15], edi
0x180101b0d  mov     rcx, rbx; unsigned __int16 *
0x180101b10  call    ?AudioDeviceInterfaceGetContainerId@@YAJPEBGPEAU_GUID@@@Z; AudioDeviceInterfaceGetContainerId(ushort const *,_GUID *)
0x180101b15  mov     ebx, eax
0x180101b17  test    eax, eax
0x180101b19  js      loc_180101BED
0x180101b1f  movaps  xmm0, xmmword ptr [rbp+57h+var_B0.Data1]
0x180101b23  lea     rdx, [rbp+57h+var_A0]
0x180101b27  lea     rcx, [rbp+57h+var_B0]
0x180101b2b  movdqa  xmmword ptr [rbp+57h+var_B0.Data1], xmm0
0x180101b30  call    ?GetHidCollectionsInContainer@@YAJU_GUID@@PEAV?$CAtlList@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@@Z; GetHidCollectionsInContainer(_GUID,ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>> *)
0x180101b35  mov     ebx, eax
0x180101b37  test    eax, eax
0x180101b39  js      loc_180101BED
0x180101b3f  lea     r9, [rbp+57h+PreparsedData]
0x180101b43  lea     r8, [rbp+57h+var_70]
0x180101b47  lea     rdx, [rbp+57h+hSourceHandle]
0x180101b4b  lea     rcx, [rbp+57h+var_A0]
0x180101b4f  call    ?FindSupportedHidCollection@@YAJPEAV?$CAtlList@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@PEAPEAXPEAU_HIDP_CAPS@@PEAPEAU_HIDP_PREPARSED_DATA@@@Z; FindSupportedHidCollection(ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>> *,void * *,_HIDP_CAPS *,_HIDP_PREPARSED_DATA * *)
0x180101b54  mov     ebx, eax
0x180101b56  test    eax, eax
0x180101b58  js      loc_180101BED
0x180101b5e  lea     rdx, [rbp+57h+Pid]; Pid
0x180101b62  mov     rcx, r12; Binding
0x180101b65  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x180101b6b  test    eax, eax
0x180101b6d  jz      short loc_180101B75
0x180101b6f  jg      short loc_180101BA8
0x180101b71  mov     ebx, eax
0x180101b73  jmp     short loc_180101BED
0x180101b75  mov     rcx, r12; BindingHandle
0x180101b78  call    cs:__imp_RpcImpersonateClient
0x180101b7e  test    eax, eax
0x180101b80  jnz     short loc_180101BED
0x180101b82  mov     r8d, [rbp+57h+Pid]; dwProcessId
0x180101b86  lea     ecx, [rax+40h]; dwDesiredAccess
0x180101b89  xor     edx, edx; bInheritHandle
0x180101b8b  mov     r13b, 1
0x180101b8e  call    cs:__imp_OpenProcess
0x180101b94  mov     rsi, rax
0x180101b97  test    rax, rax
0x180101b9a  jnz     short loc_180101BB3
0x180101b9c  call    cs:__imp_GetLastError
0x180101ba2  mov     ebx, eax
0x180101ba4  test    eax, eax
0x180101ba6  jle     short loc_180101BED
0x180101ba8  movzx   ebx, ax
0x180101bab  or      ebx, 80070000h
0x180101bb1  jmp     short loc_180101BED
0x180101bb3  call    cs:__imp_GetCurrentProcess
0x180101bb9  mov     rdx, [rbp+57h+hSourceHandle]; hSourceHandle
0x180101bbd  lea     r9, [rbp+57h+TargetHandle]; lpTargetHandle
0x180101bc1  mov     [rsp+110h+dwOptions], edi; dwOptions
0x180101bc5  mov     rcx, rax; hSourceProcessHandle
0x180101bc8  mov     [rsp+110h+bInheritHandle], edi; bInheritHandle
0x180101bcc  mov     r8, rsi; hTargetProcessHandle
0x180101bcf  mov     [rsp+110h+dwDesiredAccess], 0C0000000h; dwDesiredAccess
0x180101bd7  call    cs:__imp_DuplicateHandle
0x180101bdd  test    eax, eax
0x180101bdf  jz      short loc_180101B9C
0x180101be1  mov     eax, dword ptr [rbp+57h+TargetHandle]
0x180101be4  mov     ebx, edi
0x180101be6  mov     [r15], eax
0x180101be9  mov     [rbp+57h+TargetHandle], rdi
0x180101bed  mov     rcx, [rbp+57h+TargetHandle]; hObject
0x180101bf1  lea     rax, [rcx-1]
0x180101bf5  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180101bf9  ja      short loc_180101C05
0x180101bfb  call    cs:__imp_CloseHandle
0x180101c01  mov     [rbp+57h+TargetHandle], rdi
0x180101c05  lea     rax, [rsi-1]
0x180101c09  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180101c0d  ja      short loc_180101C18
0x180101c0f  mov     rcx, rsi; hObject
0x180101c12  call    cs:__imp_CloseHandle
0x180101c18  test    r13b, r13b
0x180101c1b  jz      short loc_180101C23
0x180101c1d  call    cs:__imp_RpcRevertToSelf
0x180101c23  mov     rcx, [rbp+57h+PreparsedData]; PreparsedData
0x180101c27  test    rcx, rcx
0x180101c2a  jz      short loc_180101C32
0x180101c2c  call    cs:__imp_HidD_FreePreparsedData
0x180101c32  mov     rcx, [rbp+57h+hSourceHandle]; hObject
0x180101c36  lea     rax, [rcx-1]
0x180101c3a  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180101c3e  ja      short loc_180101C46
0x180101c40  call    cs:__imp_CloseHandle
0x180101c46  cmp     [rbp+57h+var_90], rdi
0x180101c4a  jz      short loc_180101C8D
0x180101c4c  mov     rdx, qword ptr [rbp+57h+var_A0]
0x180101c50  test    rdx, rdx
0x180101c53  jz      short loc_180101CC5
0x180101c55  mov     rax, [rdx]
0x180101c58  mov     rdi, [rdx+10h]
0x180101c5c  mov     qword ptr [rbp+57h+var_A0], rax
0x180101c60  test    rax, rax
0x180101c63  jz      short loc_180101C6F
0x180101c65  mov     qword ptr [rax+8], 0
0x180101c6d  jmp     short loc_180101C77
0x180101c6f  mov     qword ptr [rbp+57h+var_A0+8], 0
0x180101c77  lea     rcx, [rbp+57h+var_A0]
0x180101c7b  call    ?FreeNode@?$CAtlList@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@AEAAXPEAVCNode@12@@Z; ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>>::FreeNode(ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>>::CNode *)
0x180101c80  mov     rcx, rdi; pv
0x180101c83  call    cs:__imp_CoTaskMemFree
0x180101c89  xor     edi, edi
0x180101c8b  jmp     short loc_180101C46
0x180101c8d  lea     rcx, [rbp+57h+var_C0]
0x180101c91  call    ??1?$unique_ptr@V?$CWatchdogTimer_Old@$00@@U?$default_delete@V?$CWatchdogTimer_Old@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer_Old<1>>::~unique_ptr<CWatchdogTimer_Old<1>>(void)
0x180101c96  lea     rcx, [rbp+57h+var_B8]
0x180101c9a  call    ??1?$unique_ptr@V?$CWatchdogTimer@$00@@U?$default_delete@V?$CWatchdogTimer@$00@@@std@@@std@@QEAA@XZ; std::unique_ptr<CWatchdogTimer<1>>::~unique_ptr<CWatchdogTimer<1>>(void)
0x180101c9f  lea     rcx, [rbp+57h+var_A0]
0x180101ca3  call    ?RemoveAll@?$CAtlList@PEAGV?$CElementTraits@PEAG@ATL@@@ATL@@QEAAXXZ; ATL::CAtlList<ushort *,ATL::CElementTraits<ushort *>>::RemoveAll(void)
0x180101ca8  mov     eax, ebx
0x180101caa  mov     rbx, [rsp+110h+arg_0]
0x180101cb2  add     rsp, 0E0h
0x180101cb9  pop     r15
0x180101cbb  pop     r14
0x180101cbd  pop     r13
0x180101cbf  pop     r12
0x180101cc1  pop     rdi
0x180101cc2  pop     rsi
0x180101cc3  pop     rbp
0x180101cc4  retn
0x180101cc5  mov     ecx, 80004005h; int
0x180101cca  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
```
