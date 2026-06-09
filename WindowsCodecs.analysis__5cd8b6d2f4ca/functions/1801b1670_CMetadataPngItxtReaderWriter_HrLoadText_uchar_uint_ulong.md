# CMetadataPngItxtReaderWriter::HrLoadText(uchar *,uint,ulong *)

- ea: `0x1801b1670`
- end: `0x1801b18f6`
- name: `?HrLoadText@CMetadataPngItxtReaderWriter@@MEAAJPEAEIPEAK@Z`
- size: `646`
- prototype: `__int64 __fastcall(CMetadataPngItxtReaderWriter *this, unsigned __int8 *, UINT, unsigned int *)`
- caller_count: `1`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callers

- `0x180050860`

## callees

- `0x1800190fc`
- `0x18001cfe8`
- `0x18001da9c`
- `0x180039480`
- `0x1800ae1c0`
- `0x1800bd9d4`
- `0x1800e6af4`
- `0x18017e438`
- `0x1801b1670`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b16d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b1782`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b17dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b16d2`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b1782`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801b17dd`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b17ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b1807`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b1855`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b1866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b18cc`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b17ac`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b1807`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b1855`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b1866`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1801b18cc`

## pseudocode

```c
__int64 __fastcall CMetadataPngItxtReaderWriter::HrLoadText(
        CMetadataPngItxtReaderWriter *this,
        unsigned __int8 *a2,
        UINT a3,
        unsigned int *a4)
{
  bool v4; // zf
  unsigned int *v5; // rsi
  unsigned __int8 *v7; // r14
  int v9; // ebx
  HRESULT v10; // eax
  UINT v11; // r12d
  void *v12; // rsi
  unsigned int v13; // ebx
  unsigned __int8 *v14; // rdi
  size_t v15; // rbx
  int v16; // eax
  unsigned __int8 *v17; // rax
  unsigned __int8 *v18; // r14
  unsigned __int8 *v19; // rax
  unsigned __int8 *v20; // r14
  int v21; // eax
  unsigned __int8 *v23; // [rsp+38h] [rbp-39h] BYREF
  UINT v24; // [rsp+40h] [rbp-31h]
  void *v25; // [rsp+48h] [rbp-29h]
  UINT v26; // [rsp+50h] [rbp-21h]
  SIZE_T cb; // [rsp+54h] [rbp-1Dh]
  UINT puResult; // [rsp+D8h] [rbp+67h] BYREF
  unsigned __int8 *v29; // [rsp+E0h] [rbp+6Fh]
  unsigned int *v30; // [rsp+F0h] [rbp+7Fh]

  v30 = a4;
  v29 = a2;
  v4 = *((_BYTE *)this + 168) == 1;
  v5 = a4;
  v7 = a2;
  puResult = 0;
  v9 = a3;
  if ( v4 )
  {
    v10 = ULongLongToUInt(2LL * a3, &puResult);
    v11 = puResult;
    if ( v10 < 0 )
      v11 = a3;
    v12 = CoTaskMemAlloc(v11);
    if ( !v12 )
    {
      v13 = -2147024882;
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2147024882);
      return v13;
    }
    v14 = 0;
    memset_0(&v23, 0, 0x58u);
    if ( (unsigned int)inflateInit2_(&v23, 15, "1.3.1", 88) )
    {
      v13 = -2003292304;
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(-2003292304);
    }
    else
    {
      v15 = 0;
      v23 = v7;
      v24 = a3;
LABEL_11:
      v26 = v11;
      v25 = v12;
      while ( 1 )
      {
        v16 = inflate(&v23, 2);
        if ( v16 == 1 )
          break;
        if ( v16 )
          goto LABEL_24;
        if ( !v26 )
        {
          v17 = (unsigned __int8 *)CoTaskMemAlloc((unsigned int)cb);
          v18 = v17;
          if ( !v17 )
            goto LABEL_19;
          if ( v14 )
          {
            memcpy_0(v17, v14, v15);
            CoTaskMemFree(v14);
          }
          v14 = v18;
          memcpy_0(&v18[v15], v12, (unsigned int)cb - v15);
          v15 = (unsigned int)cb;
          goto LABEL_11;
        }
      }
      v19 = (unsigned __int8 *)CoTaskMemAlloc((unsigned int)cb);
      v20 = v19;
      if ( !v19 )
      {
LABEL_19:
        v13 = -2147024882;
        goto LABEL_25;
      }
      if ( v14 )
      {
        memcpy_0(v19, v14, v15);
        CoTaskMemFree(v14);
      }
      v14 = v20;
      memcpy_0(&v20[v15], v12, (unsigned int)cb - v15);
      v9 = cb;
      if ( !(unsigned int)inflateEnd(&v23) )
      {
        CoTaskMemFree(v12);
        v7 = v29;
        v5 = v30;
        goto LABEL_31;
      }
LABEL_24:
      v13 = -2003292304;
LABEL_25:
      if ( (_DWORD)g_doStackCaptures )
        DoStackCapture(v13);
      v7 = v29;
    }
    CoTaskMemFree(v12);
  }
  else
  {
    v14 = a2;
LABEL_31:
    v21 = CMetadataPngItxtReaderWriter::ConvertMultiByteToWideChar(
            this,
            (char *)v14,
            v9,
            (unsigned __int16 **)this + 26,
            (unsigned __int64 *)this + 27);
    v13 = v21;
    if ( v21 >= 0 )
    {
      *v5 = a3;
    }
    else if ( (_DWORD)g_doStackCaptures )
    {
      DoStackCapture(v21);
    }
  }
  if ( v14 && v14 != v7 )
    CoTaskMemFree(v14);
  return v13;
}

```

