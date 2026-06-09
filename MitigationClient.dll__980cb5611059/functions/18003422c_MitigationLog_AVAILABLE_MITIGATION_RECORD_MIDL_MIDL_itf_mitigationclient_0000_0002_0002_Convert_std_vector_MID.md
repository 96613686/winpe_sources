# MitigationLog<_AVAILABLE_MITIGATION_RECORD,__MIDL___MIDL_itf_mitigationclient_0000_0002_0002>::Convert(std::vector<__MIDL___MIDL_itf_mitigationclient_0000_0002_0002,std::allocator<__MIDL___MIDL_itf_mitigationclient_0000_0002_0002>> const &,__MIDL___MIDL_itf_mitigationclient_0000_0002_0002 * *)

- ea: `0x18003422c`
- end: `0x180034385`
- name: `?Convert@?$MitigationLog@U_AVAILABLE_MITIGATION_RECORD@@U__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@@@SAXAEBV?$vector@U__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@V?$allocator@U__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@@std@@@std@@PEAPEAU__MIDL___MIDL_itf_mitigationclient_0000_0002_0002@@@Z`
- size: `345`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800344e0`

## callees

- `0x18000b2b4`
- `0x180013828`
- `0x18003422c`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034298`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180034298`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034339`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003434f`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034323`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x180034339`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x18003434f`

## string_xrefs

- `0x180034277`: `onecore\internal\sdk\inc\wil\opensource\wil\resource.h`

## pseudocode

```c
unsigned __int64 __fastcall MitigationLog<_AVAILABLE_MITIGATION_RECORD,__MIDL___MIDL_itf_mitigationclient_0000_0002_0002>::Convert(
        __int64 *a1,
        _QWORD *a2,
        __int64 a3,
        const char *a4)
{
  unsigned __int64 result; // rax
  unsigned __int64 v7; // rax
  __int64 v8; // r14
  char *v9; // rax
  char *v10; // rbx
  char *v11; // rbp
  char *i; // rdi
  __int64 v13; // rcx
  unsigned __int64 j; // r14
  char *v15; // rdx
  __int128 v16; // xmm1
  __int128 v17; // xmm2
  __int128 v18; // xmm3
  __int64 v19; // xmm4_8
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]

  result = a1[1];
  if ( *a1 != result )
  {
    v7 = 0x8E38E38E38E38E39uLL * ((__int64)(result - *a1) >> 3);
    if ( v7 > 0x38E38E38E38E38ELL )
      wil::details::in1diag3::_FailFast_Unexpected(
        retaddr,
        (void *)0x1802,
        (unsigned int)"onecore\\internal\\sdk\\inc\\wil\\opensource\\wil\\resource.h",
        a4);
    v8 = 72 * v7;
    v9 = (char *)CoTaskMemAlloc(72 * v7);
    v10 = v9;
    if ( v9 )
    {
      v11 = &v9[v8];
      for ( i = v9; i != v11; i += 72 )
        memset_0(i, 0, 0x48u);
    }
    v13 = *a1;
    result = 0x8E38E38E38E38E39uLL * ((a1[1] - *a1) >> 3);
    if ( result )
    {
      for ( j = 0; j < result; ++j )
      {
        v15 = &v10[72 * j];
        v16 = *(_OWORD *)(v13 + 72 * j + 16);
        v17 = *(_OWORD *)(v13 + 72 * j + 32);
        v18 = *(_OWORD *)(v13 + 72 * j + 48);
        v19 = *(_QWORD *)(v13 + 72 * j + 64);
        *(_OWORD *)v15 = *(_OWORD *)(v13 + 72 * j);
        *((_OWORD *)v15 + 1) = v16;
        *((_OWORD *)v15 + 2) = v17;
        *((_OWORD *)v15 + 3) = v18;
        *((_QWORD *)v15 + 8) = v19;
        WindowsDuplicateString(*(HSTRING *)(*a1 + 72 * j), (HSTRING *)v15);
        WindowsDuplicateString(*(HSTRING *)(*a1 + 72 * j + 8), (HSTRING *)&v10[72 * j + 8]);
        WindowsDuplicateString(*(HSTRING *)(*a1 + 72 * j + 32), (HSTRING *)&v10[72 * j + 32]);
        v13 = *a1;
        result = 0x8E38E38E38E38E39uLL * ((a1[1] - *a1) >> 3);
      }
    }
    *a2 = v10;
  }
  return result;
}

```

## disassembly

