# std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo,std::allocator<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>>::_Clear_and_reserve_geometric(unsigned __int64)

- ea: `0x18001f9b0`
- end: `0x18001fad4`
- name: `?_Clear_and_reserve_geometric@?$vector@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdateLocalizationInfo@Update@Management@Windows@winrt@@@std@@@std@@AEAAX_K@Z`
- size: `292`
- prototype: `char *__fastcall(__int64, unsigned __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x18001f690`

## callees

- `0x180002cc0`
- `0x180002cfc`
- `0x180016fe4`
- `0x180017bac`
- `0x18001c7f4`
- `0x18001f9b0`
- `0x18001fadc`

## pseudocode

```c
char *__fastcall std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdateLocalizationInfo>::_Clear_and_reserve_geometric(
        __int64 a1,
        unsigned __int64 a2)
{
  char *v3; // rdi
  unsigned __int64 v4; // rcx
  unsigned __int64 v5; // r8
  unsigned __int64 v6; // rsi
  char *v7; // rbp
  char *v8; // rcx
  char *v9; // rax
  unsigned __int64 v10; // rdi
  char *v11; // rax
  size_t v12; // rcx
  char *result; // rax

  if ( a2 > 0x1FFFFFFFFFFFFFFFLL )
    std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>::_Xlength();
  v3 = *(char **)a1;
  v4 = (__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3;
  v5 = v4 >> 1;
  if ( v4 <= 0x1FFFFFFFFFFFFFFFLL - (v4 >> 1) )
  {
    v6 = v4 + v5;
    if ( v4 + v5 < a2 )
      v6 = a2;
  }
  else
  {
    v6 = 0x1FFFFFFFFFFFFFFFLL;
  }
  if ( v3 )
  {
    v7 = *(char **)(a1 + 8);
    while ( v3 != v7 )
    {
      if ( *(_QWORD *)v3 )
        winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(v3);
      v3 += 8;
    }
    v8 = *(char **)a1;
    if ( (unsigned __int64)(8 * ((__int64)(*(_QWORD *)(a1 + 16) - *(_QWORD *)a1) >> 3)) < 0x1000 )
    {
      v9 = *(char **)a1;
    }
    else
    {
      v9 = (char *)*((_QWORD *)v8 - 1);
      if ( (unsigned __int64)(v8 - v9 - 8) > 0x1F )
        __fastfail(5u);
    }
    operator delete(v9);
    *(_QWORD *)a1 = 0;
    *(_QWORD *)(a1 + 8) = 0;
    *(_QWORD *)(a1 + 16) = 0;
  }
  if ( v6 > 0x1FFFFFFFFFFFFFFFLL )
    __scrt_throw_std_bad_array_new_length();
  v10 = 8 * v6;
  if ( 8 * v6 )
  {
    v12 = 8 * v6;
    if ( v10 < 0x1000 )
      v11 = (char *)operator new(v12);
    else
      v11 = (char *)std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(v12);
  }
  else
  {
    v11 = 0;
  }
  *(_QWORD *)a1 = v11;
  *(_QWORD *)(a1 + 8) = v11;
  result = &v11[v10];
  *(_QWORD *)(a1 + 16) = result;
  return result;
}

```

## disassembly

