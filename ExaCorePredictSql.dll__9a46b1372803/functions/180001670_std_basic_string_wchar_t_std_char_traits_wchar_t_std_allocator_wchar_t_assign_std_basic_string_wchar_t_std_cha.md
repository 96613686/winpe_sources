# std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>>::assign(std::basic_string<wchar_t,std::char_traits<wchar_t>,std::allocator<wchar_t>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180001670`
- end: `0x180001796`
- name: `?assign@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `294`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `2`
- callee_count: `6`
- tags: ``

## callers

- `0x180001520`
- `0x180002ac0`

## callees

- `0x180001670`
- `0x1800017a0`
- `0x1800017c0`
- `0x1800019b0`
- `0x180001ae0`
- `0x180004acc`

## pseudocode

```c
unsigned __int64 *__fastcall std::wstring::assign(
        unsigned __int64 *a1,
        unsigned __int64 *a2,
        unsigned __int64 a3,
        unsigned __int64 a4)
{
  unsigned __int64 v4; // rax
  unsigned __int64 v5; // rdi
  unsigned __int64 *v7; // rsi
  unsigned __int64 *v8; // rbx
  unsigned __int64 v9; // rax
  unsigned __int64 v10; // rcx
  unsigned __int64 v11; // rdx
  void *v12; // rcx
  bool v13; // cf
  unsigned __int64 v14; // rcx

  v4 = a2[2];
  v5 = a4;
  v7 = a2;
  v8 = a1;
  if ( v4 < a3 )
    std::wstring::_Xran(a1, a2, a3, a4);
  v9 = v4 - a3;
  if ( a4 > v9 )
    v5 = v9;
  if ( a1 == a2 )
  {
    v10 = a3 + v5;
    if ( v8[2] < a3 + v5 )
      std::wstring::_Xran(v10, a2, a3, a4);
    v8[2] = v10;
    if ( v8[3] < 8 )
      v11 = (unsigned __int64)v8;
    else
      v11 = *v8;
    *(_WORD *)(v11 + 2 * v10) = 0;
    std::wstring::erase(v8, 0, a3);
    return v8;
  }
  if ( v5 > 0x7FFFFFFFFFFFFFFELL )
    std::string::_Xlen(a1, a2);
  if ( a1[3] < v5 )
  {
    std::wstring::_Copy(a1, v5, a1[2]);
    if ( !v5 )
      return v8;
    goto LABEL_13;
  }
  if ( v5 )
  {
LABEL_13:
    if ( v7[3] >= 8 )
      v7 = (unsigned __int64 *)*v7;
    if ( v8[3] < 8 )
      v12 = v8;
    else
      v12 = (void *)*v8;
    memcpy_0(v12, (char *)v7 + 2 * a3, 2 * v5);
    v13 = v8[3] < 8;
    v8[2] = v5;
    if ( v13 )
      v14 = (unsigned __int64)v8;
    else
      v14 = *v8;
    *(_WORD *)(v14 + 2 * v5) = 0;
    return v8;
  }
  v13 = a1[3] < 8;
  a1[2] = 0;
  if ( !v13 )
    a1 = (unsigned __int64 *)*a1;
  *(_WORD *)a1 = 0;
  return v8;
}

```

## disassembly

```asm
0x180001670  mov     [rsp+arg_0], rbx
0x180001675  mov     [rsp+arg_8], rsi
0x18000167a  mov     [rsp+arg_10], rdi
0x18000167f  push    r14
0x180001681  sub     rsp, 20h
0x180001685  mov     rax, [rdx+10h]
0x180001689  mov     rdi, r9
0x18000168c  mov     r14, r8
0x18000168f  mov     rsi, rdx
0x180001692  mov     rbx, rcx
0x180001695  cmp     rax, r8
0x180001698  jb      loc_180001784
0x18000169e  sub     rax, r8
0x1800016a1  cmp     r9, rax
0x1800016a4  cmova   rdi, rax
0x1800016a8  cmp     rcx, rdx
0x1800016ab  jnz     short loc_1800016E3
0x1800016ad  lea     rcx, [r8+rdi]
0x1800016b1  cmp     [rbx+10h], rcx
0x1800016b5  jb      loc_18000178A
0x1800016bb  mov     [rbx+10h], rcx
0x1800016bf  cmp     qword ptr [rbx+18h], 8
0x1800016c4  jb      short loc_1800016CB
0x1800016c6  mov     rdx, [rbx]
0x1800016c9  jmp     short loc_1800016CE
0x1800016cb  mov     rdx, rbx
0x1800016ce  xor     eax, eax
0x1800016d0  mov     [rdx+rcx*2], ax
0x1800016d4  xor     edx, edx
0x1800016d6  mov     rcx, rbx
0x1800016d9  call    ?erase@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAAEAV12@_K0@Z; std::wstring::erase(unsigned __int64,unsigned __int64)
0x1800016de  jmp     loc_18000176B
0x1800016e3  mov     rax, 7FFFFFFFFFFFFFFEh
0x1800016ed  cmp     rdi, rax
0x1800016f0  ja      loc_180001790
0x1800016f6  cmp     [rcx+18h], rdi
0x1800016fa  jnb     short loc_180001723
0x1800016fc  mov     r8, [rcx+10h]
0x180001700  mov     rdx, rdi
0x180001703  call    ?_Copy@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180001708  test    rdi, rdi
0x18000170b  jz      short loc_18000176B
0x18000170d  cmp     qword ptr [rsi+18h], 8
0x180001712  jb      short loc_180001717
0x180001714  mov     rsi, [rsi]
0x180001717  cmp     qword ptr [rbx+18h], 8
0x18000171c  jb      short loc_18000173D
0x18000171e  mov     rcx, [rbx]
0x180001721  jmp     short loc_180001740
0x180001723  test    rdi, rdi
0x180001726  jnz     short loc_18000170D
0x180001728  xor     eax, eax
0x18000172a  cmp     qword ptr [rcx+18h], 8
0x18000172f  mov     [rcx+10h], rax
0x180001733  jb      short loc_180001738
0x180001735  mov     rcx, [rcx]
0x180001738  mov     [rcx], ax
0x18000173b  jmp     short loc_18000176B
0x18000173d  mov     rcx, rbx; void *
0x180001740  test    rdi, rdi
0x180001743  jz      short loc_180001752
0x180001745  lea     r8, [rdi+rdi]; Size
0x180001749  lea     rdx, [rsi+r14*2]; Src
0x18000174d  call    memcpy_0
0x180001752  cmp     qword ptr [rbx+18h], 8
0x180001757  mov     [rbx+10h], rdi
0x18000175b  jb      short loc_180001762
0x18000175d  mov     rcx, [rbx]
0x180001760  jmp     short loc_180001765
0x180001762  mov     rcx, rbx
0x180001765  xor     eax, eax
0x180001767  mov     [rcx+rdi*2], ax
0x18000176b  mov     rsi, [rsp+28h+arg_8]
0x180001770  mov     rax, rbx
0x180001773  mov     rbx, [rsp+28h+arg_0]
0x180001778  mov     rdi, [rsp+28h+arg_10]
0x18000177d  add     rsp, 20h
0x180001781  pop     r14
0x180001783  retn
0x180001784  call    ?_Xran@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x18000178a  call    ?_Xran@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x180001790  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
