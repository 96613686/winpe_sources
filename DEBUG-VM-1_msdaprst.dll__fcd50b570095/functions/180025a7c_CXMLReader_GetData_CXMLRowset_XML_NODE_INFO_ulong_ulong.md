# CXMLReader::GetData(CXMLRowset *,_XML_NODE_INFO * *,ulong *,ulong)

- ea: `0x180025a7c`
- end: `0x180025d25`
- name: `?GetData@CXMLReader@@QEAAJPEAVCXMLRowset@@PEAPEAU_XML_NODE_INFO@@PEAKK@Z`
- size: `681`
- prototype: `__int64 __fastcall(CXMLReader *__hidden this, struct CXMLRowset *, struct _XML_NODE_INFO **, unsigned int *, unsigned int)`
- caller_count: `1`
- callee_count: `6`
- tags: `registry_config`

## callers

- `0x180025654`

## callees

- `0x180001d94`
- `0x180002650`
- `0x180025a7c`
- `0x1800272f0`
- `0x180028ee0`
- `0x18002e012`

## import_xrefs

- `OLEAUT32!__imp_SysAllocStringLen` at `0x180025bf8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180025c18`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180025c42`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180025bf8`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180025c18`
- `OLEAUT32!__imp_SysAllocStringLen` at `0x180025c42`
- `OLEAUT32!__imp_SysFreeString` at `0x180025c72`
- `OLEAUT32!__imp_SysFreeString` at `0x180025c86`
- `OLEAUT32!__imp_SysFreeString` at `0x180025c95`
- `OLEAUT32!__imp_SysFreeString` at `0x180025c72`
- `OLEAUT32!__imp_SysFreeString` at `0x180025c86`
- `OLEAUT32!__imp_SysFreeString` at `0x180025c95`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CXMLReader::GetData(
        CCollectionList **this,
        struct CXMLRowset *a2,
        struct _XML_NODE_INFO **a3,
        unsigned int *a4,
        unsigned int a5)
{
  CCollectionList **v5; // rbx
  const OLECHAR *v6; // rsi
  unsigned __int16 *v7; // r10
  int v8; // edx
  const OLECHAR *v9; // r14
  UINT v10; // ecx
  struct _XML_NODE_INFO **v11; // rdi
  unsigned int v12; // r13d
  struct _XML_NODE_INFO **v13; // r12
  unsigned int v14; // r15d
  struct _XML_NODE_INFO *v15; // rax
  unsigned __int128 v16; // rax
  unsigned __int8 *v17; // rax
  unsigned __int8 *v18; // rcx
  unsigned __int8 *v19; // r15
  struct _XML_NODE_INFO *v20; // rbx
  char v21; // di
  int v22; // eax
  int v23; // ecx
  OLECHAR *v24; // rbx
  char v25; // r12
  unsigned __int16 *v26; // rsi
  OLECHAR *v27; // rdi
  unsigned __int16 *v28; // r13
  unsigned __int16 *v29; // r14
  __int64 v30; // rax
  __int64 v31; // rdx
  UINT ui; // [rsp+30h] [rbp-28h]
  unsigned __int64 v34; // [rsp+38h] [rbp-20h] BYREF
  unsigned __int8 *v35; // [rsp+40h] [rbp-18h] BYREF
  unsigned __int16 *v36; // [rsp+48h] [rbp-10h]
  unsigned __int8 *v39; // [rsp+B0h] [rbp+58h]

  v5 = this;
  v6 = 0;
  v34 = 0;
  v7 = (unsigned __int16 *)*a3;
  v36 = (unsigned __int16 *)*a3;
  v8 = *a4;
  v9 = 0;
  v35 = 0;
  v10 = 0;
  ui = 0;
  v11 = a3 + 1;
  v12 = v8 + 1;
  v13 = a3 + 1;
  v14 = 1;
  if ( v8 + 1 < a5 )
  {
    do
    {
      v15 = *v13;
      if ( !*v13 )
        break;
      if ( *((_DWORD *)v15 + 1) != 13 )
        break;
      v10 += *((_DWORD *)v15 + 6);
      ++v13;
      ++v12;
    }
    while ( v12 < a5 );
    ui = v10;
  }
  if ( v12 - v8 == 1 )
  {
    v6 = (const OLECHAR *)&wszZls;
    goto LABEL_19;
  }
  if ( v12 - v8 == 2 )
  {
    v6 = (const OLECHAR *)*((_QWORD *)*v11 + 2);
LABEL_19:
    v21 = 0;
    goto LABEL_20;
  }
  v16 = (v10 + 1) * (unsigned __int128)2uLL;
  if ( !is_mul_ok(v10 + 1, 2u) )
    LODWORD(v16) = -1;
  v17 = MMMAlloc(v16, DWORD2(v16));
  v9 = (const OLECHAR *)v17;
  v35 = v17;
  if ( v17 )
  {
    v18 = v17;
    if ( v11 < v13 )
    {
      v19 = v17;
      do
      {
        v20 = *v11;
        memcpy_0(v19, *((const void **)*v11 + 2), 2LL * *((unsigned int *)*v11 + 6));
        v19 += 2 * *((unsigned int *)v20 + 6);
        ++v11;
      }
      while ( v11 < v13 );
      v39 = v19;
      v14 = 1;
      v18 = v39;
      v5 = this;
    }
    *(_WORD *)v18 = 0;
    v21 = 1;
    v7 = v36;
LABEL_20:
    v22 = CCollectionList::LookUpByKey(
            (struct CXMLRowset *)((char *)a2 + 552),
            *((unsigned __int16 **)v7 + 2),
            *((_DWORD *)v7 + 6),
            &v34);
    v23 = *((_DWORD *)v5 + 119);
    if ( v22 )
    {
      if ( v23 != 1 )
        goto LABEL_38;
      v5[17] = (CCollectionList *)*((_QWORD *)a2 + 79);
      if ( v21 )
      {
        v24 = SysAllocStringLen(v9, ui);
        v25 = 1;
        v26 = v24;
        v27 = v24;
      }
      else
      {
        v26 = SysAllocStringLen(v6, ui);
        v27 = v26;
        v25 = 2;
        v24 = v26;
      }
      v28 = v36;
      v29 = SysAllocStringLen(*((const OLECHAR **)v36 + 2), *((_DWORD *)v36 + 6));
      v36 = v29;
      CXMLReader::ProcessRowsetAttribute(this, *((_DWORD *)v28 + 7), v29, v26, a2);
      SysFreeString(v29);
      if ( (v25 & 2) != 0 )
      {
        v25 &= ~2u;
        SysFreeString(v27);
      }
      if ( (v25 & 1) != 0 )
        SysFreeString(v24);
      this[17] = (CCollectionList *)*((_QWORD *)this[17] + 6);
    }
    else
    {
      if ( ((v23 - 4) & 0xFFFFFFFB) != 0 )
        v30 = *((_QWORD *)a2 + 35);
      else
        v30 = *((_QWORD *)a2 + 36);
      v31 = *(_QWORD *)(v30 + 8LL * (unsigned int)v34);
      *(_QWORD *)v31 = ui;
      if ( v21 )
      {
        v35 = 0;
        *(_DWORD *)(v31 + 4) = 0x1000000;
      }
      else
      {
        v9 = v6;
      }
      *(_QWORD *)(v31 + 8) = v9;
      *a4 = v12 - 1;
    }
    v14 = 0;
    goto LABEL_38;
  }
  v14 = -2147024882;
LABEL_38:
  CAutoP<_GUID>::~CAutoP<_GUID>(&v35);
  return v14;
}

```

