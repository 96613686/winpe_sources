# ParallelFiringControl::ParallelFiringControl(EventMethod &,EventInterface &,ICallFrame *)

- ea: `0x18000eaf0`
- end: `0x18000ec81`
- name: `??0ParallelFiringControl@@QEAA@AEAVEventMethod@@AEAVEventInterface@@PEAUICallFrame@@@Z`
- size: `401`
- prototype: `ParallelFiringControl *__fastcall(ParallelFiringControl *__hidden this, struct EventMethod *, struct EventInterface *, struct ICallFrame *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18000e6c0`

## callees

- `0x180003d54`
- `0x180008938`
- `0x180009e48`
- `0x18000e2f4`
- `0x18000eaf0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eb9c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000eb9c`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000eb6f`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18000eb6f`

## string_xrefs

- `0x18000eb79`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c
ParallelFiringControl *__fastcall ParallelFiringControl::ParallelFiringControl(
        ParallelFiringControl *this,
        struct EventMethod *a2,
        struct EventInterface *a3,
        struct ICallFrame *a4)
{
  HRESULT Instance; // eax
  CMarshalCallFrameWalker *v7; // rax
  CMarshalCallFrameWalker *v8; // rdi
  int v9; // eax
  int v10; // edi
  __int64 v12; // [rsp+70h] [rbp+8h] BYREF

