# ThreadPool::QueueWorkItem(Microsoft::WRL::ComPtr<IThreadPoolCallback>,void *,bool)

- ea: `0x18001f730`
- end: `0x18001fa0f`
- name: `?QueueWorkItem@ThreadPool@@QEAAJV?$ComPtr@UIThreadPoolCallback@@@WRL@Microsoft@@PEAX_N@Z`
- size: `735`
- prototype: `__int64 __fastcall(PVOID pv)`
- caller_count: `13`
- callee_count: `7`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18001dc38`
- `0x18001dd68`
- `0x18001de84`
- `0x18001dfa4`
- `0x180021a60`
- `0x18004a718`
- `0x18004b0d4`
- `0x18004f3d8`
- `0x18006aea4`
- `0x18006bad4`
- `0x18006d000`
- `0x180089694`
- `0x18008ac10`

## callees

- `0x18001a1f0`
- `0x18001ef7c`
- `0x18001f730`
- `0x18001fa18`
- `0x18001fa2c`
- `0x18006fec8`
- `0x180095010`

## import_xrefs

- `ntdll!RtlGetLastWin32Error` at `0x18001f9bd`
- `ntdll!RtlGetLastWin32Error` at `0x18001f9bd`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f871`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18001f871`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f8fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f9fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f8fb`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18001f9fb`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001f904`
- `api-ms-win-core-threadpool-l1-2-0!SubmitThreadpoolWork` at `0x18001f904`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001f858`
- `api-ms-win-core-threadpool-l1-2-0!CreateThreadpoolWork` at `0x18001f858`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001fa04`
- `api-ms-win-core-threadpool-l1-2-0!CloseThreadpoolWork` at `0x18001fa04`

## string_xrefs

- `0x18001f990`: `onecoreuap\base\background\bi\backgroundmanager\lib\ThreadPool.h`

## pseudocode

