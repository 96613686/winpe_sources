# std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::_Emplace_reallocate<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &>(winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo * const,winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &)

- ea: `0x18001f3f4`
- end: `0x18001f621`
- name: `??$_Emplace_reallocate@AEBUWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@AEAAPEAUWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@QEAU23456@AEBU23456@@Z`
- size: `557`
- prototype: ``
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001fb80`
- `0x1800213ac`

## callees

- `0x180002c74`
- `0x180002cac`
- `0x180017c3c`
- `0x18001888c`
- `0x18001da08`
- `0x18001f3f4`
- `0x180020e18`
- `0x18002c010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18001f608`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x18001f608`

## pseudocode

```c
// Hidden C++ exception states: #try_helpers=1
char *__fastcall std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Emplace_reallocate<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo const &>(
        __int64 **a1,
        __int64 *a2,
        __int64 *a3)
{
  __int64 *v4; // rdi
  signed __int64 v6; // r15
  __int64 v7; // rax
  unsigned __int64 v8; // rcx
  unsigned __int64 v9; // rdx
  unsigned __int64 v10; // r14
  size_t v11; // rcx
  __int64 *v12; // rbx
  unsigned __int64 v13; // r15
  __int64 v14; // rcx
  __int64 *v15; // r8
  __int64 *v16; // rcx
  __int64 *v17; // rdx
  __int64 v18; // rax
  __int64 v19; // rax
  __int64 *v20; // rcx
  char *v21; // rdx
  __int64 v22; // rax
  __int64 *v23; // rdi
  __int64 *v24; // r14
  __int64 *v25; // rcx
  unsigned __int64 v26; // rdx
  unsigned __int64 v27; // rdx
  __int64 *v28; // r8
  char *v29; // rcx
  __int64 v31; // [rsp+28h] [rbp-50h]
  __int64 v32; // [rsp+98h] [rbp+20h]

  v4 = a2;
  v6 = (char *)a2 - (char *)*a1;
  v7 = a1[1] - *a1;
  if ( v7 == 0x1FFFFFFFFFFFFFFFLL )
    goto LABEL_36;
  v31 = v7 + 1;
  v8 = a1[2] - *a1;
  v9 = v8 >> 1;
  if ( v8 > 0x1FFFFFFFFFFFFFFFLL - (v8 >> 1) )
  {
    v32 = 0x1FFFFFFFFFFFFFFFLL;
LABEL_8:
    v12 = (__int64 *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>();
    goto LABEL_12;
  }
  v10 = v7 + 1;
  if ( v9 + v8 >= v7 + 1 )
    v10 = v9 + v8;
  if ( v10 > 0x1FFFFFFFFFFFFFFFLL )
    __scrt_throw_std_bad_array_new_length();
  v11 = 8 * v10;
  v32 = v10;
  if ( 8 * v10 >= 0x1000 )
    goto LABEL_8;
  if ( v11 )
    v12 = (__int64 *)operator new(v11);
  else
    v12 = 0;
LABEL_12:
  v13 = v6 & 0xFFFFFFFFFFFFFFF8uLL;
  v14 = *a3;
  *(__int64 *)((char *)v12 + v13) = *a3;
  if ( v14 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v14 + 8LL))(v14);
  v15 = a1[1];
  v16 = *a1;
  v17 = v12;
  if ( v4 == v15 )
  {
    while ( v16 != v15 )
    {
      v18 = *v16;
      *v16 = 0;
      *v17++ = v18;
      ++v16;
    }
  }
  else
  {
    while ( v16 != v4 )
    {
      v19 = *v16;
      *v16 = 0;
      *v17++ = v19;
      ++v16;
    }
    v20 = a1[1];
    if ( v4 != v20 )
    {
      v21 = (char *)v12 + v13 - (_QWORD)v4;
      do
      {
        v22 = *v4;
        *v4 = 0;
        *(__int64 *)((char *)v4++ + (_QWORD)v21 + 8) = v22;
      }
      while ( v4 != v20 );
    }
  }
  v23 = *a1;
  if ( *a1 )
  {
    v24 = a1[1];
    while ( v23 != v24 )
    {
      if ( *v23 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v23);
      ++v23;
    }
    v25 = *a1;
    v26 = ((char *)a1[2] - (char *)*a1) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v26 < 0x1000 )
      goto LABEL_33;
    v27 = v26 + 39;
    v28 = (__int64 *)*(v25 - 1);
    v29 = (char *)((char *)v25 - (char *)v28);
    if ( (unsigned __int64)(v29 - 8) <= 0x1F )
    {
      v25 = v28;
LABEL_33:
      operator delete(v25);
      goto LABEL_34;
    }
    _o__invalid_parameter_noinfo_noreturn(v29, v27);
    __debugbreak();
LABEL_36:
    std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>::_Xlength(a1);
  }
LABEL_34:
  *a1 = v12;
  a1[1] = &v12[v31];
  a1[2] = &v12[v32];
  return (char *)v12 + v13;
}

```

