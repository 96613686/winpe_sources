# CMPEG2Demultiplexer::ConnectESEvents(void)

- ea: `0x18001376c`
- end: `0x180013a4f`
- name: `?ConnectESEvents@CMPEG2Demultiplexer@@QEAAXXZ`
- size: `739`
- prototype: `void __fastcall(CMPEG2Demultiplexer *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x18001ac30`

## callees

- `0x18001376c`
- `0x180016c8c`
- `0x180034010`

## import_xrefs

- `KERNEL32!LeaveCriticalSection` at `0x1800137d4`
- `KERNEL32!LeaveCriticalSection` at `0x1800138b9`
- `KERNEL32!LeaveCriticalSection` at `0x1800138fb`
- `KERNEL32!LeaveCriticalSection` at `0x1800137d4`
- `KERNEL32!LeaveCriticalSection` at `0x1800138b9`
- `KERNEL32!LeaveCriticalSection` at `0x1800138fb`
- `KERNEL32!EnterCriticalSection` at `0x18001379f`
- `KERNEL32!EnterCriticalSection` at `0x1800137b0`
- `KERNEL32!EnterCriticalSection` at `0x180013899`
- `KERNEL32!EnterCriticalSection` at `0x18001379f`
- `KERNEL32!EnterCriticalSection` at `0x1800137b0`
- `KERNEL32!EnterCriticalSection` at `0x180013899`
- `ole32!CoCreateInstance` at `0x18001384b`
- `ole32!CoCreateInstance` at `0x18001384b`

## pseudocode

