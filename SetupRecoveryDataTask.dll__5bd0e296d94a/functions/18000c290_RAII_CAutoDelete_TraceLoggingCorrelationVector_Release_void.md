# RAII::CAutoDelete<TraceLoggingCorrelationVector *>::Release(void)

- ea: `0x18000c290`
- end: `0x18000c2b6`
- name: `?Release@?$CAutoDelete@PEAVTraceLoggingCorrelationVector@@@RAII@@UEAAXXZ`
- size: `38`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x18000c290`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000c2a2`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000c2a2`

## pseudocode

```c
void __fastcall RAII::CAutoDelete<TraceLoggingCorrelationVector *>::Release(__int64 a1)
{
  void *v2; // rcx

  v2 = *(void **)(a1 + 8);
  if ( v2 )
  {
    operator delete(v2);
    *(_QWORD *)(a1 + 8) = 0;
  }
}

```

## disassembly

```asm
0x18000c290  push    rbx
0x18000c292  sub     rsp, 20h
0x18000c296  mov     rbx, rcx
0x18000c299  mov     rcx, [rcx+8]
0x18000c29d  test    rcx, rcx
0x18000c2a0  jz      short loc_18000C2B0
0x18000c2a2  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000c2a8  mov     qword ptr [rbx+8], 0
0x18000c2b0  add     rsp, 20h
0x18000c2b4  pop     rbx
0x18000c2b5  retn
```
