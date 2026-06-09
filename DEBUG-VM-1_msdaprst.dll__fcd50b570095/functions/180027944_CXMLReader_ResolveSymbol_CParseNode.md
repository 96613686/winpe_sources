# CXMLReader::ResolveSymbol(CParseNode *)

- ea: `0x180027944`
- end: `0x180027bfb`
- name: `?ResolveSymbol@CXMLReader@@AEAAJPEAVCParseNode@@@Z`
- size: `695`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CParseNode *)`
- caller_count: `1`
- callee_count: `10`
- tags: `registry_config`

## callers

- `0x1800250f0`

## callees

- `0x180015fb4`
- `0x18001a6c8`
- `0x180023628`
- `0x180023730`
- `0x180023bbc`
- `0x180025f80`
- `0x18002783c`
- `0x180027944`
- `0x180028ee0`
- `0x18002cd54`

## import_xrefs

- `OLEAUT32!__imp_SysStringLen` at `0x180027975`
- `OLEAUT32!__imp_SysStringLen` at `0x1800279b1`
- `OLEAUT32!__imp_SysStringLen` at `0x180027ad9`
- `OLEAUT32!__imp_SysStringLen` at `0x180027975`
- `OLEAUT32!__imp_SysStringLen` at `0x1800279b1`
- `OLEAUT32!__imp_SysStringLen` at `0x180027ad9`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
__int64 __fastcall CXMLReader::ResolveSymbol(CXMLReader *this, struct CParseNode *a2)
{
  unsigned int v4; // r15d
  BSTR *Value; // r14
  CCollectionList *v6; // rbx
  UINT v7; // eax
  struct CSymbol *v8; // rbx
  CScope *v9; // rbx
  UINT v10; // eax
  int v11; // ebx
  int v12; // r14d
  __int64 v13; // rax
  __int64 v14; // rax
  CCollectionList *v15; // rbx
  UINT v16; // eax
  __int64 v17; // rax
  int v18; // r14d
  __int64 v19; // rax
  struct CSymbol *v21; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  Value = (BSTR *)CParseNode::GetValue(a2);
  v6 = (CCollectionList *)*((_QWORD *)this + 17);
  v7 = SysStringLen(*Value);
  v21 = 0;
  CCollectionList::LookUpByKey(v6, *Value, v7, (unsigned __int64 *)&v21);
  v8 = v21;
  if ( (*((_BYTE *)a2 + 40) & 1) == 0 )
  {
    v9 = (CScope *)*((_QWORD *)this + 17);
    v10 = SysStringLen(*Value);
    v11 = CScope::AddSymbol(v9, *Value, v10, &v21);
    if ( v11 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 )
      {
        if ( off_180048D10[0] )
          bidTraceW(off_180048208[0], 2240512, off_180048D10[0], (unsigned int)v11, 2188);
      }
      ThrowHR(v11);
    }
    v8 = v21;
    v12 = CXMLReader::BuildRowDefinition(this, a2, *((_DWORD *)a2 + 6), v21);
    if ( v12 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048D08[0] )
        bidTraceW(off_180048208[0], 2241536, off_180048D08[0], (unsigned int)v12, 2189);
      ThrowHR(v12);
    }
LABEL_28:
    if ( v8 )
    {
      v19 = (unsigned int)(*((_DWORD *)a2 + 11) + 1);
      if ( (unsigned int)v19 < *((_DWORD *)this + 108) )
        CXMLReader::ReduceStack(this, *(struct CParseNode **)(*((_QWORD *)this + 53) + 8 * v19));
      *((_BYTE *)a2 + 40) = 8;
      *((_QWORD *)a2 + 2) = v8;
    }
    return v4;
  }
  if ( !*((_BYTE *)this + 472) || (v13 = *((_QWORD *)this + 17), !*(_DWORD *)(v13 + 16)) )
  {
    if ( !v21 )
      return v4;
LABEL_22:
    v18 = CXMLReader::BuildColumnDefinition(this, a2, v8, 0);
    if ( v18 < 0 )
    {
      if ( (bidGblFlags & 2) != 0 && off_180048D00[0] )
        bidTraceW(off_180048208[0], 2276352, off_180048D00[0], (unsigned int)v18, 2223);
      ThrowHR(v18);
    }
    *((_QWORD *)this + 17) = *(_QWORD *)(*((_QWORD *)this + 17) + 48LL);
    goto LABEL_28;
  }
  if ( *(_DWORD *)(v13 + 16) != 1 )
  {
    v4 = Exit(-2147467259, 0x91u);
    if ( (v4 & 0x80000000) != 0 )
      return v4;
  }
  v14 = *((_QWORD *)this + 17);
  if ( *(_DWORD *)(v14 + 16) )
    v8 = **(struct CSymbol ***)(v14 + 8);
  v15 = *(CCollectionList **)(*((_QWORD *)v8 + 1) + 632LL);
  *((_QWORD *)this + 17) = v15;
  v16 = SysStringLen(*Value);
  v21 = 0;
  CCollectionList::LookUpByKey(v15, *Value, v16, (unsigned __int64 *)&v21);
  v8 = v21;
  if ( v21 )
    goto LABEL_22;
  *((_QWORD *)this + 17) = *(_QWORD *)(*((_QWORD *)this + 17) + 48LL);
  v17 = (unsigned int)(*((_DWORD *)a2 + 11) + 1);
  if ( (unsigned int)v17 < *((_DWORD *)this + 108) )
    CXMLReader::ReduceStack(this, *(struct CParseNode **)(*((_QWORD *)this + 53) + 8 * v17));
  return v4;
}

```

