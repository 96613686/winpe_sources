# FSSourceWatchdog::WatchdogAction(_TP_CALLBACK_INSTANCE *,_TP_TIMER *)

- ea: `0x1800b4b30`
- end: `0x1800b503e`
- name: `?WatchdogAction@FSSourceWatchdog@@MEAAXPEAU_TP_CALLBACK_INSTANCE@@PEAU_TP_TIMER@@@Z`
- size: `1294`
- prototype: `void __fastcall(FSSourceWatchdog *__hidden this, struct _TP_CALLBACK_INSTANCE *, struct _TP_TIMER *)`
- caller_count: `0`
- callee_count: `20`
- tags: `authz_impersonation, registry_config, broker_com_uri`

## callees

- `0x180003e20`
- `0x18000478c`
- `0x180007bcc`
- `0x180008cf0`
- `0x180009494`
- `0x1800095c8`
- `0x180009608`
- `0x180009658`
- `0x18000a880`
- `0x1800198f4`
- `0x18001c444`
- `0x18006180c`
- `0x1800b3b88`
- `0x1800b3d0c`
- `0x1800b4b30`
- `0x1800b5044`
- `0x1800b5180`
- `0x1800b524c`
- `0x1800e924c`
- `0x1800ea010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b4f6f`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x1800b4f6f`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x1800b4d82`
- `api-ms-win-core-processthreads-l1-1-0!SuspendThread` at `0x1800b4d82`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800b4d55`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800b4ec6`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800b4d55`
- `api-ms-win-core-processthreads-l1-1-0!OpenThread` at `0x1800b4ec6`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800b4bf5`
- `api-ms-win-core-processthreads-l1-1-0!TerminateProcess` at `0x1800b4bf5`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b4bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcess` at `0x1800b4bea`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b4fac`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentProcessId` at `0x1800b4fac`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b4fd3`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800b4fd3`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b4dec`
- `api-ms-win-core-synch-l1-2-0!Sleep` at `0x1800b4dec`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x1800b4d98`
- `api-ms-win-core-processthreads-l1-1-1!GetThreadContext` at `0x1800b4d98`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b5001`
- `api-ms-win-core-errorhandling-l1-1-2!RaiseFailFastException` at `0x1800b5001`
- `api-ms-win-core-processthreads-l1-1-3!GetThreadDescription` at `0x1800b4eff`
- `api-ms-win-core-processthreads-l1-1-3!GetThreadDescription` at `0x1800b4eff`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterMemoryBlock` at `0x1800b4d04`
- `api-ms-win-core-windowserrorreporting-l1-1-0!WerRegisterMemoryBlock` at `0x1800b4d04`

## pseudocode

```c
void __fastcall FSSourceWatchdog::WatchdogAction(
        FSSourceWatchdog *this,
        struct _TP_CALLBACK_INSTANCE *a2,
        struct _TP_TIMER *a3)
{
  char v3; // r15
  HANDLE CurrentProcess; // rax
  DWORD v6; // r14d
  __int64 v7; // rdx
  PVOID v8; // rcx
  __int64 v9; // r12
  void (__fastcall *v10)(__int64, PVOID *); // rbx
  const unsigned __int16 *v11; // rax
  DWORD v12; // eax
  __int64 v13; // rcx
  int v14; // eax
  DWORD v15; // r8d
  HANDLE v16; // rax
  HANDLE v17; // r13
  DWORD v18; // ebx
  int v19; // r8d
  HANDLE v20; // rax
  bool v21; // r12
  int v22; // eax
  DWORD CurrentProcessId; // eax
  const unsigned __int16 *v24; // rdx
  HLOCAL v25; // rcx
  DWORD v26; // eax
  PVOID pvAddress; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hThread; // [rsp+48h] [rbp-B8h] BYREF
  HLOCAL hMem; // [rsp+50h] [rbp-B0h] BYREF
  DWORD dwThreadId[4]; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v31; // [rsp+68h] [rbp-98h]
  struct _EXCEPTION_RECORD pExceptionRecord; // [rsp+70h] [rbp-90h] BYREF
  CONTEXT Context; // [rsp+110h] [rbp+10h] BYREF

