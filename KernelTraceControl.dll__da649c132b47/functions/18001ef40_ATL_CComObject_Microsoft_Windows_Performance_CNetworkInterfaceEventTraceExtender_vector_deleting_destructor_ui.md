# ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vector deleting destructor'(uint)

- ea: `0x18001ef40`
- end: `0x18001ef6f`
- name: `??_E?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x18001eed0`
- `0x18001ef40`
- `0x1800268f4`

## pseudocode

```c
void *__fastcall ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::`vector deleting destructor'(
        void *Block,
        char a2)
{
  ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18001ef40  mov     [rsp+arg_0], rbx
0x18001ef45  push    rdi
0x18001ef46  sub     rsp, 20h
0x18001ef4a  mov     ebx, edx
0x18001ef4c  mov     rdi, rcx
0x18001ef4f  call    ??1?$CComObject@VCNetworkInterfaceEventTraceExtender@Performance@Windows@Microsoft@@@ATL@@UEAA@XZ; ATL::CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>::~CComObject<Microsoft::Windows::Performance::CNetworkInterfaceEventTraceExtender>(void)
0x18001ef54  test    bl, 1
0x18001ef57  jz      short loc_18001EF61
0x18001ef59  mov     rcx, rdi; Block
0x18001ef5c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18001ef61  mov     rax, rdi
0x18001ef64  mov     rbx, [rsp+28h+arg_0]
0x18001ef69  add     rsp, 20h
0x18001ef6d  pop     rdi
0x18001ef6e  retn
```
