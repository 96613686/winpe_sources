# std::time_get<ushort,std::istreambuf_iterator<ushort,std::char_traits<ushort>>>::_Getint(std::istreambuf_iterator<ushort,std::char_traits<ushort>> &,std::istreambuf_iterator<ushort,std::char_traits<ushort>> &,int,int,int &,std::ctype<ushort> const &)

- ea: `0x1800102a0`
- end: `0x180010465`
- name: `?_Getint@?$time_get@GV?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@@std@@AEBAHAEAV?$istreambuf_iterator@GU?$char_traits@G@std@@@2@0HHAEAHAEBV?$ctype@G@2@@Z`
- size: `453`
- prototype: `__int64 __fastcall(__int64, __int64 *, __int64, int, int, _DWORD *, __int64)`
- caller_count: `8`
- callee_count: `7`
- tags: ``

## callers

- `0x180018390`
- `0x180018890`
- `0x180018d90`
- `0x180019340`
- `0x180019950`
- `0x180019b00`
- `0x180019d10`
- `0x180019e30`

## callees

- `0x18000b754`
- `0x1800102a0`
- `0x180011cac`
- `0x18001c5d8`
- `0x180022780`
- `0x1800350e0`
- `0x180037010`

## pseudocode

```c
__int64 __fastcall std::time_get<unsigned short,std::istreambuf_iterator<unsigned short>>::_Getint(
        __int64 a1,
        __int64 *a2,
        __int64 a3,
        int a4,
        int a5,
        _DWORD *a6,
        __int64 a7)
{
  char *v7; // rdi
  unsigned __int16 *v11; // rax
  char v12; // al
  char v13; // r14
  unsigned __int16 *v14; // rax
  unsigned __int16 *v15; // rax
  char v16; // al
  char *v17; // rax
  char *v18; // rax
  int v19; // edi
  __int64 result; // rax
  int v21; // [rsp+20h] [rbp-40h] BYREF
  char *v22; // [rsp+28h] [rbp-38h] BYREF
  char v23; // [rsp+30h] [rbp-30h] BYREF
  char v24; // [rsp+31h] [rbp-2Fh] BYREF
  char v25; // [rsp+4Fh] [rbp-11h] BYREF

  v7 = &v23;
  v22 = 0;
  if ( (unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a2, a3) )
    goto LABEL_7;
  v11 = (unsigned __int16 *)std::istreambuf_iterator<unsigned short>::operator*(a2);
  v12 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a7 + 112LL))(a7, *v11, 0);
  if ( v12 == 43 )
  {
    v23 = 43;
LABEL_6:
    v7 = &v24;
    std::istreambuf_iterator<unsigned short>::_Inc(a2);
    goto LABEL_7;
  }
  if ( v12 == 45 )
  {
    v23 = 45;
    goto LABEL_6;
  }
LABEL_7:
  v13 = 0;
  if ( !(unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a2, a3) )
  {
    do
    {
      v14 = (unsigned __int16 *)std::istreambuf_iterator<unsigned short>::operator*(a2);
      if ( (*(unsigned __int8 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a7 + 112LL))(a7, *v14, 0) != 48 )
        break;
      v13 = 1;
      std::istreambuf_iterator<unsigned short>::_Inc(a2);
    }
    while ( !(unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a2, a3) );
    if ( v13 )
      *v7++ = 48;
  }
  while ( !(unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a2, a3) )
  {
    v15 = (unsigned __int16 *)std::istreambuf_iterator<unsigned short>::operator*(a2);
    v16 = (*(__int64 (__fastcall **)(__int64, _QWORD, _QWORD))(*(_QWORD *)a7 + 112LL))(a7, *v15, 0);
    if ( (unsigned __int8)(v16 - 48) > 9u )
      break;
    *v7 = v16;
    v13 = 1;
    std::istreambuf_iterator<unsigned short>::_Inc(a2);
    v17 = v7 + 1;
    if ( v7 >= &v25 )
      v17 = v7;
    v7 = v17;
  }
  v18 = &v23;
  v21 = 0;
  if ( v13 )
    v18 = v7;
  *v18 = 0;
  v19 = Stolx(&v23, &v22, 10, &v21);
  result = (unsigned __int8)std::istreambuf_iterator<wchar_t>::equal(a2, a3);
  if ( v22 == &v23 || v21 || v19 < a4 || a5 < v19 )
    return (unsigned __int8)result | 2u;
  *a6 = v19;
  return result;
}

```

## disassembly

