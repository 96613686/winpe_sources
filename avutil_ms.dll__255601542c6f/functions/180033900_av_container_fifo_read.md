# av_container_fifo_read

- ea: `0x180033900`
- end: `0x18003396e`
- name: `av_container_fifo_read`
- size: `110`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: ``

## callees

- `0x180033900`
- `0x180039d60`
- `0x18004e230`
- `0x18007a900`

## pseudocode

```c
__int64 __fastcall av_container_fifo_read(__int64 a1, __int64 a2, unsigned int a3)
{
  __int64 result; // rax
  unsigned int v7; // ebx
  _QWORD *v8; // [rsp+40h] [rbp+8h] BYREF

  result = av_fifo_read(*(_QWORD *)a1, (int)&v8, 1);
  if ( (int)result >= 0 )
  {
    v7 = (*(__int64 (__fastcall **)(_QWORD, __int64, _QWORD, _QWORD))(a1 + 48))(*(_QWORD *)(a1 + 16), a2, *v8, a3);
    av_refstruct_unref(&v8);
    return v7;
  }
  else
  {
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x180033900  mov     [rsp+arg_8], rbx
0x180033905  mov     [rsp+arg_10], rsi
0x18003390a  push    rdi
0x18003390b  sub     rsp, 30h
0x18003390f  mov     edi, r8d
0x180033912  mov     rsi, rdx
0x180033915  mov     rbx, rcx
0x180033918  lea     rdx, [rsp+38h+arg_0]
0x18003391d  mov     rcx, [rcx]
0x180033920  mov     r8d, 1
0x180033926  call    av_fifo_read
0x18003392b  test    eax, eax
0x18003392d  jns     short loc_180033934
0x18003392f  lfence
0x180033932  jmp     short loc_18003395E
0x180033934  mov     r8, [rsp+38h+arg_0]
0x180033939  mov     r9d, edi
0x18003393c  mov     rcx, [rbx+10h]
0x180033940  mov     rdx, rsi
0x180033943  mov     rax, [rbx+30h]
0x180033947  mov     r8, [r8]
0x18003394a  call    cs:__guard_dispatch_icall_fptr
0x180033950  lea     rcx, [rsp+38h+arg_0]
0x180033955  mov     ebx, eax
0x180033957  call    av_refstruct_unref
0x18003395c  mov     eax, ebx
0x18003395e  mov     rbx, [rsp+38h+arg_8]
0x180033963  mov     rsi, [rsp+38h+arg_10]
0x180033968  add     rsp, 30h
0x18003396c  pop     rdi
0x18003396d  retn
```
