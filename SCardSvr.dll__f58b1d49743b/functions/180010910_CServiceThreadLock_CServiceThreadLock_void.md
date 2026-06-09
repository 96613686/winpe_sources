# CServiceThreadLock::~CServiceThreadLock(void)

- ea: `0x180010910`
- end: `0x18001098d`
- name: `??1CServiceThreadLock@@QEAA@XZ`
- size: `125`
- prototype: `void __fastcall(CServiceThreadLock *__hidden this)`
- caller_count: `23`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180004804`
- `0x180004af8`
- `0x180004c8c`
- `0x180005b2c`
- `0x180010044`
- `0x180010dc4`
- `0x180012190`
- `0x180015790`
- `0x18002fe68`
- `0x180030024`
- `0x1800300b8`
- `0x18003019c`
- `0x1800330c6`
- `0x1800331cc`
- `0x180033245`
- `0x180033324`
- `0x180033720`
- `0x180033990`
- `0x180033b90`
- `0x180034130`
- `0x1800345f7`
- `0x1800363c1`
- `0x180036520`

## callees

- `0x180010910`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010963`
- `api-ms-win-core-synch-l1-1-0!SetEvent` at `0x180010963`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010985`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180010985`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010939`
- `api-ms-win-core-processthreads-l1-1-0!TlsGetValue` at `0x180010939`

## pseudocode

```c
void __fastcall CServiceThreadLock::~CServiceThreadLock(CServiceThreadLock *this)
{
  __int64 v1; // rbx

  v1 = *(_QWORD *)this;
  if ( *(_QWORD *)this )
  {
    (**(void (__fastcall ***)(__int64, _QWORD, _QWORD))(v1 + 80))(v1 + 80, 0, 0);
    if ( *(LPVOID *)(v1 + 136) == TlsGetValue(dwTlsIndex) && (*(_DWORD *)(v1 + 144))-- == 1 )
    {
      *(_QWORD *)(v1 + 136) = 0;
      if ( !SetEvent(*(HANDLE *)(v1 + 152)) )
        GetLastError();
    }
    (*(void (__fastcall **)(__int64))(*(_QWORD *)(v1 + 80) + 8LL))(v1 + 80);
  }
}

```

## disassembly

```asm
0x180010910  push    rbx
0x180010912  sub     rsp, 20h
0x180010916  mov     rbx, [rcx]
0x180010919  test    rbx, rbx
0x18001091c  jz      short loc_18001097F
0x18001091e  mov     rax, [rbx+50h]
0x180010922  xor     r8d, r8d
0x180010925  xor     edx, edx
0x180010927  lea     rcx, [rbx+50h]
0x18001092b  mov     rax, [rax]
0x18001092e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010933  mov     ecx, cs:dwTlsIndex; dwTlsIndex
0x180010939  call    cs:__imp_TlsGetValue
0x18001093f  cmp     [rbx+88h], rax
0x180010946  jnz     short loc_18001096D
0x180010948  add     dword ptr [rbx+90h], 0FFFFFFFFh
0x18001094f  jnz     short loc_18001096D
0x180010951  mov     qword ptr [rbx+88h], 0
0x18001095c  mov     rcx, [rbx+98h]; hEvent
0x180010963  call    cs:__imp_SetEvent
0x180010969  test    eax, eax
0x18001096b  jz      short loc_180010985
0x18001096d  mov     rax, [rbx+50h]
0x180010971  lea     rcx, [rbx+50h]
0x180010975  mov     rax, [rax+8]
0x180010979  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001097e  nop
0x18001097f  add     rsp, 20h
0x180010983  pop     rbx
0x180010984  retn
0x180010985  call    cs:__imp_GetLastError
0x18001098b  jmp     short loc_18001096D
```
