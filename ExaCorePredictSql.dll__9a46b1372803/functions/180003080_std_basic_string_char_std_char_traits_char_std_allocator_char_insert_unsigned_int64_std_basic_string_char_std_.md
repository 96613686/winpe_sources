# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::insert(unsigned __int64,std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180003080`
- end: `0x18000320d`
- name: `?insert@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@_KAEBV12@00@Z`
- size: `397`
- prototype: `__int64 __usercall@<rax>(void *@<rcx>, __int64)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x180002f10`

## callees

- `0x1800017a0`
- `0x180001ae0`
- `0x180003080`
- `0x180003640`
- `0x180004acc`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x180003153`
- `VCRUNTIME140!memmove` at `0x180003194`
- `VCRUNTIME140!memmove` at `0x180003153`
- `VCRUNTIME140!memmove` at `0x180003194`

## pseudocode

```c
_QWORD *__fastcall std::string::insert(_QWORD *a1, __int64 a2, _QWORD *a3, unsigned __int64 a4, unsigned __int64 a5)
{
  unsigned __int64 v5; // rax
  _QWORD *v7; // r14
  __int64 v9; // r8
  unsigned __int64 v10; // rax
  size_t v11; // rdi
  size_t v12; // rsi
  unsigned __int64 v13; // rax
  _QWORD *v14; // rdx
  _QWORD *v15; // rax
  size_t v16; // r8
  unsigned __int64 v17; // rcx
  size_t v18; // rdx
  _QWORD *v19; // rax
  void *v20; // rcx
  void *v21; // rcx
  bool v22; // cf
  _QWORD *v23; // rax

  v5 = a3[2];
  v7 = a3;
  if ( v5 < a4 )
    std::wstring::_Xran();
  v9 = a1[2];
  v10 = v5 - a4;
  v11 = a5;
  if ( a5 > v10 )
    v11 = v10;
  if ( ~v9 <= v11 )
    std::string::_Xlen();
  v12 = v9 + v11;
  if ( v11 )
  {
    if ( v12 == -1 )
      std::string::_Xlen();
    if ( a1[3] >= v12 )
    {
      if ( !v12 )
      {
        a1[2] = 0;
        if ( a1[3] < 0x10u )
          *(_BYTE *)a1 = 0;
        else
          *(_BYTE *)*a1 = 0;
        return a1;
      }
    }
    else
    {
      std::string::_Copy(a1);
      if ( !v12 )
        return a1;
    }
    v13 = a1[3];
    if ( v13 < 0x10 )
      v14 = a1;
    else
      v14 = (_QWORD *)*a1;
    if ( v13 < 0x10 )
      v15 = a1;
    else
      v15 = (_QWORD *)*a1;
    v16 = a1[2];
    if ( v16 )
      memmove((char *)v15 + v11, v14, v16);
    if ( a1 == v7 )
    {
      v17 = a1[3];
      v18 = a4 + v11;
      if ( !a4 )
        v18 = 0;
      if ( v17 < 0x10 )
        v19 = a1;
      else
        v19 = (_QWORD *)*a1;
      if ( v17 < 0x10 )
        v20 = a1;
      else
        v20 = (void *)*a1;
      memmove(v20, (char *)v19 + v18, v11);
    }
    else
    {
      if ( v7[3] >= 0x10u )
        v7 = (_QWORD *)*v7;
      if ( a1[3] < 0x10u )
        v21 = a1;
      else
        v21 = (void *)*a1;
      memcpy_0(v21, (char *)v7 + a4, v11);
    }
    v22 = a1[3] < 0x10u;
    a1[2] = v12;
    if ( v22 )
      v23 = a1;
    else
      v23 = (_QWORD *)*a1;
    *((_BYTE *)v23 + v12) = 0;
  }
  return a1;
}

