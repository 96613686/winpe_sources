# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>(std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> const &)

- ea: `0x180010634`
- end: `0x180010748`
- name: `??0?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAA@AEBV01@@Z`
- size: `276`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `3`
- callee_count: `5`
- tags: ``

## callers

- `0x180010750`
- `0x180011304`
- `0x180011858`

## callees

- `0x180001c24`
- `0x1800078d8`
- `0x180007900`
- `0x180010634`
- `0x180013ab4`

## pseudocode

```c
__int64 __fastcall std::wstring::wstring(__int64 a1, __int64 a2)
{
  _OWORD *v3; // rsi
  unsigned __int64 v4; // rdi
  __int64 v5; // rbp
  size_t v6; // rcx
  void *v7; // rax
  void *v8; // rcx
  _QWORD *v9; // rax

  *(_OWORD *)a1 = 0;
  *(_QWORD *)(a1 + 16) = 0;
  v3 = (_OWORD *)a2;
  *(_QWORD *)(a1 + 24) = 0;
  v4 = *(_QWORD *)(a2 + 16);
  if ( *(_QWORD *)(a2 + 24) > 7u )
    v3 = *(_OWORD **)a2;
  v5 = 0x7FFFFFFFFFFFFFFELL;
  if ( v4 > 0x7FFFFFFFFFFFFFFELL )
    std::_Xlen_string();
  if ( v4 > 7 )
  {
    if ( (v4 | 7) <= 0x7FFFFFFFFFFFFFFELL )
    {
      v5 = v4 | 7;
      if ( (v4 | 7) < 0xA )
        v5 = 10;
      if ( (unsigned __int64)(v5 + 1) > 0x7FFFFFFFFFFFFFFFLL )
        goto LABEL_22;
      v6 = 2 * (v5 + 1);
      if ( !v6 )
      {
        v9 = 0;
        goto LABEL_19;
      }
    }
    else
    {
      v6 = -2;
    }
    if ( v6 >= 0x1000 )
    {
      if ( v6 + 39 >= v6 )
      {
        v7 = operator new(v6 + 39);
        v8 = v7;
        if ( !v7 )
          __fastfail(5u);
        v9 = (_QWORD *)(((unsigned __int64)v7 + 39) & 0xFFFFFFFFFFFFFFE0uLL);
        *(v9 - 1) = v8;
        goto LABEL_19;
      }
LABEL_22:
      __scrt_throw_std_bad_array_new_length();
    }
    v9 = operator new(v6);
LABEL_19:
    *(_QWORD *)a1 = v9;
    *(_QWORD *)(a1 + 16) = v4;
    *(_QWORD *)(a1 + 24) = v5;
    memcpy_0(v9, v3, 2 * v4 + 2);
    return a1;
  }
  *(_QWORD *)(a1 + 16) = v4;
  *(_QWORD *)(a1 + 24) = 7;
  *(_OWORD *)a1 = *v3;
  return a1;
}

```

## disassembly

```asm
0x180010634  push    rbx
0x180010636  push    rbp
0x180010637  push    rsi
0x180010638  push    rdi
0x180010639  sub     rsp, 28h
0x18001063d  xorps   xmm0, xmm0
0x180010640  mov     rbx, rcx
0x180010643  movups  xmmword ptr [rcx], xmm0
0x180010646  mov     qword ptr [rcx+10h], 0
0x18001064e  mov     rsi, rdx
0x180010651  mov     qword ptr [rcx+18h], 0
0x180010659  mov     ecx, 7
0x18001065e  mov     rdi, [rdx+10h]
0x180010662  cmp     [rdx+18h], rcx
0x180010666  jbe     short loc_18001066B
0x180010668  mov     rsi, [rdx]
0x18001066b  mov     rbp, 7FFFFFFFFFFFFFFEh
0x180010675  cmp     rdi, rbp
0x180010678  ja      loc_18001073C
0x18001067e  cmp     rdi, rcx
0x180010681  ja      short loc_180010697
0x180010683  mov     [rbx+10h], rdi
0x180010687  mov     [rbx+18h], rcx
0x18001068b  movups  xmm0, xmmword ptr [rsi]
0x18001068e  movdqu  xmmword ptr [rbx], xmm0
0x180010692  jmp     loc_180010730
0x180010697  mov     rax, rdi
0x18001069a  or      rax, rcx
0x18001069d  cmp     rax, rbp
0x1800106a0  jbe     short loc_1800106D4
0x1800106a2  mov     rcx, 0FFFFFFFFFFFFFFFEh; Size
0x1800106a9  cmp     rcx, 1000h
0x1800106b0  jb      short loc_18001070D
0x1800106b2  lea     rax, [rcx+27h]
0x1800106b6  cmp     rax, rcx
0x1800106b9  jbe     loc_180010742
0x1800106bf  mov     rcx, rax; Size
0x1800106c2  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800106c7  mov     rcx, rax
0x1800106ca  test    rax, rax
0x1800106cd  jnz     short loc_1800106FF
0x1800106cf  lea     ecx, [rax+5]
0x1800106d2  int     29h; Win8: RtlFailFast(ecx)
0x1800106d4  mov     ecx, 0Ah
0x1800106d9  mov     rbp, rax
0x1800106dc  cmp     rax, rcx
0x1800106df  mov     rax, 7FFFFFFFFFFFFFFFh
0x1800106e9  cmovb   rbp, rcx
0x1800106ed  lea     rcx, [rbp+1]
0x1800106f1  cmp     rcx, rax
0x1800106f4  ja      short loc_180010742
0x1800106f6  add     rcx, rcx
0x1800106f9  jnz     short loc_1800106A9
0x1800106fb  xor     eax, eax
0x1800106fd  jmp     short loc_180010712
0x1800106ff  add     rax, 27h ; '''
0x180010703  and     rax, 0FFFFFFFFFFFFFFE0h
0x180010707  mov     [rax-8], rcx
0x18001070b  jmp     short loc_180010712
0x18001070d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180010712  lea     r8, ds:2[rdi*2]; Size
0x18001071a  mov     [rbx], rax
0x18001071d  mov     rdx, rsi; Src
0x180010720  mov     [rbx+10h], rdi
0x180010724  mov     rcx, rax; void *
0x180010727  mov     [rbx+18h], rbp
0x18001072b  call    memcpy_0
0x180010730  mov     rax, rbx
0x180010733  add     rsp, 28h
0x180010737  pop     rdi
0x180010738  pop     rsi
0x180010739  pop     rbp
0x18001073a  pop     rbx
0x18001073b  retn
0x18001073c  call    ?_Xlen_string@std@@YAXXZ; std::_Xlen_string(void)
0x180010742  call    ?__scrt_throw_std_bad_array_new_length@@YAXXZ; __scrt_throw_std_bad_array_new_length(void)
```
