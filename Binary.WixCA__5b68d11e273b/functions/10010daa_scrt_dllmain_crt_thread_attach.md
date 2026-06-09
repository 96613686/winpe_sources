# ___scrt_dllmain_crt_thread_attach

- ea: `0x10010daa`
- end: `0x10010dc9`
- name: `___scrt_dllmain_crt_thread_attach`
- size: `31`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `loader_planting`

## callers

- `0x10010731`

## callees

- `0x10010daa`
- `0x10012513`
- `0x1001251e`
- `0x10016b61`

## pseudocode

```c
char __scrt_dllmain_crt_thread_attach()
{
  if ( !__vcrt_thread_attach() )
    return 0;
  if ( !__acrt_thread_attach() )
  {
    __vcrt_thread_detach();
    return 0;
  }
  return 1;
}

```

## disassembly

```asm
0x10010daa  call    ___vcrt_thread_attach
0x10010daf  test    al, al
0x10010db1  jnz     short loc_10010DB6
0x10010db3  xor     al, al
0x10010db5  retn
0x10010db6  call    ___acrt_thread_attach
0x10010dbb  test    al, al
0x10010dbd  jnz     short loc_10010DC6
0x10010dbf  call    ___vcrt_thread_detach
0x10010dc4  jmp     short loc_10010DB3
0x10010dc6  mov     al, 1
0x10010dc8  retn
```
