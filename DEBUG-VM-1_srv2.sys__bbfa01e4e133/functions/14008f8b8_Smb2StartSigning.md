# Smb2StartSigning

- ea: `0x14008f8b8`
- end: `0x14008faaf`
- name: `Smb2StartSigning`
- size: `503`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x1400921f0`

## callees

- `0x14000a9e8`
- `0x14000aab4`
- `0x140038490`
- `0x140038680`
- `0x14008f8b8`

## import_xrefs

- `srvnet!SmbCryptoKeyedHashGetHashAlgorithmMetadata` at `0x14008f91c`
- `srvnet!SmbCryptoKeyedHashGetHashAlgorithmMetadata` at `0x14008f91c`
- `srvnet!SmbCryptoCreateSigningKey` at `0x14008f996`
- `srvnet!SmbCryptoCreateSigningKey` at `0x14008f996`
- `ksecdd!BCryptCreateHash` at `0x14008f9d8`
- `ksecdd!BCryptCreateHash` at `0x14008f9d8`

## pseudocode

```c
__int64 __fastcall Smb2StartSigning(__int64 a1, const void *a2, unsigned int a3)
{
  __int64 v4; // rdi
  size_t v5; // r15
  __int64 v6; // rcx
  __int64 v7; // r13
  unsigned int v8; // esi
  __int64 HashAlgorithmMetadata; // rax
  ULONG v10; // r14d
  UCHAR *SigningHashObject; // rbp
  __int64 v12; // rbx
  NTSTATUS v13; // esi
  __int128 *p_pbSecret; // rcx
  size_t v16; // r8
  __int16 v17; // [rsp+40h] [rbp-68h]
  int v18; // [rsp+44h] [rbp-64h]
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-60h] BYREF
  BCRYPT_ALG_HANDLE hAlgorithm; // [rsp+50h] [rbp-58h]
  __int128 pbSecret; // [rsp+58h] [rbp-50h] BYREF

  v4 = *(_QWORD *)(a1 + 560);
  v5 = a3;
  v6 = *(_QWORD *)(*(_QWORD *)(a1 + 96) + 496LL);
  v7 = *(_QWORD *)(*(_QWORD *)(v4 + 32) + 320LL);
  if ( v7 )
    v8 = *(_DWORD *)(v6 + 128);
  else
    v8 = 0;
  phHash = 0;
  HashAlgorithmMetadata = SmbCryptoKeyedHashGetHashAlgorithmMetadata(*(unsigned int *)(v6 + 140));
  v10 = *(_DWORD *)(HashAlgorithmMetadata + 12);
  hAlgorithm = *(BCRYPT_ALG_HANDLE *)HashAlgorithmMetadata;
  v17 = *(_WORD *)(HashAlgorithmMetadata + 16);
  v18 = *(_DWORD *)(HashAlgorithmMetadata + 8);
  if ( !v10 )
    __int2c();
  SigningHashObject = (UCHAR *)Smb2AllocateSigningHashObject(v10);
  if ( !SigningHashObject )
    return 3221225626LL;
  v12 = 16;
  if ( *(_WORD *)(*(_QWORD *)(v4 + 32) + 288LL) < 0x300u )
  {
    v16 = v5;
    pbSecret = 0;
    if ( (unsigned int)v5 >= 0x10 )
      v16 = 16;
    memmove(&pbSecret, a2, v16);
  }
  else
  {
    v13 = SmbCryptoCreateSigningKey(a2, (unsigned int)v5, v7, v8, &pbSecret, 16);
    if ( v13 < 0 )
      goto LABEL_9;
  }
  v13 = BCryptCreateHash(hAlgorithm, &phHash, SigningHashObject, v10, (PUCHAR)&pbSecret, 0x10u, 0);
