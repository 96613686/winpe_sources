# ___vcrt_uninitialize_locks

- ea: `0x40ea26`
- end: `0x40ea55`
- name: `___vcrt_uninitialize_locks`
- size: `47`
- prototype: `char()`
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x40e4f4`
- `0x40e513`
- `0x40e9ea`

## callees

- `0x40ea26`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x40ea3c`
- `KERNEL32!DeleteCriticalSection` at `0x40ea3c`

## pseudocode

```c
char __vcrt_uninitialize_locks()
{
  int v0; // esi
  struct _RTL_CRITICAL_SECTION *v1; // edi

  v0 = dword_43E064;
  if ( dword_43E064 )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)&dword_43E034[6 * dword_43E064];
    do
    {
      DeleteCriticalSection(v1);
      --dword_43E064;
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
0x40ea26  push    esi
0x40ea27  mov     esi, dword_43E064
0x40ea2d  test    esi, esi
0x40ea2f  jz      short loc_40EA51
0x40ea31  imul    eax, esi, 18h
0x40ea34  push    edi
0x40ea35  lea     edi, dword_43E034[eax]
0x40ea3b  push    edi; lpCriticalSection
0x40ea3c  call    ds:DeleteCriticalSection
0x40ea42  dec     dword_43E064
0x40ea48  sub     edi, 18h
0x40ea4b  sub     esi, 1
0x40ea4e  jnz     short loc_40EA3B
0x40ea50  pop     edi
0x40ea51  mov     al, 1
0x40ea53  pop     esi
0x40ea54  retn
```
