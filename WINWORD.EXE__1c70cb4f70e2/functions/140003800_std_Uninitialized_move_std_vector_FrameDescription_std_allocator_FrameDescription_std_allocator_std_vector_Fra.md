# std::_Uninitialized_move<std::vector<FrameDescription,std::allocator<FrameDescription>> *,std::allocator<std::vector<FrameDescription,std::allocator<FrameDescription>>>>(std::vector<FrameDescription,std::allocator<FrameDescription>> * const,std::vector<FrameDescription,std::allocator<FrameDescription>> * const,std::vector<FrameDescription,std::allocator<FrameDescription>> *,std::allocator<std::vector<FrameDescription,std::allocator<FrameDescription>>> &)

- ea: `0x140003800`
- end: `0x140003865`
- name: `??$_Uninitialized_move@PEAV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@V?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@2@@std@@YAPEAV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@0@QEAV10@0PEAV10@AEAV?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@0@@Z`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000354c`

## callees

- `0x1400015e0`
- `0x140003800`

## pseudocode

```c
char *__fastcall std::_Uninitialized_move<std::vector<FrameDescription> *,std::allocator<std::vector<FrameDescription>>>(
        __int64 *a1,
        __int64 *a2,
        char *a3)
{
  __int64 *v5; // r8
  char *v6; // r9
  __int64 v7; // rcx
  __int64 v8; // rdx
  __int64 v9; // rax

  if ( a1 != a2 )
  {
    v5 = a1 + 1;
    v6 = (char *)(a3 - (char *)a1);
    do
    {
      v7 = *v5;
      v8 = v5[1];
      v9 = *(v5 - 1);
      v5[1] = 0;
      *v5 = 0;
      *(v5 - 1) = 0;
      *(__int64 *)((char *)v5 + (_QWORD)v6) = v7;
      *(__int64 *)((char *)v5 + (_QWORD)v6 + 8) = v8;
      v5 += 3;
      *(_QWORD *)a3 = v9;
      a3 += 24;
    }
    while ( v5 - 1 != a2 );
  }
  std::_Destroy_range<std::allocator<std::vector<FrameDescription>>>(a3, a3);
  return a3;
}

```

## disassembly

```asm
0x140003800  push    rbx
0x140003802  sub     rsp, 20h
0x140003806  mov     rbx, r8
0x140003809  mov     r10, rdx
0x14000380c  cmp     rcx, rdx
0x14000380f  jz      short loc_140003851
0x140003811  mov     r9, rbx
0x140003814  lea     r8, [rcx+8]
0x140003818  sub     r9, rcx
0x14000381b  xor     r11d, r11d
0x14000381e  mov     rcx, [r8]
0x140003821  mov     rdx, [r8+8]
0x140003825  mov     rax, [r8-8]
0x140003829  mov     [r8+8], r11
0x14000382d  mov     [r8], r11
0x140003830  mov     [r8-8], r11
0x140003834  mov     [r9+r8], rcx
0x140003838  mov     [r9+r8+8], rdx
0x14000383d  lea     r8, [r8+18h]
0x140003841  mov     [rbx], rax
0x140003844  lea     rcx, [r8-8]
0x140003848  add     rbx, 18h
0x14000384c  cmp     rcx, r10
0x14000384f  jnz     short loc_14000381E
0x140003851  mov     rdx, rbx
0x140003854  mov     rcx, rbx
0x140003857  call    ??$_Destroy_range@V?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@std@@@std@@YAXPEAV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@0@QEAV10@AEAV?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@0@@Z; std::_Destroy_range<std::allocator<std::vector<FrameDescription>>>(std::vector<FrameDescription> *,std::vector<FrameDescription> * const,std::allocator<std::vector<FrameDescription>> &)
0x14000385c  mov     rax, rbx
0x14000385f  add     rsp, 20h
0x140003863  pop     rbx
0x140003864  retn
```
