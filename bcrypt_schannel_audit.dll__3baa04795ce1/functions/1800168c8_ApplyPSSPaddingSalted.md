# ApplyPSSPaddingSalted

- ea: `0x1800168c8`
- end: `0x180016b5a`
- name: `ApplyPSSPaddingSalted`
- size: `658`
- prototype: ``
- caller_count: `1`
- callee_count: `12`
- tags: `broker_com_uri`

## callers

- `0x180016b60`

## callees

- `0x180004200`
- `0x180005060`
- `0x180005280`
- `0x180006020`
- `0x180006da0`
- `0x1800078e0`
- `0x180009430`
- `0x18000cc10`
- `0x180012cc4`
- `0x1800168c8`
- `0x18001b79d`
- `0x18001b7a9`

## string_xrefs

- `0x180016955`: `onecore\ds\security\cryptoapi\ncrypt\common\format.c`

## pseudocode

```c
__int64 __fastcall ApplyPSSPaddingSalted(
        void *a1,
        ULONG a2,
        ULONG a3,
        __int64 a4,
        ULONG cbBuffer,
        void *Src,
        size_t Size,
        _BYTE *a8,
        ULONG a9)
{
  size_t v9; // r12
  ULONG v11; // r13d
  __int64 v12; // rdi
  NTSTATUS v13; // ebx
  size_t v14; // rbx
  unsigned int v15; // esi
  __int64 v16; // rax
  UCHAR *v17; // r14
  __int64 v18; // rcx
  void *v19; // rdx
  UCHAR *v20; // rbp
  int v21; // eax
  _BYTE *v22; // rbp
  size_t v23; // rbx
  UCHAR *v24; // rdi
  __int64 i; // rdx
  __int64 dwFlags; // [rsp+30h] [rbp-68h]
  UCHAR *v28; // [rsp+40h] [rbp-58h]
  UCHAR *v29; // [rsp+40h] [rbp-58h]
  UCHAR *v30; // [rsp+48h] [rbp-50h]
  UCHAR *v31; // [rsp+58h] [rbp-40h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+B8h] [rbp+20h] BYREF

  v9 = cbBuffer;
  v11 = a9;
  phHash = 0;
  v12 = a3;
  if ( a9 < a2 + cbBuffer + 2 )
    return (unsigned int)-2146893822;
  v14 = (unsigned int)Size;
  v15 = a9 - a2 - 1;
  v16 = SafeAllocaAllocateFromHeap(a3 + cbBuffer + (_DWORD)Size + 8 + 2 * v15);
  v17 = (UCHAR *)v16;
  if ( v16 )
  {
    v19 = Src;
    v20 = (UCHAR *)(v16 + v12);
    v28 = v20;
    *(_QWORD *)v20 = 0;
    memcpy_0((void *)(v16 + v12 + 8), v19, v14);
    v30 = &v20[v14 + 8];
    v13 = BCryptGenRandom(0, v30, v9, 2u);
    if ( v13 >= 0 )
    {
      v21 = BCryptCreateHash(a1, &phHash, v17, v12, 0, 0, 0);
      v13 = v21;
      if ( v21 >= 0 )
      {
        v21 = BCryptHashData(phHash, v20, v9 + Size + 8, 0);
        v13 = v21;
        if ( v21 >= 0 )
        {
          v22 = a8;
          v31 = &a8[v15];
          v21 = BCryptFinishHash(phHash, v31, a2, 0);
          v13 = v21;
          if ( v21 >= 0 )
          {
            v29 = &v28[(unsigned int)(v9 + Size + 8)];
            v23 = v15 - (unsigned int)v9 - 1;
            memset_0(v29, 0, v23);
            v29[v23] = 1;
            memcpy_0(&v29[v23 + 1], v30, v9);
            v24 = &v29[v15];
            LODWORD(dwFlags) = v11 - a2 - 1;
            v21 = MaskGeneration(a1, a2, a3, v31, a2, v24, dwFlags);
            v13 = v21;
            if ( v21 >= 0 )
            {
              for ( i = 0; (unsigned int)i < v15; i = (unsigned int)(i + 1) )
                v22[i] = v29[i] ^ v24[i];
              *v22 &= ~0x80u;
              v22[v11 - 1] = -68;
              v13 = 0;
              goto LABEL_16;
            }
          }
        }
      }
      v18 = (unsigned int)v21;
    }
    else
    {
      v18 = (unsigned int)v13;
    }
  }
  else
  {
    v13 = -1073741801;
    v18 = 3221225495LL;
  }
  DebugTraceError(v18, "Status", "onecore\\ds\\security\\cryptoapi\\ncrypt\\common\\format.c");
LABEL_16:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( v17 )
    MSCryptFree(v17);
  return (unsigned int)v13;
}

```

