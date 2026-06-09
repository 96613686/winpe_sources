# MitigationHistory::CopyFromInternalToExternalLog(std::vector<MitigationHistoryResultInternal,std::allocator<MitigationHistoryResultInternal>>,__MIDL___MIDL_itf_mitigationclient_0000_0002_0003 * *,ulong *)

- ea: `0x180052c18`
- end: `0x180052e7e`
- name: `?CopyFromInternalToExternalLog@MitigationHistory@@QEAAJV?$vector@UMitigationHistoryResultInternal@@V?$allocator@UMitigationHistoryResultInternal@@@std@@@std@@PEAPEAU__MIDL___MIDL_itf_mitigationclient_0000_0002_0003@@PEAK@Z`
- size: `614`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `service_task, broker_com_uri`

## callers

- `0x180052e84`

## callees

- `0x18000b2b4`
- `0x18001208c`
- `0x180013828`
- `0x180013a7c`
- `0x180019f68`
- `0x180052c18`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052c7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180052c7c`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052e10`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180052e10`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180052d5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180052d89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180052db2`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180052d5f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180052d89`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x180052db2`

## string_xrefs

- `0x180052c5f`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
__int64 __fastcall MitigationHistory::CopyFromInternalToExternalLog(__int64 a1, _QWORD *a2, _QWORD *a3, char *a4)
{
  SIZE_T v7; // r14
  char *v8; // rax
  char *v9; // rbx
  char *v10; // rbp
  char *i; // rsi
  unsigned __int64 j; // r14
  __int64 v13; // rsi
  char *v14; // r15
  __int16 v15; // dx
  const WCHAR *v16; // rax
  __int64 v17; // rdx
  HRESULT String; // ebp
  const WCHAR *v19; // rax
  __int64 v20; // rdx
  const WCHAR *v21; // rax
  __int64 v22; // rdx
  HRESULT v23; // eax
  unsigned int v24; // esi
  __int64 v25; // rdx
  int v27; // [rsp+20h] [rbp-48h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  if ( 0x86BCA1AF286BCA1BuLL * ((__int64)(a2[1] - *a2) >> 3) > 0x333333333333333LL )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x1802,
      (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
      a4);
  v7 = 0x1AF286BCA1AF2870LL * ((__int64)(a2[1] - *a2) >> 3);
  v8 = (char *)CoTaskMemAlloc(v7);
  v9 = v8;
  if ( v8 )
  {
    v10 = &v8[v7];
    for ( i = v8; i != v10; i += 80 )
      memset_0(i, 0, 0x50u);
    for ( j = 0; j < 0x86BCA1AF286BCA1BuLL * ((__int64)(a2[1] - *a2) >> 3); ++j )
    {
      v13 = 152 * j;
      v14 = &v9[80 * j];
      *((_OWORD *)v14 + 1) = *(_OWORD *)(*a2 + 152 * j);
      v15 = *(_WORD *)(152 * j + *a2 + 20);
      *((_DWORD *)v14 + 8) = *(_DWORD *)(152 * j + *a2 + 16);
      *((_WORD *)v14 + 18) = v15;
      *((_DWORD *)v14 + 12) = *(_DWORD *)(152 * j + *a2 + 24);
      *((_DWORD *)v14 + 13) = *(_DWORD *)(152 * j + *a2 + 28);
      *((_DWORD *)v14 + 14) = *(_DWORD *)(152 * j + *a2 + 32);
      *(_QWORD *)(v14 + 60) = *(_QWORD *)(152 * j + *a2 + 36);
      *((_DWORD *)v14 + 17) = *(_DWORD *)(152 * j + *a2 + 44);
      *((_DWORD *)v14 + 18) = *(_DWORD *)(152 * j + *a2 + 144);
      v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(152 * j + *a2 + 48LL);
      String = WindowsCreateString(v16, *(_DWORD *)(152 * j + v17 + 64), (HSTRING *)v14);
      if ( String < 0 )
      {
        v25 = 334;
        goto LABEL_15;
      }
      v19 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13 + *a2 + 80LL);
      String = WindowsCreateString(v19, *(_DWORD *)(v13 + v20 + 96), (HSTRING *)v14 + 1);
      if ( String < 0 )
      {
        v25 = 335;
LABEL_15:
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)v25,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationlog\\mitigationhistory.cpp",
          (const char *)(unsigned int)String,
          v27);
        v24 = String;
        goto LABEL_16;
      }
      v21 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(v13 + *a2 + 112LL);
      v23 = WindowsCreateString(v21, *(_DWORD *)(v13 + v22 + 128), (HSTRING *)v14 + 5);
      v24 = v23;
      if ( v23 < 0 )
      {
        wil::details::in1diag3::Return_Hr(
          retaddr,
          (void *)0x150,
          (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationlog\\mitigationhistory.cpp",
          (const char *)(unsigned int)v23,
          v27);
LABEL_16:
        CoTaskMemFree(v9);
        std::vector<MitigationHistoryResultInternal>::_Tidy(a2);
        return v24;
      }
    }
    *a3 = v9;
    *(_DWORD *)a4 = 678152731 * ((__int64)(a2[1] - *a2) >> 3);
    std::vector<MitigationHistoryResultInternal>::_Tidy(a2);
    return 0;
  }
  else
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x142,
      (unsigned int)"onecore\\base\\diagnosis\\mitigation\\client\\libs\\mitigationlog\\mitigationhistory.cpp",
      (const char *)0x8007000ELL,
      v27);
    std::vector<MitigationHistoryResultInternal>::_Tidy(a2);
    return 2147942414LL;
  }
}

