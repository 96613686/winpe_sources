# DIS11::DIS11Keywords::FixXML(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x180021a98`
- end: `0x180021c46`
- name: `?FixXML@DIS11Keywords@DIS11@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180021fac`

## callees

- `0x18000c048`
- `0x18000ffc0`
- `0x180014578`
- `0x1800219a0`
- `0x180021a98`
- `0x180021f10`
- `0x1800222b4`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall DIS11::DIS11Keywords::FixXML(const wchar_t *a1, _QWORD *a2, __int64 a3)
{
  unsigned int v5; // r14d
  __int64 i; // r8
  _QWORD *v7; // rax
  unsigned int v8; // ebx
  ATL::CStringData *v9; // rbx
  int v10; // eax
  int v11; // ebx
  const wchar_t *v12; // rbx
  const wchar_t *v13; // [rsp+40h] [rbp+20h] BYREF
  __int64 v14; // [rsp+48h] [rbp+28h] BYREF

  v13 = a1;
  v5 = 0;
  ATL::CSimpleStringT<unsigned short,0>::Empty(a3);
  if ( *(_DWORD *)(*a2 - 16LL) )
  {
    for ( i = 0; ; i = v5 )
    {
      v10 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
              a2,
              L"<Word title=\"",
              i);
      v11 = v10;
      if ( v10 == -1 )
        break;
      v7 = (_QWORD *)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
                       a2,
                       &v14,
                       v5,
                       v10 - v5 + 13);
      ATL::CSimpleStringT<unsigned short,0>::Append(a3, *v7, *(unsigned int *)(*v7 - 16LL));
      ATL::CStringData::Release((ATL::CStringData *)(v14 - 24));
      v8 = v11 + 13;
      v5 = ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Find(
             a2,
             L"\">\r\n",
             v8);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
        a2,
        &v13,
        v8,
        v5 - v8);
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        &v13,
        L"&",
        L"&amp;");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        &v13,
        L"<",
        L"&lt;");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        &v13,
        L">",
        L"&gt;");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        &v13,
        L"'",
        L"&apos;");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        &v13,
        L"\"",
        L"&quot;");
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Replace(
        &v13,
        L"\t",
        L"&#9;");
      v9 = (ATL::CStringData *)(v13 - 12);
      ATL::CSimpleStringT<unsigned short,0>::Append(a3, v13, *((unsigned int *)v13 - 4));
      ATL::CStringData::Release(v9);
    }
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::Mid(
      a2,
      &v13,
      v5,
      *(_DWORD *)(*a2 - 16LL) - v5);
    v12 = v13;
    ATL::CSimpleStringT<unsigned short,0>::Append(a3, v13, *((unsigned int *)v13 - 4));
    ATL::CStringData::Release((ATL::CStringData *)(v12 - 12));
  }
}

```

## disassembly

```asm
0x180021a98  mov     [rsp-18h+arg_10], rbx
0x180021a9d  mov     [rsp-18h+arg_18], rsi
0x180021aa2  mov     [rsp-18h+arg_0], rcx
0x180021aa7  push    rbp
0x180021aa8  push    rdi
0x180021aa9  push    r14
0x180021aab  mov     rbp, rsp
0x180021aae  sub     rsp, 20h
0x180021ab2  mov     rsi, r8
0x180021ab5  mov     rdi, rdx
0x180021ab8  xor     r14d, r14d
0x180021abb  mov     rcx, r8
0x180021abe  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180021ac3  mov     rax, [rdi]
0x180021ac6  cmp     [rax-10h], r14d
0x180021aca  jz      loc_180021C32
0x180021ad0  xor     r8d, r8d
0x180021ad3  jmp     loc_180021BE1
0x180021ad8  mov     r9d, ebx
0x180021adb  sub     r9d, r14d
0x180021ade  add     r9d, 0Dh
0x180021ae2  lea     rdx, [rbp+arg_8]
0x180021ae6  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180021aeb  nop
0x180021aec  mov     rdx, [rax]
0x180021aef  mov     r8d, [rdx-10h]
0x180021af3  mov     rcx, rsi
0x180021af6  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180021afb  nop
0x180021afc  mov     rcx, [rbp+arg_8]
0x180021b00  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180021b04  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021b09  add     ebx, 0Dh
0x180021b0c  mov     r8d, ebx
0x180021b0f  lea     rdx, asc_180092718; "\">\r\n"
0x180021b16  mov     rcx, rdi
0x180021b19  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x180021b1e  mov     r14d, eax
0x180021b21  mov     r9d, eax
0x180021b24  sub     r9d, ebx
0x180021b27  mov     r8d, ebx
0x180021b2a  lea     rdx, [rbp+arg_0]
0x180021b2e  mov     rcx, rdi
0x180021b31  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180021b36  nop
0x180021b37  lea     r8, aAmp; "&amp;"
0x180021b3e  lea     rdx, asc_180092614; "&"
0x180021b45  lea     rcx, [rbp+arg_0]
0x180021b49  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180021b4e  lea     r8, aLt; "&lt;"
0x180021b55  lea     rdx, asc_180092624; "<"
0x180021b5c  lea     rcx, [rbp+arg_0]
0x180021b60  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180021b65  lea     r8, aGt; "&gt;"
0x180021b6c  lea     rdx, asc_180092634; ">"
0x180021b73  lea     rcx, [rbp+arg_0]
0x180021b77  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180021b7c  lea     r8, aApos; "&apos;"
0x180021b83  lea     rdx, asc_180092648; "'"
0x180021b8a  lea     rcx, [rbp+arg_0]
0x180021b8e  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180021b93  lea     r8, aQuot; "&quot;"
0x180021b9a  lea     rdx, asc_180092660; "\""
0x180021ba1  lea     rcx, [rbp+arg_0]
0x180021ba5  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180021baa  lea     r8, a9; "&#9;"
0x180021bb1  lea     rdx, asc_180092674; "\t"
0x180021bb8  lea     rcx, [rbp+arg_0]
0x180021bbc  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180021bc1  mov     rdx, [rbp+arg_0]
0x180021bc5  lea     rbx, [rdx-18h]
0x180021bc9  mov     r8d, [rbx+8]
0x180021bcd  mov     rcx, rsi
0x180021bd0  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180021bd5  nop
0x180021bd6  mov     rcx, rbx; this
0x180021bd9  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021bde  mov     r8d, r14d
0x180021be1  lea     rdx, aWordTitle; "<Word title=\""
0x180021be8  mov     rcx, rdi
0x180021beb  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x180021bf0  cmp     eax, 0FFFFFFFFh
0x180021bf3  mov     ebx, eax
0x180021bf5  mov     r8d, r14d
0x180021bf8  mov     rcx, rdi
0x180021bfb  jnz     loc_180021AD8
0x180021c01  mov     rax, [rdi]
0x180021c04  mov     r9d, [rax-10h]
0x180021c08  sub     r9d, r14d
0x180021c0b  lea     rdx, [rbp+arg_0]
0x180021c0f  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180021c14  nop
0x180021c15  mov     rbx, [rbp+arg_0]
0x180021c19  mov     r8d, [rbx-10h]
0x180021c1d  mov     rdx, rbx
0x180021c20  mov     rcx, rsi
0x180021c23  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180021c28  nop
0x180021c29  lea     rcx, [rbx-18h]; this
0x180021c2d  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180021c32  mov     rbx, [rsp+20h+arg_10]
0x180021c37  mov     rsi, [rsp+20h+arg_18]
0x180021c3c  add     rsp, 20h
0x180021c40  pop     r14
0x180021c42  pop     rdi
0x180021c43  pop     rbp
0x180021c44  retn
```