## disassembly

```asm
0x180025a7c  mov     [rsp-40h+bstrString], r9
0x180025a81  mov     [rsp-40h+arg_8], rdx
0x180025a86  mov     [rsp-40h+arg_0], rcx
0x180025a8b  push    rbp
0x180025a8c  push    rbx
0x180025a8d  push    rsi
0x180025a8e  push    rdi
0x180025a8f  push    r12
0x180025a91  push    r13
0x180025a93  push    r14
0x180025a95  push    r15
0x180025a97  mov     rbp, rsp
0x180025a9a  sub     rsp, 58h
0x180025a9e  mov     rbx, rcx
0x180025aa1  xor     esi, esi
0x180025aa3  mov     dword ptr [rbp+arg_10], esi
0x180025aa6  mov     [rbp+var_20], rsi
0x180025aaa  mov     r10, [r8]
0x180025aad  mov     [rbp+var_10], r10
0x180025ab1  mov     edx, [r9]; unsigned int
0x180025ab4  mov     r14d, esi
0x180025ab7  mov     [rbp+var_18], rsi
0x180025abb  mov     byte ptr [rbp+arg_10], sil
0x180025abf  mov     ecx, esi
0x180025ac1  mov     [rbp+ui], ecx
0x180025ac4  lea     rdi, [r8+8]
0x180025ac8  lea     r13d, [rdx+1]
0x180025acc  mov     r12, rdi
0x180025acf  lea     r15d, [rsi+1]
0x180025ad3  cmp     r13d, [rbp+arg_20]
0x180025ad7  jnb     short loc_180025AFB
0x180025ad9  mov     rax, [r12]
0x180025add  test    rax, rax
0x180025ae0  jz      short loc_180025AF8
0x180025ae2  cmp     dword ptr [rax+4], 0Dh
0x180025ae6  jnz     short loc_180025AF8
0x180025ae8  add     ecx, [rax+18h]
0x180025aeb  add     r12, 8
0x180025aef  add     r13d, r15d
0x180025af2  cmp     r13d, [rbp+arg_20]
0x180025af6  jb      short loc_180025AD9
0x180025af8  mov     [rbp+ui], ecx
0x180025afb  mov     eax, r13d
0x180025afe  sub     eax, edx
0x180025b00  sub     eax, r15d
0x180025b03  jz      loc_180025B9F
0x180025b09  cmp     eax, r15d
0x180025b0c  jz      loc_180025B96
0x180025b12  inc     ecx
0x180025b14  mov     eax, 2
0x180025b19  mul     rcx
0x180025b1c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x180025b23  cmovb   rax, rcx
0x180025b27  mov     ecx, eax; unsigned int
0x180025b29  call    ?MMMAlloc@@YAPEAEIK@Z; MMMAlloc(uint,ulong)
0x180025b2e  mov     r14, rax
0x180025b31  mov     [rbp+var_18], rax
0x180025b35  test    rax, rax
0x180025b38  jnz     short loc_180025B45
0x180025b3a  mov     r15d, 8007000Eh
0x180025b40  jmp     loc_180025D08
0x180025b45  mov     rcx, rax
0x180025b48  cmp     rdi, r12
0x180025b4b  jnb     short loc_180025B88
0x180025b4d  mov     r15, rax
0x180025b50  mov     rbx, [rdi]
0x180025b53  mov     r8d, [rbx+18h]
0x180025b57  add     r8, r8; Size
0x180025b5a  mov     rdx, [rbx+10h]; Src
0x180025b5e  mov     rcx, r15; void *
0x180025b61  call    memcpy_0
0x180025b66  mov     eax, [rbx+18h]
0x180025b69  lea     r15, [r15+rax*2]
0x180025b6d  add     rdi, 8
0x180025b71  cmp     rdi, r12
0x180025b74  jb      short loc_180025B50
0x180025b76  mov     [rbp+arg_10], r15
0x180025b7a  mov     r15d, 1
0x180025b80  mov     rcx, [rbp+arg_10]
0x180025b84  mov     rbx, [rbp+arg_0]
0x180025b88  xor     eax, eax
0x180025b8a  mov     [rcx], ax
0x180025b8d  mov     dil, r15b
0x180025b90  mov     r10, [rbp+var_10]
0x180025b94  jmp     short loc_180025BAA
0x180025b96  mov     rax, [rdi]
0x180025b99  mov     rsi, [rax+10h]
0x180025b9d  jmp     short loc_180025BA6
0x180025b9f  lea     rsi, ?wszZls@@3PAGA; ushort near * wszZls
0x180025ba6  mov     dil, byte ptr [rbp+arg_10]
0x180025baa  mov     r12, [rbp+arg_8]
0x180025bae  lea     rcx, [r12+228h]; this
0x180025bb6  lea     r9, [rbp+var_20]; unsigned __int64 *
0x180025bba  mov     r8d, [r10+18h]; unsigned int
0x180025bbe  mov     rdx, [r10+10h]; unsigned __int16 *
0x180025bc2  call    ?LookUpByKey@CCollectionList@@QEAAJPEAGKPEA_K@Z; CCollectionList::LookUpByKey(ushort *,ulong,unsigned __int64 *)
0x180025bc7  mov     ecx, [rbx+1DCh]
0x180025bcd  test    eax, eax
0x180025bcf  jz      loc_180025CAF
0x180025bd5  cmp     ecx, r15d
0x180025bd8  jnz     loc_180025D08
0x180025bde  mov     rax, [r12+278h]
0x180025be6  mov     [rbx+88h], rax
0x180025bed  mov     edx, [rbp+ui]; ui
0x180025bf0  test    dil, dil
0x180025bf3  jz      short loc_180025C15
0x180025bf5  mov     rcx, r14; strIn
0x180025bf8  call    cs:__imp_SysAllocStringLen
0x180025bfe  mov     rbx, rax
0x180025c01  mov     [rbp+bstrString], rax
0x180025c05  mov     r12d, r15d
0x180025c08  mov     dword ptr [rbp+arg_10], r15d
0x180025c0c  mov     rsi, rax
0x180025c0f  mov     rdi, [rbp+bstrString]
0x180025c13  jmp     short loc_180025C36
0x180025c15  mov     rcx, rsi; strIn
0x180025c18  call    cs:__imp_SysAllocStringLen
0x180025c1e  mov     rsi, rax
0x180025c21  mov     rdi, rax
0x180025c24  mov     [rbp+bstrString], rax
0x180025c28  mov     r12d, 2
0x180025c2e  mov     dword ptr [rbp+arg_10], r12d
0x180025c32  mov     rbx, [rbp+bstrString]
0x180025c36  mov     r13, [rbp+var_10]
0x180025c3a  mov     edx, [r13+18h]; ui
0x180025c3e  mov     rcx, [r13+10h]; strIn
0x180025c42  call    cs:__imp_SysAllocStringLen
0x180025c48  mov     r14, rax
0x180025c4b  mov     [rbp+var_10], rax
0x180025c4f  mov     rdx, [rbp+arg_8]
0x180025c53  mov     [rsp+58h+var_38], rdx; struct CXMLRowset *
0x180025c58  mov     r9, rsi; unsigned __int16 *
0x180025c5b  mov     r8, rax; unsigned __int16 *
0x180025c5e  mov     edx, [r13+1Ch]; unsigned int
0x180025c62  mov     rsi, [rbp+arg_0]
0x180025c66  mov     rcx, rsi; this
0x180025c69  call    ?ProcessRowsetAttribute@CXMLReader@@AEAAJKPEAG0PEAVCXMLRowset@@@Z; CXMLReader::ProcessRowsetAttribute(ulong,ushort *,ushort *,CXMLRowset *)
0x180025c6e  nop
0x180025c6f  mov     rcx, r14; bstrString
0x180025c72  call    cs:__imp_SysFreeString
0x180025c78  nop
0x180025c79  test    r12b, 2
0x180025c7d  jz      short loc_180025C8D
0x180025c7f  and     r12d, 0FFFFFFFDh
0x180025c83  mov     rcx, rdi; bstrString
0x180025c86  call    cs:__imp_SysFreeString
0x180025c8c  nop
0x180025c8d  test    r15b, r12b
0x180025c90  jz      short loc_180025C9B
0x180025c92  mov     rcx, rbx; bstrString
0x180025c95  call    cs:__imp_SysFreeString
0x180025c9b  mov     rax, [rsi+88h]
0x180025ca2  mov     rcx, [rax+30h]
0x180025ca6  mov     [rsi+88h], rcx
0x180025cad  jmp     short loc_180025D05
0x180025caf  lea     eax, [rcx-4]
0x180025cb2  mov     ecx, dword ptr [rbp+var_20]
0x180025cb5  test    eax, 0FFFFFFFBh
0x180025cba  jz      short loc_180025CC6
0x180025cbc  mov     rax, [r12+118h]
0x180025cc4  jmp     short loc_180025CCE
0x180025cc6  mov     rax, [r12+120h]
0x180025cce  mov     rdx, [rax+rcx*8]
0x180025cd2  mov     eax, [rbp+ui]
0x180025cd5  mov     [rdx], eax
0x180025cd7  mov     dword ptr [rdx+4], 0
0x180025cde  test    dil, dil
0x180025ce1  jz      short loc_180025CF4
0x180025ce3  mov     [rbp+var_18], 0
0x180025ceb  mov     dword ptr [rdx+4], 1000000h
0x180025cf2  jmp     short loc_180025CF7
0x180025cf4  mov     r14, rsi
0x180025cf7  mov     [rdx+8], r14
0x180025cfb  lea     eax, [r13-1]
0x180025cff  mov     rcx, [rbp+bstrString]
0x180025d03  mov     [rcx], eax
0x180025d05  xor     r15d, r15d
0x180025d08  lea     rcx, [rbp+var_18]
0x180025d0c  call    ??1?$CAutoP@U_GUID@@@@QEAA@XZ; CAutoP<_GUID>::~CAutoP<_GUID>(void)
0x180025d11  mov     eax, r15d
0x180025d14  add     rsp, 58h
0x180025d18  pop     r15
0x180025d1a  pop     r14
0x180025d1c  pop     r13
0x180025d1e  pop     r12
0x180025d20  pop     rdi
0x180025d21  pop     rsi
0x180025d22  pop     rbx
0x180025d23  pop     rbp
0x180025d24  retn
```
