# std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>,std::allocator<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>>::_Emplace_reallocate<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>(wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> * const,wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64> &&)

- ea: `0x180021d84`
- end: `0x180021fcd`
- name: `??$_Emplace_reallocate@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@AEAAPEAV?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@QEAV23@$$QEAV23@@Z`
- size: `585`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x1800248b0`

## callees

- `0x1800045d4`
- `0x1800049f4`
- `0x180013908`
- `0x180017430`
- `0x18001ccac`
- `0x180021d84`
- `0x1800221e8`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f2f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180021f2f`

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
  unsigned __int64 v12; // rdx
  size_t v13; // rcx
  unsigned __int64 v14; // rax
  char *v15; // rbp
  char *v16; // rax
  __int64 v17; // rsi
  char *v18; // rdx
  char *v19; // rcx
  char *v20; // r8
  char *v21; // rcx
  __int64 v22; // rsi
  char *v23; // rcx
  char *v24; // rdi
  char *v25; // r14
  char *v26; // rax
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
  v12 = v10 >> 1;
  if ( v10 <= 0xFFFFFFFFFFFFFFFLL - (v10 >> 1) )
  {
    v14 = v10 + v12;
    v12 = v9;
    if ( v14 >= v9 )
      v12 = v14;
    if ( v12 > 0xFFFFFFFFFFFFFFFLL )
      __scrt_throw_std_bad_array_new_length();
    v4 = v12;
    v13 = 16 * v12;
    v32 = 16 * v12;
    if ( !(16 * v12) )
    {
      v15 = 0;
      goto LABEL_13;
    }
    if ( v13 < 0x1000 )
    {
      v16 = (char *)operator new(v13);
      goto LABEL_12;
    }
  }
  else
  {
    v13 = -16;
    v32 = -16;
  }
  v16 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v13, v12, a3, 0);
LABEL_12:
  v11 = 0;
  v15 = v16;
