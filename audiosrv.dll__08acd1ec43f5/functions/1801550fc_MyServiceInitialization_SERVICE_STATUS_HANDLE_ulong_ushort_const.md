# MyServiceInitialization(SERVICE_STATUS_HANDLE__ *,ulong,ushort const * *)

- ea: `0x1801550fc`
- end: `0x180155307`
- name: `?MyServiceInitialization@@YAKPEAUSERVICE_STATUS_HANDLE__@@KPEAPEBG@Z`
- size: `523`
- prototype: `unsigned int __fastcall(struct SERVICE_STATUS_HANDLE__ *, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18015570c`

## callees

- `0x18000ae1c`
- `0x18012ecfc`
- `0x1801550fc`
- `0x18015554c`
- `0x18016c010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015523e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155287`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015523e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180155287`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180155275`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180155275`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180155152`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180155152`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18015522c`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18015522c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180155170`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180155170`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801551ca`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801551ca`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801552ef`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801552ef`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
unsigned int __fastcall MyServiceInitialization(
        struct SERVICE_STATUS_HANDLE__ *a1,
        __int64 a2,
        const unsigned __int16 **a3)
{
  unsigned int result; // eax
  struct IAudioService *v5; // rax
  DWORD Instance; // ebx
  unsigned int v7; // eax
  __int64 v8; // rdx
  unsigned int v9; // eax
  int v10; // ebx
  DWORD ThreadId; // [rsp+58h] [rbp+10h] BYREF
  __int64 v12; // [rsp+60h] [rbp+18h] BYREF

  HIDWORD(v12) = HIDWORD(a3);
  LODWORD(v12) = 4;
  ThreadId = 0;
  if ( !RegGetValueW(
          HKEY_LOCAL_MACHINE,
          L"Software\\Microsoft\\Windows\\CurrentVersion\\Audio",
          L"DevApiIsRunningInVM",
          0x18u,
          0,
          &ThreadId,
          (LPDWORD)&v12)
    && ThreadId )
  {
    return -2147019873;
  }
  result = CoInitializeEx(0, 0);
  if ( result <= 1 )
  {
    v5 = g_AudioService;
    *((_QWORD *)g_AudioService + 1) = 0;
    *((_QWORD *)v5 + 2) = 0;
    *((_QWORD *)v5 + 3) = 0;
    *((_QWORD *)v5 + 5) = 0;
    *((_QWORD *)v5 + 4) = 0;
    *((_QWORD *)v5 + 6) = 0;
    *((_QWORD *)v5 + 7) = 0;
    *((_DWORD *)v5 + 16) = 0;
    McGenEventRegister_EtwEventRegister();
    Instance = CoCreateInstance(
                 &GUID_bcde0395_e52f_467c_8e3d_c4579291692e,
                 0,
                 3u,
                 &GUID_a95664d2_9614_4f35_a746_de8db63617e6,
                 (LPVOID *)&g_DeviceEnumerator);
    if ( !Instance )
    {
      v12 = 0;
      if ( ((__int64 (__fastcall *)(struct IMMDeviceEnumerator *, GUID *, __int64 *))g_DeviceEnumerator->lpVtbl->QueryInterface)(
             g_DeviceEnumerator,
             &GUID_8a189c00_2dd1_4f94_bfab_31ac1deb05d0,
             &v12) >= 0 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 88LL))(v12, Instance + 1);
      wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(&v12);
      g_WorkerEventPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
      if ( g_WorkerEventPort || (Instance = GetLastError()) == 0 )
      {
        Instance = InitializeAudioThreadpool();
        if ( !Instance )
        {
          ThreadId = 0;
          g_EventWorkerThreadHandle = CreateThread(0, 0, EventWorkerThread, 0, 0, &ThreadId);
          if ( !g_EventWorkerThreadHandle )
            Instance = GetLastError();
        }
      }
    }
    v7 = (**(__int64 (__fastcall ***)(struct IAudioService *, _QWORD))g_AudioService)(g_AudioService, Instance);
    v8 = v7;
    if ( !v7 )
    {
      v9 = (*(__int64 (__fastcall **)(struct IAudioService *, struct SERVICE_STATUS_HANDLE__ *))(*(_QWORD *)g_AudioService
                                                                                               + 8LL))(
             g_AudioService,
             a1);
      v8 = v9;
      if ( !v9 )
        v8 = (*(unsigned int (__fastcall **)(struct IAudioService *, _QWORD))(*(_QWORD *)g_AudioService + 16LL))(
               g_AudioService,
               0);
    }
    v10 = (*(__int64 (__fastcall **)(struct IAudioService *, __int64))(*(_QWORD *)g_AudioService + 24LL))(
            g_AudioService,
            v8);
    CoUninitialize();
    return v10;
  }
  return result;
}

