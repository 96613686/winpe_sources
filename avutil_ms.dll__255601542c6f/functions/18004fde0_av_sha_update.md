# av_sha_update

- ea: `0x18004fde0`
- end: `0x18004fe56`
- name: `av_sha_update`
- size: `118`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18003ccd0`
- `0x18003f070`
- `0x18004d3d8`
- `0x18004fc60`

## callees

- `0x18004fde0`
- `0x18007a900`

## pseudocode

```c
char __fastcall av_sha_update(__int64 a1, __int64 a2, unsigned __int64 a3)
{
  int v3; // r9d
  unsigned __int64 v4; // rbx
  __int64 v5; // r9
  char result; // al

  v3 = *(_DWORD *)(a1 + 8);
  v4 = 0;
  *(_QWORD *)(a1 + 8) += a3;
  v5 = v3 & 0x3F;
  if ( a3 )
  {
    do
    {
      result = *(_BYTE *)(a2 + v4);
      *(_BYTE *)(v5 + a1 + 16) = result;
      v5 = (unsigned int)(v5 + 1);
      if ( (_DWORD)v5 == 64 )
      {
        result = (*(__int64 (__fastcall **)(__int64, __int64))(a1 + 112))(a1 + 80, a1 + 16);
        v5 = 0;
      }
      ++v4;
    }
    while ( v4 < a3 );
  }
  return result;
}

```

## disassembly

```asm
0x18004fde0  mov     [rsp+arg_0], rbx
0x18004fde5  mov     [rsp+arg_8], rsi
0x18004fdea  mov     [rsp+arg_10], rdi
0x18004fdef  push    r14
0x18004fdf1  sub     rsp, 20h
0x18004fdf5  mov     r9d, [rcx+8]
0x18004fdf9  xor     ebx, ebx
0x18004fdfb  add     [rcx+8], r8
0x18004fdff  and     r9d, 3Fh
0x18004fe03  mov     rsi, r8
0x18004fe06  mov     r14, rdx
0x18004fe09  mov     rdi, rcx
0x18004fe0c  test    r8, r8
0x18004fe0f  jz      short loc_18004FE40
0x18004fe11  mov     al, [r14+rbx]
0x18004fe15  mov     [r9+rdi+10h], al
0x18004fe1a  inc     r9d
0x18004fe1d  cmp     r9d, 40h ; '@'
0x18004fe21  jnz     short loc_18004FE38
0x18004fe23  mov     rax, [rdi+70h]
0x18004fe27  lea     rdx, [rdi+10h]
0x18004fe2b  lea     rcx, [rdi+50h]
0x18004fe2f  call    cs:__guard_dispatch_icall_fptr
0x18004fe35  xor     r9d, r9d
0x18004fe38  inc     rbx
0x18004fe3b  cmp     rbx, rsi
0x18004fe3e  jb      short loc_18004FE11
0x18004fe40  mov     rbx, [rsp+28h+arg_0]
0x18004fe45  mov     rsi, [rsp+28h+arg_8]
0x18004fe4a  mov     rdi, [rsp+28h+arg_10]
0x18004fe4f  add     rsp, 20h
0x18004fe53  pop     r14
0x18004fe55  retn
```
