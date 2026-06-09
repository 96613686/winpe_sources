# ATL::CComContainedObject<CALACDecMFT>::`vector deleting destructor'(uint)

- ea: `0x180002110`
- end: `0x180002144`
- name: `??_E?$CComContainedObject@VCALACDecMFT@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, broker_com_uri`

## callees

- `0x180001574`
- `0x180001f78`
- `0x180002110`

## pseudocode

```c
CALACDecMFT *__fastcall ATL::CComContainedObject<CALACDecMFT>::`vector deleting destructor'(
        CALACDecMFT *Block,
        char a2)
{
  CALACDecMFT::~CALACDecMFT(Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002110  mov     [rsp+arg_0], rbx
0x180002115  push    rdi
0x180002116  sub     rsp, 20h
0x18000211a  mov     ebx, edx
0x18000211c  mov     rdi, rcx
0x18000211f  call    ??1CALACDecMFT@@UEAA@XZ; CALACDecMFT::~CALACDecMFT(void)
0x180002124  test    bl, 1
0x180002127  jz      short loc_180002136
0x180002129  mov     edx, 0D8h
0x18000212e  mov     rcx, rdi; Block
0x180002131  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002136  mov     rbx, [rsp+28h+arg_0]
0x18000213b  mov     rax, rdi
0x18000213e  add     rsp, 20h
0x180002142  pop     rdi
0x180002143  retn
```