  v3 = 0;
  LODWORD(pvAddress) = 0;
  if ( *((_QWORD *)this + 97) == 0x7FFFFFFFFFFFFFFFLL )
  {
    pvAddress = 0;
    hThread = 0;
    memset_0(&Context, 0, sizeof(Context));
    v6 = 0;
    memset_0(&pExceptionRecord.ExceptionRecord, 0, 0x90u);
    v7 = *((_QWORD *)this + 96);
    pExceptionRecord.ExceptionFlags = 1;
    pExceptionRecord.ExceptionCode = -805306369;
    Context.ContextFlags = 1048607;
    wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(&pvAddress, v7);
    v8 = pvAddress;
    if ( pvAddress
      || (v9 = *((_QWORD *)this + 94)) != 0
      && (v10 = *(void (__fastcall **)(__int64, PVOID *))(*(_QWORD *)v9 + 48LL),
          wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(&pvAddress),
          v10(v9, &pvAddress),
          (v8 = pvAddress) != 0) )
    {
      v11 = (const unsigned __int16 *)(*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)v8 + 312LL))(v8);
      StringCchCopyW((unsigned __int16 *)this + 392, 0x69u, v11);
      (*(void (__fastcall **)(PVOID, char *, __int64, char *))(*(_QWORD *)pvAddress + 328LL))(
        pvAddress,
        (char *)this + 1000,
        7,
        (char *)this + 1784);
      v12 = (*(__int64 (__fastcall **)(PVOID))(*(_QWORD *)pvAddress + 208LL))(pvAddress);
      WerRegisterMemoryBlock(pvAddress, v12);
    }
    v13 = *((_QWORD *)this + 95);
    if ( v13 )
    {
      v31 = 0;
      *(_OWORD *)dwThreadId = 0;
      v14 = (*(__int64 (__fastcall **)(__int64, DWORD *, __int64))(*(_QWORD *)v13 + 40LL))(v13, dwThreadId, 1);
      if ( v14 >= 0 )
      {
        v6 = dwThreadId[0];
        v15 = dwThreadId[0];
        *((_DWORD *)this + 186) = dwThreadId[0];
        v16 = OpenThread(0xAu, 0, v15);
        wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
          &hThread,
          v16);
        v17 = hThread;
        v18 = 1;
        if ( (((unsigned __int64)hThread + 1) & 0xFFFFFFFFFFFFFFFEuLL) != 0
          && SuspendThread(hThread) != -1
          && GetThreadContext(v17, &Context) )
        {
          v18 = 0;
          pExceptionRecord.ExceptionAddress = (PVOID)Context.Rip;
        }
        goto LABEL_23;
      }
      if ( v14 == -1072869852 )
      {
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 17, &WPP_26f50317b41939831fb096d13f0bfc88_Traceguids, this);
        Sleep(0xEA60u);
        if ( (unsigned __int8)byte_18010EC4D >= 8u )
          WPP_SF_q(*((_QWORD *)WPP_GLOBAL_Control + 27), 18, &WPP_26f50317b41939831fb096d13f0bfc88_Traceguids, this);
        goto LABEL_48;
      }
    }
    v18 = 1;
