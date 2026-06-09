# TXmlReader::Read(XmlNodeType *)

- ea: `0x1800109e4`
- end: `0x180010a29`
- name: `?Read@TXmlReader@@QEAAJPEAW4XmlNodeType@@@Z`
- size: `69`
- prototype: `__int64 __fastcall(TXmlReader *__hidden this, enum XmlNodeType *)`
- caller_count: `7`
- callee_count: `2`
- tags: `registry_config, broker_com_uri`

## callers

- `0x18000a0ac`
- `0x180010a84`
- `0x180010bc8`
- `0x180010c40`
- `0x180010ca0`
- `0x180010d18`
- `0x180010e08`

## callees

- `0x1800109e4`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall TXmlReader::Read(TXmlReader *this, enum XmlNodeType *a2)
{
  __int64 result; // rax

  do
    result = (*(__int64 (__fastcall **)(_QWORD, enum XmlNodeType *))(**(_QWORD **)this + 48LL))(*(_QWORD *)this, a2);
  while ( !(_DWORD)result
       && (*a2 == XmlNodeType_ProcessingInstruction
        || *a2 == XmlNodeType_DocumentType
        || *a2 == XmlNodeType_Whitespace
        || *a2 == XmlNodeType_Comment) );
  return result;
}

```

## disassembly

```asm
0x1800109e4  mov     [rsp+arg_0], rbx
0x1800109e9  push    rdi
0x1800109ea  sub     rsp, 20h
0x1800109ee  mov     rbx, rdx
0x1800109f1  mov     rdi, rcx
0x1800109f4  mov     rcx, [rdi]
0x1800109f7  mov     rdx, rbx
0x1800109fa  mov     rax, [rcx]
0x1800109fd  mov     rax, [rax+30h]
0x180010a01  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a06  test    eax, eax
0x180010a08  jnz     short loc_180010A1E
0x180010a0a  cmp     dword ptr [rbx], 7
0x180010a0d  jz      short loc_1800109F4
0x180010a0f  cmp     dword ptr [rbx], 0Ah
0x180010a12  jz      short loc_1800109F4
0x180010a14  cmp     dword ptr [rbx], 0Dh
0x180010a17  jz      short loc_1800109F4
0x180010a19  cmp     dword ptr [rbx], 8
0x180010a1c  jz      short loc_1800109F4
0x180010a1e  mov     rbx, [rsp+28h+arg_0]
0x180010a23  add     rsp, 20h
0x180010a27  pop     rdi
0x180010a28  retn
```
