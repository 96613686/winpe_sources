# TXmlReader::ReadXmlDecleration(void)

- ea: `0x180010ca0`
- end: `0x180010d12`
- name: `?ReadXmlDecleration@TXmlReader@@QEAAJXZ`
- size: `114`
- prototype: `__int64 __fastcall(TXmlReader *__hidden this)`
- caller_count: `4`
- callee_count: `3`
- tags: `registry_config`

## callers

- `0x180006904`
- `0x180008544`
- `0x18000a4c4`
- `0x18000dabc`

## callees

- `0x1800109e4`
- `0x180010ca0`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall TXmlReader::ReadXmlDecleration(TXmlReader *this)
{
  __int64 v2; // rcx
  __int64 result; // rax
  enum XmlNodeType v4; // [rsp+30h] [rbp+8h] BYREF
  enum XmlNodeType v5; // [rsp+38h] [rbp+10h] BYREF
  __int64 v6; // [rsp+40h] [rbp+18h] BYREF

  v6 = 0;
  v2 = *(_QWORD *)this;
  v4 = XmlNodeType_None;
  result = (*(__int64 (__fastcall **)(__int64, __int64, __int64 *))(*(_QWORD *)v2 + 32LL))(v2, 5, &v6);
  if ( !(_DWORD)result )
  {
    if ( v6 || (result = TXmlReader::Read(this, &v4), !(_DWORD)result) )
    {
      if ( v4 == XmlNodeType_XmlDeclaration )
      {
        v5 = XmlNodeType_None;
        return TXmlReader::Read(this, &v5);
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x180010ca0  push    rbx
0x180010ca2  sub     rsp, 20h
0x180010ca6  mov     rbx, rcx
0x180010ca9  mov     [rsp+28h+arg_10], 0
0x180010cb2  mov     rcx, [rcx]
0x180010cb5  lea     r8, [rsp+28h+arg_10]
0x180010cba  mov     [rsp+28h+arg_0], 0
0x180010cc2  mov     edx, 5
0x180010cc7  mov     rax, [rcx]
0x180010cca  mov     rax, [rax+20h]
0x180010cce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010cd3  test    eax, eax
0x180010cd5  jnz     short loc_180010D0C
0x180010cd7  cmp     [rsp+28h+arg_10], 0
0x180010cdd  jnz     short loc_180010CF0
0x180010cdf  lea     rdx, [rsp+28h+arg_0]; enum XmlNodeType *
0x180010ce4  mov     rcx, rbx; this
0x180010ce7  call    ?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z; TXmlReader::Read(XmlNodeType *)
0x180010cec  test    eax, eax
0x180010cee  jnz     short loc_180010D0C
0x180010cf0  cmp     [rsp+28h+arg_0], 11h
0x180010cf5  jnz     short loc_180010D0C
0x180010cf7  lea     rdx, [rsp+28h+arg_8]; enum XmlNodeType *
0x180010cfc  mov     [rsp+28h+arg_8], 0
0x180010d04  mov     rcx, rbx; this
0x180010d07  call    ?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z; TXmlReader::Read(XmlNodeType *)
0x180010d0c  add     rsp, 20h
0x180010d10  pop     rbx
0x180010d11  retn
```
