# ThreadPool::QueueLambda__lambda_a0be9a4f6282a9da04feb26e009edf1f___

- ea: `0x18001eac8`
- end: `0x18001ed36`
- name: `ThreadPool::QueueLambda__lambda_a0be9a4f6282a9da04feb26e009edf1f___`
- size: `622`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001e630`

## callees

- `0x18001eac8`
- `0x18001ef7c`
- `0x18001f0a0`
- `0x18001f104`
- `0x18006d938`
- `0x18006fec8`
- `0x180095010`

## import_xrefs

- `ntdll!RtlGetLastWin32Error` at `0x18001ecfe`
- `ntdll!RtlGetLastWin32Error` at `0x18001ecfe`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ec0a`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001ec0a`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ec94`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001ec94`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001eca6`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001eca6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ebee`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001ebee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ed26`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001ed26`

## pseudocode

```c
__int64 __fastcall ThreadPool::QueueLambda__lambda_a0be9a4f6282a9da04feb26e009edf1f___(char *pv, __int64 a2)
{
  _QWORD *v4; // rax
  _QWORD *v5; // rbx
  void *v6; // rax
  ThreadPoolData *v7; // rdi
  __int64 v8; // rcx
  struct _TP_WORK *ThreadpoolWork; // r14
  struct _RTL_CRITICAL_SECTION *v10; // rbp
  char *v11; // rax
  _QWORD *v12; // rdx
  ThreadPoolData *v13; // rcx
  char *v14; // rax
  char *v15; // r8
  _QWORD *v16; // rax
  char v17; // si
  unsigned int v18; // esi
  signed int LastWin32Error; // eax
  char v21; // [rsp+20h] [rbp-28h] BYREF
  void *v22; // [rsp+60h] [rbp+18h] BYREF
  _QWORD *v23; // [rsp+68h] [rbp+20h] BYREF

  v4 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
  v5 = v4;
  if ( v4 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IThreadPoolCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IThreadPoolCallback>(v4);
    v23 = v5;
    *v5 = &off_1800961D8;
    v5[1] = off_180096040;
    *((_OWORD *)v5 + 2) = *(_OWORD *)a2;
    *((_OWORD *)v5 + 3) = *(_OWORD *)(a2 + 16);
    v5[8] = *(_QWORD *)(a2 + 32);
    ((void (__fastcall *)(_QWORD *))LambdaWorkCallback__lambda_e87c92a4a8f69b091aa83bb8bbb5f78f___::AddRef)(v5);
    v6 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
    v22 = v6;
    if ( v6 )
    {
      v7 = ThreadPoolData::ThreadPoolData((ThreadPoolData *)v6);
      v22 = v5;
      (*(void (__fastcall **)(_QWORD *))(*v5 + 8LL))(v5);
      if ( *((_QWORD **)v7 + 3) != v5 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v5 + 8LL))(v5);
        v8 = *((_QWORD *)v7 + 3);
        *((_QWORD *)v7 + 3) = v5;
        if ( v8 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
      }
      *((_QWORD *)v7 + 4) = 0;
      Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v22);
      (*(void (__fastcall **)(ThreadPoolData *))(*(_QWORD *)v7 + 8LL))(v7);
      (*(void (__fastcall **)(ThreadPoolData *))(*(_QWORD *)v7 + 16LL))(v7);
      ThreadpoolWork = CreateThreadpoolWork(ThreadPool::WorkerCallback, pv, (PTP_CALLBACK_ENVIRON)(pv + 16));
      if ( ThreadpoolWork )
      {
        v10 = (struct _RTL_CRITICAL_SECTION *)(pv + 136);
        EnterCriticalSection((LPCRITICAL_SECTION)(pv + 136));
        if ( v7 )
          (*(void (__fastcall **)(ThreadPoolData *))(*(_QWORD *)v7 + 8LL))(v7);
        v11 = (char *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
        v12 = v11;
        v13 = v7;
        if ( v11 )
        {
          v14 = v11 + 16;
          v15 = pv + 112;
          *(_QWORD *)v14 = 0;
          if ( v14 != &v21 )
          {
            *(_QWORD *)v14 = v7;
            v13 = 0;
          }
          v16 = (_QWORD *)*((_QWORD *)pv + 15);
          v17 = 0;
          v12[1] = v16;
          *v12 = v15;
          *v16 = v12;
          *((_QWORD *)v15 + 1) = v12;
          ++*((_QWORD *)v15 + 2);
        }
        else
        {
          v17 = 1;
        }
        if ( v13 )
          (*(void (__fastcall **)(ThreadPoolData *))(*(_QWORD *)v13 + 16LL))(v13);
        LeaveCriticalSection(v10);
        if ( v17 )
        {
          CloseThreadpoolWork(ThreadpoolWork);
          v18 = -2147024882;
        }
        else
        {
          SubmitThreadpoolWork(ThreadpoolWork);
          v18 = 0;
        }
      }
      else
      {
        LastWin32Error = RtlGetLastWin32Error();
        v18 = LastWin32Error;
        if ( LastWin32Error > 0 )
          v18 = (unsigned __int16)LastWin32Error | 0x80070000;
      }
      if ( v7 )
        (*(void (__fastcall **)(ThreadPoolData *))(*(_QWORD *)v7 + 16LL))(v7);
    }
    else
    {
      Microsoft::WRL::Details::MakeAllocator<Execution::BackgroundManagerEventSettings>::~MakeAllocator<Execution::BackgroundManagerEventSettings>(&v22);
      v18 = -2147024882;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v23);
    (*(void (__fastcall **)(_QWORD *))(*v5 + 16LL))(v5);
  }
  else
  {
    return (unsigned int)-2147024882;
  }
  return v18;
}