## disassembly

```asm
0x180027944  mov     [rsp+arg_8], rbx
0x180027949  mov     [rsp+arg_10], rsi
0x18002794e  push    rdi
0x18002794f  push    r14
0x180027951  push    r15
0x180027953  sub     rsp, 40h
0x180027957  mov     rsi, rdx
0x18002795a  mov     rdi, rcx
0x18002795d  xor     r15d, r15d
0x180027960  mov     rcx, rdx; this
0x180027963  call    ?GetValue@CParseNode@@QEAAAEAVCComBSTR@ATL@@XZ; CParseNode::GetValue(void)
0x180027968  mov     r14, rax
0x18002796b  mov     rbx, [rdi+88h]
0x180027972  mov     rcx, [rax]; pbstr
0x180027975  call    cs:__imp_SysStringLen
0x18002797b  mov     [rsp+58h+arg_0], r15
0x180027980  lea     r9, [rsp+58h+arg_0]; unsigned __int64 *
0x180027985  mov     r8d, eax; unsigned int
0x180027988  mov     rdx, [r14]; unsigned __int16 *
0x18002798b  mov     rcx, rbx; this
0x18002798e  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180027993  mov     rbx, [rsp+58h+arg_0]
0x180027998  mov     [rsp+58h+arg_0], rbx
0x18002799d  test    byte ptr [rsi+28h], 1
0x1800279a1  jnz     loc_180027A71
0x1800279a7  mov     rbx, [rdi+88h]
0x1800279ae  mov     rcx, [r14]; pbstr
0x1800279b1  call    cs:__imp_SysStringLen
0x1800279b7  lea     r9, [rsp+58h+arg_0]; struct CSymbol **
0x1800279bc  mov     r8d, eax; unsigned int
0x1800279bf  mov     rdx, [r14]; unsigned __int16 *
0x1800279c2  mov     rcx, rbx; this
0x1800279c5  call    ?AddSymbol@CScope@@QEAAJPEAGKPEAPEAVCSymbol@@@Z; CScope::AddSymbol(ushort *,ulong,CSymbol * *)
0x1800279ca  mov     ebx, eax
0x1800279cc  test    eax, eax
0x1800279ce  jns     short loc_180027A0F
0x1800279d0  test    byte ptr cs:_bidGblFlags, 2
0x1800279d7  jz      short loc_180027A08
0x1800279d9  mov     rax, cs:off_180048D10; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x1800279e0  test    rax, rax
0x1800279e3  jz      short loc_180027A08
0x1800279e5  mov     [rsp+58h+var_38], 88Ch
0x1800279ed  mov     r9d, ebx
0x1800279f0  mov     r8, cs:off_180048D10; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x1800279f7  mov     edx, 223000h
0x1800279fc  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180027a03  call    _bidTraceW
0x180027a08  mov     ecx, ebx; int
0x180027a0a  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180027a0f  mov     rbx, [rsp+58h+arg_0]
0x180027a14  mov     r9, rbx; struct CSymbol *
0x180027a17  mov     r8d, [rsi+18h]; unsigned int
0x180027a1b  mov     rdx, rsi; struct CParseNode *
0x180027a1e  mov     rcx, rdi; this
0x180027a21  call    ?BuildRowDefinition@CXMLReader@@AEAAJPEAVCParseNode@@KPEAVCSymbol@@@Z; CXMLReader::BuildRowDefinition(CParseNode *,ulong,CSymbol *)
0x180027a26  mov     r14d, eax
0x180027a29  test    eax, eax
0x180027a2b  jns     loc_180027BB0
0x180027a31  test    byte ptr cs:_bidGblFlags, 2
0x180027a38  jz      short loc_180027A69
0x180027a3a  mov     rax, cs:off_180048D08; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x180027a41  test    rax, rax
0x180027a44  jz      short loc_180027A69
0x180027a46  mov     [rsp+58h+var_38], 88Dh
0x180027a4e  mov     r9d, r14d
0x180027a51  mov     r8, cs:off_180048D08; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x180027a58  mov     edx, 223400h
0x180027a5d  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180027a64  call    _bidTraceW
0x180027a69  mov     ecx, r14d; int
0x180027a6c  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180027a71  cmp     byte ptr [rdi+1D8h], 0
0x180027a78  jz      loc_180027B3D
0x180027a7e  mov     rax, [rdi+88h]
0x180027a85  cmp     dword ptr [rax+10h], 0
0x180027a89  jz      loc_180027B3D
0x180027a8f  cmp     dword ptr [rax+10h], 1
0x180027a93  jz      short loc_180027AB0
0x180027a95  mov     edx, 91h; unsigned int
0x180027a9a  mov     ecx, 80004005h; int
0x180027a9f  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x180027aa4  mov     r15d, eax
0x180027aa7  test    eax, eax
0x180027aa9  jns     short loc_180027AB0
0x180027aab  jmp     loc_180027BE4
0x180027ab0  mov     rax, [rdi+88h]
0x180027ab7  cmp     dword ptr [rax+10h], 0
0x180027abb  jbe     short loc_180027AC4
0x180027abd  mov     rax, [rax+8]
0x180027ac1  mov     rbx, [rax]
0x180027ac4  mov     rax, [rbx+8]
0x180027ac8  mov     rbx, [rax+278h]
0x180027acf  mov     [rdi+88h], rbx
0x180027ad6  mov     rcx, [r14]; pbstr
0x180027ad9  call    cs:__imp_SysStringLen
0x180027adf  mov     [rsp+58h+arg_0], 0
0x180027ae8  lea     r9, [rsp+58h+arg_0]; unsigned __int64 *
0x180027aed  mov     r8d, eax; unsigned int
0x180027af0  mov     rdx, [r14]; unsigned __int16 *
0x180027af3  mov     rcx, rbx; this
0x180027af6  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180027afb  mov     rbx, [rsp+58h+arg_0]
0x180027b00  test    rbx, rbx
0x180027b03  jnz     short loc_180027B46
0x180027b05  mov     rax, [rdi+88h]
0x180027b0c  mov     rcx, [rax+30h]
0x180027b10  mov     [rdi+88h], rcx
0x180027b17  mov     eax, [rsi+2Ch]
0x180027b1a  inc     eax
0x180027b1c  cmp     eax, [rdi+1B0h]
0x180027b22  jnb     short loc_180027B38
0x180027b24  mov     rdx, [rdi+1A8h]
0x180027b2b  mov     rdx, [rdx+rax*8]; struct CParseNode *
0x180027b2f  mov     rcx, rdi; this
0x180027b32  call    ?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z; CXMLReader::ReduceStack(CParseNode *)
0x180027b37  nop
0x180027b38  jmp     loc_180027BE4
0x180027b3d  test    rbx, rbx
0x180027b40  jz      loc_180027BDD
0x180027b46  xor     r9d, r9d; struct XMLCHAPTER *
0x180027b49  mov     r8, rbx; struct CSymbol *
0x180027b4c  mov     rdx, rsi; struct CParseNode *
0x180027b4f  mov     rcx, rdi; this
0x180027b52  call    ?BuildColumnDefinition@CXMLReader@@AEAAJPEAVCParseNode@@PEAVCSymbol@@PEAVXMLCHAPTER@@@Z; CXMLReader::BuildColumnDefinition(CParseNode *,CSymbol *,XMLCHAPTER *)
0x180027b57  mov     r14d, eax
0x180027b5a  test    eax, eax
0x180027b5c  jns     short loc_180027B9E
0x180027b5e  test    byte ptr cs:_bidGblFlags, 2
0x180027b65  jz      short loc_180027B96
0x180027b67  mov     rax, cs:off_180048D00; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x180027b6e  test    rax, rax
0x180027b71  jz      short loc_180027B96
0x180027b73  mov     [rsp+58h+var_38], 8AFh
0x180027b7b  mov     r9d, r14d
0x180027b7e  mov     r8, cs:off_180048D00; "<CXMLReader::ResolveSymbol|ADO|ERR>  HR"...
0x180027b85  mov     edx, 22BC00h
0x180027b8a  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180027b91  call    _bidTraceW
0x180027b96  mov     ecx, r14d; int
0x180027b99  call    ?ThrowHR@@YAXJ@Z; ThrowHR(long)
0x180027b9e  mov     rax, [rdi+88h]
0x180027ba5  mov     rcx, [rax+30h]
0x180027ba9  mov     [rdi+88h], rcx
0x180027bb0  test    rbx, rbx
0x180027bb3  jz      short loc_180027BDD
0x180027bb5  mov     eax, [rsi+2Ch]
0x180027bb8  inc     eax
0x180027bba  cmp     eax, [rdi+1B0h]
0x180027bc0  jnb     short loc_180027BD5
0x180027bc2  mov     rdx, [rdi+1A8h]
0x180027bc9  mov     rdx, [rdx+rax*8]; struct CParseNode *
0x180027bcd  mov     rcx, rdi; this
0x180027bd0  call    ?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z; CXMLReader::ReduceStack(CParseNode *)
0x180027bd5  mov     byte ptr [rsi+28h], 8
0x180027bd9  mov     [rsi+10h], rbx
0x180027bdd  jmp     short loc_180027BE4
0x180027bdf  mov     r15d, dword ptr [rsp+58h+arg_0]
0x180027be4  mov     eax, r15d
0x180027be7  mov     rbx, [rsp+58h+arg_8]
0x180027bec  mov     rsi, [rsp+58h+arg_10]
0x180027bf1  add     rsp, 40h
0x180027bf5  pop     r15
0x180027bf7  pop     r14
0x180027bf9  pop     rdi
0x180027bfa  retn
```
