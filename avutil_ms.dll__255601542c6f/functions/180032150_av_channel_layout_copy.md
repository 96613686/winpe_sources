# av_channel_layout_copy

- ea: `0x180032150`
- end: `0x1800321b9`
- name: `av_channel_layout_copy`
- size: `105`
- prototype: ``
- caller_count: `6`
- callee_count: `4`
- tags: ``

## callers

- `0x18003b520`
- `0x18003b7d0`
- `0x18003ba10`
- `0x1800460b0`
- `0x1800476a0`
- `0x180048c50`

## callees

- `0x180032150`
- `0x180033080`
- `0x180044a70`
- `0x18007a960`

## pseudocode

```c
__int64 __fastcall av_channel_layout_copy(__int64 a1, __int64 a2)
{
  __m128i *v4; // rax

  av_channel_layout_uninit();
  *(_OWORD *)a1 = *(_OWORD *)a2;
  *(_QWORD *)(a1 + 16) = *(_QWORD *)(a2 + 16);
  if ( *(_DWORD *)a2 == 2 )
  {
    v4 = (__m128i *)av_malloc_array(*(int *)(a2 + 4), 32);
    *(_QWORD *)(a1 + 8) = v4;
    if ( !v4 )
      return 4294967284LL;
    sub_18007A960(v4, *(const __m128i **)(a2 + 8), 32LL * *(int *)(a2 + 4));
  }
  return 0;
}

```

## disassembly

```asm
0x180032150  mov     [rsp+arg_0], rbx
0x180032155  push    rdi
0x180032156  sub     rsp, 20h
0x18003215a  mov     rbx, rdx
0x18003215d  mov     rdi, rcx
0x180032160  call    av_channel_layout_uninit
0x180032165  movups  xmm0, xmmword ptr [rbx]
0x180032168  movups  xmmword ptr [rdi], xmm0
0x18003216b  movsd   xmm1, qword ptr [rbx+10h]
0x180032170  movsd   qword ptr [rdi+10h], xmm1
0x180032175  cmp     dword ptr [rbx], 2
0x180032178  jnz     short loc_1800321AC
0x18003217a  movsxd  rcx, dword ptr [rbx+4]
0x18003217e  mov     edx, 20h ; ' '
0x180032183  call    av_malloc_array
0x180032188  mov     [rdi+8], rax
0x18003218c  test    rax, rax
0x18003218f  jnz     short loc_180032198
0x180032191  mov     eax, 0FFFFFFF4h
0x180032196  jmp     short loc_1800321AE
0x180032198  movsxd  r8, dword ptr [rbx+4]
0x18003219c  mov     rcx, rax
0x18003219f  mov     rdx, [rbx+8]
0x1800321a3  shl     r8, 5
0x1800321a7  call    sub_18007A960
0x1800321ac  xor     eax, eax
0x1800321ae  mov     rbx, [rsp+28h+arg_0]
0x1800321b3  add     rsp, 20h
0x1800321b7  pop     rdi
0x1800321b8  retn
```
