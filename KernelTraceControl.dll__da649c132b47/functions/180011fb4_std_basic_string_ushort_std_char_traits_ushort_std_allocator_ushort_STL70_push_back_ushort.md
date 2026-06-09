# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>,_STL70>::push_back(ushort)

- ea: `0x180011fb4`
- end: `0x180012109`
- name: `?push_back@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@QEAAXG@Z`
- size: `341`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x180011e8c`
- `0x1800126bc`

## callees

- `0x180011fb4`
- `0x1800137f8`
- `0x180027668`
- `0x1800276c0`

## import_xrefs

- `msvcrt!memmove_s` at `0x1800120bd`
- `msvcrt!memmove_s` at `0x1800120bd`

## pseudocode

```c
_WORD *__fastcall std::wstring::push_back(_QWORD *a1)
{
  _QWORD *v1; // rbx
  _QWORD *v3; // rax
  unsigned __int64 v4; // rcx
  __int64 v5; // rbp
  _QWORD *v6; // rax
  unsigned __int64 v7; // rbp
  unsigned __int64 v8; // rsi
  _WORD *result; // rax
  bool v10; // cf
  unsigned __int64 v11; // rdx
  _QWORD *v12; // rcx
  _QWORD *v13; // rax

  v1 = a1 + 1;
  if ( a1[4] < 8u )
    v3 = a1 + 1;
  else
    v3 = (_QWORD *)*v1;
  v4 = a1[3];
  v5 = (__int64)v3 + 2 * v4;
  if ( a1[4] < 8u )
    v6 = v1;
  else
    v6 = (_QWORD *)*v1;
  if ( v5 )
    v7 = (v5 - (__int64)v6) >> 1;
  else
    v7 = 0;
  if ( v4 < v7 )
    std::_String_base::_Xran();
  if ( a1[3] == -1 || ~a1[3] == 1 )
    std::_String_base::_Xlen();
  v8 = a1[3] + 1LL;
  if ( v8 > 0x7FFFFFFFFFFFFFFELL )
    std::_String_base::_Xlen();
  if ( a1[4] < v8 )
  {
    result = (_WORD *)std::wstring::_Copy(a1, a1[3] + 1LL, a1[3]);
    goto LABEL_23;
  }
  if ( a1[3] == -1 )
  {
    v10 = a1[4] < 8u;
    a1[3] = 0;
    if ( v10 )
      result = v1;
    else
      result = (_WORD *)*v1;
    *result = 0;
LABEL_23:
    if ( !v8 )
      return result;
  }
  v11 = a1[4];
  if ( v11 < 8 )
    v12 = v1;
  else
    v12 = (_QWORD *)*v1;
  if ( v11 < 8 )
    v13 = v1;
  else
    v13 = (_QWORD *)*v1;
  memmove_s((char *)v13 + 2 * v7 + 2, 2 * (v11 - v7) - 2, (char *)v12 + 2 * v7, 2 * (a1[3] - v7));
  if ( a1[4] < 8u )
    result = v1;
  else
    result = (_WORD *)*v1;
  result[v7] = 92;
  v10 = a1[4] < 8u;
  a1[3] = v8;
  if ( !v10 )
    v1 = (_QWORD *)*v1;
  *((_WORD *)v1 + v8) = 0;
  return result;
}

