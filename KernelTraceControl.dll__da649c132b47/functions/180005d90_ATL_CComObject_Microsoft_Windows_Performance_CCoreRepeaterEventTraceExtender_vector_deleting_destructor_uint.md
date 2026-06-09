# ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180005d90`
- end: `0x180005dbf`
- name: `??_E?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005c18`
- `0x180005d90`
- `0x1800268f4`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::`vector deleting destructor'(
        void *Block,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005d90  mov     [rsp+arg_0], rbx
0x180005d95  push    rdi
0x180005d96  sub     rsp, 20h
0x180005d9a  mov     ebx, edx
0x180005d9c  mov     rdi, rcx
0x180005d9f  call    ??1?$CComObject@VCCoreRepeaterEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CCoreRepeaterEventTraceExtender>(void)
0x180005da4  test    bl, 1
0x180005da7  jz      short loc_180005DB1
0x180005da9  mov     rcx, rdi; Block
0x180005dac  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005db1  mov     rax, rdi
0x180005db4  mov     rbx, [rsp+28h+arg_0]
0x180005db9  add     rsp, 20h
0x180005dbd  pop     rdi
0x180005dbe  retn
```
