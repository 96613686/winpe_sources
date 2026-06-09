# Compress(ushort const *,unsigned __int64,ushort * *)

- ea: `0x180199264`
- end: `0x1801994de`
- name: `?Compress@@YAJPEBG_KPEAPEAG@Z`
- size: `634`
- prototype: `__int64 __fastcall(const unsigned __int16 *, unsigned __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `11`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18019b928`

## callees

- `0x18001adb4`
- `0x1800607dc`
- `0x180060884`
- `0x1800aed10`
- `0x1800af918`
- `0x180199264`
- `0x1801994e4`
- `0x18019a5e0`
- `0x18019bc9c`
- `0x18019bce0`
- `0x18019cff0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019942d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199483`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18019942d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199446`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180199483`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801992b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019939a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x1801992b1`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18019939a`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Compress(const unsigned __int16 *a1, unsigned __int64 a2, unsigned __int16 **a3)
{
  unsigned int *v6; // rax
  unsigned int *v7; // rdi
  unsigned __int64 i; // rdx
  unsigned int v9; // edx
  __int64 v10; // r12
  unsigned __int64 v11; // r15
  int v12; // r14d
  _WORD *v13; // rbx
  int v14; // edx
  unsigned __int64 v15; // r9
  unsigned __int64 j; // r8
  __int64 v17; // r10
  unsigned __int16 *v18; // rax
  __int64 v19; // rdx
  __int64 v21; // rdx
  unsigned int v22[4]; // [rsp+20h] [rbp-E0h] BYREF
  __int128 v23; // [rsp+30h] [rbp-D0h] BYREF
  __int64 v24; // [rsp+40h] [rbp-C0h]
  unsigned int v25; // [rsp+48h] [rbp-B8h]
  int v26; // [rsp+4Ch] [rbp-B4h]
  unsigned __int64 v27; // [rsp+50h] [rbp-B0h]
  _BYTE v28[10248]; // [rsp+58h] [rbp-A8h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+28A8h] [rbp+27A8h]

  *a3 = 0;
  v6 = (unsigned int *)CoTaskMemAlloc(4 * a2);
  v7 = v6;
  if ( !v6 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x140,
      (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
      (const char *)0x8007000ELL,
      v22[0]);
    return 2147942414LL;
  }
  for ( i = 0; i < a2; ++i )
    v6[i] = a1[i];
  v23 = 0;
  v24 = 0;
  inverted::vector_nothrow<unsigned __int64>::clear(&v23, i);
  inverted::vector_nothrow<unsigned __int64>::push_back(&v23, qword_18021B040);
  v26 = 0;
  v27 = 0xFBFFFFFFFFFFFFFFuLL;
  memset_0(v28, 0, sizeof(v28));
  v25 = 0;
  v22[0] = 0;
  inverted::CSimple256Compressor::Compress((inverted::CSimple256Compressor *)&v23, v7, a2, v22);
  inverted::CSimple256Compressor::CompressRemainder((inverted::CSimple256Compressor *)&v23, &v7[v22[0]], a2 - v22[0]);
  v9 = v24;
  v10 = v23;
  *(_QWORD *)v23 = v25 | (unsigned __int64)(v24 << 32);
  v11 = v9;
  v12 = 4 * v9;
  v13 = CoTaskMemAlloc(2LL * (int)(4 * v9) + 2);
  if ( !v13 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x150,
      (unsigned int)"onecore\\shell\\lib\\userchoicehelpers\\userchoicecore.cpp",
      (const char *)0x8007000ELL,
      v22[0]);
    inverted::vector_nothrow<unsigned __int64>::clear(&v23, v21);
    CoTaskMemFree(v7);
    return 2147942414LL;
  }
  v14 = 0;
  v15 = 0;
  if ( (_DWORD)v11 )
  {
    do
    {
      if ( v14 >= v12 )
        break;
      for ( j = 0; j < 8; j += 2LL )
      {
        if ( v14 >= v12 )
          break;
        v17 = *(_QWORD *)(v10 + 8 * v15) >> (8 * (unsigned __int8)j);
        if ( (_WORD)v17 )
          v13[v14++] = v17;
      }
      ++v15;
    }
    while ( v15 < v11 );
  }
  v13[v14] = 0;
  wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>>>(
    v22,
    v13,
    -1,
    v15);
  v18 = *(unsigned __int16 **)v22;
  *(_QWORD *)v22 = 0;
  *a3 = v18;
  wil::details::unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<unsigned short *,void (*)(void *),&void CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,unsigned short *,unsigned short *,0,std::nullptr_t>>(v22);
  CoTaskMemFree(v13);
  inverted::vector_nothrow<unsigned __int64>::clear(&v23, v19);
  CoTaskMemFree(v7);
  return 0;
}

