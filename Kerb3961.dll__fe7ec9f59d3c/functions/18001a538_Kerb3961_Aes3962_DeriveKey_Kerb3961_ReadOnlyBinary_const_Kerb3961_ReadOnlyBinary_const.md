# Kerb3961::Aes3962::DeriveKey(Kerb3961::ReadOnlyBinary const &,Kerb3961::ReadOnlyBinary const &)

- ea: `0x18001a538`
- end: `0x18001a751`
- name: `?DeriveKey@Aes3962@Kerb3961@@AEAA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@2@AEBUReadOnlyBinary@2@0@Z`
- size: `537`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops`

## callers

- `0x18001c130`

## callees

- `0x180001d64`
- `0x180002928`
- `0x180002fc0`
- `0x18000901c`
- `0x18000e320`
- `0x18000f438`
- `0x18001a538`

## pseudocode

```c
__int64 __fastcall Kerb3961::Aes3962::DeriveKey(__int64 a1, __int64 a2, __int64 a3, size_t *a4)
{
  int v8; // r8d
  int v9; // ebx
  int v10; // r8d
  int v11; // r14d
  void *v12; // rcx
  __int64 v13; // r8
  int v14; // ebx
  void *v15; // rcx
  void *v16; // r13
  _OWORD *v17; // rsi
  __int128 v18; // xmm0
  int v19; // r8d
  unsigned int v20; // ebx
  char *v21; // rcx
  unsigned __int64 v22; // r12
  __int64 v23; // rdx
  __int64 v24; // r8
  char *v26; // [rsp+30h] [rbp-39h] BYREF
  __int64 v27; // [rsp+38h] [rbp-31h] BYREF
  void *v28; // [rsp+40h] [rbp-29h]
  char *v29; // [rsp+48h] [rbp-21h]
  size_t Size; // [rsp+50h] [rbp-19h] BYREF
  void *v31; // [rsp+58h] [rbp-11h]
  char *v32; // [rsp+60h] [rbp-9h]
  __int64 v33; // [rsp+68h] [rbp-1h] BYREF
  _OWORD *v34; // [rsp+70h] [rbp+7h]
  char *v35; // [rsp+78h] [rbp+Fh]

  Kerb3961::MakeBuffer(&Size);
  v9 = (int)v32;
  if ( (int)v32 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)"IV", (const char *)(unsigned int)v32, v8);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v9;
    goto LABEL_19;
  }
  Kerb3961::MakeBuffer(&v33);
  v11 = (int)v35;
  if ( (int)v35 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"workSpace",
      (const char *)(unsigned int)v35,
      v10);
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v11;
    goto LABEL_5;
  }
  Kerb3961::Nfold((__int64)&v27, 0x10u, a4);
  v14 = (int)v29;
  if ( (int)v29 < 0 )
  {
    Kerb3961::Logging::Verify::StatusFailed(
      (Kerb3961::Logging::Verify *)"nfoldConstant",
      (const char *)(unsigned int)v29,
      v13);
    v15 = v28;
    *(_QWORD *)a2 = 0;
    *(_QWORD *)(a2 + 8) = 0;
    *(_DWORD *)(a2 + 16) = v14;
    if ( v15 )
      operator delete(v15, 0);
LABEL_5:
    v12 = v34;
    if ( !v34 )
      goto LABEL_19;
    goto LABEL_18;
  }
  v16 = v28;
  v17 = v34;
  v27 = 16;
  v18 = *(_OWORD *)v28;
  v28 = v34;
  *v34 = v18;
  ((void (__fastcall *)(char **, _QWORD, __int64, __int64, size_t *, __int64 *))Kerb3961::EncryptCTS)(
    &v26,
    *(_QWORD *)(a1 + 168),
    v13,
    a3,
    &Size,
    &v27);
  v20 = (unsigned int)v26;
  if ( (int)v26 >= 0 )
  {
    v22 = 16;
    if ( *(_QWORD *)(a1 + 104) <= 0x10u )
    {
LABEL_17:
      v12 = v16;
      *(_QWORD *)a2 = v33;
      *(_DWORD *)(a2 + 16) = v11;
      *(_QWORD *)(a2 + 8) = v17;
      goto LABEL_18;
    }
    while ( 1 )
    {
      v17[v22 / 0x10] = v17[v22 / 0x10 - 1];
      memset_0(v31, 0, Size);
      v23 = *(_QWORD *)(a1 + 168);
      v27 = 16;
      v28 = &v17[v22 / 0x10];
      ((void (__fastcall *)(char **, __int64, __int64, __int64, size_t *, __int64 *))Kerb3961::EncryptCTS)(
        &v26,
        v23,
        v24,
        a3,
        &Size,
        &v27);
      v20 = (unsigned int)v26;
      if ( (int)v26 < 0 )
        break;
      v22 += 16LL;
      if ( v22 >= *(_QWORD *)(a1 + 104) )
        goto LABEL_17;
    }
    v21 = "BlockEncrypt(baseKey, IV, {AES_BLOCK_SIZE, &workSpace.buffer[index]})";
  }
  else
  {
    v21 = "BlockEncrypt(baseKey, IV, {AES_BLOCK_SIZE, &workSpace.buffer[0]})";
  }
  Kerb3961::Logging::Verify::StatusFailed((Kerb3961::Logging::Verify *)v21, (const char *)v20, v19);
  *(_QWORD *)a2 = 0;
  *(_QWORD *)(a2 + 8) = 0;
  *(_DWORD *)(a2 + 16) = v20;
  operator delete(v16, 0);
  if ( !v17 )
    goto LABEL_19;
  v12 = v17;
