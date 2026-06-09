# Em_AmrNB_Dec_gMedian

- ea: `0x180004c4c`
- end: `0x180004d1d`
- name: `Em_AmrNB_Dec_gMedian`
- size: `209`
- prototype: `__int64 __fastcall(void *Src)`
- caller_count: `3`
- callee_count: `3`
- tags: ``

## callers

- `0x180003800`
- `0x180008928`
- `0x180008b18`

## callees

- `0x180001400`
- `0x180004c4c`
- `0x180013811`

## pseudocode

```c
__int64 __fastcall Em_AmrNB_Dec_gMedian(void *Src, __int16 a2)
{
  int v2; // ebx
  __int16 v3; // dx
  __int16 v4; // r9
  __int16 v5; // r10
  unsigned __int16 v6; // di
  unsigned __int16 i; // r8
  __int16 v8; // r11
  __int16 v9; // ax
  __int64 v10; // rax
  _WORD v12[12]; // [rsp+20h] [rbp-28h] BYREF

  v2 = a2;
  if ( a2 > 0 )
    memcpy_0(v12, Src, 2LL * a2);
  v3 = 0;
  if ( v2 / 2 < 0 )
  {
    return v12[0];
  }
  else
  {
    do
    {
      v4 = v3 + 1;
      v5 = v3 + 1;
      v6 = v12[v3];
      for ( i = v6; v5 < (__int16)v2; i = v9 )
      {
        v8 = v5;
        v9 = v12[v5];
        if ( v9 < (__int16)i )
        {
          v9 = i;
          v8 = v3;
        }
        ++v5;
        v3 = v8;
      }
      v10 = v3;
      v3 = v4;
      v12[v10] = v6;
    }
    while ( v4 <= v2 / 2 );
  }
  return i;
}

```

## disassembly

```asm
0x180004c4c  mov     [rsp+arg_0], rbx
0x180004c51  mov     [rsp+arg_8], rsi
0x180004c56  push    rdi
0x180004c57  sub     rsp, 40h
0x180004c5b  mov     rax, cs:__security_cookie
0x180004c62  xor     rax, rsp
0x180004c65  mov     [rsp+48h+var_10], rax
0x180004c6a  movsx   rbx, dx
0x180004c6e  xor     eax, eax
0x180004c70  cmp     ax, bx
0x180004c73  jge     short loc_180004C88
0x180004c75  mov     rdx, rcx; Src
0x180004c78  mov     r8, rbx
0x180004c7b  add     r8, r8; Size
0x180004c7e  lea     rcx, [rsp+48h+var_28]; void *
0x180004c83  call    memcpy_0
0x180004c88  mov     eax, ebx
0x180004c8a  cdq
0x180004c8b  sub     eax, edx
0x180004c8d  mov     edx, 0
0x180004c92  sar     eax, 1
0x180004c94  mov     esi, eax
0x180004c96  js      short loc_180004CF6
0x180004c98  lea     r9d, [rdx+1]
0x180004c9c  movsx   rcx, dx
0x180004ca0  movzx   r10d, r9w
0x180004ca4  movzx   edi, [rsp+rcx*2+48h+var_28]
0x180004ca9  movzx   r8d, di
0x180004cad  cmp     r9w, bx
0x180004cb1  jge     short loc_180004CE3
0x180004cb3  movsx   rax, r10w
0x180004cb7  movzx   r11d, r10w
0x180004cbb  movzx   ecx, [rsp+rax*2+48h+var_28]
0x180004cc0  cmp     cx, r8w
0x180004cc4  movzx   eax, cx
0x180004cc7  cmovl   ax, r8w
0x180004ccc  cmovl   r11w, dx
0x180004cd1  inc     r10w
0x180004cd5  movzx   edx, r11w
0x180004cd9  movzx   r8d, ax
0x180004cdd  cmp     r10w, bx
0x180004ce1  jl      short loc_180004CB3
0x180004ce3  movsx   rax, dx
0x180004ce7  movsx   edx, r9w
0x180004ceb  mov     [rsp+rax*2+48h+var_28], di
0x180004cf0  cmp     edx, esi
0x180004cf2  jle     short loc_180004C98
0x180004cf4  jmp     short loc_180004CFC
0x180004cf6  movzx   r8d, [rsp+48h+var_28]
0x180004cfc  movzx   eax, r8w
0x180004d00  mov     rcx, [rsp+48h+var_10]
0x180004d05  xor     rcx, rsp; StackCookie
0x180004d08  call    __security_check_cookie
0x180004d0d  mov     rbx, [rsp+48h+arg_0]
0x180004d12  mov     rsi, [rsp+48h+arg_8]
0x180004d17  add     rsp, 40h
0x180004d1b  pop     rdi
0x180004d1c  retn
```
