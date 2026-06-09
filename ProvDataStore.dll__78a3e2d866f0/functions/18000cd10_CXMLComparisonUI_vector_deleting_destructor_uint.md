# CXMLComparisonUI::`vector deleting destructor'(uint)

- ea: `0x18000cd10`
- end: `0x18000cd40`
- name: `??_ECXMLComparisonUI@@UEAAPEAXI@Z`
- size: `48`
- prototype: `CXMLComparisonUI *__fastcall(CXMLComparisonUI *this, char)`
- caller_count: `0`
- callee_count: `2`
- tags: `file_ops, registry_config, broker_com_uri`

## callees

- `0x18000cbf0`
- `0x18000cd10`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd2c`
- `msvcrt!??3@YAXPEAX@Z` at `0x18000cd2c`

## pseudocode

```c
CXMLComparisonUI *__fastcall CXMLComparisonUI::`vector deleting destructor'(CXMLComparisonUI *this, char a2)
{
  CXMLComparison::~CXMLComparison(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x18000cd10  mov     [rsp+arg_0], rbx
0x18000cd15  push    rdi
0x18000cd16  sub     rsp, 20h
0x18000cd1a  mov     ebx, edx
0x18000cd1c  mov     rdi, rcx
0x18000cd1f  call    ??1CXMLComparison@@UEAA@XZ; CXMLComparison::~CXMLComparison(void)
0x18000cd24  test    bl, 1
0x18000cd27  jz      short loc_18000CD32
0x18000cd29  mov     rcx, rdi
0x18000cd2c  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000cd32  mov     rbx, [rsp+28h+arg_0]
0x18000cd37  mov     rax, rdi
0x18000cd3a  add     rsp, 20h
0x18000cd3e  pop     rdi
0x18000cd3f  retn
```