## disassembly

```asm
0x1801b1670  mov     rax, rsp
0x1801b1673  mov     [rax+18h], rbx
0x1801b1677  mov     [rax+20h], r9
0x1801b167b  mov     [rax+10h], rdx
0x1801b167f  push    rbp
0x1801b1680  push    rsi
0x1801b1681  push    rdi
0x1801b1682  push    r12
0x1801b1684  push    r13
0x1801b1686  push    r14
0x1801b1688  push    r15
0x1801b168a  lea     rbp, [rax-5Fh]
0x1801b168e  sub     rsp, 90h
0x1801b1695  cmp     byte ptr [rcx+0A8h], 1
0x1801b169c  mov     rsi, r9
0x1801b169f  mov     r15d, r8d
0x1801b16a2  mov     r14, rdx
0x1801b16a5  mov     r13, rcx
0x1801b16a8  mov     [rbp+57h+puResult], 0
0x1801b16af  mov     ebx, r8d
0x1801b16b2  jnz     loc_1801B187C
0x1801b16b8  lea     rcx, [r15+r15]; ullOperand
0x1801b16bc  lea     rdx, [rbp+57h+puResult]; puResult
0x1801b16c0  call    ULongLongToUInt
0x1801b16c5  mov     r12d, [rbp+57h+puResult]
0x1801b16c9  test    eax, eax
0x1801b16cb  cmovs   r12d, r15d
0x1801b16cf  mov     ecx, r12d; cb
0x1801b16d2  call    cs:__imp_CoTaskMemAlloc
0x1801b16d9  nop     dword ptr [rax+rax+00h]
0x1801b16de  mov     rsi, rax
0x1801b16e1  test    rax, rax
0x1801b16e4  jnz     short loc_1801B1703
0x1801b16e6  cmp     cs:?g_doStackCaptures@@3HA, eax; int g_doStackCaptures
0x1801b16ec  mov     ebx, 8007000Eh
0x1801b16f1  jz      loc_1801B18D8
0x1801b16f7  mov     ecx, ebx; int
0x1801b16f9  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b16fe  jmp     loc_1801B18D8
0x1801b1703  xor     edi, edi
0x1801b1705  lea     rcx, [rbp+57h+var_90]; void *
0x1801b1709  xor     edx, edx; Val
0x1801b170b  lea     ebx, [rdi+58h]
0x1801b170e  mov     r8d, ebx; Size
0x1801b1711  call    memset_0
0x1801b1716  mov     r9d, ebx
0x1801b1719  lea     r8, a131; "1.3.1"
0x1801b1720  lea     edx, [rdi+0Fh]
0x1801b1723  lea     rcx, [rbp+57h+var_90]
0x1801b1727  call    inflateInit2_
0x1801b172c  test    eax, eax
0x1801b172e  jz      short loc_1801B174D
0x1801b1730  cmp     cs:?g_doStackCaptures@@3HA, edi; int g_doStackCaptures
0x1801b1736  mov     ebx, 88982F70h
0x1801b173b  jz      loc_1801B1852
0x1801b1741  mov     ecx, ebx; int
0x1801b1743  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b1748  jmp     loc_1801B1852
0x1801b174d  xor     ebx, ebx
0x1801b174f  mov     [rbp+57h+var_90], r14
0x1801b1753  mov     [rbp+57h+var_88], r15d
0x1801b1757  mov     [rbp+57h+var_78], r12d
0x1801b175b  mov     [rbp+57h+var_80], rsi
0x1801b175f  mov     edx, 2
0x1801b1764  lea     rcx, [rbp+57h+var_90]
0x1801b1768  call    inflate
0x1801b176d  cmp     eax, 1
0x1801b1770  jz      short loc_1801B17DA
0x1801b1772  test    eax, eax
0x1801b1774  jnz     loc_1801B1839
0x1801b177a  cmp     [rbp+57h+var_78], eax
0x1801b177d  jnz     short loc_1801B175F
0x1801b177f  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x1801b1782  call    cs:__imp_CoTaskMemAlloc
0x1801b1789  nop     dword ptr [rax+rax+00h]
0x1801b178e  mov     r14, rax
0x1801b1791  test    rax, rax
0x1801b1794  jz      short loc_1801B17D3
0x1801b1796  test    rdi, rdi
0x1801b1799  jz      short loc_1801B17B8
0x1801b179b  mov     r8, rbx; Size
0x1801b179e  mov     rdx, rdi; Src
0x1801b17a1  mov     rcx, rax; void *
0x1801b17a4  call    memcpy_0
0x1801b17a9  mov     rcx, rdi; pv
0x1801b17ac  call    cs:__imp_CoTaskMemFree
0x1801b17b3  nop     dword ptr [rax+rax+00h]
0x1801b17b8  mov     r8d, dword ptr [rbp+57h+cb]
0x1801b17bc  lea     rcx, [r14+rbx]; void *
0x1801b17c0  sub     r8, rbx; Size
0x1801b17c3  mov     rdx, rsi; Src
0x1801b17c6  mov     rdi, r14
0x1801b17c9  call    memcpy_0
0x1801b17ce  mov     ebx, dword ptr [rbp+57h+cb]
0x1801b17d1  jmp     short loc_1801B1757
0x1801b17d3  mov     ebx, 8007000Eh
0x1801b17d8  jmp     short loc_1801B183E
0x1801b17da  mov     ecx, dword ptr [rbp+57h+cb]; cb
0x1801b17dd  call    cs:__imp_CoTaskMemAlloc
0x1801b17e4  nop     dword ptr [rax+rax+00h]
0x1801b17e9  mov     r14, rax
0x1801b17ec  test    rax, rax
0x1801b17ef  jz      short loc_1801B17D3
0x1801b17f1  test    rdi, rdi
0x1801b17f4  jz      short loc_1801B1813
0x1801b17f6  mov     r8, rbx; Size
0x1801b17f9  mov     rdx, rdi; Src
0x1801b17fc  mov     rcx, rax; void *
0x1801b17ff  call    memcpy_0
0x1801b1804  mov     rcx, rdi; pv
0x1801b1807  call    cs:__imp_CoTaskMemFree
0x1801b180e  nop     dword ptr [rax+rax+00h]
0x1801b1813  mov     r8d, dword ptr [rbp+57h+cb]
0x1801b1817  lea     rcx, [r14+rbx]; void *
0x1801b181b  sub     r8, rbx; Size
0x1801b181e  mov     rdx, rsi; Src
0x1801b1821  mov     rdi, r14
0x1801b1824  call    memcpy_0
0x1801b1829  mov     ebx, dword ptr [rbp+57h+cb]
0x1801b182c  lea     rcx, [rbp+57h+var_90]
0x1801b1830  call    inflateEnd
0x1801b1835  test    eax, eax
0x1801b1837  jz      short loc_1801B1863
0x1801b1839  mov     ebx, 88982F70h
0x1801b183e  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b1845  jz      short loc_1801B184E
0x1801b1847  mov     ecx, ebx; int
0x1801b1849  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b184e  mov     r14, [rbp+57h+arg_8]
0x1801b1852  mov     rcx, rsi; pv
0x1801b1855  call    cs:__imp_CoTaskMemFree
0x1801b185c  nop     dword ptr [rax+rax+00h]
0x1801b1861  jmp     short loc_1801B18BF
0x1801b1863  mov     rcx, rsi; pv
0x1801b1866  call    cs:__imp_CoTaskMemFree
0x1801b186d  nop     dword ptr [rax+rax+00h]
0x1801b1872  mov     r14, [rbp+57h+arg_8]
0x1801b1876  mov     rsi, [rbp+57h+arg_18]
0x1801b187a  jmp     short loc_1801B187F
0x1801b187c  mov     rdi, r14
0x1801b187f  lea     rax, [r13+0D8h]
0x1801b1886  mov     r8, rbx; unsigned __int64
0x1801b1889  lea     r9, [r13+0D0h]; unsigned __int16 **
0x1801b1890  mov     [rsp+20h], rax; unsigned __int64 *
0x1801b1895  mov     rdx, rdi; char *
0x1801b1898  mov     rcx, r13; this
0x1801b189b  call    ?ConvertMultiByteToWideChar@CMetadataPngItxtReaderWriter@@MEAAJPEAD_KPEAPEAGPEA_K@Z; CMetadataPngItxtReaderWriter::ConvertMultiByteToWideChar(char *,unsigned __int64,ushort * *,unsigned __int64 *)
0x1801b18a0  mov     ebx, eax
0x1801b18a2  test    eax, eax
0x1801b18a4  jns     short loc_1801B18BC
0x1801b18a6  cmp     cs:?g_doStackCaptures@@3HA, 0; int g_doStackCaptures
0x1801b18ad  jz      short loc_1801B18B8
0x1801b18af  mov     ecx, eax; int
0x1801b18b1  call    ?DoStackCapture@@YAXJ@Z; DoStackCapture(long)
0x1801b18b6  jmp     short loc_1801B18BF
0x1801b18b8  test    eax, eax
0x1801b18ba  js      short loc_1801B18BF
0x1801b18bc  mov     [rsi], r15d
0x1801b18bf  test    rdi, rdi
0x1801b18c2  jz      short loc_1801B18D8
0x1801b18c4  cmp     rdi, r14
0x1801b18c7  jz      short loc_1801B18D8
0x1801b18c9  mov     rcx, rdi; pv
0x1801b18cc  call    cs:__imp_CoTaskMemFree
0x1801b18d3  nop     dword ptr [rax+rax+00h]
0x1801b18d8  mov     eax, ebx
0x1801b18da  mov     rbx, [rsp+0C0h+arg_10]
0x1801b18e2  add     rsp, 90h
0x1801b18e9  pop     r15
0x1801b18eb  pop     r14
0x1801b18ed  pop     r13
0x1801b18ef  pop     r12
0x1801b18f1  pop     rdi
0x1801b18f2  pop     rsi
0x1801b18f3  pop     rbp
0x1801b18f4  retn
```
