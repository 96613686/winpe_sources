# std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>::_Emplace_reallocate<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)

- ea: `0x180022828`
- end: `0x180022a78`
- name: `??$_Emplace_reallocate@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@AEAAPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV23@$$QEAV23@@Z`
- size: `592`
- prototype: `char *__fastcall(char **, char *, _QWORD *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180025590`

## callees

- `0x1800045f4`
- `0x180004a08`
- `0x180013cac`
- `0x180017960`
- `0x18001d424`
- `0x180022828`
- `0x180022ca4`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800229d3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800229d3`

## pseudocode

```c
char *__fastcall std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::_Emplace_reallocate<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(
        char **a1,
        char *a2,
        _QWORD *a3)
{
  char *v3; // r12
  __int64 v4; // r14
  __int64 v7; // rax
  unsigned __int64 v9; // r15
  unsigned __int64 v10; // rcx
  __int64 v11; // r9
  size_t v12; // rcx
  unsigned __int64 v13; // rdx
  char *v14; // rbp
  char *v15; // rax
  __int64 v16; // rsi
  char *v17; // rdx
  char *v18; // rcx
  char *v19; // r8
  char *v20; // rcx
  __int64 v21; // rsi
  char *v22; // rcx
  char *v23; // rdi
  char *v24; // r14
  char *v25; // rax
  unsigned __int64 v26; // rdx
  char *v27; // rcx
  _QWORD v29[3]; // [rsp+20h] [rbp-78h] BYREF
  char *v30; // [rsp+38h] [rbp-60h]
  _QWORD *v31; // [rsp+40h] [rbp-58h]
  __int64 v32; // [rsp+A0h] [rbp+8h]

  v3 = *a1;
  v4 = 0xFFFFFFFFFFFFFFFLL;
  v7 = (a1[1] - *a1) >> 4;
  if ( v7 == 0xFFFFFFFFFFFFFFFLL )
    std::vector<unsigned char>::_Xlength();
  v9 = v7 + 1;
  v10 = (a1[2] - v3) >> 4;
  v11 = 0;
  if ( v10 <= 0xFFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v13 = v7 + 1;
    if ( v10 + (v10 >> 1) >= v9 )
      v13 = v10 + (v10 >> 1);
    if ( v13 > 0xFFFFFFFFFFFFFFFLL )
      __scrt_throw_std_bad_array_new_length();
    v4 = v13;
    v12 = 16 * v13;
    v32 = 16 * v13;
    if ( !(16 * v13) )
    {
      v14 = 0;
      goto LABEL_13;
    }
    if ( v12 < 0x1000 )
    {
      v15 = (char *)operator new(v12);
      goto LABEL_12;
    }
  }
  else
  {
    v12 = -16;
    v32 = -16;
  }
  v15 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v12);
LABEL_12:
  v11 = 0;
  v14 = v15;
LABEL_13:
  v29[0] = a1;
  v29[2] = v4;
  v16 = (a2 - v3) >> 4;
  v17 = v14;
  v18 = &v14[16 * v16];
  v30 = v18;
  v31 = v18 + 16;
  *(_QWORD *)v18 = *a3;
  *((_QWORD *)v18 + 1) = a3[1];
  *a3 = 0;
  a3[1] = 0;
  v19 = a1[1];
  v20 = *a1;
  if ( a2 == v19 )
  {
    while ( v20 != v19 )
    {
      *(_QWORD *)v17 = *(_QWORD *)v20;
      v17 += 16;
      *((_QWORD *)v17 - 1) = *((_QWORD *)v20 + 1);
      *(_QWORD *)v20 = 0;
      *((_QWORD *)v20 + 1) = 0;
      v20 += 16;
    }
    v21 = 16 * v16;
  }
  else
  {
    while ( v20 != a2 )
    {
      *(_QWORD *)v17 = *(_QWORD *)v20;
      v17 += 16;
      *((_QWORD *)v17 - 1) = *((_QWORD *)v20 + 1);
      *(_QWORD *)v20 = 0;
      *((_QWORD *)v20 + 1) = 0;
      v20 += 16;
    }
    v17 = a1[1];
    v21 = 16 * v16;
    v30 = v14;
    v22 = &v14[v21 + 16];
    while ( a2 != v17 )
    {
      *(_QWORD *)v22 = *(_QWORD *)a2;
      v22 += 16;
      *((_QWORD *)v22 - 1) = *((_QWORD *)a2 + 1);
      *(_QWORD *)a2 = 0;
      *((_QWORD *)a2 + 1) = 0;
      a2 += 16;
    }
  }
  v23 = *a1;
  v29[1] = 0;
  if ( v23 )
  {
    v24 = a1[1];
    while ( v23 != v24 )
    {
      if ( *(_QWORD *)v23 )
      {
        CoTaskMemFree(*(LPVOID *)v23);
        *(_QWORD *)v23 = 0;
        *((_QWORD *)v23 + 1) = 0;
      }
      v23 += 16;
    }
    v25 = *a1;
    v26 = (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL;
    if ( v26 < 0x1000 )
    {
      v27 = *a1;
    }
    else
    {
      v27 = (char *)*((_QWORD *)v25 - 1);
      if ( (unsigned __int64)(v25 - v27 - 8) > 0x1F )
        __fastfail(5u);
      v26 += 39LL;
    }
    operator delete(v27, v26);
  }
  *a1 = v14;
  a1[1] = &v14[16 * v9];
  a1[2] = &v14[v32];
  ((void (__fastcall *)(_QWORD *, char *, char *, __int64))std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::_Reallocation_guard::~_Reallocation_guard)(
    v29,
    v17,
    v19,
    v11);
  return &v14[v21];
}