## disassembly

```asm
0x18001f3f4  push    rbx
0x18001f3f6  push    rsi
0x18001f3f7  push    rdi
0x18001f3f8  push    r12
0x18001f3fa  push    r13
0x18001f3fc  push    r14
0x18001f3fe  push    r15
0x18001f400  sub     rsp, 40h
0x18001f404  mov     r12, r8
0x18001f407  mov     rdi, rdx
0x18001f40a  mov     rsi, rcx
0x18001f40d  mov     r15, rdx
0x18001f410  sub     r15, [rcx]
0x18001f413  mov     rax, [rcx+8]
0x18001f417  sub     rax, [rcx]
0x18001f41a  sar     rax, 3
0x18001f41e  mov     r9, 1FFFFFFFFFFFFFFFh
0x18001f428  cmp     rax, r9
0x18001f42b  jz      loc_18001F615
0x18001f431  lea     r8, [rax+1]
0x18001f435  mov     [rsp+78h+var_50], r8
0x18001f43a  mov     rcx, [rcx+10h]
0x18001f43e  sub     rcx, [rsi]
0x18001f441  sar     rcx, 3
0x18001f445  mov     rdx, rcx
0x18001f448  shr     rdx, 1
0x18001f44b  mov     rax, r9
0x18001f44e  sub     rax, rdx
0x18001f451  cmp     rcx, rax
0x18001f454  jbe     short loc_18001F46F
0x18001f456  mov     [rsp+78h+arg_0], r9
0x18001f45e  mov     rcx, 0FFFFFFFFFFFFFFF8h
0x18001f465  mov     [rsp+78h+arg_18], rcx
0x18001f46d  jmp     short loc_18001F4A7
0x18001f46f  lea     rax, [rdx+rcx]
0x18001f473  mov     r14, r8
0x18001f476  cmp     rax, r8
0x18001f479  cmovnb  r14, rax
0x18001f47d  cmp     r14, r9
0x18001f480  ja      loc_18001F61B
0x18001f486  lea     rcx, ds:0[r14*8]; Size
0x18001f48e  mov     [rsp+78h+arg_18], rcx
0x18001f496  mov     [rsp+78h+arg_0], r14
0x18001f49e  cmp     rcx, 1000h
0x18001f4a5  jb      short loc_18001F4B9
0x18001f4a7  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x18001f4ac  mov     rbx, rax
0x18001f4af  mov     [rsp+78h+arg_8], rax
0x18001f4b7  jmp     short loc_18001F4E2
0x18001f4b9  test    rcx, rcx
0x18001f4bc  jz      short loc_18001F4D0
0x18001f4be  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001f4c3  mov     rbx, rax
0x18001f4c6  mov     [rsp+78h+arg_8], rax
0x18001f4ce  jmp     short loc_18001F4DA
0x18001f4d0  xor     ebx, ebx
0x18001f4d2  mov     [rsp+78h+arg_8], rbx
0x18001f4da  mov     [rsp+78h+arg_0], r14
0x18001f4e2  and     r15, 0FFFFFFFFFFFFFFF8h
0x18001f4e6  lea     r13, [r15+rbx]
0x18001f4ea  lea     rax, [r13+8]
0x18001f4ee  mov     [rsp+78h+var_48], rax
0x18001f4f3  mov     rcx, [r12]
0x18001f4f7  mov     [r13+0], rcx
0x18001f4fb  test    rcx, rcx
0x18001f4fe  jz      short loc_18001F50C
0x18001f500  mov     rax, [rcx]
0x18001f503  mov     rax, [rax+8]
0x18001f507  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001f50c  mov     [rsp+78h+var_58], r13
0x18001f511  mov     r8, [rsi+8]
0x18001f515  mov     rcx, [rsi]
0x18001f518  mov     rdx, rbx
0x18001f51b  cmp     rdi, r8
0x18001f51e  jnz     short loc_18001F54D
0x18001f520  jmp     short loc_18001F534
0x18001f522  mov     rax, [rcx]
0x18001f525  and     qword ptr [rcx], 0
0x18001f529  mov     [rdx], rax
0x18001f52c  lea     rdx, [rdx+8]
0x18001f530  add     rcx, 8
0x18001f534  cmp     rcx, r8
0x18001f537  jnz     short loc_18001F522
0x18001f539  jmp     short loc_18001F57C
0x18001f53b  mov     rax, [rcx]
0x18001f53e  and     qword ptr [rcx], 0
0x18001f542  mov     [rdx], rax
0x18001f545  lea     rdx, [rdx+8]
0x18001f549  add     rcx, 8
0x18001f54d  cmp     rcx, rdi
0x18001f550  jnz     short loc_18001F53B
0x18001f552  mov     [rsp+78h+var_58], rbx
0x18001f557  mov     rcx, [rsi+8]
0x18001f55b  cmp     rdi, rcx
0x18001f55e  jz      short loc_18001F57C
0x18001f560  sub     r15, rdi
0x18001f563  lea     rdx, [r15+rbx]
0x18001f567  mov     rax, [rdi]
0x18001f56a  and     qword ptr [rdi], 0
0x18001f56e  mov     [rdx+rdi+8], rax
0x18001f573  add     rdi, 8
0x18001f577  cmp     rdi, rcx
0x18001f57a  jnz     short loc_18001F567
0x18001f57c  mov     rdi, [rsi]
0x18001f57f  test    rdi, rdi
0x18001f582  jz      short loc_18001F5D5
0x18001f584  mov     r14, [rsi+8]
0x18001f588  jmp     short loc_18001F59C
0x18001f58a  cmp     qword ptr [rdi], 0
0x18001f58e  jz      short loc_18001F598
0x18001f590  mov     rcx, rdi
0x18001f593  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001f598  add     rdi, 8
0x18001f59c  cmp     rdi, r14
0x18001f59f  jnz     short loc_18001F58A
0x18001f5a1  mov     rcx, [rsi]
0x18001f5a4  mov     rdx, [rsi+10h]
0x18001f5a8  sub     rdx, rcx
0x18001f5ab  and     rdx, 0FFFFFFFFFFFFFFF8h
0x18001f5af  cmp     rdx, 1000h
0x18001f5b6  jb      short loc_18001F5D0
0x18001f5b8  add     rdx, 27h ; '''; unsigned __int64
0x18001f5bc  mov     r8, [rcx-8]
0x18001f5c0  sub     rcx, r8
0x18001f5c3  lea     rax, [rcx-8]
0x18001f5c7  cmp     rax, 1Fh
0x18001f5cb  ja      short loc_18001F608
0x18001f5cd  mov     rcx, r8; void *
0x18001f5d0  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001f5d5  mov     [rsi], rbx
0x18001f5d8  mov     rax, [rsp+78h+var_50]
0x18001f5dd  lea     rcx, [rbx+rax*8]
0x18001f5e1  mov     [rsi+8], rcx
0x18001f5e5  mov     rcx, [rsp+78h+arg_18]
0x18001f5ed  add     rcx, rbx
0x18001f5f0  mov     [rsi+10h], rcx
0x18001f5f4  mov     rax, r13
0x18001f5f7  add     rsp, 40h
0x18001f5fb  pop     r15
0x18001f5fd  pop     r14
0x18001f5ff  pop     r13
0x18001f601  pop     r12
0x18001f603  pop     rdi
0x18001f604  pop     rsi
0x18001f605  pop     rbx
0x18001f606  retn
0x18001f608  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x18001f60f  nop     dword ptr [rax+rax+00h]
0x18001f614  int     3; Trap to Debugger
0x18001f615  call    ?_Xlength@?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@CAXXZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>::_Xlength(void)
0x18001f61b  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
