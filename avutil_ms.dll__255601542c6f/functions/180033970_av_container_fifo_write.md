# av_container_fifo_write

- ea: `0x180033970`
- end: `0x1800339f8`
- name: `av_container_fifo_write`
- size: `136`
- prototype: ``
- caller_count: `0`
- callee_count: `5`
- tags: ``

## callees

- `0x180033970`
- `0x180039e20`
- `0x18004e070`
- `0x18004e230`
- `0x18007a900`

## pseudocode

```c
__int64 __fastcall av_container_fifo_write(__int64 a1, __int64 a2, unsigned int a3)
{
  _QWORD *v6; // rax
  int v8; // ebx
  _QWORD *v9; // [rsp+40h] [rbp+8h] BYREF

  v6 = (_QWORD *)av_refstruct_pool_get(*(_QWORD *)(a1 + 8));
  v9 = v6;
  if ( !v6 )
    return 4294967284LL;
  v8 = (*(__int64 (__fastcall **)(_QWORD, _QWORD, __int64, _QWORD))(a1 + 48))(*(_QWORD *)(a1 + 16), *v6, a2, a3);
  if ( v8 >= 0 )
  {
    v8 = av_fifo_write(*(_QWORD *)a1, &v9, 1);
    if ( v8 >= 0 )
      return 0;
  }
  av_refstruct_unref(&v9);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x180033970  mov     [rsp+arg_8], rbx
0x180033975  mov     [rsp+arg_10], rsi
0x18003397a  push    rdi
0x18003397b  sub     rsp, 30h
0x18003397f  mov     rdi, rcx
0x180033982  mov     ebx, r8d
0x180033985  mov     rcx, [rcx+8]
0x180033989  mov     rsi, rdx
0x18003398c  call    av_refstruct_pool_get
0x180033991  mov     [rsp+38h+arg_0], rax
0x180033996  test    rax, rax
0x180033999  jnz     short loc_1800339A2
0x18003399b  mov     eax, 0FFFFFFF4h
0x1800339a0  jmp     short loc_1800339E8
0x1800339a2  mov     rdx, [rax]
0x1800339a5  mov     r9d, ebx
0x1800339a8  mov     rax, [rdi+30h]
0x1800339ac  mov     r8, rsi
0x1800339af  mov     rcx, [rdi+10h]
0x1800339b3  call    cs:__guard_dispatch_icall_fptr
0x1800339b9  mov     ebx, eax
0x1800339bb  test    eax, eax
0x1800339bd  js      short loc_1800339DC
0x1800339bf  mov     rcx, [rdi]
0x1800339c2  lea     rdx, [rsp+38h+arg_0]
0x1800339c7  mov     r8d, 1
0x1800339cd  call    av_fifo_write
0x1800339d2  mov     ebx, eax
0x1800339d4  test    eax, eax
0x1800339d6  js      short loc_1800339DC
0x1800339d8  xor     eax, eax
0x1800339da  jmp     short loc_1800339E8
0x1800339dc  lea     rcx, [rsp+38h+arg_0]
0x1800339e1  call    av_refstruct_unref
0x1800339e6  mov     eax, ebx
0x1800339e8  mov     rbx, [rsp+38h+arg_8]
0x1800339ed  mov     rsi, [rsp+38h+arg_10]
0x1800339f2  add     rsp, 30h
0x1800339f6  pop     rdi
0x1800339f7  retn
```
