# std::deque<ATL::CComPtr<ITraceEvent>,std::allocator<ATL::CComPtr<ITraceEvent>>>::_Growmap(unsigned __int64)

- ea: `0x180028d68`
- end: `0x180028f1d`
- name: `?_Growmap@?$deque@V?$CComPtr@UITraceEvent@@@ATL@@V?$allocator@V?$CComPtr@UITraceEvent@@@ATL@@@std@@@std@@AEAAX_K@Z`
- size: `437`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, broker_com_uri`

## callers

- `0x180028b18`

## callees

- `0x180009e14`
- `0x180009f84`
- `0x180016284`
- `0x180028d68`
- `0x18004a078`

## import_xrefs

- `VCRUNTIME140!memset` at `0x180028e58`
- `VCRUNTIME140!memset` at `0x180028e9b`
- `VCRUNTIME140!memset` at `0x180028e58`
- `VCRUNTIME140!memset` at `0x180028e9b`
- `VCRUNTIME140!memmove` at `0x180028e27`
- `VCRUNTIME140!memmove` at `0x180028e42`
- `VCRUNTIME140!memmove` at `0x180028e71`
- `VCRUNTIME140!memmove` at `0x180028e8c`
- `VCRUNTIME140!memmove` at `0x180028e27`
- `VCRUNTIME140!memmove` at `0x180028e42`
- `VCRUNTIME140!memmove` at `0x180028e71`
- `VCRUNTIME140!memmove` at `0x180028e8c`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180028f0a`
- `api-ms-win-crt-runtime-l1-1-0!_invoke_watson` at `0x180028f0a`

## pseudocode

```c
void __fastcall std::deque<ATL::CComPtr<ITraceEvent>>::_Growmap(_QWORD *a1)
{
  unsigned __int64 v2; // rsi
  unsigned __int64 v3; // rcx
  unsigned __int64 v4; // rdi
  __int64 v5; // r15
  char *v6; // r14
  unsigned __int64 v7; // rcx
  char *v8; // r12
  __int64 v9; // rax
  unsigned __int64 v10; // rsi
  size_t v11; // rbx
  char *v12; // r12
  const void *v13; // rdx
  size_t v14; // r8
  char *v15; // rcx
  _QWORD *v16; // rcx

  v2 = 1;
  v3 = a1[2];
  if ( v3 )
    v2 = v3;
  while ( v2 == v3 || v2 < 8 )
  {
    if ( 0xFFFFFFFFFFFFFFFLL - v2 < v2 )
      std::deque<ATL::CComPtr<ITraceEvent>>::_Xlen();
    v2 *= 2LL;
  }
  v4 = a1[3] >> 1;
  if ( v2 > 0x1FFFFFFFFFFFFFFFLL )
    __scrt_throw_std_bad_array_new_length();
  _mm_lfence();
  v5 = 8 * v4;
  v6 = (char *)std::_Allocate<16,std::_Default_allocate_traits>(8 * v2);
  v7 = v2 >> 1;
  v8 = &v6[8 * v4];
  while ( v2 <= v7 )
    v2 *= 2LL;
  v9 = a1[2];
  v10 = v2 - v9;
  v11 = 8 * v9 - v5;
  memmove(v8, (const void *)(a1[1] + v5), v11);
  v12 = &v8[v11];
  _mm_lfence();
  v13 = (const void *)a1[1];
  if ( v4 > v10 )
  {
    memmove(v12, v13, 8 * v10);
    memmove(v6, (const void *)(8 * v10 + a1[1]), v5 - 8 * v10);
    v15 = &v6[v5 - 8 * v10];
    v14 = 8 * v10;
  }
  else
  {
    memmove(v12, v13, 8 * v4);
    memset(&v12[v5], 0, 8 * (v10 - v4));
    v14 = 8 * v4;
    v15 = v6;
  }
  memset(v15, 0, v14);
  v16 = (_QWORD *)a1[1];
  if ( v16 )
  {
    if ( (unsigned __int64)(8LL * a1[2]) >= 0x1000 )
    {
      if ( (unsigned __int64)v16 - *(v16 - 1) - 8 > 0x1F )
        _invoke_watson(0, 0, 0, 0, 0);
      v16 = (_QWORD *)*(v16 - 1);
    }
    operator delete(v16);
  }
  a1[2] += v10;
  a1[1] = v6;
}

```

## disassembly

