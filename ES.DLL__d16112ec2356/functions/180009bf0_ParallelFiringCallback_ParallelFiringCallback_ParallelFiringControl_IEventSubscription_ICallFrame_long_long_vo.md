# ParallelFiringCallback::ParallelFiringCallback(ParallelFiringControl &,IEventSubscription *,ICallFrame *,long *,long *,void *,void *)

- ea: `0x180009bf0`
- end: `0x180009dc8`
- name: `??0ParallelFiringCallback@@QEAA@AEAVParallelFiringControl@@PEAUIEventSubscription@@PEAUICallFrame@@PEAJ3PEAX4@Z`
- size: `472`
- prototype: `ParallelFiringCallback *__usercall@<rax>(ParallelFiringCallback *__hidden this@<rcx>, struct ParallelFiringControl *@<rdx>, struct IEventSubscription *@<r8>, struct ICallFrame *@<r9>, int *, int *, void *, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800098f0`

## callees

- `0x180003d54`
- `0x180008938`
- `0x180009bf0`
- `0x180009dd0`
- `0x180046010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180009c69`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSectionAndSpinCount` at `0x180009c69`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009c81`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009c81`

## string_xrefs

- `0x180009d43`: `com\complus\src\events\tier1\agent.cpp`
- `0x180009d66`: `com\complus\src\events\tier1\agent.cpp`
- `0x180009d84`: `com\complus\src\events\tier1\agent.cpp`
- `0x180009daf`: `com\complus\src\events\tier1\agent.cpp`

## pseudocode

```c
ParallelFiringCallback *__fastcall ParallelFiringCallback::ParallelFiringCallback(
        ParallelFiringCallback *this,
        struct ParallelFiringControl *a2,
        struct IEventSubscription *a3,
        struct ICallFrame *a4,
        int *a5,
        int *a6,
        void *a7,
        void *a8)
{
  CCopyCallFrameWalker *v10; // rax
  CCopyCallFrameWalker *v11; // rbx
  int v12; // eax
  int *v13; // r8
  int v14; // ebx

  *((_QWORD *)this + 2) = a2;
  *(_QWORD *)this = &ParallelFiringCallback::`vftable';
  *((_QWORD *)this + 5) = a5;
  *((_QWORD *)this + 6) = a6;
  *((_QWORD *)this + 7) = a7;
  *((_QWORD *)this + 8) = a8;
  *((_DWORD *)this + 2) = 1;
  *((_QWORD *)this + 3) = a3;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_DWORD *)this + 30) = 0;
  *((_DWORD *)this + 30) = InitializeCriticalSectionAndSpinCount((LPCRITICAL_SECTION)this + 2, 0x1F4u);
  *((_DWORD *)this + 32) = 0;
  v10 = (CCopyCallFrameWalker *)CoTaskMemAlloc(0x18u);
  if ( v10 )
  {
    v11 = CCopyCallFrameWalker::CCopyCallFrameWalker(v10, this);
    if ( v11 )
      goto LABEL_3;
  }
  else
  {
    v11 = 0;
  }
  InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x1059u, 0x80001203, 0x12u);
LABEL_3:
  a5 = 0;
  v12 = (**(__int64 (__fastcall ***)(CCopyCallFrameWalker *, GUID *, int **))v11)(v11, &IID_ICallFrameWalker, &a5);
  if ( v12 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x105Eu, 0x12u, v12);
  v13 = a5;
  if ( !a5 )
  {
    InternalError(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x105Fu, 0x80001203, 0x12u);
    v13 = a5;
  }
  v14 = ((__int64 (__fastcall *)(struct ICallFrame *, __int64, int *, char *))a4->lpVtbl->Copy)(
          a4,
          1,
          v13,
          (char *)this + 32);
  (*(void (__fastcall **)(int *))(*(_QWORD *)a5 + 16LL))(a5);
  if ( v14 < 0 )
    InternalError_HR(L"com\\complus\\src\\events\\tier1\\agent.cpp", 0x106Cu, 0x12u, v14);
  (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 3) + 8LL))(*((_QWORD *)this + 3));
  return this;
}

```

## disassembly

```asm
0x180009bf0  push    rbx
0x180009bf2  push    rsi
0x180009bf3  push    rdi
0x180009bf4  push    r14
0x180009bf6  sub     rsp, 38h
0x180009bfa  mov     [rcx+10h], rdx
0x180009bfe  lea     rax, ??_7ParallelFiringCallback@@6B@; const ParallelFiringCallback::`vftable'
0x180009c05  mov     [rcx], rax
0x180009c08  mov     rdi, rcx
0x180009c0b  mov     rax, [rsp+58h+arg_20]
0x180009c13  mov     edx, 1F4h; dwSpinCount
0x180009c18  mov     [rcx+28h], rax
0x180009c1c  mov     rsi, r9
0x180009c1f  mov     rax, [rsp+58h+arg_28]
0x180009c27  mov     [rcx+30h], rax
0x180009c2b  mov     rax, [rsp+58h+arg_30]
0x180009c33  mov     [rcx+38h], rax
0x180009c37  mov     rax, [rsp+58h+arg_38]
0x180009c3f  mov     [rcx+40h], rax
0x180009c43  mov     dword ptr [rcx+8], 1
0x180009c4a  mov     [rcx+18h], r8
0x180009c4e  mov     qword ptr [rcx+20h], 0
0x180009c56  mov     qword ptr [rcx+48h], 0
0x180009c5e  mov     dword ptr [rcx+78h], 0
0x180009c65  add     rcx, 50h ; 'P'; lpCriticalSection
0x180009c69  call    cs:__imp_InitializeCriticalSectionAndSpinCount
0x180009c6f  mov     [rdi+78h], eax
0x180009c72  mov     ecx, 18h; cb
0x180009c77  mov     dword ptr [rdi+80h], 0
0x180009c81  call    cs:__imp_CoTaskMemAlloc
0x180009c87  test    rax, rax
0x180009c8a  jz      loc_180009D3C
0x180009c90  mov     rdx, rdi; struct ParallelFiringCallback *
0x180009c93  mov     rcx, rax; this
0x180009c96  call    ??0CCopyCallFrameWalker@@QEAA@PEAVParallelFiringCallback@@@Z; CCopyCallFrameWalker::CCopyCallFrameWalker(ParallelFiringCallback *)
0x180009c9b  mov     rbx, rax
0x180009c9e  test    rax, rax
0x180009ca1  jz      loc_180009D3E
0x180009ca7  mov     [rsp+58h+arg_20], 0
0x180009cb3  lea     r8, [rsp+58h+arg_20]
0x180009cbb  mov     rax, [rbx]
0x180009cbe  lea     rdx, IID_ICallFrameWalker
0x180009cc5  mov     rcx, rbx
0x180009cc8  mov     rax, [rax]
0x180009ccb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009cd0  test    eax, eax
0x180009cd2  js      loc_180009D60
0x180009cd8  mov     r8, [rsp+58h+arg_20]
0x180009ce0  test    r8, r8
0x180009ce3  jz      loc_180009D7F
0x180009ce9  mov     rax, [rsi]
0x180009cec  lea     r9, [rdi+20h]
0x180009cf0  mov     edx, 1
0x180009cf5  mov     rcx, rsi
0x180009cf8  mov     rax, [rax+68h]
0x180009cfc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d01  mov     rcx, [rsp+58h+arg_20]
0x180009d09  mov     ebx, eax
0x180009d0b  mov     rdx, [rcx]
0x180009d0e  mov     rax, [rdx+10h]
0x180009d12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d17  test    ebx, ebx
0x180009d19  js      loc_180009DA9
0x180009d1f  mov     rcx, [rdi+18h]
0x180009d23  mov     rax, [rcx]
0x180009d26  mov     rax, [rax+8]
0x180009d2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d2f  mov     rax, rdi
0x180009d32  add     rsp, 38h
0x180009d36  pop     r14
0x180009d38  pop     rdi
0x180009d39  pop     rsi
0x180009d3a  pop     rbx
0x180009d3b  retn
0x180009d3c  xor     ebx, ebx
0x180009d3e  mov     edx, 1059h; unsigned int
0x180009d43  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180009d4a  mov     r9d, 12h; unsigned __int16
0x180009d50  mov     r8d, 80001203h; unsigned int
0x180009d56  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180009d5b  jmp     loc_180009CA7
0x180009d60  mov     r8d, 12h; unsigned __int16
0x180009d66  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180009d6d  mov     r9d, eax; int
0x180009d70  mov     edx, 105Eh; unsigned int
0x180009d75  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180009d7a  jmp     loc_180009CD8
0x180009d7f  mov     edx, 105Fh; unsigned int
0x180009d84  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180009d8b  mov     r9d, 12h; unsigned __int16
0x180009d91  mov     r8d, 80001203h; unsigned int
0x180009d97  call    ?InternalError@@YA_NPEBGKKG@Z; InternalError(ushort const *,ulong,ulong,ushort)
0x180009d9c  mov     r8, [rsp+58h+arg_20]
0x180009da4  jmp     loc_180009CE9
0x180009da9  mov     r8d, 12h; unsigned __int16
0x180009daf  lea     rcx, aComComplusSrcE_10; "com\\complus\\src\\events\\tier1\\agent"...
0x180009db6  mov     r9d, ebx; int
0x180009db9  mov     edx, 106Ch; unsigned int
0x180009dbe  call    ?InternalError_HR@@YA_NPEBGKGJ@Z; InternalError_HR(ushort const *,ulong,ushort,long)
0x180009dc3  jmp     loc_180009D1F
```
