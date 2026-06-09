# std::basic_string<char,std::char_traits<char>,std::allocator<char>>::assign(std::basic_string<char,std::char_traits<char>,std::allocator<char>> const &,unsigned __int64,unsigned __int64)

- ea: `0x180003470`
- end: `0x1800035cd`
- name: `?assign@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAAEAV12@AEBV12@_K1@Z`
- size: `349`
- prototype: `__int64 __fastcall(void *)`
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1800038a0`

## callees

- `0x1800017a0`
- `0x180001ae0`
- `0x180003470`
- `0x180003640`
- `0x180004acc`

## import_xrefs

- `VCRUNTIME140!memmove` at `0x180003518`
- `VCRUNTIME140!memmove` at `0x180003518`

## pseudocode

```c
_QWORD *__fastcall std::string::assign(_QWORD *a1, _QWORD *a2, unsigned __int64 a3, size_t a4)
{
  unsigned __int64 v4; // rax
  size_t v5; // rdi
  _QWORD *v7; // r14
  _QWORD *v8; // rbx
  size_t v9; // rax
  size_t v10; // rax
  unsigned __int64 v11; // rdi
  _BYTE *v12; // rcx
  _BYTE *v13; // rcx
  bool v14; // cf
  _BYTE *v15; // rax

  v4 = a2[2];
  v5 = a4;
  v7 = a2;
  v8 = a1;
  if ( v4 < a3 )
    std::wstring::_Xran();
  v9 = v4 - a3;
  if ( a4 > v9 )
    v5 = v9;
  if ( a1 == a2 )
  {
    v10 = a3 + v5;
    if ( a1[2] < a3 + v5 )
      std::wstring::_Xran();
    a1[2] = v10;
    if ( a1[3] >= 0x10u )
      a1 = (_QWORD *)*a1;
    *((_BYTE *)a1 + v10) = 0;
    v11 = v8[2];
    if ( v11 <= a3 )
    {
      v8[2] = 0;
      if ( v8[3] >= 0x10u )
      {
        *(_BYTE *)*v8 = 0;
        return v8;
      }
LABEL_27:
      *(_BYTE *)v8 = 0;
      return v8;
    }
    if ( !a3 )
      return v8;
    if ( v8[3] < 0x10u )
      v12 = v8;
    else
      v12 = (_BYTE *)*v8;
    v5 = v11 - a3;
    if ( v5 )
      memmove(v12, &v12[a3], v5);
  }
  else
  {
    if ( v5 == -1 )
      std::string::_Xlen();
    if ( a1[3] >= v5 )
    {
      if ( !v5 )
      {
        v14 = a1[3] < 0x10u;
        a1[2] = 0;
        if ( !v14 )
        {
          *(_BYTE *)*a1 = 0;
          return v8;
        }
        goto LABEL_27;
      }
    }
    else
    {
      std::string::_Copy(a1);
      if ( !v5 )
        return v8;
    }
    if ( v7[3] >= 0x10u )
      v7 = (_QWORD *)*v7;
    if ( v8[3] < 0x10u )
      v13 = v8;
    else
      v13 = (_BYTE *)*v8;
    memcpy_0(v13, (char *)v7 + a3, v5);
  }
  v8[2] = v5;
  if ( v8[3] < 0x10u )
    v15 = v8;
  else
    v15 = (_BYTE *)*v8;
  v15[v5] = 0;
  return v8;
}

