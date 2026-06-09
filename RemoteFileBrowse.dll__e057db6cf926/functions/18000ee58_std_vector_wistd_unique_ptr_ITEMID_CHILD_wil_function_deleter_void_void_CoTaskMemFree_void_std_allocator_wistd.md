# std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>,std::allocator<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>>::_Emplace_reallocate<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>(wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> * const,wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>> &&)

- ea: `0x18000ee58`
- end: `0x18000f096`
- name: `??$_Emplace_reallocate@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@?$vector@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@AEAAPEAV?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@QEAV23@$$QEAV23@@Z`
- size: `574`
- prototype: `void **__fastcall(void ***, void **, __int64 *)`
- caller_count: `2`
- callee_count: `6`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x18001116c`
- `0x1800132f0`

## callees

- `0x180002054`
- `0x18000208c`
- `0x1800072a8`
- `0x18000e134`
- `0x18000ee58`
- `0x18000ff40`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eff9`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000eff9`

## pseudocode

```c
// Hidden C++ exception states: #wind=7
void **__fastcall std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Emplace_reallocate<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>(
        void ***a1,
        void **a2,
        __int64 *a3)
{
  void **v3; // r12
  __int64 v6; // rdx
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // r8
  unsigned __int64 v10; // rbp
  unsigned __int64 v11; // r15
  void **v12; // rbx
  void *v13; // rax
  void *v14; // rax
  __int64 v15; // r14
  void **v16; // rdx
  void **v17; // r8
  void **v18; // rcx
  void **v19; // rdx
  void *v20; // rax
  __int64 v21; // r14
  void *v22; // rax
  void **v23; // rcx
  void *v24; // rax
  void **v25; // rsi
  void **v26; // rbp
  void *v27; // rcx
  void **v28; // rcx
  unsigned __int64 v29; // rdx
  void **v30; // rax
  _QWORD v32[3]; // [rsp+20h] [rbp-78h] BYREF
  void **v33; // [rsp+38h] [rbp-60h]
  _QWORD *v34; // [rsp+40h] [rbp-58h]
  __int64 v35; // [rsp+A0h] [rbp+8h]

  v3 = *a1;
  v6 = a1[1] - *a1;
  if ( v6 == 0x1FFFFFFFFFFFFFFFLL )
    std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Xlength();
  v8 = a1[2] - v3;
  v9 = v8 >> 1;
  if ( v8 > 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) )
    goto LABEL_37;
  v35 = v6 + 1;
  v10 = v6 + 1;
  if ( v8 + v9 >= v6 + 1 )
    v10 = v8 + v9;
  if ( v10 > 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_37;
  v11 = 8 * v10;
  if ( !(8 * v10) )
  {
    v12 = 0;
    goto LABEL_13;
  }
  if ( v11 < 0x1000 )
  {
    v12 = (void **)operator new(8 * v10);
    goto LABEL_13;
  }
  if ( v11 + 39 < v11 )
LABEL_37:
    __scrt_throw_std_bad_array_new_length();
  v13 = operator new(v11 + 39);
  if ( !v13 )
    goto LABEL_32;
  v12 = (void **)(((unsigned __int64)v13 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
  *(v12 - 1) = v13;
LABEL_13:
  v14 = (void *)*a3;
  *a3 = 0;
  v15 = a2 - v3;
  v32[0] = a1;
  v32[2] = v10;
  v16 = &v12[v15];
  *v16 = v14;
  v17 = a1[1];
  v34 = v16 + 1;
  v18 = *a1;
  v33 = v16;
  v19 = v12;
  if ( a2 == v17 )
  {
    while ( v18 != v17 )
    {
      v20 = *v18;
      *v18++ = 0;
      *v19++ = v20;
    }
    v21 = v15;
  }
  else
  {
    while ( v18 != a2 )
    {
      v22 = *v18;
      *v18++ = 0;
      *v19++ = v22;
    }
    v19 = a1[1];
    v21 = v15;
    v33 = v12;
    v23 = &v12[v21 + 1];
    while ( a2 != v19 )
    {
      v24 = *a2;
      *a2++ = 0;
      *v23++ = v24;
    }
  }
  v25 = *a1;
  v32[1] = 0;
  if ( v25 )
  {
    v26 = a1[1];
    while ( v25 != v26 )
    {
      v27 = *v25;
      *v25 = 0;
      if ( v27 )
        CoTaskMemFree(v27);
      ++v25;
    }
    v28 = *a1;
    v29 = 8 * (a1[2] - *a1);
    if ( v29 < 0x1000 )
    {
      v30 = *a1;
      goto LABEL_34;
    }
    v30 = (void **)*(v28 - 1);
    if ( (unsigned __int64)((char *)v28 - (char *)v30 - 8) <= 0x1F )
    {
      v29 += 39LL;
LABEL_34:
      operator delete(v30, v29);
      goto LABEL_35;
    }
LABEL_32:
    __fastfail(5u);
  }
LABEL_35:
  *a1 = v12;
  a1[1] = &v12[v35];
  a1[2] = &v12[v11 / 8];
  std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&void CoTaskMemFree(void *)>>>::_Reallocation_guard::~_Reallocation_guard(
    v32,
    v19);
  return &v12[v21];
}

```

## disassembly

```asm
0x18000ee58  push    rbx
0x18000ee5a  push    rbp
0x18000ee5b  push    rsi
0x18000ee5c  push    rdi
0x18000ee5d  push    r12
0x18000ee5f  push    r13
0x18000ee61  push    r14
0x18000ee63  push    r15
0x18000ee65  sub     rsp, 58h
0x18000ee69  mov     r12, [rcx]
0x18000ee6c  mov     rsi, rdx
0x18000ee6f  mov     rdx, [rcx+8]
0x18000ee73  mov     r9, 1FFFFFFFFFFFFFFFh
0x18000ee7d  sub     rdx, r12
0x18000ee80  mov     r13, r8
0x18000ee83  sar     rdx, 3
0x18000ee87  mov     rdi, rcx
0x18000ee8a  cmp     rdx, r9
0x18000ee8d  jz      loc_18000F08A
0x18000ee93  mov     rcx, [rcx+10h]
0x18000ee97  mov     rax, r9
0x18000ee9a  sub     rcx, r12
0x18000ee9d  sar     rcx, 3
0x18000eea1  mov     r8, rcx
0x18000eea4  shr     r8, 1
0x18000eea7  sub     rax, r8
0x18000eeaa  cmp     rcx, rax
0x18000eead  ja      loc_18000F090
0x18000eeb3  inc     rdx
0x18000eeb6  lea     rax, [rcx+r8]
0x18000eeba  cmp     rax, rdx
0x18000eebd  mov     [rsp+98h+arg_0], rdx
0x18000eec5  mov     rbp, rdx
0x18000eec8  cmovnb  rbp, rax
0x18000eecc  cmp     rbp, r9
0x18000eecf  ja      loc_18000F090
0x18000eed5  lea     r15, ds:0[rbp*8]
0x18000eedd  test    r15, r15
0x18000eee0  jnz     short loc_18000EEE6
0x18000eee2  xor     ebx, ebx
0x18000eee4  jmp     short loc_18000EF23
0x18000eee6  cmp     r15, 1000h
0x18000eeed  jb      short loc_18000EF18
0x18000eeef  lea     rcx, [r15+27h]; Size
0x18000eef3  cmp     rcx, r15
0x18000eef6  jbe     loc_18000F090
0x18000eefc  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ef01  test    rax, rax
0x18000ef04  jz      loc_18000F03E
0x18000ef0a  lea     rbx, [rax+27h]
0x18000ef0e  and     rbx, 0FFFFFFFFFFFFFFE0h
0x18000ef12  mov     [rbx-8], rax
0x18000ef16  jmp     short loc_18000EF23
0x18000ef18  mov     rcx, r15; Size
0x18000ef1b  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000ef20  mov     rbx, rax
0x18000ef23  mov     rax, [r13+0]
0x18000ef27  mov     r14, rsi
0x18000ef2a  mov     qword ptr [r13+0], 0
0x18000ef32  sub     r14, r12
0x18000ef35  sar     r14, 3
0x18000ef39  mov     [rsp+98h+var_78], rdi
0x18000ef3e  mov     [rsp+98h+var_68], rbp
0x18000ef43  lea     rdx, [rbx+r14*8]
0x18000ef47  mov     [rdx], rax
0x18000ef4a  lea     rcx, [rdx+8]
0x18000ef4e  mov     r8, [rdi+8]
0x18000ef52  mov     [rsp+98h+var_58], rcx
0x18000ef57  mov     rcx, [rdi]
0x18000ef5a  mov     [rsp+98h+var_60], rdx
0x18000ef5f  mov     rdx, rbx
0x18000ef62  cmp     rsi, r8
0x18000ef65  jnz     short loc_18000EF9E
0x18000ef67  jmp     short loc_18000EF7E
0x18000ef69  mov     rax, [rcx]
0x18000ef6c  mov     qword ptr [rcx], 0
0x18000ef73  add     rcx, 8
0x18000ef77  mov     [rdx], rax
0x18000ef7a  lea     rdx, [rdx+8]
0x18000ef7e  cmp     rcx, r8
0x18000ef81  jnz     short loc_18000EF69
0x18000ef83  shl     r14, 3
0x18000ef87  jmp     short loc_18000EFD3
0x18000ef89  mov     rax, [rcx]
0x18000ef8c  mov     qword ptr [rcx], 0
0x18000ef93  add     rcx, 8
0x18000ef97  mov     [rdx], rax
0x18000ef9a  lea     rdx, [rdx+8]
0x18000ef9e  cmp     rcx, rsi
0x18000efa1  jnz     short loc_18000EF89
0x18000efa3  mov     rdx, [rdi+8]
0x18000efa7  shl     r14, 3
0x18000efab  mov     [rsp+98h+var_60], rbx
0x18000efb0  lea     rcx, [r14+8]
0x18000efb4  add     rcx, rbx
0x18000efb7  jmp     short loc_18000EFCE
0x18000efb9  mov     rax, [rsi]
0x18000efbc  mov     qword ptr [rsi], 0
0x18000efc3  add     rsi, 8
0x18000efc7  mov     [rcx], rax
0x18000efca  lea     rcx, [rcx+8]
0x18000efce  cmp     rsi, rdx
0x18000efd1  jnz     short loc_18000EFB9
0x18000efd3  mov     rsi, [rdi]
0x18000efd6  mov     [rsp+98h+var_70], 0
0x18000efdf  test    rsi, rsi
0x18000efe2  jz      short loc_18000F050
0x18000efe4  mov     rbp, [rdi+8]
0x18000efe8  jmp     short loc_18000F003
0x18000efea  mov     rcx, [rsi]; pv
0x18000efed  mov     qword ptr [rsi], 0
0x18000eff4  test    rcx, rcx
0x18000eff7  jz      short loc_18000EFFF
0x18000eff9  call    cs:__imp_CoTaskMemFree
0x18000efff  add     rsi, 8
0x18000f003  cmp     rsi, rbp
0x18000f006  jnz     short loc_18000EFEA
0x18000f008  mov     rcx, [rdi]
0x18000f00b  mov     rax, [rdi+10h]
0x18000f00f  sub     rax, rcx
0x18000f012  sar     rax, 3
0x18000f016  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18000f01e  cmp     rdx, 1000h
0x18000f025  jb      short loc_18000F045
0x18000f027  mov     rax, [rcx-8]
0x18000f02b  sub     rcx, rax
0x18000f02e  sub     rcx, 8
0x18000f032  cmp     rcx, 1Fh
0x18000f036  ja      short loc_18000F03E
0x18000f038  add     rdx, 27h ; '''
0x18000f03c  jmp     short loc_18000F048
0x18000f03e  mov     ecx, 5
0x18000f043  int     29h; Win8: RtlFailFast(ecx)
0x18000f045  mov     rax, rcx
0x18000f048  mov     rcx, rax; void *
0x18000f04b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f050  mov     rax, [rsp+98h+arg_0]
0x18000f058  lea     rcx, [rsp+98h+var_78]
0x18000f05d  mov     [rdi], rbx
0x18000f060  lea     rax, [rbx+rax*8]
0x18000f064  mov     [rdi+8], rax
0x18000f068  lea     rax, [r15+rbx]
0x18000f06c  mov     [rdi+10h], rax
0x18000f070  call    ??1_Reallocation_guard@?$vector@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@QEAA@XZ; std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Reallocation_guard::~_Reallocation_guard(void)
0x18000f075  lea     rax, [r14+rbx]
0x18000f079  add     rsp, 58h
0x18000f07d  pop     r15
0x18000f07f  pop     r14
0x18000f081  pop     r13
0x18000f083  pop     r12
0x18000f085  pop     rdi
0x18000f086  pop     rsi
0x18000f087  pop     rbp
0x18000f088  pop     rbx
0x18000f089  retn
0x18000f08a  call    ?_Xlength@?$vector@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@V?$allocator@V?$unique_ptr@U_ITEMID_CHILD@@U?$function_deleter@P6AXPEAX@Z$1?CoTaskMemFree@@YAX0@Z@wil@@@wistd@@@std@@@std@@CAXXZ; std::vector<wistd::unique_ptr<_ITEMID_CHILD,wil::function_deleter<void (*)(void *),&CoTaskMemFree(void *)>>>::_Xlength(void)
0x18000f090  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
