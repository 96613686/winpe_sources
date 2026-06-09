# RAII::CAutoDelete<TraceLoggingCorrelationVector *>::Release(void)

- ea: `0x180004300`
- end: `0x180004326`
- name: `?Release@?$CAutoDelete@PEAVTraceLoggingCorrelationVector@@@RAII@@UEAAXXZ`
- size: `38`
- prototype: `void __fastcall(__int64)`
- caller_count: `0`
- callee_count: `1`
- tags: `file_ops`

## callees

- `0x180004300`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180004312`
- `msvcrt!??3@YAXPEAX@Z` at `0x180004312`

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
0x180004300  push    rbx
0x180004302  sub     rsp, 20h
0x180004306  mov     rbx, rcx
0x180004309  mov     rcx, [rcx+8]
0x18000430d  test    rcx, rcx
0x180004310  jz      short loc_180004320
0x180004312  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x180004318  mov     qword ptr [rbx+8], 0
0x180004320  add     rsp, 20h
0x180004324  pop     rbx
0x180004325  retn
```
