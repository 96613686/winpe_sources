# ___vcrt_uninitialize_locks_0

- ea: `0x410230`
- end: `0x410261`
- name: `___vcrt_uninitialize_locks_0`
- size: `49`
- prototype: `char()`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x4101d0`

## callees

- `0x410230`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x410248`
- `KERNEL32!DeleteCriticalSection` at `0x410248`

## pseudocode

```c
char __vcrt_uninitialize_locks_0()
{
  int v0; // esi
  struct _RTL_CRITICAL_SECTION *v1; // edi

  v0 = dword_427010;
  if ( dword_427010 )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)&dword_426EA8[6 * dword_427010];
    do
    {
      DeleteCriticalSection(v1);
      --dword_427010;
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
0x410230  mov     edi, edi
0x410232  push    esi
0x410233  mov     esi, dword_427010
0x410239  test    esi, esi
0x41023b  jz      short loc_41025D
0x41023d  imul    eax, esi, 18h
0x410240  push    edi
0x410241  lea     edi, dword_426EA8[eax]
0x410247  push    edi; lpCriticalSection
0x410248  call    ds:DeleteCriticalSection
0x41024e  dec     dword_427010
0x410254  sub     edi, 18h
0x410257  sub     esi, 1
0x41025a  jnz     short loc_410247
0x41025c  pop     edi
0x41025d  mov     al, 1
0x41025f  pop     esi
0x410260  retn
```
