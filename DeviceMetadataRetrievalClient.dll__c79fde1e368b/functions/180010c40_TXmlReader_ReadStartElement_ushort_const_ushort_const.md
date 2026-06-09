# TXmlReader::ReadStartElement(ushort const *,ushort const *)

- ea: `0x180010c40`
- end: `0x180010c99`
- name: `?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z`
- size: `89`
- prototype: `__int64 __fastcall(TXmlReader *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `7`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180006904`
- `0x180008544`
- `0x180008d8c`
- `0x18000913c`
- `0x18000a4c4`
- `0x18000dabc`
- `0x180010e08`

## callees

- `0x1800108d8`
- `0x1800109a4`
- `0x1800109e4`
- `0x180010c40`

## pseudocode

```c
__int64 __fastcall TXmlReader::ReadStartElement(
        TXmlReader *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  __int64 result; // rax
  enum XmlNodeType v7; // [rsp+48h] [rbp+20h] BYREF

  result = TXmlReader::IsNodeType(this, XmlNodeType_Element);
  if ( !(_DWORD)result )
  {
    result = TXmlReader::IsNodeQName(this, a2, a3);
    if ( !(_DWORD)result )
    {
      v7 = XmlNodeType_None;
      return TXmlReader::Read(this, &v7);
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010c40  mov     [rsp+arg_0], rbx
0x180010c45  mov     [rsp+arg_8], rsi
0x180010c4a  push    rdi
0x180010c4b  sub     rsp, 20h
0x180010c4f  mov     rsi, rdx
0x180010c52  mov     rdi, r8
0x180010c55  mov     edx, 1; enum XmlNodeType
0x180010c5a  mov     rbx, rcx
0x180010c5d  call    ?IsNodeType@TXmlReader@@QEAAJW4XmlNodeType@@@Z; TXmlReader::IsNodeType(XmlNodeType)
0x180010c62  test    eax, eax
0x180010c64  jnz     short loc_180010C89
0x180010c66  mov     r8, rdi; unsigned __int16 *
0x180010c69  mov     rdx, rsi; unsigned __int16 *
0x180010c6c  mov     rcx, rbx; this
0x180010c6f  call    ?IsNodeQName@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::IsNodeQName(ushort const *,ushort const *)
0x180010c74  test    eax, eax
0x180010c76  jnz     short loc_180010C89
0x180010c78  lea     rdx, [rsp+28h+arg_18]; enum XmlNodeType *
0x180010c7d  mov     [rsp+28h+arg_18], eax
0x180010c81  mov     rcx, rbx; this
0x180010c84  call    ?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z; TXmlReader::Read(XmlNodeType *)
0x180010c89  mov     rbx, [rsp+28h+arg_0]
0x180010c8e  mov     rsi, [rsp+28h+arg_8]
0x180010c93  add     rsp, 20h
0x180010c97  pop     rdi
0x180010c98  retn
```
