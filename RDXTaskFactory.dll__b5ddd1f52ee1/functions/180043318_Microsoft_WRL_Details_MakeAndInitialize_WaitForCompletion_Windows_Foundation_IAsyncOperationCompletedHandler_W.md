# Microsoft::WRL::Details::MakeAndInitialize<`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::StartupTaskState>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::StartupTaskState>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::StartupTaskState> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::StartupTaskState>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::StartupTaskState>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::StartupTaskState> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate,>(`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::StartupTaskState>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::StartupTaskState>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::StartupTaskState> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate * *)

- ea: `0x180043318`
- end: `0x1800433e8`
- name: `??$MakeAndInitialize@VFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4StartupTaskState@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4StartupTaskState@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4StartupTaskState@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@V1?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4StartupTaskState@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4StartupTaskState@ApplicationModel@Windows@@@23@@@YAJ012@Z@$$V@Details@WRL@Microsoft@@YAJPEAPEAVFTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4StartupTaskState@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4StartupTaskState@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4StartupTaskState@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@@Z`
- size: `208`
- prototype: `__int64 __fastcall(_QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, service_task, broker_com_uri`

## callers

- `0x180043710`

## callees

- `0x18000534c`
- `0x180008bbc`
- `0x18000e264`
- `0x180043318`
- `0x180043e44`
- `0x180050010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180043379`
- `api-ms-win-core-synch-l1-1-0!CreateEventExW` at `0x180043379`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043388`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180043388`

## pseudocode

```c
__int64 __fastcall ___MakeAndInitialize_VFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4StartupTaskState_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4StartupTaskState_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_W4StartupTaskState_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z_V1_1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4StartupTaskState_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4StartupTaskState_ApplicationModel_Windows___23___YAJ012_Z___V_Details_WRL_Microsoft__YAJPEAPEAVFTMEventDelegate__1____WaitForCompletion_U__IAsyncOperationCompletedHandler_W4StartupTaskState_ApplicationModel_Windows___Foundation_Windows__U__IAsyncOperation_W4StartupTaskState_ApplicationModel_Windows___23___YAJPEAU__IAsyncOperation_W4StartupTaskState_ApplicationModel_Windows___Foundation_Windows__W4tagCOWAIT_FLAGS__PEAX_Z__Z(
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
    v4 = (_QWORD *)`WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<enum Windows::ApplicationModel::StartupTaskState>,Windows::Foundation::IAsyncOperation<enum Windows::ApplicationModel::StartupTaskState>>'::`2'::FTMEventDelegate::FTMEventDelegate(v2);
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
0x180043318  mov     [rsp+arg_10], rbx
0x18004331d  mov     [rsp+arg_18], rsi
0x180043322  push    rdi
0x180043323  sub     rsp, 20h
0x180043327  mov     rsi, rcx
0x18004332a  mov     qword ptr [rcx], 0
0x180043331  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180043338  mov     ecx, 40h ; '@'; unsigned __int64
0x18004333d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x180043342  mov     [rsp+28h+arg_8], rax
0x180043347  test    rax, rax
0x18004334a  jnz     short loc_180043353
0x18004334c  mov     ebx, 8007000Eh
0x180043351  jmp     short loc_1800433CC
0x180043353  mov     rcx, rax
0x180043356  call    ??0FTMEventDelegate@?1???$WaitForCompletion@U?$IAsyncOperationCompletedHandler@W4StartupTaskState@ApplicationModel@Windows@@@Foundation@Windows@@U?$IAsyncOperation@W4StartupTaskState@ApplicationModel@Windows@@@23@@@YAJPEAU?$IAsyncOperation@W4StartupTaskState@ApplicationModel@Windows@@@Foundation@Windows@@W4tagCOWAIT_FLAGS@@PEAX@Z@QEAA@XZ; `WaitForCompletion<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::ApplicationModel::StartupTaskState>,Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::StartupTaskState>>(Windows::Foundation::IAsyncOperation<Windows::ApplicationModel::StartupTaskState> *,tagCOWAIT_FLAGS,void *)'::`2'::FTMEventDelegate::FTMEventDelegate(void)
0x18004335b  mov     rdi, rax
0x18004335e  mov     [rsp+28h+arg_0], rax
0x180043363  mov     [rsp+28h+arg_8], 0
0x18004336c  mov     r9d, 1F0003h; dwDesiredAccess
0x180043372  xor     r8d, r8d; dwFlags
0x180043375  xor     edx, edx; lpName
0x180043377  xor     ecx, ecx; lpEventAttributes
0x180043379  call    cs:__imp_CreateEventExW
0x18004337f  mov     [rdi+38h], rax
0x180043383  test    rax, rax
0x180043386  jnz     short loc_1800433AD
0x180043388  call    cs:__imp_GetLastError
0x18004338e  mov     ebx, eax
0x180043390  test    eax, eax
0x180043392  jle     short loc_18004339D
0x180043394  movzx   ebx, ax
0x180043397  or      ebx, 80070000h
0x18004339d  test    ebx, ebx
0x18004339f  jns     short loc_1800433AD
0x1800433a1  lea     rcx, [rsp+28h+arg_0]
0x1800433a6  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800433ab  jmp     short loc_1800433CC
0x1800433ad  mov     rax, [rdi]
0x1800433b0  mov     rcx, rdi
0x1800433b3  mov     rax, [rax+8]
0x1800433b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800433bc  nop
0x1800433bd  mov     [rsi], rdi
0x1800433c0  lea     rcx, [rsp+28h+arg_0]
0x1800433c5  call    ?InternalRelease@?$ComPtr@UIUnknown@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<IUnknown>::InternalRelease(void)
0x1800433ca  xor     ebx, ebx
0x1800433cc  lea     rcx, [rsp+28h+arg_8]
0x1800433d1  call    ??1?$MakeAllocator@VSetWallpaperTask@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<SetWallpaperTask>::~MakeAllocator<SetWallpaperTask>(void)
0x1800433d6  mov     eax, ebx
0x1800433d8  mov     rbx, [rsp+28h+arg_10]
0x1800433dd  mov     rsi, [rsp+28h+arg_18]
0x1800433e2  add     rsp, 20h
0x1800433e6  pop     rdi
0x1800433e7  retn
```