```

## disassembly

```asm
0x180052c18  push    rbx
0x180052c1a  push    rbp
0x180052c1b  push    rsi
0x180052c1c  push    rdi
0x180052c1d  push    r12
0x180052c1f  push    r13
0x180052c21  push    r14
0x180052c23  push    r15
0x180052c25  sub     rsp, 28h
0x180052c29  mov     rax, [rdx+8]
0x180052c2d  mov     r15, 86BCA1AF286BCA1Bh
0x180052c37  sub     rax, [rdx]
0x180052c3a  mov     rcx, 333333333333333h
0x180052c44  sar     rax, 3
0x180052c48  mov     r12, r9
0x180052c4b  imul    rax, r15
0x180052c4f  mov     r13, r8
0x180052c52  mov     rdi, rdx
0x180052c55  cmp     rax, rcx
0x180052c58  jbe     short loc_180052C71
0x180052c5a  mov     rcx, [rsp+68h]; this
0x180052c5f  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x180052c66  mov     edx, 1802h; void *
0x180052c6b  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180052c71  lea     r14, [rax+rax*4]
0x180052c75  shl     r14, 4
0x180052c79  mov     rcx, r14; cb
0x180052c7c  call    cs:__imp_CoTaskMemAlloc
0x180052c82  mov     rbx, rax
0x180052c85  test    rax, rax
0x180052c88  jz      loc_180052E45
0x180052c8e  lea     rbp, [r14+rax]
0x180052c92  mov     rsi, rax
0x180052c95  cmp     rax, rbp
0x180052c98  jz      short loc_180052CB1
0x180052c9a  xor     edx, edx; Val
0x180052c9c  mov     rcx, rsi; void *
0x180052c9f  lea     r8d, [rdx+50h]; Size
0x180052ca3  call    memset_0
0x180052ca8  add     rsi, 50h ; 'P'
0x180052cac  cmp     rsi, rbp
0x180052caf  jnz     short loc_180052C9A
0x180052cb1  xor     r14d, r14d
0x180052cb4  mov     rcx, [rdi]
0x180052cb7  mov     rax, [rdi+8]
0x180052cbb  sub     rax, rcx
0x180052cbe  sar     rax, 3
0x180052cc2  imul    rax, r15
0x180052cc6  cmp     r14, rax
0x180052cc9  jnb     loc_180052E22
0x180052ccf  imul    rsi, r14, 98h
0x180052cd6  lea     r15, [r14+r14*4]
0x180052cda  shl     r15, 4
0x180052cde  add     r15, rbx
0x180052ce1  movups  xmm0, xmmword ptr [rcx+rsi]
0x180052ce5  movdqu  xmmword ptr [r15+10h], xmm0
0x180052ceb  mov     rax, [rdi]
0x180052cee  mov     ecx, [rsi+rax+10h]
0x180052cf2  movzx   edx, word ptr [rsi+rax+14h]
0x180052cf7  mov     [r15+20h], ecx
0x180052cfb  mov     [r15+24h], dx
0x180052d00  mov     rax, [rdi]
0x180052d03  mov     ecx, [rsi+rax+18h]
0x180052d07  mov     [r15+30h], ecx
0x180052d0b  mov     rax, [rdi]
0x180052d0e  mov     ecx, [rsi+rax+1Ch]
0x180052d12  mov     [r15+34h], ecx
0x180052d16  mov     rax, [rdi]
0x180052d19  mov     ecx, [rsi+rax+20h]
0x180052d1d  mov     [r15+38h], ecx
0x180052d21  mov     rax, [rdi]
0x180052d24  mov     rcx, [rsi+rax+24h]
0x180052d29  mov     [r15+3Ch], rcx
0x180052d2d  mov     rax, [rdi]
0x180052d30  mov     ecx, [rsi+rax+2Ch]
0x180052d34  mov     [r15+44h], ecx
0x180052d38  mov     rax, [rdi]
0x180052d3b  mov     ecx, [rsi+rax+90h]
0x180052d42  mov     [r15+48h], ecx
0x180052d46  mov     rdx, [rdi]
0x180052d49  lea     rcx, [rdx+30h]
0x180052d4d  add     rcx, rsi
0x180052d50  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052d55  mov     edx, [rsi+rdx+40h]; length
0x180052d59  mov     rcx, rax; sourceString
0x180052d5c  mov     r8, r15; string
0x180052d5f  call    cs:__imp_WindowsCreateString
0x180052d65  mov     ebp, eax
0x180052d67  test    eax, eax
0x180052d69  js      loc_180052DF2
0x180052d6f  mov     rdx, [rdi]
0x180052d72  lea     rcx, [rdx+50h]
0x180052d76  add     rcx, rsi
0x180052d79  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052d7e  mov     edx, [rsi+rdx+60h]; length
0x180052d82  lea     r8, [r15+8]; string
0x180052d86  mov     rcx, rax; sourceString
0x180052d89  call    cs:__imp_WindowsCreateString
0x180052d8f  mov     ebp, eax
0x180052d91  test    eax, eax
0x180052d93  js      short loc_180052DEB
0x180052d95  mov     rdx, [rdi]
0x180052d98  lea     rcx, [rdx+70h]
0x180052d9c  add     rcx, rsi
0x180052d9f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x180052da4  mov     edx, [rsi+rdx+80h]; length
0x180052dab  lea     r8, [r15+28h]; string
0x180052daf  mov     rcx, rax; sourceString
0x180052db2  call    cs:__imp_WindowsCreateString
0x180052db8  mov     esi, eax
0x180052dba  test    eax, eax
0x180052dbc  js      short loc_180052DD0
0x180052dbe  inc     r14
0x180052dc1  mov     r15, 86BCA1AF286BCA1Bh
0x180052dcb  jmp     loc_180052CB4
0x180052dd0  mov     rcx, [rsp+68h]; this
0x180052dd5  lea     r8, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180052ddc  mov     r9d, eax; char *
0x180052ddf  mov     edx, 150h; void *
0x180052de4  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052de9  jmp     short loc_180052E0D
0x180052deb  mov     edx, 14Fh
0x180052df0  jmp     short loc_180052DF7
0x180052df2  mov     edx, 14Eh; void *
0x180052df7  mov     rcx, [rsp+68h]; this
0x180052dfc  lea     r8, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180052e03  mov     r9d, ebp; char *
0x180052e06  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052e0b  mov     esi, ebp
0x180052e0d  mov     rcx, rbx; pv
0x180052e10  call    cs:__imp_CoTaskMemFree
0x180052e16  mov     rcx, rdi
0x180052e19  call    ?_Tidy@?$vector@UMitigationHistoryResultInternal@@V?$allocator@UMitigationHistoryResultInternal@@@std@@@std@@AEAAXXZ; std::vector<MitigationHistoryResultInternal>::_Tidy(void)
0x180052e1e  mov     eax, esi
0x180052e20  jmp     short loc_180052E6D
0x180052e22  mov     [r13+0], rbx
0x180052e26  mov     rcx, rdi
0x180052e29  mov     rax, [rdi+8]
0x180052e2d  sub     rax, [rdi]
0x180052e30  sar     rax, 3
0x180052e34  imul    rax, r15
0x180052e38  mov     [r12], eax
0x180052e3c  call    ?_Tidy@?$vector@UMitigationHistoryResultInternal@@V?$allocator@UMitigationHistoryResultInternal@@@std@@@std@@AEAAXXZ; std::vector<MitigationHistoryResultInternal>::_Tidy(void)
0x180052e41  xor     eax, eax
0x180052e43  jmp     short loc_180052E6D
0x180052e45  mov     rcx, [rsp+68h]; this
0x180052e4a  lea     r8, aOnecoreBaseDia_3; "onecore\\base\\diagnosis\\mitigation\\c"...
0x180052e51  mov     ebx, 8007000Eh
0x180052e56  mov     edx, 142h; void *
0x180052e5b  mov     r9d, ebx; char *
0x180052e5e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180052e63  mov     rcx, rdi
0x180052e66  call    ?_Tidy@?$vector@UMitigationHistoryResultInternal@@V?$allocator@UMitigationHistoryResultInternal@@@std@@@std@@AEAAXXZ; std::vector<MitigationHistoryResultInternal>::_Tidy(void)
0x180052e6b  mov     eax, ebx
0x180052e6d  add     rsp, 28h
0x180052e71  pop     r15
0x180052e73  pop     r14
0x180052e75  pop     r13
0x180052e77  pop     r12
0x180052e79  pop     rdi
0x180052e7a  pop     rsi
0x180052e7b  pop     rbp
0x180052e7c  pop     rbx
0x180052e7d  retn
```
