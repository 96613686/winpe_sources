# av_ripemd_update

- ea: `0x18004e580`
- end: `0x18004e5f6`
- name: `av_ripemd_update`
- size: `118`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `installer_update`

## callers

- `0x18003ccd0`
- `0x18004e440`

## callees

- `0x18004e580`
- `0x18007a900`

## pseudocode

```c
char __fastcall av_ripemd_update(__int64 a1, __int64 a2, unsigned __int64 a3)
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
        result = (*(__int64 (__fastcall **)(__int64, __int64))(a1 + 120))(a1 + 80, a1 + 16);
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
0x18004e580  mov     [rsp+arg_0], rbx
0x18004e585  mov     [rsp+arg_8], rsi
0x18004e58a  mov     [rsp+arg_10], rdi
0x18004e58f  push    r14
0x18004e591  sub     rsp, 20h
0x18004e595  mov     r9d, [rcx+8]
0x18004e599  xor     ebx, ebx
0x18004e59b  add     [rcx+8], r8
0x18004e59f  and     r9d, 3Fh
0x18004e5a3  mov     rsi, r8
0x18004e5a6  mov     r14, rdx
0x18004e5a9  mov     rdi, rcx
0x18004e5ac  test    r8, r8
0x18004e5af  jz      short loc_18004E5E0
0x18004e5b1  mov     al, [r14+rbx]
0x18004e5b5  mov     [r9+rdi+10h], al
0x18004e5ba  inc     r9d
0x18004e5bd  cmp     r9d, 40h ; '@'
0x18004e5c1  jnz     short loc_18004E5D8
0x18004e5c3  mov     rax, [rdi+78h]
0x18004e5c7  lea     rdx, [rdi+10h]
0x18004e5cb  lea     rcx, [rdi+50h]
0x18004e5cf  call    cs:__guard_dispatch_icall_fptr
0x18004e5d5  xor     r9d, r9d
0x18004e5d8  inc     rbx
0x18004e5db  cmp     rbx, rsi
0x18004e5de  jb      short loc_18004E5B1
0x18004e5e0  mov     rbx, [rsp+28h+arg_0]
0x18004e5e5  mov     rsi, [rsp+28h+arg_8]
0x18004e5ea  mov     rdi, [rsp+28h+arg_10]
0x18004e5ef  add     rsp, 20h
0x18004e5f3  pop     r14
0x18004e5f5  retn
```
