# ___acrt_uninitialize_locks

- ea: `0x10018c21`
- end: `0x10018c52`
- name: `___acrt_uninitialize_locks`
- size: `49`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x10018bc9`

## callees

- `0x10018c21`

## import_xrefs

- `KERNEL32!DeleteCriticalSection` at `0x10018c39`
- `KERNEL32!DeleteCriticalSection` at `0x10018c39`

## pseudocode

```c
char __acrt_uninitialize_locks()
{
  int v0; // esi
  struct _RTL_CRITICAL_SECTION *v1; // edi

  v0 = dword_10035288;
  if ( dword_10035288 )
  {
    v1 = (struct _RTL_CRITICAL_SECTION *)&dword_10035120[6 * dword_10035288];
    do
    {
      DeleteCriticalSection(v1);
      --dword_10035288;
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
0x10018c21  mov     edi, edi
0x10018c23  push    esi
0x10018c24  mov     esi, dword_10035288
0x10018c2a  test    esi, esi
0x10018c2c  jz      short loc_10018C4E
0x10018c2e  imul    eax, esi, 18h
0x10018c31  push    edi
0x10018c32  lea     edi, dword_10035120[eax]
0x10018c38  push    edi; lpCriticalSection
0x10018c39  call    ds:DeleteCriticalSection
0x10018c3f  dec     dword_10035288
0x10018c45  sub     edi, 18h
0x10018c48  sub     esi, 1
0x10018c4b  jnz     short loc_10018C38
0x10018c4d  pop     edi
0x10018c4e  mov     al, 1
0x10018c50  pop     esi
0x10018c51  retn
```
