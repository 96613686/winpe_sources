# MyServiceInitialization(SERVICE_STATUS_HANDLE__ *,ulong,ushort const * *)

- ea: `0x1801543ec`
- end: `0x1801545f7`
- name: `?MyServiceInitialization@@YAKPEAUSERVICE_STATUS_HANDLE__@@KPEAPEBG@Z`
- size: `523`
- prototype: `unsigned int __fastcall(struct SERVICE_STATUS_HANDLE__ *, unsigned int, const unsigned __int16 **)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1801549fc`

## callees

- `0x18000accc`
- `0x18012eaac`
- `0x1801543ec`
- `0x18015483c`
- `0x18016b010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015452e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154577`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18015452e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180154577`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180154565`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180154565`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180154442`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180154442`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18015451c`
- `api-ms-win-core-io-l1-1-0!CreateIoCompletionPort` at `0x18015451c`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801545df`
- `api-ms-win-core-com-l1-1-0!CoUninitialize` at `0x1801545df`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801544ba`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x1801544ba`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180154460`
- `api-ms-win-core-com-l1-1-0!CoInitializeEx` at `0x180154460`

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
0x1801543ec  mov     r11, rsp
0x1801543ef  mov     [r11+8], rbx
0x1801543f3  mov     [r11+20h], rsi
0x1801543f7  mov     [r11+18h], r8
0x1801543fb  mov     [rsp+ThreadId], edx
0x1801543ff  push    rdi
0x180154400  sub     rsp, 40h
0x180154404  mov     rdi, rcx
0x180154407  mov     dword ptr [rsp+48h+arg_10], 4
0x18015440f  xor     esi, esi
0x180154411  mov     [rsp+48h+ThreadId], esi
0x180154415  lea     rax, [r11+18h]
0x180154419  mov     [r11-18h], rax
0x18015441d  lea     rax, [r11+10h]
0x180154421  mov     [r11-20h], rax
0x180154425  mov     [r11-28h], rsi
0x180154429  lea     r9d, [rsi+18h]; dwFlags
0x18015442d  lea     r8, aDevapiisrunnin; "DevApiIsRunningInVM"
0x180154434  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x18015443b  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180154442  call    cs:__imp_RegGetValueW
0x180154448  test    eax, eax
0x18015444a  jnz     short loc_18015445C
0x18015444c  cmp     [rsp+48h+ThreadId], esi
0x180154450  jz      short loc_18015445C
0x180154452  mov     eax, 8007139Fh
0x180154457  jmp     loc_1801545E7
0x18015445c  xor     edx, edx; dwCoInit
0x18015445e  xor     ecx, ecx; pvReserved
0x180154460  call    cs:__imp_CoInitializeEx
0x180154466  cmp     eax, 1
0x180154469  ja      loc_1801545E7
0x18015446f  mov     rax, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180154476  mov     [rax+8], rsi
0x18015447a  mov     [rax+10h], rsi
0x18015447e  mov     [rax+18h], rsi
0x180154482  mov     [rax+28h], rsi
0x180154486  mov     [rax+20h], rsi
0x18015448a  mov     [rax+30h], rsi
0x18015448e  mov     [rax+38h], rsi
0x180154492  mov     [rax+40h], esi
0x180154495  call    McGenEventRegister_EtwEventRegister
0x18015449a  lea     rax, ?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x1801544a1  mov     [rsp+48h+ppv], rax; ppv
0x1801544a6  lea     r9, _GUID_a95664d2_9614_4f35_a746_de8db63617e6; riid
0x1801544ad  xor     edx, edx; pUnkOuter
0x1801544af  lea     r8d, [rdx+3]; dwClsContext
0x1801544b3  lea     rcx, _GUID_bcde0395_e52f_467c_8e3d_c4579291692e; rclsid
0x1801544ba  call    cs:__imp_CoCreateInstance
0x1801544c0  mov     ebx, eax
0x1801544c2  test    eax, eax
0x1801544c4  jnz     loc_18015457F
0x1801544ca  mov     [rsp+48h+arg_10], rsi
0x1801544cf  mov     rcx, cs:?g_DeviceEnumerator@@3PEAUIMMDeviceEnumerator@@EA; IMMDeviceEnumerator * g_DeviceEnumerator
0x1801544d6  mov     rax, [rcx]
0x1801544d9  lea     r8, [rsp+48h+arg_10]
0x1801544de  lea     rdx, _GUID_8a189c00_2dd1_4f94_bfab_31ac1deb05d0
0x1801544e5  mov     rax, [rax]
0x1801544e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801544ed  test    eax, eax
0x1801544ef  js      short loc_180154506
0x1801544f1  mov     rcx, [rsp+48h+arg_10]
0x1801544f6  mov     rax, [rcx]
0x1801544f9  lea     edx, [rbx+1]
0x1801544fc  mov     rax, [rax+58h]
0x180154500  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154505  nop
0x180154506  lea     rcx, [rsp+48h+arg_10]
0x18015450b  call    ??1?$com_ptr_t@UIHolographicDisplay@Holographic@Graphics@Windows@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>::~com_ptr_t<Windows::Graphics::Holographic::IHolographicDisplay,wil::err_returncode_policy>(void)
0x180154510  xor     r9d, r9d; NumberOfConcurrentThreads
0x180154513  xor     r8d, r8d; CompletionKey
0x180154516  xor     edx, edx; ExistingCompletionPort
0x180154518  or      rcx, 0FFFFFFFFFFFFFFFFh; FileHandle
0x18015451c  call    cs:__imp_CreateIoCompletionPort
0x180154522  mov     cs:?g_WorkerEventPort@@3PEAXEA, rax; void * g_WorkerEventPort
0x180154529  test    rax, rax
0x18015452c  jnz     short loc_18015453A
0x18015452e  call    cs:__imp_GetLastError
0x180154534  mov     ebx, eax
0x180154536  test    eax, eax
0x180154538  jnz     short loc_18015457F
0x18015453a  call    ?InitializeAudioThreadpool@@YAJXZ; InitializeAudioThreadpool(void)
0x18015453f  mov     ebx, eax
0x180154541  test    eax, eax
0x180154543  jnz     short loc_18015457F
0x180154545  mov     [rsp+48h+ThreadId], esi
0x180154549  lea     rax, [rsp+48h+ThreadId]
0x18015454e  mov     [rsp+48h+lpThreadId], rax; lpThreadId
0x180154553  mov     dword ptr [rsp+48h+ppv], esi; dwCreationFlags
0x180154557  xor     r9d, r9d; lpParameter
0x18015455a  lea     r8, ?EventWorkerThread@@YAKPEAX@Z; lpStartAddress
0x180154561  xor     edx, edx; dwStackSize
0x180154563  xor     ecx, ecx; lpThreadAttributes
0x180154565  call    cs:__imp_CreateThread
0x18015456b  mov     cs:?g_EventWorkerThreadHandle@@3PEAXEA, rax; void * g_EventWorkerThreadHandle
0x180154572  test    rax, rax
0x180154575  jnz     short loc_18015457F
0x180154577  call    cs:__imp_GetLastError
0x18015457d  mov     ebx, eax
0x18015457f  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x180154586  mov     rax, [rcx]
0x180154589  mov     edx, ebx
0x18015458b  mov     rax, [rax]
0x18015458e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180154593  mov     edx, eax
0x180154595  test    eax, eax
0x180154597  jnz     short loc_1801545CA
0x180154599  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801545a0  mov     rax, [rcx]
0x1801545a3  mov     rdx, rdi
0x1801545a6  mov     rax, [rax+8]
0x1801545aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801545af  mov     edx, eax
0x1801545b1  test    eax, eax
0x1801545b3  jnz     short loc_1801545CA
0x1801545b5  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801545bc  mov     rax, [rcx]
0x1801545bf  mov     rax, [rax+10h]
0x1801545c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801545c8  mov     edx, eax
0x1801545ca  mov     rcx, cs:?g_AudioService@@3PEAVIAudioService@@EA; IAudioService * g_AudioService
0x1801545d1  mov     rax, [rcx]
0x1801545d4  mov     rax, [rax+18h]
0x1801545d8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1801545dd  mov     ebx, eax
0x1801545df  call    cs:__imp_CoUninitialize
0x1801545e5  mov     eax, ebx
0x1801545e7  mov     rbx, [rsp+48h+arg_0]
0x1801545ec  mov     rsi, [rsp+48h+arg_18]
0x1801545f1  add     rsp, 40h
0x1801545f5  pop     rdi
0x1801545f6  retn
```