LABEL_13:
  v29[0] = a1;
  v29[2] = v4;
  v17 = (a2 - v3) >> 4;
  v18 = v15;
  v19 = &v15[16 * v17];
  v30 = v19;
  v31 = v19 + 16;
  *(_QWORD *)v19 = *a3;
  *((_QWORD *)v19 + 1) = a3[1];
  *a3 = 0;
  a3[1] = 0;
  v20 = a1[1];
  v21 = *a1;
  if ( a2 == v20 )
  {
    while ( v21 != v20 )
    {
      *(_QWORD *)v18 = *(_QWORD *)v21;
      v18 += 16;
      *((_QWORD *)v18 - 1) = *((_QWORD *)v21 + 1);
      *(_QWORD *)v21 = 0;
      *((_QWORD *)v21 + 1) = 0;
      v21 += 16;
    }
    v22 = 16 * v17;
  }
  else
  {
    while ( v21 != a2 )
    {
      *(_QWORD *)v18 = *(_QWORD *)v21;
      v18 += 16;
      *((_QWORD *)v18 - 1) = *((_QWORD *)v21 + 1);
      *(_QWORD *)v21 = 0;
      *((_QWORD *)v21 + 1) = 0;
      v21 += 16;
    }
    v18 = a1[1];
    v22 = 16 * v17;
    v30 = v15;
    v23 = &v15[v22 + 16];
    while ( a2 != v18 )
    {
      *(_QWORD *)v23 = *(_QWORD *)a2;
      v23 += 16;
      *((_QWORD *)v23 - 1) = *((_QWORD *)a2 + 1);
      *(_QWORD *)a2 = 0;
      *((_QWORD *)a2 + 1) = 0;
      a2 += 16;
    }
  }
  v24 = *a1;
  v29[1] = 0;
  if ( v24 )
  {
    v25 = a1[1];
    while ( v24 != v25 )
    {
      if ( *(_QWORD *)v24 )
      {
        CoTaskMemFree(*(LPVOID *)v24);
        *(_QWORD *)v24 = 0;
        *((_QWORD *)v24 + 1) = 0;
      }
      v24 += 16;
    }
    v26 = *a1;
    if ( ((a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL) < 0x1000 )
    {
      v27 = *a1;
    }
    else
    {
      v27 = (char *)*((_QWORD *)v26 - 1);
      if ( (unsigned __int64)(v26 - v27 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v27);
  }
  *a1 = v15;
  a1[1] = &v15[16 * v9];
  a1[2] = &v15[v32];
  ((void (__fastcall *)(_QWORD *, char *, char *, __int64))std::vector<wil::unique_any_array_ptr<unsigned char,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::_Reallocation_guard::~_Reallocation_guard)(
    v29,
    v18,
    v20,
    v11);
  return &v15[v22];
}

```

## disassembly

```asm
0x180021d84  push    rbx
0x180021d86  push    rbp
0x180021d87  push    rsi
0x180021d88  push    rdi
0x180021d89  push    r12
0x180021d8b  push    r13
0x180021d8d  push    r14
0x180021d8f  push    r15
0x180021d91  sub     rsp, 58h
0x180021d95  mov     r12, [rcx]
0x180021d98  mov     r14, 0FFFFFFFFFFFFFFFh
0x180021da2  mov     rax, [rcx+8]
0x180021da6  mov     r13, r8
0x180021da9  sub     rax, r12
0x180021dac  mov     rdi, rdx
0x180021daf  sar     rax, 4
0x180021db3  mov     rbx, rcx
0x180021db6  cmp     rax, r14
0x180021db9  jz      loc_180021FC7
0x180021dbf  mov     rcx, [rcx+10h]
0x180021dc3  lea     r15, [rax+1]
0x180021dc7  sub     rcx, r12
0x180021dca  mov     rax, r14
0x180021dcd  sar     rcx, 4
0x180021dd1  xor     r9d, r9d
0x180021dd4  mov     rdx, rcx
0x180021dd7  shr     rdx, 1
0x180021dda  sub     rax, rdx
0x180021ddd  cmp     rcx, rax
0x180021de0  jbe     short loc_180021DF0
0x180021de2  lea     rcx, [r9-10h]
0x180021de6  mov     [rsp+98h+arg_0], rcx
0x180021dee  jmp     short loc_180021E2C
0x180021df0  lea     rax, [rcx+rdx]
0x180021df4  mov     rdx, r15
0x180021df7  cmp     rax, r15
0x180021dfa  cmovnb  rdx, rax
0x180021dfe  cmp     rdx, r14
0x180021e01  ja      loc_180021FC1
0x180021e07  mov     rcx, rdx
0x180021e0a  mov     r14, rdx
0x180021e0d  shl     rcx, 4; Size
0x180021e11  mov     [rsp+98h+arg_0], rcx
0x180021e19  test    rcx, rcx
0x180021e1c  jnz     short loc_180021E23
0x180021e1e  mov     rbp, r9
0x180021e21  jmp     short loc_180021E3E
0x180021e23  cmp     rcx, 1000h
0x180021e2a  jb      short loc_180021E33
0x180021e2c  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x180021e31  jmp     short loc_180021E38
0x180021e33  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180021e38  xor     r9d, r9d
0x180021e3b  mov     rbp, rax
0x180021e3e  mov     rsi, rdi
0x180021e41  mov     [rsp+98h+var_78], rbx
0x180021e46  sub     rsi, r12
0x180021e49  mov     [rsp+98h+var_68], r14
0x180021e4e  sar     rsi, 4
0x180021e52  mov     rdx, rbp
0x180021e55  mov     rcx, rsi
0x180021e58  shl     rcx, 4
0x180021e5c  add     rcx, rbp
0x180021e5f  mov     [rsp+98h+var_60], rcx
0x180021e64  lea     rax, [rcx+10h]
0x180021e68  mov     [rsp+98h+var_58], rax
0x180021e6d  mov     rax, [r13+0]
0x180021e71  mov     [rcx], rax
0x180021e74  mov     rax, [r13+8]
0x180021e78  mov     [rcx+8], rax
0x180021e7c  mov     [r13+0], r9
0x180021e80  mov     [r13+8], r9
0x180021e84  mov     r8, [rbx+8]
0x180021e88  mov     rcx, [rbx]
0x180021e8b  cmp     rdi, r8
0x180021e8e  jnz     short loc_180021ED7
0x180021e90  jmp     short loc_180021EAF
0x180021e92  mov     rax, [rcx]
0x180021e95  mov     [rdx], rax
0x180021e98  lea     rdx, [rdx+10h]
0x180021e9c  mov     rax, [rcx+8]
0x180021ea0  mov     [rdx-8], rax
0x180021ea4  mov     [rcx], r9
0x180021ea7  mov     [rcx+8], r9
0x180021eab  add     rcx, 10h
0x180021eaf  cmp     rcx, r8
0x180021eb2  jnz     short loc_180021E92
0x180021eb4  shl     rsi, 4
0x180021eb8  jmp     short loc_180021F14
0x180021eba  mov     rax, [rcx]
0x180021ebd  mov     [rdx], rax
0x180021ec0  lea     rdx, [rdx+10h]
0x180021ec4  mov     rax, [rcx+8]
0x180021ec8  mov     [rdx-8], rax
0x180021ecc  mov     [rcx], r9
0x180021ecf  mov     [rcx+8], r9
0x180021ed3  add     rcx, 10h
0x180021ed7  cmp     rcx, rdi
0x180021eda  jnz     short loc_180021EBA
0x180021edc  mov     rdx, [rbx+8]
0x180021ee0  shl     rsi, 4
0x180021ee4  mov     [rsp+98h+var_60], rbp
0x180021ee9  lea     rcx, [rsi+10h]
0x180021eed  add     rcx, rbp
0x180021ef0  jmp     short loc_180021F0F
0x180021ef2  mov     rax, [rdi]
0x180021ef5  mov     [rcx], rax
0x180021ef8  lea     rcx, [rcx+10h]
0x180021efc  mov     rax, [rdi+8]
0x180021f00  mov     [rcx-8], rax
0x180021f04  mov     [rdi], r9
0x180021f07  mov     [rdi+8], r9
0x180021f0b  add     rdi, 10h
0x180021f0f  cmp     rdi, rdx
0x180021f12  jnz     short loc_180021EF2
0x180021f14  mov     rdi, [rbx]
0x180021f17  mov     [rsp+98h+var_70], r9
0x180021f1c  test    rdi, rdi
0x180021f1f  jz      short loc_180021F85
0x180021f21  mov     r14, [rbx+8]
0x180021f25  jmp     short loc_180021F43
0x180021f27  mov     rcx, [rdi]; pv
0x180021f2a  test    rcx, rcx
0x180021f2d  jz      short loc_180021F3F
0x180021f2f  call    cs:__imp_CoTaskMemFree
0x180021f35  xor     r9d, r9d
0x180021f38  mov     [rdi], r9
0x180021f3b  mov     [rdi+8], r9
0x180021f3f  add     rdi, 10h
0x180021f43  cmp     rdi, r14
0x180021f46  jnz     short loc_180021F27
0x180021f48  mov     rax, [rbx]
0x180021f4b  mov     rdx, [rbx+10h]
0x180021f4f  sub     rdx, rax
0x180021f52  and     rdx, 0FFFFFFFFFFFFFFF0h
0x180021f56  cmp     rdx, 1000h
0x180021f5d  jb      short loc_180021F7D
0x180021f5f  mov     rcx, [rax-8]
0x180021f63  sub     rax, rcx
0x180021f66  sub     rax, 8
0x180021f6a  cmp     rax, 1Fh
0x180021f6e  ja      short loc_180021F76
0x180021f70  add     rdx, 27h ; '''
0x180021f74  jmp     short loc_180021F80
0x180021f76  mov     ecx, 5
0x180021f7b  int     29h; Win8: RtlFailFast(ecx)
0x180021f7d  mov     rcx, rax; Block
0x180021f80  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180021f85  mov     rax, [rsp+98h+arg_0]
0x180021f8d  lea     rcx, [rsp+98h+var_78]
0x180021f92  mov     [rbx], rbp
0x180021f95  add     rax, rbp
0x180021f98  shl     r15, 4
0x180021f9c  add     r15, rbp
0x180021f9f  mov     [rbx+8], r15
0x180021fa3  mov     [rbx+10h], rax
0x180021fa7  call    ??1_Reallocation_guard@?$vector@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@V?$allocator@V?$unique_any_array_ptr@EU?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@Uempty_deleter@2@_K@wil@@@std@@@std@@QEAA@XZ; std::vector<wil::unique_any_array_ptr<uchar,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>,wil::empty_deleter,unsigned __int64>>::_Reallocation_guard::~_Reallocation_guard(void)
0x180021fac  lea     rax, [rsi+rbp]
0x180021fb0  add     rsp, 58h
0x180021fb4  pop     r15
0x180021fb6  pop     r14
0x180021fb8  pop     r13
0x180021fba  pop     r12
0x180021fbc  pop     rdi
0x180021fbd  pop     rsi
0x180021fbe  pop     rbp
0x180021fbf  pop     rbx
0x180021fc0  retn
0x180021fc1  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180021fc7  call    ?_Xlength@?$vector@EV?$allocator@E@std@@@std@@CAXXZ; std::vector<uchar>::_Xlength(void)
```
