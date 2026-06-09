# CalculateAppPoolHash(ushort const *,APP_POOL_HASH * *)

- ea: `0x18002bbf0`
- end: `0x18002bd9c`
- name: `?CalculateAppPoolHash@@YAJPEBGPEAPEAUAPP_POOL_HASH@@@Z`
- size: `428`
- prototype: `__int64 __fastcall(const unsigned __int16 *Src, struct APP_POOL_HASH **)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x18002bda4`

## callees

- `0x180002990`
- `0x1800029d0`
- `0x180003402`
- `0x180003460`
- `0x18002bbf0`

## import_xrefs

- `msvcrt!_wcslwr_s` at `0x18002bc92`
- `msvcrt!_wcslwr_s` at `0x18002bc92`
- `bcrypt!BCryptDestroyHash` at `0x18002bd3e`
- `bcrypt!BCryptDestroyHash` at `0x18002bd3e`
- `bcrypt!BCryptHashData` at `0x18002bd0a`
- `bcrypt!BCryptHashData` at `0x18002bd0a`
- `bcrypt!BCryptFinishHash` at `0x18002bd2a`
- `bcrypt!BCryptFinishHash` at `0x18002bd2a`
- `bcrypt!BCryptCreateHash` at `0x18002bce6`
- `bcrypt!BCryptCreateHash` at `0x18002bce6`

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
0x18002bbf0  mov     [rsp+arg_10], rbx
0x18002bbf5  mov     [rsp+arg_18], rbp
0x18002bbfa  push    rsi
0x18002bbfb  push    rdi
0x18002bbfc  push    r12
0x18002bbfe  push    r14
0x18002bc00  push    r15
0x18002bc02  sub     rsp, 70h
0x18002bc06  mov     rax, cs:__security_cookie
0x18002bc0d  xor     rax, rsp
0x18002bc10  mov     [rsp+98h+var_38], rax
0x18002bc15  xor     r12d, r12d
0x18002bc18  mov     rdi, rcx
0x18002bc1b  or      rcx, 0FFFFFFFFFFFFFFFFh
0x18002bc1f  mov     [rsp+98h+phHash], r12
0x18002bc24  mov     rsi, rcx
0x18002bc27  mov     [rdx], r12
0x18002bc2a  mov     r15, rdx
0x18002bc2d  inc     rsi
0x18002bc30  cmp     [rdi+rsi*2], r12w
0x18002bc35  jnz     short loc_18002BC2D
0x18002bc37  mov     eax, 0FFFFFFFFh
0x18002bc3c  cmp     rsi, rax
0x18002bc3f  jb      short loc_18002BC4B
0x18002bc41  mov     ebx, 80070057h
0x18002bc46  jmp     loc_18002BD74
0x18002bc4b  lea     r14, [rsi+1]
0x18002bc4f  mov     eax, 2
0x18002bc54  mul     r14
0x18002bc57  cmovb   rax, rcx
0x18002bc5b  mov     rcx, rax; Size
0x18002bc5e  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bc63  mov     rbp, rax
0x18002bc66  test    rax, rax
0x18002bc69  jnz     short loc_18002BC75
0x18002bc6b  mov     ebx, 8007000Eh
0x18002bc70  jmp     loc_18002BD74
0x18002bc75  lea     rbx, [rsi+rsi]
0x18002bc79  mov     rdx, rdi; Src
0x18002bc7c  mov     r8, rbx; Size
0x18002bc7f  mov     rcx, rbp; void *
0x18002bc82  call    memcpy_0
0x18002bc87  mov     rdx, r14; SizeInWords
0x18002bc8a  mov     [rbx+rbp], r12w
0x18002bc8f  mov     rcx, rbp; String
0x18002bc92  call    cs:__imp__wcslwr_s
0x18002bc98  test    eax, eax
0x18002bc9a  jz      short loc_18002BCA9
0x18002bc9c  mov     rdi, r12
0x18002bc9f  mov     ebx, 80070057h
0x18002bca4  jmp     loc_18002BD5B
0x18002bca9  mov     ecx, 14h; Size
0x18002bcae  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18002bcb3  mov     rdi, rax
0x18002bcb6  test    rax, rax
0x18002bcb9  jnz     short loc_18002BCC5
0x18002bcbb  mov     ebx, 8007000Eh
0x18002bcc0  jmp     loc_18002BD5B
0x18002bcc5  xor     r9d, r9d; cbHashObject
0x18002bcc8  mov     [rsp+98h+dwFlags], r12d; dwFlags
0x18002bccd  mov     [rsp+98h+cbSecret], r12d; cbSecret
0x18002bcd2  lea     rdx, [rsp+98h+phHash]; phHash
0x18002bcd7  xor     r8d, r8d; pbHashObject
0x18002bcda  mov     [rsp+98h+pbSecret], r12; pbSecret
0x18002bcdf  mov     ebx, r12d
0x18002bce2  lea     ecx, [r9+31h]; hAlgorithm
0x18002bce6  call    cs:__imp_BCryptCreateHash
0x18002bcec  mov     r14d, 7
0x18002bcf2  test    eax, eax
0x18002bcf4  jns     short loc_18002BCFB
0x18002bcf6  mov     ecx, r14d
0x18002bcf9  int     29h; Win8: RtlFailFast(ecx)
0x18002bcfb  mov     rcx, [rsp+98h+phHash]; hHash
0x18002bd00  lea     r8d, [rsi+rsi]; cbInput
0x18002bd04  xor     r9d, r9d; dwFlags
0x18002bd07  mov     rdx, rbp; pbInput
0x18002bd0a  call    cs:__imp_BCryptHashData
0x18002bd10  test    eax, eax
0x18002bd12  jns     short loc_18002BD19
0x18002bd14  mov     rcx, r14
0x18002bd17  int     29h; Win8: RtlFailFast(ecx)
0x18002bd19  mov     rcx, [rsp+98h+phHash]; hHash
0x18002bd1e  lea     rdx, [rsp+98h+pbOutput]; pbOutput
0x18002bd23  xor     r9d, r9d; dwFlags
0x18002bd26  lea     r8d, [r9+14h]; cbOutput
0x18002bd2a  call    cs:__imp_BCryptFinishHash
0x18002bd30  test    eax, eax
0x18002bd32  jns     short loc_18002BD39
0x18002bd34  mov     rcx, r14
0x18002bd37  int     29h; Win8: RtlFailFast(ecx)
0x18002bd39  mov     rcx, [rsp+98h+phHash]; hHash
0x18002bd3e  call    cs:__imp_BCryptDestroyHash
0x18002bd44  movups  xmm0, xmmword ptr [rsp+98h+pbOutput]
0x18002bd49  mov     [rsp+98h+phHash], r12
0x18002bd4e  movups  xmmword ptr [rdi], xmm0
0x18002bd51  mov     eax, [rsp+98h+var_40]
0x18002bd55  mov     [rdi+10h], eax
0x18002bd58  mov     [r15], rdi
0x18002bd5b  mov     rcx, rbp; Block
0x18002bd5e  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002bd63  test    ebx, ebx
0x18002bd65  jns     short loc_18002BD74
0x18002bd67  test    rdi, rdi
0x18002bd6a  jz      short loc_18002BD74
0x18002bd6c  mov     rcx, rdi; Block
0x18002bd6f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x18002bd74  mov     eax, ebx
0x18002bd76  mov     rcx, [rsp+98h+var_38]
0x18002bd7b  xor     rcx, rsp; StackCookie
0x18002bd7e  call    __security_check_cookie
0x18002bd83  lea     r11, [rsp+98h+var_28]
0x18002bd88  mov     rbx, [r11+40h]
0x18002bd8c  mov     rbp, [r11+48h]
0x18002bd90  mov     rsp, r11
0x18002bd93  pop     r15
0x18002bd95  pop     r14
0x18002bd97  pop     r12
0x18002bd99  pop     rdi
0x18002bd9a  pop     rsi
0x18002bd9b  retn
```
