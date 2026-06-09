# ___vcrt_uninitialize_locks

- ea: `0x40d8f6`
- end: `0x40d925`
- name: `___vcrt_uninitialize_locks`
- size: `47`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x40d4af`
- `0x40d4ce`
- `0x40d8ba`

## callees

- `0x40d8f6`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x40d90c`
- `KERNEL32!DeleteCriticalSection` at `0x40d90c`

## pseudocode

```c
char __vcrt_uninitialize_locks()
{
  int v0; // esi
  struct _RTL_CRITICAL_SECTION *v1; // edi

  v0 = dword_417D5C;
  if ( dword_417D5C )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)&dword_417D2C[6 * dword_417D5C];
    do
    {
      DeleteCriticalSection(v1);
      --dword_417D5C;
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
0x40d8f6  push    esi
0x40d8f7  mov     esi, dword_417D5C
0x40d8fd  test    esi, esi
0x40d8ff  jz      short loc_40D921
0x40d901  imul    eax, esi, 18h
0x40d904  push    edi
0x40d905  lea     edi, dword_417D2C[eax]
0x40d90b  push    edi; lpCriticalSection
0x40d90c  call    ds:DeleteCriticalSection
0x40d912  dec     dword_417D5C
0x40d918  sub     edi, 18h
0x40d91b  sub     esi, 1
0x40d91e  jnz     short loc_40D90B
0x40d920  pop     edi
0x40d921  mov     al, 1
0x40d923  pop     esi
0x40d924  retn
```