```c
__int64 __fastcall ThreadPool::QueueWorkItem(
        char *pv,
        __int64 (__fastcall ****a2)(_QWORD, GUID *, __int64 *),
        __int64 a3,
        char a4)
{
  __int64 *v8; // rax
  __int64 *v9; // rbx
  __int64 (__fastcall ***v10)(_QWORD, GUID *, __int64 *); // rdi
  __int64 v11; // rcx
  struct _TP_WORK *ThreadpoolWork; // r15
  char *v13; // rax
  _QWORD *v14; // rdx
  __int64 *v15; // rcx
  char *v16; // rax
  _QWORD *v17; // rax
  char v18; // di
  struct _RTL_CRITICAL_SECTION *v19; // rcx
  unsigned int v20; // ebp
  __int64 (__fastcall ***v21)(_QWORD, GUID *, __int64 *); // rcx
  __int64 v23; // rcx
  int v24; // eax
  signed int LastWin32Error; // eax
  int v26[2]; // [rsp+20h] [rbp-38h] BYREF
  char v27; // [rsp+28h] [rbp-30h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  __int64 (__fastcall ***v29)(_QWORD, GUID *, __int64 *); // [rsp+68h] [rbp+10h] BYREF

  v8 = (__int64 *)operator new(0x28u, (const struct std::nothrow_t *)std::nothrow);
  v9 = v8;
  if ( v8 )
  {
    Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>(v8);
    *v9 = (__int64)&Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable';
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
    *(_QWORD *)v26 = v9;
    *v9 = (__int64)&ThreadPoolData::`vftable';
    v9[2] = 0;
    v9[3] = 0;
    v9[4] = 0;
    v10 = *a2;
    v29 = v10;
    if ( v10 )
      ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v10)[1])(v10);
    if ( a4 )
    {
      if ( (__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *))v9[3] != v10 )
      {
        if ( v10 )
          ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v10)[1])(v10);
        v11 = v9[3];
        v9[3] = (__int64)v10;
        if ( v11 )
          (*(void (__fastcall **)(__int64))(*(_QWORD *)v11 + 16LL))(v11);
      }
      goto LABEL_12;
    }
    v23 = v9[2];
    v9[2] = 0;
    if ( v23 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v23 + 16LL))(v23);
    v24 = Microsoft::WRL::AsWeak<IThreadPoolCallback>(v10, v9 + 2);
    v20 = v24;
    if ( v24 >= 0 )
    {
LABEL_12:
      v9[4] = a3;
      if ( v10 )
        ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v10)[2])(v10);
      (*(void (__fastcall **)(__int64 *))(*v9 + 8))(v9);
      (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
      ThreadpoolWork = CreateThreadpoolWork(ThreadPool::WorkerCallback, pv, (PTP_CALLBACK_ENVIRON)(pv + 16));
      if ( !ThreadpoolWork )
      {
        LastWin32Error = RtlGetLastWin32Error();
        v20 = LastWin32Error;
        if ( LastWin32Error > 0 )
          v20 = (unsigned __int16)LastWin32Error | 0x80070000;
        goto LABEL_22;
      }
      EnterCriticalSection((LPCRITICAL_SECTION)(pv + 136));
      (*(void (__fastcall **)(__int64 *))(*v9 + 8))(v9);
      v13 = (char *)operator new(0x18u, (const struct std::nothrow_t *)std::nothrow);
      v14 = v13;
      v15 = v9;
      if ( v13 )
      {
        v16 = v13 + 16;
        *(_QWORD *)v16 = 0;
        if ( v16 != &v27 )
        {
          *(_QWORD *)v16 = v9;
          v15 = 0;
        }
        v17 = (_QWORD *)*((_QWORD *)pv + 15);
        v18 = 0;
        v14[1] = v17;
        *v14 = pv + 112;
        *v17 = v14;
        *((_QWORD *)pv + 15) = v14;
        ++*((_QWORD *)pv + 16);
        if ( !v15 )
          goto LABEL_20;
      }
      else
      {
        v18 = 1;
      }
      (*(void (__fastcall **)(__int64 *))(*v15 + 16))(v15);
LABEL_20:
      v19 = (struct _RTL_CRITICAL_SECTION *)(pv + 136);
      if ( v18 )
      {
        v20 = -2147024882;
        LeaveCriticalSection(v19);
        CloseThreadpoolWork(ThreadpoolWork);
      }
      else
      {
        LeaveCriticalSection(v19);
        SubmitThreadpoolWork(ThreadpoolWork);
        v20 = 0;
      }
LABEL_22:
      (*(void (__fastcall **)(__int64 *))(*v9 + 16))(v9);
      goto LABEL_23;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x2D,
      (unsigned int)"onecoreuap\\base\\background\\bi\\backgroundmanager\\lib\\ThreadPool.h",
      (const char *)(unsigned int)v24,
      v26[0]);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(&v29);
    Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(v26);
  }
  else
  {
    v20 = -2147024882;
  }
LABEL_23:
  v21 = *a2;
  if ( *a2 )
  {
    *a2 = 0;
    ((void (__fastcall *)(__int64 (__fastcall ***)(_QWORD, GUID *, __int64 *)))(*v21)[2])(v21);
  }
  return v20;
}

