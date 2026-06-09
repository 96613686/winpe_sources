# av_interleaved_write_frame

- ea: `0x180012150`
- end: `0x1800121b7`
- name: `av_interleaved_write_frame`
- size: `103`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800144ac`

## callees

- `0x180012150`
- `0x180013d48`
- `0x180014244`
- `0x18001b9f6`
- `0x18001bb58`

## string_xrefs

- `0x180012185`: `av_interleaved_write_frame FLUSH\n`

## pseudocode

```c
__int64 __fastcall av_interleaved_write_frame(__int64 a1, __int64 a2)
{
  int v4; // edi

  if ( a2 )
  {
    v4 = sub_180014244(a1, a2, 1);
    if ( v4 < 0 )
    {
      _mm_lfence();
      av_packet_unref(a2);
    }
    return (unsigned int)v4;
  }
  else
  {
    av_log(a1, 56, "av_interleaved_write_frame FLUSH\n");
    return sub_180013D48(a1, *(_QWORD *)(a1 + 504), 1);
  }
}

```

## disassembly

```asm
0x180012150  mov     [rsp+arg_0], rbx
0x180012155  push    rdi
0x180012156  sub     rsp, 20h
0x18001215a  mov     rbx, rdx
0x18001215d  mov     rdi, rcx
0x180012160  test    rdx, rdx
0x180012163  jz      short loc_180012185
0x180012165  mov     r8d, 1
0x18001216b  call    sub_180014244
0x180012170  mov     edi, eax
0x180012172  test    eax, eax
0x180012174  jns     short loc_180012181
0x180012176  lfence
0x180012179  mov     rcx, rbx
0x18001217c  call    av_packet_unref
0x180012181  mov     eax, edi
0x180012183  jmp     short loc_1800121AC
0x180012185  lea     r8, aAvInterleavedW_1; "av_interleaved_write_frame FLUSH\n"
0x18001218c  mov     edx, 38h ; '8'
0x180012191  call    av_log
0x180012196  mov     rdx, [rdi+1F8h]
0x18001219d  xor     r9d, r9d
0x1800121a0  mov     rcx, rdi
0x1800121a3  lea     r8d, [r9+1]
0x1800121a7  call    sub_180013D48
0x1800121ac  mov     rbx, [rsp+28h+arg_0]
0x1800121b1  add     rsp, 20h
0x1800121b5  pop     rdi
0x1800121b6  retn
```
