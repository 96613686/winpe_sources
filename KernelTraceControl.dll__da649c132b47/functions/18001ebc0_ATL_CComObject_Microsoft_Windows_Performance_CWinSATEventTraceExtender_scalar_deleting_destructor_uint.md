# ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`scalar deleting destructor'(uint)

- ea: `0x18001ebc0`
- end: `0x18001ebef`
- name: `??_G?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001eb24`
- `0x18001ebc0`
- `0x1800268f4`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::`scalar deleting destructor'(
        void *Block,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18001ebc0  mov     [rsp+arg_0], rbx
0x18001ebc5  push    rdi
0x18001ebc6  sub     rsp, 20h
0x18001ebca  mov     ebx, edx
0x18001ebcc  mov     rdi, rcx
0x18001ebcf  call    ??1?$CComObject@VCWinSATEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CWinSATEventTraceExtender>(void)
0x18001ebd4  test    bl, 1
0x18001ebd7  jz      short loc_18001EBE1
0x18001ebd9  mov     rcx, rdi; Block
0x18001ebdc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ebe1  mov     rax, rdi
0x18001ebe4  mov     rbx, [rsp+28h+arg_0]
0x18001ebe9  add     rsp, 20h
0x18001ebed  pop     rdi
0x18001ebee  retn
```