```

## disassembly

```asm
0x18001f730  push    rbp
0x18001f732  push    rsi
0x18001f733  push    r12
0x18001f735  sub     rsp, 40h
0x18001f739  mov     [rsp+58h+arg_0], rbx
0x18001f73e  mov     rsi, rdx
0x18001f741  mov     [rsp+58h+arg_18], r13
0x18001f746  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f74d  mov     r13, rcx
0x18001f750  mov     [rsp+58h+var_28], r15
0x18001f755  mov     ecx, 28h ; '('; unsigned __int64
0x18001f75a  movzx   ebp, r9b
0x18001f75e  mov     r15, r8
0x18001f761  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f766  xor     r12d, r12d
0x18001f769  mov     rbx, rax
0x18001f76c  test    rax, rax
0x18001f76f  jz      loc_18001F9DB
0x18001f775  mov     [rsp+58h+arg_10], rdi
0x18001f77a  mov     rcx, rax
0x18001f77d  mov     [rsp+58h+var_20], r14
0x18001f782  call    ??0?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@IEAA@XZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>(void)
0x18001f787  lea     rcx, ??_7?$RuntimeClass@U?$RuntimeClassFlags@$01@WRL@Microsoft@@UIUnknown@@@WRL@Microsoft@@6B@; const Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<2>,IUnknown>::`vftable'
0x18001f78e  mov     [rbx], rcx
0x18001f791  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18001f798  test    rcx, rcx
0x18001f79b  jnz     loc_18001F9E5
0x18001f7a1  lea     rax, ??_7ThreadPoolData@@6B@; const ThreadPoolData::`vftable'
0x18001f7a8  mov     qword ptr [rsp+58h+var_38], rbx; int
0x18001f7ad  mov     [rbx], rax
0x18001f7b0  mov     [rbx+10h], r12
0x18001f7b4  mov     [rbx+18h], r12
0x18001f7b8  mov     [rbx+20h], r12
0x18001f7bc  mov     rdi, [rsi]
0x18001f7bf  mov     [rsp+58h+arg_8], rdi
0x18001f7c4  test    rdi, rdi
0x18001f7c7  jz      short loc_18001F7D8
0x18001f7c9  mov     rax, [rdi]
0x18001f7cc  mov     rcx, rdi
0x18001f7cf  mov     rax, [rax+8]
0x18001f7d3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7d8  test    bpl, bpl
0x18001f7db  jz      loc_18001F95C
0x18001f7e1  cmp     [rbx+18h], rdi
0x18001f7e5  jz      short loc_18001F814
0x18001f7e7  test    rdi, rdi
0x18001f7ea  jz      short loc_18001F7FB
0x18001f7ec  mov     rax, [rdi]
0x18001f7ef  mov     rcx, rdi
0x18001f7f2  mov     rax, [rax+8]
0x18001f7f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f7fb  mov     rcx, [rbx+18h]
0x18001f7ff  mov     [rbx+18h], rdi
0x18001f803  test    rcx, rcx
0x18001f806  jz      short loc_18001F814
0x18001f808  mov     rax, [rcx]
0x18001f80b  mov     rax, [rax+10h]
0x18001f80f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f814  mov     [rbx+20h], r15
0x18001f818  test    rdi, rdi
0x18001f81b  jz      short loc_18001F82C
0x18001f81d  mov     rax, [rdi]
0x18001f820  mov     rcx, rdi
0x18001f823  mov     rax, [rax+10h]
0x18001f827  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f82c  mov     rax, [rbx]
0x18001f82f  mov     rcx, rbx
0x18001f832  mov     rax, [rax+8]
0x18001f836  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f83b  mov     rax, [rbx]
0x18001f83e  mov     rcx, rbx
0x18001f841  mov     rax, [rax+10h]
0x18001f845  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f84a  lea     r8, [r13+10h]; pcbe
0x18001f84e  mov     rdx, r13; pv
0x18001f851  lea     rcx, ?WorkerCallback@ThreadPool@@CAXPEAU_TP_CALLBACK_INSTANCE@@PEAXPEAU_TP_WORK@@@Z; pfnwk
0x18001f858  call    cs:__imp_CreateThreadpoolWork
0x18001f85e  mov     r15, rax
0x18001f861  test    rax, rax
0x18001f864  jz      loc_18001F9BD
0x18001f86a  lea     rcx, [r13+88h]; lpCriticalSection
0x18001f871  call    cs:__imp_EnterCriticalSection
0x18001f877  mov     rax, [rbx]
0x18001f87a  mov     rcx, rbx
0x18001f87d  mov     rax, [rax+8]
0x18001f881  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f886  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x18001f88d  mov     ecx, 18h; unsigned __int64
0x18001f892  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x18001f897  mov     rdx, rax
0x18001f89a  mov     rcx, rbx
0x18001f89d  test    rax, rax
0x18001f8a0  jz      loc_18001F957
0x18001f8a6  add     rax, 10h
0x18001f8aa  lea     r9, [rsp+58h+var_30]
0x18001f8af  lea     r8, [r13+70h]
0x18001f8b3  mov     [rax], r12
0x18001f8b6  cmp     rax, r9
0x18001f8b9  jz      short loc_18001F8C1
0x18001f8bb  mov     [rax], rbx
0x18001f8be  mov     rcx, r12
0x18001f8c1  mov     rax, [r8+8]
0x18001f8c5  xor     dil, dil
0x18001f8c8  mov     [rdx+8], rax
0x18001f8cc  mov     [rdx], r8
0x18001f8cf  mov     [rax], rdx
0x18001f8d2  mov     [r8+8], rdx
0x18001f8d6  inc     qword ptr [r8+10h]
0x18001f8da  test    rcx, rcx
0x18001f8dd  jz      short loc_18001F8EB
0x18001f8df  mov     rax, [rcx]
0x18001f8e2  mov     rax, [rax+10h]
0x18001f8e6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f8eb  lea     rcx, [r13+88h]; lpCriticalSection
0x18001f8f2  test    dil, dil
0x18001f8f5  jnz     loc_18001F9F6
0x18001f8fb  call    cs:__imp_LeaveCriticalSection
0x18001f901  mov     rcx, r15; pwk
0x18001f904  call    cs:__imp_SubmitThreadpoolWork
0x18001f90a  mov     ebp, r12d
0x18001f90d  mov     rax, [rbx]
0x18001f910  mov     rcx, rbx
0x18001f913  mov     rax, [rax+10h]
0x18001f917  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f91c  mov     rdi, [rsp+58h+arg_10]
0x18001f921  mov     r14, [rsp+58h+var_20]
0x18001f926  mov     rcx, [rsi]
0x18001f929  mov     r15, [rsp+58h+var_28]
0x18001f92e  mov     r13, [rsp+58h+arg_18]
0x18001f933  mov     rbx, [rsp+58h+arg_0]
0x18001f938  test    rcx, rcx
0x18001f93b  jz      short loc_18001F94C
0x18001f93d  mov     [rsi], r12
0x18001f940  mov     rdx, [rcx]
0x18001f943  mov     rax, [rdx+10h]
0x18001f947  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f94c  mov     eax, ebp
0x18001f94e  add     rsp, 40h
0x18001f952  pop     r12
0x18001f954  pop     rsi
0x18001f955  pop     rbp
0x18001f956  retn
0x18001f957  mov     dil, 1
0x18001f95a  jmp     short loc_18001F8DF
0x18001f95c  mov     rcx, [rbx+10h]
0x18001f960  mov     [rbx+10h], r12
0x18001f964  test    rcx, rcx
0x18001f967  jz      short loc_18001F975
0x18001f969  mov     rax, [rcx]
0x18001f96c  mov     rax, [rax+10h]
0x18001f970  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f975  lea     rdx, [rbx+10h]
0x18001f979  mov     rcx, rdi
0x18001f97c  call    ??$AsWeak@UIThreadPoolCallback@@@WRL@Microsoft@@YAJPEAUIThreadPoolCallback@@PEAVWeakRef@01@@Z; Microsoft::WRL::AsWeak<IThreadPoolCallback>(IThreadPoolCallback *,Microsoft::WRL::WeakRef *)
0x18001f981  mov     ebp, eax
0x18001f983  test    eax, eax
0x18001f985  jns     loc_18001F814
0x18001f98b  mov     rcx, [rsp+58h]; this
0x18001f990  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\background\\bi\\backg"...
0x18001f997  mov     r9d, eax; char *
0x18001f99a  mov     edx, 2Dh ; '-'; void *
0x18001f99f  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18001f9a4  lea     rcx, [rsp+58h+arg_8]
0x18001f9a9  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f9ae  lea     rcx, [rsp+58h+var_38]
0x18001f9b3  call    ?InternalRelease@?$ComPtr@UIUser@System@Windows@@@WRL@Microsoft@@IEAAKXZ; Microsoft::WRL::ComPtr<Windows::System::IUser>::InternalRelease(void)
0x18001f9b8  jmp     loc_18001F91C
0x18001f9bd  call    cs:__imp_RtlGetLastWin32Error
0x18001f9c3  mov     ebp, eax
0x18001f9c5  test    eax, eax
0x18001f9c7  jle     loc_18001F90D
0x18001f9cd  movzx   ebp, ax
0x18001f9d0  or      ebp, 80070000h
0x18001f9d6  jmp     loc_18001F90D
0x18001f9db  mov     ebp, 8007000Eh
0x18001f9e0  jmp     loc_18001F926
0x18001f9e5  mov     rax, [rcx]
0x18001f9e8  mov     rax, [rax+8]
0x18001f9ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f9f1  jmp     loc_18001F7A1
0x18001f9f6  mov     ebp, 8007000Eh
0x18001f9fb  call    cs:__imp_LeaveCriticalSection
0x18001fa01  mov     rcx, r15; pwk
0x18001fa04  call    cs:__imp_CloseThreadpoolWork
0x18001fa0a  jmp     loc_18001F90D
```
