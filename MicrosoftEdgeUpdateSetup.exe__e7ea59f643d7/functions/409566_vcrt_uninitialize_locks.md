# ___vcrt_uninitialize_locks

- ea: `0x409566`
- end: `0x409595`
- name: `___vcrt_uninitialize_locks`
- size: `47`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x408ee1`
- `0x408f00`
- `0x40952a`

## callees

- `0x409566`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x40957c`
- `KERNEL32!DeleteCriticalSection` at `0x40957c`

## pseudocode

```c
char __vcrt_uninitialize_locks()
{
  int v0; // esi
  struct _RTL_CRITICAL_SECTION *v1; // edi

  v0 = dword_426CD0;
  if ( dword_426CD0 )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)&dword_426CA0[6 * dword_426CD0];
    do
    {
      DeleteCriticalSection(v1);
      --dword_426CD0;
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
0x409566  push    esi
0x409567  mov     esi, dword_426CD0
0x40956d  test    esi, esi
0x40956f  jz      short loc_409591
0x409571  imul    eax, esi, 18h
0x409574  push    edi
0x409575  lea     edi, dword_426CA0[eax]
0x40957b  push    edi; lpCriticalSection
0x40957c  call    ds:DeleteCriticalSection
0x409582  dec     dword_426CD0
0x409588  sub     edi, 18h
0x40958b  sub     esi, 1
0x40958e  jnz     short loc_40957B
0x409590  pop     edi
0x409591  mov     al, 1
0x409593  pop     esi
0x409594  retn
```
