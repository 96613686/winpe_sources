# CXMLReader::EndChildren(IXMLNodeSource *,int,_XML_NODE_INFO *)

- ea: `0x1800250f0`
- end: `0x18002532e`
- name: `?EndChildren@CXMLReader@@UEAAJPEAUIXMLNodeSource@@HPEAU_XML_NODE_INFO@@@Z`
- size: `574`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct IXMLNodeSource *, int, struct _XML_NODE_INFO *)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, registry_config`

## callees

- `0x180015fb4`
- `0x1800250f0`
- `0x180026270`
- `0x180027944`
- `0x18002809c`
- `0x180030010`

## string_xrefs

- `0x1800251e3`: `delete`

## pseudocode

```c
__int64 __fastcall CXMLReader::EndChildren(
        CXMLReader *this,
        struct IXMLNodeSource *a2,
        int a3,
        struct _XML_NODE_INFO *a4)
{
  __int64 v4; // rsi
  unsigned int v5; // ebp
  __int64 v8; // rax
  __int64 v9; // rcx
  __int64 v10; // rcx
  __int64 v11; // r9
  __int64 v12; // r8
  __int64 v13; // rdx
  __int64 v14; // rax
  __int64 v15; // rcx
  __int64 v16; // rcx

  v4 = *((_QWORD *)a4 + 4);
  v5 = 0;
  if ( *((_DWORD *)this + 120) == 5 )
  {
    if ( v4 )
    {
      if ( *((_BYTE *)this + 400) )
        *(_DWORD *)(v4 + 24) = *((_DWORD *)this + 108);
      if ( a3 && !*((_BYTE *)this + 400) )
      {
        *(_DWORD *)(v4 + 8) = 0;
        *(_BYTE *)(v4 + 40) = 5;
      }
      v8 = *((_QWORD *)this + 58);
      if ( !v8 || v4 == v8 )
      {
        v9 = *(_QWORD *)(*((_QWORD *)this + 17) + 48LL);
        if ( v9 )
          *((_QWORD *)this + 17) = v9;
        v10 = *((_QWORD *)this + 56);
        *((_BYTE *)this + 400) = 0;
        *((_QWORD *)this + 58) = 0;
        (*(void (__fastcall **)(__int64, struct IXMLNodeSource *))(*(_QWORD *)v10 + 208LL))(v10, a2);
      }
    }
    else if ( !a3
           && (*((_DWORD *)this + 119) == 1
            && (unsigned __int8)CXMLReader::IsMatch(
                                  this,
                                  *((_QWORD *)a4 + 2),
                                  *((unsigned int *)a4 + 6),
                                  *((unsigned int *)a4 + 7),
                                  &wszInsert,
                                  6,
                                  3)
            || *((_DWORD *)this + 119) == 4
            && (unsigned __int8)CXMLReader::IsMatch(
                                  this,
                                  *((_QWORD *)a4 + 2),
                                  *((unsigned int *)a4 + 6),
                                  *((unsigned int *)a4 + 7),
                                  &wszDelete,
                                  6,
                                  3)) )
    {
      *((_DWORD *)this + 119) = 8;
    }
  }
  if ( *((_DWORD *)this + 120) == 3 )
  {
    v11 = *((unsigned int *)a4 + 7);
    v12 = *((unsigned int *)a4 + 6);
    v13 = *((_QWORD *)a4 + 2);
    if ( v4 )
    {
      if ( (unsigned __int8)CXMLReader::IsMatch(this, v13, v12, v11, &wszElementType, 11, 1)
        || (unsigned __int8)CXMLReader::IsMatch(
                              this,
                              *((_QWORD *)a4 + 2),
                              *((unsigned int *)a4 + 6),
                              *((unsigned int *)a4 + 7),
                              &wszAttributeType,
                              13,
                              1) )
      {
        return (unsigned int)CXMLReader::ResolveSymbol(this, (struct CParseNode *)v4);
      }
    }
    else if ( (unsigned __int8)CXMLReader::IsMatch(this, v13, v12, v11, &wszSchema, 6, 1) )
    {
      if ( *((_BYTE *)this + 472) )
      {
        v14 = *((_QWORD *)this + 17);
        v15 = 0;
        if ( *(_DWORD *)(v14 + 16) )
          v15 = **(_QWORD **)(v14 + 8);
        if ( !(unsigned int)CXMLRowset::AllColumnsInitialized(*(CXMLRowset **)(v15 + 8)) )
        {
          v5 = -2147467259;
          Exit(-2147467259, 0x91u);
        }
      }
      v16 = *((_QWORD *)this + 56);
      *((_DWORD *)this + 120) = 4;
      (*(void (__fastcall **)(__int64))(*(_QWORD *)v16 + 208LL))(v16);
    }
  }
  return v5;
}

