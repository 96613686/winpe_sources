# TXmlReader::ReadEndElement(ushort const *,ushort const *)

- ea: `0x180010bc8`
- end: `0x180010c3a`
- name: `?ReadEndElement@TXmlReader@@QEAAJPEBG0@Z`
- size: `114`
- prototype: `__int64 __fastcall(TXmlReader *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `5`
- tags: `registry_config`

## callers

- `0x180008544`
- `0x180008d8c`
- `0x18000913c`
- `0x18000a0ac`
- `0x18000a4c4`
- `0x18000dabc`
- `0x180010a84`

## callees

- `0x1800108d8`
- `0x1800109a4`
- `0x1800109e4`
- `0x180010bc8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall TXmlReader::ReadEndElement(TXmlReader *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  unsigned int IsNodeType; // ebx
  enum XmlNodeType v8; // [rsp+68h] [rbp+20h] BYREF

  IsNodeType = TXmlReader::IsNodeType(this, XmlNodeType_EndElement);
  if ( !IsNodeType )
  {
    IsNodeType = TXmlReader::IsNodeQName(this, a2, a3);
    if ( !IsNodeType )
    {
      v8 = XmlNodeType_None;
      IsNodeType = TXmlReader::Read(this, &v8);
      if ( IsNodeType == 1 )
        return (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 200LL))(*(_QWORD *)this) == 0;
    }
  }
  return IsNodeType;
}

```

## disassembly

```asm
0x180010bc8  push    rbx
0x180010bca  push    rbp
0x180010bcb  push    rsi
0x180010bcc  push    rdi
0x180010bcd  sub     rsp, 28h
0x180010bd1  mov     rbp, rdx
0x180010bd4  mov     rsi, r8
0x180010bd7  mov     edx, 0Fh; enum XmlNodeType
0x180010bdc  mov     rdi, rcx
0x180010bdf  call    ?IsNodeType@TXmlReader@@QEAAJW4XmlNodeType@@@Z; TXmlReader::IsNodeType(XmlNodeType)
0x180010be4  mov     ebx, eax
0x180010be6  test    eax, eax
0x180010be8  jnz     short loc_180010C2F
0x180010bea  mov     r8, rsi; unsigned __int16 *
0x180010bed  mov     rdx, rbp; unsigned __int16 *
0x180010bf0  mov     rcx, rdi; this
0x180010bf3  call    ?IsNodeQName@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::IsNodeQName(ushort const *,ushort const *)
0x180010bf8  mov     ebx, eax
0x180010bfa  test    eax, eax
0x180010bfc  jnz     short loc_180010C2F
0x180010bfe  lea     rdx, [rsp+48h+arg_18]; enum XmlNodeType *
0x180010c03  mov     [rsp+48h+arg_18], eax
0x180010c07  mov     rcx, rdi; this
0x180010c0a  call    ?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z; TXmlReader::Read(XmlNodeType *)
0x180010c0f  mov     ebx, eax
0x180010c11  cmp     eax, 1
0x180010c14  jnz     short loc_180010C2F
0x180010c16  mov     rcx, [rdi]
0x180010c19  mov     rax, [rcx]
0x180010c1c  mov     rax, [rax+0C8h]
0x180010c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010c28  xor     ecx, ecx
0x180010c2a  test    eax, eax
0x180010c2c  cmovnz  ebx, ecx
0x180010c2f  mov     eax, ebx
0x180010c31  add     rsp, 28h
0x180010c35  pop     rdi
0x180010c36  pop     rsi
0x180010c37  pop     rbp
0x180010c38  pop     rbx
0x180010c39  retn
```
