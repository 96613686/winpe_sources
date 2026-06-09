# CXMLReader::CreateNode(IXMLNodeSource *,void *,ushort,_XML_NODE_INFO * *)

- ea: `0x180024190`
- end: `0x180024abf`
- name: `?CreateNode@CXMLReader@@UEAAJPEAUIXMLNodeSource@@PEAXGPEAPEAU_XML_NODE_INFO@@@Z`
- size: `2351`
- prototype: `__int64 __usercall@<rax>(CXMLReader *__hidden this@<rcx>, struct IXMLNodeSource *@<rdx>, void *@<r8>, unsigned __int16@<r9w>, struct _XML_NODE_INFO **)`
- caller_count: `0`
- callee_count: `11`
- tags: `registry_config`

## callees

- `0x18001a6c8`
- `0x180024190`
- `0x180025edc`
- `0x180025f98`
- `0x180026270`
- `0x180026318`
- `0x180026efc`
- `0x180027c04`
- `0x180028b08`
- `0x180028ee0`
- `0x18002cd54`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x1800241f6`
- `OLEAUT32!__imp_SysStringLen` at `0x1800241f6`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CXMLReader::CreateNode(
        CXMLReader *this,
        struct IXMLNodeSource *a2,
        struct CParseNode *a3,
        unsigned __int16 a4,
        struct _XML_NODE_INFO **a5)
{
  struct _XML_NODE_INFO *v6; // rsi
  int *v7; // r12
  int v8; // edi
  UINT v10; // eax
  unsigned int *v11; // r14
  unsigned __int16 **v12; // r15
  _DWORD *v13; // r13
  int v14; // ecx
  CXMLReader *v15; // rcx
  _QWORD *v16; // r13
  unsigned __int64 v17; // rcx
  CCollectionList *v18; // r13
  int v19; // edx
  struct CParseNode *Node; // r15
  char v21; // cl
  char v22; // dl
  __int64 i; // rax
  int v24; // r13d
  struct _XML_NODE_INFO *v25; // r14
  unsigned int v26; // r8d
  struct CParseNode *v27; // rdx
  const unsigned __int16 *v28; // r9
  unsigned int v29; // eax
  unsigned int v30; // ecx
  int v31; // r13d
  __int64 v32; // rax
  char IsMatch; // al
  int v34; // r14d
  __int64 v35; // rax
  char v36; // al
  int v37; // r14d
  unsigned int v38; // r8d
  const unsigned __int16 *v39; // rdx
  int v40; // r14d
  int v41; // r14d
  char v42; // [rsp+40h] [rbp-48h]
  char v43; // [rsp+41h] [rbp-47h]
  unsigned int v44; // [rsp+44h] [rbp-44h]
  int v45; // [rsp+48h] [rbp-40h]
  unsigned __int64 v46[2]; // [rsp+50h] [rbp-38h] BYREF

  v44 = 0;
  v6 = *a5;
  v7 = (int *)((char *)this + 480);
  v8 = 1;
  if ( *((_DWORD *)*a5 + 1) != 1 && *v7 != 5 )
    return 0;
  if ( *v7 == 4 )
  {
    v10 = SysStringLen(*((BSTR *)this + 18));
    v11 = (unsigned int *)((char *)v6 + 24);
    v12 = (unsigned __int16 **)((char *)v6 + 16);
    if ( (unsigned __int8)CXMLReader::IsMatch(
                            this,
                            *((_QWORD *)v6 + 2),
                            *((unsigned int *)v6 + 6),
                            0,
                            *((_QWORD *)this + 18),
                            v10,
                            6) )
    {
      *v7 = 5;
      return 0;
    }
    v13 = (_DWORD *)((char *)this + 480);
  }
  else
  {
    v13 = (_DWORD *)((char *)this + 480);
    v11 = (unsigned int *)((char *)v6 + 24);
    v12 = (unsigned __int16 **)((char *)v6 + 16);
  }
  v14 = *v7;
  if ( *v7 == 2 )
  {
    if ( (unsigned __int8)CXMLReader::IsMatch(
                            this,
                            *((_QWORD *)v6 + 2),
                            *((unsigned int *)v6 + 6),
                            *((unsigned int *)v6 + 7),
                            &wszSchema,
                            6,
                            1) )
    {
      if ( CXMLReader::IsRowsetSchema(v15, a5, a4) )
        *v13 = 3;
    }
    else if ( (unsigned __int8)CXMLReader::IsMatch(
                                 this,
                                 *((_QWORD *)v6 + 2),
                                 *((unsigned int *)v6 + 6),
                                 *((unsigned int *)v6 + 7),
                                 L"xml",
                                 3,
                                 6) )
    {
      return (unsigned int)CXMLReader::ProcessNamespaceDcl(this, a5, a4);
    }
    return v44;
  }
  if ( ((v14 - 3) & 0xFFFFFFFD) != 0 )
    return 0;
  if ( v14 != 5 || *((_QWORD *)this + 57) )
  {
LABEL_34:
    if ( *v7 == 3
      && ((unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszExtends, 7, 1)
       || !(unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszElementType, 11, 1)
       && !(unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszAttributeType, 13, 1)
       && !(unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszDataType, 8, 1)
       && !(unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszElement, 7, 1)
       && !(unsigned __int8)CXMLReader::IsMatch(this, *v12, *v11, *((unsigned int *)v6 + 7), &wszAttribute, 9, 1)) )
    {
      return 0;
    }
    Node = 0;
    v21 = 0;
    v42 = 0;
    v22 = 0;
    v43 = 0;
    for ( i = 0; ; i = (unsigned int)(v45 + 1) )
    {
      v45 = i;
      v24 = a4;
      LODWORD(v46[0]) = a4;
      if ( (unsigned int)i >= a4 )
        return 0;
      v25 = a5[i];
      if ( (unsigned int)(*((_DWORD *)v25 + 1) - 1) <= 1 )
      {
        Node = CNodePool::GetNode(*((CNodePool **)this + 51), (struct CNodePool **)this + 51);
        if ( !Node )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048CC0[0] )
            bidTraceW(off_180048208[0], 2775040, off_180048CC0[0], 2147942414LL, 2710);
          ThrowHR(-2147024882);
        }
        if ( *v7 != 5 || *((_BYTE *)this + 400) )
        {
          v30 = *((_DWORD *)v25 + 7);
          v29 = *((_DWORD *)v25 + 6);
          v28 = (const unsigned __int16 *)*((_QWORD *)v25 + 2);
          v26 = *((_DWORD *)v25 + 1);
          if ( v45 )
            v27 = (struct CParseNode *)*((_QWORD *)v6 + 4);
          else
            v27 = a3;
        }
        else
        {
          v26 = *((_DWORD *)v25 + 1);
          if ( v45 )
            v27 = (struct CParseNode *)*((_QWORD *)v6 + 4);
          else
            v27 = a3;
          v28 = 0;
          v29 = 0;
          v30 = 0;
        }
        CParseNode::Init(Node, v27, v26, v28, v29, v30);
        v31 = CCollectionArray::Insert(
                (CXMLReader *)((char *)this + 416),
                *((_DWORD *)this + 110),
                (unsigned __int64)Node);
        if ( v31 < 0 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048CB8[0] )
            bidTraceW(off_180048208[0], 2784256, off_180048CB8[0], (unsigned int)v31, 2719);
          ThrowHR(v31);
        }
        *((_DWORD *)Node + 11) = (*((_DWORD *)this + 110))++;
        v24 = v46[0];
        v21 = v42;
        v22 = v43;
      }
      switch ( *((_DWORD *)v25 + 1) )
      {
        case 1:
          *((_QWORD *)v6 + 4) = Node;
          if ( *v7 == 3 )
          {
            if ( a3 )
              ++*((_DWORD *)a3 + 6);
            if ( (unsigned __int8)CXMLReader::IsMatch(
                                    this,
                                    *((_QWORD *)v25 + 2),
                                    *((unsigned int *)v25 + 6),
                                    *((unsigned int *)v25 + 7),
                                    &wszAttributeType,
                                    13,
                                    1) )
              *((_BYTE *)Node + 40) |= 1u;
          }
          if ( *v7 == 5 && !*((_BYTE *)this + 400) )
          {
            *((_DWORD *)Node + 6) = v24;
            *((_QWORD *)Node + 2) = a5;
            return 0;
          }
          v22 = 0;
          v43 = 0;
          v21 = 0;
          v42 = 0;
          break;
        case 2:
          if ( *v7 == 3 )
          {
            v43 = 0;
            if ( (unsigned __int8)CXMLReader::IsMatch(
                                    this,
                                    *((_QWORD *)v25 + 2),
                                    *((unsigned int *)v25 + 6),
                                    *((unsigned int *)v25 + 7),
                                    &wszName,
                                    4,
                                    1)
              || (unsigned __int8)CXMLReader::IsMatch(
                                    this,
                                    *((_QWORD *)v25 + 2),
                                    *((unsigned int *)v25 + 6),
                                    *((unsigned int *)v25 + 7),
                                    &wszType,
                                    4,
                                    1) )
            {
              v21 = 1;
              v42 = 1;
              v22 = 0;
            }
            else
            {
              v42 = 0;
              v32 = -1;
              do
                ++v32;
              while ( *((_WORD *)&wszContent + v32) );
              IsMatch = CXMLReader::IsMatch(
                          this,
                          *((_QWORD *)v25 + 2),
                          *((unsigned int *)v25 + 6),
                          *((unsigned int *)v25 + 7),
                          &wszContent,
                          v32,
                          6);
              v21 = 0;
              if ( IsMatch )
              {
                v22 = 1;
                v43 = 1;
              }
              else
              {
                v22 = 0;
              }
            }
          }
          break;
        case 0xD:
          if ( *v7 != 3 )
          {
            if ( *v7 != 5 )
              continue;
            v38 = *((_DWORD *)v25 + 6);
            v39 = (const unsigned __int16 *)*((_QWORD *)v25 + 2);
            if ( Node )
            {
              v40 = CParseNode::SetValue(Node, v39, v38);
              if ( v40 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 && off_180048CA0[0] )
                  bidTraceW(off_180048208[0], 2861056, off_180048CA0[0], (unsigned int)v40, 2794);
                ThrowHR(v40);
              }
            }
            else
            {
              v41 = CParseNode::SetValue(a3, v39, v38);
              if ( v41 < 0 )
              {
                if ( (bidGblFlags & 2) != 0 && off_180048C98[0] )
                  bidTraceW(off_180048208[0], 2869248, off_180048C98[0], (unsigned int)v41, 2802);
                ThrowHR(v41);
              }
            }
            goto LABEL_115;
          }
          if ( v21 )
          {
            v34 = CParseNode::SetValue(
                    *((CParseNode **)v6 + 4),
                    *((const unsigned __int16 **)v25 + 2),
                    *((_DWORD *)v25 + 6));
            if ( v34 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180048CB0[0] )
                bidTraceW(off_180048208[0], 2842624, off_180048CB0[0], (unsigned int)v34, 2776);
              ThrowHR(v34);
            }
LABEL_115:
            v21 = v42;
            v22 = v43;
            continue;
          }
          if ( !v22 )
          {
            v37 = CParseNode::SetValue(Node, *((const unsigned __int16 **)v25 + 2), *((_DWORD *)v25 + 6));
            if ( v37 < 0 )
            {
              if ( (bidGblFlags & 2) != 0 && off_180048CA8[0] )
                bidTraceW(off_180048208[0], 2852864, off_180048CA8[0], (unsigned int)v37, 2786);
              ThrowHR(v37);
            }
            goto LABEL_115;
          }
          v35 = -1;
          do
            ++v35;
          while ( *((_WORD *)&wszTextOnly + v35) );
          v36 = CXMLReader::IsMatch(
                  this,
                  *((_QWORD *)v25 + 2),
                  *((unsigned int *)v25 + 6),
                  *((unsigned int *)v25 + 7),
                  &wszTextOnly,
                  v35,
                  6);
          v21 = v42;
          v22 = v43;
          if ( v36 )
            *(_BYTE *)(*((_QWORD *)v6 + 4) + 40LL) |= 1u;
          break;
        default:
          continue;
      }
    }
  }
  v16 = (_QWORD *)((char *)this + 136);
  v11 = (unsigned int *)((char *)v6 + 24);
  v12 = (unsigned __int16 **)((char *)v6 + 16);
  v46[0] = 0;
  CCollectionList::LookUpByKey(
    *((CCollectionList **)this + 17),
    *((unsigned __int16 **)v6 + 2),
    *((_DWORD *)v6 + 6),
    v46);
  v17 = v46[0];
  *((_QWORD *)this + 57) = v46[0];
  if ( !v17 )
  {
    v46[0] = 0;
    CCollectionList::LookUpByKey((CXMLReader *)((char *)this + 80), *v12, *v11, v46);
    v17 = v46[0];
    *((_QWORD *)this + 57) = v46[0];
  }
  if ( v17 )
  {
LABEL_27:
    v19 = *(_DWORD *)v17;
    if ( (unsigned int)(*(_DWORD *)v17 - 5) <= 1 )
    {
      if ( v19 != 6 )
        v8 = 4;
      *((_DWORD *)this + 119) = v8;
      *((_QWORD *)this + 57) = 0;
      return 0;
    }
    if ( v19 == 1 )
      *v16 = *(_QWORD *)(*(_QWORD *)(v17 + 8) + 632LL);
    goto LABEL_34;
  }
  v18 = *(CCollectionList **)(*((_QWORD *)this + 17) + 48LL);
  while ( v18 )
  {
    v46[0] = 0;
    CCollectionList::LookUpByKey(v18, *((unsigned __int16 **)v6 + 2), *((_DWORD *)v6 + 6), v46);
    v17 = v46[0];
    *((_QWORD *)this + 57) = v46[0];
    v18 = (CCollectionList *)*((_QWORD *)v18 + 6);
    if ( v17 )
    {
      v16 = (_QWORD *)((char *)this + 136);
      goto LABEL_27;
    }
  }
  return 0;
}

```