```

## disassembly

```asm
0x180003080  mov     [rsp+arg_10], rbx
0x180003085  mov     [rsp+arg_18], r14
0x18000308a  push    r15
0x18000308c  sub     rsp, 20h
0x180003090  mov     rax, [r8+10h]
0x180003094  mov     r15, r9
0x180003097  mov     r14, r8
0x18000309a  mov     rbx, rcx
0x18000309d  cmp     rax, r9
0x1800030a0  jb      loc_1800031FB
0x1800030a6  mov     r8, [rcx+10h]
0x1800030aa  sub     rax, r9
0x1800030ad  mov     [rsp+28h+arg_8], rdi
0x1800030b2  mov     rdi, [rsp+28h+arg_20]
0x1800030b7  cmp     rdi, rax
0x1800030ba  cmova   rdi, rax
0x1800030be  mov     rax, r8
0x1800030c1  not     rax
0x1800030c4  cmp     rax, rdi
0x1800030c7  jbe     loc_180003201
0x1800030cd  mov     [rsp+28h+arg_0], rsi
0x1800030d2  lea     rsi, [r8+rdi]
0x1800030d6  test    rdi, rdi
0x1800030d9  jz      loc_1800031DD
0x1800030df  cmp     rsi, 0FFFFFFFFFFFFFFFEh
0x1800030e3  ja      loc_180003207
0x1800030e9  cmp     [rcx+18h], rsi
0x1800030ed  jnb     short loc_18000310F
0x1800030ef  mov     rdx, rsi
0x1800030f2  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x1800030f7  test    rsi, rsi
0x1800030fa  jz      loc_1800031DD
0x180003100  mov     rax, [rbx+18h]
0x180003104  cmp     rax, 10h
0x180003108  jb      short loc_180003135
0x18000310a  mov     rdx, [rbx]
0x18000310d  jmp     short loc_180003138
0x18000310f  test    rsi, rsi
0x180003112  jnz     short loc_180003100
0x180003114  mov     [rcx+10h], rsi
0x180003118  cmp     qword ptr [rcx+18h], 10h
0x18000311d  jb      short loc_18000312A
0x18000311f  mov     rax, [rcx]
0x180003122  mov     [rax], sil
0x180003125  jmp     loc_1800031DD
0x18000312a  mov     rax, rbx
0x18000312d  mov     byte ptr [rbx], 0
0x180003130  jmp     loc_1800031DD
0x180003135  mov     rdx, rbx; Src
0x180003138  cmp     rax, 10h
0x18000313c  jb      short loc_180003143
0x18000313e  mov     rax, [rbx]
0x180003141  jmp     short loc_180003146
0x180003143  mov     rax, rbx
0x180003146  mov     r8, [rbx+10h]; Size
0x18000314a  test    r8, r8
0x18000314d  jz      short loc_180003159
0x18000314f  lea     rcx, [rax+rdi]; void *
0x180003153  call    cs:__imp_memmove
0x180003159  cmp     rbx, r14
0x18000315c  jnz     short loc_18000319C
0x18000315e  mov     rcx, [rbx+18h]
0x180003162  lea     rdx, [r15+rdi]
0x180003166  test    r15, r15
0x180003169  cmovz   rdx, r15
0x18000316d  cmp     rcx, 10h
0x180003171  jb      short loc_180003178
0x180003173  mov     rax, [rbx]
0x180003176  jmp     short loc_18000317B
0x180003178  mov     rax, rbx
0x18000317b  cmp     rcx, 10h
0x18000317f  jb      short loc_180003186
0x180003181  mov     rcx, [rbx]
0x180003184  jmp     short loc_180003189
0x180003186  mov     rcx, rbx; void *
0x180003189  test    rdi, rdi
0x18000318c  jz      short loc_1800031C6
0x18000318e  add     rdx, rax; Src
0x180003191  mov     r8, rdi; Size
0x180003194  call    cs:__imp_memmove
0x18000319a  jmp     short loc_1800031C6
0x18000319c  cmp     qword ptr [r14+18h], 10h
0x1800031a1  jb      short loc_1800031A6
0x1800031a3  mov     r14, [r14]
0x1800031a6  cmp     qword ptr [rbx+18h], 10h
0x1800031ab  jb      short loc_1800031B2
0x1800031ad  mov     rcx, [rbx]
0x1800031b0  jmp     short loc_1800031B5
0x1800031b2  mov     rcx, rbx; void *
0x1800031b5  test    rdi, rdi
0x1800031b8  jz      short loc_1800031C6
0x1800031ba  lea     rdx, [r14+r15]; Src
0x1800031be  mov     r8, rdi; Size
0x1800031c1  call    memcpy_0
0x1800031c6  cmp     qword ptr [rbx+18h], 10h
0x1800031cb  mov     [rbx+10h], rsi
0x1800031cf  jb      short loc_1800031D6
0x1800031d1  mov     rax, [rbx]
0x1800031d4  jmp     short loc_1800031D9
0x1800031d6  mov     rax, rbx
0x1800031d9  mov     byte ptr [rax+rsi], 0
0x1800031dd  mov     rsi, [rsp+28h+arg_0]
0x1800031e2  mov     rax, rbx
0x1800031e5  mov     rbx, [rsp+28h+arg_10]
0x1800031ea  mov     rdi, [rsp+28h+arg_8]
0x1800031ef  mov     r14, [rsp+28h+arg_18]
0x1800031f4  add     rsp, 20h
0x1800031f8  pop     r15
0x1800031fa  retn
0x1800031fb  call    ?_Xran@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x180003201  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
0x180003207  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