```

## disassembly

```asm
0x180199264  mov     [rsp-8+arg_0], rbx
0x180199269  push    rbp
0x18019926a  push    rsi
0x18019926b  push    rdi
0x18019926c  push    r12
0x18019926e  push    r13
0x180199270  push    r14
0x180199272  push    r15
0x180199274  lea     rbp, [rsp-2770h]
0x18019927c  mov     eax, 2870h
0x180199281  call    _alloca_probe
0x180199286  sub     rsp, rax
0x180199289  mov     rax, cs:__security_cookie
0x180199290  xor     rax, rsp
0x180199293  mov     [rbp+27A0h+var_40], rax
0x18019929a  mov     rsi, r8
0x18019929d  mov     rbx, rdx
0x1801992a0  mov     r14, rcx
0x1801992a3  xor     r13d, r13d
0x1801992a6  mov     [r8], r13
0x1801992a9  lea     rcx, ds:0[rdx*4]; cb
0x1801992b1  call    cs:__imp_CoTaskMemAlloc
0x1801992b8  nop     dword ptr [rax+rax+00h]
0x1801992bd  mov     rdi, rax
0x1801992c0  test    rax, rax
0x1801992c3  jz      loc_180199491
0x1801992c9  mov     edx, r13d
0x1801992cc  test    rbx, rbx
0x1801992cf  jz      short loc_1801992E1
0x1801992d1  movzx   ecx, word ptr [r14+rdx*2]
0x1801992d6  mov     [rax+rdx*4], ecx
0x1801992d9  inc     rdx
0x1801992dc  cmp     rdx, rbx
0x1801992df  jb      short loc_1801992D1
0x1801992e1  xorps   xmm0, xmm0
0x1801992e4  movdqa  [rsp+28A0h+var_2870], xmm0
0x1801992ea  mov     [rsp+28A0h+var_2860], r13
0x1801992ef  lea     rcx, [rsp+28A0h+var_2870]
0x1801992f4  call    ?clear@?$vector_nothrow@_K@inverted@@QEAAXXZ; inverted::vector_nothrow<unsigned __int64>::clear(void)
0x1801992f9  lea     rdx, qword_18021B040
0x180199300  lea     rcx, [rsp+28A0h+var_2870]
0x180199305  call    ?push_back@?$vector_nothrow@_K@inverted@@QEAAXAEB_K@Z; inverted::vector_nothrow<unsigned __int64>::push_back(unsigned __int64 const &)
0x18019930a  mov     [rsp+28A0h+var_2854], r13d
0x18019930f  mov     rax, 0FBFFFFFFFFFFFFFFh
0x180199319  mov     [rsp+28A0h+var_2850], rax
0x18019931e  xor     edx, edx; Val
0x180199320  mov     r8d, 2808h; Size
0x180199326  lea     rcx, [rsp+28A0h+var_2848]; void *
0x18019932b  call    memset_0
0x180199330  mov     [rsp+28A0h+var_2858], r13d
0x180199335  mov     [rsp+28A0h+var_2880], r13d; int
0x18019933a  lea     r9, [rsp+28A0h+var_2880]; unsigned int *
0x18019933f  mov     r8d, ebx; unsigned int
0x180199342  mov     rdx, rdi; unsigned int *
0x180199345  lea     rcx, [rsp+28A0h+var_2870]; this
0x18019934a  call    ?Compress@CSimple256Compressor@inverted@@AEAAXPEBIIPEAI@Z; inverted::CSimple256Compressor::Compress(uint const *,uint,uint *)
0x18019934f  sub     ebx, [rsp+28A0h+var_2880]
0x180199353  mov     eax, [rsp+28A0h+var_2880]
0x180199357  lea     rdx, [rdi+rax*4]; unsigned int *
0x18019935b  mov     r8d, ebx; unsigned int
0x18019935e  lea     rcx, [rsp+28A0h+var_2870]; this
0x180199363  call    ?CompressRemainder@CSimple256Compressor@inverted@@AEAAXPEBII@Z; inverted::CSimple256Compressor::CompressRemainder(uint const *,uint)
0x180199368  mov     rdx, [rsp+28A0h+var_2860]
0x18019936d  mov     rcx, rdx
0x180199370  shl     rcx, 20h
0x180199374  mov     eax, [rsp+28A0h+var_2858]
0x180199378  or      rcx, rax
0x18019937b  mov     r12, qword ptr [rsp+28A0h+var_2870]
0x180199380  mov     [r12], rcx
0x180199384  mov     r15d, edx
0x180199387  lea     r14d, ds:0[r15*4]
0x18019938f  movsxd  rcx, r14d
0x180199392  lea     rcx, ds:2[rcx*2]; cb
0x18019939a  call    cs:__imp_CoTaskMemAlloc
0x1801993a1  nop     dword ptr [rax+rax+00h]
0x1801993a6  mov     rbx, rax
0x1801993a9  test    rax, rax
0x1801993ac  jz      loc_180199456
0x1801993b2  mov     edx, r13d
0x1801993b5  mov     r9, r13
0x1801993b8  test    r15d, r15d
0x1801993bb  jz      short loc_1801993F9
0x1801993bd  cmp     edx, r14d
0x1801993c0  jge     short loc_1801993F9
0x1801993c2  mov     r8, r13
0x1801993c5  cmp     edx, r14d
0x1801993c8  jge     short loc_1801993F1
0x1801993ca  mov     cl, r8b
0x1801993cd  shl     cl, 3
0x1801993d0  mov     r10, [r12+r9*8]
0x1801993d4  shr     r10, cl
0x1801993d7  test    r10w, r10w
0x1801993db  jz      short loc_1801993E7
0x1801993dd  movsxd  rax, edx
0x1801993e0  mov     [rbx+rax*2], r10w
0x1801993e5  inc     edx
0x1801993e7  add     r8, 2
0x1801993eb  cmp     r8, 8
0x1801993ef  jb      short loc_1801993C5
0x1801993f1  inc     r9
0x1801993f4  cmp     r9, r15
0x1801993f7  jb      short loc_1801993BD
0x1801993f9  movsxd  rcx, edx
0x1801993fc  mov     [rbx+rcx*2], r13w
0x180199401  or      r8, 0FFFFFFFFFFFFFFFFh
0x180199405  mov     rdx, rbx
0x180199408  lea     rcx, [rsp+28A0h+var_2880]
0x18019940d  call    ??$make_unique_string_nothrow@V?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@wil@@@wil@@YA?AV?$unique_any_t@V?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@@0@PEBG_K@Z; wil::make_unique_string_nothrow<wil::unique_any_t<wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>>>(ushort const *,unsigned __int64)
0x180199412  mov     rax, qword ptr [rsp+28A0h+var_2880]
0x180199417  mov     qword ptr [rsp+28A0h+var_2880], r13
0x18019941c  mov     [rsi], rax
0x18019941f  lea     rcx, [rsp+28A0h+var_2880]
0x180199424  call    ??1?$unique_storage@U?$resource_policy@PEAGP6AXPEAX@Z$1?CoTaskMemFree@@YAX0@ZU?$integral_constant@_K$0A@@wistd@@PEAGPEAG$0A@$$T@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>::~unique_storage<wil::details::resource_policy<ushort *,void (*)(void *),&CoTaskMemFree(void *),wistd::integral_constant<unsigned __int64,0>,ushort *,ushort *,0,std::nullptr_t>>(void)
0x180199429  nop
0x18019942a  mov     rcx, rbx; pv
0x18019942d  call    cs:__imp_CoTaskMemFree
0x180199434  nop     dword ptr [rax+rax+00h]
0x180199439  lea     rcx, [rsp+28A0h+var_2870]
0x18019943e  call    ?clear@?$vector_nothrow@_K@inverted@@QEAAXXZ; inverted::vector_nothrow<unsigned __int64>::clear(void)
0x180199443  mov     rcx, rdi; pv
0x180199446  call    cs:__imp_CoTaskMemFree
0x18019944d  nop     dword ptr [rax+rax+00h]
0x180199452  xor     eax, eax
0x180199454  jmp     short loc_1801994B3
0x180199456  mov     rcx, [rbp+27A8h]; this
0x18019945d  mov     ebx, 8007000Eh
0x180199462  mov     r9d, ebx; char *
0x180199465  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\userchoicehelpers"...
0x18019946c  mov     edx, 150h; void *
0x180199471  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180199476  lea     rcx, [rsp+28A0h+var_2870]
0x18019947b  call    ?clear@?$vector_nothrow@_K@inverted@@QEAAXXZ; inverted::vector_nothrow<unsigned __int64>::clear(void)
0x180199480  mov     rcx, rdi; pv
0x180199483  call    cs:__imp_CoTaskMemFree
0x18019948a  nop     dword ptr [rax+rax+00h]
0x18019948f  jmp     short loc_1801994B1
0x180199491  mov     rcx, [rbp+27A8h]; this
0x180199498  mov     ebx, 8007000Eh
0x18019949d  mov     r9d, ebx; char *
0x1801994a0  lea     r8, aOnecoreShellLi; "onecore\\shell\\lib\\userchoicehelpers"...
0x1801994a7  mov     edx, 140h; void *
0x1801994ac  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1801994b1  mov     eax, ebx
0x1801994b3  mov     rcx, [rbp+27A0h+var_40]
0x1801994ba  xor     rcx, rsp; StackCookie
0x1801994bd  call    __security_check_cookie
0x1801994c2  mov     rbx, [rsp+28A0h+arg_0]
0x1801994ca  add     rsp, 2870h
0x1801994d1  pop     r15
0x1801994d3  pop     r14
0x1801994d5  pop     r13
0x1801994d7  pop     r12
0x1801994d9  pop     rdi
0x1801994da  pop     rsi
0x1801994db  pop     rbp
0x1801994dc  retn
```
