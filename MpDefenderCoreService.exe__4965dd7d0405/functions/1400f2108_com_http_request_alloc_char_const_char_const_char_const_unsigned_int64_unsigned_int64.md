# com::http::request_alloc(char const *,char const *,char const *,unsigned __int64,unsigned __int64)

- ea: `0x1400f2108`
- end: `0x1400f2342`
- name: `?request_alloc@http@com@@YA?AV?$unique_ptr@U__MIDL___MIDL_itf_com_http_server_if_0000_0000_0002@@Urequest_deleter_t@http@com@@@std@@PEBD00_K1@Z`
- size: `570`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `service_task, broker_com_uri`

## callers

- `0x1400f00e4`

## callees

- `0x1400f2108`
- `0x1401662d0`
- `0x140166990`

## import_xrefs

- `ole32!CoTaskMemAlloc` at `0x1400f2158`
- `ole32!CoTaskMemAlloc` at `0x1400f21a0`
- `ole32!CoTaskMemAlloc` at `0x1400f21e5`
- `ole32!CoTaskMemAlloc` at `0x1400f223f`
- `ole32!CoTaskMemAlloc` at `0x1400f226e`
- `ole32!CoTaskMemAlloc` at `0x1400f2291`
- `ole32!CoTaskMemAlloc` at `0x1400f2158`
- `ole32!CoTaskMemAlloc` at `0x1400f21a0`
- `ole32!CoTaskMemAlloc` at `0x1400f21e5`
- `ole32!CoTaskMemAlloc` at `0x1400f223f`
- `ole32!CoTaskMemAlloc` at `0x1400f226e`
- `ole32!CoTaskMemAlloc` at `0x1400f2291`
- `ole32!CoTaskMemFree` at `0x1400f22d3`
- `ole32!CoTaskMemFree` at `0x1400f22dc`
- `ole32!CoTaskMemFree` at `0x1400f22ec`
- `ole32!CoTaskMemFree` at `0x1400f22f5`
- `ole32!CoTaskMemFree` at `0x1400f230c`
- `ole32!CoTaskMemFree` at `0x1400f231a`
- `ole32!CoTaskMemFree` at `0x1400f2328`
- `ole32!CoTaskMemFree` at `0x1400f22d3`
- `ole32!CoTaskMemFree` at `0x1400f22dc`
- `ole32!CoTaskMemFree` at `0x1400f22ec`
- `ole32!CoTaskMemFree` at `0x1400f22f5`
- `ole32!CoTaskMemFree` at `0x1400f230c`
- `ole32!CoTaskMemFree` at `0x1400f231a`
- `ole32!CoTaskMemFree` at `0x1400f2328`

## pseudocode

```c
_QWORD *__fastcall com::http::request_alloc(_QWORD *a1, _BYTE *a2, _BYTE *a3, _BYTE *a4, __int64 a5, SIZE_T a6)
{
  size_t v6; // r15
  size_t v11; // rbx
  void *v12; // rax
  void *v13; // rbp
  size_t v14; // rbx
  void *v15; // rax
  void *v16; // rsi
  void *v17; // rax
  void *v18; // rdi
  _QWORD *v19; // rax
  _QWORD *v20; // rbx
  void *v21; // rax
  void *v22; // r15
  void *v23; // rax
  void *v24; // r12

  v6 = -1;
  if ( a2 )
  {
    v11 = -1;
    do
      ++v11;
    while ( a2[v11] );
    v12 = CoTaskMemAlloc(v11 + 1);
    v13 = v12;
    if ( v12 )
      memset(v12, 0, v11 + 1);
    else
      v13 = 0;
    memmove(v13, a2, v11);
  }
  else
  {
    v13 = 0;
  }
  if ( a3 )
  {
    v14 = -1;
    do
      ++v14;
    while ( a3[v14] );
    v15 = CoTaskMemAlloc(v14 + 1);
    v16 = v15;
    if ( v15 )
      memset(v15, 0, v14 + 1);
    else
      v16 = 0;
    memmove(v16, a3, v14);
  }
  else
  {
    v16 = 0;
  }
  if ( a4 )
  {
    do
      ++v6;
    while ( a4[v6] );
    v17 = CoTaskMemAlloc(v6 + 1);
    v18 = v17;
    if ( v17 )
      memset(v17, 0, v6 + 1);
    else
      v18 = 0;
    memmove(v18, a4, v6);
  }
  else
  {
    v18 = 0;
  }
  if ( v13 && v16 )
  {
    if ( v18 )
    {
      v19 = CoTaskMemAlloc(0x40u);
      v20 = v19;
      if ( v19 )
      {
        memset(v19, 0, 0x40u);
        v21 = CoTaskMemAlloc(24 * a5);
        v22 = v21;
        if ( v21 )
        {
          memset(v21, 0, 24 * a5);
          v23 = CoTaskMemAlloc(a6);
          v24 = v23;
          if ( v23 )
          {
            memset(v23, 0, a6);
            *v20 = v13;
            v20[1] = v16;
            v20[2] = v18;
            *((_DWORD *)v20 + 8) = a5;
            v20[5] = v22;
            *((_DWORD *)v20 + 12) = a6;
            v20[7] = v24;
            *a1 = v20;
            return a1;
          }
          CoTaskMemFree(v22);
        }
        CoTaskMemFree(v20);
      }
      *a1 = 0;
      CoTaskMemFree(v18);
      CoTaskMemFree(v16);
LABEL_40:
      CoTaskMemFree(v13);
      return a1;
    }
    *a1 = 0;
    goto LABEL_38;
  }
  *a1 = 0;
  if ( v18 )
    CoTaskMemFree(v18);
  if ( v16 )
LABEL_38:
    CoTaskMemFree(v16);
  if ( v13 )
    goto LABEL_40;
  return a1;
}

```

