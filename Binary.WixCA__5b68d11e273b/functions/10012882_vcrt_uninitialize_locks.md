# ___vcrt_uninitialize_locks

- ea: `0x10012882`
- end: `0x100128b1`
- name: `___vcrt_uninitialize_locks`
- size: `47`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: ``

## callers

- `0x100124ea`
- `0x10012529`
- `0x10012846`

## callees

- `0x10012882`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x10012898`
- `KERNEL32!DeleteCriticalSection` at `0x10012898`

## pseudocode

```c
char __vcrt_uninitialize_locks()
{
  int v0; // esi
  struct _RTL_CRITICAL_SECTION *v1; // edi

  v0 = dword_10034D9C;
  if ( dword_10034D9C )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)&dword_10034D6C[6 * dword_10034D9C];
    do
    {
      DeleteCriticalSection(v1);
      --dword_10034D9C;
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
0x10012882  push    esi
0x10012883  mov     esi, dword_10034D9C
0x10012889  test    esi, esi
0x1001288b  jz      short loc_100128AD
0x1001288d  imul    eax, esi, 18h
0x10012890  push    edi
0x10012891  lea     edi, dword_10034D6C[eax]
0x10012897  push    edi; lpCriticalSection
0x10012898  call    ds:DeleteCriticalSection
0x1001289e  dec     dword_10034D9C
0x100128a4  sub     edi, 18h
0x100128a7  sub     esi, 1
0x100128aa  jnz     short loc_10012897
0x100128ac  pop     edi
0x100128ad  mov     al, 1
0x100128af  pop     esi
0x100128b0  retn
```
