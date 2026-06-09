# std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::_Clear_and_reserve_geometric(unsigned __int64)

- ea: `0x180020cdc`
- end: `0x180020e10`
- name: `?_Clear_and_reserve_geometric@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@AEAAX_K@Z`
- size: `308`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x1800209b0`

## callees

- `0x180002c74`
- `0x180002cac`
- `0x180017c3c`
- `0x18001888c`
- `0x18001da08`
- `0x180020cdc`
- `0x180020e18`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180020dbe`
- `api-ms-win-crt-private-l1-1-0!_o__invalid_parameter_noinfo_noreturn` at `0x180020dbe`

## pseudocode

```c
char *__fastcall std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Clear_and_reserve_geometric(
        __int64 a1,
        unsigned __int64 a2)
{
  unsigned __int64 v2; // r8
  __int64 *v4; // rdi
  unsigned __int64 v5; // rcx
  unsigned __int64 v6; // rdx
  unsigned __int64 v7; // rbp
  char *v8; // rbx
  __int64 *v9; // r14
  __int64 *v10; // rcx
  unsigned __int64 v11; // rdx
  __int64 *v12; // r8
  unsigned __int64 v13; // rdx
  char *v14; // rcx
  char *v15; // rax
  char *result; // rax

  v2 = a2;
  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>::_Xlength(a1);
  v4 = *(__int64 **)a1;
  v5 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3;
  v6 = v5 >> 1;
  if ( v5 <= 0x1FFFFFFFFFFFFFFFLL - (v5 >> 1) )
  {
    v7 = v6 + v5;
    if ( v6 + v5 < v2 )
      v7 = v2;
  }
  else
  {
    v7 = 0x1FFFFFFFFFFFFFFFLL;
  }
  v8 = 0;
  if ( v4 )
  {
    v9 = *(__int64 **)(a1 + 8);
    while ( v4 != v9 )
    {
      if ( *v4 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v4);
      ++v4;
    }
    v10 = *(__int64 **)a1;
    v11 = (*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) & 0xFFFFFFFFFFFFFFF8uLL;
    if ( v11 >= 0x1000 )
    {
      v12 = (__int64 *)*(v10 - 1);
      v13 = v11 + 39;
      v14 = (char *)((char *)v10 - (char *)v12);
      if ( (unsigned __int64)(v14 - 8) > 0x1F )
      {
        _o__invalid_parameter_noinfo_noreturn(v14, v13);
        __debugbreak();
        goto LABEL_20;
      }
      v10 = v12;
    }
    operator delete(v10);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
  if ( v7 > 0x1FFFFFFFFFFFFFFFLL )
    __scrt_throw_std_bad_array_new_length();
  v4 = (__int64 *)(8 * v7);
  if ( 8 * v7 >= 0x1000 )
  {
    v15 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(8 * v7, v6, v2);
LABEL_22:
    v8 = v15;
    goto LABEL_23;
  }
LABEL_20:
  if ( v4 )
  {
    v15 = (char *)operator new((size_t)v4);
    goto LABEL_22;
  }
LABEL_23:
  result = &v8[(_QWORD)v4];
  *(_QWORD *)a1 = v8;
  *(_QWORD *)(a1 + 8) = v8;
  *(_QWORD *)(a1 + 16) = &v8[(_QWORD)v4];
  return result;
}

```

## disassembly

```asm
0x180020cdc  mov     [rsp+arg_0], rbx
0x180020ce1  mov     [rsp+arg_8], rbp
0x180020ce6  mov     [rsp+arg_10], rsi
0x180020ceb  push    rdi
0x180020cec  push    r14
0x180020cee  push    r15
0x180020cf0  sub     rsp, 20h
0x180020cf4  mov     r15, 1FFFFFFFFFFFFFFFh
0x180020cfe  mov     r8, rdx
0x180020d01  mov     rsi, rcx
0x180020d04  cmp     rdx, r15
0x180020d07  ja      loc_180020E0A
0x180020d0d  mov     rdi, [rcx]
0x180020d10  mov     rax, r15
0x180020d13  mov     rcx, [rcx+10h]
0x180020d17  sub     rcx, rdi
0x180020d1a  sar     rcx, 3
0x180020d1e  mov     rdx, rcx
0x180020d21  shr     rdx, 1
0x180020d24  sub     rax, rdx
0x180020d27  cmp     rcx, rax
0x180020d2a  jbe     short loc_180020D31
0x180020d2c  mov     rbp, r15
0x180020d2f  jmp     short loc_180020D3C
0x180020d31  lea     rbp, [rdx+rcx]
0x180020d35  cmp     rbp, r8
0x180020d38  cmovb   rbp, r8
0x180020d3c  xor     ebx, ebx
0x180020d3e  test    rdi, rdi
0x180020d41  jz      short loc_180020D9E
0x180020d43  mov     r14, [rsi+8]
0x180020d47  jmp     short loc_180020D5A
0x180020d49  cmp     [rdi], rbx
0x180020d4c  jz      short loc_180020D56
0x180020d4e  mov     rcx, rdi
0x180020d51  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x180020d56  add     rdi, 8
0x180020d5a  cmp     rdi, r14
0x180020d5d  jnz     short loc_180020D49
0x180020d5f  mov     rcx, [rsi]
0x180020d62  mov     rdx, [rsi+10h]
0x180020d66  sub     rdx, rcx
0x180020d69  and     rdx, 0FFFFFFFFFFFFFFF8h
0x180020d6d  cmp     rdx, 1000h
0x180020d74  jb      short loc_180020D8E
0x180020d76  mov     r8, [rcx-8]
0x180020d7a  add     rdx, 27h ; '''; unsigned __int64
0x180020d7e  sub     rcx, r8
0x180020d81  lea     rax, [rcx-8]
0x180020d85  cmp     rax, 1Fh
0x180020d89  ja      short loc_180020DBE
0x180020d8b  mov     rcx, r8; void *
0x180020d8e  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180020d93  mov     [rsi], rbx
0x180020d96  mov     [rsi+8], rbx
0x180020d9a  mov     [rsi+10h], rbx
0x180020d9e  cmp     rbp, r15
0x180020da1  ja      short loc_180020E04
0x180020da3  lea     rdi, ds:0[rbp*8]
0x180020dab  cmp     rdi, 1000h
0x180020db2  jb      short loc_180020DCB
0x180020db4  mov     rcx, rdi
0x180020db7  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x180020dbc  jmp     short loc_180020DD8
0x180020dbe  call    cs:__imp__o__invalid_parameter_noinfo_noreturn
0x180020dc5  nop     dword ptr [rax+rax+00h]
0x180020dca  int     3; Trap to Debugger
0x180020dcb  test    rdi, rdi
0x180020dce  jz      short loc_180020DDB
0x180020dd0  mov     rcx, rdi; Size
0x180020dd3  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180020dd8  mov     rbx, rax
0x180020ddb  mov     rbp, [rsp+38h+arg_8]
0x180020de0  lea     rax, [rdi+rbx]
0x180020de4  mov     [rsi], rbx
0x180020de7  mov     [rsi+8], rbx
0x180020deb  mov     rbx, [rsp+38h+arg_0]
0x180020df0  mov     [rsi+10h], rax
0x180020df4  mov     rsi, [rsp+38h+arg_10]
0x180020df9  add     rsp, 20h
0x180020dfd  pop     r15
0x180020dff  pop     r14
0x180020e01  pop     rdi
0x180020e02  retn
0x180020e04  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x180020e0a  call    ?_Xlength@?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@CAXXZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>::_Xlength(void)
```