```c
void __fastcall CMPEG2Demultiplexer::ConnectESEvents(struct _RTL_CRITICAL_SECTION *this)
{
  int (__fastcall ***OwningThread)(_QWORD, GUID *, struct IESEvents **); // rsi
  ULONG_PTR *p_SpinCount; // r15
  struct _RTL_CRITICAL_SECTION *v4; // rdi
  _QWORD *v5; // rbx
  ULONG_PTR v6; // rcx
  struct IESEvents *v7; // rcx
  __int64 v8; // r8
  HANDLE v9; // rcx
  struct IESEvents *v10; // [rsp+70h] [rbp+40h] BYREF
  __int64 v11; // [rsp+78h] [rbp+48h] BYREF
  __int64 v12; // [rsp+80h] [rbp+50h] BYREF
  __int64 v13; // [rsp+88h] [rbp+58h] BYREF

  OwningThread = (int (__fastcall ***)(_QWORD, GUID *, struct IESEvents **))this[2].OwningThread;
  p_SpinCount = &this[35].SpinCount;
  if ( !OwningThread )
    goto LABEL_23;
  v4 = this + 36;
  EnterCriticalSection(this + 36);
  v10 = 0;
  v11 = 0;
  EnterCriticalSection((LPCRITICAL_SECTION)(p_SpinCount + 1));
  v5 = p_SpinCount + 6;
  v6 = p_SpinCount[6];
  if ( v6 )
  {
    (*(void (__fastcall **)(ULONG_PTR))(*(_QWORD *)v6 + 16LL))(v6);
    *v5 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(p_SpinCount + 1));
  if ( (**OwningThread)(OwningThread, &IID_IServiceProvider, &v10) < 0 )
    goto LABEL_13;
  v7 = v10;
  if ( !v10 )
  {
    v8 = v11;
    goto LABEL_18;
  }
  if ( ((int (__fastcall *)(struct IESEvents *, GUID *, GUID *, struct _RTL_CRITICAL_SECTION *))v10->lpVtbl->OnESEventReceived)(
         v10,
         &CLSID_ESEventService,
         &IID_IESEventService,
         &v4[1]) >= 0
    && *v5 )
  {
    goto LABEL_16;
  }
  if ( CoCreateInstance(
         &CLSID_ESEventService,
         0,
         1u,
         &GUID_ed89a619_4c06_4b2f_99eb_c7669b13047c,
         (LPVOID *)&v4[1].DebugInfo) < 0 )
    goto LABEL_13;
  if ( !*v5 )
    goto LABEL_16;
  if ( (**(int (__fastcall ***)(_QWORD, GUID *, __int64 *))*v5)(*v5, &IID_IESEventServiceConfiguration, &v11) < 0 )
  {
LABEL_13:
    EnterCriticalSection((LPCRITICAL_SECTION)(p_SpinCount + 1));
    if ( *v5 )
    {
      (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v5 + 16LL))(*v5);
      *v5 = 0;
    }
    LeaveCriticalSection((LPCRITICAL_SECTION)(p_SpinCount + 1));
    goto LABEL_16;
  }
  v8 = v11;
  if ( v11 )
  {
    if ( (*(int (__fastcall **)(__int64, int (__fastcall ***)(_QWORD, GUID *, struct IESEvents **)))(*(_QWORD *)v11 + 56LL))(
           v11,
           OwningThread) < 0 )
      goto LABEL_13;
LABEL_16:
    v8 = v11;
  }
  v7 = v10;
LABEL_18:
  if ( v8 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v8 + 16LL))(v8);
    v7 = v10;
    v11 = 0;
  }
  if ( v7 )
  {
    ((void (__fastcall *)(struct IESEvents *))v7->lpVtbl->Release)(v7);
    v10 = 0;
  }
  LeaveCriticalSection((LPCRITICAL_SECTION)(p_SpinCount + 1));
LABEL_23:
  v9 = this[2].OwningThread;
  v13 = 0;
  v11 = 0;
  LODWORD(v10) = 0;
  v12 = 0;
  if ( (*(int (__fastcall **)(HANDLE, __int64 *))(*(_QWORD *)v9 + 40LL))(v9, &v12) >= 0 )
  {
LABEL_24:
    v11 = 0;
    while ( (*(int (__fastcall **)(__int64, __int64, __int64 *, struct IESEvents **))(*(_QWORD *)v12 + 24LL))(
              v12,
              1,
              &v11,
              &v10) >= 0
         && (_DWORD)v10 )
    {
      if ( (**(int (__fastcall ***)(__int64, GUID *, __int64 *))v11)(v11, &IID_IBDA_NetworkProvider, &v13) >= 0 )
      {
        if ( v11 )
        {
          (*(void (**)(void))(*(_QWORD *)v11 + 16LL))();
          v11 = 0;
        }
        break;
      }
      if ( v11 )
      {
        (*(void (**)(void))(*(_QWORD *)v11 + 16LL))();
        goto LABEL_24;
      }
    }
    if ( v12 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  }
  if ( v13 )
  {
    v10 = 0;
    if ( (**(int (__fastcall ***)(__int64, GUID *, struct IESEvents **))v13)(
           v13,
           &GUID_abd414bf_cfe5_4e5e_af5b_4b4e49c5bfeb,
           &v10) >= 0 )
    {
      if ( v10 )
      {
        CDShowESEventEx::RegisterForESEvents(
          (CDShowESEventEx *)p_SpinCount,
          &GUID_b2127d42_7be5_4f4b_9130_6679899f4f4b,
          v10);
        CDShowESEventEx::RegisterForESEvents(
          (CDShowESEventEx *)p_SpinCount,
          &GUID_d97287b2_2dfd_436a_9485_99d7d4ab5a69,
          v10);
        if ( v10 )
        {
          ((void (__fastcall *)(struct IESEvents *))v10->lpVtbl->Release)(v10);
          v10 = 0;
        }
      }
    }
    if ( v13 )
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v13 + 16LL))(v13);
  }
}

```

## disassembly

