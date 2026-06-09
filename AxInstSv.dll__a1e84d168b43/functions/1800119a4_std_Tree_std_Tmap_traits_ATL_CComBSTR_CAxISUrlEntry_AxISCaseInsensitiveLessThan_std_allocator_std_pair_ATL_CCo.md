# std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Emplace<std::pair<ATL::CComBSTR,CAxISUrlEntry *>>(std::pair<ATL::CComBSTR,CAxISUrlEntry *> &&)

- ea: `0x1800119a4`
- end: `0x180011aa9`
- name: `??$_Emplace@U?$pair@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@IEAA?AU?$pair@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@_N@1@$$QEAU?$pair@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@@1@@Z`
- size: `261`
- prototype: ``
- caller_count: `1`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180011d1c`

## callees

- `0x18000177c`
- `0x180003208`
- `0x180004d88`
- `0x1800119a4`
- `0x180011b08`
- `0x180011bb8`
- `0x180011c38`
- `0x180011e24`

## import_xrefs

- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011a00`
- `msvcp_win!?_Xlength_error@std@@YAXPEBD@Z` at `0x180011a00`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Emplace<std::pair<ATL::CComBSTR,CAxISUrlEntry *>>(
        __int64 *a1,
        __int64 a2,
        ATL::CComBSTR *a3)
{
  __int64 v6; // rax
  __int128 v7; // xmm6
  __int64 v8; // rdi
  __int64 v9; // rcx
  __int64 v10; // r14
  _QWORD *v11; // rdi
  unsigned __int16 *v12; // rax
  _OWORD v14[2]; // [rsp+20h] [rbp-58h] BYREF

  v6 = std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Find_lower_bound<ATL::CComBSTR>(
         a1,
         v14);
  v7 = *(_OWORD *)v6;
  v8 = *(_QWORD *)(v6 + 16);
  if ( (unsigned __int8)std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Lower_bound_duplicate<ATL::CComBSTR>(
                          v9,
                          v8,
                          a3) )
  {
    *(_QWORD *)a2 = v8;
    *(_BYTE *)(a2 + 8) = 0;
  }
  else
  {
    if ( a1[1] == 0x555555555555555LL )
      std::_Xlength_error("map/set too long");
    v10 = *a1;
    v14[0] = (unsigned __int64)a1;
    v11 = operator new(0x30u);
    *((_QWORD *)&v14[0] + 1) = v11;
    v12 = ATL::CComBSTR::Copy(a3);
    v11[4] = v12;
    if ( *(_QWORD *)a3 && !v12 )
      ATL::AtlThrowImpl(-2147024882);
    v11[5] = *((_QWORD *)a3 + 1);
    *v11 = v10;
    v11[1] = v10;
    v11[2] = v10;
    *((_WORD *)v11 + 12) = 0;
    *((_QWORD *)&v14[0] + 1) = 0;
    std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(v14);
    v14[0] = v7;
    *(_QWORD *)a2 = std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Insert_node(
                      a1,
                      v14,
                      v11);
    *(_BYTE *)(a2 + 8) = 1;
  }
  return a2;
}

