# ___vcrt_uninitialize_locks_0

- ea: `0x40fd60`
- end: `0x40fd91`
- name: `___vcrt_uninitialize_locks_0`
- size: `49`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x40fd00`

## callees

- `0x40fd60`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x40fd78`
- `KERNEL32!DeleteCriticalSection` at `0x40fd78`

## pseudocode

```c
char __vcrt_uninitialize_locks_0()
{
  int v0; // esi
  struct _RTL_CRITICAL_SECTION *v1; // edi

  v0 = dword_418178;
  if ( dword_418178 )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)(&stru_418008._end + 6 * dword_418178);
    do
    {
      DeleteCriticalSection(v1);
      --dword_418178;
      --v1;
      --v0;
    }
    while ( v0 );
  }
  return 1;
}

```

## disassembly

```asm
0x40fd60  mov     edi, edi
0x40fd62  push    esi
0x40fd63  mov     esi, dword_418178
0x40fd69  test    esi, esi
0x40fd6b  jz      short loc_40FD8D
0x40fd6d  imul    eax, esi, 18h
0x40fd70  push    edi
0x40fd71  lea     edi, stru_418008._end[eax]
0x40fd77  push    edi; lpCriticalSection
0x40fd78  call    ds:DeleteCriticalSection
0x40fd7e  dec     dword_418178
0x40fd84  sub     edi, 18h
0x40fd87  sub     esi, 1
0x40fd8a  jnz     short loc_40FD77
0x40fd8c  pop     edi
0x40fd8d  mov     al, 1
0x40fd8f  pop     esi
0x40fd90  retn
```