LABEL_9:
  p_pbSecret = &pbSecret;
  do
  {
    *(_BYTE *)p_pbSecret = 0;
    p_pbSecret = (__int128 *)((char *)p_pbSecret + 1);
    --v12;
  }
  while ( v12 );
  if ( v13 >= 0 )
  {
    *(_QWORD *)(*(_QWORD *)(v4 + 144) + 184LL) = phHash;
    *(_QWORD *)(*(_QWORD *)(v4 + 144) + 200LL) = SigningHashObject;
    *(_DWORD *)(*(_QWORD *)(v4 + 144) + 192LL) = v10;
    *(_DWORD *)(*(_QWORD *)(v4 + 144) + 196LL) = v18;
    *(_WORD *)(*(_QWORD *)(v4 + 144) + 208LL) = v17;
    return 0;
  }
  else
  {
    Smb2DeallocateSigningHashObject(SigningHashObject);
    return (unsigned int)v13;
  }
}

```

## disassembly

```asm
0x14008f8b8  mov     [rsp+arg_18], rbx
0x14008f8bd  push    rbp
0x14008f8be  push    rsi
0x14008f8bf  push    rdi
0x14008f8c0  push    r12
0x14008f8c2  push    r13
0x14008f8c4  push    r14
0x14008f8c6  push    r15
0x14008f8c8  sub     rsp, 70h
0x14008f8cc  mov     rax, cs:__security_cookie
0x14008f8d3  xor     rax, rsp
0x14008f8d6  mov     [rsp+0A8h+var_40], rax
0x14008f8db  mov     rax, [rcx+60h]
0x14008f8df  mov     r12, rdx
0x14008f8e2  mov     rdi, [rcx+230h]
0x14008f8e9  mov     r15d, r8d
0x14008f8ec  mov     rcx, [rax+1F0h]
0x14008f8f3  mov     rax, [rdi+20h]
0x14008f8f7  mov     r13, [rax+140h]
0x14008f8fe  test    r13, r13
0x14008f901  jz      loc_14008F9F0
0x14008f907  mov     esi, [rcx+80h]
0x14008f90d  mov     [rsp+0A8h+phHash], 0
0x14008f916  mov     ecx, [rcx+8Ch]
0x14008f91c  call    cs:__imp_SmbCryptoKeyedHashGetHashAlgorithmMetadata
0x14008f923  nop     dword ptr [rax+rax+00h]
0x14008f928  mov     rcx, [rax]
0x14008f92b  mov     r14d, [rax+0Ch]
0x14008f92f  mov     [rsp+0A8h+hAlgorithm], rcx
0x14008f934  mov     ecx, [rax+8]
0x14008f937  movzx   eax, word ptr [rax+10h]
0x14008f93b  mov     [rsp+0A8h+var_68], ax
0x14008f940  mov     [rsp+0A8h+var_64], ecx
0x14008f944  test    r14d, r14d
0x14008f947  jz      loc_14008FA32
0x14008f94d  mov     ecx, r14d
0x14008f950  call    Smb2AllocateSigningHashObject
0x14008f955  mov     rbp, rax
0x14008f958  test    rax, rax
0x14008f95b  jz      loc_14008F9F7
0x14008f961  mov     rax, [rdi+20h]
0x14008f965  mov     ecx, 300h
0x14008f96a  mov     ebx, 10h
0x14008f96f  cmp     [rax+120h], cx
0x14008f976  jb      loc_14008FA39
0x14008f97c  lea     rax, [rsp+0A8h+var_50]
0x14008f981  mov     [rsp+0A8h+cbSecret], ebx
0x14008f985  mov     r9d, esi
0x14008f988  mov     [rsp+0A8h+pbSecret], rax
0x14008f98d  mov     r8, r13
0x14008f990  mov     edx, r15d
0x14008f993  mov     rcx, r12
0x14008f996  call    cs:__imp_SmbCryptoCreateSigningKey
0x14008f99d  nop     dword ptr [rax+rax+00h]
0x14008f9a2  mov     esi, eax
0x14008f9a4  lea     rcx, [rsp+0A8h+var_50]
0x14008f9a9  test    esi, esi
0x14008f9ab  mov     eax, ebx
0x14008f9ad  cmovs   eax, r15d
0x14008f9b1  cmovs   rcx, r12
0x14008f9b5  js      short loc_14008F9E6
0x14008f9b7  mov     [rsp+0A8h+dwFlags], 0; dwFlags
0x14008f9bf  lea     rdx, [rsp+0A8h+phHash]; phHash
0x14008f9c4  mov     [rsp+0A8h+cbSecret], eax; cbSecret
0x14008f9c8  mov     r9d, r14d; cbHashObject
0x14008f9cb  mov     [rsp+0A8h+pbSecret], rcx; pbSecret
0x14008f9d0  mov     r8, rbp; pbHashObject
0x14008f9d3  mov     rcx, [rsp+0A8h+hAlgorithm]; hAlgorithm
0x14008f9d8  call    cs:__imp_BCryptCreateHash
0x14008f9df  nop     dword ptr [rax+rax+00h]
0x14008f9e4  mov     esi, eax
0x14008f9e6  lea     rcx, [rsp+0A8h+var_50]
0x14008f9eb  jmp     loc_14009BB99
0x14008f9f0  xor     esi, esi
0x14008f9f2  jmp     loc_14008F90D
0x14008f9f7  mov     eax, 0C000009Ah
0x14008f9fc  jmp     short loc_14008FA0C
0x14008f9fe  test    esi, esi
0x14008fa00  jns     short loc_14008FA55
0x14008fa02  mov     rcx, rbp
0x14008fa05  call    Smb2DeallocateSigningHashObject
0x14008fa0a  mov     eax, esi
0x14008fa0c  mov     rcx, [rsp+0A8h+var_40]
0x14008fa11  xor     rcx, rsp; StackCookie
0x14008fa14  call    __security_check_cookie
0x14008fa19  mov     rbx, [rsp+0A8h+arg_18]
0x14008fa21  add     rsp, 70h
0x14008fa25  pop     r15
0x14008fa27  pop     r14
0x14008fa29  pop     r13
0x14008fa2b  pop     r12
0x14008fa2d  pop     rdi
0x14008fa2e  pop     rsi
0x14008fa2f  pop     rbp
0x14008fa30  retn
0x14008fa32  int     2Ch; Windows NT - assertion failure
0x14008fa34  jmp     loc_14008F94D
0x14008fa39  xorps   xmm0, xmm0
0x14008fa3c  mov     r8, r15; Size
0x14008fa3f  movups  [rsp+0A8h+var_50], xmm0
0x14008fa44  cmp     r15d, ebx
0x14008fa47  jb      loc_14009BB80
0x14008fa4d  mov     r8, rbx
0x14008fa50  jmp     loc_14009BB80
0x14008fa55  mov     rcx, [rdi+90h]
0x14008fa5c  mov     rax, [rsp+0A8h+phHash]
0x14008fa61  mov     [rcx+0B8h], rax
0x14008fa68  mov     rax, [rdi+90h]
0x14008fa6f  mov     ecx, [rsp+0A8h+var_64]
0x14008fa73  mov     [rax+0C8h], rbp
0x14008fa7a  mov     rax, [rdi+90h]
0x14008fa81  mov     [rax+0C0h], r14d
0x14008fa88  mov     rax, [rdi+90h]
0x14008fa8f  mov     [rax+0C4h], ecx
0x14008fa95  mov     rax, [rdi+90h]
0x14008fa9c  movzx   ecx, [rsp+0A8h+var_68]
0x14008faa1  mov     [rax+0D0h], cx
0x14008faa8  xor     eax, eax
0x14008faaa  jmp     loc_14008FA0C
0x14009bb80  mov     rdx, r12; Src
0x14009bb83  lea     rcx, [rsp+0A8h+var_50]; void *
0x14009bb88  call    memmove
0x14009bb8d  lea     rcx, [rsp+0A8h+var_50]
0x14009bb92  mov     eax, ebx
0x14009bb94  jmp     loc_14008F9B7
0x14009bb99  mov     byte ptr [rcx], 0
0x14009bb9c  inc     rcx
0x14009bb9f  sub     rbx, 1
0x14009bba3  jnz     short loc_14009BB99
0x14009bba5  jmp     loc_14008F9FE
```