## disassembly

```asm
0x1800168c8  mov     rax, rsp
0x1800168cb  mov     [rax+10h], rbx
0x1800168cf  mov     [rax+20h], r9
0x1800168d3  mov     [rax+18h], r8d
0x1800168d7  mov     [rax+8], rcx
0x1800168db  push    rbp
0x1800168dc  push    rsi
0x1800168dd  push    rdi
0x1800168de  push    r12
0x1800168e0  push    r13
0x1800168e2  push    r14
0x1800168e4  push    r15
0x1800168e6  sub     rsp, 60h
0x1800168ea  mov     r12d, [rsp+98h+cbBuffer]
0x1800168f2  mov     r15d, edx
0x1800168f5  mov     r13d, [rsp+98h+arg_40]
0x1800168fd  mov     qword ptr [rax+20h], 0
0x180016905  mov     edi, r8d
0x180016908  lea     eax, [r12+2]
0x18001690d  add     eax, edx
0x18001690f  cmp     r13d, eax
0x180016912  jnb     short loc_18001691E
0x180016914  mov     ebx, 80090002h
0x180016919  jmp     loc_180016B3F
0x18001691e  mov     ebx, dword ptr [rsp+98h+Size]
0x180016925  mov     esi, r13d
0x180016928  sub     esi, r15d
0x18001692b  dec     esi
0x18001692d  lea     eax, [rbx+8]
0x180016930  add     eax, r12d
0x180016933  lea     ecx, [rax+rsi*2]
0x180016936  add     ecx, edi
0x180016938  call    SafeAllocaAllocateFromHeap
0x18001693d  mov     r14, rax
0x180016940  test    rax, rax
0x180016943  jnz     short loc_18001696D
0x180016945  mov     ebx, 0C0000017h
0x18001694a  mov     r9d, 3B0h
0x180016950  mov     ecx, 0C0000017h
0x180016955  lea     r8, aOnecoreDsSecur_2; "onecore\\ds\\security\\cryptoapi\\ncryp"...
0x18001695c  lea     rdx, aStatus; "Status"
0x180016963  call    DebugTraceError
0x180016968  jmp     loc_180016B20
0x18001696d  mov     rdx, [rsp+98h+Src]; Src
0x180016975  lea     rbp, [rax+rdi]
0x180016979  xor     eax, eax
0x18001697b  mov     [rsp+98h+var_58], rbp
0x180016980  lea     rcx, [rbp+8]; void *
0x180016984  mov     [rbp+0], rax
0x180016988  mov     r8, rbx; Size
0x18001698b  call    memcpy_0
0x180016990  lea     rax, [rbx+8]
0x180016994  mov     r9d, 2; dwFlags
0x18001699a  add     rax, rbp
0x18001699d  mov     r8d, r12d; cbBuffer
0x1800169a0  mov     rdx, rax; pbBuffer
0x1800169a3  mov     [rsp+98h+var_50], rax
0x1800169a8  xor     ecx, ecx; hAlgorithm
0x1800169aa  call    BCryptGenRandom
0x1800169af  mov     ebx, eax
0x1800169b1  xor     eax, eax
0x1800169b3  test    ebx, ebx
0x1800169b5  jns     short loc_1800169C1
0x1800169b7  mov     r9d, 3C5h
0x1800169bd  mov     ecx, ebx
0x1800169bf  jmp     short loc_180016955
0x1800169c1  mov     rcx, [rsp+98h+hAlgorithm]; hAlgorithm
0x1800169c9  lea     rdx, [rsp+98h+phHash]; phHash
0x1800169d1  mov     [rsp+98h+dwFlags], eax; dwFlags
0x1800169d5  mov     r9d, edi; cbHashObject
0x1800169d8  mov     [rsp+98h+cbSecret], eax; cbSecret
0x1800169dc  mov     r8, r14; pbHashObject
0x1800169df  mov     [rsp+98h+pbSecret], rax; pbSecret
0x1800169e4  call    BCryptCreateHash
0x1800169e9  mov     ebx, eax
0x1800169eb  test    eax, eax
0x1800169ed  jns     short loc_1800169FC
0x1800169ef  mov     r9d, 3D9h
0x1800169f5  mov     ecx, eax
0x1800169f7  jmp     loc_180016955
0x1800169fc  mov     r8d, dword ptr [rsp+98h+Size]
0x180016a04  xor     r9d, r9d; dwFlags
0x180016a07  mov     rcx, [rsp+98h+phHash]; hHash
0x180016a0f  add     r8d, 8
0x180016a13  add     r8d, r12d; cbInput
0x180016a16  mov     rdx, rbp; pbInput
0x180016a19  call    BCryptHashData
0x180016a1e  mov     ebx, eax
0x180016a20  test    eax, eax
0x180016a22  jns     short loc_180016A2C
0x180016a24  mov     r9d, 3E3h
0x180016a2a  jmp     short loc_1800169F5
0x180016a2c  mov     rbp, [rsp+98h+arg_38]
0x180016a34  xor     r9d, r9d; dwFlags
0x180016a37  mov     rcx, [rsp+98h+phHash]; hHash
0x180016a3f  mov     r8d, r15d; cbOutput
0x180016a42  mov     eax, esi
0x180016a44  add     rax, rbp
0x180016a47  mov     rdx, rax; pbOutput
0x180016a4a  mov     [rsp+98h+var_40], rax
0x180016a4f  call    BCryptFinishHash
0x180016a54  mov     ebx, eax
0x180016a56  test    eax, eax
0x180016a58  jns     short loc_180016A62
0x180016a5a  mov     r9d, 3EDh
0x180016a60  jmp     short loc_1800169F5
0x180016a62  mov     eax, dword ptr [rsp+98h+Size]
0x180016a69  xor     edx, edx; Val
0x180016a6b  mov     rcx, [rsp+98h+var_58]
0x180016a70  add     eax, 8
0x180016a73  add     eax, r12d
0x180016a76  mov     rdi, r12
0x180016a79  add     rcx, rax; void *
0x180016a7c  mov     eax, esi
0x180016a7e  add     rax, rcx
0x180016a81  mov     [rsp+98h+var_58], rcx
0x180016a86  mov     [rsp+98h+var_48], rax
0x180016a8b  mov     eax, esi
0x180016a8d  sub     eax, r12d
0x180016a90  dec     eax
0x180016a92  mov     r8d, eax; Size
0x180016a95  mov     ebx, eax
0x180016a97  call    memset_0
0x180016a9c  mov     r12, [rsp+98h+var_58]
0x180016aa1  mov     r8, rdi; Size
0x180016aa4  mov     rdx, [rsp+98h+var_50]; Src
0x180016aa9  lea     rcx, [r12+1]
0x180016aae  mov     byte ptr [rbx+r12], 1
0x180016ab3  add     rcx, rbx; void *
0x180016ab6  call    memcpy_0
0x180016abb  mov     rdi, [rsp+98h+var_48]
0x180016ac0  mov     edx, r15d
0x180016ac3  mov     r9, [rsp+98h+var_40]
0x180016ac8  mov     r8d, [rsp+98h+arg_10]
0x180016ad0  mov     rcx, [rsp+98h+hAlgorithm]
0x180016ad8  mov     [rsp+98h+dwFlags], esi
0x180016adc  mov     qword ptr [rsp+98h+cbSecret], rdi
0x180016ae1  mov     dword ptr [rsp+98h+pbSecret], r15d
0x180016ae6  call    MaskGeneration
0x180016aeb  mov     ebx, eax
0x180016aed  test    eax, eax
0x180016aef  jns     short loc_180016AFC
0x180016af1  mov     r9d, 400h
0x180016af7  jmp     loc_1800169F5
0x180016afc  xor     edx, edx
0x180016afe  test    esi, esi
0x180016b00  jz      short loc_180016B12
0x180016b02  mov     al, [rdx+rdi]
0x180016b05  xor     al, [rdx+r12]
0x180016b09  mov     [rdx+rbp], al
0x180016b0c  inc     edx
0x180016b0e  cmp     edx, esi
0x180016b10  jb      short loc_180016B02
0x180016b12  and     byte ptr [rbp+0], 7Fh
0x180016b16  lea     eax, [r13-1]
0x180016b1a  mov     byte ptr [rax+rbp], 0BCh
0x180016b1e  xor     ebx, ebx
0x180016b20  mov     rcx, [rsp+98h+phHash]; hHash
0x180016b28  test    rcx, rcx
0x180016b2b  jz      short loc_180016B32
0x180016b2d  call    BCryptDestroyHash
0x180016b32  test    r14, r14
0x180016b35  jz      short loc_180016B3F
0x180016b37  mov     rcx, r14
0x180016b3a  call    MSCryptFree
0x180016b3f  mov     eax, ebx
0x180016b41  mov     rbx, [rsp+98h+arg_8]
0x180016b49  add     rsp, 60h
0x180016b4d  pop     r15
0x180016b4f  pop     r14
0x180016b51  pop     r13
0x180016b53  pop     r12
0x180016b55  pop     rdi
0x180016b56  pop     rsi
0x180016b57  pop     rbp
0x180016b58  retn
```
