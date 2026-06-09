# CDumpWriter::WriteSymmetricKey(void)

- ea: `0x180002a00`
- end: `0x180002b4f`
- name: `?WriteSymmetricKey@CDumpWriter@@AEAAJXZ`
- size: `335`
- prototype: `__int64 __fastcall(CDumpWriter *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops`

## callers

- `0x180002440`

## callees

- `0x180001424`
- `0x180001454`
- `0x180002a00`
- `0x180003010`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x180002a7d`
- `bcrypt!BCryptEncrypt` at `0x180002afa`
- `bcrypt!BCryptEncrypt` at `0x180002a7d`
- `bcrypt!BCryptEncrypt` at `0x180002afa`

## pseudocode

```c
__int64 __fastcall CDumpWriter::WriteSymmetricKey(CDumpWriter *this)
{
  ULONG cbOutput; // ebp
  UCHAR *pbOutput; // rdi
  NTSTATUS v5; // eax
  unsigned __int64 v6; // rdx
  int v7; // ebx
  NTSTATUS v8; // ebx
  ULONG pcbResult; // [rsp+70h] [rbp+8h] BYREF
  int v10; // [rsp+78h] [rbp+10h] BYREF
  UCHAR *v11; // [rsp+80h] [rbp+18h]

  cbOutput = *((_DWORD *)this + 26);
  pbOutput = (UCHAR *)operator new[](cbOutput, (const struct std::nothrow_t *)&std::nothrow);
  v11 = pbOutput;
  if ( !pbOutput )
    return 2147942414LL;
  pcbResult = 0;
  v5 = BCryptEncrypt(
         *((BCRYPT_KEY_HANDLE *)this + 12),
         (PUCHAR)this + 24,
         0x20u,
         0,
         0,
         0,
         pbOutput,
         cbOutput,
         &pcbResult,
         2u);
  v7 = v5 | 0x10000000;
  if ( v5 >= 0 )
    v7 = 0;
  if ( v7 >= 0 )
  {
    v10 = 0;
    v7 = (*(__int64 (__fastcall **)(_QWORD, UCHAR *, _QWORD, int *))(**((_QWORD **)this + 1) + 32LL))(
           *((_QWORD *)this + 1),
           pbOutput,
           pcbResult,
           &v10);
    if ( v7 >= 0 )
    {
      v8 = BCryptEncrypt(
             *((BCRYPT_KEY_HANDLE *)this + 12),
             (PUCHAR)this + 56,
             0x10u,
             0,
             0,
             0,
             pbOutput,
             cbOutput,
             &pcbResult,
             2u);
      if ( v8 >= 0 || (v7 = v8 | 0x10000000, v7 >= 0) )
      {
        v10 = 0;
        v7 = (*(__int64 (__fastcall **)(_QWORD, UCHAR *, _QWORD, int *))(**((_QWORD **)this + 1) + 32LL))(
               *((_QWORD *)this + 1),
               pbOutput,
               pcbResult,
               &v10);
      }
    }
  }
  operator delete(pbOutput, v6);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x180002a00  mov     [rsp+arg_18], rbx
0x180002a05  push    rbp
0x180002a06  push    rsi
0x180002a07  push    rdi
0x180002a08  sub     rsp, 50h
0x180002a0c  mov     rsi, rcx
0x180002a0f  mov     ebp, [rcx+68h]
0x180002a12  mov     ecx, ebp; unsigned __int64
0x180002a14  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002a1b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180002a20  mov     rdi, rax
0x180002a23  mov     [rsp+68h+arg_10], rax
0x180002a2b  test    rax, rax
0x180002a2e  jnz     short loc_180002A3A
0x180002a30  mov     eax, 8007000Eh
0x180002a35  jmp     loc_180002B3F
0x180002a3a  mov     [rsp+68h+arg_0], 0
0x180002a42  lea     rdx, [rsi+18h]; pbInput
0x180002a46  mov     [rsp+68h+dwFlags], 2; dwFlags
0x180002a4e  lea     rax, [rsp+68h+arg_0]
0x180002a53  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180002a58  mov     [rsp+68h+cbOutput], ebp; cbOutput
0x180002a5c  mov     [rsp+68h+pbOutput], rdi; pbOutput
0x180002a61  mov     [rsp+68h+cbIV], 0; cbIV
0x180002a69  mov     [rsp+68h+pbIV], 0; pbIV
0x180002a72  xor     r9d, r9d; pPaddingInfo
0x180002a75  lea     r8d, [r9+20h]; cbInput
0x180002a79  mov     rcx, [rsi+60h]; hKey
0x180002a7d  call    cs:__imp_BCryptEncrypt
0x180002a83  mov     ebx, eax
0x180002a85  bts     ebx, 1Ch
0x180002a89  xor     ecx, ecx
0x180002a8b  test    eax, eax
0x180002a8d  cmovns  ebx, ecx
0x180002a90  test    ebx, ebx
0x180002a92  js      loc_180002B35
0x180002a98  mov     [rsp+68h+arg_8], ecx
0x180002a9c  mov     rcx, [rsi+8]
0x180002aa0  mov     rax, [rcx]
0x180002aa3  lea     r9, [rsp+68h+arg_8]
0x180002aa8  mov     r8d, [rsp+68h+arg_0]
0x180002aad  mov     rdx, rdi
0x180002ab0  mov     rax, [rax+20h]
0x180002ab4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ab9  mov     ebx, eax
0x180002abb  test    eax, eax
0x180002abd  js      short loc_180002B35
0x180002abf  lea     rdx, [rsi+38h]; pbInput
0x180002ac3  mov     [rsp+68h+dwFlags], 2; dwFlags
0x180002acb  lea     rax, [rsp+68h+arg_0]
0x180002ad0  mov     [rsp+68h+pcbResult], rax; pcbResult
0x180002ad5  mov     [rsp+68h+cbOutput], ebp; cbOutput
0x180002ad9  mov     [rsp+68h+pbOutput], rdi; pbOutput
0x180002ade  mov     [rsp+68h+cbIV], 0; cbIV
0x180002ae6  mov     [rsp+68h+pbIV], 0; pbIV
0x180002aef  xor     r9d, r9d; pPaddingInfo
0x180002af2  lea     r8d, [r9+10h]; cbInput
0x180002af6  mov     rcx, [rsi+60h]; hKey
0x180002afa  call    cs:__imp_BCryptEncrypt
0x180002b00  mov     ebx, eax
0x180002b02  test    eax, eax
0x180002b04  jns     short loc_180002B0E
0x180002b06  or      ebx, 10000000h
0x180002b0c  jl      short loc_180002B35
0x180002b0e  mov     [rsp+68h+arg_8], 0
0x180002b16  mov     rcx, [rsi+8]
0x180002b1a  mov     rax, [rcx]
0x180002b1d  lea     r9, [rsp+68h+arg_8]
0x180002b22  mov     r8d, [rsp+68h+arg_0]
0x180002b27  mov     rdx, rdi
0x180002b2a  mov     rax, [rax+20h]
0x180002b2e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002b33  mov     ebx, eax
0x180002b35  mov     rcx, rdi; void *
0x180002b38  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002b3d  mov     eax, ebx
0x180002b3f  mov     rbx, [rsp+68h+arg_18]
0x180002b47  add     rsp, 50h
0x180002b4b  pop     rdi
0x180002b4c  pop     rsi
0x180002b4d  pop     rbp
0x180002b4e  retn
```
