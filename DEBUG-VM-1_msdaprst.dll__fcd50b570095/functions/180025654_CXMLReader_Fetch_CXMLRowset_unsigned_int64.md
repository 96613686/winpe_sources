# CXMLReader::Fetch(CXMLRowset *,unsigned __int64)

- ea: `0x180025654`
- end: `0x180025953`
- name: `?Fetch@CXMLReader@@QEAAJPEAVCXMLRowset@@_K@Z`
- size: `767`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CXMLRowset *, unsigned __int64)`
- caller_count: `2`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x1800276d0`
- `0x180028560`

## callees

- `0x18001a6c8`
- `0x180025654`
- `0x180025a7c`
- `0x180025d2c`
- `0x180026270`
- `0x1800266e4`
- `0x1800276d0`
- `0x18002783c`
- `0x180030010`

## pseudocode

```c
__int64 __fastcall CXMLReader::Fetch(CXMLReader *this, struct CXMLRowset *a2, __int64 a3)
{
  struct CParseNode ***v3; // r15
  __int64 v4; // rax
  struct CParseNode ***v5; // rbx
  __int64 *v6; // r14
  struct CXMLRowset *v7; // r8
  unsigned int v9; // ebx
  __int64 v10; // rdx
  __int64 v11; // r13
  int Data; // ebx
  int v13; // eax
  __int64 v14; // r12
  struct CParseNode *v15; // rbp
  unsigned int v16; // edx
  unsigned int v17; // esi
  int v18; // eax
  struct CParseNode *v19; // r8
  __int64 v20; // rcx
  unsigned int v22; // [rsp+40h] [rbp-48h]
  unsigned int v25; // [rsp+A8h] [rbp+20h] BYREF

  v3 = (struct CParseNode ***)((char *)this + 424);
  v4 = a3;
  v5 = (struct CParseNode ***)((char *)this + 424);
  v6 = (__int64 *)((char *)this + 456);
  v7 = a2;
  while ( 2 )
  {
    if ( v4 )
    {
      v9 = *(_DWORD *)(v4 + 8);
      if ( v9 )
      {
        if ( v9 < *((_DWORD *)this + 108) )
        {
          v10 = *v6;
          v11 = v4;
          goto LABEL_18;
        }
        return 1;
      }
      v5 = v3;
    }
    v10 = *v6;
    if ( *v6 )
    {
      Data = 0;
      v13 = 2;
    }
    else
    {
      if ( *((_DWORD *)this + 108) )
        CXMLReader::ReduceStack(this, **v5);
      Data = (*(__int64 (__fastcall **)(_QWORD, __int64, struct CXMLRowset *))(**((_QWORD **)this + 56) + 192LL))(
               *((_QWORD *)this + 56),
               0xFFFFFFFFLL,
               v7);
      v13 = (*(__int64 (__fastcall **)(_QWORD))(**((_QWORD **)this + 56) + 200LL))(*((_QWORD *)this + 56));
      v10 = *v6;
      if ( !*v6 )
      {
LABEL_38:
        if ( v13 == 3 )
          goto LABEL_43;
        return 1;
      }
      if ( *(_DWORD *)v10 == 4 && v13 == 3 )
        return 1;
      v7 = a2;
    }
    if ( *(_DWORD *)v10 == 1 && *(struct CXMLRowset **)(v10 + 8) != v7 )
      goto LABEL_38;
    v9 = 0;
    v11 = 0;
LABEL_18:
    v14 = 0;
    v15 = (*v3)[v9];
    if ( (*((_BYTE *)v15 + 40) & 4) != 0 )
      v14 = *((_QWORD *)v15 + 2);
    if ( (unsigned int)(*(_DWORD *)v10 - 4) > 2 )
    {
      CXMLReader::PrepareData(this, v7);
      v16 = *((_DWORD *)v15 + 6);
      v17 = v9 + 1;
      v22 = v16;
      Data = 0;
      while ( 1 )
      {
        v25 = v17;
        if ( v17 >= v16 )
        {
          if ( v11 )
            *(_DWORD *)(v11 + 8) = v16;
          *v6 = 0;
LABEL_43:
          if ( Data < 0 )
          {
LABEL_49:
            if ( *((_DWORD *)this + 108) )
              CXMLReader::ReduceStack(this, **v3);
          }
          return (unsigned int)Data;
        }
        if ( v14 )
          break;
        v19 = (*v3)[v17];
        if ( *((struct CParseNode **)v19 + 2) == v15 && (unsigned int)(*((_DWORD *)v19 + 2) - 1) <= 1 )
        {
          Data = CXMLReader::GetData(this, a2, v19);
          if ( Data < 0 )
            goto LABEL_49;
LABEL_33:
          v16 = v22;
        }
LABEL_34:
        ++v17;
      }
      if ( *(_DWORD *)(*(_QWORD *)(v14 + 8LL * v17) + 4LL) != 2 )
        goto LABEL_34;
      v18 = CXMLReader::GetData(this, a2, (struct _XML_NODE_INFO **)(v14 + 8LL * v17), &v25, v16);
      Data = v18;
      if ( v18 < 0 )
        goto LABEL_49;
      if ( v18 == 1 )
      {
        v17 = v25;
        if ( (unsigned __int8)CXMLReader::IsMatch(
                                this,
                                *(_QWORD *)(*(_QWORD *)(v14 + 8LL * v25) + 16LL),
                                *(unsigned int *)(*(_QWORD *)(v14 + 8LL * v25) + 24LL),
                                *(unsigned int *)(*(_QWORD *)(v14 + 8LL * v25) + 28LL),
                                &wszDuplicate,
                                9,
                                3) )
        {
          v5 = v3;
          if ( (*((_BYTE *)v15 + 40) & 1) == 0 )
          {
            v20 = *((_QWORD *)this + 56);
            *((_QWORD *)this + 58) = v15;
            *((_BYTE *)this + 400) = 0;
            (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v20 + 192LL))(v20, 0xFFFFFFFFLL);
            *((_QWORD *)this + 58) = 0;
          }
          v7 = a2;
          v4 = a3;
          *v6 = 0;
          continue;
        }
        Data = 0;
      }
      else
      {
        v17 = v25;
      }
      goto LABEL_33;
    }
    break;
  }
  Data = CXMLReader::ProcessUpdate(this, v7);
  if ( Data < 0 )
  {
    if ( (bidGblFlags & 2) != 0 && off_180048D18[0] )
      bidTraceW(off_180048208[0], 1698816, off_180048D18[0], (unsigned int)Data, 1659);
    goto LABEL_49;
  }
  return (unsigned int)Data;
}

```