LABEL_23:
    if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_FSWatchdogWppExceptionCode>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_FSWatchdogWppExceptionCode>::GetImpl'::`2'::impl) )
    {
      if ( byte_18010EC4D )
        WPP_SF_qdDDS(
          *((_QWORD *)WPP_GLOBAL_Control + 27),
          19,
          v19,
          (_DWORD)this,
          *((_DWORD *)this + 13),
          v6,
          *((_DWORD *)this + 20),
          (__int64)this + 216);
    }
    else if ( byte_18010EC4D )
    {
      WPP_SF_qdDDS(
        *((_QWORD *)WPP_GLOBAL_Control + 27),
        20,
        v19,
        (_DWORD)this,
        *((_DWORD *)this + 13),
        v6,
        255,
        (__int64)this + 216);
    }
    if ( *((_DWORD *)this + 21) < 0xFu )
    {
      *((_QWORD *)this + (unsigned int)(*((_DWORD *)this + 21))++ + 11) = v6;
      hMem = 0;
      v20 = OpenThread(0x800u, 0, v6);
      wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
        &hThread,
        v20);
      v21 = 0;
      if ( hThread )
      {
        *(_QWORD *)&dwThreadId[2] = 0;
        *(_QWORD *)dwThreadId = &hMem;
        LOBYTE(v31) = 1;
        v3 = 1;
        if ( GetThreadDescription(hThread, (PWSTR *)&dwThreadId[2]) >= 0 )
          v21 = 1;
      }
      if ( (v3 & 1) != 0 )
        wil::details::out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<unsigned short [0],wil::function_deleter<void * (*)(void *),&void * LocalFree(void *)>>>(dwThreadId);
      if ( v21 )
      {
        if ( byte_18010EC4D )
          WPP_SF_qDS(
            *((_QWORD *)WPP_GLOBAL_Control + 27),
            21,
            (unsigned int)&WPP_26f50317b41939831fb096d13f0bfc88_Traceguids,
            (_DWORD)this,
            v6,
            (__int64)hMem);
        v22 = _o__wcsicmp(hMem, L"mfdebucketize_kssynchronouscontrol");
        if ( v6 && !v22 )
        {
          if ( byte_18010EC4D )
            WPP_SF_qD(
              *((_QWORD *)WPP_GLOBAL_Control + 27),
              22,
              &WPP_26f50317b41939831fb096d13f0bfc88_Traceguids,
              this,
              v6);
          CurrentProcessId = GetCurrentProcessId();
          FSSourceWatchdog::GenerateKernelDump(this, v24, CurrentProcessId, v6);
        }
      }
      v25 = hMem;
      hMem = 0;
      if ( v25 )
        LocalFree(v25);
    }
    v26 = *((_DWORD *)this + 21);
    pExceptionRecord.NumberParameters = v26;
    if ( v26 )
      memcpy_0(pExceptionRecord.ExceptionInformation, (char *)this + 88, 8LL * v26);
    RaiseFailFastException(&pExceptionRecord, 0, v18);
LABEL_48:
    wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hThread);
    wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(&pvAddress);
    return;
  }
  if ( (Microsoft_Windows_MF_FrameServerEnableBits & 4) != 0 )
    McTemplateU0qxqd_EventWriteTransfer(
      (_DWORD)this,
      (_DWORD)a2,
      *((_DWORD *)this + 14),
      *((_QWORD *)this + 9),
      *((_DWORD *)this + 13),
      *((_DWORD *)this + 20));
  if ( byte_18010EC4D )
    WPP_SF_qdqDS(
      *((_QWORD *)WPP_GLOBAL_Control + 27),
      (_DWORD)a2,
      (_DWORD)a3,
      (_DWORD)this,
      *((_DWORD *)this + 13),
      *((_QWORD *)this + 9),
      *((_DWORD *)this + 20),
      (__int64)this + 216);
  CurrentProcess = GetCurrentProcess();
  TerminateProcess(CurrentProcess, 0);
}

