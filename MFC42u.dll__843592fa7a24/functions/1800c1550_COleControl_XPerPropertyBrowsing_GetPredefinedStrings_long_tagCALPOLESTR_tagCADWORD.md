# COleControl::XPerPropertyBrowsing::GetPredefinedStrings(long,tagCALPOLESTR *,tagCADWORD *)

- ea: `0x1800c1550`
- end: `0x1800c1773`
- name: `?GetPredefinedStrings@XPerPropertyBrowsing@COleControl@@UEAAJJPEAUtagCALPOLESTR@@PEAUtagCADWORD@@@Z`
- size: `547`
- prototype: `__int64 __fastcall(COleControl::XPerPropertyBrowsing *__hidden this, int, struct tagCALPOLESTR *, struct tagCADWORD *)`
- caller_count: `0`
- callee_count: `8`
- tags: `service_task, broker_com_uri`

## callees

- `0x180011480`
- `0x180019220`
- `0x180019290`
- `0x1800239f0`
- `0x18003aff0`
- `0x18003bad0`
- `0x1800c1550`
- `0x1800d7010`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x1800c16c6`
- `msvcrt!wcscpy_s` at `0x1800c16c6`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c1613`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c1648`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c16ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c1613`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c1648`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1800c16ad`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c165c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c170e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c171e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c165c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c170e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800c171e`

## pseudocode

```c
__int64 __fastcall COleControl::XPerPropertyBrowsing::GetPredefinedStrings(
        COleControl::XPerPropertyBrowsing *this,
        unsigned int a2,
        struct tagCALPOLESTR *a3,
        struct tagCADWORD *a4)
{
  __int64 *v4; // r15
  __int64 v6; // rbx
  __int64 Data; // rax
  __int64 v10; // rdi
  __int64 v11; // rsi
  unsigned int v12; // ebx
  __int64 v13; // rax
  int v14; // r15d
  signed int v15; // r13d
  SIZE_T v16; // rbx
  LPOLESTR *v17; // rax
  OLECHAR *v18; // r15
  __int64 result; // rax
  DWORD *v20; // rax
  signed int v21; // ebx
  wchar_t *v22; // rcx
  __int64 v23; // rax
  wchar_t *v24; // rax
  unsigned int v25; // eax
  __int64 v26; // rdx
  rsize_t SizeInWords; // [rsp+30h] [rbp-39h]
  _BYTE v28[8]; // [rsp+38h] [rbp-31h] BYREF
  _QWORD v29[2]; // [rsp+40h] [rbp-29h] BYREF
  __int64 v30; // [rsp+50h] [rbp-19h]
  __int64 v31; // [rsp+58h] [rbp-11h]
  __int64 v32; // [rsp+60h] [rbp-9h]
  _QWORD v33[11]; // [rsp+68h] [rbp-1h] BYREF
  int v34; // [rsp+D0h] [rbp+67h]
  wchar_t *Source; // [rsp+E0h] [rbp+77h]

  v4 = (__int64 *)((char *)this - 584);
  v6 = *((_QWORD *)this - 66);
  Data = CThreadLocal<_AFX_THREAD_STATE>::GetData();
  v10 = Data;
  v11 = *(_QWORD *)(Data + 8);
  *(_QWORD *)(Data + 8) = v6;
  v12 = 0;
  if ( a3 && a4 )
  {
    v29[1] = 0;
    v29[0] = &CStringArray::`vftable';
    v32 = 0;
    v33[0] = &CDWordArray::`vftable';
    v13 = *v4;
    v31 = 0;
    v30 = 0;
    memset(&v33[1], 0, 32);
    v34 = (*(__int64 (__fastcall **)(__int64 *, _QWORD, _QWORD *, _QWORD *))(v13 + 768))(v4, a2, v29, v33);
    v14 = v34;
    if ( v34 )
    {
      v15 = v30;
      v16 = 8LL * (unsigned int)v30;
      v17 = (LPOLESTR *)CoTaskMemAlloc(v16);
      v18 = 0;
      a3->pElems = v17;
      if ( v17 )
      {
        v20 = (DWORD *)CoTaskMemAlloc(v16);
        a4->pElems = v20;
        if ( v20 )
        {
          a3->cElems = v15;
          v21 = 0;
          a4->cElems = v15;
          while ( 1 )
          {
            if ( v21 >= v15 )
            {
              v14 = v34;
              v12 = 0;
              goto LABEL_21;
            }
            v22 = *(wchar_t **)CStringArray::GetAt(v29, v28, v21);
            Source = v22;
            if ( v22 )
            {
              v23 = -1;
              do
                ++v23;
              while ( v22[v23] );
              SizeInWords = (int)v23 + 1;
              v24 = (wchar_t *)CoTaskMemAlloc(2LL * (int)SizeInWords);
              v18 = v24;
              if ( v24 )
                wcscpy_s(v24, SizeInWords, Source);
            }
            CString::~CString((CString *)v28);
            if ( !v18 )
              break;
            a3->pElems[v21] = v18;
            v25 = CUIntArray::GetAt((CUIntArray *)v33, v21);
            v26 = v21++;
            v18 = 0;
            a4->pElems[v26] = v25;
          }
          while ( --v21 >= 0 )
            CoTaskMemFree(a3->pElems[v21]);
          CoTaskMemFree(a4->pElems);
        }
        CoTaskMemFree(a3->pElems);
      }
      CDWordArray::~CDWordArray((CDWordArray *)v33);
      CStringArray::~CStringArray((CStringArray *)v29);
      result = 2147942414LL;
      *(_QWORD *)(v10 + 8) = v11;
    }
    else
    {
LABEL_21:
      LOBYTE(v12) = v14 == 0;
      CDWordArray::~CDWordArray((CDWordArray *)v33);
      CStringArray::~CStringArray((CStringArray *)v29);
      result = v12;
      *(_QWORD *)(v10 + 8) = v11;
    }
  }
  else
  {
    *(_QWORD *)(Data + 8) = v11;
    return 2147500035LL;
  }
  return result;
}

