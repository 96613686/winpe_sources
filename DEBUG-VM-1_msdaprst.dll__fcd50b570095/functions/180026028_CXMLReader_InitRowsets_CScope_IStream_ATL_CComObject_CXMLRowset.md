# CXMLReader::InitRowsets(CScope *,IStream *,ATL::CComObject<CXMLRowset> * *)

- ea: `0x180026028`
- end: `0x18002626a`
- name: `?InitRowsets@CXMLReader@@AEAAJPEAVCScope@@PEAUIStream@@PEAPEAV?$CComObject@VCXMLRowset@@@ATL@@@Z`
- size: `578`
- prototype: ``
- caller_count: `2`
- callee_count: `10`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180024ac8`
- `0x180026028`

## callees

- `0x180015fb4`
- `0x180018874`
- `0x18001a6c8`
- `0x18002010c`
- `0x18002058c`
- `0x180026028`
- `0x18002867c`
- `0x180028894`
- `0x1800288bc`
- `0x180030010`

## import_xrefs

- `OLEAUT32!__imp_SysFreeString` at `0x1800261e3`
- `OLEAUT32!__imp_SysFreeString` at `0x1800261e3`
- `OLEAUT32!__imp_SysStringLen` at `0x180026103`
- `OLEAUT32!__imp_SysStringLen` at `0x18002619f`
- `OLEAUT32!__imp_SysStringLen` at `0x180026103`
- `OLEAUT32!__imp_SysStringLen` at `0x18002619f`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall CXMLReader::InitRowsets(__int64 a1, __int64 a2, struct IUnknown *a3, CRowset **a4)
{
  CRowset **v4; // r15
  int v7; // ebx
  unsigned int v8; // r12d
  unsigned __int64 v9; // rdi
  unsigned int i; // esi
  CRowset *v11; // rbp
  const unsigned __int16 *v12; // rbx
  unsigned int v13; // edx
  _QWORD *v14; // rcx
  UINT v15; // eax
  __int64 v16; // r8
  unsigned int v17; // eax
  unsigned __int16 *v18; // rbx
  UINT v19; // eax
  __int64 v20; // rdx
  BSTR pbstr; // [rsp+78h] [rbp+10h] BYREF
  struct IUnknown *v23; // [rsp+80h] [rbp+18h]
  CRowset **v24; // [rsp+88h] [rbp+20h]

  v24 = a4;
  v23 = a3;
  v4 = a4;
  v7 = 0;
  v8 = *(_DWORD *)(a2 + 16);
  v9 = 0;
  for ( i = 0; i < v8; ++i )
  {
    if ( i < *(_DWORD *)(a2 + 16) )
    {
      v9 = *(_QWORD *)(*(_QWORD *)(a2 + 8) + 8LL * i);
      v7 = 0;
    }
    else
    {
      v7 = 1;
    }
    if ( *(_DWORD *)v9 == 1 )
    {
      v11 = *(CRowset **)(v9 + 8);
      if ( *v4 )
      {
        *((_QWORD *)v11 + 75) = a1;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 8LL))(*(_QWORD *)(a1 + 448));
      }
      else
      {
        if ( v8 != 1 )
        {
          v7 = Exit(-2147467259, 0x91u);
          if ( v7 < 0 )
            return (unsigned int)v7;
        }
        v12 = 0;
        pbstr = 0;
        if ( *(_DWORD *)(a2 + 24) )
        {
          v13 = 0;
          do
          {
            v14 = *(_QWORD **)(*(_QWORD *)(a2 + 32) + 8LL * v13);
            if ( v14 )
            {
              while ( v14 )
              {
                if ( v14[2] == v9 )
                {
                  v12 = (const unsigned __int16 *)v14[1];
                  goto LABEL_17;
                }
                v14 = (_QWORD *)v14[3];
              }
            }
            ++v13;
          }
          while ( v13 < *(_DWORD *)(a2 + 24) );
          v12 = 0;
        }
LABEL_17:
        v15 = SysStringLen(*(BSTR *)(a1 + 152));
        ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, *(const unsigned __int16 **)(a1 + 152), v15);
        v16 = -1;
        do
          ++v16;
        while ( v12[v16] );
        ATL::CComBSTR::Append((ATL::CComBSTR *)&pbstr, v12, v16);
        v17 = CCollectionArray::DeleteByData((CCollectionArray *)a2, v9);
        if ( v17 )
        {
          if ( (bidGblFlags & 2) != 0 && off_180048E10[0] )
            bidTraceW(off_180048218, 1027072, off_180048E10[0], v17, 1003);
        }
        else
        {
          CCollectionMap::DeleteByData((CCollectionMap *)(a2 + 24), v9);
        }
        v18 = pbstr;
        v19 = SysStringLen(pbstr);
        CCollectionList::Append((CCollectionList *)a2, v18, v19, v9);
        *((_QWORD *)v11 + 75) = a1;
        (*(void (__fastcall **)(_QWORD))(**(_QWORD **)(a1 + 448) + 8LL))(*(_QWORD *)(a1 + 448));
        v4 = v24;
        *v24 = v11;
        *(_BYTE *)(v9 + 16) = 0;
        SysFreeString(v18);
      }
      v7 = CRowset::Init(v11);
      if ( v7 < 0 )
        return (unsigned int)v7;
      CRowset::CheckThreadModel(v11, v23);
      v20 = *((_QWORD *)v11 + 79);
      if ( v20 )
        CXMLReader::InitRowsets(a1, v20, v23, v4);
    }
  }
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180026028  mov     [rsp+arg_0], rbx
0x18002602d  mov     [rsp+arg_18], r9
0x180026032  mov     [rsp+arg_10], r8
0x180026037  push    rbp
0x180026038  push    rsi
0x180026039  push    rdi
0x18002603a  push    r12
0x18002603c  push    r13
0x18002603e  push    r14
0x180026040  push    r15
0x180026042  sub     rsp, 30h
0x180026046  mov     r15, r9
0x180026049  mov     r14, rdx
0x18002604c  mov     r13, rcx
0x18002604f  xor     r9d, r9d
0x180026052  mov     ebx, r9d
0x180026055  mov     r12d, [rdx+10h]
0x180026059  mov     edi, r9d
0x18002605c  mov     esi, r9d
0x18002605f  test    r12d, r12d
0x180026062  jz      loc_180026253
0x180026068  cmp     esi, [r14+10h]
0x18002606c  jb      short loc_180026075
0x18002606e  mov     ebx, 1
0x180026073  jmp     short loc_180026082
0x180026075  mov     ecx, esi
0x180026077  mov     rax, [r14+8]
0x18002607b  mov     rdi, [rax+rcx*8]
0x18002607f  mov     ebx, r9d
0x180026082  cmp     dword ptr [rdi], 1
0x180026085  jnz     loc_180026248
0x18002608b  mov     rbp, [rdi+8]
0x18002608f  cmp     [r15], r9
0x180026092  jnz     loc_1800261EB
0x180026098  cmp     r12d, 1
0x18002609c  jz      short loc_1800260BA
0x18002609e  mov     edx, 91h; unsigned int
0x1800260a3  mov     ecx, 80004005h; int
0x1800260a8  call    ?Exit@@YAJJK@Z; Exit(long,ulong)
0x1800260ad  mov     ebx, eax
0x1800260af  xor     r9d, r9d
0x1800260b2  test    eax, eax
0x1800260b4  js      loc_180026253
0x1800260ba  mov     rbx, r9
0x1800260bd  mov     [rsp+68h+pbstr], r9
0x1800260c2  lea     r15, [r14+18h]
0x1800260c6  cmp     [r15], r9d
0x1800260c9  jbe     short loc_1800260FC
0x1800260cb  mov     edx, r9d
0x1800260ce  mov     r8, [r15+8]
0x1800260d2  mov     eax, edx
0x1800260d4  mov     rcx, [r8+rax*8]
0x1800260d8  test    rcx, rcx
0x1800260db  jz      short loc_1800260F2
0x1800260dd  test    rcx, rcx
0x1800260e0  jz      short loc_1800260F2
0x1800260e2  cmp     [rcx+10h], rdi
0x1800260e6  jz      loc_180026183
0x1800260ec  mov     rcx, [rcx+18h]
0x1800260f0  jmp     short loc_1800260DD
0x1800260f2  inc     edx
0x1800260f4  cmp     edx, [r15]
0x1800260f7  jb      short loc_1800260D2
0x1800260f9  mov     rbx, r9
0x1800260fc  mov     rcx, [r13+98h]; pbstr
0x180026103  call    cs:__imp_SysStringLen
0x180026109  mov     r8d, eax; int
0x18002610c  mov     rdx, [r13+98h]; unsigned __int16 *
0x180026113  lea     rcx, [rsp+68h+pbstr]; this
0x180026118  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002611d  or      r8, 0FFFFFFFFFFFFFFFFh
0x180026121  xor     eax, eax
0x180026123  inc     r8; int
0x180026126  cmp     [rbx+r8*2], ax
0x18002612b  jnz     short loc_180026123
0x18002612d  mov     rdx, rbx; unsigned __int16 *
0x180026130  lea     rcx, [rsp+68h+pbstr]; this
0x180026135  call    ?Append@CComBSTR@ATL@@QEAAJPEBGH@Z; ATL::CComBSTR::Append(ushort const *,int)
0x18002613a  mov     rdx, rdi; unsigned __int64
0x18002613d  mov     rcx, r14; this
0x180026140  call    ?DeleteByData@CCollectionArray@@QEAAJ_K@Z; CCollectionArray::DeleteByData(unsigned __int64)
0x180026145  test    eax, eax
0x180026147  jz      short loc_18002618C
0x180026149  test    byte ptr cs:_bidGblFlags, 2
0x180026150  jz      short loc_180026197
0x180026152  mov     rcx, cs:off_180048E10; "<CCollectionList::DeleteByData|ADO|ERR>"...
0x180026159  test    rcx, rcx
0x18002615c  jz      short loc_180026197
0x18002615e  mov     [rsp+68h+var_48], 3EBh
0x180026166  mov     r9d, eax
0x180026169  mov     r8, cs:off_180048E10; "<CCollectionList::DeleteByData|ADO|ERR>"...
0x180026170  mov     edx, 0FAC00h
0x180026175  mov     rcx, cs:off_180048218; "enduser\\databaseaccess\\src\\mdac\\rds"...
0x18002617c  call    _bidTraceW
0x180026181  jmp     short loc_180026197
0x180026183  mov     rbx, [rcx+8]
0x180026187  jmp     loc_1800260FC
0x18002618c  mov     rdx, rdi; unsigned __int64
0x18002618f  mov     rcx, r15; this
0x180026192  call    ?DeleteByData@CCollectionMap@@QEAAJ_K@Z; CCollectionMap::DeleteByData(unsigned __int64)
0x180026197  mov     rbx, [rsp+68h+pbstr]
0x18002619c  mov     rcx, rbx; pbstr
0x18002619f  call    cs:__imp_SysStringLen
0x1800261a5  mov     r9, rdi; unsigned __int64
0x1800261a8  mov     r8d, eax; unsigned int
0x1800261ab  mov     rdx, rbx; unsigned __int16 *
0x1800261ae  mov     rcx, r14; this
0x1800261b1  call    ?Append@CCollectionList@@QEAAJPEAGK_K@Z; CCollectionList::Append(ushort *,ulong,unsigned __int64)
0x1800261b6  mov     [rbp+258h], r13
0x1800261bd  mov     rcx, [r13+1C0h]
0x1800261c4  mov     rax, [rcx]
0x1800261c7  mov     rax, [rax+8]
0x1800261cb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800261d0  mov     r15, [rsp+68h+arg_18]
0x1800261d8  mov     [r15], rbp
0x1800261db  xor     eax, eax
0x1800261dd  mov     [rdi+10h], al
0x1800261e0  mov     rcx, rbx; bstrString
0x1800261e3  call    cs:__imp_SysFreeString
0x1800261e9  jmp     short loc_180026205
0x1800261eb  mov     [rbp+258h], r13
0x1800261f2  mov     rcx, [r13+1C0h]
0x1800261f9  mov     rax, [rcx]
0x1800261fc  mov     rax, [rax+8]
0x180026200  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026205  mov     rcx, rbp; this
0x180026208  call    ?Init@CRowset@@QEAAJXZ; CRowset::Init(void)
0x18002620d  mov     ebx, eax
0x18002620f  test    eax, eax
0x180026211  js      short loc_180026253
0x180026213  mov     rdx, [rsp+68h+arg_10]; struct IUnknown *
0x18002621b  mov     rcx, rbp; this
0x18002621e  call    ?CheckThreadModel@CRowset@@QEAAXPEAUIUnknown@@@Z; CRowset::CheckThreadModel(IUnknown *)
0x180026223  mov     rdx, [rbp+278h]
0x18002622a  xor     r9d, r9d
0x18002622d  test    rdx, rdx
0x180026230  jz      short loc_180026248
0x180026232  mov     r9, r15
0x180026235  mov     r8, [rsp+68h+arg_10]
0x18002623d  mov     rcx, r13
0x180026240  call    ?InitRowsets@CXMLReader@@AEAAJPEAVCScope@@PEAUIStream@@PEAPEAV?$CComObject@VCXMLRowset@@@ATL@@@Z; CXMLReader::InitRowsets(CScope *,IStream *,ATL::CComObject<CXMLRowset> * *)
0x180026245  xor     r9d, r9d
0x180026248  inc     esi
0x18002624a  cmp     esi, r12d
0x18002624d  jb      loc_180026068
0x180026253  mov     eax, ebx
0x180026255  mov     rbx, [rsp+68h+arg_0]
0x18002625a  add     rsp, 30h
0x18002625e  pop     r15
0x180026260  pop     r14
0x180026262  pop     r13
0x180026264  pop     r12
0x180026266  pop     rdi
0x180026267  pop     rsi
0x180026268  pop     rbp
0x180026269  retn
```
