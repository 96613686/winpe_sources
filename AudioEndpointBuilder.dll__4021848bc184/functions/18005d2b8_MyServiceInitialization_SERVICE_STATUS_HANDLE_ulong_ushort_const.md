# MyServiceInitialization(SERVICE_STATUS_HANDLE__ *,ulong,ushort const * *)

- ea: `0x18005d2b8`
- end: `0x18005d4c3`
- name: `?MyServiceInitialization@@YAKPEAUSERVICE_STATUS_HANDLE__@@KPEAPEBG@Z`
- size: `523`
- prototype: `unsigned int __fastcall(struct SERVICE_STATUS_HANDLE__ *, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003496c`

## callees

- `0x180006b0c`
- `0x180037644`
- `0x18005d2b8`
- `0x18005f75c`
- `0x180068010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d3fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d443`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d3fa`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18005d443`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005d431`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x18005d431`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005d30e`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18005d30e`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18005d3e8`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18005d3e8`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005d386`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18005d386`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18005d32c`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x18005d32c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005d4ab`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x18005d4ab`

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
      if ( ((__int64 (__fastcall *)(struct IUnknown *, GUID *, __int64 *))g_DeviceEnumerator->lpVtbl->QueryInterface)(
             g_DeviceEnumerator,
             &GUID_8a189c00_2dd1_4f94_bfab_31ac1deb05d0,
             &v12) >= 0 )
        (*(void (__fastcall **)(__int64, _QWORD))(*(_QWORD *)v12 + 88LL))(v12, Instance + 1);
      ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v12);
      g_WorkerEventPort = CreateIoCompletionPort((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0, 0, 0);
      if ( g_WorkerEventPort || (Instance = GetLastError()) == 0 )
      {
        Instance = InitializeAudioThreadpool();
        if ( !Instance )
        {
          ThreadId = 0;
          g_EventWorkerThreadHandle = CreateThread(0, 0, (LPTHREAD_START_ROUTINE)EventWorkerThread, 0, 0, &ThreadId);
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
0x18005d2b8  mov     r11, rsp
0x18005d2bb  mov     [r11+8], rbx
0x18005d2bf  mov     [r11+20h], rsi
0x18005d2c3  mov     [r11+18h], r8
0x18005d2c7  mov     [rsp+ThreadId], edx
0x18005d2cb  push    rdi
0x18005d2cc  sub     rsp, 40h
0x18005d2d0  mov     rdi, rcx
0x18005d2d3  mov     dword ptr [rsp+48h+arg_10], 4
0x18005d2db  xor     esi, esi
0x18005d2dd  mov     [rsp+48h+ThreadId], esi
0x18005d2e1  lea     rax, [r11+18h]
0x18005d2e5  mov     [r11-18h], rax
0x18005d2e9  lea     rax, [r11+10h]
0x18005d2ed  mov     [r11-20h], rax
0x18005d2f1  mov     [r11-28h], rsi
0x18005d2f5  lea     r9d, [rsi+18h]; dwFlags
0x18005d2f9  lea     r8, aDevapiisrunnin; "DevApiIsRunningInVM"
0x18005d300  lea     rdx, aSoftwareMicros; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18005d307  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18005d30e  call    cs:__imp_RegGetValueW
0x18005d314  test    eax, eax
0x18005d316  jnz     short loc_18005D328
0x18005d318  cmp     [rsp+48h+ThreadId], esi
0x18005d31c  jz      short loc_18005D328
0x18005d31e  mov     eax, 8007139Fh
0x18005d323  jmp     loc_18005D4B3
0x18005d328  xor     edx, edx; dwCoInit
0x18005d32a  xor     ecx, ecx; pvReserved
0x18005d32c  call    cs:__imp_CoInitializeEx
0x18005d332  cmp     eax, 1
0x18005d335  ja      loc_18005D4B3
0x18005d33b  mov     rax, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d342  mov     [rax+8], rsi
0x18005d346  mov     [rax+10h], rsi
0x18005d34a  mov     [rax+18h], rsi
0x18005d34e  mov     [rax+28h], rsi
0x18005d352  mov     [rax+20h], rsi
0x18005d356  mov     [rax+30h], rsi
0x18005d35a  mov     [rax+38h], rsi
0x18005d35e  mov     [rax+40h], esi
0x18005d361  call    McGenEventRegister_EtwEventRegister
0x18005d366  lea     rax, ?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18005d36d  mov     [rsp+48h+ppv], rax; ppv
0x18005d372  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x18005d379  xor     edx, edx; pUnkOuter
0x18005d37b  lea     r8d, [rdx+3]; dwClsContext
0x18005d37f  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x18005d386  call    cs:__imp_CoCreateInstance
0x18005d38c  mov     ebx, eax
0x18005d38e  test    eax, eax
0x18005d390  jnz     loc_18005D44B
0x18005d396  mov     [rsp+48h+arg_10], rsi
0x18005d39b  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x18005d3a2  mov     rax, [rcx]
0x18005d3a5  lea     r8, [rsp+48h+arg_10]
0x18005d3aa  lea     rdx, _GUID_8a189c00_2dd1_4f94_bfab_31ac1deb05d0
0x18005d3b1  mov     rax, [rax]
0x18005d3b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3b9  test    eax, eax
0x18005d3bb  js      short loc_18005D3D2
0x18005d3bd  mov     rcx, [rsp+48h+arg_10]
0x18005d3c2  mov     rax, [rcx]
0x18005d3c5  lea     edx, [rbx+1]
0x18005d3c8  mov     rax, [rax+58h]
0x18005d3cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d3d1  nop
0x18005d3d2  lea     rcx, [rsp+48h+arg_10]
0x18005d3d7  call    ??1?$CComPtrBase@UIUnknown@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(void)
0x18005d3dc  xor     r9d, r9d; NumberOfConcurrentThreads
0x18005d3df  xor     r8d, r8d; CompletionKey
0x18005d3e2  xor     edx, edx; ExistingCompletionPort
0x18005d3e4  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18005d3e8  call    cs:__imp_CreateIoCompletionPort
0x18005d3ee  mov     cs:?g_WorkerEventPort@@3PEAXEA, rax; void * g_WorkerEventPort
0x18005d3f5  test    rax, rax
0x18005d3f8  jnz     short loc_18005D406
0x18005d3fa  call    cs:__imp_GetLastError
0x18005d400  mov     ebx, eax
0x18005d402  test    eax, eax
0x18005d404  jnz     short loc_18005D44B
0x18005d406  call    ?InitializeAudioThreadpool@@YAJXZ; InitializeAudioThreadpool(void)
0x18005d40b  mov     ebx, eax
0x18005d40d  test    eax, eax
0x18005d40f  jnz     short loc_18005D44B
0x18005d411  mov     [rsp+48h+ThreadId], esi
0x18005d415  lea     rax, [rsp+48h+ThreadId]
0x18005d41a  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x18005d41f  mov     dword ptr [rsp+48h+ppv], esi; dwCreationFlags
0x18005d423  xor     r9d, r9d; lpParameter
0x18005d426  lea     r8, ?EventWorkerThread@@YAKPEAX@Z; lpStartAddress
0x18005d42d  xor     edx, edx; dwStackSize
0x18005d42f  xor     ecx, ecx; lpThreadAttributes
0x18005d431  call    cs:__imp_CreateThread
0x18005d437  mov     cs:?g_EventWorkerThreadHandle@@3PEAXEA, rax; void * g_EventWorkerThreadHandle
0x18005d43e  test    rax, rax
0x18005d441  jnz     short loc_18005D44B
0x18005d443  call    cs:__imp_GetLastError
0x18005d449  mov     ebx, eax
0x18005d44b  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d452  mov     rax, [rcx]
0x18005d455  mov     edx, ebx
0x18005d457  mov     rax, [rax]
0x18005d45a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d45f  mov     edx, eax
0x18005d461  test    eax, eax
0x18005d463  jnz     short loc_18005D496
0x18005d465  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d46c  mov     rax, [rcx]
0x18005d46f  mov     rdx, rdi
0x18005d472  mov     rax, [rax+8]
0x18005d476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d47b  mov     edx, eax
0x18005d47d  test    eax, eax
0x18005d47f  jnz     short loc_18005D496
0x18005d481  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d488  mov     rax, [rcx]
0x18005d48b  mov     rax, [rax+10h]
0x18005d48f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d494  mov     edx, eax
0x18005d496  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x18005d49d  mov     rax, [rcx]
0x18005d4a0  mov     rax, [rax+18h]
0x18005d4a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005d4a9  mov     ebx, eax
0x18005d4ab  call    cs:__imp_CoUninitialize
0x18005d4b1  mov     eax, ebx
0x18005d4b3  mov     rbx, [rsp+48h+arg_0]
0x18005d4b8  mov     rsi, [rsp+48h+arg_18]
0x18005d4bd  add     rsp, 40h
0x18005d4c1  pop     rdi
0x18005d4c2  retn
```