```

## disassembly

```asm
0x1800c1550  mov     [rsp-8+arg_8], rbx
0x1800c1555  push    rbp
0x1800c1556  push    rsi
0x1800c1557  push    rdi
0x1800c1558  push    r12
0x1800c155a  push    r13
0x1800c155c  push    r14
0x1800c155e  push    r15
0x1800c1560  lea     rbp, [rsp-27h]
0x1800c1565  sub     rsp, 90h
0x1800c156c  lea     r15, [rcx-248h]
0x1800c1573  mov     r12, r9
0x1800c1576  mov     rbx, [r15+38h]
0x1800c157a  mov     r14, r8
0x1800c157d  mov     r13d, edx
0x1800c1580  call    ?GetData@?$CThreadLocal@V_AFX_THREAD_STATE@@@@QEAAPEAV_AFX_THREAD_STATE@@XZ; CThreadLocal<_AFX_THREAD_STATE>::GetData(void)
0x1800c1585  mov     rdi, rax
0x1800c1588  mov     rsi, [rax+8]
0x1800c158c  mov     [rax+8], rbx
0x1800c1590  xor     ebx, ebx
0x1800c1592  test    r14, r14
0x1800c1595  jz      loc_1800C174F
0x1800c159b  test    r12, r12
0x1800c159e  jz      loc_1800C174F
0x1800c15a4  lea     rax, ??_7CStringArray@@6B@; const CStringArray::`vftable'
0x1800c15ab  mov     [rbp+57h+var_78], rbx
0x1800c15af  mov     [rbp+57h+var_80], rax
0x1800c15b3  lea     r9, [rbp+57h+var_58]
0x1800c15b7  lea     rax, ??_7CDWordArray@@6B@; const CDWordArray::`vftable'
0x1800c15be  mov     [rbp+57h+var_60], rbx
0x1800c15c2  mov     [rbp+57h+var_58], rax
0x1800c15c6  lea     r8, [rbp+57h+var_80]
0x1800c15ca  mov     rax, [r15]
0x1800c15cd  mov     edx, r13d
0x1800c15d0  mov     rcx, r15
0x1800c15d3  mov     [rbp+57h+var_68], rbx
0x1800c15d7  mov     [rbp+57h+var_70], rbx
0x1800c15db  mov     [rbp+57h+var_50], rbx
0x1800c15df  mov     rax, [rax+300h]
0x1800c15e6  mov     [rbp+57h+var_38], rbx
0x1800c15ea  mov     [rbp+57h+var_40], rbx
0x1800c15ee  mov     [rbp+57h+var_48], rbx
0x1800c15f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c15f7  mov     [rbp+57h+arg_0], eax
0x1800c15fa  mov     r15d, eax
0x1800c15fd  test    eax, eax
0x1800c15ff  jz      loc_1800C172F
0x1800c1605  mov     r13d, dword ptr [rbp+57h+var_70]
0x1800c1609  mov     ebx, r13d
0x1800c160c  shl     rbx, 3
0x1800c1610  mov     rcx, rbx; cb
0x1800c1613  call    cs:__imp_CoTaskMemAlloc
0x1800c1619  xor     r15d, r15d
0x1800c161c  mov     [r14+8], rax
0x1800c1620  test    rax, rax
0x1800c1623  jnz     short loc_1800C1645
0x1800c1625  lea     rcx, [rbp+57h+var_58]; this
0x1800c1629  call    ??1CDWordArray@@UEAA@XZ; CDWordArray::~CDWordArray(void)
0x1800c162e  lea     rcx, [rbp+57h+var_80]; this
0x1800c1632  call    ??1CStringArray@@UEAA@XZ; CStringArray::~CStringArray(void)
0x1800c1637  mov     eax, 8007000Eh
0x1800c163c  mov     [rdi+8], rsi
0x1800c1640  jmp     loc_1800C1758
0x1800c1645  mov     rcx, rbx; cb
0x1800c1648  call    cs:__imp_CoTaskMemAlloc
0x1800c164e  mov     [r12+8], rax
0x1800c1653  test    rax, rax
0x1800c1656  jnz     short loc_1800C1664
0x1800c1658  mov     rcx, [r14+8]; pv
0x1800c165c  call    cs:__imp_CoTaskMemFree
0x1800c1662  jmp     short loc_1800C1625
0x1800c1664  mov     [r14], r13d
0x1800c1667  mov     ebx, r15d
0x1800c166a  mov     [r12], r13d
0x1800c166e  cmp     ebx, r13d
0x1800c1671  jge     loc_1800C1729
0x1800c1677  movsxd  r8, ebx
0x1800c167a  lea     rdx, [rbp+57h+var_88]
0x1800c167e  lea     rcx, [rbp+57h+var_80]
0x1800c1682  call    ?GetAt@CStringArray@@QEBA?AVCString@@_J@Z; CStringArray::GetAt(__int64)
0x1800c1687  mov     rcx, [rax]
0x1800c168a  mov     [rbp+57h+Source], rcx
0x1800c168e  test    rcx, rcx
0x1800c1691  jz      short loc_1800C16CC
0x1800c1693  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c1697  inc     rax
0x1800c169a  cmp     [rcx+rax*2], r15w
0x1800c169f  jnz     short loc_1800C1697
0x1800c16a1  inc     eax
0x1800c16a3  cdqe
0x1800c16a5  mov     [rbp+57h+SizeInWords], rax
0x1800c16a9  lea     rcx, [rax+rax]; cb
0x1800c16ad  call    cs:__imp_CoTaskMemAlloc
0x1800c16b3  mov     r15, rax
0x1800c16b6  test    rax, rax
0x1800c16b9  jz      short loc_1800C16CC
0x1800c16bb  mov     r8, [rbp+57h+Source]; Source
0x1800c16bf  mov     rcx, rax; Destination
0x1800c16c2  mov     rdx, [rbp+57h+SizeInWords]; SizeInWords
0x1800c16c6  call    cs:__imp_wcscpy_s
0x1800c16cc  lea     rcx, [rbp+57h+var_88]; this
0x1800c16d0  call    ??1CString@@QEAA@XZ; CString::~CString(void)
0x1800c16d5  test    r15, r15
0x1800c16d8  jz      short loc_1800C1714
0x1800c16da  mov     rax, [r14+8]
0x1800c16de  movsxd  rcx, ebx
0x1800c16e1  mov     rdx, rcx; __int64
0x1800c16e4  mov     [rax+rcx*8], r15
0x1800c16e8  lea     rcx, [rbp+57h+var_58]; this
0x1800c16ec  call    ?GetAt@CUIntArray@@QEBAI_J@Z; CUIntArray::GetAt(__int64)
0x1800c16f1  mov     rcx, [r12+8]
0x1800c16f6  movsxd  rdx, ebx
0x1800c16f9  inc     ebx
0x1800c16fb  xor     r15d, r15d
0x1800c16fe  mov     [rcx+rdx*4], eax
0x1800c1701  jmp     loc_1800C166E
0x1800c1706  mov     rcx, [r14+8]
0x1800c170a  mov     rcx, [rcx+rbx*8]; pv
0x1800c170e  call    cs:__imp_CoTaskMemFree
0x1800c1714  sub     ebx, 1
0x1800c1717  jns     short loc_1800C1706
0x1800c1719  mov     rcx, [r12+8]; pv
0x1800c171e  call    cs:__imp_CoTaskMemFree
0x1800c1724  jmp     loc_1800C1658
0x1800c1729  mov     r15d, [rbp+57h+arg_0]
0x1800c172d  xor     ebx, ebx
0x1800c172f  test    r15d, r15d
0x1800c1732  lea     rcx, [rbp+57h+var_58]; this
0x1800c1736  setz    bl
0x1800c1739  call    ??1CDWordArray@@UEAA@XZ; CDWordArray::~CDWordArray(void)
0x1800c173e  lea     rcx, [rbp+57h+var_80]; this
0x1800c1742  call    ??1CStringArray@@UEAA@XZ; CStringArray::~CStringArray(void)
0x1800c1747  mov     eax, ebx
0x1800c1749  mov     [rdi+8], rsi
0x1800c174d  jmp     short loc_1800C1758
0x1800c174f  mov     [rax+8], rsi
0x1800c1753  mov     eax, 80004003h
0x1800c1758  mov     rbx, [rsp+0C0h+arg_8]
0x1800c1760  add     rsp, 90h
0x1800c1767  pop     r15
0x1800c1769  pop     r14
0x1800c176b  pop     r13
0x1800c176d  pop     r12
0x1800c176f  pop     rdi
0x1800c1770  pop     rsi
0x1800c1771  pop     rbp
0x1800c1772  retn
```
