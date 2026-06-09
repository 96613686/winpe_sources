# CBdeCfgConsole::BdeCfgpLoadBrandedResourceString(uint,ushort * *)

- ea: `0x140001aa4`
- end: `0x140001bee`
- name: `?BdeCfgpLoadBrandedResourceString@CBdeCfgConsole@@AEAAJIPEAPEAG@Z`
- size: `330`
- prototype: `__int64 __fastcall(CBdeCfgConsole *this, __int64, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops`

## callers

- `0x140003884`

## callees

- `0x140001008`
- `0x1400013c8`
- `0x140001aa4`

## import_xrefs

- `KERNEL32!GlobalFree` at `0x140001bb0`
- `KERNEL32!GlobalFree` at `0x140001bb0`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140001ad8`
- `BDEHDCFGLIB!BdeCfgLoadResourceString` at `0x140001ad8`
- `WINBRAND!BrandingFormatString` at `0x140001aed`
- `WINBRAND!BrandingFormatString` at `0x140001aed`

## pseudocode

```c
__int64 __fastcall CBdeCfgConsole::BdeCfgpLoadBrandedResourceString(
        CBdeCfgConsole *this,
        __int64 a2,
        unsigned __int16 **a3)
{
  unsigned __int16 *v3; // r14
  int ResourceString; // ebx
  __int64 v6; // rax
  void *v7; // rbp
  unsigned __int64 v8; // rdi
  unsigned __int64 v9; // rsi
  size_t v10; // rax
  unsigned __int16 *v11; // rax
  unsigned __int16 *v12; // rcx
  unsigned __int16 *v13; // rcx
  signed int v14; // eax
  void *Block; // [rsp+50h] [rbp+8h] BYREF

  Block = 0;
  v3 = 0;
  *a3 = 0;
  ResourceString = BdeCfgLoadResourceString(0x197u, (unsigned __int16 **)&Block);
  if ( ResourceString >= 0 )
  {
    v6 = BrandingFormatString(Block);
    v7 = (void *)v6;
    if ( !v6 )
    {
      ResourceString = -1063256037;
      goto LABEL_22;
    }
    v8 = -1;
    do
      ++v8;
    while ( *(_WORD *)(v6 + 2 * v8) );
    v9 = v8 + 1;
    v10 = 2 * (v8 + 1);
    if ( !is_mul_ok(v8 + 1, 2u) )
      v10 = -1;
    v11 = (unsigned __int16 *)operator new(v10, (const struct std::nothrow_t *)std::nothrow);
    v3 = v11;
    ResourceString = -2147024809;
    if ( v8 == -1 )
    {
      v14 = -2147024809;
    }
    else
    {
      if ( v9 > 0x7FFFFFFF )
      {
        *v11 = 0;
        goto LABEL_21;
      }
      if ( v8 > 0x7FFFFFFE )
      {
        *v11 = 0;
LABEL_21:
        GlobalFree(v7);
        goto LABEL_22;
      }
      v12 = (unsigned __int16 *)v7;
      do
      {
        if ( !v8 )
          break;
        if ( !*v12 )
          break;
        *v11++ = *v12++;
        --v8;
        --v9;
      }
      while ( v9 );
      v13 = v11 - 1;
      if ( v9 )
        v13 = v11;
      v14 = v9 == 0 ? 0x8007007A : 0;
      *v13 = 0;
    }
    ResourceString = v14;
    if ( v14 >= 0 )
    {
      *a3 = v3;
      v3 = 0;
    }
    goto LABEL_21;
  }
LABEL_22:
  operator delete(Block);
  operator delete(v3);
  return (unsigned int)ResourceString;
}

