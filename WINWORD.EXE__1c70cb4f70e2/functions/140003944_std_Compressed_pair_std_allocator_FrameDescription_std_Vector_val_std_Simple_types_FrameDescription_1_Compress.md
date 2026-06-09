# std::_Compressed_pair<std::allocator<FrameDescription>,std::_Vector_val<std::_Simple_types<FrameDescription>>,1>::~_Compressed_pair<std::allocator<FrameDescription>,std::_Vector_val<std::_Simple_types<FrameDescription>>,1>(void)

- ea: `0x140003944`
- end: `0x14000395c`
- name: `??1?$_Compressed_pair@V?$allocator@UFrameDescription@@@std@@V?$_Vector_val@U?$_Simple_types@UFrameDescription@@@std@@@2@$00@std@@QEAA@XZ`
- size: `24`
- prototype: ``
- caller_count: `0`
- callee_count: `0`
- tags: `broker_com_uri`

## pseudocode

```c
void __fastcall std::_Compressed_pair<std::allocator<FrameDescription>,std::_Vector_val<std::_Simple_types<FrameDescription>>,1>::~_Compressed_pair<std::allocator<FrameDescription>,std::_Vector_val<std::_Simple_types<FrameDescription>>,1>(
        _QWORD *a1)
{
  *a1 = 19937;
  a1[1] = 19937;
  a1[2] = 19937;
}

```

## disassembly

```asm
0x140003944  mov     qword ptr [rcx], 4DE1h
0x14000394b  mov     qword ptr [rcx+8], 4DE1h
0x140003953  mov     qword ptr [rcx+10h], 4DE1h
0x14000395b  retn
```
