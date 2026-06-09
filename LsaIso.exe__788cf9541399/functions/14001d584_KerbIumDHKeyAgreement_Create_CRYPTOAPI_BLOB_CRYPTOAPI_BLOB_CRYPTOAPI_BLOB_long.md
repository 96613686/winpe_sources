# KerbIumDHKeyAgreement::Create(_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,_CRYPTOAPI_BLOB *,long *)

- ea: `0x14001d584`
- end: `0x14001d721`
- name: `?Create@KerbIumDHKeyAgreement@@SAPEAVKerbKeyAgreement@@PEAU_CRYPTOAPI_BLOB@@00PEAJ@Z`
- size: `413`
- prototype: `struct KerbKeyAgreement *__fastcall(struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *, struct _CRYPTOAPI_BLOB *, int *)`
- caller_count: `1`
- callee_count: `7`
- tags: ``

## callers

- `0x140016e90`

## callees

- `0x140003a48`
- `0x140003ad6`
- `0x1400066f0`
- `0x140006720`
- `0x14001c194`
- `0x14001d584`
- `0x140038cd2`

## import_xrefs

- `bcrypt!BCryptDestroyKey` at `0x14001d6ea`
- `bcrypt!BCryptDestroyKey` at `0x14001d6ea`

## pseudocode

```c
struct KerbKeyAgreement *__fastcall KerbIumDHKeyAgreement::Create(
        struct _CRYPTOAPI_BLOB *a1,
        struct _CRYPTOAPI_BLOB *a2,
        struct _CRYPTOAPI_BLOB *a3,
        int *a4)
{
  __int64 i; // r10
  __int128 v9; // xmm1
  __int128 v10; // xmm0
  __int128 v11; // xmm1
  __int128 v12; // xmm0
  int v13; // eax
  DWORD v14; // esi
  BYTE *v15; // rax
  DWORD v16; // r12d
  size_t v17; // rcx
  BYTE *v18; // rax
  size_t v19; // rcx
  BYTE *v20; // rax
  BYTE *pbData; // rcx
  DWORD v22; // eax
  const void *v23; // rdx
  char *v24; // rcx
  BCRYPT_KEY_HANDLE v25; // rax
  size_t size[2]; // [rsp+20h] [rbp-58h] BYREF
  size_t Size[2]; // [rsp+30h] [rbp-48h]
  size_t v29[2]; // [rsp+40h] [rbp-38h]
  void *Src[2]; // [rsp+50h] [rbp-28h]
  __int128 v31; // [rsp+60h] [rbp-18h]
  BCRYPT_KEY_HANDLE hKey; // [rsp+D8h] [rbp+60h] BYREF

  hKey = 0;
  memset_0(size, 0, 0x50u);
  for ( i = 0; (unsigned int)i < 2; i = (unsigned int)(i + 1) )
  {
    if ( LODWORD(qword_1400414A0[10 * i]) == 2048 )
    {
      v9 = *(_OWORD *)&qword_1400414A0[10 * i + 2];
      *(_OWORD *)size = *(_OWORD *)&qword_1400414A0[10 * i];
      v10 = *(_OWORD *)&qword_1400414A0[10 * i + 4];
      *(_OWORD *)Size = v9;
      v11 = *(_OWORD *)&qword_1400414A0[10 * i + 6];
      *(_OWORD *)v29 = v10;
      v12 = *(_OWORD *)&qword_1400414A0[10 * i + 8];
      *(_OWORD *)Src = v11;
      v31 = v12;
      break;
    }
  }
  v13 = KerbDHCreateBCryptKey((const struct _CERT_X942_DH_PARAMETERS *)&size[1], &hKey);
  *a4 = v13;
  if ( v13 )
    return 0;
  v14 = size[1];
  v15 = (BYTE *)MIDL_user_allocate(LODWORD(size[1]));
  v16 = Size[1];
  v17 = LODWORD(Size[1]);
  a1->pbData = v15;
  v18 = (BYTE *)MIDL_user_allocate(v17);
  v19 = LODWORD(v29[1]);
  a2->pbData = v18;
  v20 = (BYTE *)MIDL_user_allocate(v19);
  a3->pbData = v20;
  pbData = a1->pbData;
  if ( !pbData || !a2->pbData || !v20 )
  {
    SafeAllocaFreeToHeap(pbData);
    SafeAllocaFreeToHeap(a2->pbData);
    SafeAllocaFreeToHeap(a3->pbData);
    return 0;
  }
  v22 = v29[1];
  v23 = (const void *)Size[0];
  a1->cbData = v14;
  a2->cbData = v16;
  a3->cbData = v22;
  memcpy_0(a1->pbData, v23, v14);
  memcpy_0(a2->pbData, (const void *)v29[0], v16);
  memcpy_0(a3->pbData, Src[0], LODWORD(v29[1]));
  v24 = (char *)operator new(0x38u, (const struct std::nothrow_t *)byte_140052C49);
  if ( v24 )
  {
    v25 = hKey;
    v24[40] = 0;
    *(_OWORD *)(v24 + 8) = 0;
    *(_OWORD *)(v24 + 24) = 0;
    *(_QWORD *)v24 = &KerbIumDHKeyAgreement::`vftable';
    *((_QWORD *)v24 + 6) = v25;
  }
  else
  {
    BCryptDestroyKey(hKey);
    return 0;
  }
  return (struct KerbKeyAgreement *)v24;
}

