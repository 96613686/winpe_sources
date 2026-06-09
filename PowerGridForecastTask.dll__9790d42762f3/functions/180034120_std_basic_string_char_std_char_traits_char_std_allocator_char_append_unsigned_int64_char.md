# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::append(unsigned __int64,char)

- ea: `0x180034120`
- end: `0x1800341f5`
- name: `?append@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KD@Z`
- size: `213`
- prototype: `char *__fastcall(char *, size_t, char)`
- caller_count: `19`
- callee_count: `4`
- tags: ``

## callers

- `0x180003cfc`
- `0x1800047b8`
- `0x1800053b4`
- `0x1800074b0`
- `0x18000d948`
- `0x18000e050`
- `0x18000e758`
- `0x18000eee8`
- `0x18000fa28`
- `0x18000fe64`
- `0x18001046c`
- `0x18001108c`
- `0x18001e3c0`
- `0x1800206d0`
- `0x180021980`
- `0x180021ba0`
- `0x180021de0`
- `0x180021f60`
- `0x180034d18`

## callees

- `0x1800268ef`
- `0x18002fdc4`
- `0x18002ff70`
- `0x180034120`

## pseudocode

```c
char *__fastcall std::string::append(char *a1, size_t a2, char a3)
{
  int v3; // ebp
  size_t v5; // r8
  size_t v7; // rdi
  __int64 v8; // rcx
  _BYTE *v9; // rax
  _BYTE *v10; // rax
  char *v11; // rax
  _BYTE *v12; // rax

  v3 = a3;
  v5 = *((_QWORD *)a1 + 2);
  if ( ~v5 <= a2 )
    goto LABEL_25;
  if ( !a2 )
    return a1;
  v7 = v5 + a2;
  if ( v5 + a2 == -1 )
LABEL_25:
    std::wstring::_Xlen();
  if ( *((_QWORD *)a1 + 3) >= v7 )
  {
    if ( !v7 )
    {
      if ( *((_QWORD *)a1 + 3) < 0x10u )
        v10 = a1;
      else
        v10 = *(_BYTE **)a1;
      *((_QWORD *)a1 + 2) = 0;
      *v10 = 0;
      return a1;
    }
  }
  else
  {
    std::string::_Copy((const void **)a1, v5 + a2, v5);
    if ( !v7 )
      return a1;
  }
  v8 = *((_QWORD *)a1 + 2);
  if ( a2 == 1 )
  {
    if ( *((_QWORD *)a1 + 3) < 0x10u )
      v9 = a1;
    else
      v9 = *(_BYTE **)a1;
    v9[v8] = v3;
  }
  else
  {
    if ( *((_QWORD *)a1 + 3) < 0x10u )
      v11 = a1;
    else
      v11 = *(char **)a1;
    memset_0(&v11[v8], v3, a2);
  }
  if ( *((_QWORD *)a1 + 3) < 0x10u )
    v12 = a1;
  else
    v12 = *(_BYTE **)a1;
  *((_QWORD *)a1 + 2) = v7;
  v12[v7] = 0;
  return a1;
}

```

## disassembly

```asm
0x180034120  push    rbx
0x180034122  push    rbp
0x180034123  push    rsi
0x180034124  push    rdi
0x180034125  sub     rsp, 28h
0x180034129  movsx   ebp, r8b
0x18003412d  mov     rsi, rdx
0x180034130  mov     r8, [rcx+10h]
0x180034134  mov     rbx, rcx
0x180034137  mov     rax, r8
0x18003413a  not     rax
0x18003413d  cmp     rax, rdx
0x180034140  jbe     loc_1800341EF
0x180034146  test    rdx, rdx
0x180034149  jz      loc_1800341E3
0x18003414f  lea     rdi, [r8+rdx]
0x180034153  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180034157  ja      loc_1800341EF
0x18003415d  cmp     [rcx+18h], rdi
0x180034161  jnb     short loc_180034186
0x180034163  mov     rdx, rdi
0x180034166  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18003416b  test    rdi, rdi
0x18003416e  jz      short loc_1800341E3
0x180034170  mov     rcx, [rbx+10h]
0x180034174  cmp     rsi, 1
0x180034178  jnz     short loc_1800341B0
0x18003417a  cmp     qword ptr [rbx+18h], 10h
0x18003417f  jb      short loc_1800341A7
0x180034181  mov     rax, [rbx]
0x180034184  jmp     short loc_1800341AA
0x180034186  test    rdi, rdi
0x180034189  jnz     short loc_180034170
0x18003418b  cmp     qword ptr [rcx+18h], 10h
0x180034190  jb      short loc_180034197
0x180034192  mov     rax, [rcx]
0x180034195  jmp     short loc_18003419A
0x180034197  mov     rax, rbx
0x18003419a  mov     qword ptr [rcx+10h], 0
0x1800341a2  mov     byte ptr [rax], 0
0x1800341a5  jmp     short loc_1800341E3
0x1800341a7  mov     rax, rbx
0x1800341aa  mov     [rcx+rax], bpl
0x1800341ae  jmp     short loc_1800341CC
0x1800341b0  cmp     qword ptr [rbx+18h], 10h
0x1800341b5  jb      short loc_1800341BC
0x1800341b7  mov     rax, [rbx]
0x1800341ba  jmp     short loc_1800341BF
0x1800341bc  mov     rax, rbx
0x1800341bf  mov     edx, ebp; Val
0x1800341c1  add     rcx, rax; void *
0x1800341c4  mov     r8, rsi; Size
0x1800341c7  call    memset_0
0x1800341cc  cmp     qword ptr [rbx+18h], 10h
0x1800341d1  jb      short loc_1800341D8
0x1800341d3  mov     rax, [rbx]
0x1800341d6  jmp     short loc_1800341DB
0x1800341d8  mov     rax, rbx
0x1800341db  mov     [rbx+10h], rdi
0x1800341df  mov     byte ptr [rdi+rax], 0
0x1800341e3  mov     rax, rbx
0x1800341e6  add     rsp, 28h
0x1800341ea  pop     rdi
0x1800341eb  pop     rsi
0x1800341ec  pop     rbp
0x1800341ed  pop     rbx
0x1800341ee  retn
0x1800341ef  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
