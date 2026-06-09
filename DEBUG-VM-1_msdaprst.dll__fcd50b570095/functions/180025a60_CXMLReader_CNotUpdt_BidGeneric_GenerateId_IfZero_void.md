# CXMLReader::CNotUpdt_BidGeneric::GenerateId_IfZero(void)

- ea: `0x180025a60`
- end: `0x180025a73`
- name: `?GenerateId_IfZero@CNotUpdt_BidGeneric@CXMLReader@@EEBAXXZ`
- size: `19`
- prototype: `void __fastcall(CXMLReader::CNotUpdt_BidGeneric *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `registry_config`

## callees

- `0x18001a5c8`

## string_xrefs

- `0x180025a63`: `<CXMLReader::CNotUpdt_BidGeneric::GenerateId_IfZero|ID|OBJ|PERSIST> %p{.}`

## pseudocode

```c
void __fastcall CXMLReader::CNotUpdt_BidGeneric::GenerateId_IfZero(CXMLReader::CNotUpdt_BidGeneric *this)
{
  bidObtainItemIdIfZeroW(
    (char *)this + 8,
    L"<CXMLReader::CNotUpdt_BidGeneric::GenerateId_IfZero|ID|OBJ|PERSIST> %p{.}",
    this);
}

```

## disassembly

```asm
0x180025a60  mov     r8, rcx
0x180025a63  lea     rdx, aCxmlreaderCnot_0; "<CXMLReader::CNotUpdt_BidGeneric::Gener"...
0x180025a6a  add     rcx, 8
0x180025a6e  jmp     _bidObtainItemIdIfZeroW
```
