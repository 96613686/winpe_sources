# Em_AmrNB_Dec_sGsmAmrDelete

- ea: `0x180004720`
- end: `0x180004749`
- name: `Em_AmrNB_Dec_sGsmAmrDelete`
- size: `41`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: ``

## callees

- `0x180001f36`
- `0x180004720`

## pseudocode

```c
void __fastcall Em_AmrNB_Dec_sGsmAmrDelete(_QWORD *Block)
{
  void *v2; // rcx

  if ( Block )
  {
    v2 = (void *)Block[5];
    if ( v2 )
      free(v2);
    free(Block);
  }
}

```

## disassembly

```asm
0x180004720  test    rcx, rcx
0x180004723  jz      short locret_180004748
0x180004725  push    rbx
0x180004726  sub     rsp, 20h
0x18000472a  mov     rbx, rcx
0x18000472d  mov     rcx, [rcx+28h]; Block
0x180004731  test    rcx, rcx
0x180004734  jz      short loc_18000473B
0x180004736  call    free
0x18000473b  mov     rcx, rbx; Block
0x18000473e  call    free
0x180004743  add     rsp, 20h
0x180004747  pop     rbx
0x180004748  retn
```