LABEL_18:
  operator delete(v12, 0);
LABEL_19:
  if ( v31 )
    operator delete(v31, 0);
  return a2;
}

```

## disassembly

```asm
0x18001a538  mov     [rsp-8+arg_10], r8
0x18001a53d  push    rbp
0x18001a53e  push    rbx
0x18001a53f  push    rsi
0x18001a540  push    rdi
0x18001a541  push    r12
0x18001a543  push    r13
0x18001a545  push    r14
0x18001a547  push    r15
0x18001a549  lea     rbp, [rsp-1Fh]
0x18001a54e  sub     rsp, 88h
0x18001a555  mov     rdi, rdx
0x18001a558  mov     r15, rcx
0x18001a55b  mov     edx, 10h
0x18001a560  lea     rcx, [rbp+57h+Size]
0x18001a564  mov     rsi, r9
0x18001a567  mov     r12, r8
0x18001a56a  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001a56f  mov     ebx, dword ptr [rbp+57h+var_60]
0x18001a572  xor     r13d, r13d
0x18001a575  test    ebx, ebx
0x18001a577  jns     short loc_18001A596
0x18001a579  mov     edx, ebx; char *
0x18001a57b  lea     rcx, aIv; "IV"
0x18001a582  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a587  mov     [rdi], r13
0x18001a58a  mov     [rdi+8], r13
0x18001a58e  mov     [rdi+10h], ebx
0x18001a591  jmp     loc_18001A71E
0x18001a596  mov     rdx, [r15+68h]
0x18001a59a  lea     rcx, [rbp+57h+var_58]
0x18001a59e  call    ?MakeBuffer@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_K@Z; Kerb3961::MakeBuffer(unsigned __int64)
0x18001a5a3  mov     r14, [rbp+57h+var_48]
0x18001a5a7  test    r14d, r14d
0x18001a5aa  jns     short loc_18001A5D8
0x18001a5ac  mov     edx, r14d; char *
0x18001a5af  lea     rcx, aWorkspace; "workSpace"
0x18001a5b6  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a5bb  mov     [rdi], r13
0x18001a5be  mov     [rdi+8], r13
0x18001a5c2  mov     [rdi+10h], r14d
0x18001a5c6  mov     rcx, [rbp+57h+var_50]
0x18001a5ca  test    rcx, rcx
0x18001a5cd  jz      loc_18001A71E
0x18001a5d3  jmp     loc_18001A717
0x18001a5d8  mov     r8, rsi
0x18001a5db  lea     rcx, [rbp+57h+var_88]
0x18001a5df  mov     edx, 10h
0x18001a5e4  call    ?Nfold@Kerb3961@@YA?AU?$ReturnType@UOwnedBinary@Kerb3961@@$1??$SingleGetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UOwnedBinary@Kerb3961@@$0BA@@2@YAAEAU32@AEAU12@@Z@1@_KAEBUReadOnlyBinary@1@@Z; Kerb3961::Nfold(unsigned __int64,Kerb3961::ReadOnlyBinary const &)
0x18001a5e9  mov     ebx, dword ptr [rbp+57h+var_78]
0x18001a5ec  test    ebx, ebx
0x18001a5ee  jns     short loc_18001A61A
0x18001a5f0  mov     edx, ebx; char *
0x18001a5f2  lea     rcx, aNfoldconstant; "nfoldConstant"
0x18001a5f9  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a5fe  mov     rcx, [rbp+57h+var_80]; void *
0x18001a602  mov     [rdi], r13
0x18001a605  mov     [rdi+8], r13
0x18001a609  mov     [rdi+10h], ebx
0x18001a60c  test    rcx, rcx
0x18001a60f  jz      short loc_18001A5C6
0x18001a611  xor     edx, edx; struct std::nothrow_t *
0x18001a613  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a618  jmp     short loc_18001A5C6
0x18001a61a  mov     r13, [rbp+57h+var_80]
0x18001a61e  lea     rax, [rbp+57h+var_88]
0x18001a622  mov     rsi, [rbp+57h+var_50]
0x18001a626  lea     rcx, [rbp+57h+var_90]
0x18001a62a  mov     [rsp+0C0h+var_98], rax
0x18001a62f  mov     r9, r12
0x18001a632  lea     rax, [rbp+57h+Size]
0x18001a636  mov     [rbp+57h+var_88], 10h
0x18001a63e  movups  xmm0, xmmword ptr [r13+0]
0x18001a643  mov     [rbp+57h+var_80], rsi
0x18001a647  mov     [rsp+0C0h+var_A0], rax
0x18001a64c  movdqu  xmmword ptr [rsi], xmm0
0x18001a650  mov     rdx, [r15+0A8h]
0x18001a657  call    ?EncryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::EncryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x18001a65c  mov     ebx, dword ptr [rbp+57h+var_90]
0x18001a65f  test    ebx, ebx
0x18001a661  jns     short loc_18001A69B
0x18001a663  lea     rcx, aBlockencryptBa; "BlockEncrypt(baseKey, IV, {AES_BLOCK_SI"...
0x18001a66a  mov     edx, ebx; char *
0x18001a66c  call    ?StatusFailed@Verify@Logging@Kerb3961@@YAXPEBDJ@Z; Kerb3961::Logging::Verify::StatusFailed(char const *,long)
0x18001a671  mov     qword ptr [rdi], 0
0x18001a678  xor     edx, edx; struct std::nothrow_t *
0x18001a67a  mov     qword ptr [rdi+8], 0
0x18001a682  mov     rcx, r13; void *
0x18001a685  mov     [rdi+10h], ebx
0x18001a688  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a68d  test    rsi, rsi
0x18001a690  jz      loc_18001A71E
0x18001a696  mov     rcx, rsi
0x18001a699  jmp     short loc_18001A717
0x18001a69b  mov     r12d, 10h
0x18001a6a1  cmp     [r15+68h], r12
0x18001a6a5  jbe     short loc_18001A705
0x18001a6a7  lea     rbx, [r12+rsi]
0x18001a6ab  xor     edx, edx; Val
0x18001a6ad  movups  xmm0, xmmword ptr [rbx-10h]
0x18001a6b1  movdqu  xmmword ptr [rbx], xmm0
0x18001a6b5  mov     r8, [rbp+57h+Size]; Size
0x18001a6b9  mov     rcx, [rbp+57h+var_68]; void *
0x18001a6bd  call    memset_0
0x18001a6c2  mov     r9, [rbp+57h+arg_10]
0x18001a6c6  lea     rax, [rbp+57h+var_88]
0x18001a6ca  mov     rdx, [r15+0A8h]
0x18001a6d1  lea     rcx, [rbp+57h+var_90]
0x18001a6d5  mov     [rsp+0C0h+var_98], rax
0x18001a6da  lea     rax, [rbp+57h+Size]
0x18001a6de  mov     [rsp+0C0h+var_A0], rax
0x18001a6e3  mov     [rbp+57h+var_88], 10h
0x18001a6eb  mov     [rbp+57h+var_80], rbx
0x18001a6ef  call    ?EncryptCTS@Kerb3961@@YA?AU?$ReturnType@UStatusOnly@Kerb3961@@$1??$SingleGetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEBUResultBlock@2@AEBU12@@Z$1??$SingleSetter@UStatusOnly@Kerb3961@@$0A@@2@YAAEAU32@AEAU12@@Z@1@PEAX_KAEBUReadOnlyBinary@1@AEBUMutableBinary@1@3@Z; Kerb3961::EncryptCTS(void *,unsigned __int64,Kerb3961::ReadOnlyBinary const &,Kerb3961::MutableBinary const &,Kerb3961::MutableBinary const &)
0x18001a6f4  mov     ebx, dword ptr [rbp+57h+var_90]
0x18001a6f7  test    ebx, ebx
0x18001a6f9  js      short loc_18001A745
0x18001a6fb  add     r12, 10h
0x18001a6ff  cmp     r12, [r15+68h]
0x18001a703  jb      short loc_18001A6A7
0x18001a705  mov     rax, [rbp+57h+var_58]
0x18001a709  mov     rcx, r13; void *
0x18001a70c  mov     [rdi], rax
0x18001a70f  mov     [rdi+10h], r14d
0x18001a713  mov     [rdi+8], rsi
0x18001a717  xor     edx, edx; struct std::nothrow_t *
0x18001a719  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a71e  mov     rcx, [rbp+57h+var_68]; void *
0x18001a722  test    rcx, rcx
0x18001a725  jz      short loc_18001A72E
0x18001a727  xor     edx, edx; struct std::nothrow_t *
0x18001a729  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18001a72e  mov     rax, rdi
0x18001a731  add     rsp, 88h
0x18001a738  pop     r15
0x18001a73a  pop     r14
0x18001a73c  pop     r13
0x18001a73e  pop     r12
0x18001a740  pop     rdi
0x18001a741  pop     rsi
0x18001a742  pop     rbx
0x18001a743  pop     rbp
0x18001a744  retn
0x18001a745  lea     rcx, aBlockencryptBa_1; "BlockEncrypt(baseKey, IV, {AES_BLOCK_SI"...
0x18001a74c  jmp     loc_18001A66A
```
