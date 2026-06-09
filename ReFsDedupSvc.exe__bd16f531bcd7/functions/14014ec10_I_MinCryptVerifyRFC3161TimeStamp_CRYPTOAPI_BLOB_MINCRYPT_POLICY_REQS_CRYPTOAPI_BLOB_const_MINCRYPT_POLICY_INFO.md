# I_MinCryptVerifyRFC3161TimeStamp(_CRYPTOAPI_BLOB *,_MINCRYPT_POLICY_REQS *,_CRYPTOAPI_BLOB * const,_MINCRYPT_POLICY_INFO *,_LARGE_INTEGER *,uint *)

- ea: `0x14014ec10`
- end: `0x14014ed9f`
- name: `?I_MinCryptVerifyRFC3161TimeStamp@@YAJPEAU_CRYPTOAPI_BLOB@@PEAU_MINCRYPT_POLICY_REQS@@QEAU1@PEAU_MINCRYPT_POLICY_INFO@@PEAT_LARGE_INTEGER@@PEAI@Z`
- size: `399`
- prototype: `__int64 __fastcall(struct _CRYPTOAPI_BLOB *, struct _MINCRYPT_POLICY_REQS *, struct _CRYPTOAPI_BLOB *const, struct _MINCRYPT_POLICY_INFO *, union _LARGE_INTEGER *, unsigned int *)`
- caller_count: `1`
- callee_count: `7`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x14014e86c`

## callees

- `0x140004870`
- `0x14014ec10`
- `0x14014eeec`
- `0x1401a47c0`
- `0x1401a4ce8`
- `0x1401a53b8`
- `0x1401a5490`

## import_xrefs

- `ntdll!RtlCompareMemory` at `0x14014ecb3`
- `ntdll!RtlCompareMemory` at `0x14014ed4e`
- `ntdll!RtlCompareMemory` at `0x14014ecb3`
- `ntdll!RtlCompareMemory` at `0x14014ed4e`

## pseudocode

```c
__int64 __fastcall I_MinCryptVerifyRFC3161TimeStamp(
        struct _CRYPTOAPI_BLOB *a1,
        struct _MINCRYPT_POLICY_REQS *a2,
        struct _CRYPTOAPI_BLOB *const a3,
        struct _MINCRYPT_POLICY_INFO *a4,
        union _LARGE_INTEGER *a5,
        unsigned int *a6)
{
  struct _CRYPTOAPI_BLOB v6; // xmm0
  DWORD cbData; // edx
  BYTE *pbData; // rcx
  int Values; // eax
  __int64 v10; // rdx
  unsigned int v11; // esi
  int v12; // edi
  __int64 v13; // rbx
  unsigned int Length; // [rsp+50h] [rbp-B0h] BYREF
  int Length_4; // [rsp+54h] [rbp-ACh] BYREF
  struct _CRYPTOAPI_BLOB v18; // [rsp+58h] [rbp-A8h] BYREF
  int v19; // [rsp+70h] [rbp-90h] BYREF
  void *Source2; // [rsp+78h] [rbp-88h]
  int v21; // [rsp+80h] [rbp-80h]
  __int64 v22; // [rsp+88h] [rbp-78h]
  _BYTE v23[16]; // [rsp+C0h] [rbp-40h] BYREF
  int v24; // [rsp+D0h] [rbp-30h]
  _BYTE v25[16]; // [rsp+F0h] [rbp-10h] BYREF
  int v26; // [rsp+100h] [rbp+0h]
  void *v27; // [rsp+108h] [rbp+8h]
  _BYTE v28[16]; // [rsp+110h] [rbp+10h] BYREF
  _BYTE Source1[64]; // [rsp+120h] [rbp+20h] BYREF

  v6 = a3[17];
  cbData = a1->cbData;
  pbData = a1->pbData;
  Length = 0;
  v18 = v6;
  if ( (int)MinCryptVerifySignedDataLMode((int)pbData, cbData, 0, 0, (__int64)a2, &v19, a4) < 0
    || v19 != 11
    || RtlCompareMemory(qword_1401EEC48, Source2, 0xBu) != 11 )
  {
    return (unsigned int)-1073740760;
  }
  Length_4 = 14;
  Values = MinAsn1ExtractValues(v22, v21, (unsigned int)&Length_4, (unsigned int)&qword_1401BD890, 6, (__int64)v23);
  if ( Values > 0 )
    Values = v24;
  if ( Values < 0 )
    return (unsigned int)-1073740760;
  v11 = MinCryptDecodeHashAlgorithmIdentifier(v25, v10);
  if ( !v11 )
    return (unsigned int)-1073740760;
  v12 = MinCryptHashMemory(v11, 1, (unsigned int)&v18, (unsigned int)Source1, (__int64)&Length);
  if ( v12 < 0 )
    return (unsigned int)v12;
  if ( Length != v26 )
    return (unsigned int)-1073740760;
  v13 = Length;
  if ( RtlCompareMemory(Source1, v27, Length) != v13 )
    return (unsigned int)-1073740760;
  if ( !(unsigned __int8)MinAsn1DecodeGeneralizedTime(v28, a5) )
    a5->QuadPart = 0;
  *a6 = v11;
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x14014ec10  push    rbp
0x14014ec12  push    rbx
0x14014ec13  push    rsi
0x14014ec14  push    rdi
0x14014ec15  push    r14
0x14014ec17  push    r15
0x14014ec19  lea     rbp, [rsp-78h]
0x14014ec1e  sub     rsp, 178h
0x14014ec25  mov     rax, cs:__security_cookie
0x14014ec2c  xor     rax, rsp
0x14014ec2f  mov     [rbp+0A0h+var_40], rax
0x14014ec33  movups  xmm0, xmmword ptr [r8+110h]
0x14014ec3b  mov     r14, [rbp+0A0h+arg_20]
0x14014ec42  lea     rax, [rsp+1A0h+var_130]
0x14014ec47  mov     r15, [rbp+0A0h+arg_28]
0x14014ec4e  xor     r8d, r8d; int
0x14014ec51  mov     [rsp+1A0h+var_160], 0
0x14014ec5a  mov     [rsp+1A0h+var_168], 0
0x14014ec63  mov     [rsp+1A0h+var_170], r9; struct _MINCRYPT_POLICY_INFO *
0x14014ec68  xor     r9d, r9d; int
0x14014ec6b  mov     [rsp+1A0h+var_178], rax; void *
0x14014ec70  mov     [rsp+1A0h+var_180], rdx; __int64
0x14014ec75  mov     edx, [rcx]; int
0x14014ec77  mov     rcx, [rcx+8]; int
0x14014ec7b  mov     dword ptr [rsp+1A0h+Length], 0
0x14014ec83  movdqu  [rsp+1A0h+var_148], xmm0
0x14014ec89  call    MinCryptVerifySignedDataLMode
0x14014ec8e  test    eax, eax
0x14014ec90  js      loc_14014ED7B
0x14014ec96  cmp     [rsp+1A0h+var_130], 0Bh
0x14014ec9b  jnz     loc_14014ED7B
0x14014eca1  mov     rdx, [rsp+1A0h+Source2]; Source2
0x14014eca6  lea     rcx, qword_1401EEC48; Source1
0x14014ecad  mov     r8d, 0Bh; Length
0x14014ecb3  call    cs:__imp_RtlCompareMemory
0x14014ecba  nop     dword ptr [rax+rax+00h]
0x14014ecbf  cmp     rax, 0Bh
0x14014ecc3  jnz     loc_14014ED7B
0x14014ecc9  mov     edx, [rbp+0A0h+var_120]
0x14014eccc  lea     rax, [rbp+0A0h+var_E0]
0x14014ecd0  mov     rcx, [rbp+0A0h+var_118]
0x14014ecd4  lea     r9, qword_1401BD890
0x14014ecdb  mov     [rsp+1A0h+var_178], rax
0x14014ece0  lea     r8, [rsp+1A0h+Length+4]
0x14014ece5  mov     dword ptr [rsp+1A0h+var_180], 6
0x14014eced  mov     dword ptr [rsp+1A0h+Length+4], 0Eh
0x14014ecf5  call    MinAsn1ExtractValues
0x14014ecfa  test    eax, eax
0x14014ecfc  cmovg   eax, [rbp+0A0h+var_D0]
0x14014ed00  test    eax, eax
0x14014ed02  js      short loc_14014ED7B
0x14014ed04  lea     rcx, [rbp+0A0h+var_B0]
0x14014ed08  call    MinCryptDecodeHashAlgorithmIdentifier
0x14014ed0d  mov     esi, eax
0x14014ed0f  test    eax, eax
0x14014ed11  jz      short loc_14014ED7B
0x14014ed13  lea     rax, [rsp+1A0h+Length]
0x14014ed18  mov     edx, 1
0x14014ed1d  lea     r9, [rbp+0A0h+Source1]
0x14014ed21  mov     [rsp+1A0h+var_180], rax
0x14014ed26  lea     r8, [rsp+1A0h+var_148]
0x14014ed2b  mov     ecx, esi
0x14014ed2d  call    MinCryptHashMemory
0x14014ed32  mov     edi, eax
0x14014ed34  test    eax, eax
0x14014ed36  js      short loc_14014ED80
0x14014ed38  mov     eax, dword ptr [rsp+1A0h+Length]
0x14014ed3c  cmp     eax, [rbp+0A0h+var_A0]
0x14014ed3f  jnz     short loc_14014ED7B
0x14014ed41  mov     rdx, [rbp+0A0h+var_98]; Source2
0x14014ed45  lea     rcx, [rbp+0A0h+Source1]; Source1
0x14014ed49  mov     r8d, eax; Length
0x14014ed4c  mov     ebx, eax
0x14014ed4e  call    cs:__imp_RtlCompareMemory
0x14014ed55  nop     dword ptr [rax+rax+00h]
0x14014ed5a  cmp     rax, rbx
0x14014ed5d  jnz     short loc_14014ED7B
0x14014ed5f  mov     rdx, r14
0x14014ed62  lea     rcx, [rbp+0A0h+var_90]
0x14014ed66  call    MinAsn1DecodeGeneralizedTime
0x14014ed6b  test    al, al
0x14014ed6d  jnz     short loc_14014ED76
0x14014ed6f  mov     qword ptr [r14], 0
0x14014ed76  mov     [r15], esi
0x14014ed79  jmp     short loc_14014ED80
0x14014ed7b  mov     edi, 0C0000428h
0x14014ed80  mov     eax, edi
0x14014ed82  mov     rcx, [rbp+0A0h+var_40]
0x14014ed86  xor     rcx, rsp; StackCookie
0x14014ed89  call    __security_check_cookie
0x14014ed8e  add     rsp, 178h
0x14014ed95  pop     r15
0x14014ed97  pop     r14
0x14014ed99  pop     rdi
0x14014ed9a  pop     rsi
0x14014ed9b  pop     rbx
0x14014ed9c  pop     rbp
0x14014ed9d  retn
```
