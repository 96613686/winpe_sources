# ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x180008b80`
- end: `0x180008baf`
- name: `??_E?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180008b04`
- `0x180008b80`
- `0x1800268f4`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::`vector deleting destructor'(
        void *Block,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180008b80  mov     [rsp+arg_0], rbx
0x180008b85  push    rdi
0x180008b86  sub     rsp, 20h
0x180008b8a  mov     ebx, edx
0x180008b8c  mov     rdi, rcx
0x180008b8f  call    ??1?$CComObject@VCBuildInfoEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CBuildInfoEventTraceExtender>(void)
0x180008b94  test    bl, 1
0x180008b97  jz      short loc_180008BA1
0x180008b99  mov     rcx, rdi; Block
0x180008b9c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180008ba1  mov     rax, rdi
0x180008ba4  mov     rbx, [rsp+28h+arg_0]
0x180008ba9  add     rsp, 20h
0x180008bad  pop     rdi
0x180008bae  retn
```