```

## disassembly

```asm
0x180022828  push    rbx
0x18002282a  push    rbp
0x18002282b  push    rsi
0x18002282c  push    rdi
0x18002282d  push    r12
0x18002282f  push    r13
0x180022831  push    r14
0x180022833  push    r15
0x180022835  sub     rsp, 58h
0x180022839  mov     r12, [rcx]
0x18002283c  mov     r14, 0FFFFFFFFFFFFFFFh
0x180022846  mov     rax, [rcx+8]
0x18002284a  mov     r13, r8
0x18002284d  sub     rax, r12
0x180022850  mov     rdi, rdx
0x180022853  sar     rax, 4
0x180022857  mov     rbx, rcx
0x18002285a  cmp     rax, r14
0x18002285d  jz      loc_180022A72
0x180022863  mov     rcx, [rcx+10h]
0x180022867  lea     r15, [rax+1]
0x18002286b  sub     rcx, r12
0x18002286e  mov     rax, r14
0x180022871  sar     rcx, 4
0x180022875  xor     r9d, r9d
0x180022878  mov     rdx, rcx
0x18002287b  shr     rdx, 1
0x18002287e  sub     rax, rdx
0x180022881  cmp     rcx, rax
0x180022884  jbe     short loc_180022894
0x180022886  lea     rcx, [r9-10h]
0x18002288a  mov     [rsp+98h+arg_0], rcx
0x180022892  jmp     short loc_1800228D0
0x180022894  lea     rax, [rcx+rdx]
0x180022898  mov     rdx, r15
0x18002289b  cmp     rax, r15
0x18002289e  cmovnb  rdx, rax
0x1800228a2  cmp     rdx, r14
0x1800228a5  ja      loc_180022A6C
0x1800228ab  mov     rcx, rdx
0x1800228ae  mov     r14, rdx
0x1800228b1  shl     rcx, 4; Size
0x1800228b5  mov     [rsp+98h+arg_0], rcx
0x1800228bd  test    rcx, rcx
0x1800228c0  jnz     short loc_1800228C7
0x1800228c2  mov     rbp, r9
0x1800228c5  jmp     short loc_1800228E2
0x1800228c7  cmp     rcx, 1000h
0x1800228ce  jb      short loc_1800228D7
0x1800228d0  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x1800228d5  jmp     short loc_1800228DC
0x1800228d7  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800228dc  xor     r9d, r9d
0x1800228df  mov     rbp, rax
0x1800228e2  mov     rsi, rdi
0x1800228e5  mov     [rsp+98h+var_78], rbx
0x1800228ea  sub     rsi, r12
0x1800228ed  mov     [rsp+98h+var_68], r14
0x1800228f2  sar     rsi, 4
0x1800228f6  mov     rdx, rbp
0x1800228f9  mov     rcx, rsi
0x1800228fc  shl     rcx, 4
0x180022900  add     rcx, rbp
0x180022903  mov     [rsp+98h+var_60], rcx
0x180022908  lea     rax, [rcx+10h]
0x18002290c  mov     [rsp+98h+var_58], rax
0x180022911  mov     rax, [r13+0]
0x180022915  mov     [rcx], rax
0x180022918  mov     rax, [r13+8]
0x18002291c  mov     [rcx+8], rax
0x180022920  mov     [r13+0], r9
0x180022924  mov     [r13+8], r9
0x180022928  mov     r8, [rbx+8]
0x18002292c  mov     rcx, [rbx]
0x18002292f  cmp     rdi, r8
0x180022932  jnz     short loc_18002297B
0x180022934  jmp     short loc_180022953
0x180022936  mov     rax, [rcx]
0x180022939  mov     [rdx], rax
0x18002293c  lea     rdx, [rdx+10h]
0x180022940  mov     rax, [rcx+8]
0x180022944  mov     [rdx-8], rax
0x180022948  mov     [rcx], r9
0x18002294b  mov     [rcx+8], r9
0x18002294f  add     rcx, 10h
0x180022953  cmp     rcx, r8
0x180022956  jnz     short loc_180022936
0x180022958  shl     rsi, 4
0x18002295c  jmp     short loc_1800229B8
0x18002295e  mov     rax, [rcx]
0x180022961  mov     [rdx], rax
0x180022964  lea     rdx, [rdx+10h]
0x180022968  mov     rax, [rcx+8]
0x18002296c  mov     [rdx-8], rax
0x180022970  mov     [rcx], r9
0x180022973  mov     [rcx+8], r9
0x180022977  add     rcx, 10h
0x18002297b  cmp     rcx, rdi
0x18002297e  jnz     short loc_18002295E
0x180022980  mov     rdx, [rbx+8]
0x180022984  shl     rsi, 4
0x180022988  mov     [rsp+98h+var_60], rbp
0x18002298d  lea     rcx, [rsi+10h]
0x180022991  add     rcx, rbp
0x180022994  jmp     short loc_1800229B3
0x180022996  mov     rax, [rdi]
0x180022999  mov     [rcx], rax
0x18002299c  lea     rcx, [rcx+10h]
0x1800229a0  mov     rax, [rdi+8]
0x1800229a4  mov     [rcx-8], rax
0x1800229a8  mov     [rdi], r9
0x1800229ab  mov     [rdi+8], r9
0x1800229af  add     rdi, 10h
0x1800229b3  cmp     rdi, rdx
0x1800229b6  jnz     short loc_180022996
0x1800229b8  mov     rdi, [rbx]
0x1800229bb  mov     [rsp+98h+var_70], r9
0x1800229c0  test    rdi, rdi
0x1800229c3  jz      short loc_180022A2F
0x1800229c5  mov     r14, [rbx+8]
0x1800229c9  jmp     short loc_1800229ED
0x1800229cb  mov     rcx, [rdi]; pv
0x1800229ce  test    rcx, rcx
0x1800229d1  jz      short loc_1800229E9
0x1800229d3  call    cs:__imp_CoTaskMemFree
0x1800229da  nop     dword ptr [rax+rax+00h]
0x1800229df  xor     r9d, r9d
0x1800229e2  mov     [rdi], r9
0x1800229e5  mov     [rdi+8], r9
0x1800229e9  add     rdi, 10h
0x1800229ed  cmp     rdi, r14
0x1800229f0  jnz     short loc_1800229CB
0x1800229f2  mov     rax, [rbx]
0x1800229f5  mov     rdx, [rbx+10h]
0x1800229f9  sub     rdx, rax
0x1800229fc  and     rdx, 0FFFFFFFFFFFFFFF0h; unsigned __int64
0x180022a00  cmp     rdx, 1000h
0x180022a07  jb      short loc_180022A27
0x180022a09  mov     rcx, [rax-8]
0x180022a0d  sub     rax, rcx
0x180022a10  sub     rax, 8
0x180022a14  cmp     rax, 1Fh
0x180022a18  ja      short loc_180022A20
0x180022a1a  add     rdx, 27h ; '''
0x180022a1e  jmp     short loc_180022A2A
0x180022a20  mov     ecx, 5
0x180022a25  int     29h; Win8: RtlFailFast(ecx)
0x180022a27  mov     rcx, rax; void *
0x180022a2a  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180022a2f  mov     rax, [rsp+98h+arg_0]
0x180022a37  lea     rcx, [rsp+98h+var_78]
0x180022a3c  mov     [rbx], rbp
0x180022a3f  add     rax, rbp
0x180022a42  shl     r15, 4
0x180022a46  add     r15, rbp
0x180022a49  mov     [rbx+8], r15
0x180022a4d  mov     [rbx+10h], rax
0x180022a51  call    ??1_Reallocation_guard@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180022a56  lea     rax, [rsi+rbp]
0x180022a5a  add     rsp, 58h
0x180022a5e  pop     r15
0x180022a60  pop     r14
0x180022a62  pop     r13
0x180022a64  pop     r12
0x180022a66  pop     rdi
0x180022a67  pop     rsi
0x180022a68  pop     rbp
0x180022a69  pop     rbx
0x180022a6a  retn
0x180022a6c  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180022a72  call    ?_Xlength@?$vector@EV?$allocator@E@std@@@std@@CAXXZ; std::vector<uchar>::_Xlength(void)
```
