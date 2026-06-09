# RAII::CAutoDelete<TraceLoggingCorrelationVector *>::`vector deleting destructor'(uint)

- ea: `0x18000c0e0`
- end: `0x18000c12d`
- name: `??_E?$CAutoDelete@PEAVTraceLoggingCorrelationVector@@@RAII@@UEAAPEAXI@Z`
- size: `77`
- prototype: `_QWORD *__fastcall(_QWORD *, char)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000c0e0`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c102`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c119`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c102`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c119`

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
0x18000c0e0  mov     [rsp+arg_0], rbx
0x18000c0e5  push    rdi
0x18000c0e6  sub     rsp, 20h
0x18000c0ea  lea     rax, ??_7?$CAutoDelete@PEAVTraceLoggingCorrelationVector@@@RAII@@6B@; const RAII::CAutoDelete<TraceLoggingCorrelationVector *>::`vftable'
0x18000c0f1  mov     rbx, rcx
0x18000c0f4  mov     [rcx], rax
0x18000c0f7  mov     edi, edx
0x18000c0f9  mov     rcx, [rcx+8]
0x18000c0fd  test    rcx, rcx
0x18000c100  jz      short loc_18000C110
0x18000c102  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c108  mov     qword ptr [rbx+8], 0
0x18000c110  test    dil, 1
0x18000c114  jz      short loc_18000C11F
0x18000c116  mov     rcx, rbx
0x18000c119  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c11f  mov     rax, rbx
0x18000c122  mov     rbx, [rsp+28h+arg_0]
0x18000c127  add     rsp, 20h
0x18000c12b  pop     rdi
0x18000c12c  retn
```