```

## disassembly

```asm
0x180011fb4  mov     rax, rsp
0x180011fb7  mov     [rax+8], rbx
0x180011fbb  mov     [rax+10h], rbp
0x180011fbf  mov     [rax+18h], rsi
0x180011fc3  mov     [rax+20h], rdi
0x180011fc7  push    r14
0x180011fc9  sub     rsp, 20h
0x180011fcd  cmp     qword ptr [rcx+20h], 8
0x180011fd2  lea     rbx, [rcx+8]
0x180011fd6  mov     rdi, rcx
0x180011fd9  jb      short loc_180011FE0
0x180011fdb  mov     rax, [rbx]
0x180011fde  jmp     short loc_180011FE3
0x180011fe0  mov     rax, rbx
0x180011fe3  cmp     qword ptr [rdi+20h], 8
0x180011fe8  mov     rcx, [rcx+18h]
0x180011fec  lea     rbp, [rax+rcx*2]
0x180011ff0  jb      short loc_180011FF7
0x180011ff2  mov     rax, [rbx]
0x180011ff5  jmp     short loc_180011FFA
0x180011ff7  mov     rax, rbx
0x180011ffa  xor     r14d, r14d
0x180011ffd  test    rbp, rbp
0x180012000  jnz     short loc_180012007
0x180012002  mov     ebp, r14d
0x180012005  jmp     short loc_18001200D
0x180012007  sub     rbp, rax
0x18001200a  sar     rbp, 1
0x18001200d  cmp     rcx, rbp
0x180012010  jnb     short loc_180012017
0x180012012  call    ?_Xran@_String_base@std@@SAXXZ; std::_String_base::_Xran(void)
0x180012017  mov     rax, [rdi+18h]
0x18001201b  not     rax
0x18001201e  cmp     rax, 1
0x180012022  ja      short loc_180012029
0x180012024  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x180012029  mov     rsi, [rdi+18h]
0x18001202d  mov     rax, 7FFFFFFFFFFFFFFEh
0x180012037  inc     rsi
0x18001203a  cmp     rsi, rax
0x18001203d  jbe     short loc_180012044
0x18001203f  call    ?_Xlen@_String_base@std@@SAXXZ; std::_String_base::_Xlen(void)
0x180012044  cmp     [rdi+20h], rsi
0x180012048  jnb     short loc_18001205B
0x18001204a  mov     r8, [rdi+18h]
0x18001204e  mov     rdx, rsi
0x180012051  mov     rcx, rdi
0x180012054  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@V_STL70@@@std@@IEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x180012059  jmp     short loc_180012077
0x18001205b  test    rsi, rsi
0x18001205e  jnz     short loc_18001207C
0x180012060  cmp     qword ptr [rdi+20h], 8
0x180012065  mov     [rdi+18h], r14
0x180012069  jb      short loc_180012070
0x18001206b  mov     rax, [rbx]
0x18001206e  jmp     short loc_180012073
0x180012070  mov     rax, rbx
0x180012073  mov     [rax], r14w
0x180012077  test    rsi, rsi
0x18001207a  jz      short loc_1800120EE
0x18001207c  mov     rdx, [rdi+20h]
0x180012080  cmp     rdx, 8
0x180012084  jb      short loc_18001208B
0x180012086  mov     rcx, [rbx]
0x180012089  jmp     short loc_18001208E
0x18001208b  mov     rcx, rbx
0x18001208e  cmp     rdx, 8
0x180012092  jb      short loc_180012099
0x180012094  mov     rax, [rbx]
0x180012097  jmp     short loc_18001209C
0x180012099  mov     rax, rbx
0x18001209c  mov     r9, [rdi+18h]
0x1800120a0  lea     r8, [rcx+rbp*2]; Source
0x1800120a4  sub     rdx, rbp
0x1800120a7  lea     rcx, [rax+2]
0x1800120ab  sub     r9, rbp
0x1800120ae  lea     rcx, [rcx+rbp*2]; Destination
0x1800120b2  add     r9, r9; SourceSize
0x1800120b5  lea     rdx, ds:0FFFFFFFFFFFFFFFEh[rdx*2]; DestinationSize
0x1800120bd  call    cs:__imp_memmove_s
0x1800120c3  cmp     qword ptr [rdi+20h], 8
0x1800120c8  jb      short loc_1800120CF
0x1800120ca  mov     rax, [rbx]
0x1800120cd  jmp     short loc_1800120D2
0x1800120cf  mov     rax, rbx
0x1800120d2  mov     ecx, 5Ch ; '\'
0x1800120d7  mov     [rax+rbp*2], cx
0x1800120db  cmp     qword ptr [rdi+20h], 8
0x1800120e0  mov     [rdi+18h], rsi
0x1800120e4  jb      short loc_1800120E9
0x1800120e6  mov     rbx, [rbx]
0x1800120e9  mov     [rbx+rsi*2], r14w
0x1800120ee  mov     rbx, [rsp+28h+arg_0]
0x1800120f3  mov     rbp, [rsp+28h+arg_8]
0x1800120f8  mov     rsi, [rsp+28h+arg_10]
0x1800120fd  mov     rdi, [rsp+28h+arg_18]
0x180012102  add     rsp, 20h
0x180012106  pop     r14
0x180012108  retn
```
