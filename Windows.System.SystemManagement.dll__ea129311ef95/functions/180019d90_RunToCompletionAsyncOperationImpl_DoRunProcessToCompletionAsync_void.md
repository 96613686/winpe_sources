# RunToCompletionAsyncOperationImpl::DoRunProcessToCompletionAsync(void)

- ea: `0x180019d90`
- end: `0x180019fde`
- name: `?DoRunProcessToCompletionAsync@RunToCompletionAsyncOperationImpl@@AEAAXXZ`
- size: `590`
- prototype: `void __fastcall(HANDLE *this)`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001c010`

## callees

- `0x180007248`
- `0x18000fa18`
- `0x1800172b8`
- `0x180018c3c`
- `0x180019ba8`
- `0x180019d90`
- `0x18001adcc`
- `0x18001bdb8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180019ef8`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObjectEx` at `0x180019ef8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f35`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019dfe`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019e63`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019ec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f02`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180019f35`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019de8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019e4d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019eb2`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019de8`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019e4d`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x180019eb2`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180019f2b`
- `api-ms-win-core-processthreads-l1-1-0!GetExitCodeProcess` at `0x180019f2b`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall RunToCompletionAsyncOperationImpl::DoRunProcessToCompletionAsync(HANDLE *this)
{
  signed int ProcessAsCurrentUser; // ebx
  HANDLE Thread; // rax
  signed int LastError; // eax
  HANDLE v5; // rax
  signed int v6; // eax
  HANDLE v7; // rax
  signed int v8; // eax
  signed int v9; // eax
  signed int v10; // eax
  HANDLE v11; // rdx
  HANDLE v12; // rdx
  DWORD ExitCode; // [rsp+60h] [rbp+8h] BYREF

  ProcessAsCurrentUser = RunToCompletionAsyncOperationImpl::PrepStdStreams((RunToCompletionAsyncOperationImpl *)this);
  if ( ProcessAsCurrentUser >= 0 )
  {
    if ( !this[25] )
      goto LABEL_11;
    (*((void (__fastcall **)(HANDLE *))*this + 1))(this);
    Thread = CreateThread(0, 0, RunToCompletionAsyncOperationImpl::s_ReadFromStandardInput, this, 0, 0);
    wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
      this + 31,
      Thread);
    if ( this[31] )
      goto LABEL_11;
    LastError = GetLastError();
    ProcessAsCurrentUser = LastError;
    if ( LastError > 0 )
      ProcessAsCurrentUser = (unsigned __int16)LastError | 0x80070000;
    if ( ProcessAsCurrentUser >= 0 )
    {
LABEL_11:
      if ( !this[26] )
        goto LABEL_16;
      (*((void (__fastcall **)(HANDLE *))*this + 1))(this);
      v5 = CreateThread(0, 0, RunToCompletionAsyncOperationImpl::s_WriteToStandardOutput, this, 0, 0);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        this + 32,
        v5);
      if ( this[32] )
        goto LABEL_16;
      v6 = GetLastError();
      ProcessAsCurrentUser = v6;
      if ( v6 > 0 )
        ProcessAsCurrentUser = (unsigned __int16)v6 | 0x80070000;
      if ( ProcessAsCurrentUser >= 0 )
      {
LABEL_16:
        if ( !this[27] )
          goto LABEL_17;
        (*((void (__fastcall **)(HANDLE *))*this + 1))(this);
        v7 = CreateThread(0, 0, RunToCompletionAsyncOperationImpl::s_WriteToStandardError, this, 0, 0);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          this + 33,
          v7);
        if ( this[33] )
          goto LABEL_17;
        v8 = GetLastError();
        ProcessAsCurrentUser = v8;
        if ( v8 > 0 )
          ProcessAsCurrentUser = (unsigned __int16)v8 | 0x80070000;
        if ( ProcessAsCurrentUser >= 0 )
        {
LABEL_17:
          ProcessAsCurrentUser = RunToCompletionAsyncOperationImpl::CreateProcessAsCurrentUser((RunToCompletionAsyncOperationImpl *)this);
          if ( ProcessAsCurrentUser >= 0 )
          {
            if ( WaitForSingleObjectEx(this[29], 0xFFFFFFFF, 0) )
            {
              v9 = GetLastError();
              ProcessAsCurrentUser = v9;
              if ( v9 > 0 )
                ProcessAsCurrentUser = (unsigned __int16)v9 | 0x80070000;
            }
          }
        }
      }
    }
  }
  ExitCode = -1;
  if ( ProcessAsCurrentUser >= 0 && !GetExitCodeProcess(this[29], &ExitCode) )
  {
    v10 = GetLastError();
    ProcessAsCurrentUser = v10;
    if ( v10 > 0 )
      ProcessAsCurrentUser = (unsigned __int16)v10 | 0x80070000;
  }
  *((_DWORD *)this + 68) = 1;
  if ( ProcessAsCurrentUser >= 0 )
  {
    Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(this + 48);
    ProcessAsCurrentUser = Microsoft::WRL::Details::MakeAndInitialize<ProcessLauncherResultImpl,Windows::System::IProcessLauncherResult,unsigned long &>(
                             this + 48,
                             &ExitCode);
  }
  v11 = this[31];
  if ( v11 )
    RunToCompletionAsyncOperationImpl::WaitForIoThreadComplete((RunToCompletionAsyncOperationImpl *)this, v11);
  v12 = this[32];
  if ( v12 )
    RunToCompletionAsyncOperationImpl::WaitForIoThreadComplete((RunToCompletionAsyncOperationImpl *)this, v12);
  if ( this[32] )
    RunToCompletionAsyncOperationImpl::WaitForIoThreadComplete((RunToCompletionAsyncOperationImpl *)this, this[33]);
  if ( ProcessAsCurrentUser < 0 )
    Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(
      this + 2,
      (unsigned int)ProcessAsCurrentUser);
  (*((void (__fastcall **)(char *))this[2] + 16))((char *)this + 16);
}

```

