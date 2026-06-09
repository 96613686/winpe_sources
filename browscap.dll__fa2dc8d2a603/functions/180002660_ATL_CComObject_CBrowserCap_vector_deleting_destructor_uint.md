# ATL::CComObject<CBrowserCap>::`vector deleting destructor'(uint)

- ea: `0x180002660`
- end: `0x180002695`
- name: `??_E?$CComObject@VCBrowserCap@@@ATL@@UEAAPEAXI@Z`
- size: `53`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x1800023b4`
- `0x180002660`

## import_xrefs

- `msvcrt!free` at `0x180002681`
- `msvcrt!free` at `0x180002681`

## pseudocode

```c
CBrowserCap *__fastcall ATL::CComObject<CBrowserCap>::`vector deleting destructor'(CBrowserCap *Block, char a2)
{
  ATL::CComObject<CBrowserCap>::~CComObject<CBrowserCap>(Block);
  if ( (a2 & 1) != 0 && Block )
    free(Block);
  return Block;
}

```

## disassembly

```asm
0x180002660  mov     [rsp+arg_0], rbx
0x180002665  push    rdi
0x180002666  sub     rsp, 20h
0x18000266a  mov     ebx, edx
0x18000266c  mov     rdi, rcx
0x18000266f  call    ??1?$CComObject@VCBrowserCap@@@ATL@@UEAA@XZ; ATL::CComObject<CBrowserCap>::~CComObject<CBrowserCap>(void)
0x180002674  test    bl, 1
0x180002677  jz      short loc_180002687
0x180002679  test    rdi, rdi
0x18000267c  jz      short loc_180002687
0x18000267e  mov     rcx, rdi; Block
0x180002681  call    cs:__imp_free
0x180002687  mov     rbx, [rsp+28h+arg_0]
0x18000268c  mov     rax, rdi
0x18000268f  add     rsp, 20h
0x180002693  pop     rdi
0x180002694  retn
```