## disassembly

```asm
0x180024190  mov     rax, rsp
0x180024193  mov     [rax+8], rbx
0x180024197  mov     [rax+10h], rsi
0x18002419b  mov     [rax+20h], r9w
0x1800241a0  mov     [rax+18h], r8
0x1800241a4  push    rdi
0x1800241a5  push    r12
0x1800241a7  push    r13
0x1800241a9  push    r14
0x1800241ab  push    r15
0x1800241ad  sub     rsp, 60h
0x1800241b1  mov     rbx, rcx
0x1800241b4  mov     [rsp+88h+var_44], 0
0x1800241bc  mov     rax, [rsp+88h+arg_20]
0x1800241c4  mov     rsi, [rax]
0x1800241c7  lea     r12, [rcx+1E0h]
0x1800241ce  mov     edi, 1
0x1800241d3  cmp     [rsi+4], edi
0x1800241d6  jz      short loc_1800241E8
0x1800241d8  cmp     dword ptr [r12], 5
0x1800241dd  jz      short loc_1800241E8
0x1800241df  mov     eax, [rsp+88h+var_44]
0x1800241e3  jmp     loc_180024AA5
0x1800241e8  cmp     dword ptr [r12], 4
0x1800241ed  jnz     short loc_18002424B
0x1800241ef  mov     rcx, [rcx+90h]; pbstr
0x1800241f6  call    cs:__imp_SysStringLen
0x1800241fc  lea     r14, [rsi+18h]
0x180024200  lea     r15, [rsi+10h]
0x180024204  mov     [rsp+88h+var_58], 6
0x18002420c  mov     [rsp+88h+var_60], eax
0x180024210  mov     rax, [rbx+90h]
0x180024217  mov     qword ptr [rsp+88h+var_68], rax
0x18002421c  xor     r9d, r9d
0x18002421f  mov     r8d, [r14]
0x180024222  mov     rdx, [r15]
0x180024225  mov     rcx, rbx
0x180024228  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x18002422d  test    al, al
0x18002422f  jz      short loc_180024242
0x180024231  mov     dword ptr [r12], 5
0x180024239  mov     eax, [rsp+88h+var_44]
0x18002423d  jmp     loc_180024AA5
0x180024242  lea     r13, [rbx+1E0h]
0x180024249  jmp     short loc_180024256
0x18002424b  mov     r13, r12
0x18002424e  lea     r14, [rsi+18h]
0x180024252  lea     r15, [rsi+10h]
0x180024256  mov     ecx, [r12]
0x18002425a  cmp     ecx, 2
0x18002425d  jnz     loc_180024311
0x180024263  mov     [rsp+88h+var_58], edi
0x180024267  mov     [rsp+88h+var_60], 6
0x18002426f  lea     rax, ?wszSchema@@3PAGA; "Schema"
0x180024276  mov     qword ptr [rsp+88h+var_68], rax
0x18002427b  mov     r9d, [rsi+1Ch]
0x18002427f  mov     r8d, [rsi+18h]
0x180024283  mov     rdx, [rsi+10h]
0x180024287  mov     rcx, rbx
0x18002428a  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x18002428f  test    al, al
0x180024291  jz      short loc_1800242B7
0x180024293  movzx   r8d, [rsp+88h+arg_18]; unsigned int
0x18002429c  mov     rdx, [rsp+88h+arg_20]; struct _XML_NODE_INFO **
0x1800242a4  call    ?IsRowsetSchema@CXMLReader@@AEAA_NPEAPEAU_XML_NODE_INFO@@K@Z; CXMLReader::IsRowsetSchema(_XML_NODE_INFO * *,ulong)
0x1800242a9  test    al, al
0x1800242ab  jz      short loc_180024308
0x1800242ad  mov     dword ptr [r13+0], 3
0x1800242b5  jmp     short loc_180024308
0x1800242b7  mov     [rsp+88h+var_58], 6
0x1800242bf  mov     [rsp+88h+var_60], 3
0x1800242c7  lea     rax, aXml; "xml"
0x1800242ce  mov     qword ptr [rsp+88h+var_68], rax
0x1800242d3  mov     r9d, [rsi+1Ch]
0x1800242d7  mov     r8d, [rsi+18h]
0x1800242db  mov     rdx, [rsi+10h]
0x1800242df  mov     rcx, rbx
0x1800242e2  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x1800242e7  test    al, al
0x1800242e9  jz      short loc_180024308
0x1800242eb  movzx   r8d, [rsp+88h+arg_18]; unsigned int
0x1800242f4  mov     rdx, [rsp+88h+arg_20]; struct _XML_NODE_INFO **
0x1800242fc  mov     rcx, rbx; this
0x1800242ff  call    ?ProcessNamespaceDcl@CXMLReader@@AEAAJPEAPEAU_XML_NODE_INFO@@K@Z; CXMLReader::ProcessNamespaceDcl(_XML_NODE_INFO * *,ulong)
0x180024304  mov     [rsp+88h+var_44], eax
0x180024308  mov     eax, [rsp+88h+var_44]
0x18002430c  jmp     loc_180024AA5
0x180024311  lea     eax, [rcx-3]
0x180024314  test    eax, 0FFFFFFFDh
0x180024319  jnz     loc_18002479A
0x18002431f  xor     r13d, r13d
0x180024322  cmp     ecx, 5
0x180024325  jnz     loc_180024443
0x18002432b  cmp     [rbx+1C8h], r13
0x180024332  jnz     loc_180024443
0x180024338  lea     r13, [rbx+88h]
0x18002433f  lea     r14, [rsi+18h]
0x180024343  lea     r15, [rsi+10h]
0x180024347  mov     [rsp+88h+var_38], 0
0x180024350  lea     r9, [rsp+88h+var_38]; unsigned __int64 *
0x180024355  mov     r8d, [r14]; unsigned int
0x180024358  mov     rdx, [r15]; unsigned __int16 *
0x18002435b  mov     rcx, [r13+0]; this
0x18002435f  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180024364  mov     rcx, [rsp+88h+var_38]
0x180024369  mov     [rbx+1C8h], rcx
0x180024370  xor     r8d, r8d
0x180024373  test    rcx, rcx
0x180024376  jnz     short loc_1800243A9
0x180024378  mov     [rsp+88h+var_38], r8
0x18002437d  lea     rcx, [rbx+50h]; this
0x180024381  lea     r9, [rsp+88h+var_38]; unsigned __int64 *
0x180024386  mov     r8d, [r14]; unsigned int
0x180024389  mov     rdx, [r15]; unsigned __int16 *
0x18002438c  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180024391  mov     rcx, [rsp+88h+var_38]
0x180024396  mov     [rbx+1C8h], rcx
0x18002439d  lea     rax, [rbx+88h]
0x1800243a4  xor     r8d, r8d
0x1800243a7  jmp     short loc_1800243AC
0x1800243a9  mov     rax, r13
0x1800243ac  test    rcx, rcx
0x1800243af  jnz     short loc_180024401
0x1800243b1  mov     rax, [rax]
0x1800243b4  mov     r13, [rax+30h]
0x1800243b8  test    r13, r13
0x1800243bb  jz      short loc_1800243F8
0x1800243bd  mov     [rsp+88h+var_38], r8
0x1800243c2  lea     r9, [rsp+88h+var_38]; unsigned __int64 *
0x1800243c7  mov     r8d, [rsi+18h]; unsigned int
0x1800243cb  mov     rdx, [rsi+10h]; unsigned __int16 *
0x1800243cf  mov     rcx, r13; this
0x1800243d2  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x1800243d7  mov     rcx, [rsp+88h+var_38]
0x1800243dc  mov     [rbx+1C8h], rcx
0x1800243e3  mov     r13, [r13+30h]
0x1800243e7  xor     r8d, r8d
0x1800243ea  test    rcx, rcx
0x1800243ed  jz      short loc_1800243B8
0x1800243ef  lea     r13, [rbx+88h]
0x1800243f6  jmp     short loc_180024401
0x1800243f8  mov     eax, [rsp+88h+var_44]
0x1800243fc  jmp     loc_180024AA5
0x180024401  mov     edx, [rcx]
0x180024403  lea     eax, [rdx-5]
0x180024406  cmp     eax, edi
0x180024408  jbe     short loc_180024422
0x18002440a  cmp     edx, edi
0x18002440c  jnz     short loc_18002441D
0x18002440e  mov     rax, [rcx+8]
0x180024412  mov     rcx, [rax+278h]
0x180024419  mov     [r13+0], rcx
0x18002441d  xor     r13d, r13d
0x180024420  jmp     short loc_180024443
0x180024422  cmp     edx, 6
0x180024425  mov     eax, 4
0x18002442a  cmovnz  edi, eax
0x18002442d  mov     [rbx+1DCh], edi
0x180024433  mov     [rbx+1C8h], r8
0x18002443a  mov     eax, [rsp+88h+var_44]
0x18002443e  jmp     loc_180024AA5
0x180024443  cmp     dword ptr [r12], 3
0x180024448  jnz     loc_18002457A
0x18002444e  mov     [rsp+88h+var_58], edi
0x180024452  mov     [rsp+88h+var_60], 7
0x18002445a  lea     rax, ?wszExtends@@3PAGA; "extends"
0x180024461  mov     qword ptr [rsp+88h+var_68], rax
0x180024466  mov     r9d, [rsi+1Ch]
0x18002446a  mov     r8d, [r14]
0x18002446d  mov     rdx, [r15]
0x180024470  mov     rcx, rbx
0x180024473  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180024478  test    al, al
0x18002447a  jnz     loc_180024571
0x180024480  mov     [rsp+88h+var_58], edi
0x180024484  mov     [rsp+88h+var_60], 0Bh
0x18002448c  lea     rax, ?wszElementType@@3PAGA; "ElementType"
0x180024493  mov     qword ptr [rsp+88h+var_68], rax
0x180024498  mov     r9d, [rsi+1Ch]
0x18002449c  mov     r8d, [r14]
0x18002449f  mov     rdx, [r15]
0x1800244a2  mov     rcx, rbx
0x1800244a5  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x1800244aa  test    al, al
0x1800244ac  jnz     loc_18002457A
0x1800244b2  mov     [rsp+88h+var_58], edi
0x1800244b6  mov     [rsp+88h+var_60], 0Dh
0x1800244be  lea     r13, ?wszAttributeType@@3PAGA; "AttributeType"
0x1800244c5  mov     qword ptr [rsp+88h+var_68], r13
0x1800244ca  mov     r9d, [rsi+1Ch]
0x1800244ce  mov     r8d, [r14]
0x1800244d1  mov     rdx, [r15]
0x1800244d4  mov     rcx, rbx
0x1800244d7  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x1800244dc  xor     r13d, r13d
0x1800244df  test    al, al
0x1800244e1  jnz     loc_18002457A
0x1800244e7  mov     [rsp+88h+var_58], edi
0x1800244eb  mov     [rsp+88h+var_60], 8
0x1800244f3  lea     rax, ?wszDataType@@3PAGA; "datatype"
0x1800244fa  mov     qword ptr [rsp+88h+var_68], rax
0x1800244ff  mov     r9d, [rsi+1Ch]
0x180024503  mov     r8d, [r14]
0x180024506  mov     rdx, [r15]
0x180024509  mov     rcx, rbx
0x18002450c  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180024511  test    al, al
0x180024513  jnz     short loc_18002457A
0x180024515  mov     [rsp+88h+var_58], edi
0x180024519  mov     [rsp+88h+var_60], 7
0x180024521  lea     rax, ?wszElement@@3PAGA; "element"
0x180024528  mov     qword ptr [rsp+88h+var_68], rax
0x18002452d  mov     r9d, [rsi+1Ch]
0x180024531  mov     r8d, [r14]
0x180024534  mov     rdx, [r15]
0x180024537  mov     rcx, rbx
0x18002453a  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x18002453f  test    al, al
0x180024541  jnz     short loc_18002457A
0x180024543  mov     [rsp+88h+var_58], edi
0x180024547  mov     [rsp+88h+var_60], 9
0x18002454f  lea     rax, ?wszAttribute@@3PAGA; "attribute"
0x180024556  mov     qword ptr [rsp+88h+var_68], rax
0x18002455b  mov     r9d, [rsi+1Ch]
0x18002455f  mov     r8d, [r14]
0x180024562  mov     rdx, [r15]
0x180024565  mov     rcx, rbx
0x180024568  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x18002456d  test    al, al
0x18002456f  jnz     short loc_18002457A
0x180024571  mov     eax, [rsp+88h+var_44]
0x180024575  jmp     loc_180024AA5
0x18002457a  mov     r15, r13
0x18002457d  mov     cl, r13b
0x180024580  mov     [rsp+88h+var_48], cl
0x180024584  mov     dl, r13b
0x180024587  mov     [rsp+88h+var_47], dl
0x18002458b  mov     eax, r13d
0x18002458e  lea     r9, ?wszTextOnly@@3PAGA; "textOnly"
0x180024595  mov     [rsp+88h+var_40], eax
0x180024599  movzx   r13d, [rsp+88h+arg_18]
0x1800245a2  mov     dword ptr [rsp+88h+var_38], r13d
0x1800245a7  cmp     eax, r13d
0x1800245aa  jnb     loc_18002479A
0x1800245b0  mov     r8, [rsp+88h+arg_20]
0x1800245b8  mov     r14, [r8+rax*8]
0x1800245bc  mov     eax, [r14+4]
0x1800245c0  sub     eax, edi
0x1800245c2  cmp     eax, edi
0x1800245c4  ja      loc_18002471B
0x1800245ca  lea     rcx, [rbx+198h]
0x1800245d1  mov     rdx, rcx; struct CNodePool **
0x1800245d4  mov     rcx, [rcx]; this
0x1800245d7  call    ?GetNode@CNodePool@@QEAAPEAVCParseNode@@PEAPEAV1@@Z; CNodePool::GetNode(CNodePool * *)
0x1800245dc  mov     r15, rax
0x1800245df  xor     r10d, r10d
0x1800245e2  test    rax, rax
0x1800245e5  jnz     short loc_18002462C
0x1800245e7  test    byte ptr cs:_bidGblFlags, 2
0x1800245ee  jz      short loc_180024622
0x1800245f0  mov     rax, cs:off_180048CC0; "<CXMLReader::CreateNode|ADO|ERR>  HRESU"...
0x1800245f7  test    rax, rax
0x1800245fa  jz      short loc_180024622
0x1800245fc  mov     [rsp+88h+var_68], 0A96h
0x180024604  mov     r9d, 8007000Eh
0x18002460a  mov     r8, cs:off_180048CC0; "<CXMLReader::CreateNode|ADO|ERR>  HRESU"...
0x180024611  mov     edx, 2A5800h
0x180024616  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002461d  call    _bidTraceW
0x180024622  mov     ecx, 8007000Eh; int
0x180024627  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x18002462c  cmp     dword ptr [r12], 5
0x180024631  jnz     short loc_180024660
0x180024633  cmp     [rbx+190h], r10b
0x18002463a  jnz     short loc_180024660
0x18002463c  mov     r8d, [r14+4]
0x180024640  cmp     [rsp+88h+var_40], r10d
0x180024645  jz      short loc_18002464D
0x180024647  mov     rdx, [rsi+20h]
0x18002464b  jmp     short loc_180024655
0x18002464d  mov     rdx, [rsp+88h+arg_10]
0x180024655  mov     r9, r10
0x180024658  mov     eax, r10d
0x18002465b  mov     ecx, r10d
0x18002465e  jmp     short loc_180024685
0x180024660  mov     ecx, [r14+1Ch]
0x180024664  mov     eax, [r14+18h]
0x180024668  mov     r9, [r14+10h]; unsigned __int16 *
0x18002466c  mov     r8d, [r14+4]; unsigned int
0x180024670  cmp     [rsp+88h+var_40], r10d
0x180024675  jz      short loc_18002467D
0x180024677  mov     rdx, [rsi+20h]
0x18002467b  jmp     short loc_180024685
0x18002467d  mov     rdx, [rsp+88h+arg_10]; struct CParseNode *
0x180024685  mov     [rsp+88h+var_60], ecx; unsigned int
0x180024689  mov     [rsp+88h+var_68], eax; unsigned int
0x18002468d  mov     rcx, r15; this
0x180024690  call    ?Init@CParseNode@@QEAAJPEAV1@KPEBGKK@Z; CParseNode::Init(CParseNode *,ulong,ushort const *,ulong,ulong)
0x180024695  lea     rax, [rbx+1A0h]
0x18002469c  mov     r8, r15; unsigned __int64
  ... truncated ...
```