## disassembly

```asm
0x180019d90  push    rbx
0x180019d92  push    rbp
0x180019d93  push    rsi
0x180019d94  push    rdi
0x180019d95  sub     rsp, 38h
0x180019d99  mov     rdi, rcx
0x180019d9c  call    ?PrepStdStreams@RunToCompletionAsyncOperationImpl@@AEAAJXZ; RunToCompletionAsyncOperationImpl::PrepStdStreams(void)
0x180019da1  xor     esi, esi
0x180019da3  mov     ebx, eax
0x180019da5  mov     ebp, 80070000h
0x180019daa  test    eax, eax
0x180019dac  js      loc_180019F13
0x180019db2  cmp     [rdi+0C8h], rsi
0x180019db9  jz      short loc_180019E17
0x180019dbb  mov     rax, [rdi]
0x180019dbe  mov     rcx, rdi
0x180019dc1  mov     rax, [rax+8]
0x180019dc5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019dca  mov     r9, rdi; lpParameter
0x180019dcd  mov     [rsp+58h+lpThreadId], rsi; lpThreadId
0x180019dd2  lea     r8, ?s_ReadFromStandardInput@RunToCompletionAsyncOperationImpl@@CAKPEAX@Z; lpStartAddress
0x180019dd9  mov     [rsp+58h+dwCreationFlags], esi; dwCreationFlags
0x180019ddd  xor     edx, edx; dwStackSize
0x180019ddf  lea     rbx, [rdi+0F8h]
0x180019de6  xor     ecx, ecx; lpThreadAttributes
0x180019de8  call    cs:__imp_CreateThread
0x180019dee  mov     rdx, rax
0x180019df1  mov     rcx, rbx
0x180019df4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180019df9  cmp     [rbx], rsi
0x180019dfc  jnz     short loc_180019E17
0x180019dfe  call    cs:__imp_GetLastError
0x180019e04  mov     ebx, eax
0x180019e06  test    eax, eax
0x180019e08  jle     short loc_180019E0F
0x180019e0a  movzx   ebx, ax
0x180019e0d  or      ebx, ebp
0x180019e0f  test    ebx, ebx
0x180019e11  js      loc_180019F13
0x180019e17  cmp     [rdi+0D0h], rsi
0x180019e1e  jz      short loc_180019E7C
0x180019e20  mov     rax, [rdi]
0x180019e23  mov     rcx, rdi
0x180019e26  mov     rax, [rax+8]
0x180019e2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e2f  mov     r9, rdi; lpParameter
0x180019e32  mov     [rsp+58h+lpThreadId], rsi; lpThreadId
0x180019e37  lea     r8, ?s_WriteToStandardOutput@RunToCompletionAsyncOperationImpl@@CAKPEAX@Z; lpStartAddress
0x180019e3e  mov     [rsp+58h+dwCreationFlags], esi; dwCreationFlags
0x180019e42  xor     edx, edx; dwStackSize
0x180019e44  lea     rbx, [rdi+100h]
0x180019e4b  xor     ecx, ecx; lpThreadAttributes
0x180019e4d  call    cs:__imp_CreateThread
0x180019e53  mov     rdx, rax
0x180019e56  mov     rcx, rbx
0x180019e59  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180019e5e  cmp     [rbx], rsi
0x180019e61  jnz     short loc_180019E7C
0x180019e63  call    cs:__imp_GetLastError
0x180019e69  mov     ebx, eax
0x180019e6b  test    eax, eax
0x180019e6d  jle     short loc_180019E74
0x180019e6f  movzx   ebx, ax
0x180019e72  or      ebx, ebp
0x180019e74  test    ebx, ebx
0x180019e76  js      loc_180019F13
0x180019e7c  cmp     [rdi+0D8h], rsi
0x180019e83  jz      short loc_180019EDD
0x180019e85  mov     rax, [rdi]
0x180019e88  mov     rcx, rdi
0x180019e8b  mov     rax, [rax+8]
0x180019e8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019e94  mov     r9, rdi; lpParameter
0x180019e97  mov     [rsp+58h+lpThreadId], rsi; lpThreadId
0x180019e9c  lea     r8, ?s_WriteToStandardError@RunToCompletionAsyncOperationImpl@@CAKPEAX@Z; lpStartAddress
0x180019ea3  mov     [rsp+58h+dwCreationFlags], esi; dwCreationFlags
0x180019ea7  xor     edx, edx; dwStackSize
0x180019ea9  lea     rbx, [rdi+108h]
0x180019eb0  xor     ecx, ecx; lpThreadAttributes
0x180019eb2  call    cs:__imp_CreateThread
0x180019eb8  mov     rdx, rax
0x180019ebb  mov     rcx, rbx
0x180019ebe  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x180019ec3  cmp     [rbx], rsi
0x180019ec6  jnz     short loc_180019EDD
0x180019ec8  call    cs:__imp_GetLastError
0x180019ece  mov     ebx, eax
0x180019ed0  test    eax, eax
0x180019ed2  jle     short loc_180019ED9
0x180019ed4  movzx   ebx, ax
0x180019ed7  or      ebx, ebp
0x180019ed9  test    ebx, ebx
0x180019edb  js      short loc_180019F13
0x180019edd  mov     rcx, rdi; this
0x180019ee0  call    ?CreateProcessAsCurrentUser@RunToCompletionAsyncOperationImpl@@AEAAJXZ; RunToCompletionAsyncOperationImpl::CreateProcessAsCurrentUser(void)
0x180019ee5  mov     ebx, eax
0x180019ee7  test    eax, eax
0x180019ee9  js      short loc_180019F13
0x180019eeb  mov     rcx, [rdi+0E8h]; hHandle
0x180019ef2  xor     r8d, r8d; bAlertable
0x180019ef5  or      edx, 0FFFFFFFFh; dwMilliseconds
0x180019ef8  call    cs:__imp_WaitForSingleObjectEx
0x180019efe  test    eax, eax
0x180019f00  jz      short loc_180019F13
0x180019f02  call    cs:__imp_GetLastError
0x180019f08  mov     ebx, eax
0x180019f0a  test    eax, eax
0x180019f0c  jle     short loc_180019F13
0x180019f0e  movzx   ebx, ax
0x180019f11  or      ebx, ebp
0x180019f13  mov     [rsp+58h+ExitCode], 0FFFFFFFFh
0x180019f1b  test    ebx, ebx
0x180019f1d  js      short loc_180019F46
0x180019f1f  mov     rcx, [rdi+0E8h]; hProcess
0x180019f26  lea     rdx, [rsp+58h+ExitCode]; lpExitCode
0x180019f2b  call    cs:__imp_GetExitCodeProcess
0x180019f31  test    eax, eax
0x180019f33  jnz     short loc_180019F46
0x180019f35  call    cs:__imp_GetLastError
0x180019f3b  mov     ebx, eax
0x180019f3d  test    eax, eax
0x180019f3f  jle     short loc_180019F46
0x180019f41  movzx   ebx, ax
0x180019f44  or      ebx, ebp
0x180019f46  mov     dword ptr [rdi+110h], 1
0x180019f50  test    ebx, ebx
0x180019f52  js      short loc_180019F72
0x180019f54  lea     rbx, [rdi+180h]
0x180019f5b  mov     rcx, rbx
0x180019f5e  call    ?InternalRelease@?$ComPtr@U?$IVector@PEAUHSTRING__@@@Collections@Foundation@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::Foundation::Collections::IVector<HSTRING__ *>>::InternalRelease(void)
0x180019f63  lea     rdx, [rsp+58h+ExitCode]
0x180019f68  mov     rcx, rbx
0x180019f6b  call    ??$MakeAndInitialize@VProcessLauncherResultImpl@@UIProcessLauncherResult@System@Windows@@AEAK@Details@WRL@Microsoft@@YAJPEAPEAUIProcessLauncherResult@System@Windows@@AEAK@Z; Microsoft::WRL::Details::MakeAndInitialize<ProcessLauncherResultImpl,Windows::System::IProcessLauncherResult,ulong &>(Windows::System::IProcessLauncherResult * *,ulong &)
0x180019f70  mov     ebx, eax
0x180019f72  mov     rdx, [rdi+0F8h]; void *
0x180019f79  test    rdx, rdx
0x180019f7c  jz      short loc_180019F86
0x180019f7e  mov     rcx, rdi; this
0x180019f81  call    ?WaitForIoThreadComplete@RunToCompletionAsyncOperationImpl@@AEAAXPEAX@Z; RunToCompletionAsyncOperationImpl::WaitForIoThreadComplete(void *)
0x180019f86  mov     rdx, [rdi+100h]; void *
0x180019f8d  test    rdx, rdx
0x180019f90  jz      short loc_180019F9A
0x180019f92  mov     rcx, rdi; this
0x180019f95  call    ?WaitForIoThreadComplete@RunToCompletionAsyncOperationImpl@@AEAAXPEAX@Z; RunToCompletionAsyncOperationImpl::WaitForIoThreadComplete(void *)
0x180019f9a  cmp     [rdi+100h], rsi
0x180019fa1  jz      short loc_180019FB2
0x180019fa3  mov     rdx, [rdi+108h]; void *
0x180019faa  mov     rcx, rdi; this
0x180019fad  call    ?WaitForIoThreadComplete@RunToCompletionAsyncOperationImpl@@AEAAXPEAX@Z; RunToCompletionAsyncOperationImpl::WaitForIoThreadComplete(void *)
0x180019fb2  test    ebx, ebx
0x180019fb4  jns     short loc_180019FC1
0x180019fb6  mov     edx, ebx
0x180019fb8  lea     rcx, [rdi+10h]
0x180019fbc  call    ?TryTransitionToError@?$AsyncBase@U?$IAsyncOperationCompletedHandler@PEAVProcessLauncherResult@System@Windows@@@Foundation@Windows@@VNil@Details@WRL@Microsoft@@$00U?$AsyncOptions@$0?0$0A@$1?GUID_CAUSALITY_WINDOWS_PLATFORM_ID@@3U_GUID@@B$01@67@@WRL@Microsoft@@IEAA_NJW4CancelTransitionPolicy@23@PEAX@Z; Microsoft::WRL::AsyncBase<Windows::Foundation::IAsyncOperationCompletedHandler<Windows::System::ProcessLauncherResult *>,Microsoft::WRL::Details::Nil,1,Microsoft::WRL::AsyncOptions<-1,0,&_GUID const GUID_CAUSALITY_WINDOWS_PLATFORM_ID,2>>::TryTransitionToError(long,Microsoft::WRL::CancelTransitionPolicy,void *)
0x180019fc1  mov     rax, [rdi+10h]
0x180019fc5  lea     rcx, [rdi+10h]
0x180019fc9  mov     rax, [rax+80h]
0x180019fd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019fd5  add     rsp, 38h
0x180019fd9  pop     rdi
0x180019fda  pop     rsi
0x180019fdb  pop     rbp
0x180019fdc  pop     rbx
0x180019fdd  retn
```
