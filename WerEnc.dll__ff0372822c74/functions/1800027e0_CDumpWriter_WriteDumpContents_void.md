# CDumpWriter::WriteDumpContents(void)

- ea: `0x1800027e0`
- end: `0x18000294e`
- name: `?WriteDumpContents@CDumpWriter@@AEAAJXZ`
- size: `366`
- prototype: `__int64 __fastcall(BCRYPT_KEY_HANDLE *this)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops`

## callers

- `0x180002440`

## callees

- `0x180001424`
- `0x180001454`
- `0x180001fe4`
- `0x1800027e0`
- `0x180003010`

## import_xrefs

- `bcrypt!BCryptEncrypt` at `0x1800028c9`
- `bcrypt!BCryptEncrypt` at `0x1800028c9`

## pseudocode

```c
__int64 __fastcall CDumpWriter::WriteDumpContents(BCRYPT_KEY_HANDLE *this)
{
  UCHAR *v2; // rsi
  void *v3; // rax
  unsigned __int64 v4; // rdx
  void *pbOutput; // rdi
  int v6; // eax
  int v7; // ebx
  ULONG v8; // ecx
  NTSTATUS v9; // ebx
  ULONG v11; // [rsp+98h] [rbp+38h] BYREF
  ULONG pcbResult; // [rsp+A0h] [rbp+40h] BYREF
  int v13; // [rsp+A8h] [rbp+48h] BYREF

  v2 = (UCHAR *)operator new[](0x40000u, (const struct std::nothrow_t *)&std::nothrow);
  v3 = operator new[](0x40000u, (const struct std::nothrow_t *)&std::nothrow);
  pbOutput = v3;
  if ( v2 && v3 )
  {
    do
    {
      memset_0(pbOutput, 0, 0x40000u);
      v11 = 0;
      v6 = (*(__int64 (__fastcall **)(BCRYPT_KEY_HANDLE, UCHAR *, __int64, ULONG *))(*(_QWORD *)*this + 24LL))(
             *this,
             v2,
             0x40000,
             &v11);
      v7 = v6;
      if ( v6 >= 0 && !v11 )
        break;
      v8 = (v11 + 15) & 0xFFFFFFF0;
      v11 = v8;
      if ( v6 < 0 )
        break;
      pcbResult = 0;
      v9 = BCryptEncrypt(this[11], v2, v8, 0, (PUCHAR)this + 56, 0x10u, (PUCHAR)pbOutput, 0x40000u, &pcbResult, 0);
      if ( v9 < 0 )
      {
        v7 = v9 | 0x10000000;
        break;
      }
      v13 = 0;
      v7 = (*(__int64 (__fastcall **)(BCRYPT_KEY_HANDLE, void *, _QWORD, int *))(*(_QWORD *)this[1] + 32LL))(
             this[1],
             pbOutput,
             pcbResult,
             &v13);
      if ( pcbResult != v13 )
      {
        v7 = -2147024883;
        break;
      }
    }
    while ( v7 >= 0 );
  }
  else
  {
    v7 = -2147024882;
  }
  if ( pbOutput )
    operator delete(pbOutput, v4);
  if ( v2 )
    operator delete(v2, v4);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x1800027e0  mov     [rsp-28h+arg_0], rbx
0x1800027e5  push    rbp
0x1800027e6  push    rsi
0x1800027e7  push    rdi
0x1800027e8  push    r12
0x1800027ea  push    r14
0x1800027ec  mov     rbp, rsp
0x1800027ef  sub     rsp, 60h
0x1800027f3  mov     r14, rcx
0x1800027f6  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x1800027fd  mov     r12d, 40000h
0x180002803  mov     ecx, r12d; unsigned __int64
0x180002806  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x18000280b  mov     rsi, rax
0x18000280e  mov     [rbp+var_10], rax
0x180002812  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180002819  mov     ecx, r12d; unsigned __int64
0x18000281c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180002821  mov     rdi, rax
0x180002824  mov     [rbp+var_8], rax
0x180002828  test    rsi, rsi
0x18000282b  jz      loc_180002918
0x180002831  test    rax, rax
0x180002834  jz      loc_180002918
0x18000283a  mov     r8, r12; Size
0x18000283d  xor     edx, edx; Val
0x18000283f  mov     rcx, rdi; void *
0x180002842  call    memset_0
0x180002847  mov     [rbp+arg_8], 0
0x18000284e  mov     rcx, [r14]
0x180002851  mov     rax, [rcx]
0x180002854  lea     r9, [rbp+arg_8]
0x180002858  mov     r8d, r12d
0x18000285b  mov     rdx, rsi
0x18000285e  mov     rax, [rax+18h]
0x180002862  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002867  mov     ebx, eax
0x180002869  mov     ecx, [rbp+arg_8]
0x18000286c  test    eax, eax
0x18000286e  js      short loc_180002878
0x180002870  test    ecx, ecx
0x180002872  jz      loc_18000291D
0x180002878  add     ecx, 0Fh
0x18000287b  and     ecx, 0FFFFFFF0h
0x18000287e  mov     [rbp+arg_8], ecx
0x180002881  test    eax, eax
0x180002883  js      loc_18000291D
0x180002889  mov     [rbp+arg_10], 0
0x180002890  lea     rax, [r14+38h]
0x180002894  mov     [rsp+60h+dwFlags], 0; dwFlags
0x18000289c  lea     rdx, [rbp+arg_10]
0x1800028a0  mov     [rsp+60h+pcbResult], rdx; pcbResult
0x1800028a5  mov     [rsp+60h+cbOutput], r12d; cbOutput
0x1800028aa  mov     [rsp+60h+pbOutput], rdi; pbOutput
0x1800028af  mov     [rsp+60h+cbIV], 10h; cbIV
0x1800028b7  mov     [rsp+60h+pbIV], rax; pbIV
0x1800028bc  xor     r9d, r9d; pPaddingInfo
0x1800028bf  mov     r8d, ecx; cbInput
0x1800028c2  mov     rdx, rsi; pbInput
0x1800028c5  mov     rcx, [r14+58h]; hKey
0x1800028c9  call    cs:__imp_BCryptEncrypt
0x1800028cf  mov     ebx, eax
0x1800028d1  test    eax, eax
0x1800028d3  js      short loc_180002912
0x1800028d5  mov     [rbp+arg_18], 0
0x1800028dc  mov     rcx, [r14+8]
0x1800028e0  mov     rax, [rcx]
0x1800028e3  lea     r9, [rbp+arg_18]
0x1800028e7  mov     r8d, [rbp+arg_10]
0x1800028eb  mov     rdx, rdi
0x1800028ee  mov     rax, [rax+20h]
0x1800028f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800028f7  mov     ebx, eax
0x1800028f9  mov     eax, [rbp+arg_18]
0x1800028fc  cmp     [rbp+arg_10], eax
0x1800028ff  jnz     short loc_18000290B
0x180002901  test    ebx, ebx
0x180002903  jns     loc_18000283A
0x180002909  jmp     short loc_18000291D
0x18000290b  mov     ebx, 8007000Dh
0x180002910  jmp     short loc_18000291D
0x180002912  bts     ebx, 1Ch
0x180002916  jmp     short loc_18000291D
0x180002918  mov     ebx, 8007000Eh
0x18000291d  test    rdi, rdi
0x180002920  jz      short loc_18000292B
0x180002922  mov     rcx, rdi; void *
0x180002925  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000292a  nop
0x18000292b  test    rsi, rsi
0x18000292e  jz      short loc_180002938
0x180002930  mov     rcx, rsi; void *
0x180002933  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180002938  mov     eax, ebx
0x18000293a  mov     rbx, [rsp+60h+arg_0]
0x180002942  add     rsp, 60h
0x180002946  pop     r14
0x180002948  pop     r12
0x18000294a  pop     rdi
0x18000294b  pop     rsi
0x18000294c  pop     rbp
0x18000294d  retn
```
