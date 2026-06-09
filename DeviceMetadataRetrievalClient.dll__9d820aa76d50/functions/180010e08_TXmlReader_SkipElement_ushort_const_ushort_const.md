# TXmlReader::SkipElement(ushort const *,ushort const *)

- ea: `0x180010e08`
- end: `0x180010ea5`
- name: `?SkipElement@TXmlReader@@QEAAJPEBG0@Z`
- size: `157`
- prototype: `__int64 __fastcall(TXmlReader *__hidden this, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `4`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180008d8c`
- `0x18000913c`
- `0x18000a4c4`
- `0x18000dabc`

## callees

- `0x1800108d8`
- `0x1800109a4`
- `0x1800109e4`
- `0x180010c40`
- `0x180010e08`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall TXmlReader::SkipElement(TXmlReader *this, const unsigned __int16 *a2, const unsigned __int16 *a3)
{
  int v6; // edi
  __int64 result; // rax
  enum XmlNodeType v8; // [rsp+50h] [rbp+8h] BYREF

  v6 = (*(__int64 (__fastcall **)(_QWORD))(**(_QWORD **)this + 160LL))(*(_QWORD *)this);
  result = TXmlReader::ReadStartElement(this, a2, a3);
  if ( !(_DWORD)result )
  {
    if ( !v6 )
    {
      while ( 1 )
      {
        result = TXmlReader::IsNodeType(this, XmlNodeType_EndElement);
        if ( !(_DWORD)result )
        {
          result = TXmlReader::IsNodeQName(this, a2, a3);
          if ( !(_DWORD)result )
            break;
        }
        if ( (_DWORD)result == 1 )
        {
          v8 = XmlNodeType_None;
          result = TXmlReader::Read(this, &v8);
          if ( !(_DWORD)result )
            continue;
        }
        return result;
      }
    }
    v8 = XmlNodeType_None;
    return TXmlReader::Read(this, &v8);
  }
  return result;
}

```

## disassembly

```asm
0x180010e08  push    rbx
0x180010e0a  push    rbp
0x180010e0b  push    rsi
0x180010e0c  push    rdi
0x180010e0d  sub     rsp, 28h
0x180010e11  mov     rbx, rcx
0x180010e14  mov     rsi, r8
0x180010e17  mov     rcx, [rcx]
0x180010e1a  mov     rbp, rdx
0x180010e1d  mov     rax, [rcx]
0x180010e20  mov     rax, [rax+0A0h]
0x180010e27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010e2c  mov     r8, rsi; unsigned __int16 *
0x180010e2f  mov     rdx, rbp; unsigned __int16 *
0x180010e32  mov     rcx, rbx; this
0x180010e35  mov     edi, eax
0x180010e37  call    ?ReadStartElement@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::ReadStartElement(ushort const *,ushort const *)
0x180010e3c  test    eax, eax
0x180010e3e  jnz     short loc_180010E9C
0x180010e40  test    edi, edi
0x180010e42  jnz     short loc_180010E87
0x180010e44  mov     edx, 0Fh; enum XmlNodeType
0x180010e49  mov     rcx, rbx; this
0x180010e4c  call    ?IsNodeType@TXmlReader@@QEAAJW4XmlNodeType@@@Z; TXmlReader::IsNodeType(XmlNodeType)
0x180010e51  test    eax, eax
0x180010e53  jnz     short loc_180010E67
0x180010e55  mov     r8, rsi; unsigned __int16 *
0x180010e58  mov     rdx, rbp; unsigned __int16 *
0x180010e5b  mov     rcx, rbx; this
0x180010e5e  call    ?IsNodeQName@TXmlReader@@QEAAJPEBG0@Z; TXmlReader::IsNodeQName(ushort const *,ushort const *)
0x180010e63  test    eax, eax
0x180010e65  jz      short loc_180010E87
0x180010e67  cmp     eax, 1
0x180010e6a  jnz     short loc_180010E9C
0x180010e6c  lea     rdx, [rsp+48h+arg_0]; enum XmlNodeType *
0x180010e71  mov     [rsp+48h+arg_0], 0
0x180010e79  mov     rcx, rbx; this
0x180010e7c  call    ?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z; TXmlReader::Read(XmlNodeType *)
0x180010e81  test    eax, eax
0x180010e83  jz      short loc_180010E44
0x180010e85  jmp     short loc_180010E9C
0x180010e87  lea     rdx, [rsp+48h+arg_0]; enum XmlNodeType *
0x180010e8c  mov     [rsp+48h+arg_0], 0
0x180010e94  mov     rcx, rbx; this
0x180010e97  call    ?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z; TXmlReader::Read(XmlNodeType *)
0x180010e9c  add     rsp, 28h
0x180010ea0  pop     rdi
0x180010ea1  pop     rsi
0x180010ea2  pop     rbp
0x180010ea3  pop     rbx
0x180010ea4  retn
```
