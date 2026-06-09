# std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>>::assign(ushort const *,unsigned __int64)

- ea: `0x18000afa0`
- end: `0x18000b0a9`
- name: `?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@PEBG_K@Z`
- size: `265`
- prototype: `_QWORD *__fastcall(_QWORD *, char *Src, unsigned __int64)`
- caller_count: `5`
- callee_count: `5`
- tags: ``

## callers

- `0x1800081a0`
- `0x180008974`
- `0x180009250`
- `0x180009898`
- `0x180009b54`

## callees

- `0x180002766`
- `0x180007170`
- `0x18000a6a8`
- `0x18000ae28`
- `0x18000afa0`

## pseudocode

```c
_QWORD *__fastcall std::wstring::assign(_QWORD *a1, char *Src, unsigned __int64 a3)
{
  _QWORD *v5; // rbx
  char *v6; // rax
  _BYTE *v7; // rax
  void *v9; // rcx
  _WORD *v10; // rcx
  _WORD *v11; // rcx

  v5 = a1;
  if ( !Src )
    goto LABEL_13;
  v6 = a1[3] < 8u ? (char *)a1 : (char *)*a1;
  if ( Src < v6 )
    goto LABEL_13;
  if ( a1[3] >= 8u )
    a1 = (_QWORD *)*a1;
  if ( (char *)a1 + 2 * v5[2] <= Src )
  {
LABEL_13:
    if ( a3 > 0x7FFFFFFFFFFFFFFELL )
      std::wstring::_Xlen();
    if ( v5[3] >= a3 )
    {
      if ( !a3 )
      {
        if ( v5[3] < 8u )
          v10 = v5;
        else
          v10 = (_WORD *)*v5;
        v5[2] = 0;
        *v10 = 0;
        return v5;
      }
    }
    else
    {
      std::wstring::_Copy((const void **)v5, a3, v5[2]);
      if ( !a3 )
        return v5;
    }
    if ( v5[3] < 8u )
      v9 = v5;
    else
      v9 = (void *)*v5;
    memcpy_0(v9, Src, 2 * a3);
    if ( v5[3] < 8u )
      v11 = v5;
    else
      v11 = (_WORD *)*v5;
    v5[2] = a3;
    v11[a3] = 0;
    return v5;
  }
  if ( v5[3] < 8u )
    v7 = v5;
  else
    v7 = (_BYTE *)*v5;
  return std::wstring::assign(v5, v5, (Src - v7) >> 1, a3);
}

```

## disassembly

```asm
0x18000afa0  push    rbx
0x18000afa2  push    rsi
0x18000afa3  push    rdi
0x18000afa4  push    r14
0x18000afa6  sub     rsp, 28h
0x18000afaa  mov     rdi, r8
0x18000afad  mov     rsi, rdx
0x18000afb0  mov     rbx, rcx
0x18000afb3  test    rdx, rdx
0x18000afb6  jz      short loc_18000B00E
0x18000afb8  cmp     qword ptr [rcx+18h], 8
0x18000afbd  jb      short loc_18000AFC4
0x18000afbf  mov     rax, [rcx]
0x18000afc2  jmp     short loc_18000AFC7
0x18000afc4  mov     rax, rbx
0x18000afc7  cmp     rsi, rax
0x18000afca  jb      short loc_18000B00E
0x18000afcc  cmp     qword ptr [rcx+18h], 8
0x18000afd1  jb      short loc_18000AFD6
0x18000afd3  mov     rcx, [rcx]
0x18000afd6  mov     rax, [rbx+10h]
0x18000afda  lea     rcx, [rcx+rax*2]
0x18000afde  cmp     rcx, rsi
0x18000afe1  jbe     short loc_18000B00E
0x18000afe3  cmp     qword ptr [rbx+18h], 8
0x18000afe8  jb      short loc_18000AFEF
0x18000afea  mov     rax, [rbx]
0x18000afed  jmp     short loc_18000AFF2
0x18000afef  mov     rax, rbx
0x18000aff2  sub     rsi, rax
0x18000aff5  mov     r9, rdi
0x18000aff8  sar     rsi, 1
0x18000affb  mov     rdx, rbx
0x18000affe  mov     r8, rsi
0x18000b001  mov     rcx, rbx; void *
0x18000b004  call    ?assign@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV12@AEBV12@_K1@Z; std::wstring::assign(std::wstring const &,unsigned __int64,unsigned __int64)
0x18000b009  jmp     loc_18000B099
0x18000b00e  mov     rax, 7FFFFFFFFFFFFFFEh
0x18000b018  cmp     rdi, rax
0x18000b01b  ja      loc_18000B0A3
0x18000b021  cmp     [rbx+18h], rdi
0x18000b025  jnb     short loc_18000B047
0x18000b027  mov     r8, [rbx+10h]
0x18000b02b  mov     rdx, rdi
0x18000b02e  mov     rcx, rbx; Src
0x18000b031  call    ?_Copy@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAX_K0@Z; std::wstring::_Copy(unsigned __int64,unsigned __int64)
0x18000b036  test    rdi, rdi
0x18000b039  jz      short loc_18000B096
0x18000b03b  cmp     qword ptr [rbx+18h], 8
0x18000b040  jb      short loc_18000B06A
0x18000b042  mov     rcx, [rbx]
0x18000b045  jmp     short loc_18000B06D
0x18000b047  test    rdi, rdi
0x18000b04a  jnz     short loc_18000B03B
0x18000b04c  cmp     qword ptr [rbx+18h], 8
0x18000b051  jb      short loc_18000B058
0x18000b053  mov     rcx, [rbx]
0x18000b056  jmp     short loc_18000B05B
0x18000b058  mov     rcx, rbx
0x18000b05b  xor     eax, eax
0x18000b05d  mov     qword ptr [rbx+10h], 0
0x18000b065  mov     [rcx], ax
0x18000b068  jmp     short loc_18000B096
0x18000b06a  mov     rcx, rbx; void *
0x18000b06d  lea     r14, [rdi+rdi]
0x18000b071  mov     rdx, rsi; Src
0x18000b074  mov     r8, r14; Size
0x18000b077  call    memcpy_0
0x18000b07c  cmp     qword ptr [rbx+18h], 8
0x18000b081  jb      short loc_18000B088
0x18000b083  mov     rcx, [rbx]
0x18000b086  jmp     short loc_18000B08B
0x18000b088  mov     rcx, rbx
0x18000b08b  xor     eax, eax
0x18000b08d  mov     [rbx+10h], rdi
0x18000b091  mov     [r14+rcx], ax
0x18000b096  mov     rax, rbx
0x18000b099  add     rsp, 28h
0x18000b09d  pop     r14
0x18000b09f  pop     rdi
0x18000b0a0  pop     rsi
0x18000b0a1  pop     rbx
0x18000b0a2  retn
0x18000b0a3  call    ?_Xlen@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEBAXXZ; std::wstring::_Xlen(void)
```