```asm
0x18001376c  push    rbp
0x18001376e  push    rbx
0x18001376f  push    rsi
0x180013770  push    rdi
0x180013771  push    r12
0x180013773  push    r14
0x180013775  push    r15
0x180013777  mov     rbp, rsp
0x18001377a  sub     rsp, 30h
0x18001377e  mov     rsi, [rcx+60h]
0x180013782  lea     r15, [rcx+598h]
0x180013789  xor     r12d, r12d
0x18001378c  mov     r14, rcx
0x18001378f  test    rsi, rsi
0x180013792  jz      loc_180013901
0x180013798  lea     rdi, [r15+8]
0x18001379c  mov     rcx, rdi; lpCriticalSection
0x18001379f  call    cs:__imp_EnterCriticalSection
0x1800137a5  mov     rcx, rdi; lpCriticalSection
0x1800137a8  mov     [rbp+arg_0], r12
0x1800137ac  mov     [rbp+arg_8], r12
0x1800137b0  call    cs:__imp_EnterCriticalSection
0x1800137b6  lea     rbx, [rdi+28h]
0x1800137ba  mov     rcx, [rbx]
0x1800137bd  test    rcx, rcx
0x1800137c0  jz      short loc_1800137D1
0x1800137c2  mov     rax, [rcx]
0x1800137c5  mov     rax, [rax+10h]
0x1800137c9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137ce  mov     [rbx], r12
0x1800137d1  mov     rcx, rdi; lpCriticalSection
0x1800137d4  call    cs:__imp_LeaveCriticalSection
0x1800137da  mov     rax, [rsi]
0x1800137dd  lea     r8, [rbp+arg_0]
0x1800137e1  lea     rdx, IID_IServiceProvider
0x1800137e8  mov     rcx, rsi
0x1800137eb  mov     rax, [rax]
0x1800137ee  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800137f3  test    eax, eax
0x1800137f5  js      loc_180013896
0x1800137fb  mov     rcx, [rbp+arg_0]
0x1800137ff  test    rcx, rcx
0x180013802  jz      loc_18001398D
0x180013808  mov     rax, [rcx]
0x18001380b  lea     r8, IID_IESEventService
0x180013812  mov     r9, rbx
0x180013815  lea     rdx, CLSID_ESEventService
0x18001381c  mov     rax, [rax+18h]
0x180013820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013825  test    eax, eax
0x180013827  js      short loc_180013832
0x180013829  cmp     [rbx], r12
0x18001382c  jnz     loc_1800138BF
0x180013832  xor     edx, edx; pUnkOuter
0x180013834  mov     [rsp+30h+ppv], rbx; ppv
0x180013839  lea     r9, _GUID_ed89a619_4c06_4b2f_99eb_c7669b13047c; riid
0x180013840  lea     rcx, CLSID_ESEventService; rclsid
0x180013847  lea     r8d, [rdx+1]; dwClsContext
0x18001384b  call    cs:__imp_CoCreateInstance
0x180013851  test    eax, eax
0x180013853  js      short loc_180013896
0x180013855  mov     rcx, [rbx]
0x180013858  test    rcx, rcx
0x18001385b  jz      short loc_1800138BF
0x18001385d  mov     rax, [rcx]
0x180013860  lea     r8, [rbp+arg_8]
0x180013864  lea     rdx, IID_IESEventServiceConfiguration
0x18001386b  mov     rax, [rax]
0x18001386e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013873  test    eax, eax
0x180013875  js      short loc_180013896
0x180013877  mov     r8, [rbp+arg_8]
0x18001387b  test    r8, r8
0x18001387e  jz      short loc_1800138C3
0x180013880  mov     rax, [r8]
0x180013883  mov     rdx, rsi
0x180013886  mov     rcx, r8
0x180013889  mov     rax, [rax+38h]
0x18001388d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013892  test    eax, eax
0x180013894  jns     short loc_1800138BF
0x180013896  mov     rcx, rdi; lpCriticalSection
0x180013899  call    cs:__imp_EnterCriticalSection
0x18001389f  mov     rcx, [rbx]
0x1800138a2  test    rcx, rcx
0x1800138a5  jz      short loc_1800138B6
0x1800138a7  mov     rax, [rcx]
0x1800138aa  mov     rax, [rax+10h]
0x1800138ae  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138b3  mov     [rbx], r12
0x1800138b6  mov     rcx, rdi; lpCriticalSection
0x1800138b9  call    cs:__imp_LeaveCriticalSection
0x1800138bf  mov     r8, [rbp+arg_8]
0x1800138c3  mov     rcx, [rbp+arg_0]
0x1800138c7  test    r8, r8
0x1800138ca  jz      short loc_1800138E3
0x1800138cc  mov     rax, [r8]
0x1800138cf  mov     rcx, r8
0x1800138d2  mov     rax, [rax+10h]
0x1800138d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138db  mov     rcx, [rbp+arg_0]
0x1800138df  mov     [rbp+arg_8], r12
0x1800138e3  test    rcx, rcx
0x1800138e6  jz      short loc_1800138F8
0x1800138e8  mov     rax, [rcx]
0x1800138eb  mov     rax, [rax+10h]
0x1800138ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800138f4  mov     [rbp+arg_0], r12
0x1800138f8  mov     rcx, rdi; lpCriticalSection
0x1800138fb  call    cs:__imp_LeaveCriticalSection
0x180013901  mov     rcx, [r14+60h]
0x180013905  lea     rdx, [rbp+arg_10]
0x180013909  mov     [rbp+arg_18], r12
0x18001390d  mov     [rbp+arg_8], r12
0x180013911  mov     dword ptr [rbp+arg_0], r12d
0x180013915  mov     [rbp+arg_10], r12
0x180013919  mov     rax, [rcx]
0x18001391c  mov     rax, [rax+28h]
0x180013920  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013925  test    eax, eax
0x180013927  js      loc_1800139C0
0x18001392d  mov     [rbp+arg_8], r12
0x180013931  mov     rcx, [rbp+arg_10]
0x180013935  lea     r9, [rbp+arg_0]
0x180013939  lea     r8, [rbp+arg_8]
0x18001393d  mov     edx, 1
0x180013942  mov     rax, [rcx]
0x180013945  mov     rax, [rax+18h]
0x180013949  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001394e  test    eax, eax
0x180013950  js      short loc_1800139AB
0x180013952  cmp     dword ptr [rbp+arg_0], r12d
0x180013956  jz      short loc_1800139AB
0x180013958  mov     rcx, [rbp+arg_8]
0x18001395c  lea     r8, [rbp+arg_18]
0x180013960  lea     rdx, IID_IBDA_NetworkProvider
0x180013967  mov     rax, [rcx]
0x18001396a  mov     rax, [rax]
0x18001396d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013972  mov     rcx, [rbp+arg_8]
0x180013976  test    eax, eax
0x180013978  jns     short loc_180013996
0x18001397a  test    rcx, rcx
0x18001397d  jz      short loc_180013931
0x18001397f  mov     rax, [rcx]
0x180013982  mov     rax, [rax+10h]
0x180013986  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001398b  jmp     short loc_18001392D
0x18001398d  mov     r8, [rbp+arg_8]
0x180013991  jmp     loc_1800138C7
0x180013996  test    rcx, rcx
0x180013999  jz      short loc_1800139AB
0x18001399b  mov     rax, [rcx]
0x18001399e  mov     rax, [rax+10h]
0x1800139a2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139a7  mov     [rbp+arg_8], r12
0x1800139ab  mov     rcx, [rbp+arg_10]
0x1800139af  test    rcx, rcx
0x1800139b2  jz      short loc_1800139C0
0x1800139b4  mov     rax, [rcx]
0x1800139b7  mov     rax, [rax+10h]
0x1800139bb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139c0  mov     rcx, [rbp+arg_18]
0x1800139c4  test    rcx, rcx
0x1800139c7  jz      short loc_180013A40
0x1800139c9  mov     [rbp+arg_0], r12
0x1800139cd  lea     r8, [rbp+arg_0]
0x1800139d1  mov     rax, [rcx]
0x1800139d4  lea     rdx, _GUID_abd414bf_cfe5_4e5e_af5b_4b4e49c5bfeb
0x1800139db  mov     rax, [rax]
0x1800139de  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800139e3  test    eax, eax
0x1800139e5  js      short loc_180013A2B
0x1800139e7  mov     r8, [rbp+arg_0]; struct IESEvents *
0x1800139eb  test    r8, r8
0x1800139ee  jz      short loc_180013A2B
0x1800139f0  lea     rdx, _GUID_b2127d42_7be5_4f4b_9130_6679899f4f4b; struct _GUID *
0x1800139f7  mov     rcx, r15; this
0x1800139fa  call    ?RegisterForESEvents@CDShowESEventEx@@QEAAJAEBU_GUID@@PEAUIESEvents@@@Z; CDShowESEventEx::RegisterForESEvents(_GUID const &,IESEvents *)
0x1800139ff  mov     r8, [rbp+arg_0]; struct IESEvents *
0x180013a03  lea     rdx, _GUID_d97287b2_2dfd_436a_9485_99d7d4ab5a69; struct _GUID *
0x180013a0a  mov     rcx, r15; this
0x180013a0d  call    ?RegisterForESEvents@CDShowESEventEx@@QEAAJAEBU_GUID@@PEAUIESEvents@@@Z; CDShowESEventEx::RegisterForESEvents(_GUID const &,IESEvents *)
0x180013a12  mov     rcx, [rbp+arg_0]
0x180013a16  test    rcx, rcx
0x180013a19  jz      short loc_180013A2B
0x180013a1b  mov     rax, [rcx]
0x180013a1e  mov     rax, [rax+10h]
0x180013a22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a27  mov     [rbp+arg_0], r12
0x180013a2b  mov     rcx, [rbp+arg_18]
0x180013a2f  test    rcx, rcx
0x180013a32  jz      short loc_180013A40
0x180013a34  mov     rax, [rcx]
0x180013a37  mov     rax, [rax+10h]
0x180013a3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013a40  add     rsp, 30h
0x180013a44  pop     r15
0x180013a46  pop     r14
0x180013a48  pop     r12
0x180013a4a  pop     rdi
0x180013a4b  pop     rsi
0x180013a4c  pop     rbx
0x180013a4d  pop     rbp
0x180013a4e  retn
```
