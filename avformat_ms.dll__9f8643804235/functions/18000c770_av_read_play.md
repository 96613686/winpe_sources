# av_read_play

- ea: `0x18000c770`
- end: `0x18000c79a`
- name: `av_read_play`
- size: `42`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004430`
- `0x18000c770`
- `0x18001d6e0`

## pseudocode

```c
__int64 __fastcall av_read_play(__int64 a1)
{
  __int64 (*v1)(void); // rax
  __int64 v3; // rcx

  v1 = *(__int64 (**)(void))(*(_QWORD *)(a1 + 8) + 120LL);
  if ( v1 )
    return v1();
  v3 = *(_QWORD *)(a1 + 32);
  if ( v3 )
    return avio_pause(v3, 0);
  else
    return 4294967256LL;
}

```

## disassembly

```asm
0x18000c770  mov     rax, [rcx+8]
0x18000c774  mov     rax, [rax+78h]
0x18000c778  test    rax, rax
0x18000c77b  jz      short loc_18000C784
0x18000c77d  jmp     cs:__guard_dispatch_icall_fptr
0x18000c784  mov     rcx, [rcx+20h]
0x18000c788  test    rcx, rcx
0x18000c78b  jz      short loc_18000C794
0x18000c78d  xor     edx, edx
0x18000c78f  jmp     avio_pause
0x18000c794  mov     eax, 0FFFFFFD8h
0x18000c799  retn
```