```asm
0x180028d68  mov     [rsp+arg_8], rbx
0x180028d6d  mov     [rsp+arg_10], rbp
0x180028d72  push    rsi
0x180028d73  push    rdi
0x180028d74  push    r12
0x180028d76  push    r14
0x180028d78  push    r15
0x180028d7a  sub     rsp, 30h
0x180028d7e  mov     rbp, rcx
0x180028d81  mov     esi, 1
0x180028d86  mov     rcx, [rcx+10h]
0x180028d8a  test    rcx, rcx
0x180028d8d  cmovnz  rsi, rcx
0x180028d91  mov     rax, rsi
0x180028d94  sub     rax, rcx
0x180028d97  cmp     rax, 1
0x180028d9b  jb      short loc_180028DA3
0x180028d9d  cmp     rsi, 8
0x180028da1  jnb     short loc_180028DBE
0x180028da3  mov     rax, 0FFFFFFFFFFFFFFFh
0x180028dad  sub     rax, rsi
0x180028db0  cmp     rax, rsi
0x180028db3  jb      loc_180028F17
0x180028db9  add     rsi, rsi
0x180028dbc  jmp     short loc_180028D91
0x180028dbe  mov     rdi, [rbp+18h]
0x180028dc2  mov     rax, 1FFFFFFFFFFFFFFFh
0x180028dcc  shr     rdi, 1
0x180028dcf  cmp     rsi, rax
0x180028dd2  ja      loc_180028F11
0x180028dd8  lfence
0x180028ddb  lea     rcx, ds:0[rsi*8]
0x180028de3  call    ??$_Allocate@$0BA@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate<16,std::_Default_allocate_traits>(unsigned __int64)
0x180028de8  lea     r15, ds:0[rdi*8]
0x180028df0  mov     rcx, rsi
0x180028df3  mov     r14, rax
0x180028df6  shr     rcx, 1
0x180028df9  lea     r12, [r15+rax]
0x180028dfd  jmp     short loc_180028E02
0x180028dff  add     rsi, rsi
0x180028e02  cmp     rsi, rcx
0x180028e05  jbe     short loc_180028DFF
0x180028e07  mov     rcx, [rbp+8]
0x180028e0b  mov     rax, [rbp+10h]
0x180028e0f  sub     rsi, rax
0x180028e12  shl     rax, 3
0x180028e16  lea     rdx, [rcx+r15]; Src
0x180028e1a  sub     rax, rdx
0x180028e1d  lea     rbx, [rax+rcx]
0x180028e21  mov     rcx, r12; void *
0x180028e24  mov     r8, rbx; Size
0x180028e27  call    cs:__imp_memmove
0x180028e2d  add     r12, rbx
0x180028e30  lfence
0x180028e33  mov     rdx, [rbp+8]; Src
0x180028e37  mov     rcx, r12; void *
0x180028e3a  cmp     rdi, rsi
0x180028e3d  ja      short loc_180028E66
0x180028e3f  mov     r8, r15; Size
0x180028e42  call    cs:__imp_memmove
0x180028e48  mov     r8, rsi
0x180028e4b  lea     rcx, [r15+r12]; void *
0x180028e4f  sub     r8, rdi
0x180028e52  xor     edx, edx; Val
0x180028e54  shl     r8, 3; Size
0x180028e58  call    cs:__imp_memset
0x180028e5e  mov     r8, r15
0x180028e61  mov     rcx, r14
0x180028e64  jmp     short loc_180028E99
0x180028e66  lea     rdi, ds:0[rsi*8]
0x180028e6e  mov     r8, rdi; Size
0x180028e71  call    cs:__imp_memmove
0x180028e77  mov     rax, [rbp+8]
0x180028e7b  mov     rcx, r14; void *
0x180028e7e  lea     rdx, [rdi+rax]; Src
0x180028e82  sub     rax, rdx
0x180028e85  lea     rbx, [rax+r15]
0x180028e89  mov     r8, rbx; Size
0x180028e8c  call    cs:__imp_memmove
0x180028e92  lea     rcx, [rbx+r14]; void *
0x180028e96  mov     r8, rdi; Size
0x180028e99  xor     edx, edx; Val
0x180028e9b  call    cs:__imp_memset
0x180028ea1  mov     rcx, [rbp+8]
0x180028ea5  test    rcx, rcx
0x180028ea8  jz      short loc_180028ED8
0x180028eaa  mov     rdx, [rbp+10h]
0x180028eae  shl     rdx, 3
0x180028eb2  cmp     rdx, 1000h
0x180028eb9  jb      short loc_180028ED3
0x180028ebb  mov     rax, [rcx-8]
0x180028ebf  add     rdx, 27h ; '''
0x180028ec3  sub     rcx, rax
0x180028ec6  sub     rcx, 8
0x180028eca  cmp     rcx, 1Fh
0x180028ece  ja      short loc_180028EF7
0x180028ed0  mov     rcx, rax; Block
0x180028ed3  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180028ed8  add     [rbp+10h], rsi
0x180028edc  mov     rbx, [rsp+58h+arg_8]
0x180028ee1  mov     [rbp+8], r14
0x180028ee5  mov     rbp, [rsp+58h+arg_10]
0x180028eea  add     rsp, 30h
0x180028eee  pop     r15
0x180028ef0  pop     r14
0x180028ef2  pop     r12
0x180028ef4  pop     rdi
0x180028ef5  pop     rsi
0x180028ef6  retn
0x180028ef7  xor     r9d, r9d; LineNo
0x180028efa  mov     [rsp+58h+Reserved], 0; Reserved
0x180028f03  xor     r8d, r8d; FileName
0x180028f06  xor     edx, edx; FunctionName
0x180028f08  xor     ecx, ecx; Expression
0x180028f0a  call    cs:__imp__invoke_watson
0x180028f11  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180028f17  call    ?_Xlen@?$deque@V?$CComPtr@UITraceEvent@@@ATL@@V?$allocator@V?$CComPtr@UITraceEvent@@@ATL@@@std@@@std@@CAXXZ; std::deque<ATL::CComPtr<ITraceEvent>>::_Xlen(void)
```