```asm
0x18001f9b0  push    rbx
0x18001f9b2  push    rbp
0x18001f9b3  push    rsi
0x18001f9b4  push    rdi
0x18001f9b5  push    r15
0x18001f9b7  sub     rsp, 20h
0x18001f9bb  mov     r15, 1FFFFFFFFFFFFFFFh
0x18001f9c5  mov     rbx, rcx
0x18001f9c8  cmp     rdx, r15
0x18001f9cb  ja      loc_18001FACE
0x18001f9d1  mov     rdi, [rcx]
0x18001f9d4  mov     rax, r15
0x18001f9d7  mov     rcx, [rcx+10h]
0x18001f9db  sub     rcx, rdi
0x18001f9de  sar     rcx, 3
0x18001f9e2  mov     r8, rcx
0x18001f9e5  shr     r8, 1
0x18001f9e8  sub     rax, r8
0x18001f9eb  cmp     rcx, rax
0x18001f9ee  jbe     short loc_18001F9F5
0x18001f9f0  mov     rsi, r15
0x18001f9f3  jmp     short loc_18001FA00
0x18001f9f5  lea     rsi, [rcx+r8]
0x18001f9f9  cmp     rsi, rdx
0x18001f9fc  cmovb   rsi, rdx
0x18001fa00  test    rdi, rdi
0x18001fa03  jz      short loc_18001FA81
0x18001fa05  mov     rbp, [rbx+8]
0x18001fa09  jmp     short loc_18001FA1D
0x18001fa0b  cmp     qword ptr [rdi], 0
0x18001fa0f  jz      short loc_18001FA19
0x18001fa11  mov     rcx, rdi
0x18001fa14  call    ?unconditional_release_ref@?$com_ptr@Utype@?$abi@UIUnknown@Foundation@Windows@winrt@@X@impl@winrt@@@winrt@@AEAAXXZ; winrt::com_ptr<winrt::impl::abi<winrt::Windows::Foundation::IUnknown,void>::type>::unconditional_release_ref(void)
0x18001fa19  add     rdi, 8
0x18001fa1d  cmp     rdi, rbp
0x18001fa20  jnz     short loc_18001FA0B
0x18001fa22  mov     rcx, [rbx]
0x18001fa25  mov     rax, [rbx+10h]
0x18001fa29  sub     rax, rcx
0x18001fa2c  sar     rax, 3
0x18001fa30  lea     rdx, ds:0[rax*8]; unsigned __int64
0x18001fa38  cmp     rdx, 1000h
0x18001fa3f  jb      short loc_18001FA5F
0x18001fa41  mov     rax, [rcx-8]
0x18001fa45  sub     rcx, rax
0x18001fa48  sub     rcx, 8
0x18001fa4c  cmp     rcx, 1Fh
0x18001fa50  ja      short loc_18001FA58
0x18001fa52  add     rdx, 27h ; '''
0x18001fa56  jmp     short loc_18001FA62
0x18001fa58  mov     ecx, 5
0x18001fa5d  int     29h; Win8: RtlFailFast(ecx)
0x18001fa5f  mov     rax, rcx
0x18001fa62  mov     rcx, rax; void *
0x18001fa65  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18001fa6a  mov     qword ptr [rbx], 0
0x18001fa71  mov     qword ptr [rbx+8], 0
0x18001fa79  mov     qword ptr [rbx+10h], 0
0x18001fa81  cmp     rsi, r15
0x18001fa84  ja      short loc_18001FAC8
0x18001fa86  lea     rdi, ds:0[rsi*8]
0x18001fa8e  test    rdi, rdi
0x18001fa91  jnz     short loc_18001FA97
0x18001fa93  xor     eax, eax
0x18001fa95  jmp     short loc_18001FAAF
0x18001fa97  mov     rcx, rdi; Size
0x18001fa9a  cmp     rdi, 1000h
0x18001faa1  jb      short loc_18001FAAA
0x18001faa3  call    ??$_Allocate_manually_vector_aligned@U_Default_allocate_traits@std@@@std@@YAPEAX_K@Z; std::_Allocate_manually_vector_aligned<std::_Default_allocate_traits>(unsigned __int64)
0x18001faa8  jmp     short loc_18001FAAF
0x18001faaa  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18001faaf  mov     [rbx], rax
0x18001fab2  mov     [rbx+8], rax
0x18001fab6  add     rax, rdi
0x18001fab9  mov     [rbx+10h], rax
0x18001fabd  add     rsp, 20h
0x18001fac1  pop     r15
0x18001fac3  pop     rdi
0x18001fac4  pop     rsi
0x18001fac5  pop     rbp
0x18001fac6  pop     rbx
0x18001fac7  retn
0x18001fac8  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
0x18001face  call    ?_Xlength@?$vector@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@V?$allocator@UWindowsSoftwareUpdate@Update@Management@Windows@winrt@@@std@@@std@@CAXXZ; std::vector<winrt::Windows::Management::Update::WindowsSoftwareUpdate>::_Xlength(void)
```
