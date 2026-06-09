# StringCchCopyExW(ushort *,unsigned __int64,ushort const *,ushort * *,unsigned __int64 *,ulong)

- ea: `0x14000e448`
- end: `0x14000e529`
- name: `?StringCchCopyExW@@YAJPEAG_KPEBGPEAPEAGPEA_KK@Z`
- size: `225`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned __int64, const unsigned __int16 *, unsigned __int16 **, unsigned __int64 *, unsigned int)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000dd14`

## callees

- `0x14000e448`
- `0x14000e79c`

## pseudocode

```c
__int64 __fastcall StringCchCopyExW(
        unsigned __int16 *a1,
        size_t a2,
        const unsigned __int16 *a3,
        unsigned __int16 **a4,
        unsigned __int64 *a5)
{
  const unsigned __int16 *v6; // rdi
  unsigned __int16 *v7; // rbx
  __int64 v8; // rdx
  _WORD *v9; // rcx
  _WORD *v10; // r8
  HRESULT v11; // r10d
  unsigned __int64 v12; // r11
  __int64 v13; // rax
  unsigned __int64 v14; // r8
  unsigned __int16 *v15; // r9
  __int64 v16; // rcx
  __int64 v17; // rdx
  unsigned __int16 *v18; // rcx

  v6 = a3;
  v7 = a1;
  v11 = StringExValidateDestW(a1, a2, (const size_t)a3, 0);
  if ( v11 < 0 )
  {
    if ( v12 )
      *v9 = 0;
  }
  else
  {
    if ( v8 )
    {
      v13 = 2147483646;
      v14 = v12;
      v15 = v7;
      v16 = 0;
      do
      {
        if ( !v13 )
          break;
        if ( !*v6 )
          break;
        *v15++ = *v6++;
        --v13;
        ++v16;
        --v14;
      }
      while ( v14 );
      v17 = v16 - 1;
      if ( v14 )
        v17 = v16;
      v11 = v14 == 0 ? 0x8007007A : 0;
      v7 += v17;
      v18 = v15 - 1;
      if ( v14 )
        v18 = v15;
      v12 -= v17;
      *v18 = 0;
    }
    else
    {
      v11 = 0;
      if ( *v10 )
      {
        if ( !v9 )
          return (unsigned int)-2147024809;
        v11 = -2147024774;
      }
    }
    if ( a4 )
      *a4 = v7;
    if ( a5 )
      *a5 = v12;
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x14000e448  push    rbx
0x14000e44a  push    rbp
0x14000e44b  push    rsi
0x14000e44c  push    rdi
0x14000e44d  sub     rsp, 28h
0x14000e451  mov     rsi, r9
0x14000e454  mov     rdi, r8
0x14000e457  xor     r9d, r9d; dwFlags
0x14000e45a  mov     r11, rdx
0x14000e45d  mov     rbx, rcx
0x14000e460  call    StringExValidateDestW
0x14000e465  xor     ebp, ebp
0x14000e467  mov     r10d, eax
0x14000e46a  test    eax, eax
0x14000e46c  js      loc_14000E515
0x14000e472  test    rdx, rdx
0x14000e475  jnz     short loc_14000E498
0x14000e477  mov     r10d, ebp
0x14000e47a  cmp     [r8], bp
0x14000e47e  jz      short loc_14000E4FE
0x14000e480  test    rcx, rcx
0x14000e483  jnz     short loc_14000E490
0x14000e485  mov     r10d, 80070057h
0x14000e48b  jmp     loc_14000E51D
0x14000e490  mov     r10d, 8007007Ah
0x14000e496  jmp     short loc_14000E4FE
0x14000e498  mov     eax, 7FFFFFFEh
0x14000e49d  mov     r8, r11
0x14000e4a0  mov     r9, rbx
0x14000e4a3  mov     rcx, rbp
0x14000e4a6  test    rax, rax
0x14000e4a9  jz      short loc_14000E4CB
0x14000e4ab  movzx   edx, word ptr [rdi]
0x14000e4ae  test    dx, dx
0x14000e4b1  jz      short loc_14000E4CB
0x14000e4b3  mov     [r9], dx
0x14000e4b7  add     rdi, 2
0x14000e4bb  add     r9, 2
0x14000e4bf  dec     rax
0x14000e4c2  inc     rcx
0x14000e4c5  sub     r8, 1
0x14000e4c9  jnz     short loc_14000E4A6
0x14000e4cb  lea     rdx, [rcx-1]
0x14000e4cf  test    r8, r8
0x14000e4d2  mov     rax, r8
0x14000e4d5  mov     r10d, 8007007Ah
0x14000e4db  cmovnz  rdx, rcx
0x14000e4df  neg     rax
0x14000e4e2  sbb     ecx, ecx
0x14000e4e4  not     ecx
0x14000e4e6  and     r10d, ecx
0x14000e4e9  lea     rbx, [rbx+rdx*2]
0x14000e4ed  test    r8, r8
0x14000e4f0  lea     rcx, [r9-2]
0x14000e4f4  cmovnz  rcx, r9
0x14000e4f8  sub     r11, rdx
0x14000e4fb  mov     [rcx], bp
0x14000e4fe  test    rsi, rsi
0x14000e501  jz      short loc_14000E506
0x14000e503  mov     [rsi], rbx
0x14000e506  mov     rax, [rsp+48h+arg_20]
0x14000e50b  test    rax, rax
0x14000e50e  jz      short loc_14000E51D
0x14000e510  mov     [rax], r11
0x14000e513  jmp     short loc_14000E51D
0x14000e515  test    r11, r11
0x14000e518  jz      short loc_14000E51D
0x14000e51a  mov     [rcx], bp
0x14000e51d  mov     eax, r10d
0x14000e520  add     rsp, 28h
0x14000e524  pop     rdi
0x14000e525  pop     rsi
0x14000e526  pop     rbp
0x14000e527  pop     rbx
0x14000e528  retn
```
