# CXMLReader::GetData(CXMLRowset *,CParseNode *)

- ea: `0x180025d2c`
- end: `0x180025ed3`
- name: `?GetData@CXMLReader@@QEAAJPEAVCXMLRowset@@PEAVCParseNode@@@Z`
- size: `423`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CXMLRowset *, struct CParseNode *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config`

## callers

- `0x180025654`

## callees

- `0x180025d2c`
- `0x180025f80`
- `0x18002769c`
- `0x180028ee0`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180025d5d`
- `OLEAUT32!__imp_SysStringLen` at `0x180025da8`
- `OLEAUT32!__imp_SysStringLen` at `0x180025e6f`
- `OLEAUT32!__imp_SysStringLen` at `0x180025d5d`
- `OLEAUT32!__imp_SysStringLen` at `0x180025da8`
- `OLEAUT32!__imp_SysStringLen` at `0x180025e6f`

## pseudocode

```c
__int64 __fastcall CXMLReader::GetData(CXMLReader *this, struct CXMLRowset *a2, struct CParseNode *a3)
{
  _DWORD *v3; // r14
  OLECHAR *v5; // rcx
  CCollectionList *v8; // rbx
  UINT v9; // eax
  unsigned __int16 *v10; // rdx
  UINT v12; // eax
  int v13; // r15d
  __int64 v14; // rbx
  _QWORD *v15; // rdx
  BSTR *Value; // rax
  UINT v17; // eax
  unsigned int v18; // r14d
  __int64 v19; // rbx
  __int64 v20; // rdx
  unsigned __int64 v21; // [rsp+60h] [rbp+18h] BYREF
  unsigned __int64 v22; // [rsp+68h] [rbp+20h] BYREF

  v3 = 0;
  v5 = (OLECHAR *)*((_QWORD *)a3 + 4);
  v21 = 0;
  if ( v5
    && (v8 = (CCollectionList *)*((_QWORD *)this + 17),
        v9 = SysStringLen(v5),
        v10 = (unsigned __int16 *)*((_QWORD *)a3 + 4),
        v22 = 0,
        CCollectionList::LookUpByKey(v8, v10, v9, &v22),
        (v3 = (_DWORD *)v22) != 0)
    || *((_DWORD *)this + 119) != 2 )
  {
    v12 = SysStringLen(*((BSTR *)a3 + 4));
    v13 = CCollectionList::LookUpByKey(
            (struct CXMLRowset *)((char *)a2 + 552),
            *((unsigned __int16 **)a3 + 4),
            v12,
            &v21);
    if ( v13 >= 0 )
    {
      if ( ((*((_DWORD *)this + 119) - 4) & 0xFFFFFFFB) != 0 )
        v14 = *(_QWORD *)(*((_QWORD *)a2 + 35) + 8LL * (unsigned int)v21);
      else
        v14 = *(_QWORD *)(*((_QWORD *)a2 + 36) + 8LL * (unsigned int)v21);
      if ( *v3 == 1 )
      {
        v15 = *(_QWORD **)(*((_QWORD *)a2 + 68) + 8LL * (unsigned int)v21);
        if ( !v15[2] )
        {
          v15[2] = a3;
          *(_QWORD *)(v14 + 8) = v15;
          *(_DWORD *)(*v15 + 612LL) = 0;
          *(_DWORD *)(*v15 + 248LL) = 0;
          *((_DWORD *)v15 + 2) = *((_DWORD *)a3 + 11);
        }
      }
      else
      {
        *(_DWORD *)(v14 + 4) = 0;
        *(_QWORD *)(v14 + 8) = *(_QWORD *)CParseNode::GetValue(a3);
        Value = (BSTR *)CParseNode::GetValue(a3);
        v17 = SysStringLen(*Value);
        *(_DWORD *)v14 = v17;
        if ( !v17 && *((_DWORD *)this + 119) == 2 && *((_DWORD *)a3 + 2) == 1 )
        {
          v18 = *((_DWORD *)this + 108);
          LODWORD(v19) = *((_DWORD *)a3 + 11);
          while ( 1 )
          {
            v19 = (unsigned int)(v19 + 1);
            if ( (unsigned int)v19 >= v18 )
              break;
            v20 = *(_QWORD *)(*((_QWORD *)this + 53) + 8 * v19);
            if ( *(_DWORD *)(v20 + 8) == 2 && *(struct CParseNode **)(v20 + 16) == a3 )
              CXMLReader::ProcessRowsetAttribute(this, (struct CParseNode *)v20, a2);
          }
        }
      }
    }
    return (unsigned int)v13;
  }
  else
  {
    CXMLReader::ProcessRowsetAttribute(this, a3, a2);
    return 0;
  }
}

```

## disassembly