```asm
0x1800102a0  mov     [rsp-38h+arg_0], rbx
0x1800102a5  push    rbp
0x1800102a6  push    rsi
0x1800102a7  push    rdi
0x1800102a8  push    r12
0x1800102aa  push    r13
0x1800102ac  push    r14
0x1800102ae  push    r15
0x1800102b0  mov     rbp, rsp
0x1800102b3  sub     rsp, 60h
0x1800102b7  mov     rax, cs:__security_cookie
0x1800102be  xor     rax, rsp
0x1800102c1  mov     [rbp+var_10], rax
0x1800102c5  mov     r13, [rbp+arg_28]
0x1800102c9  lea     rdi, [rbp+var_30]
0x1800102cd  mov     r15, [rbp+arg_30]
0x1800102d1  mov     rbx, rdx
0x1800102d4  mov     rcx, rbx
0x1800102d7  mov     [rbp+var_38], 0
0x1800102df  mov     rdx, r8
0x1800102e2  mov     r12d, r9d
0x1800102e5  mov     rsi, r8
0x1800102e8  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x1800102ed  test    al, al
0x1800102ef  jnz     short loc_18001032D
0x1800102f1  mov     rcx, rbx
0x1800102f4  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x1800102f9  mov     rcx, [r15]
0x1800102fc  xor     r8d, r8d
0x1800102ff  movzx   edx, word ptr [rax]
0x180010302  mov     r9, [rcx+70h]
0x180010306  mov     rcx, r15
0x180010309  mov     rax, r9
0x18001030c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010311  cmp     al, 2Bh ; '+'
0x180010313  jnz     short loc_18001031A
0x180010315  mov     [rbp+var_30], al
0x180010318  jmp     short loc_180010321
0x18001031a  cmp     al, 2Dh ; '-'
0x18001031c  jnz     short loc_18001032D
0x18001031e  mov     [rbp+var_30], al
0x180010321  mov     rcx, rbx
0x180010324  lea     rdi, [rbp+var_2F]
0x180010328  call    ?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ
0x18001032d  mov     rdx, rsi
0x180010330  mov     rcx, rbx
0x180010333  xor     r14b, r14b
0x180010336  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18001033b  test    al, al
0x18001033d  jnz     loc_1800103D5
0x180010343  mov     rcx, rbx
0x180010346  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x18001034b  mov     rcx, [r15]
0x18001034e  xor     r8d, r8d
0x180010351  movzx   edx, word ptr [rax]
0x180010354  mov     r9, [rcx+70h]
0x180010358  mov     rcx, r15
0x18001035b  mov     rax, r9
0x18001035e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010363  cmp     al, 30h ; '0'
0x180010365  jnz     short loc_180010381
0x180010367  mov     rcx, rbx
0x18001036a  mov     r14b, 1
0x18001036d  call    ?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ
0x180010372  mov     rdx, rsi
0x180010375  mov     rcx, rbx
0x180010378  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18001037d  test    al, al
0x18001037f  jz      short loc_180010343
0x180010381  test    r14b, r14b
0x180010384  jz      short loc_1800103D5
0x180010386  mov     byte ptr [rdi], 30h ; '0'
0x180010389  inc     rdi
0x18001038c  jmp     short loc_1800103D5
0x18001038e  mov     rcx, rbx
0x180010391  call    ??D?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@QEBAAEBGXZ
0x180010396  mov     rcx, [r15]
0x180010399  xor     r8d, r8d
0x18001039c  movzx   edx, word ptr [rax]
0x18001039f  mov     r9, [rcx+70h]
0x1800103a3  mov     rcx, r15
0x1800103a6  mov     rax, r9
0x1800103a9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800103ae  lea     ecx, [rax-30h]
0x1800103b1  cmp     cl, 9
0x1800103b4  ja      short loc_1800103E4
0x1800103b6  mov     rcx, rbx
0x1800103b9  mov     [rdi], al
0x1800103bb  mov     r14b, 1
0x1800103be  call    ?_Inc@?$istreambuf_iterator@GU?$char_traits@G@std@@@std@@AEAAXXZ
0x1800103c3  lea     rax, [rdi+1]
0x1800103c7  lea     rcx, [rbp+var_11]
0x1800103cb  cmp     rdi, rcx
0x1800103ce  cmovnb  rax, rdi
0x1800103d2  mov     rdi, rax
0x1800103d5  mov     rdx, rsi
0x1800103d8  mov     rcx, rbx
0x1800103db  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x1800103e0  test    al, al
0x1800103e2  jz      short loc_18001038E
0x1800103e4  xor     r15d, r15d
0x1800103e7  lea     rax, [rbp+var_30]
0x1800103eb  test    r14b, r14b
0x1800103ee  mov     [rbp+var_40], r15d
0x1800103f2  lea     r9, [rbp+var_40]
0x1800103f6  cmovnz  rax, rdi
0x1800103fa  lea     rdx, [rbp+var_38]
0x1800103fe  lea     r8d, [r15+0Ah]
0x180010402  lea     rcx, [rbp+var_30]
0x180010406  mov     [rax], r15b
0x180010409  call    _Stolx
0x18001040e  mov     rdx, rsi
0x180010411  mov     rcx, rbx
0x180010414  mov     edi, eax
0x180010416  call    ?equal@?$istreambuf_iterator@_WU?$char_traits@_W@std@@@std@@QEBA_NAEBV12@@Z
0x18001041b  lea     rcx, [rbp+var_30]
0x18001041f  movzx   eax, al
0x180010422  cmp     [rbp+var_38], rcx
0x180010426  jz      short loc_18001043E
0x180010428  cmp     [rbp+var_40], r15d
0x18001042c  jnz     short loc_18001043E
0x18001042e  cmp     edi, r12d
0x180010431  jl      short loc_18001043E
0x180010433  cmp     [rbp+arg_20], edi
0x180010436  jl      short loc_18001043E
0x180010438  mov     [r13+0], edi
0x18001043c  jmp     short loc_180010441
0x18001043e  or      eax, 2
0x180010441  mov     rcx, [rbp+var_10]
0x180010445  xor     rcx, rsp; StackCookie
0x180010448  call    __security_check_cookie
0x18001044d  mov     rbx, [rsp+60h+arg_0]
0x180010455  add     rsp, 60h
0x180010459  pop     r15
0x18001045b  pop     r14
0x18001045d  pop     r13
0x18001045f  pop     r12
0x180010461  pop     rdi
0x180010462  pop     rsi
0x180010463  pop     rbp
0x180010464  retn
```
