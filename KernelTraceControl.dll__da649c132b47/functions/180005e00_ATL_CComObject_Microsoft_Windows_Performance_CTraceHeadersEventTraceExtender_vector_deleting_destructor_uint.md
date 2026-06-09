# ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180005e00`
- end: `0x180005e2f`
- name: `??_E?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180005c88`
- `0x180005e00`
- `0x1800268f4`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::`vector deleting destructor'(
        void *Block,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180005e00  mov     [rsp+arg_0], rbx
0x180005e05  push    rdi
0x180005e06  sub     rsp, 20h
0x180005e0a  mov     ebx, edx
0x180005e0c  mov     rdi, rcx
0x180005e0f  call    ??1?$CComObject@VCTraceHeadersEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CTraceHeadersEventTraceExtender>(void)
0x180005e14  test    bl, 1
0x180005e17  jz      short loc_180005E21
0x180005e19  mov     rcx, rdi; Block
0x180005e1c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180005e21  mov     rax, rdi
0x180005e24  mov     rbx, [rsp+28h+arg_0]
0x180005e29  add     rsp, 20h
0x180005e2d  pop     rdi
0x180005e2e  retn
```