## disassembly

```asm
0x1400f2108  push    rbx
0x1400f210a  push    rbp
0x1400f210b  push    rsi
0x1400f210c  push    rdi
0x1400f210d  push    r12
0x1400f210f  push    r13
0x1400f2111  push    r14
0x1400f2113  push    r15
0x1400f2115  sub     rsp, 38h
0x1400f2119  mov     rax, [rsp+78h+arg_20]
0x1400f2121  or      r15, 0FFFFFFFFFFFFFFFFh
0x1400f2125  mov     [rsp+78h+var_58], rax
0x1400f212a  mov     r13, r9
0x1400f212d  mov     rax, [rsp+78h+arg_28]
0x1400f2135  mov     r12, r8
0x1400f2138  mov     [rsp+78h+cb], rax
0x1400f213d  mov     rdi, rdx
0x1400f2140  mov     r14, rcx
0x1400f2143  test    rdx, rdx
0x1400f2146  jz      short loc_1400F2188
0x1400f2148  mov     rbx, r15
0x1400f214b  inc     rbx
0x1400f214e  cmp     byte ptr [rdx+rbx], 0
0x1400f2152  jnz     short loc_1400F214B
0x1400f2154  lea     rcx, [rbx+1]; cb
0x1400f2158  call    cs:__imp_CoTaskMemAlloc
0x1400f215e  mov     rbp, rax
0x1400f2161  test    rax, rax
0x1400f2164  jz      short loc_1400F2176
0x1400f2166  lea     r8, [rbx+1]; Size
0x1400f216a  xor     edx, edx; Val
0x1400f216c  mov     rcx, rax; void *
0x1400f216f  call    memset
0x1400f2174  jmp     short loc_1400F2178
0x1400f2176  xor     ebp, ebp
0x1400f2178  mov     r8, rbx; Size
0x1400f217b  mov     rdx, rdi; Src
0x1400f217e  mov     rcx, rbp; void *
0x1400f2181  call    memmove
0x1400f2186  jmp     short loc_1400F218A
0x1400f2188  xor     ebp, ebp
0x1400f218a  test    r12, r12
0x1400f218d  jz      short loc_1400F21D0
0x1400f218f  mov     rbx, r15
0x1400f2192  inc     rbx
0x1400f2195  cmp     byte ptr [r12+rbx], 0
0x1400f219a  jnz     short loc_1400F2192
0x1400f219c  lea     rcx, [rbx+1]; cb
0x1400f21a0  call    cs:__imp_CoTaskMemAlloc
0x1400f21a6  mov     rsi, rax
0x1400f21a9  test    rax, rax
0x1400f21ac  jz      short loc_1400F21BE
0x1400f21ae  lea     r8, [rbx+1]; Size
0x1400f21b2  xor     edx, edx; Val
0x1400f21b4  mov     rcx, rax; void *
0x1400f21b7  call    memset
0x1400f21bc  jmp     short loc_1400F21C0
0x1400f21be  xor     esi, esi
0x1400f21c0  mov     r8, rbx; Size
0x1400f21c3  mov     rdx, r12; Src
0x1400f21c6  mov     rcx, rsi; void *
0x1400f21c9  call    memmove
0x1400f21ce  jmp     short loc_1400F21D2
0x1400f21d0  xor     esi, esi
0x1400f21d2  test    r13, r13
0x1400f21d5  jz      short loc_1400F2215
0x1400f21d7  inc     r15
0x1400f21da  cmp     byte ptr [r15+r13], 0
0x1400f21df  jnz     short loc_1400F21D7
0x1400f21e1  lea     rcx, [r15+1]; cb
0x1400f21e5  call    cs:__imp_CoTaskMemAlloc
0x1400f21eb  mov     rdi, rax
0x1400f21ee  test    rax, rax
0x1400f21f1  jz      short loc_1400F2203
0x1400f21f3  lea     r8, [r15+1]; Size
0x1400f21f7  xor     edx, edx; Val
0x1400f21f9  mov     rcx, rax; void *
0x1400f21fc  call    memset
0x1400f2201  jmp     short loc_1400F2205
0x1400f2203  xor     edi, edi
0x1400f2205  mov     r8, r15; Size
0x1400f2208  mov     rdx, r13; Src
0x1400f220b  mov     rcx, rdi; void *
0x1400f220e  call    memmove
0x1400f2213  jmp     short loc_1400F2217
0x1400f2215  xor     edi, edi
0x1400f2217  test    rbp, rbp
0x1400f221a  jz      loc_1400F22FD
0x1400f2220  test    rsi, rsi
0x1400f2223  jz      loc_1400F22FD
0x1400f2229  test    rdi, rdi
0x1400f222c  jnz     short loc_1400F2236
0x1400f222e  mov     [r14], rdi
0x1400f2231  jmp     loc_1400F2317
0x1400f2236  mov     r15d, 40h ; '@'
0x1400f223c  mov     ecx, r15d; cb
0x1400f223f  call    cs:__imp_CoTaskMemAlloc
0x1400f2245  mov     rbx, rax
0x1400f2248  test    rax, rax
0x1400f224b  jz      loc_1400F22E2
0x1400f2251  mov     r8d, r15d; Size
0x1400f2254  xor     edx, edx; Val
0x1400f2256  mov     rcx, rax; void *
0x1400f2259  call    memset
0x1400f225e  mov     rax, [rsp+78h+var_58]
0x1400f2263  lea     r12, [rax+rax*2]
0x1400f2267  shl     r12, 3
0x1400f226b  mov     rcx, r12; cb
0x1400f226e  call    cs:__imp_CoTaskMemAlloc
0x1400f2274  mov     r15, rax
0x1400f2277  test    rax, rax
0x1400f227a  jz      short loc_1400F22D9
0x1400f227c  mov     r8, r12; Size
0x1400f227f  xor     edx, edx; Val
0x1400f2281  mov     rcx, rax; void *
0x1400f2284  call    memset
0x1400f2289  mov     r13, [rsp+78h+cb]
0x1400f228e  mov     rcx, r13; cb
0x1400f2291  call    cs:__imp_CoTaskMemAlloc
0x1400f2297  mov     r12, rax
0x1400f229a  test    rax, rax
0x1400f229d  jz      short loc_1400F22D0
0x1400f229f  mov     r8, r13; Size
0x1400f22a2  xor     edx, edx; Val
0x1400f22a4  mov     rcx, rax; void *
0x1400f22a7  call    memset
0x1400f22ac  mov     rax, [rsp+78h+var_58]
0x1400f22b1  mov     [rbx], rbp
0x1400f22b4  mov     [rbx+8], rsi
0x1400f22b8  mov     [rbx+10h], rdi
0x1400f22bc  mov     [rbx+20h], eax
0x1400f22bf  mov     [rbx+28h], r15
0x1400f22c3  mov     [rbx+30h], r13d
0x1400f22c7  mov     [rbx+38h], r12
0x1400f22cb  mov     [r14], rbx
0x1400f22ce  jmp     short loc_1400F232E
0x1400f22d0  mov     rcx, r15; pv
0x1400f22d3  call    cs:__imp_CoTaskMemFree
0x1400f22d9  mov     rcx, rbx; pv
0x1400f22dc  call    cs:__imp_CoTaskMemFree
0x1400f22e2  mov     rcx, rdi; pv
0x1400f22e5  mov     qword ptr [r14], 0
0x1400f22ec  call    cs:__imp_CoTaskMemFree
0x1400f22f2  mov     rcx, rsi; pv
0x1400f22f5  call    cs:__imp_CoTaskMemFree
0x1400f22fb  jmp     short loc_1400F2325
0x1400f22fd  mov     qword ptr [r14], 0
0x1400f2304  test    rdi, rdi
0x1400f2307  jz      short loc_1400F2312
0x1400f2309  mov     rcx, rdi; pv
0x1400f230c  call    cs:__imp_CoTaskMemFree
0x1400f2312  test    rsi, rsi
0x1400f2315  jz      short loc_1400F2320
0x1400f2317  mov     rcx, rsi; pv
0x1400f231a  call    cs:__imp_CoTaskMemFree
0x1400f2320  test    rbp, rbp
0x1400f2323  jz      short loc_1400F232E
0x1400f2325  mov     rcx, rbp; pv
0x1400f2328  call    cs:__imp_CoTaskMemFree
0x1400f232e  mov     rax, r14
0x1400f2331  add     rsp, 38h
0x1400f2335  pop     r15
0x1400f2337  pop     r14
0x1400f2339  pop     r13
0x1400f233b  pop     r12
0x1400f233d  pop     rdi
0x1400f233e  pop     rsi
0x1400f233f  pop     rbp
0x1400f2340  pop     rbx
0x1400f2341  retn
```
