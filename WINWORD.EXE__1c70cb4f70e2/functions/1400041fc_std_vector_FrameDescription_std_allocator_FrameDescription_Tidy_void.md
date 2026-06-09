# std::vector<FrameDescription,std::allocator<FrameDescription>>::_Tidy(void)

- ea: `0x1400041fc`
- end: `0x140004230`
- name: `?_Tidy@?$vector@UFrameDescription@@V?$allocator@UFrameDescription@@@std@@@std@@AEAAXXZ`
- size: `52`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x1400015e0`
- `0x140003a50`

## callees

- `0x140001628`
- `0x1400041fc`

## pseudocode

```c
__int64 __fastcall std::vector<FrameDescription>::_Tidy(__int64 a1)
{
  _QWORD *v2; // rcx
  __int64 result; // rax

  v2 = *(_QWORD **)a1;
  if ( v2 )
  {
    std::_Deallocate<16>(v2, (*(_QWORD *)(a1 + 16) - (_QWORD)v2) & 0xFFFFFFFFFFFFFFF0uLL);
    result = 0;
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
  return result;
}

```

## disassembly

```asm
0x1400041fc  push    rbx
0x1400041fe  sub     rsp, 20h
0x140004202  mov     rbx, rcx
0x140004205  mov     rcx, [rcx]
0x140004208  test    rcx, rcx
0x14000420b  jz      short loc_14000422A
0x14000420d  mov     rdx, [rbx+10h]
0x140004211  sub     rdx, rcx
0x140004214  and     rdx, 0FFFFFFFFFFFFFFF0h
0x140004218  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000421d  xor     eax, eax
0x14000421f  mov     [rbx], rax
0x140004222  mov     [rbx+8], rax
0x140004226  mov     [rbx+10h], rax
0x14000422a  add     rsp, 20h
0x14000422e  pop     rbx
0x14000422f  retn
```
