# TXmlReader::ReadElementString(ushort const *,ushort const *,ushort const * *)

- ea: `0x180010a84`
- end: `0x180010bc2`
- name: `?ReadElementString@TXmlReader@@QEAAJPEBG0PEAPEBG@Z`
- size: `318`
- prototype: `__int64 __fastcall(TXmlReader *__hidden this, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 **)`
- caller_count: `7`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x18000838c`
- `0x180008544`
- `0x180008d8c`
- `0x18000913c`
- `0x18000a0ac`
- `0x18000a200`
- `0x18000dabc`

## callees

- `0x1800106b4`
- `0x1800108d8`
- `0x1800109a4`
- `0x1800109e4`
- `0x180010a84`
- `0x180010bc8`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall TXmlReader::ReadElementString(
        TXmlReader *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        const unsigned __int16 **a4)
{
  __int64 result; // rax
  unsigned int v9; // [rsp+20h] [rbp-10h] BYREF
  enum XmlNodeType v10; // [rsp+24h] [rbp-Ch] BYREF
  unsigned __int16 *v11; // [rsp+28h] [rbp-8h] BYREF
  enum XmlNodeType v12; // [rsp+68h] [rbp+38h] BYREF

  v12 = XmlNodeType_None;
  v11 = 0;
  v9 = 0;
  *a4 = 0;
  result = TXmlReader::IsNodeType(this, XmlNodeType_Element);
  if ( !(_DWORD)result )
  {
    result = TXmlReader::IsNodeQName(this, a2, a3);
    if ( !(_DWORD)result )
    {
      if ( (*(unsigned int (__fastcall **)(_QWORD))(**(_QWORD **)this + 160LL))(*(_QWORD *)this) )
      {
        result = TXmlReader::CopyStringToWorkBuffer(this, &word_180017E8C, 0, a4);
        if ( !(_DWORD)result )
          return TXmlReader::Read(this, &v12);
      }
      else
      {
        result = TXmlReader::Read(this, &v12);
        if ( (_DWORD)result )
          return result;
        if ( v12 != XmlNodeType_Text )
        {
          result = TXmlReader::CopyStringToWorkBuffer(this, &word_180017E8C, 0, a4);
LABEL_10:
          if ( !(_DWORD)result )
            return TXmlReader::ReadEndElement(this, a2, a3);
          return result;
        }
        result = (*(__int64 (__fastcall **)(_QWORD, unsigned __int16 **, unsigned int *))(**(_QWORD **)this + 128LL))(
                   *(_QWORD *)this,
                   &v11,
                   &v9);
        if ( !(_DWORD)result )
        {
          result = TXmlReader::CopyStringToWorkBuffer(this, v11, v9, a4);
          if ( !(_DWORD)result )
          {
            v10 = XmlNodeType_None;
            result = TXmlReader::Read(this, &v10);
            goto LABEL_10;
          }
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010a84  mov     [rsp-18h+arg_0], rbx
0x180010a89  mov     [rsp-18h+arg_8], rsi
0x180010a8e  push    rbp
0x180010a8f  push    rdi
0x180010a90  push    r14
0x180010a92  mov     rbp, rsp
0x180010a95  sub     rsp, 30h
0x180010a99  mov     r14, rdx
0x180010a9c  mov     [rbp+arg_18], 0
0x180010aa3  mov     edx, 1; enum XmlNodeType
0x180010aa8  mov     [rbp+var_8], 0
0x180010ab0  mov     rdi, r9
0x180010ab3  mov     [rbp+var_10], 0
0x180010aba  mov     rsi, r8
0x180010abd  mov     qword ptr [r9], 0
0x180010ac4  mov     rbx, rcx
0x180010ac7  call    ?IsNodeType@TXmlReader@@QEAAJW4XmlNodeType@@@Z; TXmlReader::IsNodeType(XmlNodeType)
0x180010acc  test    eax, eax
0x180010ace  jnz     loc_180010BAF
0x180010ad4  mov     r8, rsi; unsigned __int16 *
0x180010ad7  mov     rdx, r14; unsigned __int16 *
0x180010ada  mov     rcx, rbx; this
0x180010add  call    ?IsNodeQName@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::IsNodeQName(ushort const *,ushort const *)
0x180010ae2  test    eax, eax
0x180010ae4  jnz     loc_180010BAF
0x180010aea  mov     rcx, [rbx]
0x180010aed  mov     rax, [rcx]
0x180010af0  mov     rax, [rax+0A0h]
0x180010af7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010afc  mov     rcx, rbx; this
0x180010aff  test    eax, eax
0x180010b01  jnz     loc_180010B8D
0x180010b07  lea     rdx, [rbp+arg_18]; enum XmlNodeType *
0x180010b0b  call    ?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z; TXmlReader::Read(XmlNodeType *)
0x180010b10  test    eax, eax
0x180010b12  jnz     loc_180010BAF
0x180010b18  cmp     [rbp+arg_18], 3
0x180010b1c  jnz     short loc_180010B64
0x180010b1e  mov     rcx, [rbx]
0x180010b21  lea     r8, [rbp+var_10]
0x180010b25  lea     rdx, [rbp+var_8]
0x180010b29  mov     rax, [rcx]
0x180010b2c  mov     rax, [rax+80h]
0x180010b33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010b38  test    eax, eax
0x180010b3a  jnz     short loc_180010BAF
0x180010b3c  mov     r8d, [rbp+var_10]; unsigned int
0x180010b40  mov     r9, rdi; unsigned __int16 **
0x180010b43  mov     rdx, [rbp+var_8]; unsigned __int16 *
0x180010b47  mov     rcx, rbx; this
0x180010b4a  call    ?CopyStringToWorkBuffer@TXmlReader@@IEAAJPEBGIPEAPEBG@Z; TXmlReader::CopyStringToWorkBuffer(ushort const *,uint,ushort const * *)
0x180010b4f  test    eax, eax
0x180010b51  jnz     short loc_180010BAF
0x180010b53  lea     rdx, [rbp+var_C]; enum XmlNodeType *
0x180010b57  mov     [rbp+var_C], eax
0x180010b5a  mov     rcx, rbx; this
0x180010b5d  call    ?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z; TXmlReader::Read(XmlNodeType *)
0x180010b62  jmp     short loc_180010B79
0x180010b64  mov     r9, rdi; unsigned __int16 **
0x180010b67  lea     rdx, word_180017E8C; unsigned __int16 *
0x180010b6e  xor     r8d, r8d; unsigned int
0x180010b71  mov     rcx, rbx; this
0x180010b74  call    ?CopyStringToWorkBuffer@TXmlReader@@IEAAJPEBGIPEAPEBG@Z; TXmlReader::CopyStringToWorkBuffer(ushort const *,uint,ushort const * *)
0x180010b79  test    eax, eax
0x180010b7b  jnz     short loc_180010BAF
0x180010b7d  mov     r8, rsi; unsigned __int16 *
0x180010b80  mov     rdx, r14; unsigned __int16 *
0x180010b83  mov     rcx, rbx; this
0x180010b86  call    ?ReadEndElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadEndElement(ushort const *,ushort const *)
0x180010b8b  jmp     short loc_180010BAF
0x180010b8d  mov     r9, rdi; unsigned __int16 **
0x180010b90  lea     rdx, word_180017E8C; unsigned __int16 *
0x180010b97  xor     r8d, r8d; unsigned int
0x180010b9a  call    ?CopyStringToWorkBuffer@TXmlReader@@IEAAJPEBGIPEAPEBG@Z; TXmlReader::CopyStringToWorkBuffer(ushort const *,uint,ushort const * *)
0x180010b9f  test    eax, eax
0x180010ba1  jnz     short loc_180010BAF
0x180010ba3  lea     rdx, [rbp+arg_18]; enum XmlNodeType *
0x180010ba7  mov     rcx, rbx; this
0x180010baa  call    ?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z; TXmlReader::Read(XmlNodeType *)
0x180010baf  mov     rbx, [rsp+30h+arg_0]
0x180010bb4  mov     rsi, [rsp+30h+arg_8]
0x180010bb9  add     rsp, 30h
0x180010bbd  pop     r14
0x180010bbf  pop     rdi
0x180010bc0  pop     rbp
0x180010bc1  retn
```