```asm
0x180025d2c  mov     [rsp+arg_0], rbx
0x180025d31  push    rbp
0x180025d32  push    rsi
0x180025d33  push    rdi
0x180025d34  push    r14
0x180025d36  push    r15
0x180025d38  sub     rsp, 20h
0x180025d3c  xor     r14d, r14d
0x180025d3f  mov     rsi, rcx
0x180025d42  mov     rcx, [r8+20h]; pbstr
0x180025d46  mov     rdi, r8
0x180025d49  mov     [rsp+48h+arg_10], r14
0x180025d4e  mov     rbp, rdx
0x180025d51  test    rcx, rcx
0x180025d54  jz      short loc_180025D86
0x180025d56  mov     rbx, [rsi+88h]
0x180025d5d  call    cs:__imp_SysStringLen
0x180025d63  mov     rdx, [rdi+20h]; unsigned __int16 *
0x180025d67  lea     r9, [rsp+48h+arg_18]; unsigned __int64 *
0x180025d6c  mov     r8d, eax; unsigned int
0x180025d6f  mov     [rsp+48h+arg_18], r14
0x180025d74  mov     rcx, rbx; this
0x180025d77  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180025d7c  mov     r14, [rsp+48h+arg_18]
0x180025d81  test    r14, r14
0x180025d84  jnz     short loc_180025DA4
0x180025d86  cmp     dword ptr [rsi+1DCh], 2
0x180025d8d  jnz     short loc_180025DA4
0x180025d8f  mov     r8, rbp; struct CXMLRowset *
0x180025d92  mov     rdx, rdi; struct CParseNode *
0x180025d95  mov     rcx, rsi; this
0x180025d98  call    ?ProcessRowsetAttribute@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCXMLRowset@@@Z; CXMLReader::ProcessRowsetAttribute(CParseNode *,CXMLRowset *)
0x180025d9d  xor     eax, eax
0x180025d9f  jmp     loc_180025EC2
0x180025da4  mov     rcx, [rdi+20h]; pbstr
0x180025da8  call    cs:__imp_SysStringLen
0x180025dae  mov     rdx, [rdi+20h]; unsigned __int16 *
0x180025db2  lea     rcx, [rbp+228h]; this
0x180025db9  mov     r8d, eax; unsigned int
0x180025dbc  lea     r9, [rsp+48h+arg_10]; unsigned __int64 *
0x180025dc1  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180025dc6  mov     r15d, eax
0x180025dc9  test    eax, eax
0x180025dcb  js      loc_180025EBF
0x180025dd1  mov     ecx, [rsi+1DCh]
0x180025dd7  mov     r8, [rsp+48h+arg_10]
0x180025ddc  sub     ecx, 4
0x180025ddf  test    ecx, 0FFFFFFFBh
0x180025de5  jz      short loc_180025DF7
0x180025de7  mov     rcx, [rbp+118h]
0x180025dee  mov     edx, r8d
0x180025df1  mov     rbx, [rcx+rdx*8]
0x180025df5  jmp     short loc_180025E05
0x180025df7  mov     rax, [rbp+120h]
0x180025dfe  mov     ecx, r8d
0x180025e01  mov     rbx, [rax+rcx*8]
0x180025e05  cmp     dword ptr [r14], 1
0x180025e09  jnz     short loc_180025E4E
0x180025e0b  mov     rax, [rbp+220h]
0x180025e12  mov     ecx, r8d
0x180025e15  mov     rdx, [rax+rcx*8]
0x180025e19  cmp     qword ptr [rdx+10h], 0
0x180025e1e  jnz     loc_180025EBF
0x180025e24  mov     [rdx+10h], rdi
0x180025e28  mov     [rbx+8], rdx
0x180025e2c  mov     rax, [rdx]
0x180025e2f  mov     dword ptr [rax+264h], 0
0x180025e39  mov     rax, [rdx]
0x180025e3c  mov     dword ptr [rax+0F8h], 0
0x180025e46  mov     eax, [rdi+2Ch]
0x180025e49  mov     [rdx+8], eax
0x180025e4c  jmp     short loc_180025EBF
0x180025e4e  mov     rcx, rdi; this
0x180025e51  mov     dword ptr [rbx+4], 0
0x180025e58  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x180025e5d  mov     rcx, [rax]
0x180025e60  mov     [rbx+8], rcx
0x180025e64  mov     rcx, rdi; this
0x180025e67  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x180025e6c  mov     rcx, [rax]; pbstr
0x180025e6f  call    cs:__imp_SysStringLen
0x180025e75  mov     [rbx], eax
0x180025e77  test    eax, eax
0x180025e79  jnz     short loc_180025EBF
0x180025e7b  cmp     dword ptr [rsi+1DCh], 2
0x180025e82  jnz     short loc_180025EBF
0x180025e84  cmp     dword ptr [rdi+8], 1
0x180025e88  jnz     short loc_180025EBF
0x180025e8a  mov     r14d, [rsi+1B0h]
0x180025e91  mov     ebx, [rdi+2Ch]
0x180025e94  jmp     short loc_180025EB8
0x180025e96  mov     rax, [rsi+1A8h]
0x180025e9d  mov     rdx, [rax+rbx*8]; struct CParseNode *
0x180025ea1  cmp     dword ptr [rdx+8], 2
0x180025ea5  jnz     short loc_180025EB8
0x180025ea7  cmp     [rdx+10h], rdi
0x180025eab  jnz     short loc_180025EB8
0x180025ead  mov     r8, rbp; struct CXMLRowset *
0x180025eb0  mov     rcx, rsi; this
0x180025eb3  call    ?ProcessRowsetAttribute@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCXMLRowset@@@Z; CXMLReader::ProcessRowsetAttribute(CParseNode *,CXMLRowset *)
0x180025eb8  inc     ebx
0x180025eba  cmp     ebx, r14d
0x180025ebd  jb      short loc_180025E96
0x180025ebf  mov     eax, r15d
0x180025ec2  mov     rbx, [rsp+48h+arg_0]
0x180025ec7  add     rsp, 20h
0x180025ecb  pop     r15
0x180025ecd  pop     r14
0x180025ecf  pop     rdi
0x180025ed0  pop     rsi
0x180025ed1  pop     rbp
0x180025ed2  retn
```
