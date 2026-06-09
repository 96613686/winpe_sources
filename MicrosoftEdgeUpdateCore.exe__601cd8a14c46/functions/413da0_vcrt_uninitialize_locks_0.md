# ___vcrt_uninitialize_locks_0

- ea: `0x413da0`
- end: `0x413dd1`
- name: `___vcrt_uninitialize_locks_0`
- size: `49`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x413d40`

## callees

- `0x413da0`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x413db8`
- `KERNEL32!DeleteCriticalSection` at `0x413db8`

## pseudocode

```c
char __vcrt_uninitialize_locks_0()
{
  int v0; // esi
  struct _RTL_CRITICAL_SECTION *v1; // edi

  v0 = dword_43E478;
  if ( dword_43E478 )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)&dword_43E310[6 * dword_43E478];
    do
    {
      DeleteCriticalSection(v1);
      --dword_43E478;
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
0x413da0  mov     edi, edi
0x413da2  push    esi
0x413da3  mov     esi, dword_43E478
0x413da9  test    esi, esi
0x413dab  jz      short loc_413DCD
0x413dad  imul    eax, esi, 18h
0x413db0  push    edi
0x413db1  lea     edi, dword_43E310[eax]
0x413db7  push    edi; lpCriticalSection
0x413db8  call    ds:DeleteCriticalSection
0x413dbe  dec     dword_43E478
0x413dc4  sub     edi, 18h
0x413dc7  sub     esi, 1
0x413dca  jnz     short loc_413DB7
0x413dcc  pop     edi
0x413dcd  mov     al, 1
0x413dcf  pop     esi
0x413dd0  retn
```