```

## disassembly

```asm
0x14001d584  push    rbp
0x14001d586  push    rbx
0x14001d587  push    rsi
0x14001d588  push    rdi
0x14001d589  push    r12
0x14001d58b  push    r13
0x14001d58d  push    r14
0x14001d58f  push    r15
0x14001d591  mov     rbp, rsp
0x14001d594  sub     rsp, 78h
0x14001d598  mov     rbx, rdx
0x14001d59b  mov     [rbp+hKey], 0
0x14001d5a3  xor     edx, edx; Val
0x14001d5a5  mov     rdi, r8
0x14001d5a8  mov     r14, rcx
0x14001d5ab  mov     rsi, r9
0x14001d5ae  lea     rcx, [rbp+size]; void *
0x14001d5b2  lea     r8d, [rdx+50h]; Size
0x14001d5b6  call    memset_0
0x14001d5bb  xor     r10d, r10d
0x14001d5be  cmp     r10d, 2
0x14001d5c2  jnb     short loc_14001D60C
0x14001d5c4  lea     rcx, [r10+r10*4]
0x14001d5c8  add     rcx, rcx
0x14001d5cb  lea     rax, qword_1400414A0
0x14001d5d2  cmp     dword ptr [rax+rcx*8], 800h
0x14001d5d9  jz      short loc_14001D5E0
0x14001d5db  inc     r10d
0x14001d5de  jmp     short loc_14001D5BE
0x14001d5e0  movups  xmm0, xmmword ptr [rax+rcx*8]
0x14001d5e4  movups  xmm1, xmmword ptr [rax+rcx*8+10h]
0x14001d5e9  movaps  xmmword ptr [rbp+size], xmm0
0x14001d5ed  movups  xmm0, xmmword ptr [rax+rcx*8+20h]
0x14001d5f2  movaps  xmmword ptr [rbp+Size], xmm1
0x14001d5f6  movups  xmm1, xmmword ptr [rax+rcx*8+30h]
0x14001d5fb  movaps  xmmword ptr [rbp+var_38], xmm0
0x14001d5ff  movups  xmm0, xmmword ptr [rax+rcx*8+40h]
0x14001d604  movaps  xmmword ptr [rbp+Src], xmm1
0x14001d608  movaps  [rbp+var_18], xmm0
0x14001d60c  lea     rdx, [rbp+hKey]; void **
0x14001d610  lea     rcx, [rbp+size+8]; struct _CERT_X942_DH_PARAMETERS *
0x14001d614  call    ?KerbDHCreateBCryptKey@@YAJAEBU_CERT_X942_DH_PARAMETERS@@PEAPEAX@Z; KerbDHCreateBCryptKey(_CERT_X942_DH_PARAMETERS const &,void * *)
0x14001d619  mov     [rsi], eax
0x14001d61b  test    eax, eax
0x14001d61d  jnz     loc_14001D70E
0x14001d623  mov     esi, dword ptr [rbp+size+8]
0x14001d626  mov     ecx, esi; size
0x14001d628  call    MIDL_user_allocate
0x14001d62d  mov     r12d, dword ptr [rbp+Size+8]
0x14001d631  mov     ecx, r12d; size
0x14001d634  mov     [r14+8], rax
0x14001d638  call    MIDL_user_allocate
0x14001d63d  mov     ecx, dword ptr [rbp+var_38+8]; size
0x14001d640  mov     [rbx+8], rax
0x14001d644  call    MIDL_user_allocate
0x14001d649  mov     [rdi+8], rax
0x14001d64d  mov     rcx, [r14+8]; void *
0x14001d651  test    rcx, rcx
0x14001d654  jz      loc_14001D6F7
0x14001d65a  cmp     qword ptr [rbx+8], 0
0x14001d65f  jz      loc_14001D6F7
0x14001d665  test    rax, rax
0x14001d668  jz      loc_14001D6F7
0x14001d66e  mov     eax, dword ptr [rbp+var_38+8]
0x14001d671  mov     r8d, esi; Size
0x14001d674  mov     rdx, [rbp+Size]; Src
0x14001d678  mov     [r14], esi
0x14001d67b  mov     [rbx], r12d
0x14001d67e  mov     [rdi], eax
0x14001d680  mov     rcx, [r14+8]; void *
0x14001d684  call    memcpy_0
0x14001d689  mov     rdx, [rbp+var_38]; Src
0x14001d68d  mov     r8d, r12d; Size
0x14001d690  mov     rcx, [rbx+8]; void *
0x14001d694  call    memcpy_0
0x14001d699  mov     r8d, dword ptr [rbp+var_38+8]; Size
0x14001d69d  mov     rdx, [rbp+Src]; Src
0x14001d6a1  mov     rcx, [rdi+8]; void *
0x14001d6a5  call    memcpy_0
0x14001d6aa  lea     rdx, byte_140052C49; struct std::nothrow_t *
0x14001d6b1  mov     ecx, 38h ; '8'; unsigned __int64
0x14001d6b6  call    ??2@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new(unsigned __int64,std::nothrow_t const &)
0x14001d6bb  mov     rcx, rax
0x14001d6be  test    rax, rax
0x14001d6c1  jz      short loc_14001D6E6
0x14001d6c3  mov     rax, [rbp+hKey]
0x14001d6c7  lea     rdx, ??_7KerbIumDHKeyAgreement@@6B@; const KerbIumDHKeyAgreement::`vftable'
0x14001d6ce  xorps   xmm0, xmm0
0x14001d6d1  mov     byte ptr [rcx+28h], 0
0x14001d6d5  movups  xmmword ptr [rcx+8], xmm0
0x14001d6d9  movups  xmmword ptr [rcx+18h], xmm0
0x14001d6dd  mov     [rcx], rdx
0x14001d6e0  mov     [rcx+30h], rax
0x14001d6e4  jmp     short loc_14001D6F2
0x14001d6e6  mov     rcx, [rbp+hKey]; hKey
0x14001d6ea  call    cs:__imp_BCryptDestroyKey
0x14001d6f0  xor     ecx, ecx
0x14001d6f2  mov     rax, rcx
0x14001d6f5  jmp     short loc_14001D710
0x14001d6f7  call    SafeAllocaFreeToHeap
0x14001d6fc  mov     rcx, [rbx+8]; void *
0x14001d700  call    SafeAllocaFreeToHeap
0x14001d705  mov     rcx, [rdi+8]; void *
0x14001d709  call    SafeAllocaFreeToHeap
0x14001d70e  xor     eax, eax
0x14001d710  add     rsp, 78h
0x14001d714  pop     r15
0x14001d716  pop     r14
0x14001d718  pop     r13
0x14001d71a  pop     r12
0x14001d71c  pop     rdi
0x14001d71d  pop     rsi
0x14001d71e  pop     rbx
0x14001d71f  pop     rbp
0x14001d720  retn
```
