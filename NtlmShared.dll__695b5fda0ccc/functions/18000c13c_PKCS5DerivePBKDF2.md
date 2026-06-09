# PKCS5DerivePBKDF2

- ea: `0x18000c13c`
- end: `0x18000c3a8`
- name: `PKCS5DerivePBKDF2`
- size: `620`
- prototype: `__int64 __usercall@<rax>(unsigned __int8 *@<rcx>, unsigned int, int, char, __int64, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x18000b67c`

## callees

- `0x18000bc3c`
- `0x18000bf2c`
- `0x18000c13c`
- `0x18000c560`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c22e`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x18000c22e`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c374`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x18000c374`
- `bcrypt!BCryptCreateHash` at `0x18000c26b`
- `bcrypt!BCryptCreateHash` at `0x18000c26b`
- `bcrypt!BCryptDestroyHash` at `0x18000c366`
- `bcrypt!BCryptDestroyHash` at `0x18000c366`
- `bcrypt!BCryptGetProperty` at `0x18000c20f`
- `bcrypt!BCryptGetProperty` at `0x18000c20f`

## pseudocode

```c
_BOOL8 __fastcall PKCS5DerivePBKDF2(
        unsigned __int8 *a1,
        __int64 a2,
        __int128 *a3,
        __int64 a4,
        unsigned int a5,
        unsigned int a6,
        char a7,
        UCHAR *a8,
        unsigned int a9)
{
  NTSTATUS Property; // ebx
  unsigned int v12; // esi
  ULONG cbInput; // r15d
  UCHAR *pbHashObject; // rdi
  BCRYPT_ALG_HANDLE BCryptProviderHandle; // r14
  ULONG v16; // r9d
  __int128 v17; // xmm0
  UCHAR *v18; // r13
  int v19; // ebx
  __int64 v20; // rdx
  UCHAR pbOutput[4]; // [rsp+60h] [rbp-89h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+68h] [rbp-81h] BYREF
  ULONG pcbResult; // [rsp+70h] [rbp-79h] BYREF
  PUCHAR v25; // [rsp+78h] [rbp-71h]
  UCHAR pbInput[16]; // [rsp+80h] [rbp-69h] BYREF
  __int16 v27; // [rsp+90h] [rbp-59h]
  char v28; // [rsp+92h] [rbp-57h]
  char v29; // [rsp+93h] [rbp-56h]
  unsigned __int8 v30[4]; // [rsp+A0h] [rbp-49h] BYREF

  v25 = a8;
  Property = -2146893792;
  pcbResult = 0;
  *(_DWORD *)pbOutput = 0;
  phHash = 0;
  if ( !a6 || !a1 || !a3 )
    return Property >= 0;
  v12 = 32772;
  if ( a5 != 32777 )
    v12 = a5;
  if ( v12 == 32772 )
  {
    cbInput = 20;
  }
  else
  {
    if ( v12 != 32782 )
      return Property >= 0;
    cbInput = 64;
  }
  pbHashObject = 0;
  BCryptProviderHandle = GetBCryptProviderHandle(v12, 0, 0x28u);
  if ( BCryptProviderHandle )
  {
    Property = BCryptGetProperty(BCryptProviderHandle, L"ObjectLength", pbOutput, 4u, &pcbResult, 0);
    if ( Property >= 0 )
    {
      v16 = *(_DWORD *)pbOutput;
      if ( *(_DWORD *)pbOutput )
      {
        pbHashObject = (UCHAR *)LocalAlloc(0, *(unsigned int *)pbOutput);
        if ( !pbHashObject )
        {
LABEL_14:
          Property = -2146893792;
          goto LABEL_24;
        }
        v16 = *(_DWORD *)pbOutput;
      }
      Property = BCryptCreateHash(BCryptProviderHandle, &phHash, pbHashObject, v16, a1, 0x14u, 0);
      if ( Property < 0 )
        goto LABEL_24;
      v17 = *a3;
      v18 = v25;
      v29 = a7;
      v27 = 0;
      v28 = 0;
      *(_OWORD *)pbInput = v17;
      if ( (unsigned int)ReusableHMAC(
                           BCryptProviderHandle,
                           phHash,
                           v12,
                           a1,
                           0x14u,
                           pbInput,
                           0x14u,
                           pbHashObject,
                           *(unsigned int *)pbOutput,
                           v25,
                           a9) )
      {
        v19 = 1;
        if ( a6 <= 1 )
        {
LABEL_23:
          Property = 0;
          goto LABEL_24;
        }
        while ( (unsigned int)ReusableHMAC(
                                BCryptProviderHandle,
                                phHash,
                                v12,
                                a1,
                                0x14u,
                                v18,
                                cbInput,
                                pbHashObject,
                                *(unsigned int *)pbOutput,
                                v30,
                                0x40u) )
        {
          v20 = 0;
          do
          {
            *(_DWORD *)&v18[4 * v20] ^= *(_DWORD *)&v30[4 * v20];
            v20 = (unsigned int)(v20 + 1);
          }
          while ( (unsigned int)v20 < cbInput >> 2 );
          if ( ++v19 >= a6 )
            goto LABEL_23;
        }
      }
      goto LABEL_14;
    }
  }
LABEL_24:
  if ( phHash )
    BCryptDestroyHash(phHash);
  if ( pbHashObject )
    LocalFree(pbHashObject);
  return Property >= 0;
}

```

