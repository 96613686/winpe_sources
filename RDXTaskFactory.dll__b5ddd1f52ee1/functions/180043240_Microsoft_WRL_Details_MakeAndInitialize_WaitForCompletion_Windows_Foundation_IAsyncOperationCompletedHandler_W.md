# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Internal::StartupTaskInternal *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Internal::StartupTaskInternal *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Internal::StartupTaskInternal *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180043240`
- end: `0x180043310`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180043580`

## callees

- `0x18000534c`
- `0x180008bbc`
- `0x18000e264`
- `0x180043240`
- `0x180043db4`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800432a1`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x1800432a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432b0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800432b0`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_PEAVStartupTaskInternal_Internal_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
        _QWORD *a1)
{
  void *v2; // rax
  signed int v3; // ebx
  _QWORD *v4; // rdi
  HANDLE Event; // rax
  signed int LastError; // eax
  __int64 v7; // rdx
  __int64 v8; // r8
  __int64 v9; // rdx
  __int64 v10; // r8
  _QWORD *v12; // [rsp+30h] [rbp+8h] BYREF
  void *v13; // [rsp+38h] [rbp+10h] BYREF

  *a1 = 0;
  v2 = operator new(0x40u, (const struct std::nothrow_t *)&std::nothrow);
  v13 = v2;
  if ( v2 )
  {
    v4 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Internal::StartupTaskInternal *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
    v12 = v4;
    v13 = 0;
    Event = CreateEventExW(0, 0, 0, 0x1F0003u);
    v4[7] = Event;
    if ( Event )
      goto LABEL_8;
    LastError = GetLastError();
    v3 = LastError;
    if ( LastError > 0 )
      v3 = (unsigned __int16)LastError | 0x80070000;
    if ( v3 >= 0 )
    {
LABEL_8:
      (*(void (__fastcall **)(_QWORD *))(*v4 + 8LL))(v4);
      *a1 = v4;
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12, v9, v10);
      v3 = 0;
    }
    else
    {
      Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(&v12, v7, v8);
    }
  }
  else
  {
    v3 = -2147024882;
  }
  Microsoft::WRL::Details::MakeAllocator<SetWallpaperTask>::~MakeAllocator<SetWallpaperTask>(&v13);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x180043240  mov     [rsp+arg_10], rbx
0x180043245  mov     [rsp+arg_18], rsi
0x18004324a  push    rdi
0x18004324b  sub     rsp, 20h
0x18004324f  mov     rsi, rcx
0x180043252  mov     qword ptr [rcx], 0
0x180043259  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180043260  mov     ecx, 40h ; '@'; unsigned __int64
0x180043265  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18004326a  mov     [rsp+28h+arg_8], rax
0x18004326f  test    rax, rax
0x180043272  jnz     short loc_18004327B
0x180043274  mov     ebx, 8007000Eh
0x180043279  jmp     short loc_1800432F4
0x18004327b  mov     rcx, rax
0x18004327e  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@PEAVStartupTaskInternal@Internal@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::Internal::StartupTaskInternal *>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::Internal::StartupTaskInternal *> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x180043283  mov     rdi, rax
0x180043286  mov     [rsp+28h+arg_0], rax
0x18004328b  mov     [rsp+28h+arg_8], 0
0x180043294  mov     r9d, 1F0003h; dwDesiredAccess
0x18004329a  xor     r8d, r8d; dwFlags
0x18004329d  xor     edx, edx; lpName
0x18004329f  xor     ecx, ecx; lpEventAttributes
0x1800432a1  call    cs:__imp_CreateEventExW
0x1800432a7  mov     [rdi+38h], rax
0x1800432ab  test    rax, rax
0x1800432ae  jnz     short loc_1800432D5
0x1800432b0  call    cs:__imp_GetLastError
0x1800432b6  mov     ebx, eax
0x1800432b8  test    eax, eax
0x1800432ba  jle     short loc_1800432C5
0x1800432bc  movzx   ebx, ax
0x1800432bf  or      ebx, 80070000h
0x1800432c5  test    ebx, ebx
0x1800432c7  jns     short loc_1800432D5
0x1800432c9  lea     rcx, [rsp+28h+arg_0]
0x1800432ce  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800432d3  jmp     short loc_1800432F4
0x1800432d5  mov     rax, [rdi]
0x1800432d8  mov     rcx, rdi
0x1800432db  mov     rax, [rax+8]
0x1800432df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800432e4  nop
0x1800432e5  mov     [rsi], rdi
0x1800432e8  lea     rcx, [rsp+28h+arg_0]
0x1800432ed  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800432f2  xor     ebx, ebx
0x1800432f4  lea     rcx, [rsp+28h+arg_8]
0x1800432f9  call    ??1?$MakeAllocator@VSetWallpaperTask@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SetWallpaperTask>::~MakeAllocator<SetWallpaperTask>(void)
0x1800432fe  mov     eax, ebx
0x180043300  mov     rbx, [rsp+28h+arg_10]
0x180043305  mov     rsi, [rsp+28h+arg_18]
0x18004330a  add     rsp, 20h
0x18004330e  pop     rdi
0x18004330f  retn
```
