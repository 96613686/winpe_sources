# std::filesystem::operator/(std::filesystem::path const &,std::filesystem::path const &)

- ea: `0x180009208`
- end: `0x1800093a9`
- name: `??Kfilesystem@std@@YA?AVpath@01@AEBV201@0@Z`
- size: `417`
- prototype: `std::filesystem::path *__fastcall(std::filesystem::path *Src, struct std::filesystem::path *, std::filesystem *this)`
- caller_count: `4`
- callee_count: `5`
- tags: ``

## callers

- `0x180009d10`
- `0x180009fc8`
- `0x18000a060`
- `0x18000aa84`

## callees

- `0x180007da0`
- `0x180008c00`
- `0x180009208`
- `0x180009508`
- `0x18000bd94`

## pseudocode

```c
std::filesystem::path *__fastcall std::filesystem::operator/(
        std::filesystem::path *Src,
        struct std::filesystem::path *a2,
        std::filesystem *this)
{
  __int64 v6; // rdx
  std::filesystem *v7; // r15
  size_t v8; // r13
  __int64 v9; // rcx
  unsigned __int8 v10; // r12
  size_t v11; // r14
  unsigned __int64 v12; // rdi
  std::filesystem::path *v13; // rbp
  _WORD *v14; // rcx
  std::filesystem::path *v15; // rcx

  v6 = *((_QWORD *)this + 2);
  if ( *((_QWORD *)this + 3) <= 7u )
    v7 = this;
  else
    v7 = *(std::filesystem **)this;
  if ( !v6
    || (v8 = 2 * v6, 2 * v6 >= 4) && (*(_DWORD *)v7 & 0xFFFFFFDF) - 3801153 < 0x1A
    || *(_WORD *)v7 == 92
    || *(_WORD *)v7 == 47 )
  {
    std::filesystem::path::path(Src, a2);
    std::filesystem::path::operator/=(Src, this);
    return Src;
  }
  v9 = *((_QWORD *)a2 + 2);
  if ( *((_QWORD *)a2 + 3) > 7u )
    a2 = *(struct std::filesystem::path **)a2;
  if ( v9 == 2 )
  {
    if ( (*(_DWORD *)a2 & 0xFFFFFFDF) - 3801153 < 0x1A )
      goto LABEL_13;
  }
  else if ( !v9 )
  {
    goto LABEL_13;
  }
  v11 = 2 * v9;
  if ( *((_WORD *)a2 + v9 - 1) != 92 && *(_WORD *)((char *)a2 + v11 - 2) != 47 )
  {
    v10 = 1;
    goto LABEL_14;
  }
LABEL_13:
  v10 = 0;
  v11 = 2 * v9;
LABEL_14:
  v12 = v6 + v9 + v10;
  *(_OWORD *)Src = 0;
  *((_QWORD *)Src + 2) = 0;
  *((_QWORD *)Src + 3) = 7;
  *(_WORD *)Src = 0;
  if ( v12 <= 7 )
    *((_QWORD *)Src + 2) = v12;
  else
    std::wstring::_Reallocate_grow_by<_lambda_3c42e42a79350c8a48dd4e272c8dbcce_,>(Src);
  if ( *((_QWORD *)Src + 3) <= 7u )
    v13 = Src;
  else
    v13 = *(std::filesystem::path **)Src;
  memcpy_0(v13, a2, v11);
  v14 = (_WORD *)((char *)v13 + v11);
  if ( v10 )
    *v14++ = 92;
  memcpy_0(v14, v7, v8);
  *((_QWORD *)Src + 2) = v12;
  if ( *((_QWORD *)Src + 3) <= 7u )
    v15 = Src;
  else
    v15 = *(std::filesystem::path **)Src;
  *((_WORD *)v15 + v12) = 0;
  return Src;
}

```

## disassembly

