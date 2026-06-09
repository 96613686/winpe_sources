# std::_Destroy_range<std::allocator<std::vector<FrameDescription,std::allocator<FrameDescription>>>>(std::vector<FrameDescription,std::allocator<FrameDescription>> *,std::vector<FrameDescription,std::allocator<FrameDescription>> * const,std::allocator<std::vector<FrameDescription,std::allocator<FrameDescription>>> &)

- ea: `0x1400015e0`
- end: `0x140001628`
- name: `??$_Destroy_range@V?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@std@@@std@@YAXPEAV?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@0@QEAV10@AEAV?$allocator@V?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@@0@@Z`
- size: `72`
- prototype: ``
- caller_count: `4`
- callee_count: `2`
- tags: ``

## callers

- `0x140003220`
- `0x140003800`
- `0x140003978`
- `0x140004138`

## callees

- `0x1400015e0`
- `0x1400041fc`

## pseudocode

```c
__int64 __fastcall std::_Destroy_range<std::allocator<std::vector<FrameDescription>>>(_QWORD *a1, _QWORD *a2)
{
  _QWORD *v3; // rbx
  __int64 result; // rax

  if ( a1 != a2 )
  {
    v3 = a1;
    do
    {
      result = std::vector<FrameDescription>::_Tidy(v3);
      *v3 = 19937;
      v3[1] = 19937;
      v3[2] = 19937;
      v3 += 3;
    }
    while ( v3 != a2 );
  }
  return result;
}

```

## disassembly

```asm
0x1400015e0  cmp     rcx, rdx
0x1400015e3  jz      short locret_140001627
0x1400015e5  mov     [rsp+arg_0], rbx
0x1400015ea  push    rdi
0x1400015eb  sub     rsp, 20h
0x1400015ef  mov     rdi, rdx
0x1400015f2  mov     rbx, rcx
0x1400015f5  mov     rcx, rbx
0x1400015f8  call    ?_Tidy@?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@AEAAXXZ; std::vector<FrameDescription>::_Tidy(void)
0x1400015fd  mov     qword ptr [rbx], 4DE1h
0x140001604  mov     qword ptr [rbx+8], 4DE1h
0x14000160c  mov     qword ptr [rbx+10h], 4DE1h
0x140001614  add     rbx, 18h
0x140001618  cmp     rbx, rdi
0x14000161b  jnz     short loc_1400015F5
0x14000161d  mov     rbx, [rsp+28h+arg_0]
0x140001622  add     rsp, 20h
0x140001626  pop     rdi
0x140001627  retn
```
