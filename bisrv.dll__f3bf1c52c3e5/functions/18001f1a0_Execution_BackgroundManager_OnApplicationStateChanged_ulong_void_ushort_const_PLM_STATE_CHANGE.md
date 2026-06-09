# Execution::BackgroundManager::OnApplicationStateChanged(ulong,void *,ushort const *,PLM_STATE_CHANGE)

- ea: `0x18001f1a0`
- end: `0x18001f708`
- name: `?OnApplicationStateChanged@BackgroundManager@Execution@@UEAAJKPEAXPEBGW4PLM_STATE_CHANGE@@@Z`
- size: `1384`
- prototype: `int __high(unsigned int, void *, const unsigned __int16 *, enum PLM_STATE_CHANGE)`
- caller_count: `0`
- callee_count: `8`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x18001ef7c`
- `0x18001f150`
- `0x18001f1a0`
- `0x18001f710`
- `0x18001fa18`
- `0x18006fec8`
- `0x18006ffbc`
- `0x180095010`

## import_xrefs

- `msvcrt!_wcsdup` at `0x18001f29f`
- `msvcrt!_wcsdup` at `0x18001f29f`
- `ntdll!RtlGetLastWin32Error` at `0x18001f680`
- `ntdll!RtlGetLastWin32Error` at `0x18001f680`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f272`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4c1`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f272`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f4c1`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f6e3`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f553`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f613`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f6e3`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001f55e`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001f55e`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001f4a6`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001f4a6`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f6ee`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001f6ee`

## pseudocode

```c
__int64 __fastcall Execution::BackgroundManager::OnApplicationStateChanged(
        __int64 a1,
        int a2,
        void *a3,
        const wchar_t *a4,
        int a5)
{
  __int64 v5; // rbp
  const wchar_t *v7; // r15
  Execution::Sid *v8; // r12
  Execution::Sid *v9; // rax
  Execution::Sid *v10; // rbx
  int v11; // r13d
  struct _RTL_CRITICAL_SECTION *v12; // rdi
  Execution::Sid *v13; // rax
  Execution::Sid *v14; // r14
  Execution::Sid *v15; // rsi
  Execution::Sid *v16; // rcx
  __int64 v17; // rbx
  __int64 v18; // rsi
  __int64 v19; // r13
  __int64 v20; // rbp
  Execution::Sid *v21; // r15
  _QWORD *v22; // rax
  _QWORD *v23; // rsi
  _QWORD *v24; // rcx
  _QWORD *v25; // rax
  _QWORD *v26; // r14
  _QWORD *v27; // rcx
  __int64 v28; // rcx
  char *v29; // rax
  _QWORD *v30; // rdx
  _QWORD *v31; // rcx
  char *v32; // rax
  __int64 v33; // r8
  _QWORD *v34; // rax
  char v35; // r13
  struct _RTL_CRITICAL_SECTION *v36; // rcx
  signed int LastWin32Error; // eax
  Execution::Sid *v39; // [rsp+20h] [rbp-98h] BYREF
  __int64 v40; // [rsp+28h] [rbp-90h]
  PTP_WORK pwk; // [rsp+30h] [rbp-88h]
  void *Block; // [rsp+38h] [rbp-80h]
  Execution::Sid *v43; // [rsp+40h] [rbp-78h]
  char v44; // [rsp+48h] [rbp-70h] BYREF
  char v45; // [rsp+50h] [rbp-68h] BYREF
  char v46; // [rsp+58h] [rbp-60h] BYREF

  v5 = a1;
  v7 = a4;
  v39 = 0;
  Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  v8 = 0;
  v9 = (Execution::Sid *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
  v10 = v9;
  if ( v9 )
  {
    Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>(v9);
    *((_QWORD *)v10 + 2) = 0;
    *(_QWORD *)v10 = &Execution::Sid::`vftable';
    v39 = v10;
    v11 = Execution::Sid::RuntimeClassInitialize(v10, a3);
    if ( v11 >= 0 )
    {
      (*(void (__fastcall **)(Execution::Sid *))(*(_QWORD *)v10 + 8LL))(v10);
      v8 = v10;
      (*(void (__fastcall **)(Execution::Sid *))(*(_QWORD *)v10 + 16LL))(v10);
      v12 = (struct _RTL_CRITICAL_SECTION *)(v5 + 192);
      EnterCriticalSection((LPCRITICAL_SECTION)(v5 + 192));
      v13 = (Execution::Sid *)(v5 + 176);
      v11 = 0;
      v14 = *(Execution::Sid **)(v5 + 176);
      v39 = (Execution::Sid *)(v5 + 176);
      while ( 1 )
      {
        if ( v14 == v13 )
        {
LABEL_45:
          LeaveCriticalSection(v12);
          goto LABEL_46;
        }
        v15 = *(Execution::Sid **)v14;
        Block = _wcsdup(v7);
        if ( !Block )
        {
          v11 = -2147024882;
          goto LABEL_45;
        }
        v16 = v14;
        v43 = v15;
        v14 = v15;
        v17 = 0;
        v18 = *((_QWORD *)v16 + 2);
        if ( v18 )
        {
          (*(void (__fastcall **)(_QWORD))(*(_QWORD *)v18 + 8LL))(*((_QWORD *)v16 + 2));
          v17 = v18;
        }
        v19 = *(_QWORD *)(v5 + 24);
        v20 = v17;
        v40 = v19;
        if ( v17 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 8LL))(v17);
        v21 = v8;
        if ( v8 )
          (*(void (__fastcall **)(Execution::Sid *))(*(_QWORD *)v8 + 8LL))(v8);
        v22 = operator new(0x48u, (const struct std::nothrow_t *)std::nothrow);
        v23 = v22;
        if ( v22 )
          break;
        v11 = -2147024882;
LABEL_35:
        if ( v21 )
          (*(void (__fastcall **)(Execution::Sid *))(*(_QWORD *)v21 + 16LL))(v21);
        if ( v20 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v20 + 16LL))(v20);
        if ( v11 < 0 )
          free_0(Block);
        v13 = v39;
        v5 = a1;
        v7 = a4;
        if ( v17 )
        {
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v17 + 16LL))(v17);
          v13 = v39;
        }
      }
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Execution::IBackgroundManagerSessionFactory>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Execution::IBackgroundManagerSessionFactory>(v22);
      *v24 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IThreadPoolCallback>::`vftable'{for `IThreadPoolCallback'};
      v24[1] = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IThreadPoolCallback>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'};
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *v23 = &off_180096138;
      v23[1] = off_1800960D8;
      v23[4] = 0;
      if ( v23 + 4 != (_QWORD *)&v45 )
      {
        v23[4] = v17;
        v20 = 0;
      }
      v23[5] = 0;
      if ( v23 + 5 != (_QWORD *)&v46 )
      {
        v23[5] = v8;
        v21 = 0;
      }
      *((_DWORD *)v23 + 12) = a2;
      v23[7] = Block;
      *((_DWORD *)v23 + 16) = a5;
      (*(void (__fastcall **)(_QWORD *))(*v23 + 8LL))(v23);
      v25 = operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
      v26 = v25;
      if ( !v25 )
      {
        v11 = -2147024882;
        goto LABEL_34;
      }
      Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>(v25);
      *v27 = &Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable';
      if ( Microsoft::WRL::Details::ModuleBase::module_ )
        (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                             + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
      *v26 = &ThreadPoolData::`vftable';
      v26[2] = 0;
      v26[3] = 0;
      v26[4] = 0;
      (*(void (__fastcall **)(_QWORD *))(*v23 + 8LL))(v23);
      if ( (_QWORD *)v26[3] != v23 )
      {
        (*(void (__fastcall **)(_QWORD *))(*v23 + 8LL))(v23);
        v28 = v26[3];
        v26[3] = v23;
        if ( v28 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v28 + 16LL))(v28);
      }
      v26[4] = 0;
      (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
      (*(void (__fastcall **)(_QWORD *))(*v26 + 8LL))(v26);
      (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
      pwk = CreateThreadpoolWork(ThreadPool::WorkerCallback, (PVOID)v19, (PTP_CALLBACK_ENVIRON)(v19 + 16));
      if ( !pwk )
      {
        LastWin32Error = RtlGetLastWin32Error();
        v11 = LastWin32Error;
        if ( LastWin32Error > 0 )
          v11 = (unsigned __int16)LastWin32Error | 0x80070000;
        goto LABEL_33;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(v19 + 136));
      (*(void (__fastcall **)(_QWORD *))(*v26 + 8LL))(v26);
      v29 = (char *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
      v30 = v29;
      v31 = v26;
      if ( v29 )
      {
        v32 = v29 + 16;
        v33 = v19 + 112;
        *(_QWORD *)v32 = 0;
        if ( v32 != &v44 )
        {
          *(_QWORD *)v32 = v26;
          v31 = 0;
        }
        v34 = *(_QWORD **)(v19 + 120);
        v35 = 0;
        v30[1] = v34;
        *v30 = v33;
        *v34 = v30;
        *(_QWORD *)(v33 + 8) = v30;
        ++*(_QWORD *)(v33 + 16);
        if ( !v31 )
          goto LABEL_31;
      }
      else
      {
        v35 = 1;
      }
      (*(void (__fastcall **)(_QWORD *))(*v31 + 16LL))(v31);
LABEL_31:
      v36 = (struct _RTL_CRITICAL_SECTION *)(v40 + 136);
      if ( v35 )
      {
        v11 = -2147024882;
        LeaveCriticalSection(v36);
        CloseThreadpoolWork(pwk);
      }
      else
      {
        LeaveCriticalSection(v36);
        SubmitThreadpoolWork(pwk);
        v11 = 0;
      }
LABEL_33:
      (*(void (__fastcall **)(_QWORD *))(*v26 + 16LL))(v26);
LABEL_34:
      (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
      (*(void (__fastcall **)(_QWORD *))(*v23 + 16LL))(v23);
      v14 = v43;
      goto LABEL_35;
    }
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v39);
  }
  else
  {
    v11 = -2147024882;
  }
LABEL_46:
  if ( v8 )
    (*(void (__fastcall **)(Execution::Sid *))(*(_QWORD *)v8 + 16LL))(v8);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x18001f1a0  mov     rax, rsp
0x18001f1a3  mov     [rax+20h], r9
0x18001f1a7  mov     [rax+10h], edx
0x18001f1aa  mov     [rax+8], rcx
0x18001f1ae  push    r12
0x18001f1b0  push    r13
0x18001f1b2  sub     rsp, 0A8h
0x18001f1b9  mov     [rax+18h], rbx
0x18001f1bd  mov     [rax-18h], rbp
0x18001f1c1  mov     rbp, rcx
0x18001f1c4  mov     [rax-20h], rsi
0x18001f1c8  lea     rcx, [rsp+0B8h+var_98]
0x18001f1cd  mov     [rax-28h], rdi
0x18001f1d1  xor     esi, esi
0x18001f1d3  mov     [rax-38h], r15
0x18001f1d7  mov     rdi, r8
0x18001f1da  mov     r15, r9
0x18001f1dd  mov     [rsp+0B8h+var_98], rsi
0x18001f1e2  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f1e7  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f1ee  mov     ecx, 18h; unsigned __int64
0x18001f1f3  mov     r12d, esi
0x18001f1f6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f1fb  mov     rbx, rax
0x18001f1fe  test    rax, rax
0x18001f201  jz      loc_18001F66D
0x18001f207  mov     rcx, rax
0x18001f20a  call    ??0?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>(void)
0x18001f20f  lea     rax, ??_7Sid@Execution@@6B@; const Execution::Sid::`vftable'
0x18001f216  mov     [rbx+10h], rsi
0x18001f21a  mov     [rbx], rax
0x18001f21d  mov     rdx, rdi
0x18001f220  mov     rax, cs:off_1800960D0
0x18001f227  mov     rcx, rbx
0x18001f22a  mov     [rsp+0B8h+var_98], rbx
0x18001f22f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f234  mov     r13d, eax
0x18001f237  test    eax, eax
0x18001f239  js      loc_18001F6A1
0x18001f23f  mov     rax, [rbx]
0x18001f242  mov     rcx, rbx
0x18001f245  mov     [rsp+0B8h+var_30], r14
0x18001f24d  mov     rax, [rax+8]
0x18001f251  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f256  mov     rax, [rbx]
0x18001f259  mov     rcx, rbx
0x18001f25c  mov     r12, rbx
0x18001f25f  mov     rax, [rax+10h]
0x18001f263  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f268  lea     rdi, [rbp+0C0h]
0x18001f26f  mov     rcx, rdi; lpCriticalSection
0x18001f272  call    cs:__imp_EnterCriticalSection
0x18001f278  lea     rax, [rbp+0B0h]
0x18001f27f  mov     r13d, esi
0x18001f282  mov     r14, [rax]
0x18001f285  mov     [rsp+0B8h+var_98], rax
0x18001f28a  nop     word ptr [rax+rax+00h]
0x18001f290  cmp     r14, rax
0x18001f293  jz      loc_18001F610
0x18001f299  mov     rsi, [r14]
0x18001f29c  mov     rcx, r15; String
0x18001f29f  call    cs:__imp__wcsdup
0x18001f2a5  mov     [rsp+0B8h+Block], rax
0x18001f2aa  test    rax, rax
0x18001f2ad  jz      loc_18001F60A
0x18001f2b3  mov     rcx, r14
0x18001f2b6  mov     [rsp+0B8h+var_78], rsi
0x18001f2bb  mov     r14, rsi
0x18001f2be  xor     ebx, ebx
0x18001f2c0  mov     rsi, [rcx+10h]
0x18001f2c4  test    rsi, rsi
0x18001f2c7  jz      short loc_18001F2DB
0x18001f2c9  mov     rcx, [rsi]
0x18001f2cc  mov     rax, [rcx+8]
0x18001f2d0  mov     rcx, rsi
0x18001f2d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2d8  mov     rbx, rsi
0x18001f2db  mov     r13, [rbp+18h]
0x18001f2df  mov     rbp, rbx
0x18001f2e2  mov     [rsp+0B8h+var_90], r13
0x18001f2e7  test    rbx, rbx
0x18001f2ea  jz      short loc_18001F2FB
0x18001f2ec  mov     rax, [rbx]
0x18001f2ef  mov     rcx, rbx
0x18001f2f2  mov     rax, [rax+8]
0x18001f2f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f2fb  mov     r15, r12
0x18001f2fe  test    r12, r12
0x18001f301  jz      short loc_18001F313
0x18001f303  mov     rax, [r12]
0x18001f307  mov     rcx, r12
0x18001f30a  mov     rax, [rax+8]
0x18001f30e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f313  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f31a  mov     ecx, 48h ; 'H'; unsigned __int64
0x18001f31f  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f324  mov     rsi, rax
0x18001f327  test    rax, rax
0x18001f32a  jz      loc_18001F675
0x18001f330  mov     rcx, rax
0x18001f333  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIBackgroundManagerSessionFactory@Execution@@@Details@WRL@Microsoft@@QEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Execution::IBackgroundManagerSessionFactory>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Execution::IBackgroundManagerSessionFactory>(void)
0x18001f338  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIThreadPoolCallback@@@WRL@Microsoft@@6BIThreadPoolCallback@@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IThreadPoolCallback>::`vftable'{for `IThreadPoolCallback'}
0x18001f33f  mov     [rcx], rax
0x18001f342  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIThreadPoolCallback@@@WRL@Microsoft@@6B?$ImplementsHelper@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00UIWeakReferenceSource@@@Details@12@@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<3>,IThreadPoolCallback>::`vftable'{for `Microsoft::WRL::Details::ImplementsHelper<Microsoft::WRL::RuntimeClassFlags<3>,1,IWeakReferenceSource>'}
0x18001f349  mov     [rcx+8], rax
0x18001f34d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001f354  test    rcx, rcx
0x18001f357  jnz     loc_18001F6B0
0x18001f35d  lea     rax, off_180096138
0x18001f364  xor     r8d, r8d
0x18001f367  mov     [rsi], rax
0x18001f36a  lea     rcx, [rsp+0B8h+var_68]
0x18001f36f  lea     rax, off_1800960D8
0x18001f376  mov     [rsi+8], rax
0x18001f37a  lea     rax, [rsi+20h]
0x18001f37e  mov     [rax], r8
0x18001f381  cmp     rax, rcx
0x18001f384  jz      short loc_18001F38C
0x18001f386  mov     [rax], rbx
0x18001f389  mov     ebp, r8d
0x18001f38c  lea     rcx, [rax+8]
0x18001f390  lea     rdx, [rsp+0B8h+var_60]
0x18001f395  mov     [rcx], r8
0x18001f398  cmp     rcx, rdx
0x18001f39b  jz      short loc_18001F3A3
0x18001f39d  mov     [rcx], r12
0x18001f3a0  mov     r15, r8
0x18001f3a3  mov     ecx, [rsp+0B8h+arg_8]
0x18001f3aa  mov     [rax+10h], ecx
0x18001f3ad  mov     rcx, [rsp+0B8h+Block]
0x18001f3b2  mov     [rax+18h], rcx
0x18001f3b6  mov     ecx, [rsp+0B8h+arg_20]
0x18001f3bd  mov     [rax+20h], ecx
0x18001f3c0  mov     rcx, rsi
0x18001f3c3  mov     rax, [rsi]
0x18001f3c6  mov     rax, [rax+8]
0x18001f3ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f3cf  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f3d6  mov     ecx, 28h ; '('; unsigned __int64
0x18001f3db  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f3e0  mov     r14, rax
0x18001f3e3  test    rax, rax
0x18001f3e6  jz      loc_18001F6C1
0x18001f3ec  mov     rcx, rax
0x18001f3ef  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>(void)
0x18001f3f4  lea     rax, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x18001f3fb  mov     [rcx], rax
0x18001f3fe  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001f405  test    rcx, rcx
0x18001f408  jnz     loc_18001F6CC
0x18001f40e  lea     rax, ??_7ThreadPoolData@@6B@; const ThreadPoolData::`vftable'
0x18001f415  mov     rcx, rsi
0x18001f418  mov     [r14], rax
0x18001f41b  xor     eax, eax
0x18001f41d  mov     [r14+10h], rax
0x18001f421  mov     [r14+18h], rax
0x18001f425  mov     [r14+20h], rax
0x18001f429  mov     rax, [rsi]
0x18001f42c  mov     rax, [rax+8]
0x18001f430  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f435  cmp     [r14+18h], rsi
0x18001f439  jz      short loc_18001F463
0x18001f43b  mov     rax, [rsi]
0x18001f43e  mov     rcx, rsi
0x18001f441  mov     rax, [rax+8]
0x18001f445  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f44a  mov     rcx, [r14+18h]
0x18001f44e  mov     [r14+18h], rsi
0x18001f452  test    rcx, rcx
0x18001f455  jz      short loc_18001F463
0x18001f457  mov     rax, [rcx]
0x18001f45a  mov     rax, [rax+10h]
0x18001f45e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f463  mov     qword ptr [r14+20h], 0
0x18001f46b  mov     rcx, rsi
0x18001f46e  mov     rax, [rsi]
0x18001f471  mov     rax, [rax+10h]
0x18001f475  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f47a  mov     rax, [r14]
0x18001f47d  mov     rcx, r14
0x18001f480  mov     rax, [rax+8]
0x18001f484  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f489  mov     rax, [r14]
0x18001f48c  mov     rcx, r14
0x18001f48f  mov     rax, [rax+10h]
0x18001f493  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f498  lea     r8, [r13+10h]; pcbe
0x18001f49c  mov     rdx, r13; pv
0x18001f49f  lea     rcx, ?WorkerCallback@ThreadPool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001f4a6  call    cs:__imp_CreateThreadpoolWork
0x18001f4ac  mov     [rsp+0B8h+pwk], rax
0x18001f4b1  test    rax, rax
0x18001f4b4  jz      loc_18001F680
0x18001f4ba  lea     rcx, [r13+88h]; lpCriticalSection
0x18001f4c1  call    cs:__imp_EnterCriticalSection
0x18001f4c7  mov     rax, [r14]
0x18001f4ca  mov     rcx, r14
0x18001f4cd  mov     rax, [rax+8]
0x18001f4d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f4d6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f4dd  mov     ecx, 18h; unsigned __int64
0x18001f4e2  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f4e7  mov     rdx, rax
0x18001f4ea  mov     rcx, r14
0x18001f4ed  test    rax, rax
0x18001f4f0  jz      loc_18001F602
0x18001f4f6  add     rax, 10h
0x18001f4fa  lea     r9, [rsp+0B8h+var_70]
0x18001f4ff  lea     r8, [r13+70h]
0x18001f503  mov     qword ptr [rax], 0
0x18001f50a  cmp     rax, r9
0x18001f50d  jz      short loc_18001F514
0x18001f50f  mov     [rax], r14
0x18001f512  xor     ecx, ecx
0x18001f514  mov     rax, [r8+8]
0x18001f518  xor     r13b, r13b
0x18001f51b  mov     [rdx+8], rax
0x18001f51f  mov     [rdx], r8
0x18001f522  mov     [rax], rdx
0x18001f525  mov     [r8+8], rdx
0x18001f529  inc     qword ptr [r8+10h]
0x18001f52d  test    rcx, rcx
0x18001f530  jz      short loc_18001F53E
0x18001f532  mov     rax, [rcx]
0x18001f535  mov     rax, [rax+10h]
0x18001f539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f53e  mov     rcx, [rsp+0B8h+var_90]
0x18001f543  add     rcx, 88h; lpCriticalSection
0x18001f54a  test    r13b, r13b
0x18001f54d  jnz     loc_18001F6DD
0x18001f553  call    cs:__imp_LeaveCriticalSection
0x18001f559  mov     rcx, [rsp+0B8h+pwk]; pwk
0x18001f55e  call    cs:__imp_SubmitThreadpoolWork
0x18001f564  xor     r13d, r13d
0x18001f567  mov     rax, [r14]
0x18001f56a  mov     rcx, r14
0x18001f56d  mov     rax, [rax+10h]
0x18001f571  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f576  mov     rax, [rsi]
0x18001f579  mov     rcx, rsi
0x18001f57c  mov     rax, [rax+10h]
0x18001f580  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f585  mov     rax, [rsi]
0x18001f588  mov     rcx, rsi
0x18001f58b  mov     rax, [rax+10h]
0x18001f58f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f594  mov     r14, [rsp+0B8h+var_78]
0x18001f599  test    r15, r15
0x18001f59c  jz      short loc_18001F5AD
0x18001f59e  mov     rax, [r15]
0x18001f5a1  mov     rcx, r15
0x18001f5a4  mov     rax, [rax+10h]
0x18001f5a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5ad  test    rbp, rbp
0x18001f5b0  jz      short loc_18001F5C2
0x18001f5b2  mov     rax, [rbp+0]
0x18001f5b6  mov     rcx, rbp
0x18001f5b9  mov     rax, [rax+10h]
0x18001f5bd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5c2  test    r13d, r13d
0x18001f5c5  js      loc_18001F6F9
0x18001f5cb  mov     rax, [rsp+0B8h+var_98]
0x18001f5d0  mov     rbp, [rsp+0B8h+arg_0]
0x18001f5d8  mov     r15, [rsp+0B8h+arg_18]
0x18001f5e0  test    rbx, rbx
0x18001f5e3  jz      loc_18001F290
0x18001f5e9  mov     rax, [rbx]
0x18001f5ec  mov     rcx, rbx
0x18001f5ef  mov     rax, [rax+10h]
0x18001f5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f5f8  mov     rax, [rsp+0B8h+var_98]
0x18001f5fd  jmp     loc_18001F290
0x18001f602  mov     r13b, 1
0x18001f605  jmp     loc_18001F532
0x18001f60a  mov     r13d, 8007000Eh
0x18001f610  mov     rcx, rdi; lpCriticalSection
0x18001f613  call    cs:__imp_LeaveCriticalSection
0x18001f619  mov     r14, [rsp+0B8h+var_30]
0x18001f621  mov     r15, [rsp+0B8h+var_38]
0x18001f629  mov     rdi, [rsp+0B8h+var_28]
0x18001f631  mov     rsi, [rsp+0B8h+var_20]
0x18001f639  mov     rbp, [rsp+0B8h+var_18]
0x18001f641  mov     rbx, [rsp+0B8h+arg_10]
0x18001f649  test    r12, r12
0x18001f64c  jz      short loc_18001F65E
0x18001f64e  mov     rdx, [r12]
0x18001f652  mov     rcx, r12
0x18001f655  mov     rax, [rdx+10h]
0x18001f659  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f65e  mov     eax, r13d
0x18001f661  add     rsp, 0A8h
0x18001f668  pop     r13
0x18001f66a  pop     r12
0x18001f66c  retn
0x18001f66d  mov     r13d, 8007000Eh
0x18001f673  jmp     short loc_18001F621
0x18001f675  mov     r13d, 8007000Eh
0x18001f67b  jmp     loc_18001F599
0x18001f680  call    cs:__imp_RtlGetLastWin32Error
0x18001f686  mov     r13d, eax
  ... truncated ...
```