```

## disassembly

```asm
0x1800250f0  push    rbx
0x1800250f2  push    rbp
0x1800250f3  push    rsi
0x1800250f4  push    rdi
0x1800250f5  sub     rsp, 48h
0x1800250f9  mov     rsi, [r9+20h]
0x1800250fd  xor     ebp, ebp
0x1800250ff  cmp     dword ptr [rcx+1E0h], 5
0x180025106  mov     rdi, r9
0x180025109  mov     rbx, rcx
0x18002510c  jnz     loc_18002521D
0x180025112  test    rsi, rsi
0x180025115  jz      short loc_180025193
0x180025117  cmp     [rcx+190h], bpl
0x18002511e  jz      short loc_180025129
0x180025120  mov     eax, [rcx+1B0h]
0x180025126  mov     [rsi+18h], eax
0x180025129  test    r8d, r8d
0x18002512c  jz      short loc_18002513E
0x18002512e  cmp     [rcx+190h], bpl
0x180025135  jnz     short loc_18002513E
0x180025137  mov     [rsi+8], ebp
0x18002513a  mov     byte ptr [rsi+28h], 5
0x18002513e  mov     rax, [rcx+1D0h]
0x180025145  test    rax, rax
0x180025148  jz      short loc_180025153
0x18002514a  cmp     rsi, rax
0x18002514d  jnz     loc_18002521D
0x180025153  mov     rax, [rcx+88h]
0x18002515a  mov     rcx, [rax+30h]
0x18002515e  test    rcx, rcx
0x180025161  jz      short loc_18002516A
0x180025163  mov     [rbx+88h], rcx
0x18002516a  mov     rcx, [rbx+1C0h]
0x180025171  mov     [rbx+190h], bpl
0x180025178  mov     [rbx+1D0h], rbp
0x18002517f  mov     rax, [rcx]
0x180025182  mov     rax, [rax+0D0h]
0x180025189  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002518e  jmp     loc_18002521D
0x180025193  test    r8d, r8d
0x180025196  jnz     loc_18002521D
0x18002519c  cmp     dword ptr [rcx+1DCh], 1
0x1800251a3  jnz     short loc_1800251D6
0x1800251a5  mov     r9d, [r9+1Ch]
0x1800251a9  lea     rax, ?wszInsert@@3PAGA; "insert"
0x1800251b0  mov     r8d, [rdi+18h]
0x1800251b4  mov     rdx, [rdi+10h]
0x1800251b8  mov     [rsp+68h+var_38], 3
0x1800251c0  mov     [rsp+68h+var_40], 6
0x1800251c8  mov     [rsp+68h+var_48], rax
0x1800251cd  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x1800251d2  test    al, al
0x1800251d4  jnz     short loc_180025213
0x1800251d6  cmp     dword ptr [rbx+1DCh], 4
0x1800251dd  jnz     short loc_18002521D
0x1800251df  mov     r9d, [rdi+1Ch]
0x1800251e3  lea     rax, ?wszDelete@@3PAGA; "delete"
0x1800251ea  mov     r8d, [rdi+18h]
0x1800251ee  mov     rcx, rbx
0x1800251f1  mov     rdx, [rdi+10h]
0x1800251f5  mov     [rsp+68h+var_38], 3
0x1800251fd  mov     [rsp+68h+var_40], 6
0x180025205  mov     [rsp+68h+var_48], rax
0x18002520a  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x18002520f  test    al, al
0x180025211  jz      short loc_18002521D
0x180025213  mov     dword ptr [rbx+1DCh], 8
0x18002521d  cmp     dword ptr [rbx+1E0h], 3
0x180025224  jnz     loc_180025323
0x18002522a  mov     r9d, [rdi+1Ch]
0x18002522e  mov     rcx, rbx
0x180025231  mov     r8d, [rdi+18h]
0x180025235  mov     rdx, [rdi+10h]
0x180025239  mov     [rsp+68h+var_38], 1
0x180025241  test    rsi, rsi
0x180025244  jz      short loc_1800252AA
0x180025246  lea     rax, ?wszElementType@@3PAGA; "ElementType"
0x18002524d  mov     [rsp+68h+var_40], 0Bh
0x180025255  mov     [rsp+68h+var_48], rax
0x18002525a  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x18002525f  test    al, al
0x180025261  jnz     short loc_18002529B
0x180025263  mov     r9d, [rdi+1Ch]
0x180025267  lea     rax, ?wszAttributeType@@3PAGA; "AttributeType"
0x18002526e  mov     r8d, [rdi+18h]
0x180025272  mov     rcx, rbx
0x180025275  mov     rdx, [rdi+10h]
0x180025279  mov     [rsp+68h+var_38], 1
0x180025281  mov     [rsp+68h+var_40], 0Dh
0x180025289  mov     [rsp+68h+var_48], rax
0x18002528e  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180025293  test    al, al
0x180025295  jz      loc_180025323
0x18002529b  mov     rdx, rsi; struct CParseNode *
0x18002529e  mov     rcx, rbx; this
0x1800252a1  call    ?ResolveSymbol@CXMLReader@@AEAAJPEAVCParseNode@@@Z; CXMLReader::ResolveSymbol(CParseNode *)
0x1800252a6  mov     ebp, eax
0x1800252a8  jmp     short loc_180025323
0x1800252aa  lea     rax, ?wszSchema@@3PAGA; "Schema"
0x1800252b1  mov     [rsp+68h+var_40], 6
0x1800252b9  mov     [rsp+68h+var_48], rax
0x1800252be  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x1800252c3  test    al, al
0x1800252c5  jz      short loc_180025323
0x1800252c7  cmp     [rbx+1D8h], bpl
0x1800252ce  jz      short loc_180025303
0x1800252d0  mov     rax, [rbx+88h]
0x1800252d7  xor     ecx, ecx
0x1800252d9  cmp     [rax+10h], ecx
0x1800252dc  jbe     short loc_1800252E5
0x1800252de  mov     rax, [rax+8]
0x1800252e2  mov     rcx, [rax]
0x1800252e5  mov     rcx, [rcx+8]; this
0x1800252e9  call    ?AllColumnsInitialized@CXMLRowset@@QEAAHXZ; CXMLRowset::AllColumnsInitialized(void)
0x1800252ee  test    eax, eax
0x1800252f0  jnz     short loc_180025303
0x1800252f2  mov     ebp, 80004005h
0x1800252f7  mov     edx, 91h; unsigned int
0x1800252fc  mov     ecx, ebp; int
0x1800252fe  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180025303  mov     rcx, [rbx+1C0h]
0x18002530a  mov     dword ptr [rbx+1E0h], 4
0x180025314  mov     rax, [rcx]
0x180025317  mov     rax, [rax+0D0h]
0x18002531e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025323  mov     eax, ebp
0x180025325  add     rsp, 48h
0x180025329  pop     rdi
0x18002532a  pop     rsi
0x18002532b  pop     rbp
0x18002532c  pop     rbx
0x18002532d  retn
```
