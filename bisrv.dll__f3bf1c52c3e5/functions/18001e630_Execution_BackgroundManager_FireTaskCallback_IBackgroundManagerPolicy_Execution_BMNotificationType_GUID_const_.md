# Execution::BackgroundManager::FireTaskCallback(IBackgroundManagerPolicy *,Execution::BMNotificationType,_GUID const *,_GUID const *,ushort const *)

- ea: `0x18001e630`
- end: `0x18001eac2`
- name: `?FireTaskCallback@BackgroundManager@Execution@@MEAAJPEAUIBackgroundManagerPolicy@@W4BMNotificationType@2@PEBU_GUID@@2PEBG@Z`
- size: `1170`
- prototype: ``
- caller_count: `0`
- callee_count: `14`
- tags: `file_ops, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18001a1f0`
- `0x18001d824`
- `0x18001e630`
- `0x18001eac8`
- `0x18001ef7c`
- `0x18001f0a0`
- `0x18001fa2c`
- `0x18001fb64`
- `0x18001fed0`
- `0x18006d938`
- `0x18006f9f4`
- `0x18006fec8`
- `0x18006ffbc`
- `0x180095010`

## import_xrefs

- `msvcrt!_wcsdup` at `0x18001e97c`
- `msvcrt!_wcsdup` at `0x18001e97c`
- `ntdll!RtlGetLastWin32Error` at `0x18001ea0c`
- `ntdll!RtlGetLastWin32Error` at `0x18001ea0c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e847`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001e847`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e8d0`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001e8d0`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001e72a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x18001e72a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x18001e740`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e8e2`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001e8e2`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e82b`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001e82b`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ea7f`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ea7f`

## string_xrefs

- `0x18001ea4c`: `onecoreuap\base\background\bi\backgroundmanager\lib\ThreadPool.h`

## pseudocode

