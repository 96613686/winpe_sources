# TXmlReader::IsNodeType(XmlNodeType)

- ea: `0x1800109a4`
- end: `0x1800109dc`
- name: `?IsNodeType@TXmlReader@@QEAAJW4XmlNodeType@@@Z`
- size: `56`
- prototype: `__int64 __fastcall(TXmlReader *__hidden this, enum XmlNodeType)`
- caller_count: `5`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x180010a84`
- `0x180010bc8`
- `0x180010c40`
- `0x180010d18`
- `0x180010e08`

## callees

- `0x1800109a4`
- `0x180014010`

## pseudocode

```c
__int64 __fastcall TXmlReader::IsNodeType(TXmlReader *this, enum XmlNodeType a2)
{
  __int64 v2; // rcx
  __int64 result; // rax
  int v5; // [rsp+30h] [rbp+8h] BYREF

  v2 = *(_QWORD *)this;
  v5 = 0;
  result = (*(__int64 (__fastcall **)(__int64, int *))(*(_QWORD *)v2 + 56LL))(v2, &v5);
  if ( !(_DWORD)result && v5 != a2 )
    return 1;
  return result;
}

```

## disassembly

```asm
0x1800109a4  push    rbx
0x1800109a6  sub     rsp, 20h
0x1800109aa  mov     rcx, [rcx]
0x1800109ad  mov     ebx, edx
0x1800109af  mov     [rsp+28h+arg_0], 0
0x1800109b7  lea     rdx, [rsp+28h+arg_0]
0x1800109bc  mov     rax, [rcx]
0x1800109bf  mov     rax, [rax+38h]
0x1800109c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800109c8  test    eax, eax
0x1800109ca  jnz     short loc_1800109D6
0x1800109cc  cmp     [rsp+28h+arg_0], ebx
0x1800109d0  lea     ecx, [rax+1]
0x1800109d3  cmovnz  eax, ecx
0x1800109d6  add     rsp, 20h
0x1800109da  pop     rbx
0x1800109db  retn
```
