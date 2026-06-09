# DIS11::DIS11Keywords::FixXML(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> *)

- ea: `0x180020a30`
- end: `0x180020bdd`
- name: `?FixXML@DIS11Keywords@DIS11@@AEAAXAEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@PEAV34@@Z`
- size: `429`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config`

## callers

- `0x180020f20`

## callees

- `0x18000bac0`
- `0x18000f944`
- `0x180013bcc`
- `0x18002093c`
- `0x180020a30`
- `0x180020e84`
- `0x180021204`

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
0x180020a30  mov     [rsp-18h+arg_10], rbx
0x180020a35  mov     [rsp-18h+arg_18], rsi
0x180020a3a  mov     [rsp-18h+arg_0], rcx
0x180020a3f  push    rbp
0x180020a40  push    rdi
0x180020a41  push    r14
0x180020a43  mov     rbp, rsp
0x180020a46  sub     rsp, 20h
0x180020a4a  mov     rsi, r8
0x180020a4d  mov     rdi, rdx
0x180020a50  xor     r14d, r14d
0x180020a53  mov     rcx, r8
0x180020a56  call    ?Empty@?$CSimpleStringT@G$0A@@ATL@@QEAAXXZ; ATL::CSimpleStringT<ushort,0>::Empty(void)
0x180020a5b  mov     rax, [rdi]
0x180020a5e  cmp     [rax-10h], r14d
0x180020a62  jz      loc_180020BCA
0x180020a68  xor     r8d, r8d
0x180020a6b  jmp     loc_180020B79
0x180020a70  mov     r9d, ebx
0x180020a73  sub     r9d, r14d
0x180020a76  add     r9d, 0Dh
0x180020a7a  lea     rdx, [rbp+arg_8]
0x180020a7e  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180020a83  nop
0x180020a84  mov     rdx, [rax]
0x180020a87  mov     r8d, [rdx-10h]
0x180020a8b  mov     rcx, rsi
0x180020a8e  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180020a93  nop
0x180020a94  mov     rcx, [rbp+arg_8]
0x180020a98  add     rcx, 0FFFFFFFFFFFFFFE8h; this
0x180020a9c  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020aa1  add     ebx, 0Dh
0x180020aa4  mov     r8d, ebx
0x180020aa7  lea     rdx, asc_180091758; "\">\r\n"
0x180020aae  mov     rcx, rdi
0x180020ab1  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x180020ab6  mov     r14d, eax
0x180020ab9  mov     r9d, eax
0x180020abc  sub     r9d, ebx
0x180020abf  mov     r8d, ebx
0x180020ac2  lea     rdx, [rbp+arg_0]
0x180020ac6  mov     rcx, rdi
0x180020ac9  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180020ace  nop
0x180020acf  lea     r8, aAmp; "&amp;"
0x180020ad6  lea     rdx, asc_180091654; "&"
0x180020add  lea     rcx, [rbp+arg_0]
0x180020ae1  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180020ae6  lea     r8, aLt; "&lt;"
0x180020aed  lea     rdx, asc_180091664; "<"
0x180020af4  lea     rcx, [rbp+arg_0]
0x180020af8  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180020afd  lea     r8, aGt; "&gt;"
0x180020b04  lea     rdx, asc_180091674; ">"
0x180020b0b  lea     rcx, [rbp+arg_0]
0x180020b0f  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180020b14  lea     r8, aApos; "&apos;"
0x180020b1b  lea     rdx, asc_180091688; "'"
0x180020b22  lea     rcx, [rbp+arg_0]
0x180020b26  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180020b2b  lea     r8, aQuot; "&quot;"
0x180020b32  lea     rdx, asc_1800916A0; "\""
0x180020b39  lea     rcx, [rbp+arg_0]
0x180020b3d  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180020b42  lea     r8, a9; "&#9;"
0x180020b49  lea     rdx, asc_1800916B4; "\t"
0x180020b50  lea     rcx, [rbp+arg_0]
0x180020b54  call    ?Replace@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAHPEBG0@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Replace(ushort const *,ushort const *)
0x180020b59  mov     rdx, [rbp+arg_0]
0x180020b5d  lea     rbx, [rdx-18h]
0x180020b61  mov     r8d, [rbx+8]
0x180020b65  mov     rcx, rsi
0x180020b68  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180020b6d  nop
0x180020b6e  mov     rcx, rbx; this
0x180020b71  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020b76  mov     r8d, r14d
0x180020b79  lea     rdx, aWordTitle; "<Word title=\""
0x180020b80  mov     rcx, rdi
0x180020b83  call    ?Find@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBAHPEBGH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Find(ushort const *,int)
0x180020b88  cmp     eax, 0FFFFFFFFh
0x180020b8b  mov     ebx, eax
0x180020b8d  mov     r8d, r14d
0x180020b90  mov     rcx, rdi
0x180020b93  jnz     loc_180020A70
0x180020b99  mov     rax, [rdi]
0x180020b9c  mov     r9d, [rax-10h]
0x180020ba0  sub     r9d, r14d
0x180020ba3  lea     rdx, [rbp+arg_0]
0x180020ba7  call    ?Mid@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEBA?AV12@HH@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::Mid(int,int)
0x180020bac  nop
0x180020bad  mov     rbx, [rbp+arg_0]
0x180020bb1  mov     r8d, [rbx-10h]
0x180020bb5  mov     rdx, rbx
0x180020bb8  mov     rcx, rsi
0x180020bbb  call    ?Append@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBGH@Z; ATL::CSimpleStringT<ushort,0>::Append(ushort const *,int)
0x180020bc0  nop
0x180020bc1  lea     rcx, [rbx-18h]; this
0x180020bc5  call    ?Release@CStringData@ATL@@QEAAXXZ; ATL::CStringData::Release(void)
0x180020bca  mov     rbx, [rsp+20h+arg_10]
0x180020bcf  mov     rsi, [rsp+20h+arg_18]
0x180020bd4  add     rsp, 20h
0x180020bd8  pop     r14
0x180020bda  pop     rdi
0x180020bdb  pop     rbp
0x180020bdc  retn
```