```c
__int64 __fastcall Execution::BackgroundManager::FireTaskCallback(
        __int64 a1,
        __int64 a2,
        int a3,
        _OWORD *a4,
        _OWORD *a5,
        PCNZWCH sourceString)
{
  __int64 v9; // rsi
  _OWORD *v10; // r15
  const WCHAR *v11; // r12
  char *v12; // rbx
  __int64 v13; // rcx
  unsigned __int64 v14; // rdx
  __int128 v15; // xmm0
  HSTRING v16; // rcx
  __int64 v17; // r13
  __int64 (__fastcall ***v18)(_QWORD, GUID *, __int64 *); // rdi
  ThreadPoolData *v19; // rax
  __int64 *v20; // rsi
  __int64 v21; // rcx
  int v22; // eax
  signed int v23; // edi
  struct _TP_WORK *ThreadpoolWork; // r12
  char *v25; // rax
  _QWORD *v26; // rdx
  __int64 *v27; // rcx
  char *v28; // rax
  _QWORD *v29; // rax
  char v30; // di
  _OWORD *v31; // r14
  _OWORD *v32; // rsi
  wchar_t *v33; // rax
  wchar_t *v34; // r12
  void *v35; // rcx
  signed int LastWin32Error; // eax
  __int64 (__fastcall ***v38)(_QWORD, GUID *, __int64 *); // [rsp+20h] [rbp-58h] BYREF
  __int64 v39; // [rsp+28h] [rbp-50h] BYREF
  __int64 *v40; // [rsp+30h] [rbp-48h] BYREF
  char v41; // [rsp+38h] [rbp-40h] BYREF
  __int64 v42; // [rsp+40h] [rbp-38h]
  int v43; // [rsp+48h] [rbp-30h]
  _OWORD *v44; // [rsp+50h] [rbp-28h]
  _OWORD *v45; // [rsp+58h] [rbp-20h]
  wchar_t *v46; // [rsp+60h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+B8h] [rbp+40h]
  HSTRING string; // [rsp+C8h] [rbp+50h] BYREF
  int v50; // [rsp+D0h] [rbp+58h]
  _OWORD *v51; // [rsp+D8h] [rbp+60h]

  v51 = a4;
  v50 = a3;
  string = 0;
  v9 = a1;
  if ( !a2 || !a4 || (v10 = a5) == 0 || (v11 = sourceString) == 0 )
    return (unsigned int)-2147024809;
  v12 = (char *)operator new(0x38u, (const struct std::nothrow_t *)std::nothrow);
  if ( !v12 )
    return (unsigned int)-2147024882;
  *((_QWORD *)v12 + 5) = 0;
  *((_QWORD *)v12 + 6) = 0;
  tlx::auto_xxx<Execution::BM_NOTIFICATION *,void (*)(Execution::BM_NOTIFICATION *),&void tlx::_delete<Execution::BM_NOTIFICATION>(Execution::BM_NOTIFICATION *),0>::_Delete(&string);
  if ( *((_QWORD *)v12 + 6) != a2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)a2 + 8LL))(a2);
    v13 = *((_QWORD *)v12 + 6);
    *((_QWORD *)v12 + 6) = a2;
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
  *(_DWORD *)v12 = a3;
  v14 = -1;
  v15 = *a4;
  string = 0;
  *(_OWORD *)(v12 + 4) = v15;
  *(_OWORD *)(v12 + 20) = *v10;
  do
    ++v14;
  while ( v11[v14] );
  if ( v14 <= 0xFFFFFFFF && WindowsCreateString(v11, v14, &string) >= 0 )
  {
    v16 = (HSTRING)*((_QWORD *)v12 + 5);
    *((_QWORD *)v12 + 5) = string;
    WindowsDeleteString(v16);
  }
  v17 = *(_QWORD *)(v9 + 96);
  v18 = (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))(v9 + 64);
  v39 = v9 + 64;
  Microsoft::WRL::ComPtr<IThreadPoolCallback>::InternalAddRef(&v39);
  v19 = (ThreadPoolData *)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  string = (HSTRING)v19;
  if ( v19 )
  {
    v20 = (__int64 *)ThreadPoolData::ThreadPoolData(v19);
    v40 = v20;
    v38 = v18;
    string = 0;
    if ( v18 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v18)[1])(v18);
    v21 = v20[2];
    v20[2] = 0;
    if ( v21 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v21 + 16LL))(v21);
    v22 = Microsoft::WRL::AsWeak<IThreadPoolCallback>(v18, v20 + 2);
    v23 = v22;
    if ( v22 < 0 )
    {
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0x2D,
        (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\ThreadPool.h",
        (const char *)(unsigned int)v22,
        (int)v38);
    }
    else
    {
      v20[4] = (__int64)v12;
      v23 = 0;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v38);
    if ( v23 < 0 )
    {
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v40);
      Microsoft::WRL::Details::MakeAllocator<Execution::BackgroundManagerEventSettings>::~MakeAllocator<Execution::BackgroundManagerEventSettings>((void **)&string);
    }
    else
    {
      if ( v20 )
      {
        (*(void (__fastcall **)(__int64 *))(*v20 + 8))(v20);
        (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
      }
      ThreadpoolWork = CreateThreadpoolWork(ThreadPool::WorkerCallback, (PVOID)v17, (PTP_CALLBACK_ENVIRON)(v17 + 16));
      if ( ThreadpoolWork )
      {
        EnterCriticalSection((LPCRITICAL_SECTION)(v17 + 136));
        if ( v20 )
          (*(void (__fastcall **)(__int64 *))(*v20 + 8))(v20);
        v25 = (char *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        v26 = v25;
        v27 = v20;
        if ( v25 )
        {
          v28 = v25 + 16;
          *(_QWORD *)v28 = 0;
          if ( v28 != &v41 )
          {
            *(_QWORD *)v28 = v20;
            v27 = 0;
          }
          v29 = *(_QWORD **)(v17 + 120);
          v30 = 0;
          v26[1] = v29;
          *v26 = v17 + 112;
          *v29 = v26;
          *(_QWORD *)(v17 + 120) = v26;
          ++*(_QWORD *)(v17 + 128);
        }
        else
        {
          v30 = 1;
        }
        if ( v27 )
          (*(void (__fastcall **)(__int64 *))(*v27 + 16))(v27);
        LeaveCriticalSection((LPCRITICAL_SECTION)(v17 + 136));
        if ( v30 )
        {
          CloseThreadpoolWork(ThreadpoolWork);
          v23 = -2147024882;
        }
        else
        {
          SubmitThreadpoolWork(ThreadpoolWork);
          v23 = 0;
        }
      }
      else
      {
        LastWin32Error = RtlGetLastWin32Error();
        v23 = LastWin32Error;
        if ( LastWin32Error > 0 )
          v23 = (unsigned __int16)LastWin32Error | 0x80070000;
      }
      if ( v20 )
        (*(void (__fastcall **)(__int64 *))(*v20 + 16))(v20);
    }
    v11 = sourceString;
    v9 = a1;
  }
  else
  {
    Microsoft::WRL::Details::MakeAllocator<Execution::BackgroundManagerEventSettings>::~MakeAllocator<Execution::BackgroundManagerEventSettings>((void **)&string);
    v23 = -2147024882;
  }
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  if ( v23 >= 0 )
  {
    v12 = 0;
    if ( !*(_QWORD *)(v9 + 496) )
      return (unsigned int)v23;
    v31 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
    if ( v31 )
      *v31 = *v51;
    else
      v31 = 0;
    v32 = operator new(0x10u, (const struct std::nothrow_t *)std::nothrow);
    if ( v32 )
      *v32 = *a5;
    else
      v32 = 0;
    v33 = _wcsdup(v11);
    v34 = v33;
    if ( !v31 || !v32 || !v33 )
      return (unsigned int)-2147024882;
    v42 = a1;
    v43 = v50;
    v35 = *(void **)(a1 + 96);
    v44 = v31;
    v45 = v32;
    v46 = v33;
    v23 = ThreadPool::QueueLambda__lambda_a0be9a4f6282a9da04feb26e009edf1f___(v35);
    if ( v23 < 0 )
    {
      operator delete(v31);
      operator delete(v32);
      free_0(v34);
    }
  }
  if ( v12 )
    tlx::_delete<Execution::BM_NOTIFICATION>((Execution::BM_NOTIFICATION *)v12);
  return (unsigned int)v23;
}

```