```asm
0x18003422c  push    rbx
0x18003422e  push    rbp
0x18003422f  push    rsi
0x180034230  push    rdi
0x180034231  push    r12
0x180034233  push    r14
0x180034235  push    r15
0x180034237  sub     rsp, 20h
0x18003423b  mov     rax, [rcx+8]
0x18003423f  mov     r15, rdx
0x180034242  mov     rsi, rcx
0x180034245  cmp     [rcx], rax
0x180034248  jz      loc_180034376
0x18003424e  sub     rax, [rcx]
0x180034251  mov     r12, 8E38E38E38E38E39h
0x18003425b  sar     rax, 3
0x18003425f  mov     rcx, 38E38E38E38E38Eh
0x180034269  imul    rax, r12
0x18003426d  cmp     rax, rcx
0x180034270  jbe     short loc_180034289
0x180034272  mov     rcx, [rsp+58h]; this
0x180034277  lea     r8, aOnecoreInterna_0; "onecore\\internal\\sdk\\inc\\wil\\opens"...
0x18003427e  mov     edx, 1802h; void *
0x180034283  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x180034289  lea     rax, [rax+rax*8]
0x18003428d  lea     r14, ds:0[rax*8]
0x180034295  mov     rcx, r14; cb
0x180034298  call    cs:__imp_CoTaskMemAlloc
0x18003429e  mov     rbx, rax
0x1800342a1  test    rax, rax
0x1800342a4  jz      short loc_1800342C9
0x1800342a6  lea     rbp, [r14+rax]
0x1800342aa  mov     rdi, rax
0x1800342ad  cmp     rax, rbp
0x1800342b0  jz      short loc_1800342C9
0x1800342b2  xor     edx, edx; Val
0x1800342b4  mov     rcx, rdi; void *
0x1800342b7  lea     r8d, [rdx+48h]; Size
0x1800342bb  call    memset_0
0x1800342c0  add     rdi, 48h ; 'H'
0x1800342c4  cmp     rdi, rbp
0x1800342c7  jnz     short loc_1800342B2
0x1800342c9  mov     rcx, [rsi]
0x1800342cc  mov     rax, [rsi+8]
0x1800342d0  sub     rax, rcx
0x1800342d3  sar     rax, 3
0x1800342d7  imul    rax, r12
0x1800342db  test    rax, rax
0x1800342de  jz      loc_180034373
0x1800342e4  xor     r14d, r14d
0x1800342e7  lea     rdi, [r14+r14*8]
0x1800342eb  movups  xmm0, xmmword ptr [rcx+rdi*8]
0x1800342ef  lea     rdx, [rbx+rdi*8]; newString
0x1800342f3  movups  xmm1, xmmword ptr [rcx+rdi*8+10h]
0x1800342f8  movups  xmm2, xmmword ptr [rcx+rdi*8+20h]
0x1800342fd  movups  xmm3, xmmword ptr [rcx+rdi*8+30h]
0x180034302  movsd   xmm4, qword ptr [rcx+rdi*8+40h]
0x180034308  movups  xmmword ptr [rdx], xmm0
0x18003430b  movups  xmmword ptr [rdx+10h], xmm1
0x18003430f  movups  xmmword ptr [rdx+20h], xmm2
0x180034313  movups  xmmword ptr [rdx+30h], xmm3
0x180034317  movsd   qword ptr [rdx+40h], xmm4
0x18003431c  mov     rcx, [rsi]
0x18003431f  mov     rcx, [rcx+rdi*8]; string
0x180034323  call    cs:__imp_WindowsDuplicateString
0x180034329  mov     rcx, [rsi]
0x18003432c  lea     rdx, [rbx+8]
0x180034330  lea     rdx, [rdx+rdi*8]; newString
0x180034334  mov     rcx, [rcx+rdi*8+8]; string
0x180034339  call    cs:__imp_WindowsDuplicateString
0x18003433f  mov     rcx, [rsi]
0x180034342  lea     rdx, [rbx+20h]
0x180034346  lea     rdx, [rdx+rdi*8]; newString
0x18003434a  mov     rcx, [rcx+rdi*8+20h]; string
0x18003434f  call    cs:__imp_WindowsDuplicateString
0x180034355  mov     rcx, [rsi]
0x180034358  inc     r14
0x18003435b  mov     rax, [rsi+8]
0x18003435f  sub     rax, rcx
0x180034362  sar     rax, 3
0x180034366  imul    rax, r12
0x18003436a  cmp     r14, rax
0x18003436d  jb      loc_1800342E7
0x180034373  mov     [r15], rbx
0x180034376  add     rsp, 20h
0x18003437a  pop     r15
0x18003437c  pop     r14
0x18003437e  pop     r12
0x180034380  pop     rdi
0x180034381  pop     rsi
0x180034382  pop     rbp
0x180034383  pop     rbx
0x180034384  retn
```