```

## disassembly

```asm
0x1800b4b30  push    rbp
0x1800b4b32  push    rbx
0x1800b4b33  push    rsi
0x1800b4b34  push    rdi
0x1800b4b35  push    r12
0x1800b4b37  push    r13
0x1800b4b39  push    r14
0x1800b4b3b  push    r15
0x1800b4b3d  lea     rbp, [rsp-4F8h]
0x1800b4b45  sub     rsp, 5F8h
0x1800b4b4c  mov     rax, cs:__security_cookie
0x1800b4b53  xor     rax, rsp
0x1800b4b56  mov     [rbp+530h+var_50], rax
0x1800b4b5d  xor     r15d, r15d
0x1800b4b60  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800b4b6a  mov     dword ptr [rsp+630h+pvAddress], r15d
0x1800b4b6f  mov     rdi, rcx
0x1800b4b72  cmp     [rcx+308h], rax
0x1800b4b79  jz      loc_1800B4C00
0x1800b4b7f  test    cs:Microsoft_Windows_MF_FrameServerEnableBits, 4
0x1800b4b86  jz      short loc_1800B4BA3
0x1800b4b88  mov     eax, [rcx+50h]
0x1800b4b8b  mov     r9, [rcx+48h]
0x1800b4b8f  mov     r8d, [rcx+38h]
0x1800b4b93  mov     dword ptr [rsp+630h+var_608], eax
0x1800b4b97  mov     eax, [rcx+34h]
0x1800b4b9a  mov     [rsp+630h+var_610], eax
0x1800b4b9e  call    McTemplateU0qxqd_EventWriteTransfer
0x1800b4ba3  mov     esi, 1
0x1800b4ba8  cmp     cs:byte_18010EC4D, sil
0x1800b4baf  jb      short loc_1800B4BEA
0x1800b4bb1  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4bb8  lea     rax, [rdi+0D8h]
0x1800b4bbf  mov     [rsp+630h+var_5F8], rax
0x1800b4bc4  mov     r9, rdi
0x1800b4bc7  mov     eax, [rdi+50h]
0x1800b4bca  mov     [rsp+630h+var_600], eax
0x1800b4bce  mov     rax, [rdi+48h]
0x1800b4bd2  mov     rcx, [rcx+0D8h]
0x1800b4bd9  mov     [rsp+630h+var_608], rax
0x1800b4bde  mov     eax, [rdi+34h]
0x1800b4be1  mov     [rsp+630h+var_610], eax
0x1800b4be5  call    WPP_SF_qdqDS
0x1800b4bea  call    cs:__imp_GetCurrentProcess
0x1800b4bf0  mov     rcx, rax; hProcess
0x1800b4bf3  xor     edx, edx; uExitCode
0x1800b4bf5  call    cs:__imp_TerminateProcess
0x1800b4bfb  jmp     loc_1800B501B
0x1800b4c00  xor     edx, edx; Val
0x1800b4c02  mov     [rsp+630h+pvAddress], r15
0x1800b4c07  mov     r8d, 4D0h; Size
0x1800b4c0d  mov     [rsp+630h+hThread], r15
0x1800b4c12  lea     rcx, [rbp+530h+Context]; void *
0x1800b4c16  call    memset_0
0x1800b4c1b  xor     edx, edx; Val
0x1800b4c1d  lea     rcx, [rsp+630h+pExceptionRecord.ExceptionRecord]; void *
0x1800b4c22  mov     r8d, 90h; Size
0x1800b4c28  xor     r14d, r14d
0x1800b4c2b  call    memset_0
0x1800b4c30  mov     rdx, [rdi+300h]
0x1800b4c37  lea     esi, [r14+1]
0x1800b4c3b  lea     rcx, [rsp+630h+pvAddress]
0x1800b4c40  mov     [rsp+630h+pExceptionRecord.ExceptionFlags], esi
0x1800b4c44  mov     [rsp+630h+pExceptionRecord.ExceptionCode], 0CFFFFFFFh
0x1800b4c4c  mov     [rbp+530h+Context.ContextFlags], 10001Fh
0x1800b4c53  call    ??4?$com_ptr_t@UIFSClientContextInfo@@Uerr_returncode_policy@wil@@@wil@@QEAAAEAV01@PEAUIFSClientContextInfo@@@Z; wil::com_ptr_t<IFSClientContextInfo,wil::err_returncode_policy>::operator=(IFSClientContextInfo *)
0x1800b4c58  mov     rcx, [rsp+630h+pvAddress]
0x1800b4c5d  test    rcx, rcx
0x1800b4c60  jnz     short loc_1800B4C9E
0x1800b4c62  mov     r12, [rdi+2F0h]
0x1800b4c69  test    r12, r12
0x1800b4c6c  jz      loc_1800B4D0A
0x1800b4c72  mov     rax, [r12]
0x1800b4c76  lea     rcx, [rsp+630h+pvAddress]
0x1800b4c7b  mov     rbx, [rax+30h]
0x1800b4c7f  call    ?reset@?$com_ptr_t@UIFSProcessActivities@@Uerr_returncode_policy@wil@@@wil@@QEAAXXZ; wil::com_ptr_t<IFSProcessActivities,wil::err_returncode_policy>::reset(void)
0x1800b4c84  lea     rdx, [rsp+630h+pvAddress]
0x1800b4c89  mov     rcx, r12
0x1800b4c8c  mov     rax, rbx
0x1800b4c8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4c94  mov     rcx, [rsp+630h+pvAddress]
0x1800b4c99  test    rcx, rcx
0x1800b4c9c  jz      short loc_1800B4D0A
0x1800b4c9e  mov     rax, [rcx]
0x1800b4ca1  mov     rax, [rax+138h]
0x1800b4ca8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4cad  mov     r8, rax; unsigned __int16 *
0x1800b4cb0  lea     rcx, [rdi+310h]; unsigned __int16 *
0x1800b4cb7  mov     edx, 69h ; 'i'; unsigned __int64
0x1800b4cbc  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x1800b4cc1  mov     rcx, [rsp+630h+pvAddress]
0x1800b4cc6  lea     r9, [rdi+6F8h]
0x1800b4ccd  lea     rdx, [rdi+3E8h]
0x1800b4cd4  mov     r8d, 7
0x1800b4cda  mov     rax, [rcx]
0x1800b4cdd  mov     rax, [rax+148h]
0x1800b4ce4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4ce9  mov     rcx, [rsp+630h+pvAddress]
0x1800b4cee  mov     rax, [rcx]
0x1800b4cf1  mov     rax, [rax+0D0h]
0x1800b4cf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4cfd  mov     rcx, [rsp+630h+pvAddress]; pvAddress
0x1800b4d02  mov     edx, eax; dwSize
0x1800b4d04  call    cs:__imp_WerRegisterMemoryBlock
0x1800b4d0a  mov     rcx, [rdi+2F8h]
0x1800b4d11  test    rcx, rcx
0x1800b4d14  jz      loc_1800B4E26
0x1800b4d1a  xor     eax, eax
0x1800b4d1c  lea     rdx, [rsp+630h+dwThreadId]
0x1800b4d21  mov     [rsp+630h+var_5C8], rax
0x1800b4d26  xorps   xmm0, xmm0
0x1800b4d29  movups  xmmword ptr [rsp+630h+dwThreadId], xmm0
0x1800b4d2e  mov     rax, [rcx]
0x1800b4d31  mov     r8d, esi
0x1800b4d34  mov     rax, [rax+28h]
0x1800b4d38  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800b4d3d  test    eax, eax
0x1800b4d3f  js      short loc_1800B4DB5
0x1800b4d41  mov     r14d, [rsp+630h+dwThreadId]
0x1800b4d46  xor     edx, edx; bInheritHandle
0x1800b4d48  mov     r8d, r14d; dwThreadId
0x1800b4d4b  mov     [rdi+2E8h], r14d
0x1800b4d52  lea     ecx, [rdx+0Ah]; dwDesiredAccess
0x1800b4d55  call    cs:__imp_OpenThread
0x1800b4d5b  mov     rdx, rax
0x1800b4d5e  lea     rcx, [rsp+630h+hThread]
0x1800b4d63  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b4d68  mov     r13, [rsp+630h+hThread]
0x1800b4d6d  mov     ebx, esi
0x1800b4d6f  lea     rax, [r13+1]
0x1800b4d73  test    rax, 0FFFFFFFFFFFFFFFEh
0x1800b4d79  jz      loc_1800B4E28
0x1800b4d7f  mov     rcx, r13; hThread
0x1800b4d82  call    cs:__imp_SuspendThread
0x1800b4d88  cmp     eax, 0FFFFFFFFh
0x1800b4d8b  jz      loc_1800B4E28
0x1800b4d91  lea     rdx, [rbp+530h+Context]; lpContext
0x1800b4d95  mov     rcx, r13; hThread
0x1800b4d98  call    cs:__imp_GetThreadContext
0x1800b4d9e  test    eax, eax
0x1800b4da0  jz      loc_1800B4E28
0x1800b4da6  mov     rax, [rbp+530h+Context.Rip]
0x1800b4dad  xor     ebx, ebx
0x1800b4daf  mov     [rbp+530h+pExceptionRecord.ExceptionAddress], rax
0x1800b4db3  jmp     short loc_1800B4E28
0x1800b4db5  cmp     eax, 0C00D4E24h
0x1800b4dba  jnz     short loc_1800B4E26
0x1800b4dbc  cmp     cs:byte_18010EC4D, 8
0x1800b4dc3  jb      short loc_1800B4DE7
0x1800b4dc5  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4dcc  lea     r8, WPP_26f50317b41939831fb096d13f0bfc88_Traceguids
0x1800b4dd3  mov     edx, 11h
0x1800b4dd8  mov     r9, rdi
0x1800b4ddb  mov     rcx, [rcx+0D8h]
0x1800b4de2  call    WPP_SF_q
0x1800b4de7  mov     ecx, 0EA60h; dwMilliseconds
0x1800b4dec  call    cs:__imp_Sleep
0x1800b4df2  cmp     cs:byte_18010EC4D, 8
0x1800b4df9  jb      loc_1800B5007
0x1800b4dff  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4e06  lea     r8, WPP_26f50317b41939831fb096d13f0bfc88_Traceguids
0x1800b4e0d  mov     edx, 12h
0x1800b4e12  mov     r9, rdi
0x1800b4e15  mov     rcx, [rcx+0D8h]
0x1800b4e1c  call    WPP_SF_q
0x1800b4e21  jmp     loc_1800B5007
0x1800b4e26  mov     ebx, esi
0x1800b4e28  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_FSWatchdogWppExceptionCode@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_FSWatchdogWppExceptionCode@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FSWatchdogWppExceptionCode> `wil::Feature<__WilFeatureTraits_Feature_FSWatchdogWppExceptionCode>::GetImpl(void)'::`2'::impl
0x1800b4e2f  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_FSWatchdogWppExceptionCode@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_FSWatchdogWppExceptionCode>::__private_IsEnabled(void)
0x1800b4e34  test    al, al
0x1800b4e36  jz      short loc_1800B4E5B
0x1800b4e38  cmp     cs:byte_18010EC4D, sil
0x1800b4e3f  jb      short loc_1800B4E9F
0x1800b4e41  lea     rax, [rdi+0D8h]
0x1800b4e48  mov     edx, 13h
0x1800b4e4d  mov     [rsp+630h+var_5F8], rax
0x1800b4e52  mov     eax, [rdi+50h]
0x1800b4e55  mov     [rsp+630h+var_600], eax
0x1800b4e59  jmp     short loc_1800B4E7D
0x1800b4e5b  cmp     cs:byte_18010EC4D, sil
0x1800b4e62  jb      short loc_1800B4E9F
0x1800b4e64  lea     rax, [rdi+0D8h]
0x1800b4e6b  mov     edx, 14h
0x1800b4e70  mov     [rsp+630h+var_5F8], rax
0x1800b4e75  mov     [rsp+630h+var_600], 0CFFFFFFFh
0x1800b4e7d  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4e84  mov     r9, rdi
0x1800b4e87  mov     eax, [rdi+34h]
0x1800b4e8a  mov     dword ptr [rsp+630h+var_608], r14d
0x1800b4e8f  mov     [rsp+630h+var_610], eax
0x1800b4e93  mov     rcx, [rcx+0D8h]
0x1800b4e9a  call    WPP_SF_qdDDS
0x1800b4e9f  cmp     dword ptr [rdi+54h], 0Fh
0x1800b4ea3  jnb     loc_1800B4FD9
0x1800b4ea9  mov     eax, [rdi+54h]
0x1800b4eac  mov     r8d, r14d; dwThreadId
0x1800b4eaf  mov     ecx, r14d
0x1800b4eb2  xor     edx, edx; bInheritHandle
0x1800b4eb4  mov     [rdi+rax*8+58h], rcx
0x1800b4eb9  mov     ecx, 800h; dwDesiredAccess
0x1800b4ebe  add     [rdi+54h], esi
0x1800b4ec1  mov     [rsp+630h+hMem], r15
0x1800b4ec6  call    cs:__imp_OpenThread
0x1800b4ecc  mov     rdx, rax
0x1800b4ecf  lea     rcx, [rsp+630h+hThread]
0x1800b4ed4  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x1800b4ed9  mov     rcx, [rsp+630h+hThread]; hThread
0x1800b4ede  test    rcx, rcx
0x1800b4ee1  jz      short loc_1800B4F0E
0x1800b4ee3  lea     rax, [rsp+630h+hMem]
0x1800b4ee8  mov     qword ptr [rsp+630h+dwThreadId+8], r15
0x1800b4eed  lea     rdx, [rsp+630h+dwThreadId+8]; ppszThreadDescription
0x1800b4ef2  mov     qword ptr [rsp+630h+dwThreadId], rax
0x1800b4ef7  mov     byte ptr [rsp+630h+var_5C8], sil
0x1800b4efc  mov     r15d, esi
0x1800b4eff  call    cs:__imp_GetThreadDescription
0x1800b4f05  test    eax, eax
0x1800b4f07  js      short loc_1800B4F0E
0x1800b4f09  mov     r12b, sil
0x1800b4f0c  jmp     short loc_1800B4F11
0x1800b4f0e  xor     r12b, r12b
0x1800b4f11  test    sil, r15b
0x1800b4f14  jz      short loc_1800B4F20
0x1800b4f16  lea     rcx, [rsp+630h+dwThreadId]
0x1800b4f1b  call    ??1?$out_param_t@V?$unique_ptr@$$BY0A@GU?$function_deleter@P6APEAXPEAX@Z$1?LocalFree@@YAPEAX0@Z@wil@@@wistd@@@details@wil@@QEAA@XZ; wil::details::out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>::~out_param_t<wistd::unique_ptr<ushort [0],wil::function_deleter<void * (*)(void *),&LocalFree(void *)>>>(void)
0x1800b4f20  test    r12b, r12b
0x1800b4f23  jz      loc_1800B4FC0
0x1800b4f29  cmp     cs:byte_18010EC4D, sil
0x1800b4f30  jb      short loc_1800B4F63
0x1800b4f32  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4f39  lea     r8, WPP_26f50317b41939831fb096d13f0bfc88_Traceguids
0x1800b4f40  mov     rax, [rsp+630h+hMem]
0x1800b4f45  mov     edx, 15h
0x1800b4f4a  mov     [rsp+630h+var_608], rax
0x1800b4f4f  mov     r9, rdi
0x1800b4f52  mov     [rsp+630h+var_610], r14d
0x1800b4f57  mov     rcx, [rcx+0D8h]
0x1800b4f5e  call    WPP_SF_qDS
0x1800b4f63  mov     rcx, [rsp+630h+hMem]
0x1800b4f68  lea     rdx, aMfdebucketizeK; "mfdebucketize_kssynchronouscontrol"
0x1800b4f6f  call    cs:__imp__o__wcsicmp
0x1800b4f75  test    r14d, r14d
0x1800b4f78  jz      short loc_1800B4FC0
0x1800b4f7a  test    eax, eax
0x1800b4f7c  jnz     short loc_1800B4FC0
0x1800b4f7e  cmp     cs:byte_18010EC4D, sil
0x1800b4f85  jb      short loc_1800B4FAC
0x1800b4f87  mov     rcx, cs:WPP_GLOBAL_Control
0x1800b4f8e  lea     edx, [rax+16h]
0x1800b4f91  mov     r9, rdi
0x1800b4f94  mov     [rsp+630h+var_610], r14d
0x1800b4f99  lea     r8, WPP_26f50317b41939831fb096d13f0bfc88_Traceguids
0x1800b4fa0  mov     rcx, [rcx+0D8h]
0x1800b4fa7  call    WPP_SF_qD
0x1800b4fac  call    cs:__imp_GetCurrentProcessId
0x1800b4fb2  mov     r9d, r14d; unsigned int
0x1800b4fb5  mov     rcx, rdi; this
0x1800b4fb8  mov     r8d, eax; unsigned int
0x1800b4fbb  call    ?GenerateKernelDump@FSSourceWatchdog@@IEAAJPEBGKK@Z; FSSourceWatchdog::GenerateKernelDump(ushort const *,ulong,ulong)
0x1800b4fc0  mov     rcx, [rsp+630h+hMem]; hMem
0x1800b4fc5  mov     [rsp+630h+hMem], 0
0x1800b4fce  test    rcx, rcx
0x1800b4fd1  jz      short loc_1800B4FD9
0x1800b4fd3  call    cs:__imp_LocalFree
0x1800b4fd9  mov     eax, [rdi+54h]
0x1800b4fdc  mov     [rbp+530h+pExceptionRecord.NumberParameters], eax
0x1800b4fdf  test    eax, eax
0x1800b4fe1  jz      short loc_1800B4FF7
0x1800b4fe3  mov     r8d, eax
0x1800b4fe6  lea     rdx, [rdi+58h]; Src
0x1800b4fea  shl     r8, 3; Size
0x1800b4fee  lea     rcx, [rbp+530h+pExceptionRecord.ExceptionInformation]; void *
0x1800b4ff2  call    memcpy_0
0x1800b4ff7  mov     r8d, ebx; dwFlags
0x1800b4ffa  lea     rcx, [rsp+630h+pExceptionRecord]; pExceptionRecord
0x1800b4fff  xor     edx, edx; pContextRecord
0x1800b5001  call    cs:__imp_RaiseFailFastException
0x1800b5007  lea     rcx, [rsp+630h+hThread]
0x1800b500c  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x1800b5011  lea     rcx, [rsp+630h+pvAddress]; void *
0x1800b5016  call    ??1?$com_ptr_t@UIFSSensorGroupTransform@@Uerr_returncode_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>::~com_ptr_t<IFSSensorGroupTransform,wil::err_returncode_policy>(void)
0x1800b501b  mov     rcx, [rbp+530h+var_50]
0x1800b5022  xor     rcx, rsp; StackCookie
0x1800b5025  call    __security_check_cookie
0x1800b502a  add     rsp, 5F8h
0x1800b5031  pop     r15
0x1800b5033  pop     r14
0x1800b5035  pop     r13
0x1800b5037  pop     r12
0x1800b5039  pop     rdi
0x1800b503a  pop     rsi
0x1800b503b  pop     rbx
0x1800b503c  pop     rbp
0x1800b503d  retn
```