```

## disassembly

```asm
0x1800119a4  push    rbx
0x1800119a6  push    rbp
0x1800119a7  push    rsi
0x1800119a8  push    rdi
0x1800119a9  push    r14
0x1800119ab  sub     rsp, 50h
0x1800119af  movaps  [rsp+78h+var_38], xmm6
0x1800119b4  mov     rbp, r8
0x1800119b7  mov     rbx, rdx
0x1800119ba  mov     rsi, rcx
0x1800119bd  lea     rdx, [rsp+78h+var_58]
0x1800119c2  call    ??$_Find_lower_bound@VCComBSTR@ATL@@@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@IEBA?AU?$_Tree_find_result@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@1@AEBVCComBSTR@ATL@@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Find_lower_bound<ATL::CComBSTR>(ATL::CComBSTR const &)
0x1800119c7  movups  xmm6, xmmword ptr [rax]
0x1800119ca  mov     rdi, [rax+10h]
0x1800119ce  mov     r8, rbp
0x1800119d1  mov     rdx, rdi
0x1800119d4  call    ??$_Lower_bound_duplicate@VCComBSTR@ATL@@@?$_Tree@V?$_Tmap_traits@VCComBSTR@ATL@@PEAVCAxISUrlEntry@@UAxISCaseInsensitiveLessThan@@V?$allocator@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@$0A@@std@@@std@@IEBA_NQEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@1@AEBVCComBSTR@ATL@@@Z; std::_Tree<std::_Tmap_traits<ATL::CComBSTR,CAxISUrlEntry *,AxISCaseInsensitiveLessThan,std::allocator<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>,0>>::_Lower_bound_duplicate<ATL::CComBSTR>(std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> * const,ATL::CComBSTR const &)
0x1800119d9  test    al, al
0x1800119db  jz      short loc_1800119E9
0x1800119dd  mov     [rbx], rdi
0x1800119e0  mov     byte ptr [rbx+8], 0
0x1800119e4  jmp     loc_180011A96
0x1800119e9  mov     rax, 555555555555555h
0x1800119f3  cmp     [rsi+8], rax
0x1800119f7  jnz     short loc_180011A07
0x1800119f9  lea     rcx, aMapSetTooLong; "map/set too long"
0x180011a00  call    cs:__imp_?_Xlength_error@std@@YAXPEBD@Z; std::_Xlength_error(char const *)
0x180011a07  mov     r14, [rsi]
0x180011a0a  mov     qword ptr [rsp+78h+var_58], rsi
0x180011a0f  mov     qword ptr [rsp+78h+var_58+8], 0
0x180011a18  mov     ecx, 30h ; '0'; Size
0x180011a1d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180011a22  mov     rdi, rax
0x180011a25  mov     qword ptr [rsp+78h+var_58+8], rax
0x180011a2a  mov     rcx, rbp; this
0x180011a2d  call    ?Copy@CComBSTR@ATL@@QEBAPEAGXZ; ATL::CComBSTR::Copy(void)
0x180011a32  mov     [rdi+20h], rax
0x180011a36  cmp     qword ptr [rbp+0], 0
0x180011a3b  jz      short loc_180011A4D
0x180011a3d  test    rax, rax
0x180011a40  jnz     short loc_180011A4D
0x180011a42  mov     ecx, 8007000Eh; int
0x180011a47  call    ?AtlThrowImpl@ATL@@YAXJ@Z; ATL::AtlThrowImpl(long)
0x180011a4d  mov     rax, [rbp+8]
0x180011a51  mov     [rdi+28h], rax
0x180011a55  mov     [rdi], r14
0x180011a58  mov     [rdi+8], r14
0x180011a5c  mov     [rdi+10h], r14
0x180011a60  mov     word ptr [rdi+18h], 0
0x180011a66  mov     qword ptr [rsp+78h+var_58+8], 0
0x180011a6f  lea     rcx, [rsp+78h+var_58]
0x180011a74  call    ??1?$_Tree_temp_node@V?$allocator@U?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@std@@@std@@QEAA@XZ; std::_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>::~_Tree_temp_node<std::allocator<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *>>>(void)
0x180011a79  movdqu  [rsp+78h+var_58], xmm6
0x180011a7f  mov     r8, rdi
0x180011a82  lea     rdx, [rsp+78h+var_58]
0x180011a87  mov     rcx, rsi
0x180011a8a  call    ?_Insert_node@?$_Tree_val@U?$_Tree_simple_types@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@@std@@@std@@QEAAPEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@2@U?$_Tree_id@PEAU?$_Tree_node@U?$pair@$$CBVCComBSTR@ATL@@PEAVCAxISUrlEntry@@@std@@PEAX@std@@@2@QEAU32@@Z; std::_Tree_val<std::_Tree_simple_types<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>>>::_Insert_node(std::_Tree_id<std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> *>,std::_Tree_node<std::pair<ATL::CComBSTR const,CAxISUrlEntry *>,void *> * const)
0x180011a8f  mov     [rbx], rax
0x180011a92  mov     byte ptr [rbx+8], 1
0x180011a96  mov     rax, rbx
0x180011a99  movaps  xmm6, [rsp+78h+var_38]
0x180011a9e  add     rsp, 50h
0x180011aa2  pop     r14
0x180011aa4  pop     rdi
0x180011aa5  pop     rsi
0x180011aa6  pop     rbp
0x180011aa7  pop     rbx
0x180011aa8  retn
```