```

## disassembly

```asm
0x180003470  mov     [rsp+arg_0], rbx
0x180003475  mov     [rsp+arg_8], rsi
0x18000347a  mov     [rsp+arg_10], rdi
0x18000347f  push    r14
0x180003481  sub     rsp, 20h
0x180003485  mov     rax, [rdx+10h]
0x180003489  mov     rdi, r9
0x18000348c  mov     rsi, r8
0x18000348f  mov     r14, rdx
0x180003492  mov     rbx, rcx
0x180003495  cmp     rax, r8
0x180003498  jb      loc_1800035BB
0x18000349e  sub     rax, r8
0x1800034a1  cmp     r9, rax
0x1800034a4  cmova   rdi, rax
0x1800034a8  cmp     rcx, rdx
0x1800034ab  jnz     short loc_180003520
0x1800034ad  lea     rax, [r8+rdi]
0x1800034b1  cmp     [rcx+10h], rax
0x1800034b5  jb      loc_1800035C1
0x1800034bb  mov     [rcx+10h], rax
0x1800034bf  cmp     qword ptr [rcx+18h], 10h
0x1800034c4  jb      short loc_1800034C9
0x1800034c6  mov     rcx, [rcx]
0x1800034c9  mov     byte ptr [rcx+rax], 0
0x1800034cd  mov     rdi, [rbx+10h]
0x1800034d1  cmp     rdi, rsi
0x1800034d4  ja      short loc_1800034F4
0x1800034d6  mov     qword ptr [rbx+10h], 0
0x1800034de  cmp     qword ptr [rbx+18h], 10h
0x1800034e3  jb      loc_18000356F
0x1800034e9  mov     rax, [rbx]
0x1800034ec  mov     byte ptr [rax], 0
0x1800034ef  jmp     loc_1800035A2
0x1800034f4  test    rsi, rsi
0x1800034f7  jz      loc_1800035A2
0x1800034fd  cmp     qword ptr [rbx+18h], 10h
0x180003502  jb      short loc_180003509
0x180003504  mov     rcx, [rbx]
0x180003507  jmp     short loc_18000350C
0x180003509  mov     rcx, rbx; void *
0x18000350c  sub     rdi, rsi
0x18000350f  jz      short loc_18000358B
0x180003511  lea     rdx, [rcx+r8]; Src
0x180003515  mov     r8, rdi; Size
0x180003518  call    cs:__imp_memmove
0x18000351e  jmp     short loc_18000358B
0x180003520  cmp     rdi, 0FFFFFFFFFFFFFFFEh
0x180003524  ja      loc_1800035C7
0x18000352a  cmp     [rcx+18h], rdi
0x18000352e  jnb     short loc_180003557
0x180003530  mov     r8, [rcx+10h]
0x180003534  mov     rdx, rdi
0x180003537  call    ?_Copy@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEAAX_K0@Z; std::string::_Copy(unsigned __int64,unsigned __int64)
0x18000353c  test    rdi, rdi
0x18000353f  jz      short loc_1800035A2
0x180003541  cmp     qword ptr [r14+18h], 10h
0x180003546  jb      short loc_18000354B
0x180003548  mov     r14, [r14]
0x18000354b  cmp     qword ptr [rbx+18h], 10h
0x180003550  jb      short loc_180003577
0x180003552  mov     rcx, [rbx]
0x180003555  jmp     short loc_18000357A
0x180003557  test    rdi, rdi
0x18000355a  jnz     short loc_180003541
0x18000355c  cmp     qword ptr [rcx+18h], 10h
0x180003561  mov     [rcx+10h], rdi
0x180003565  jb      short loc_18000356F
0x180003567  mov     rax, [rcx]
0x18000356a  mov     [rax], dil
0x18000356d  jmp     short loc_1800035A2
0x18000356f  mov     rax, rbx
0x180003572  mov     byte ptr [rbx], 0
0x180003575  jmp     short loc_1800035A2
0x180003577  mov     rcx, rbx; void *
0x18000357a  test    rdi, rdi
0x18000357d  jz      short loc_18000358B
0x18000357f  lea     rdx, [r14+rsi]; Src
0x180003583  mov     r8, rdi; Size
0x180003586  call    memcpy_0
0x18000358b  mov     [rbx+10h], rdi
0x18000358f  cmp     qword ptr [rbx+18h], 10h
0x180003594  jb      short loc_18000359B
0x180003596  mov     rax, [rbx]
0x180003599  jmp     short loc_18000359E
0x18000359b  mov     rax, rbx
0x18000359e  mov     byte ptr [rax+rdi], 0
0x1800035a2  mov     rsi, [rsp+28h+arg_8]
0x1800035a7  mov     rax, rbx
0x1800035aa  mov     rbx, [rsp+28h+arg_0]
0x1800035af  mov     rdi, [rsp+28h+arg_10]
0x1800035b4  add     rsp, 20h
0x1800035b8  pop     r14
0x1800035ba  retn
0x1800035bb  call    ?_Xran@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x1800035c1  call    ?_Xran@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@QEBAXXZ; std::wstring::_Xran(void)
0x1800035c7  call    ?_Xlen@?$basic_string@DU?$char_traits@D@std@@V?$allocator@D@2@@std@@QEBAXXZ; std::string::_Xlen(void)
```
