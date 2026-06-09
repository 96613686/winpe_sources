# std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70>::assign(std::basic_string<char,std::char_traits<char>,std::allocator<char>,_STL70> const &,unsigned __int64,unsigned __int64)

- ea: `0x180001760`
- end: `0x180001848`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `232`
- prototype: ``
- caller_count: `6`
- callee_count: `6`
- tags: ``

## callers

- `0x1800010e4`
- `0x18000115c`
- `0x1800011d4`
- `0x180001240`
- `0x1800012b8`
- `0x180001850`

## callees

- `0x180001444`
- `0x1800016a4`
- `0x180001700`
- `0x180001760`
- `0x180001934`
- `0x180001f12`

## pseudocode

```c
__int64 __fastcall std::string::assign(__int64 a1, _QWORD *a2, unsigned __int64 a3, unsigned __int64 a4)
{
  unsigned __int64 v4; // rbx
  unsigned __int64 v8; // rbx
  _QWORD *v9; // rax
  rsize_t v10; // rdx
  void **v11; // rsi
  void *v12; // rcx
  _QWORD *v13; // rax

  v4 = a2[3];
  if ( v4 < a3 )
    std::_String_base::_Xran();
  v8 = v4 - a3;
  if ( a4 < v8 )
    v8 = a4;
  if ( (_QWORD *)a1 == a2 )
  {
    std::string::erase(a1, v8 + a3, -1);
    std::string::erase(a1, 0, a3);
    return a1;
  }
  if ( v8 == -1 )
    std::_String_base::_Xlen();
  if ( *(_QWORD *)(a1 + 32) < v8 )
  {
    std::string::_Copy(a1, v8, *(_QWORD *)(a1 + 24));
    if ( !v8 )
      return a1;
    goto LABEL_9;
  }
  if ( v8 )
  {
LABEL_9:
    v9 = a2 + 1;
    if ( a2[4] >= 0x10u )
      v9 = (_QWORD *)*v9;
    v10 = *(_QWORD *)(a1 + 32);
    v11 = (void **)(a1 + 8);
    if ( v10 < 0x10 )
      v12 = (void *)(a1 + 8);
    else
      v12 = *v11;
    memcpy_s_0(v12, v10, (char *)v9 + a3, v8);
    if ( *(_QWORD *)(a1 + 32) >= 0x10u )
      v11 = (void **)*v11;
    *(_QWORD *)(a1 + 24) = v8;
    *((_BYTE *)v11 + v8) = 0;
    return a1;
  }
  v13 = (_QWORD *)(a1 + 8);
  if ( *(_QWORD *)(a1 + 32) >= 0x10u )
    v13 = (_QWORD *)*v13;
  *(_QWORD *)(a1 + 24) = 0;
  *(_BYTE *)v13 = 0;
  return a1;
}

```

## disassembly

```asm
0x180001760  push    rbx
0x180001762  push    rbp
0x180001763  push    rsi
0x180001764  push    rdi
0x180001765  sub     rsp, 28h
0x180001769  mov     rbx, [rdx+18h]
0x18000176d  mov     rbp, r8
0x180001770  mov     rsi, rdx
0x180001773  mov     rdi, rcx
0x180001776  cmp     rbx, r8
0x180001779  jb      loc_18000183C
0x18000177f  sub     rbx, r8
0x180001782  cmp     r9, rbx
0x180001785  cmovb   rbx, r9
0x180001789  cmp     rcx, rdx
0x18000178c  jnz     short loc_1800017AD
0x18000178e  lea     rdx, [rbx+r8]
0x180001792  or      r8, 0FFFFFFFFFFFFFFFFh
0x180001796  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x18000179b  mov     r8, rbp
0x18000179e  xor     edx, edx
0x1800017a0  mov     rcx, rdi
0x1800017a3  call    ?erase@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@QEAAAEAV12@_K0@Z; std::string::erase(unsigned __int64,unsigned __int64)
0x1800017a8  jmp     loc_180001830
0x1800017ad  cmp     rbx, 0FFFFFFFFFFFFFFFEh
0x1800017b1  ja      loc_180001842
0x1800017b7  cmp     [rcx+20h], rbx
0x1800017bb  jnb     short loc_1800017EF
0x1800017bd  mov     r8, [rcx+18h]
0x1800017c1  mov     rdx, rbx
0x1800017c4  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@V_STL70@@@std@@IEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800017c9  test    rbx, rbx
0x1800017cc  jz      short loc_180001830
0x1800017ce  cmp     qword ptr [rsi+20h], 10h
0x1800017d3  lea     rax, [rsi+8]
0x1800017d7  jb      short loc_1800017DC
0x1800017d9  mov     rax, [rax]
0x1800017dc  mov     rdx, [rdi+20h]; DestinationSize
0x1800017e0  lea     rsi, [rdi+8]
0x1800017e4  cmp     rdx, 10h
0x1800017e8  jb      short loc_18000180F
0x1800017ea  mov     rcx, [rsi]
0x1800017ed  jmp     short loc_180001812
0x1800017ef  test    rbx, rbx
0x1800017f2  jnz     short loc_1800017CE
0x1800017f4  cmp     qword ptr [rcx+20h], 10h
0x1800017f9  lea     rax, [rcx+8]
0x1800017fd  jb      short loc_180001802
0x1800017ff  mov     rax, [rax]
0x180001802  mov     qword ptr [rcx+18h], 0
0x18000180a  mov     byte ptr [rax], 0
0x18000180d  jmp     short loc_180001830
0x18000180f  mov     rcx, rsi; Destination
0x180001812  lea     r8, [rax+rbp]; Source
0x180001816  mov     r9, rbx; SourceSize
0x180001819  call    memcpy_s_0
0x18000181e  cmp     qword ptr [rdi+20h], 10h
0x180001823  jb      short loc_180001828
0x180001825  mov     rsi, [rsi]
0x180001828  mov     [rdi+18h], rbx
0x18000182c  mov     byte ptr [rsi+rbx], 0
0x180001830  mov     rax, rdi
0x180001833  add     rsp, 28h
0x180001837  pop     rdi
0x180001838  pop     rsi
0x180001839  pop     rbp
0x18000183a  pop     rbx
0x18000183b  retn
0x18000183c  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180001842  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
```