```

## disassembly

```asm
0x1801550fc  mov     r11, rsp
0x1801550ff  mov     [r11+8], rbx
0x180155103  mov     [r11+20h], rsi
0x180155107  mov     [r11+18h], r8
0x18015510b  mov     [rsp+ThreadId], edx
0x18015510f  push    rdi
0x180155110  sub     rsp, 40h
0x180155114  mov     rdi, rcx
0x180155117  mov     dword ptr [rsp+48h+arg_10], 4
0x18015511f  xor     esi, esi
0x180155121  mov     [rsp+48h+ThreadId], esi
0x180155125  lea     rax, [r11+18h]
0x180155129  mov     [r11-18h], rax
0x18015512d  lea     rax, [r11+10h]
0x180155131  mov     [r11-20h], rax
0x180155135  mov     [r11-28h], rsi
0x180155139  lea     r9d, [rsi+18h]; dwFlags
0x18015513d  lea     r8, aDevapiisrunnin; "DevApiIsRunningInVM"
0x180155144  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18015514b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180155152  call    cs:__imp_RegGetValueW
0x180155158  test    eax, eax
0x18015515a  jnz     short loc_18015516C
0x18015515c  cmp     [rsp+48h+ThreadId], esi
0x180155160  jz      short loc_18015516C
0x180155162  mov     eax, 8007139Fh
0x180155167  jmp     loc_1801552F7
0x18015516c  xor     edx, edx; dwCoInit
0x18015516e  xor     ecx, ecx; pvReserved
0x180155170  call    cs:__imp_CoInitializeEx
0x180155176  cmp     eax, 1
0x180155179  ja      loc_1801552F7
0x18015517f  mov     rax, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180155186  mov     [rax+8], rsi
0x18015518a  mov     [rax+10h], rsi
0x18015518e  mov     [rax+18h], rsi
0x180155192  mov     [rax+28h], rsi
0x180155196  mov     [rax+20h], rsi
0x18015519a  mov     [rax+30h], rsi
0x18015519e  mov     [rax+38h], rsi
0x1801551a2  mov     [rax+40h], esi
0x1801551a5  call    McGenEventRegister_EtwEventRegister
0x1801551aa  lea     rax, ?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x1801551b1  mov     [rsp+48h+ppv], rax; ppv
0x1801551b6  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1801551bd  xor     edx, edx; pUnkOuter
0x1801551bf  lea     r8d, [rdx+3]; dwClsContext
0x1801551c3  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1801551ca  call    cs:__imp_CoCreateInstance
0x1801551d0  mov     ebx, eax
0x1801551d2  test    eax, eax
0x1801551d4  jnz     loc_18015528F
0x1801551da  mov     [rsp+48h+arg_10], rsi
0x1801551df  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x1801551e6  mov     rax, [rcx]
0x1801551e9  lea     r8, [rsp+48h+arg_10]
0x1801551ee  lea     rdx, _GUID_8a189c00_2dd1_4f94_bfab_31ac1deb05d0
0x1801551f5  mov     rax, [rax]
0x1801551f8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801551fd  test    eax, eax
0x1801551ff  js      short loc_180155216
0x180155201  mov     rcx, [rsp+48h+arg_10]
0x180155206  mov     rax, [rcx]
0x180155209  lea     edx, [rbx+1]
0x18015520c  mov     rax, [rax+58h]
0x180155210  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180155215  nop
0x180155216  lea     rcx, [rsp+48h+arg_10]
0x18015521b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180155220  xor     r9d, r9d; NumberOfConcurrentThreads
0x180155223  xor     r8d, r8d; CompletionKey
0x180155226  xor     edx, edx; ExistingCompletionPort
0x180155228  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18015522c  call    cs:__imp_CreateIoCompletionPort
0x180155232  mov     cs:?g_WorkerEventPort@@3PEAXEA, rax; void * g_WorkerEventPort
0x180155239  test    rax, rax
0x18015523c  jnz     short loc_18015524A
0x18015523e  call    cs:__imp_GetLastError
0x180155244  mov     ebx, eax
0x180155246  test    eax, eax
0x180155248  jnz     short loc_18015528F
0x18015524a  call    ?InitializeAudioThreadpool@@YAJXZ; InitializeAudioThreadpool(void)
0x18015524f  mov     ebx, eax
0x180155251  test    eax, eax
0x180155253  jnz     short loc_18015528F
0x180155255  mov     [rsp+48h+ThreadId], esi
0x180155259  lea     rax, [rsp+48h+ThreadId]
0x18015525e  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180155263  mov     dword ptr [rsp+48h+ppv], esi; dwCreationFlags
0x180155267  xor     r9d, r9d; lpParameter
0x18015526a  lea     r8, ?EventWorkerThread@@YAKPEAX@Z; lpStartAddress
0x180155271  xor     edx, edx; dwStackSize
0x180155273  xor     ecx, ecx; lpThreadAttributes
0x180155275  call    cs:__imp_CreateThread
0x18015527b  mov     cs:?g_EventWorkerThreadHandle@@3PEAXEA, rax; void * g_EventWorkerThreadHandle
0x180155282  test    rax, rax
0x180155285  jnz     short loc_18015528F
0x180155287  call    cs:__imp_GetLastError
0x18015528d  mov     ebx, eax
0x18015528f  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180155296  mov     rax, [rcx]
0x180155299  mov     edx, ebx
0x18015529b  mov     rax, [rax]
0x18015529e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801552a3  mov     edx, eax
0x1801552a5  test    eax, eax
0x1801552a7  jnz     short loc_1801552DA
0x1801552a9  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801552b0  mov     rax, [rcx]
0x1801552b3  mov     rdx, rdi
0x1801552b6  mov     rax, [rax+8]
0x1801552ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801552bf  mov     edx, eax
0x1801552c1  test    eax, eax
0x1801552c3  jnz     short loc_1801552DA
0x1801552c5  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801552cc  mov     rax, [rcx]
0x1801552cf  mov     rax, [rax+10h]
0x1801552d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801552d8  mov     edx, eax
0x1801552da  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801552e1  mov     rax, [rcx]
0x1801552e4  mov     rax, [rax+18h]
0x1801552e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801552ed  mov     ebx, eax
0x1801552ef  call    cs:__imp_CoUninitialize
0x1801552f5  mov     eax, ebx
0x1801552f7  mov     rbx, [rsp+48h+arg_0]
0x1801552fc  mov     rsi, [rsp+48h+arg_18]
0x180155301  add     rsp, 40h
0x180155305  pop     rdi
0x180155306  retn
```