```

## disassembly

```asm
0x18001eac8  mov     [rsp+arg_0], rbx
0x18001eacd  mov     [rsp+arg_8], rbp
0x18001ead2  push    rsi
0x18001ead3  push    rdi
0x18001ead4  push    r14
0x18001ead6  sub     rsp, 30h
0x18001eada  mov     rdi, rdx
0x18001eadd  mov     rsi, rcx
0x18001eae0  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001eae7  mov     ecx, 48h ; 'H'; unsigned __int64
0x18001eaec  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001eaf1  mov     rbx, rax
0x18001eaf4  test    rax, rax
0x18001eaf7  jz      loc_18001ECF0
0x18001eafd  mov     rcx, rax
0x18001eb00  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIThreadPoolCallback@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IThreadPoolCallback>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IThreadPoolCallback>(void)
0x18001eb05  lea     rdx, off_1800961D8
0x18001eb0c  mov     [rsp+48h+arg_18], rbx
0x18001eb11  mov     [rbx], rdx
0x18001eb14  lea     rax, off_180096040
0x18001eb1b  mov     [rbx+8], rax
0x18001eb1f  mov     rcx, rbx
0x18001eb22  movups  xmm0, xmmword ptr [rdi]
0x18001eb25  mov     rax, [rdx+8]
0x18001eb29  movups  xmmword ptr [rbx+20h], xmm0
0x18001eb2d  movups  xmm1, xmmword ptr [rdi+10h]
0x18001eb31  movups  xmmword ptr [rbx+30h], xmm1
0x18001eb35  movsd   xmm0, qword ptr [rdi+20h]
0x18001eb3a  movsd   qword ptr [rbx+40h], xmm0
0x18001eb3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb44  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001eb4b  mov     ecx, 28h ; '('; unsigned __int64
0x18001eb50  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001eb55  mov     [rsp+48h+arg_10], rax
0x18001eb5a  test    rax, rax
0x18001eb5d  jz      loc_18001ED15
0x18001eb63  mov     rcx, rax; this
0x18001eb66  call    ??0ThreadPoolData@@QEAA@XZ; ThreadPoolData::ThreadPoolData(void)
0x18001eb6b  mov     rdi, rax
0x18001eb6e  mov     [rsp+48h+arg_10], rbx
0x18001eb73  mov     rax, [rbx]
0x18001eb76  mov     rcx, rbx
0x18001eb79  mov     rax, [rax+8]
0x18001eb7d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb82  cmp     [rdi+18h], rbx
0x18001eb86  jz      short loc_18001EBB0
0x18001eb88  mov     rax, [rbx]
0x18001eb8b  mov     rcx, rbx
0x18001eb8e  mov     rax, [rax+8]
0x18001eb92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001eb97  mov     rcx, [rdi+18h]
0x18001eb9b  mov     [rdi+18h], rbx
0x18001eb9f  test    rcx, rcx
0x18001eba2  jz      short loc_18001EBB0
0x18001eba4  mov     rax, [rcx]
0x18001eba7  mov     rax, [rax+10h]
0x18001ebab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebb0  lea     rcx, [rsp+48h+arg_10]
0x18001ebb5  mov     qword ptr [rdi+20h], 0
0x18001ebbd  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001ebc2  mov     rax, [rdi]
0x18001ebc5  mov     rcx, rdi
0x18001ebc8  mov     rax, [rax+8]
0x18001ebcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebd1  mov     rax, [rdi]
0x18001ebd4  mov     rcx, rdi
0x18001ebd7  mov     rax, [rax+10h]
0x18001ebdb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ebe0  lea     r8, [rsi+10h]; pcbe
0x18001ebe4  mov     rdx, rsi; pv
0x18001ebe7  lea     rcx, ?WorkerCallback@ThreadPool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001ebee  call    cs:__imp_CreateThreadpoolWork
0x18001ebf4  mov     r14, rax
0x18001ebf7  test    rax, rax
0x18001ebfa  jz      loc_18001ECFE
0x18001ec00  lea     rbp, [rsi+88h]
0x18001ec07  mov     rcx, rbp; lpCriticalSection
0x18001ec0a  call    cs:__imp_EnterCriticalSection
0x18001ec10  test    rdi, rdi
0x18001ec13  jz      short loc_18001EC24
0x18001ec15  mov     rax, [rdi]
0x18001ec18  mov     rcx, rdi
0x18001ec1b  mov     rax, [rax+8]
0x18001ec1f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec24  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001ec2b  mov     ecx, 18h; unsigned __int64
0x18001ec30  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001ec35  mov     rdx, rax
0x18001ec38  mov     rcx, rdi
0x18001ec3b  test    rax, rax
0x18001ec3e  jz      loc_18001ECF7
0x18001ec44  add     rax, 10h
0x18001ec48  lea     r9, [rsp+48h+var_28]
0x18001ec4d  lea     r8, [rsi+70h]
0x18001ec51  mov     qword ptr [rax], 0
0x18001ec58  cmp     rax, r9
0x18001ec5b  jz      short loc_18001EC62
0x18001ec5d  mov     [rax], rdi
0x18001ec60  xor     ecx, ecx
0x18001ec62  mov     rax, [r8+8]
0x18001ec66  mov     esi, 1
0x18001ec6b  mov     [rdx+8], rax
0x18001ec6f  mov     [rdx], r8
0x18001ec72  mov     [rax], rdx
0x18001ec75  mov     [r8+8], rdx
0x18001ec79  add     [r8+10h], rsi
0x18001ec7d  xor     sil, sil
0x18001ec80  test    rcx, rcx
0x18001ec83  jz      short loc_18001EC91
0x18001ec85  mov     rax, [rcx]
0x18001ec88  mov     rax, [rax+10h]
0x18001ec8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ec91  mov     rcx, rbp; lpCriticalSection
0x18001ec94  call    cs:__imp_LeaveCriticalSection
0x18001ec9a  mov     rcx, r14; pwk
0x18001ec9d  test    sil, sil
0x18001eca0  jnz     loc_18001ED26
0x18001eca6  call    cs:__imp_SubmitThreadpoolWork
0x18001ecac  xor     esi, esi
0x18001ecae  test    rdi, rdi
0x18001ecb1  jz      short loc_18001ECC2
0x18001ecb3  mov     rax, [rdi]
0x18001ecb6  mov     rcx, rdi
0x18001ecb9  mov     rax, [rax+10h]
0x18001ecbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecc2  lea     rcx, [rsp+48h+arg_18]
0x18001ecc7  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001eccc  mov     rax, [rbx]
0x18001eccf  mov     rcx, rbx
0x18001ecd2  mov     rax, [rax+10h]
0x18001ecd6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001ecdb  mov     rbx, [rsp+48h+arg_0]
0x18001ece0  mov     eax, esi
0x18001ece2  mov     rbp, [rsp+48h+arg_8]
0x18001ece7  add     rsp, 30h
0x18001eceb  pop     r14
0x18001eced  pop     rdi
0x18001ecee  pop     rsi
0x18001ecef  retn
0x18001ecf0  mov     esi, 8007000Eh
0x18001ecf5  jmp     short loc_18001ECDB
0x18001ecf7  mov     esi, 1
0x18001ecfc  jmp     short loc_18001EC80
0x18001ecfe  call    cs:__imp_RtlGetLastWin32Error
0x18001ed04  mov     esi, eax
0x18001ed06  test    eax, eax
0x18001ed08  jle     short loc_18001ECAE
0x18001ed0a  movzx   esi, ax
0x18001ed0d  or      esi, 80070000h
0x18001ed13  jmp     short loc_18001ECAE
0x18001ed15  lea     rcx, [rsp+48h+arg_10]
0x18001ed1a  call    ??1?$MakeAllocator@VBackgroundManagerEventSettings@Execution@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::MakeAllocator<Execution::BackgroundManagerEventSettings>::~MakeAllocator<Execution::BackgroundManagerEventSettings>(void)
0x18001ed1f  mov     esi, 8007000Eh
0x18001ed24  jmp     short loc_18001ECC2
0x18001ed26  call    cs:__imp_CloseThreadpoolWork
0x18001ed2c  mov     esi, 8007000Eh
0x18001ed31  jmp     loc_18001ECAE
```