  FiringControl::FiringControl(this, a2, a3, a4);
  *((_DWORD *)this + 14) = 0;
  *(_QWORD *)this = &ParallelFiringControl::`vftable';
  *((_QWORD *)this + 8) = 0;
  *((_DWORD *)this + 22) = 0;
  *((_QWORD *)this + 12) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 13) = 0;
  *((_DWORD *)this + 28) = 10;
  *((_QWORD *)this + 15) = 0;
  *(_QWORD *)((char *)this + 132) = 0;
  *((_DWORD *)this + 32) = 0;
  *((_DWORD *)this + 36) = 0;
  *((_QWORD *)this + 19) = 0;
  Instance = CoCreateInstance(&CLSID_StdGlobalInterfaceTable, 0, 0x17u, &IID_IGlobalInterfaceTable, (LPVOID *)this + 19);
  if ( Instance < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xF7Cu, 0x12u, Instance);
  v7 = (CMarshalCallFrameWalker *)CoTaskMemAlloc(0x18u);
  if ( !v7 )
  {
    v8 = 0;
    goto LABEL_7;
  }
  v8 = CMarshalCallFrameWalker::CMarshalCallFrameWalker(v7, this);
  if ( !v8 )
LABEL_7:
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xF81u, 0x80001203, 0x12u);
  v12 = 0;
  v9 = (**(__int64 (__fastcall ***)(CMarshalCallFrameWalker *, GUID *, __int64 *))v8)(v8, &IID_ICallFrameWalker, &v12);
  if ( v9 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xF85u, 0x12u, v9);
  if ( !v12 )
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xF86u, 0x80001203, 0x12u);
  v10 = ((__int64 (__fastcall *)(struct ICallFrame *, __int64))a4->lpVtbl->WalkFrame)(a4, 3);
  (*(void (__fastcall **)(__int64))(*(_QWORD *)v12 + 16LL))(v12);
  if ( v10 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0xF8Au, 0x12u, v10);
  return this;
}

```

## disassembly

```asm
0x18000eaf0  push    rbx
0x18000eaf2  push    rbp
0x18000eaf3  push    rsi
0x18000eaf4  push    rdi
0x18000eaf5  push    r14
0x18000eaf7  push    r15
0x18000eaf9  sub     rsp, 38h
0x18000eafd  mov     rsi, r9
0x18000eb00  mov     rbx, rcx
0x18000eb03  call    ??0FiringControl@@QEAA@AEAVEventMethod@@AEAVEventInterface@@PEAUICallFrame@@@Z; FiringControl::FiringControl(EventMethod &,EventInterface &,ICallFrame *)
0x18000eb08  xor     ebp, ebp
0x18000eb0a  lea     rax, [rbx+98h]
0x18000eb11  mov     [rbx+38h], ebp
0x18000eb14  lea     rcx, ??_7ParallelFiringControl@@6B@; const ParallelFiringControl::`vftable'
0x18000eb1b  mov     [rbx], rcx
0x18000eb1e  lea     r9, IID_IGlobalInterfaceTable; riid
0x18000eb25  mov     [rbx+40h], rbp
0x18000eb29  lea     rcx, CLSID_StdGlobalInterfaceTable; rclsid
0x18000eb30  mov     [rbx+58h], ebp
0x18000eb33  lea     r8d, [rbp+17h]; dwClsContext
0x18000eb37  mov     [rbx+60h], rbp
0x18000eb3b  xor     edx, edx; pUnkOuter
0x18000eb3d  mov     [rbx+50h], rbp
0x18000eb41  mov     [rbx+48h], rbp
0x18000eb45  mov     [rbx+68h], rbp
0x18000eb49  mov     dword ptr [rbx+70h], 0Ah
0x18000eb50  mov     [rbx+78h], rbp
0x18000eb54  mov     [rbx+84h], rbp
0x18000eb5b  mov     [rbx+80h], ebp
0x18000eb61  mov     [rbx+90h], ebp
0x18000eb67  mov     [rax], rbp
0x18000eb6a  mov     [rsp+68h+ppv], rax; ppv
0x18000eb6f  call    cs:__imp_CoCreateInstance
0x18000eb75  lea     r14d, [rbp+12h]
0x18000eb79  lea     r15, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x18000eb80  test    eax, eax
0x18000eb82  jns     short loc_18000EB97
0x18000eb84  mov     r8d, r14d; unsigned __int16
0x18000eb87  mov     r9d, eax; int
0x18000eb8a  mov     edx, 0F7Ch; unsigned int
0x18000eb8f  mov     rcx, r15; unsigned __int16 *
0x18000eb92  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000eb97  mov     ecx, 18h; cb
0x18000eb9c  call    cs:__imp_CoTaskMemAlloc
0x18000eba2  test    rax, rax
0x18000eba5  jz      short loc_18000EBBC
0x18000eba7  mov     rdx, rbx; struct ParallelFiringControl *
0x18000ebaa  mov     rcx, rax; this
0x18000ebad  call    ??0CMarshalCallFrameWalker@@QEAA@PEAVParallelFiringControl@@@Z; CMarshalCallFrameWalker::CMarshalCallFrameWalker(ParallelFiringControl *)
0x18000ebb2  mov     rdi, rax
0x18000ebb5  test    rax, rax
0x18000ebb8  jz      short loc_18000EBBF
0x18000ebba  jmp     short loc_18000EBD5
0x18000ebbc  mov     rdi, rbp
0x18000ebbf  mov     r9d, r14d; unsigned __int16
0x18000ebc2  mov     edx, 0F81h; unsigned int
0x18000ebc7  mov     r8d, 80001203h; unsigned int
0x18000ebcd  mov     rcx, r15; unsigned __int16 *
0x18000ebd0  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000ebd5  mov     [rsp+68h+arg_0], rbp
0x18000ebda  lea     r8, [rsp+68h+arg_0]
0x18000ebdf  mov     rax, [rdi]
0x18000ebe2  lea     rdx, IID_ICallFrameWalker
0x18000ebe9  mov     rcx, rdi
0x18000ebec  mov     rax, [rax]
0x18000ebef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ebf4  test    eax, eax
0x18000ebf6  jns     short loc_18000EC0B
0x18000ebf8  mov     r8d, r14d; unsigned __int16
0x18000ebfb  mov     r9d, eax; int
0x18000ebfe  mov     edx, 0F85h; unsigned int
0x18000ec03  mov     rcx, r15; unsigned __int16 *
0x18000ec06  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000ec0b  mov     r8, [rsp+68h+arg_0]
0x18000ec10  test    r8, r8
0x18000ec13  jnz     short loc_18000EC30
0x18000ec15  mov     r9d, r14d; unsigned __int16
0x18000ec18  mov     edx, 0F86h; unsigned int
0x18000ec1d  mov     r8d, 80001203h; unsigned int
0x18000ec23  mov     rcx, r15; unsigned __int16 *
0x18000ec26  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x18000ec2b  mov     r8, [rsp+68h+arg_0]
0x18000ec30  mov     rax, [rsi]
0x18000ec33  mov     edx, 3
0x18000ec38  mov     rcx, rsi
0x18000ec3b  mov     rax, [rax+80h]
0x18000ec42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec47  mov     rcx, [rsp+68h+arg_0]
0x18000ec4c  mov     edi, eax
0x18000ec4e  mov     rdx, [rcx]
0x18000ec51  mov     rax, [rdx+10h]
0x18000ec55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec5a  test    edi, edi
0x18000ec5c  jns     short loc_18000EC71
0x18000ec5e  mov     r8d, r14d; unsigned __int16
0x18000ec61  mov     r9d, edi; int
0x18000ec64  mov     edx, 0F8Ah; unsigned int
0x18000ec69  mov     rcx, r15; unsigned __int16 *
0x18000ec6c  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x18000ec71  mov     rax, rbx
0x18000ec74  add     rsp, 38h
0x18000ec78  pop     r15
0x18000ec7a  pop     r14
0x18000ec7c  pop     rdi
0x18000ec7d  pop     rsi
0x18000ec7e  pop     rbp
0x18000ec7f  pop     rbx
0x18000ec80  retn
```
