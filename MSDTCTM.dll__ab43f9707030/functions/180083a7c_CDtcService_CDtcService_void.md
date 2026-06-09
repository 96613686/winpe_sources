# CDtcService::~CDtcService(void)

- ea: `0x180083a7c`
- end: `0x180083af3`
- name: `??1CDtcService@@QEAA@XZ`
- size: `119`
- prototype: `void __fastcall(CDtcService *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180006750`

## callees

- `0x180083a7c`
- `0x1800bd010`

## import_xrefs

- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180083ac7`
- `api-ms-win-core-processthreads-l1-1-0!TerminateThread` at `0x180083ac7`
- `msvcrt!free` at `0x180083a98`
- `msvcrt!free` at `0x180083aa7`
- `msvcrt!free` at `0x180083ab6`
- `msvcrt!free` at `0x180083a98`
- `msvcrt!free` at `0x180083aa7`
- `msvcrt!free` at `0x180083ab6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CDtcService::~CDtcService(CDtcService *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx
  __int64 v6; // rcx

  *(_QWORD *)this = &CDtcService::`vftable';
  v2 = (void *)*((_QWORD *)this + 1);
  if ( v2 )
    free(v2);
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
    free(v3);
  v4 = (void *)*((_QWORD *)this + 3);
  if ( v4 )
    free(v4);
  v5 = (void *)*((_QWORD *)this + 5);
  if ( v5 )
    TerminateThread(v5, 0);
  v6 = *((_QWORD *)this + 9);
  if ( v6 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v6 + 16LL))(v6);
  z_pService = 0;
}

```

## disassembly

```asm
0x180083a7c  push    rbx
0x180083a7e  sub     rsp, 20h
0x180083a82  mov     rbx, rcx
0x180083a85  lea     rax, ??_7CDtcService@@6B@; const CDtcService::`vftable'
0x180083a8c  mov     [rcx], rax
0x180083a8f  mov     rcx, [rcx+8]; Block
0x180083a93  test    rcx, rcx
0x180083a96  jz      short loc_180083A9E
0x180083a98  call    cs:__imp_free
0x180083a9e  mov     rcx, [rbx+10h]; Block
0x180083aa2  test    rcx, rcx
0x180083aa5  jz      short loc_180083AAD
0x180083aa7  call    cs:__imp_free
0x180083aad  mov     rcx, [rbx+18h]; Block
0x180083ab1  test    rcx, rcx
0x180083ab4  jz      short loc_180083ABC
0x180083ab6  call    cs:__imp_free
0x180083abc  mov     rcx, [rbx+28h]; hThread
0x180083ac0  test    rcx, rcx
0x180083ac3  jz      short loc_180083ACD
0x180083ac5  xor     edx, edx; dwExitCode
0x180083ac7  call    cs:__imp_TerminateThread
0x180083acd  mov     rcx, [rbx+48h]
0x180083ad1  test    rcx, rcx
0x180083ad4  jz      short loc_180083AE2
0x180083ad6  mov     rax, [rcx]
0x180083ad9  mov     rax, [rax+10h]
0x180083add  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180083ae2  mov     cs:?z_pService@@3PEAVCDtcService@@EA, 0; CDtcService * z_pService
0x180083aed  add     rsp, 20h
0x180083af1  pop     rbx
0x180083af2  retn
```
