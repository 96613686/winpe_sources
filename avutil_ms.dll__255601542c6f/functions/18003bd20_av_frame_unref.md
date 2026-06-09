# av_frame_unref

- ea: `0x18003bd20`
- end: `0x18003bdfb`
- name: `av_frame_unref`
- size: `219`
- prototype: ``
- caller_count: `9`
- callee_count: `8`
- tags: `authz_impersonation`

## callers

- `0x180033aa0`
- `0x18003b220`
- `0x18003b2f0`
- `0x18003b520`
- `0x18003b7d0`
- `0x18003ba10`
- `0x18003c30c`
- `0x18003c57c`
- `0x18003f740`

## callees

- `0x18002f210`
- `0x180033080`
- `0x180035db0`
- `0x18003bd20`
- `0x18003c4e8`
- `0x1800449d0`
- `0x18004e230`
- `0x180050ab0`

## pseudocode

```c
__int64 __fastcall av_frame_unref(__int64 a1)
{
  int v2; // edi
  unsigned int i; // esi
  __int64 result; // rax

  if ( a1 )
  {
    v2 = 0;
    av_frame_side_data_free((_QWORD *)(a1 + 264), (_DWORD *)(a1 + 272));
    for ( i = 0; i < 8; ++i )
      av_buffer_unref((_QWORD *)(a1 + 8 * ((int)i + 23LL)));
    if ( *(int *)(a1 + 256) > 0 )
    {
      do
        av_buffer_unref((_QWORD *)(*(_QWORD *)(a1 + 248) + 8LL * v2++));
      while ( v2 < *(_DWORD *)(a1 + 256) );
    }
    av_freep((__m128i *)(a1 + 248));
    av_dict_free(a1 + 312);
    av_buffer_unref((_QWORD *)(a1 + 328));
    av_buffer_unref((_QWORD *)(a1 + 336));
    av_refstruct_unref(a1 + 376);
    if ( *(_QWORD *)(a1 + 96) != a1 )
      av_freep((__m128i *)(a1 + 96));
    av_channel_layout_uninit(a1 + 384);
    return sub_18003C4E8(a1);
  }
  return result;
}

```

## disassembly

```asm
0x18003bd20  test    rcx, rcx
0x18003bd23  jz      locret_18003BDFA
0x18003bd29  mov     [rsp+arg_0], rbx
0x18003bd2e  mov     [rsp+arg_8], rsi
0x18003bd33  push    rdi
0x18003bd34  sub     rsp, 20h
0x18003bd38  mov     rbx, rcx
0x18003bd3b  lea     rdx, [rcx+110h]
0x18003bd42  add     rcx, 108h
0x18003bd49  xor     edi, edi
0x18003bd4b  call    av_frame_side_data_free
0x18003bd50  mov     esi, edi
0x18003bd52  movsxd  rax, esi
0x18003bd55  add     rax, 17h
0x18003bd59  lea     rcx, [rbx+rax*8]
0x18003bd5d  call    av_buffer_unref
0x18003bd62  inc     esi
0x18003bd64  cmp     esi, 8
0x18003bd67  jb      short loc_18003BD52
0x18003bd69  lea     rsi, [rbx+0F8h]
0x18003bd70  cmp     [rbx+100h], edi
0x18003bd76  jle     short loc_18003BD91
0x18003bd78  mov     rax, [rsi]
0x18003bd7b  movsxd  rdx, edi
0x18003bd7e  lea     rcx, [rax+rdx*8]
0x18003bd82  call    av_buffer_unref
0x18003bd87  inc     edi
0x18003bd89  cmp     edi, [rbx+100h]
0x18003bd8f  jl      short loc_18003BD78
0x18003bd91  mov     rcx, rsi
0x18003bd94  call    av_freep
0x18003bd99  lea     rcx, [rbx+138h]
0x18003bda0  call    av_dict_free
0x18003bda5  lea     rcx, [rbx+148h]
0x18003bdac  call    av_buffer_unref
0x18003bdb1  lea     rcx, [rbx+150h]
0x18003bdb8  call    av_buffer_unref
0x18003bdbd  lea     rcx, [rbx+178h]
0x18003bdc4  call    av_refstruct_unref
0x18003bdc9  lea     rcx, [rbx+60h]
0x18003bdcd  cmp     [rcx], rbx
0x18003bdd0  jz      short loc_18003BDD7
0x18003bdd2  call    av_freep
0x18003bdd7  lea     rcx, [rbx+180h]
0x18003bdde  call    av_channel_layout_uninit
0x18003bde3  mov     rcx, rbx
0x18003bde6  call    sub_18003C4E8
0x18003bdeb  mov     rbx, [rsp+28h+arg_0]
0x18003bdf0  mov     rsi, [rsp+28h+arg_8]
0x18003bdf5  add     rsp, 20h
0x18003bdf9  pop     rdi
0x18003bdfa  retn
```