```asm
0x180009208  mov     [rsp+arg_8], rbx
0x18000920d  mov     [rsp+arg_0], rcx
0x180009212  push    rbp
0x180009213  push    rsi
0x180009214  push    rdi
0x180009215  push    r12
0x180009217  push    r13
0x180009219  push    r14
0x18000921b  push    r15
0x18000921d  sub     rsp, 20h
0x180009221  mov     rdi, r8
0x180009224  mov     rsi, rdx
0x180009227  mov     rbx, rcx
0x18000922a  mov     r8d, 1
0x180009230  mov     [rsp+58h+arg_10], r8d
0x180009235  mov     rdx, [rdi+10h]
0x180009239  lea     ebp, [r8+6]
0x18000923d  cmp     [rdi+18h], rbp
0x180009241  jbe     short loc_180009248
0x180009243  mov     r15, [rdi]
0x180009246  jmp     short loc_18000924B
0x180009248  mov     r15, rdi
0x18000924b  test    rdx, rdx
0x18000924e  jz      loc_180009374
0x180009254  lea     r13, [rdx+rdx]
0x180009258  mov     rax, r13
0x18000925b  and     rax, 0FFFFFFFFFFFFFFFEh
0x18000925f  mov     r9d, 0FFFFFFDFh
0x180009265  mov     r10d, 3A0041h
0x18000926b  cmp     rax, 4
0x18000926f  jl      short loc_180009283
0x180009271  mov     eax, [r15]
0x180009274  and     eax, r9d
0x180009277  sub     eax, r10d
0x18000927a  cmp     eax, 1Ah
0x18000927d  jb      loc_180009374
0x180009283  mov     r11d, 5Ch ; '\'
0x180009289  cmp     [r15], r11w
0x18000928d  jz      loc_180009374
0x180009293  cmp     word ptr [r15], 2Fh ; '/'
0x180009298  jz      loc_180009374
0x18000929e  mov     rcx, [rsi+10h]
0x1800092a2  cmp     [rsi+18h], rbp
0x1800092a6  jbe     short loc_1800092AB
0x1800092a8  mov     rsi, [rsi]
0x1800092ab  cmp     rcx, 2
0x1800092af  jnz     short loc_1800092FD
0x1800092b1  mov     eax, [rsi]
0x1800092b3  and     eax, r9d
0x1800092b6  sub     eax, r10d
0x1800092b9  cmp     eax, 1Ah
0x1800092bc  jnb     short loc_180009302
0x1800092be  xor     r12b, r12b
0x1800092c1  lea     r14, [rcx+rcx]
0x1800092c5  movzx   edi, r12b
0x1800092c9  add     rdi, rcx
0x1800092cc  add     rdi, rdx
0x1800092cf  xorps   xmm0, xmm0
0x1800092d2  movups  xmmword ptr [rbx], xmm0
0x1800092d5  mov     qword ptr [rbx+10h], 0
0x1800092dd  mov     [rbx+18h], rbp
0x1800092e1  xor     eax, eax
0x1800092e3  mov     [rbx], ax
0x1800092e6  mov     [rsp+58h+arg_10], r8d
0x1800092eb  cmp     rdi, rbp
0x1800092ee  jbe     short loc_18000931C
0x1800092f0  mov     rdx, rdi
0x1800092f3  mov     rcx, rbx; Src
0x1800092f6  call    ??$_Reallocate_grow_by@V_lambda_3c42e42a79350c8a48dd4e272c8dbcce_@@$$V@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_3c42e42a79350c8a48dd4e272c8dbcce_@@@Z; std::wstring::_Reallocate_grow_by<_lambda_3c42e42a79350c8a48dd4e272c8dbcce_,>(unsigned __int64,_lambda_3c42e42a79350c8a48dd4e272c8dbcce_)
0x1800092fb  jmp     short loc_180009320
0x1800092fd  test    rcx, rcx
0x180009300  jz      short loc_1800092BE
0x180009302  lea     r14, [rcx+rcx]
0x180009306  cmp     [r14+rsi-2], r11w
0x18000930c  jz      short loc_1800092BE
0x18000930e  cmp     word ptr [r14+rsi-2], 2Fh ; '/'
0x180009315  jz      short loc_1800092BE
0x180009317  mov     r12b, r8b
0x18000931a  jmp     short loc_1800092C5
0x18000931c  mov     [rbx+10h], rdi
0x180009320  cmp     [rbx+18h], rbp
0x180009324  jbe     short loc_18000932B
0x180009326  mov     rbp, [rbx]
0x180009329  jmp     short loc_18000932E
0x18000932b  mov     rbp, rbx
0x18000932e  mov     r8, r14; Size
0x180009331  mov     rdx, rsi; Src
0x180009334  mov     rcx, rbp; void *
0x180009337  call    memcpy_0
0x18000933c  lea     rcx, [r14+rbp]
0x180009340  test    r12b, r12b
0x180009343  jz      short loc_18000934E
0x180009345  mov     word ptr [rcx], 5Ch ; '\'
0x18000934a  add     rcx, 2; void *
0x18000934e  mov     r8, r13; Size
0x180009351  mov     rdx, r15; Src
0x180009354  call    memcpy_0
0x180009359  mov     [rbx+10h], rdi
0x18000935d  cmp     qword ptr [rbx+18h], 7
0x180009362  jbe     short loc_180009369
0x180009364  mov     rcx, [rbx]
0x180009367  jmp     short loc_18000936C
0x180009369  mov     rcx, rbx; this
0x18000936c  xor     eax, eax
0x18000936e  mov     [rcx+rdi*2], ax
0x180009372  jmp     short loc_180009391
0x180009374  mov     rdx, rsi; struct std::filesystem::path *
0x180009377  call    ??0path@filesystem@std@@QEAA@AEBV012@@Z; std::filesystem::path::path(std::filesystem::path const &)
0x18000937c  nop
0x18000937d  mov     [rsp+58h+arg_10], 3
0x180009385  mov     rdx, rdi; this
0x180009388  mov     rcx, rbx; Src
0x18000938b  call    ??_0path@filesystem@std@@QEAAAEAV012@AEBV012@@Z; std::filesystem::path::operator/=(std::filesystem::path const &)
0x180009390  nop
0x180009391  mov     rax, rbx
0x180009394  mov     rbx, [rsp+58h+arg_8]
0x180009399  add     rsp, 20h
0x18000939d  pop     r15
0x18000939f  pop     r14
0x1800093a1  pop     r13
0x1800093a3  pop     r12
0x1800093a5  pop     rdi
0x1800093a6  pop     rsi
0x1800093a7  pop     rbp
0x1800093a8  retn
```
