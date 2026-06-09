# CalculateAppPoolHash(ushort const *,APP_POOL_HASH * *)

- ea: `0x18000885c`
- end: `0x180008a08`
- name: `?CalculateAppPoolHash@@YAJPEBGPEAPEAUAPP_POOL_HASH@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, struct APP_POOL_HASH **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180007878`

## callees

- `0x180001008`
- `0x180001048`
- `0x18000885c`
- `0x180008c13`
- `0x180008c50`

## import_xrefs

- `msvcrt!_wcslwr_s` at `0x1800088fe`
- `msvcrt!_wcslwr_s` at `0x1800088fe`
- `bcrypt!BCryptDestroyHash` at `0x1800089aa`
- `bcrypt!BCryptDestroyHash` at `0x1800089aa`
- `bcrypt!BCryptHashData` at `0x180008976`
- `bcrypt!BCryptHashData` at `0x180008976`
- `bcrypt!BCryptCreateHash` at `0x180008952`
- `bcrypt!BCryptCreateHash` at `0x180008952`
- `bcrypt!BCryptFinishHash` at `0x180008996`
- `bcrypt!BCryptFinishHash` at `0x180008996`

## pseudocode

```c
__int64 __fastcall CalculateAppPoolHash(const unsigned __int16 *Src, struct APP_POOL_HASH **a2)
{
  unsigned __int64 v3; // rsi
  int v5; // ebx
  UCHAR *v6; // rax
  UCHAR *v7; // rbp
  struct APP_POOL_HASH *v8; // rdi
  BCRYPT_HASH_HANDLE phHash; // [rsp+40h] [rbp-58h] BYREF
  UCHAR pbOutput[16]; // [rsp+48h] [rbp-50h] BYREF
  int v12; // [rsp+58h] [rbp-40h]

  phHash = 0;
  v3 = -1;
  *a2 = 0;
  do
    ++v3;
  while ( Src[v3] );
  if ( v3 < 0xFFFFFFFF )
  {
    v6 = (UCHAR *)operator new(saturated_mul(v3 + 1, 2u));
    v7 = v6;
    if ( v6 )
    {
      memcpy_0(v6, Src, 2 * v3);
      *(_WORD *)&v7[2 * v3] = 0;
      if ( _wcslwr_s((wchar_t *)v7, v3 + 1) )
      {
        v8 = 0;
        v5 = -2147024809;
      }
      else
      {
        v8 = (struct APP_POOL_HASH *)operator new(0x14u);
        if ( v8 )
        {
          v5 = 0;
          if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &phHash, 0, 0, 0, 0, 0) < 0 )
            __fastfail(7u);
          if ( BCryptHashData(phHash, v7, 2 * v3, 0) < 0 )
            __fastfail(7u);
          if ( BCryptFinishHash(phHash, pbOutput, 0x14u, 0) < 0 )
            __fastfail(7u);
          BCryptDestroyHash(phHash);
          phHash = 0;
          *(_OWORD *)v8 = *(_OWORD *)pbOutput;
          *((_DWORD *)v8 + 4) = v12;
          *a2 = v8;
        }
        else
        {
          v5 = -2147024882;
        }
      }
      operator delete(v7);
      if ( v5 < 0 && v8 )
        operator delete(v8);
    }
    else
    {
      return (unsigned int)-2147024882;
    }
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x18000885c  mov     [rsp+arg_10], rbx
0x180008861  mov     [rsp+arg_18], rbp
0x180008866  push    rsi
0x180008867  push    rdi
0x180008868  push    r12
0x18000886a  push    r14
0x18000886c  push    r15
0x18000886e  sub     rsp, 70h
0x180008872  mov     rax, cs:__security_cookie
0x180008879  xor     rax, rsp
0x18000887c  mov     [rsp+98h+var_38], rax
0x180008881  xor     r12d, r12d
0x180008884  mov     rdi, rcx
0x180008887  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18000888b  mov     [rsp+98h+phHash], r12
0x180008890  mov     rsi, rcx
0x180008893  mov     [rdx], r12
0x180008896  mov     r15, rdx
0x180008899  inc     rsi
0x18000889c  cmp     [rdi+rsi*2], r12w
0x1800088a1  jnz     short loc_180008899
0x1800088a3  mov     eax, 0FFFFFFFFh
0x1800088a8  cmp     rsi, rax
0x1800088ab  jb      short loc_1800088B7
0x1800088ad  mov     ebx, 80070057h
0x1800088b2  jmp     loc_1800089E0
0x1800088b7  lea     r14, [rsi+1]
0x1800088bb  mov     eax, 2
0x1800088c0  mul     r14
0x1800088c3  cmovb   rax, rcx
0x1800088c7  mov     rcx, rax; Size
0x1800088ca  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x1800088cf  mov     rbp, rax
0x1800088d2  test    rax, rax
0x1800088d5  jnz     short loc_1800088E1
0x1800088d7  mov     ebx, 8007000Eh
0x1800088dc  jmp     loc_1800089E0
0x1800088e1  lea     rbx, [rsi+rsi]
0x1800088e5  mov     rdx, rdi; Src
0x1800088e8  mov     r8, rbx; Size
0x1800088eb  mov     rcx, rbp; void *
0x1800088ee  call    memcpy_0
0x1800088f3  mov     rdx, r14; SizeInWords
0x1800088f6  mov     [rbx+rbp], r12w
0x1800088fb  mov     rcx, rbp; String
0x1800088fe  call    cs:__imp__wcslwr_s
0x180008904  test    eax, eax
0x180008906  jz      short loc_180008915
0x180008908  mov     rdi, r12
0x18000890b  mov     ebx, 80070057h
0x180008910  jmp     loc_1800089C7
0x180008915  mov     ecx, 14h; Size
0x18000891a  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000891f  mov     rdi, rax
0x180008922  test    rax, rax
0x180008925  jnz     short loc_180008931
0x180008927  mov     ebx, 8007000Eh
0x18000892c  jmp     loc_1800089C7
0x180008931  xor     r9d, r9d; cbHashObject
0x180008934  mov     [rsp+98h+dwFlags], r12d; dwFlags
0x180008939  mov     [rsp+98h+cbSecret], r12d; cbSecret
0x18000893e  lea     rdx, [rsp+98h+phHash]; phHash
0x180008943  xor     r8d, r8d; pbHashObject
0x180008946  mov     [rsp+98h+pbSecret], r12; pbSecret
0x18000894b  mov     ebx, r12d
0x18000894e  lea     ecx, [r9+31h]; hAlgorithm
0x180008952  call    cs:__imp_BCryptCreateHash
0x180008958  mov     r14d, 7
0x18000895e  test    eax, eax
0x180008960  jns     short loc_180008967
0x180008962  mov     ecx, r14d
0x180008965  int     29h; Win8: RtlFailFast(ecx)
0x180008967  mov     rcx, [rsp+98h+phHash]; hHash
0x18000896c  lea     r8d, [rsi+rsi]; cbInput
0x180008970  xor     r9d, r9d; dwFlags
0x180008973  mov     rdx, rbp; pbInput
0x180008976  call    cs:__imp_BCryptHashData
0x18000897c  test    eax, eax
0x18000897e  jns     short loc_180008985
0x180008980  mov     rcx, r14
0x180008983  int     29h; Win8: RtlFailFast(ecx)
0x180008985  mov     rcx, [rsp+98h+phHash]; hHash
0x18000898a  lea     rdx, [rsp+98h+pbOutput]; pbOutput
0x18000898f  xor     r9d, r9d; dwFlags
0x180008992  lea     r8d, [r9+14h]; cbOutput
0x180008996  call    cs:__imp_BCryptFinishHash
0x18000899c  test    eax, eax
0x18000899e  jns     short loc_1800089A5
0x1800089a0  mov     rcx, r14
0x1800089a3  int     29h; Win8: RtlFailFast(ecx)
0x1800089a5  mov     rcx, [rsp+98h+phHash]; hHash
0x1800089aa  call    cs:__imp_BCryptDestroyHash
0x1800089b0  movups  xmm0, xmmword ptr [rsp+98h+pbOutput]
0x1800089b5  mov     [rsp+98h+phHash], r12
0x1800089ba  movups  xmmword ptr [rdi], xmm0
0x1800089bd  mov     eax, [rsp+98h+var_40]
0x1800089c1  mov     [rdi+10h], eax
0x1800089c4  mov     [r15], rdi
0x1800089c7  mov     rcx, rbp; Block
0x1800089ca  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800089cf  test    ebx, ebx
0x1800089d1  jns     short loc_1800089E0
0x1800089d3  test    rdi, rdi
0x1800089d6  jz      short loc_1800089E0
0x1800089d8  mov     rcx, rdi; Block
0x1800089db  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800089e0  mov     eax, ebx
0x1800089e2  mov     rcx, [rsp+98h+var_38]
0x1800089e7  xor     rcx, rsp; StackCookie
0x1800089ea  call    __security_check_cookie
0x1800089ef  lea     r11, [rsp+98h+var_28]
0x1800089f4  mov     rbx, [r11+40h]
0x1800089f8  mov     rbp, [r11+48h]
0x1800089fc  mov     rsp, r11
0x1800089ff  pop     r15
0x180008a01  pop     r14
0x180008a03  pop     r12
0x180008a05  pop     rdi
0x180008a06  pop     rsi
0x180008a07  retn
```
