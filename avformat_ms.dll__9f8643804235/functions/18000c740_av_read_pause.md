# av_read_pause

- ea: `0x18000c740`
- end: `0x18000c770`
- name: `av_read_pause`
- size: `48`
- prototype: ``
- caller_count: `0`
- callee_count: `3`
- tags: ``

## callees

- `0x180004430`
- `0x18000c740`
- `0x18001d6e0`

## pseudocode

```c
__int64 __fastcall av_read_pause(__int64 a1)
{
  __int64 (*v1)(void); // rax
  __int64 v3; // rcx

  v1 = *(__int64 (**)(void))(*(_QWORD *)(a1 + 8) + 128LL);
  if ( v1 )
    return v1();
  v3 = *(_QWORD *)(a1 + 32);
  if ( v3 )
    return avio_pause(v3, 1);
  else
    return 4294967256LL;
}

```

## disassembly

```asm
0x18000c740  mov     rax, [rcx+8]
0x18000c744  mov     rax, [rax+80h]
0x18000c74b  test    rax, rax
0x18000c74e  jz      short loc_18000C757
0x18000c750  jmp     cs:__guard_dispatch_icall_fptr
0x18000c757  mov     rcx, [rcx+20h]
0x18000c75b  test    rcx, rcx
0x18000c75e  jz      short loc_18000C76A
0x18000c760  mov     edx, 1
0x18000c765  jmp     avio_pause
0x18000c76a  mov     eax, 0FFFFFFD8h
0x18000c76f  retn
```