## disassembly

```asm
0x18000c13c  mov     [rsp-8+arg_8], rbx
0x18000c141  push    rbp
0x18000c142  push    rsi
0x18000c143  push    rdi
0x18000c144  push    r12
0x18000c146  push    r13
0x18000c148  push    r14
0x18000c14a  push    r15
0x18000c14c  lea     rbp, [rsp-7]
0x18000c151  sub     rsp, 0F0h
0x18000c158  mov     rax, cs:__security_cookie
0x18000c15f  xor     rax, rsp
0x18000c162  mov     [rbp+37h+var_40], rax
0x18000c166  mov     eax, [rbp+37h+arg_20]
0x18000c169  xor     edx, edx
0x18000c16b  cmp     [rbp+37h+arg_28], 1
0x18000c16f  mov     r12, rcx
0x18000c172  mov     rcx, [rbp+37h+arg_38]
0x18000c176  mov     r13, r8
0x18000c179  mov     [rbp+37h+var_A8], rcx
0x18000c17d  mov     ebx, 80090020h
0x18000c182  mov     [rbp+37h+var_B0], edx
0x18000c185  mov     dword ptr [rsp+120h+pbOutput], edx
0x18000c189  mov     [rsp+120h+phHash], rdx
0x18000c18e  jb      loc_18000C37A
0x18000c194  test    r12, r12
0x18000c197  jz      loc_18000C37A
0x18000c19d  test    r8, r8
0x18000c1a0  jz      loc_18000C37A
0x18000c1a6  mov     ecx, 8004h
0x18000c1ab  cmp     eax, 8009h
0x18000c1b0  mov     esi, ecx
0x18000c1b2  cmovnz  esi, eax
0x18000c1b5  cmp     esi, ecx
0x18000c1b7  jnz     short loc_18000C1BF
0x18000c1b9  lea     r15d, [rdx+14h]
0x18000c1bd  jmp     short loc_18000C1D1
0x18000c1bf  cmp     esi, 800Eh
0x18000c1c5  jnz     loc_18000C37A
0x18000c1cb  mov     r15d, 40h ; '@'
0x18000c1d1  mov     r8d, 28h ; '('
0x18000c1d7  mov     ecx, esi
0x18000c1d9  mov     rdi, rdx
0x18000c1dc  call    GetBCryptProviderHandle
0x18000c1e1  mov     r14, rax
0x18000c1e4  test    rax, rax
0x18000c1e7  jz      loc_18000C35C
0x18000c1ed  lea     rax, [rbp+37h+var_B0]
0x18000c1f1  mov     [rsp+120h+dwFlags], edi; dwFlags
0x18000c1f5  mov     r9d, 4; cbOutput
0x18000c1fb  mov     [rsp+120h+pcbResult], rax; pcbResult
0x18000c200  lea     r8, [rsp+120h+pbOutput]; pbOutput
0x18000c205  mov     rcx, r14; hObject
0x18000c208  lea     rdx, aObjectlength; "ObjectLength"
0x18000c20f  call    cs:__imp_BCryptGetProperty
0x18000c215  mov     ebx, eax
0x18000c217  test    eax, eax
0x18000c219  js      loc_18000C35C
0x18000c21f  mov     r9d, dword ptr [rsp+120h+pbOutput]
0x18000c224  test    r9d, r9d
0x18000c227  jz      short loc_18000C24B
0x18000c229  mov     edx, r9d; uBytes
0x18000c22c  xor     ecx, ecx; uFlags
0x18000c22e  call    cs:__imp_LocalAlloc
0x18000c234  mov     rdi, rax
0x18000c237  test    rax, rax
0x18000c23a  jnz     short loc_18000C246
0x18000c23c  mov     ebx, 80090020h
0x18000c241  jmp     loc_18000C35C
0x18000c246  mov     r9d, dword ptr [rsp+120h+pbOutput]; cbHashObject
0x18000c24b  mov     [rsp+120h+cbInput], 0; dwFlags
0x18000c253  lea     rdx, [rsp+120h+phHash]; phHash
0x18000c258  mov     [rsp+120h+dwFlags], 14h; cbSecret
0x18000c260  mov     r8, rdi; pbHashObject
0x18000c263  mov     rcx, r14; hAlgorithm
0x18000c266  mov     [rsp+120h+pcbResult], r12; pbSecret
0x18000c26b  call    cs:__imp_BCryptCreateHash
0x18000c271  xor     ecx, ecx
0x18000c273  mov     ebx, eax
0x18000c275  test    eax, eax
0x18000c277  js      loc_18000C35C
0x18000c27d  mov     al, [rbp+37h+arg_30]
0x18000c280  mov     r9, r12; unsigned __int8 *
0x18000c283  movups  xmm0, xmmword ptr [r13+0]
0x18000c288  mov     r13, [rbp+37h+var_A8]
0x18000c28c  mov     r8d, esi; unsigned int
0x18000c28f  mov     rdx, [rsp+120h+phHash]; void *
0x18000c294  mov     [rbp+37h+var_8D], al
0x18000c297  mov     eax, [rbp+37h+arg_40]
0x18000c29d  mov     [rsp+120h+var_D0], eax; unsigned int
0x18000c2a1  mov     eax, dword ptr [rsp+120h+pbOutput]
0x18000c2a5  mov     [rsp+120h+var_D8], r13; unsigned __int8 *
0x18000c2aa  mov     [rsp+120h+var_E0], eax; unsigned int
0x18000c2ae  lea     rax, [rbp+37h+pbInput]
0x18000c2b2  mov     [rbp+37h+var_90], cx
0x18000c2b6  mov     [rbp+37h+var_8E], cl
0x18000c2b9  mov     ecx, 14h
0x18000c2be  mov     [rsp+120h+pbHashObject], rdi; pbHashObject
0x18000c2c3  mov     [rsp+120h+cbInput], ecx; cbInput
0x18000c2c7  mov     qword ptr [rsp+120h+dwFlags], rax; pbInput
0x18000c2cc  mov     dword ptr [rsp+120h+pcbResult], ecx; ULONG
0x18000c2d0  mov     rcx, r14; hAlgorithm
0x18000c2d3  movdqu  xmmword ptr [rbp+37h+pbInput], xmm0
0x18000c2d8  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x18000c2dd  test    eax, eax
0x18000c2df  jz      loc_18000C23C
0x18000c2e5  mov     ebx, 1
0x18000c2ea  cmp     [rbp+37h+arg_28], ebx
0x18000c2ed  jbe     short loc_18000C35A
0x18000c2ef  mov     rdx, [rsp+120h+phHash]; void *
0x18000c2f4  lea     rax, [rbp+37h+var_80]
0x18000c2f8  mov     [rsp+120h+var_D0], 40h ; '@'; unsigned int
0x18000c300  mov     r9, r12; unsigned __int8 *
0x18000c303  mov     [rsp+120h+var_D8], rax; unsigned __int8 *
0x18000c308  mov     r8d, esi; unsigned int
0x18000c30b  mov     eax, dword ptr [rsp+120h+pbOutput]
0x18000c30f  mov     rcx, r14; hAlgorithm
0x18000c312  mov     [rsp+120h+var_E0], eax; unsigned int
0x18000c316  mov     [rsp+120h+pbHashObject], rdi; pbHashObject
0x18000c31b  mov     [rsp+120h+cbInput], r15d; cbInput
0x18000c320  mov     qword ptr [rsp+120h+dwFlags], r13; pbInput
0x18000c325  mov     dword ptr [rsp+120h+pcbResult], 14h; ULONG
0x18000c32d  call    ?ReusableHMAC@@YAHPEAX0KPEAEK1K1K1K@Z; ReusableHMAC(void *,void *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong,uchar *,ulong)
0x18000c332  test    eax, eax
0x18000c334  jz      loc_18000C23C
0x18000c33a  mov     r8d, r15d
0x18000c33d  shr     r8d, 2
0x18000c341  xor     edx, edx
0x18000c343  mov     eax, dword ptr [rbp+rdx*4+37h+var_80]
0x18000c347  xor     [r13+rdx*4+0], eax
0x18000c34c  inc     edx
0x18000c34e  cmp     edx, r8d
0x18000c351  jb      short loc_18000C343
0x18000c353  inc     ebx
0x18000c355  cmp     ebx, [rbp+37h+arg_28]
0x18000c358  jb      short loc_18000C2EF
0x18000c35a  xor     ebx, ebx
0x18000c35c  mov     rcx, [rsp+120h+phHash]; hHash
0x18000c361  test    rcx, rcx
0x18000c364  jz      short loc_18000C36C
0x18000c366  call    cs:__imp_BCryptDestroyHash
0x18000c36c  test    rdi, rdi
0x18000c36f  jz      short loc_18000C37A
0x18000c371  mov     rcx, rdi; hMem
0x18000c374  call    cs:__imp_LocalFree
0x18000c37a  not     ebx
0x18000c37c  shr     ebx, 1Fh
0x18000c37f  mov     eax, ebx
0x18000c381  mov     rcx, [rbp+37h+var_40]
0x18000c385  xor     rcx, rsp; StackCookie
0x18000c388  call    __security_check_cookie
0x18000c38d  mov     rbx, [rsp+120h+arg_8]
0x18000c395  add     rsp, 0F0h
0x18000c39c  pop     r15
0x18000c39e  pop     r14
0x18000c3a0  pop     r13
0x18000c3a2  pop     r12
0x18000c3a4  pop     rdi
0x18000c3a5  pop     rsi
0x18000c3a6  pop     rbp
0x18000c3a7  retn
```
