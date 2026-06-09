# CWbemVssWriter::~CWbemVssWriter(void)

- ea: `0x180016c90`
- end: `0x180016cec`
- name: `??1CWbemVssWriter@@UEAA@XZ`
- size: `92`
- prototype: `void __fastcall(CWbemVssWriter *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x180016d40`

## callees

- `0x180016c44`
- `0x180016c90`
- `0x180020010`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016cd8`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180016cd8`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall CWbemVssWriter::~CWbemVssWriter(CWbemVssWriter *this)
{
  __int64 v2; // rcx

  *(_QWORD *)this = &CWbemVssWriter::`vftable';
  v2 = *((_QWORD *)this + 2);
  if ( v2 )
  {
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 48LL))(v2);
    (*(void (__fastcall **)(_QWORD))(**((_QWORD **)this + 2) + 16LL))(*((_QWORD *)this + 2));
    *((_QWORD *)this + 2) = 0;
  }
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 24));
  CVssWriter::~CVssWriter(this);
}

```

## disassembly

```asm
0x180016c90  mov     [rsp+arg_0], rcx
0x180016c95  push    rbx
0x180016c96  sub     rsp, 20h
0x180016c9a  mov     rbx, rcx
0x180016c9d  lea     rax, ??_7CWbemVssWriter@@6B@; const CWbemVssWriter::`vftable'
0x180016ca4  mov     [rcx], rax
0x180016ca7  mov     rcx, [rcx+10h]
0x180016cab  test    rcx, rcx
0x180016cae  jz      short loc_180016CD4
0x180016cb0  mov     rax, [rcx]
0x180016cb3  mov     rax, [rax+30h]
0x180016cb7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016cbc  mov     rcx, [rbx+10h]
0x180016cc0  mov     rax, [rcx]
0x180016cc3  mov     rax, [rax+10h]
0x180016cc7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016ccc  mov     qword ptr [rbx+10h], 0
0x180016cd4  lea     rcx, [rbx+18h]; lpCriticalSection
0x180016cd8  call    cs:__imp_DeleteCriticalSection
0x180016cde  nop
0x180016cdf  mov     rcx, rbx; this
0x180016ce2  add     rsp, 20h
0x180016ce6  pop     rbx
0x180016ce7  jmp     ??1CVssWriter@@UEAA@XZ; CVssWriter::~CVssWriter(void)
```
