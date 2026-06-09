# av_frame_copy

- ea: `0x18003b270`
- end: `0x18003b2d2`
- name: `av_frame_copy`
- size: `98`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x18003b520`
- `0x18003b7d0`

## callees

- `0x180031f10`
- `0x18003b270`
- `0x18003bf24`
- `0x18003c258`

## pseudocode

```c
__int64 __fastcall av_frame_copy(int *a1, __int64 a2)
{
  int v2; // eax

  v2 = a1[29];
  if ( v2 != *(_DWORD *)(a2 + 116) || v2 < 0 )
    return 4294967274LL;
  if ( a1[26] > 0 && a1[27] > 0 )
    return sub_18003C258();
  if ( a1[28] > 0 && (unsigned int)av_channel_layout_check(a1 + 96) )
    return sub_18003BF24(a1, a2);
  else
    return 4294967274LL;
}

```

## disassembly

```asm
0x18003b270  mov     [rsp+arg_0], rbx
0x18003b275  push    rdi
0x18003b276  sub     rsp, 20h
0x18003b27a  mov     eax, [rcx+74h]
0x18003b27d  mov     rdi, rdx
0x18003b280  mov     rbx, rcx
0x18003b283  cmp     eax, [rdx+74h]
0x18003b286  jnz     short loc_18003B2C2
0x18003b288  test    eax, eax
0x18003b28a  js      short loc_18003B2C2
0x18003b28c  cmp     dword ptr [rcx+68h], 0
0x18003b290  jle     short loc_18003B29F
0x18003b292  cmp     dword ptr [rcx+6Ch], 0
0x18003b296  jle     short loc_18003B29F
0x18003b298  call    sub_18003C258
0x18003b29d  jmp     short loc_18003B2C7
0x18003b29f  cmp     dword ptr [rcx+70h], 0
0x18003b2a3  jle     short loc_18003B2C2
0x18003b2a5  add     rcx, 180h
0x18003b2ac  call    av_channel_layout_check
0x18003b2b1  test    eax, eax
0x18003b2b3  jz      short loc_18003B2C2
0x18003b2b5  mov     rdx, rdi
0x18003b2b8  mov     rcx, rbx
0x18003b2bb  call    sub_18003BF24
0x18003b2c0  jmp     short loc_18003B2C7
0x18003b2c2  mov     eax, 0FFFFFFEAh
0x18003b2c7  mov     rbx, [rsp+28h+arg_0]
0x18003b2cc  add     rsp, 20h
0x18003b2d0  pop     rdi
0x18003b2d1  retn
```
