# ATL::CComObject<CMigrationPlugin>::`scalar deleting destructor'(uint)

- ea: `0x18000ce40`
- end: `0x18000ce74`
- name: `??_G?$CComObject@VCMigrationPlugin@@@ATL@@UEAAPEAXI@Z`
- size: `52`
- prototype: `void *__fastcall(void *Block, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, loader_planting, broker_com_uri`

## callees

- `0x180002b9c`
- `0x18000c9c0`
- `0x18000ce40`

## pseudocode

```c
void *__fastcall ATL::CComObject<CMigrationPlugin>::`scalar deleting destructor'(void *Block, char a2)
{
  ATL::CComObject<CMigrationPlugin>::~CComObject<CMigrationPlugin>((__int64)Block);
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x18000ce40  mov     [rsp+arg_0], rbx
0x18000ce45  push    rdi
0x18000ce46  sub     rsp, 20h
0x18000ce4a  mov     ebx, edx
0x18000ce4c  mov     rdi, rcx
0x18000ce4f  call    ??1?$CComObject@VCMigrationPlugin@@@ATL@@UEAA@XZ; ATL::CComObject<CMigrationPlugin>::~CComObject<CMigrationPlugin>(void)
0x18000ce54  test    bl, 1
0x18000ce57  jz      short loc_18000CE66
0x18000ce59  mov     edx, 68h ; 'h'
0x18000ce5e  mov     rcx, rdi; Block
0x18000ce61  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000ce66  mov     rbx, [rsp+28h+arg_0]
0x18000ce6b  mov     rax, rdi
0x18000ce6e  add     rsp, 20h
0x18000ce72  pop     rdi
0x18000ce73  retn
```