## disassembly

```asm
0x180025654  mov     [rsp+arg_0], rbx
0x180025659  mov     [rsp+arg_10], r8
0x18002565e  mov     [rsp+arg_8], rdx
0x180025663  push    rbp
0x180025664  push    rsi
0x180025665  push    rdi
0x180025666  push    r12
0x180025668  push    r13
0x18002566a  push    r14
0x18002566c  push    r15
0x18002566e  sub     rsp, 50h
0x180025672  lea     r15, [rcx+1A8h]
0x180025679  mov     rax, r8
0x18002567c  mov     rbx, r15
0x18002567f  lea     r14, [rcx+1C8h]
0x180025686  mov     r8, rdx
0x180025689  mov     rdi, rcx
0x18002568c  mov     esi, 1
0x180025691  test    rax, rax
0x180025694  jz      short loc_1800256B7
0x180025696  mov     ebx, [rax+8]
0x180025699  test    ebx, ebx
0x18002569b  jz      short loc_1800256B4
0x18002569d  cmp     ebx, [rdi+1B0h]
0x1800256a3  jnb     loc_1800258C5
0x1800256a9  mov     rdx, [r14]
0x1800256ac  mov     r13, rax
0x1800256af  jmp     loc_180025742
0x1800256b4  mov     rbx, r15
0x1800256b7  mov     rdx, [r14]
0x1800256ba  test    rdx, rdx
0x1800256bd  jnz     short loc_18002572A
0x1800256bf  cmp     [rdi+1B0h], edx
0x1800256c5  jz      short loc_1800256D5
0x1800256c7  mov     rdx, [rbx]
0x1800256ca  mov     rcx, rdi; this
0x1800256cd  mov     rdx, [rdx]; struct CParseNode *
0x1800256d0  call    ?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z; CXMLReader::ReduceStack(CParseNode *)
0x1800256d5  mov     rcx, [rdi+1C0h]
0x1800256dc  or      edx, 0FFFFFFFFh
0x1800256df  mov     rax, [rcx]
0x1800256e2  mov     rax, [rax+0C0h]
0x1800256e9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800256ee  mov     rcx, [rdi+1C0h]
0x1800256f5  mov     ebx, eax
0x1800256f7  mov     rdx, [rcx]
0x1800256fa  mov     rax, [rdx+0C8h]
0x180025701  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025706  mov     rdx, [r14]
0x180025709  test    rdx, rdx
0x18002570c  jz      loc_1800258C0
0x180025712  cmp     dword ptr [rdx], 4
0x180025715  jnz     short loc_180025720
0x180025717  cmp     eax, 3
0x18002571a  jz      loc_1800258C5
0x180025720  mov     r8, [rsp+88h+arg_8]
0x180025728  jmp     short loc_18002572F
0x18002572a  xor     ebx, ebx
0x18002572c  lea     eax, [rbx+2]
0x18002572f  cmp     [rdx], esi
0x180025731  jnz     short loc_18002573D
0x180025733  cmp     [rdx+8], r8
0x180025737  jnz     loc_1800258C0
0x18002573d  xor     ebx, ebx
0x18002573f  xor     r13d, r13d
0x180025742  mov     rax, [r15]
0x180025745  xor     r12d, r12d
0x180025748  mov     ecx, ebx
0x18002574a  mov     rbp, [rax+rcx*8]
0x18002574e  test    byte ptr [rbp+28h], 4
0x180025752  jz      short loc_180025758
0x180025754  mov     r12, [rbp+10h]
0x180025758  mov     eax, [rdx]
0x18002575a  mov     rcx, rdi; this
0x18002575d  sub     eax, 4
0x180025760  mov     rdx, r8; struct CXMLRowset *
0x180025763  cmp     eax, 2
0x180025766  jbe     loc_1800258DF
0x18002576c  call    ?PrepareData@CXMLReader@@AEAAXPEAVCXMLRowset@@@Z; CXMLReader::PrepareData(CXMLRowset *)
0x180025771  mov     edx, [rbp+18h]
0x180025774  lea     esi, [rbx+1]
0x180025777  mov     [rsp+88h+var_48], edx
0x18002577b  xor     ebx, ebx
0x18002577d  mov     ecx, esi
0x18002577f  mov     [rsp+88h+arg_18], esi
0x180025786  mov     eax, esi
0x180025788  cmp     ecx, edx
0x18002578a  jnb     loc_1800258C9
0x180025790  mov     r8d, eax
0x180025793  test    r12, r12
0x180025796  jz      loc_180025827
0x18002579c  mov     rax, [r12+r8*8]
0x1800257a0  cmp     dword ptr [rax+4], 2
0x1800257a4  jnz     loc_18002585D
0x1800257aa  mov     eax, ecx
0x1800257ac  lea     r9, [rsp+88h+arg_18]; unsigned int *
0x1800257b4  mov     [rsp+88h+var_68], edx; unsigned int
0x1800257b8  mov     rcx, rdi; this
0x1800257bb  mov     rdx, [rsp+88h+arg_8]; struct CXMLRowset *
0x1800257c3  lea     r8, [r12+rax*8]; struct _XML_NODE_INFO **
0x1800257c7  call    ?GetData@CXMLReader@@QEAAJPEAVCXMLRowset@@PEAPEAU_XML_NODE_INFO@@PEAKK@Z; CXMLReader::GetData(CXMLRowset *,_XML_NODE_INFO * *,ulong *,ulong)
0x1800257cc  mov     ebx, eax
0x1800257ce  test    eax, eax
0x1800257d0  js      loc_180025922
0x1800257d6  cmp     eax, 1
0x1800257d9  jnz     short loc_18002581E
0x1800257db  mov     esi, [rsp+88h+arg_18]
0x1800257e2  lea     rax, ?wszDuplicate@@3PAGA; "duplicate"
0x1800257e9  mov     [rsp+88h+var_58], 3
0x1800257f1  mov     rcx, rdi
0x1800257f4  mov     [rsp+88h+var_60], 9
0x1800257fc  mov     qword ptr [rsp+88h+var_68], rax
0x180025801  mov     rdx, [r12+rsi*8]
0x180025805  mov     r9d, [rdx+1Ch]
0x180025809  mov     r8d, [rdx+18h]
0x18002580d  mov     rdx, [rdx+10h]
0x180025811  call    ?IsMatch@CXMLReader@@AEAA_NPEBGKKPEAGKW4_NAMESPACETYPE@@@Z; CXMLReader::IsMatch(ushort const *,ulong,ulong,ushort *,ulong,_NAMESPACETYPE)
0x180025816  test    al, al
0x180025818  jnz     short loc_180025864
0x18002581a  xor     ebx, ebx
0x18002581c  jmp     short loc_180025859
0x18002581e  mov     esi, [rsp+88h+arg_18]
0x180025825  jmp     short loc_180025859
0x180025827  mov     rax, [r15]
0x18002582a  mov     r8, [rax+r8*8]; struct CParseNode *
0x18002582e  cmp     [r8+10h], rbp
0x180025832  jnz     short loc_18002585D
0x180025834  mov     eax, [r8+8]
0x180025838  dec     eax
0x18002583a  cmp     eax, 1
0x18002583d  ja      short loc_18002585D
0x18002583f  mov     rdx, [rsp+88h+arg_8]; struct CXMLRowset *
0x180025847  mov     rcx, rdi; this
0x18002584a  call    ?GetData@CXMLReader@@QEAAJPEAVCXMLRowset@@PEAVCParseNode@@@Z; CXMLReader::GetData(CXMLRowset *,CParseNode *)
0x18002584f  mov     ebx, eax
0x180025851  test    eax, eax
0x180025853  js      loc_180025922
0x180025859  mov     edx, [rsp+88h+var_48]
0x18002585d  inc     esi
0x18002585f  jmp     loc_18002577D
0x180025864  mov     esi, 1
0x180025869  mov     rbx, r15
0x18002586c  test    [rbp+28h], sil
0x180025870  jnz     short loc_1800258A4
0x180025872  mov     rcx, [rdi+1C0h]
0x180025879  or      edx, 0FFFFFFFFh
0x18002587c  mov     [rdi+1D0h], rbp
0x180025883  mov     byte ptr [rdi+190h], 0
0x18002588a  mov     rax, [rcx]
0x18002588d  mov     rax, [rax+0C0h]
0x180025894  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025899  mov     qword ptr [rdi+1D0h], 0
0x1800258a4  mov     r8, [rsp+88h+arg_8]
0x1800258ac  mov     rax, [rsp+88h+arg_10]
0x1800258b4  mov     qword ptr [r14], 0
0x1800258bb  jmp     loc_180025691
0x1800258c0  cmp     eax, 3
0x1800258c3  jz      short loc_1800258D9
0x1800258c5  mov     ebx, esi
0x1800258c7  jmp     short loc_180025939
0x1800258c9  test    r13, r13
0x1800258cc  jz      short loc_1800258D2
0x1800258ce  mov     [r13+8], edx
0x1800258d2  mov     qword ptr [r14], 0
0x1800258d9  test    ebx, ebx
0x1800258db  jns     short loc_180025939
0x1800258dd  jmp     short loc_180025922
0x1800258df  call    ?ProcessUpdate@CXMLReader@@AEAAJPEAVCXMLRowset@@W4SYMBOL_TYPE@@@Z; CXMLReader::ProcessUpdate(CXMLRowset *,SYMBOL_TYPE)
0x1800258e4  mov     ebx, eax
0x1800258e6  test    eax, eax
0x1800258e8  jns     short loc_180025939
0x1800258ea  test    byte ptr cs:_bidGblFlags, 2
0x1800258f1  jz      short loc_180025922
0x1800258f3  mov     rax, cs:off_180048D18; "<CXMLReader::Fetch|ADO|ERR>  HRESULT: 0"...
0x1800258fa  test    rax, rax
0x1800258fd  jz      short loc_180025922
0x1800258ff  mov     r8, cs:off_180048D18; "<CXMLReader::Fetch|ADO|ERR>  HRESULT: 0"...
0x180025906  mov     r9d, ebx
0x180025909  mov     rcx, cs:off_180048208; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x180025910  mov     edx, 19EC00h
0x180025915  mov     [rsp+88h+var_68], 67Bh
0x18002591d  call    _bidTraceW
0x180025922  cmp     dword ptr [rdi+1B0h], 0
0x180025929  jz      short loc_180025939
0x18002592b  mov     rdx, [r15]
0x18002592e  mov     rcx, rdi; this
0x180025931  mov     rdx, [rdx]; struct CParseNode *
0x180025934  call    ?ReduceStack@CXMLReader@@AEAAXPEAVCParseNode@@@Z; CXMLReader::ReduceStack(CParseNode *)
0x180025939  mov     eax, ebx
0x18002593b  mov     rbx, [rsp+88h+arg_0]
0x180025943  add     rsp, 50h
0x180025947  pop     r15
0x180025949  pop     r14
0x18002594b  pop     r13
0x18002594d  pop     r12
0x18002594f  pop     rdi
0x180025950  pop     rsi
0x180025951  pop     rbp
0x180025952  retn
```