## disassembly

```asm
0x18001e630  mov     [rsp-40h+arg_18], r9
0x18001e635  mov     [rsp-40h+arg_10], r8d
0x18001e63a  mov     [rsp-40h+arg_0], rcx
0x18001e63f  push    rbp
0x18001e640  push    rbx
0x18001e641  push    rsi
0x18001e642  push    rdi
0x18001e643  push    r12
0x18001e645  push    r13
0x18001e647  push    r14
0x18001e649  push    r15
0x18001e64b  mov     rbp, rsp
0x18001e64e  sub     rsp, 78h
0x18001e652  xor     eax, eax
0x18001e654  mov     r14, r9
0x18001e657  mov     [rbp+string], rax
0x18001e65b  mov     r13d, r8d
0x18001e65e  mov     rdi, rdx
0x18001e661  mov     rsi, rcx
0x18001e664  test    rdx, rdx
0x18001e667  jz      loc_18001E9F1
0x18001e66d  test    r9, r9
0x18001e670  jz      loc_18001E9F1
0x18001e676  mov     r15, [rbp+arg_20]
0x18001e67a  test    r15, r15
0x18001e67d  jz      loc_18001E9F1
0x18001e683  mov     r12, [rbp+sourceString]
0x18001e687  test    r12, r12
0x18001e68a  jz      loc_18001E9F1
0x18001e690  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e697  lea     ecx, [rax+38h]; unsigned __int64
0x18001e69a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e69f  mov     rbx, rax
0x18001e6a2  xor     eax, eax
0x18001e6a4  test    rbx, rbx
0x18001e6a7  jz      loc_18001E9F8
0x18001e6ad  mov     [rbx+28h], rax
0x18001e6b1  lea     rcx, [rbp+string]
0x18001e6b5  mov     [rbx+30h], rax
0x18001e6b9  call    ?_Delete@?$auto_xxx@PEAVBM_NOTIFICATION@Execution@@P6AXPEAV12@@Z$1??$_delete@VBM_NOTIFICATION@Execution@@@tlx@@YAX0@Z$0A@@tlx@@AEAAXXZ; tlx::auto_xxx<Execution::BM_NOTIFICATION *,void (*)(Execution::BM_NOTIFICATION *),&tlx::_delete<Execution::BM_NOTIFICATION>(Execution::BM_NOTIFICATION *),0>::_Delete(void)
0x18001e6be  cmp     [rbx+30h], rdi
0x18001e6c2  jz      loc_18001EA2D
0x18001e6c8  mov     rax, [rdi]
0x18001e6cb  mov     rcx, rdi
0x18001e6ce  mov     rax, [rax+8]
0x18001e6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6d7  mov     rcx, [rbx+30h]
0x18001e6db  mov     [rbx+30h], rdi
0x18001e6df  xor     edi, edi
0x18001e6e1  test    rcx, rcx
0x18001e6e4  jz      short loc_18001E6F2
0x18001e6e6  mov     rax, [rcx]
0x18001e6e9  mov     rax, [rax+10h]
0x18001e6ed  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e6f2  mov     [rbx], r13d
0x18001e6f5  or      rdx, 0FFFFFFFFFFFFFFFFh
0x18001e6f9  movups  xmm0, xmmword ptr [r14]
0x18001e6fd  mov     [rbp+string], rdi
0x18001e701  movdqu  xmmword ptr [rbx+4], xmm0
0x18001e706  movups  xmm1, xmmword ptr [r15]
0x18001e70a  movdqu  xmmword ptr [rbx+14h], xmm1
0x18001e70f  inc     rdx; length
0x18001e712  cmp     [r12+rdx*2], di
0x18001e717  jnz     short loc_18001E70F
0x18001e719  mov     eax, 0FFFFFFFFh
0x18001e71e  cmp     rdx, rax
0x18001e721  ja      short loc_18001E746
0x18001e723  lea     r8, [rbp+string]; string
0x18001e727  mov     rcx, r12; sourceString
0x18001e72a  call    cs:__imp_WindowsCreateString
0x18001e730  test    eax, eax
0x18001e732  js      short loc_18001E746
0x18001e734  mov     rax, [rbp+string]
0x18001e738  mov     rcx, [rbx+28h]; string
0x18001e73c  mov     [rbx+28h], rax
0x18001e740  call    cs:__imp_WindowsDeleteString
0x18001e746  mov     r13, [rsi+60h]
0x18001e74a  lea     rdi, [rsi+40h]
0x18001e74e  lea     rcx, [rbp+var_50]
0x18001e752  mov     [rbp+var_50], rdi
0x18001e756  mov     r14, rbx
0x18001e759  call    ?InternalAddRef@?$ComPtr@UIThreadPoolCallback@@@WRL@Microsoft@@IEBAXXZ; Microsoft::WRL::ComPtr<IThreadPoolCallback>::InternalAddRef(void)
0x18001e75e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e765  mov     ecx, 28h ; '('; unsigned __int64
0x18001e76a  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e76f  mov     [rbp+string], rax
0x18001e773  mov     r15d, 8007000Eh
0x18001e779  test    rax, rax
0x18001e77c  jz      loc_18001EA34
0x18001e782  mov     rcx, rax; this
0x18001e785  call    ??0ThreadPoolData@@QEAA@XZ; ThreadPoolData::ThreadPoolData(void)
0x18001e78a  mov     rsi, rax
0x18001e78d  mov     [rbp+var_48], rax
0x18001e791  xor     eax, eax
0x18001e793  mov     [rbp+var_58], rdi
0x18001e797  mov     [rbp+string], rax
0x18001e79b  test    rdi, rdi
0x18001e79e  jz      short loc_18001E7B1
0x18001e7a0  mov     rax, [rdi]
0x18001e7a3  mov     rcx, rdi
0x18001e7a6  mov     rax, [rax+8]
0x18001e7aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7af  xor     eax, eax
0x18001e7b1  lea     r12, [rsi+10h]
0x18001e7b5  mov     rcx, [r12]
0x18001e7b9  mov     [r12], rax
0x18001e7bd  test    rcx, rcx
0x18001e7c0  jz      short loc_18001E7CE
0x18001e7c2  mov     rax, [rcx]
0x18001e7c5  mov     rax, [rax+10h]
0x18001e7c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e7ce  mov     rdx, r12
0x18001e7d1  mov     rcx, rdi
0x18001e7d4  call    ??$AsWeak@UIThreadPoolCallback@@@WRL@Microsoft@@YAJPEAUIThreadPoolCallback@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IThreadPoolCallback>(IThreadPoolCallback *,Microsoft::WRL::WeakRef *)
0x18001e7d9  mov     edi, eax
0x18001e7db  test    eax, eax
0x18001e7dd  js      loc_18001EA48
0x18001e7e3  mov     [rsi+20h], r14
0x18001e7e7  xor     edi, edi
0x18001e7e9  lea     rcx, [rbp+var_58]
0x18001e7ed  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001e7f2  test    edi, edi
0x18001e7f4  js      loc_18001EA65
0x18001e7fa  test    rsi, rsi
0x18001e7fd  jz      short loc_18001E81D
0x18001e7ff  mov     rax, [rsi]
0x18001e802  mov     rcx, rsi
0x18001e805  mov     rax, [rax+8]
0x18001e809  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e80e  mov     rax, [rsi]
0x18001e811  mov     rcx, rsi
0x18001e814  mov     rax, [rax+10h]
0x18001e818  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e81d  lea     r8, [r13+10h]; pcbe
0x18001e821  mov     rdx, r13; pv
0x18001e824  lea     rcx, ?WorkerCallback@ThreadPool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001e82b  call    cs:__imp_CreateThreadpoolWork
0x18001e831  mov     r12, rax
0x18001e834  test    rax, rax
0x18001e837  jz      loc_18001EA0C
0x18001e83d  lea     r14, [r13+88h]
0x18001e844  mov     rcx, r14; lpCriticalSection
0x18001e847  call    cs:__imp_EnterCriticalSection
0x18001e84d  test    rsi, rsi
0x18001e850  jz      short loc_18001E861
0x18001e852  mov     rax, [rsi]
0x18001e855  mov     rcx, rsi
0x18001e858  mov     rax, [rax+8]
0x18001e85c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e861  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e868  mov     ecx, 18h; unsigned __int64
0x18001e86d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e872  mov     rdx, rax
0x18001e875  mov     rcx, rsi
0x18001e878  test    rax, rax
0x18001e87b  jz      loc_18001E9FF
0x18001e881  add     rax, 10h
0x18001e885  lea     r8, [r13+70h]
0x18001e889  xor     r13d, r13d
0x18001e88c  lea     r9, [rbp+var_40]
0x18001e890  mov     [rax], r13
0x18001e893  cmp     rax, r9
0x18001e896  jz      short loc_18001E89E
0x18001e898  mov     [rax], rsi
0x18001e89b  mov     ecx, r13d
0x18001e89e  mov     rax, [r8+8]
0x18001e8a2  mov     edi, 1
0x18001e8a7  mov     [rdx+8], rax
0x18001e8ab  mov     [rdx], r8
0x18001e8ae  mov     [rax], rdx
0x18001e8b1  mov     [r8+8], rdx
0x18001e8b5  add     [r8+10h], rdi
0x18001e8b9  mov     dil, r13b
0x18001e8bc  test    rcx, rcx
0x18001e8bf  jz      short loc_18001E8CD
0x18001e8c1  mov     rax, [rcx]
0x18001e8c4  mov     rax, [rax+10h]
0x18001e8c8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8cd  mov     rcx, r14; lpCriticalSection
0x18001e8d0  call    cs:__imp_LeaveCriticalSection
0x18001e8d6  mov     rcx, r12; pwk
0x18001e8d9  test    dil, dil
0x18001e8dc  jnz     loc_18001EA7F
0x18001e8e2  call    cs:__imp_SubmitThreadpoolWork
0x18001e8e8  mov     edi, r13d
0x18001e8eb  test    rsi, rsi
0x18001e8ee  jz      short loc_18001E8FF
0x18001e8f0  mov     rax, [rsi]
0x18001e8f3  mov     rcx, rsi
0x18001e8f6  mov     rax, [rax+10h]
0x18001e8fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001e8ff  mov     r12, [rbp+sourceString]
0x18001e903  mov     rsi, [rbp+arg_0]
0x18001e907  lea     rcx, [rbp+var_50]
0x18001e90b  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001e910  test    edi, edi
0x18001e912  js      loc_18001E9D1
0x18001e918  mov     rbx, r13
0x18001e91b  cmp     [rsi+1F0h], r13
0x18001e922  jz      loc_18001E9DE
0x18001e928  mov     edi, 10h
0x18001e92d  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e934  mov     ecx, edi; unsigned __int64
0x18001e936  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e93b  mov     r14, rax
0x18001e93e  test    rax, rax
0x18001e941  jz      loc_18001EA8D
0x18001e947  mov     rax, [rbp+arg_18]
0x18001e94b  movups  xmm0, xmmword ptr [rax]
0x18001e94e  movdqu  xmmword ptr [r14], xmm0
0x18001e953  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001e95a  mov     rcx, rdi; unsigned __int64
0x18001e95d  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001e962  mov     rsi, rax
0x18001e965  test    rax, rax
0x18001e968  jz      loc_18001EA95
0x18001e96e  mov     rax, [rbp+arg_20]
0x18001e972  movups  xmm0, xmmword ptr [rax]
0x18001e975  movdqu  xmmword ptr [rsi], xmm0
0x18001e979  mov     rcx, r12; String
0x18001e97c  call    cs:__imp__wcsdup
0x18001e982  mov     r12, rax
0x18001e985  test    r14, r14
0x18001e988  jz      loc_18001EA9D
0x18001e98e  test    rsi, rsi
0x18001e991  jz      loc_18001EA9D
0x18001e997  test    rax, rax
0x18001e99a  jz      loc_18001EA9D
0x18001e9a0  mov     rcx, [rbp+arg_0]
0x18001e9a4  lea     rdx, [rbp+var_38]
0x18001e9a8  mov     eax, [rbp+arg_10]
0x18001e9ab  mov     [rbp+var_38], rcx
0x18001e9af  mov     [rbp+var_30], eax
0x18001e9b2  mov     rcx, [rcx+60h]; pv
0x18001e9b6  mov     [rbp+var_28], r14
0x18001e9ba  mov     [rbp+var_20], rsi
0x18001e9be  mov     [rbp+var_18], r12
0x18001e9c2  call    ThreadPool__QueueLambda__lambda_a0be9a4f6282a9da04feb26e009edf1f___
0x18001e9c7  mov     edi, eax
0x18001e9c9  test    eax, eax
0x18001e9cb  js      loc_18001EAA5
0x18001e9d1  test    rbx, rbx
0x18001e9d4  jz      short loc_18001E9DE
0x18001e9d6  mov     rcx, rbx; Block
0x18001e9d9  call    ??$_delete@VBM_NOTIFICATION@Execution@@@tlx@@YAXPEAVBM_NOTIFICATION@Execution@@@Z; tlx::_delete<Execution::BM_NOTIFICATION>(Execution::BM_NOTIFICATION *)
0x18001e9de  mov     eax, edi
0x18001e9e0  add     rsp, 78h
0x18001e9e4  pop     r15
0x18001e9e6  pop     r14
0x18001e9e8  pop     r13
0x18001e9ea  pop     r12
0x18001e9ec  pop     rdi
0x18001e9ed  pop     rsi
0x18001e9ee  pop     rbx
0x18001e9ef  pop     rbp
0x18001e9f0  retn
0x18001e9f1  mov     edi, 80070057h
0x18001e9f6  jmp     short loc_18001E9DE
0x18001e9f8  mov     edi, 8007000Eh
0x18001e9fd  jmp     short loc_18001E9DE
0x18001e9ff  mov     edi, 1
0x18001ea04  xor     r13d, r13d
0x18001ea07  jmp     loc_18001E8BC
0x18001ea0c  call    cs:__imp_RtlGetLastWin32Error
0x18001ea12  xor     r13d, r13d
0x18001ea15  mov     edi, eax
0x18001ea17  test    eax, eax
0x18001ea19  jle     loc_18001E8EB
0x18001ea1f  movzx   edi, ax
0x18001ea22  or      edi, 80070000h
0x18001ea28  jmp     loc_18001E8EB
0x18001ea2d  xor     edi, edi
0x18001ea2f  jmp     loc_18001E6F2
0x18001ea34  lea     rcx, [rbp+string]
0x18001ea38  call    ??1?$MakeAllocator@VBackgroundManagerEventSettings@Execution@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Execution::BackgroundManagerEventSettings>::~MakeAllocator<Execution::BackgroundManagerEventSettings>(void)
0x18001ea3d  xor     r13d, r13d
0x18001ea40  mov     edi, r15d
0x18001ea43  jmp     loc_18001E907
0x18001ea48  mov     rcx, [rbp+40h]; this
0x18001ea4c  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\background\\bi\\backg"...
0x18001ea53  mov     r9d, eax; char *
0x18001ea56  mov     edx, 2Dh ; '-'; void *
0x18001ea5b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001ea60  jmp     loc_18001E7E9
0x18001ea65  lea     rcx, [rbp+var_48]
0x18001ea69  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001ea6e  lea     rcx, [rbp+string]
0x18001ea72  call    ??1?$MakeAllocator@VBackgroundManagerEventSettings@Execution@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Execution::BackgroundManagerEventSettings>::~MakeAllocator<Execution::BackgroundManagerEventSettings>(void)
0x18001ea77  xor     r13d, r13d
0x18001ea7a  jmp     loc_18001E8FF
0x18001ea7f  call    cs:__imp_CloseThreadpoolWork
0x18001ea85  mov     edi, r15d
0x18001ea88  jmp     loc_18001E8EB
0x18001ea8d  mov     r14, r13
0x18001ea90  jmp     loc_18001E953
0x18001ea95  mov     rsi, r13
0x18001ea98  jmp     loc_18001E979
0x18001ea9d  mov     edi, r15d
0x18001eaa0  jmp     loc_18001E9DE
0x18001eaa5  mov     rcx, r14; Block
  ... truncated ...
```
