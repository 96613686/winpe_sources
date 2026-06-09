# RAII::CAutoDelete<TraceLoggingCorrelationVector *>::`vector deleting destructor'(uint)

- ea: `0x180004150`
- end: `0x18000419d`
- name: `??_E?$CAutoDelete@PEAVTraceLoggingCorrelationVector@@@RAII@@UEAAPEAXI@Z`
- size: `77`
- prototype: ``
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180004150`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004172`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004189`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004172`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004189`

## pseudocode

```c
_QWORD *__fastcall RAII::CAutoDelete<TraceLoggingCorrelationVector *>::`vector deleting destructor'(
        _QWORD *a1,
        char a2)
{
  void *v4; // rcx

  *a1 = &RAII::CAutoDelete<TraceLoggingCorrelationVector *>::`vftable';
  v4 = (void *)a1[1];
  if ( v4 )
  {
    operator delete(v4);
    a1[1] = 0;
  }
  if ( (a2 & 1) != 0 )
    operator delete(a1);
  return a1;
}

```

## disassembly

```asm
0x180004150  mov     [rsp+arg_0], rbx
0x180004155  push    rdi
0x180004156  sub     rsp, 20h
0x18000415a  lea     rax, ??_7?$CAutoDelete@PEAVTraceLoggingCorrelationVector@@@RAII@@6B@; const RAII::CAutoDelete<TraceLoggingCorrelationVector *>::`vftable'
0x180004161  mov     rbx, rcx
0x180004164  mov     [rcx], rax
0x180004167  mov     edi, edx
0x180004169  mov     rcx, [rcx+8]
0x18000416d  test    rcx, rcx
0x180004170  jz      short loc_180004180
0x180004172  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004178  mov     qword ptr [rbx+8], 0
0x180004180  test    dil, 1
0x180004184  jz      short loc_18000418F
0x180004186  mov     rcx, rbx
0x180004189  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000418f  mov     rax, rbx
0x180004192  mov     rbx, [rsp+28h+arg_0]
0x180004197  add     rsp, 20h
0x18000419b  pop     rdi
0x18000419c  retn
```
