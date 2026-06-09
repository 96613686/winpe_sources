# UserLanguages::RemoveDuplicateAndProhibitedRelatedUserLanguages(std::vector<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>,std::allocator<std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>>> &,bool)

- ea: `0x18000e73c`
- end: `0x18000e839`
- name: `?RemoveDuplicateAndProhibitedRelatedUserLanguages@UserLanguages@@AEAAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@_N@Z`
- size: `253`
- prototype: `__int64 __fastcall(__int64, char **)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path`

## callers

- `0x18000e6ac`

## callees

- `0x180004c88`
- `0x18000e73c`
- `0x180010dd0`
- `0x18001e5ec`
- `0x180022584`
- `0x1800227c0`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall UserLanguages::RemoveDuplicateAndProhibitedRelatedUserLanguages(__int64 a1, char **a2)
{
  __int64 v3; // rbp
  unsigned int v4; // edx
  char *v5; // rdi
  char *v6; // rsi
  int v7; // ecx
  unsigned __int64 v8; // rbx
  char *v9; // r15
  char *v10; // rsi
  _QWORD v12[2]; // [rsp+20h] [rbp-68h] BYREF
  _DWORD v13[4]; // [rsp+30h] [rbp-58h]

  NormalizeAllLanguageTags<std::vector<std::wstring>>(a2);
  v3 = 0;
  v13[0] = 55;
  v13[1] = 56;
  v13[2] = 40;
  do
  {
    v4 = v13[v3];
    v5 = *a2;
    v6 = a2[1];
    v7 = 166;
    if ( v4 != 40 )
      v7 = 0;
    v12[1] = __PAIR64__(v4, v7);
    v8 = __PAIR64__(v4, v7);
    v12[0] = __PAIR64__(v4, v7);
    while ( v5 != v6 && !(unsigned __int8)lambda_bab0d47ea7fdfa9628bd6c31a27d7e97_::operator()(v12, v5) )
      v5 += 40;
    v9 = a2[1];
    if ( v9 - v5 >= 80 )
    {
      v10 = v5 + 40;
      v12[0] = v8;
      while ( v10 != v9 )
      {
        if ( (unsigned __int8)lambda_bab0d47ea7fdfa9628bd6c31a27d7e97_::operator()(v12, v10) )
          std::wstring::assign(v10, v5, 0, 0xFFFFFFFFFFFFFFFFuLL);
        v10 += 40;
      }
    }
    ++v3;
  }
  while ( v3 != 3 );
  return RemoveDuplicates<std::vector<std::wstring>>((void **)a2);
}

```

## disassembly

```asm
0x18000e73c  push    rbx
0x18000e73e  push    rbp
0x18000e73f  push    rsi
0x18000e740  push    rdi
0x18000e741  push    r14
0x18000e743  push    r15
0x18000e745  sub     rsp, 58h
0x18000e749  mov     rax, cs:__security_cookie
0x18000e750  xor     rax, rsp
0x18000e753  mov     [rsp+88h+var_48], rax
0x18000e758  mov     rcx, rdx
0x18000e75b  mov     r14, rdx
0x18000e75e  call    ??$NormalizeAllLanguageTags@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; NormalizeAllLanguageTags<std::vector<std::wstring>>(std::vector<std::wstring> &)
0x18000e763  xor     ebp, ebp
0x18000e765  mov     [rsp+88h+var_58], 37h ; '7'
0x18000e76d  mov     [rsp+88h+var_54], 38h ; '8'
0x18000e775  mov     [rsp+88h+var_50], 28h ; '('
0x18000e77d  mov     edx, [rsp+rbp*4+88h+var_58]
0x18000e781  xor     eax, eax
0x18000e783  mov     rdi, [r14]
0x18000e786  cmp     edx, 28h ; '('
0x18000e789  mov     rsi, [r14+8]
0x18000e78d  mov     ecx, 0A6h
0x18000e792  cmovnz  ecx, eax
0x18000e795  mov     dword ptr [rsp+88h+var_60+4], edx
0x18000e799  mov     dword ptr [rsp+88h+var_60], ecx
0x18000e79d  mov     rbx, [rsp+88h+var_60]
0x18000e7a2  mov     [rsp+88h+var_68], rbx
0x18000e7a7  jmp     short loc_18000E7BE
0x18000e7a9  mov     rdx, rdi
0x18000e7ac  lea     rcx, [rsp+88h+var_68]
0x18000e7b1  call    _lambda_bab0d47ea7fdfa9628bd6c31a27d7e97___operator__
0x18000e7b6  test    al, al
0x18000e7b8  jnz     short loc_18000E7C3
0x18000e7ba  add     rdi, 28h ; '('
0x18000e7be  cmp     rdi, rsi
0x18000e7c1  jnz     short loc_18000E7A9
0x18000e7c3  mov     r15, [r14+8]
0x18000e7c7  mov     rax, r15
0x18000e7ca  sub     rax, rdi
0x18000e7cd  cmp     rax, 50h ; 'P'
0x18000e7d1  jl      short loc_18000E80A
0x18000e7d3  lea     rsi, [rdi+28h]
0x18000e7d7  mov     [rsp+88h+var_68], rbx
0x18000e7dc  jmp     short loc_18000E805
0x18000e7de  mov     rdx, rsi
0x18000e7e1  lea     rcx, [rsp+88h+var_68]
0x18000e7e6  call    _lambda_bab0d47ea7fdfa9628bd6c31a27d7e97___operator__
0x18000e7eb  test    al, al
0x18000e7ed  jz      short loc_18000E801
0x18000e7ef  or      r9, 0FFFFFFFFFFFFFFFFh
0x18000e7f3  xor     r8d, r8d
0x18000e7f6  mov     rdx, rdi
0x18000e7f9  mov     rcx, rsi
0x18000e7fc  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000e801  add     rsi, 28h ; '('
0x18000e805  cmp     rsi, r15
0x18000e808  jnz     short loc_18000E7DE
0x18000e80a  inc     rbp
0x18000e80d  cmp     rbp, 3
0x18000e811  jnz     loc_18000E77D
0x18000e817  mov     rcx, r14
0x18000e81a  call    ??$RemoveDuplicates@V?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@@YAXAEAV?$vector@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@V?$allocator@V?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@2@@std@@@Z; RemoveDuplicates<std::vector<std::wstring>>(std::vector<std::wstring> &)
0x18000e81f  mov     rcx, [rsp+88h+var_48]
0x18000e824  xor     rcx, rsp; StackCookie
0x18000e827  call    __security_check_cookie
0x18000e82c  add     rsp, 58h
0x18000e830  pop     r15
0x18000e832  pop     r14
0x18000e834  pop     rdi
0x18000e835  pop     rsi
0x18000e836  pop     rbp
0x18000e837  pop     rbx
0x18000e838  retn
```