```

## disassembly

```asm
0x140001aa4  mov     rax, rsp
0x140001aa7  mov     [rax+10h], rbx
0x140001aab  mov     [rax+18h], rbp
0x140001aaf  mov     [rax+8], rcx
0x140001ab3  push    rsi
0x140001ab4  push    rdi
0x140001ab5  push    r12
0x140001ab7  push    r14
0x140001ab9  push    r15
0x140001abb  sub     rsp, 20h
0x140001abf  xor     r12d, r12d
0x140001ac2  lea     rdx, [rax+8]
0x140001ac6  mov     ecx, 197h
0x140001acb  mov     [rax+8], r12
0x140001acf  mov     r14d, r12d
0x140001ad2  mov     [r8], r12
0x140001ad5  mov     r15, r8
0x140001ad8  call    cs:__imp_?BdeCfgLoadResourceString@@YAJIPEAPEAG@Z; BdeCfgLoadResourceString(uint,ushort * *)
0x140001ade  mov     ebx, eax
0x140001ae0  test    eax, eax
0x140001ae2  js      loc_140001BB6
0x140001ae8  mov     rcx, [rsp+48h+Block]
0x140001aed  call    cs:__imp_BrandingFormatString
0x140001af3  mov     rbp, rax
0x140001af6  test    rax, rax
0x140001af9  jnz     short loc_140001B05
0x140001afb  mov     ebx, 0C0A0001Bh
0x140001b00  jmp     loc_140001BB6
0x140001b05  or      rcx, 0FFFFFFFFFFFFFFFFh
0x140001b09  mov     rdi, rcx
0x140001b0c  inc     rdi
0x140001b0f  cmp     [rax+rdi*2], r12w
0x140001b14  jnz     short loc_140001B0C
0x140001b16  lea     rsi, [rdi+1]
0x140001b1a  mov     eax, 2
0x140001b1f  mul     rsi
0x140001b22  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x140001b29  cmovb   rax, rcx
0x140001b2d  mov     rcx, rax; unsigned __int64
0x140001b30  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x140001b35  mov     r14, rax
0x140001b38  mov     ebx, 80070057h
0x140001b3d  test    rsi, rsi
0x140001b40  jz      loc_140001BE1
0x140001b46  cmp     rsi, 7FFFFFFFh
0x140001b4d  ja      loc_140001BE8
0x140001b53  cmp     rdi, 7FFFFFFEh
0x140001b5a  jbe     short loc_140001B62
0x140001b5c  mov     [rax], r12w
0x140001b60  jmp     short loc_140001BAD
0x140001b62  mov     rcx, rbp
0x140001b65  test    rdi, rdi
0x140001b68  jz      short loc_140001B86
0x140001b6a  movzx   edx, word ptr [rcx]
0x140001b6d  test    dx, dx
0x140001b70  jz      short loc_140001B86
0x140001b72  mov     [rax], dx
0x140001b75  add     rcx, 2
0x140001b79  add     rax, 2
0x140001b7d  dec     rdi
0x140001b80  sub     rsi, 1
0x140001b84  jnz     short loc_140001B65
0x140001b86  lea     rcx, [rax-2]
0x140001b8a  test    rsi, rsi
0x140001b8d  cmovnz  rcx, rax
0x140001b91  neg     rsi
0x140001b94  sbb     eax, eax
0x140001b96  not     eax
0x140001b98  and     eax, 8007007Ah
0x140001b9d  mov     [rcx], r12w
0x140001ba1  mov     ebx, eax
0x140001ba3  test    eax, eax
0x140001ba5  js      short loc_140001BAD
0x140001ba7  mov     [r15], r14
0x140001baa  mov     r14, r12
0x140001bad  mov     rcx, rbp; hMem
0x140001bb0  call    cs:__imp_GlobalFree
0x140001bb6  mov     rcx, [rsp+48h+Block]; Block
0x140001bbb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001bc0  mov     rcx, r14; Block
0x140001bc3  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140001bc8  mov     rbp, [rsp+48h+arg_10]
0x140001bcd  mov     eax, ebx
0x140001bcf  mov     rbx, [rsp+48h+arg_8]
0x140001bd4  add     rsp, 20h
0x140001bd8  pop     r15
0x140001bda  pop     r14
0x140001bdc  pop     r12
0x140001bde  pop     rdi
0x140001bdf  pop     rsi
0x140001be0  retn
0x140001be1  mov     eax, ebx
0x140001be3  test    rsi, rsi
0x140001be6  jz      short loc_140001BA1
0x140001be8  mov     [r14], r12w
0x140001bec  jmp     short loc_140001BAD
```
