# tpm12class::W8_ComputeCpHash(ushort,uint,uint,tpm12class::TPMW82B_BUFFER * const,uint,uchar const *,tpm12class::TPMW82B_BUFFER *,tpm12class::TPMW82B_BUFFER *)

- ea: `0x140068c88`
- end: `0x140068f18`
- name: `?W8_ComputeCpHash@tpm12class@@YAJGIIQEAVTPMW82B_BUFFER@1@IPEBEPEAV21@2@Z`
- size: `656`
- prototype: `__int64 __fastcall(tpm12class *__hidden this, unsigned __int16, unsigned int, unsigned int, void **, unsigned int, const unsigned __int8 *, ULONG, struct tpm12class::TPMW82B_BUFFER *)`
- caller_count: `3`
- callee_count: `8`
- tags: `file_ops, installer_update, broker_com_uri`

## callers

- `0x140056fb4`
- `0x1400589bc`
- `0x14005afe4`

## callees

- `0x140007410`
- `0x14000fc3c`
- `0x14000fc48`
- `0x140010514`
- `0x140068abc`
- `0x140068b48`
- `0x140068bcc`
- `0x140068c88`

## import_xrefs

- `bcrypt!BCryptCreateHash` at `0x140068e3a`
- `bcrypt!BCryptCreateHash` at `0x140068e3a`
- `bcrypt!BCryptGetProperty` at `0x140068d29`
- `bcrypt!BCryptGetProperty` at `0x140068db6`
- `bcrypt!BCryptGetProperty` at `0x140068d29`
- `bcrypt!BCryptGetProperty` at `0x140068db6`

## pseudocode

```c
__int64 __fastcall tpm12class::W8_ComputeCpHash(
        tpm12class *this,
        unsigned int a2,
        __int64 a3,
        __int64 a4,
        void **a5,
        unsigned int a6,
        const unsigned __int8 *a7,
        ULONG pcbResult)
{
  const unsigned __int8 *v8; // rsi
  NTSTATUS Property; // eax
  int v11; // ebx
  bool v12; // sf
  void *v13; // r14
  NTSTATUS v14; // eax
  bool v15; // sf
  void *v16; // rdi
  NTSTATUS Hash; // eax
  void *v18; // rdx
  void *v19; // r9
  bool v20; // sf
  unsigned __int8 *v21; // r9
  unsigned __int8 *v22; // r9
  unsigned __int8 *v23; // r9
  __int64 v24; // rax
  _BYTE *v25; // rcx
  BCRYPT_HASH_HANDLE phHash[2]; // [rsp+48h] [rbp-59h] BYREF
  _QWORD v28[3]; // [rsp+58h] [rbp-49h] BYREF
  int v29; // [rsp+70h] [rbp-31h]
  __int64 v30; // [rsp+78h] [rbp-29h]
  __int64 v31; // [rsp+80h] [rbp-21h]
  char v32; // [rsp+88h] [rbp-19h]
  __int16 v33; // [rsp+90h] [rbp-11h]
  __int64 v34; // [rsp+98h] [rbp-9h]
  unsigned int pbOutput; // [rsp+E8h] [rbp+47h] BYREF
  unsigned int v36; // [rsp+F0h] [rbp+4Fh] BYREF
  ULONG v37; // [rsp+F8h] [rbp+57h] BYREF

  v36 = a2;
  v8 = a7;
  v28[0] = &tpm12class::TPMW82B_BUFFER::`vftable';
  phHash[0] = 0;
  v37 = 0;
  pbOutput = 0;
  pcbResult = 0;
  v28[1] = 0;
  v28[2] = 0;
  v29 = 0;
  v30 = 0;
  v31 = 0;
  v32 = 0;
  v33 = 0;
  v34 = 0;
  if ( *((_QWORD *)a7 + 8) || *((_WORD *)a7 + 28) )
  {
    v11 = -2147024809;
    goto LABEL_36;
  }
  Property = BCryptGetProperty((BCRYPT_HANDLE)0x41, L"HashDigestLength", (PUCHAR)&pbOutput, 4u, &pcbResult, 0);
  if ( !Property )
    goto LABEL_12;
  if ( (Property & 0xFFFF000) == 0x290000 )
  {
    v11 = Property & 0xFFF | 0x80280000;
  }
  else if ( (Property & 0xFFF0000) == 0x70000 )
  {
    v11 = (unsigned __int16)Property;
    v12 = 0;
    if ( !(_WORD)Property )
      goto LABEL_11;
    v11 = (unsigned __int16)Property | 0x80070000;
  }
  else
  {
    v11 = Property | 0x10000000;
  }
  v12 = v11 < 0;
LABEL_11:
  if ( v12 )
    goto LABEL_36;
LABEL_12:
  v13 = operator new(pbOutput);
  memset_0(v13, 0, pbOutput);
  v14 = BCryptGetProperty((BCRYPT_HANDLE)0x41, L"ObjectLength", (PUCHAR)&v37, 4u, &pcbResult, 0);
  if ( !v14 )
    goto LABEL_21;
  if ( (v14 & 0xFFFF000) == 0x290000 )
  {
    v11 = v14 & 0xFFF | 0x80280000;
  }
  else if ( (v14 & 0xFFF0000) == 0x70000 )
  {
    v11 = (unsigned __int16)v14;
    v15 = 0;
    if ( !(_WORD)v14 )
      goto LABEL_20;
    v11 = (unsigned __int16)v14 | 0x80070000;
  }
  else
  {
    v11 = v14 | 0x10000000;
  }
  v15 = v11 < 0;
LABEL_20:
  if ( v15 )
    goto LABEL_36;
LABEL_21:
  v16 = operator new(v37);
  memset_0(v16, 0, v37);
  Hash = BCryptCreateHash((BCRYPT_ALG_HANDLE)0x41, phHash, (PUCHAR)v16, v37, 0, 0, 0);
  if ( !Hash )
  {
    v11 = 0;
LABEL_31:
    tpm12class::CryptUpdateDigestInt((tpm12class *)phHash[0], v18, (unsigned int)&v36, v19);
    tpm12class::CryptUpdateDigest(
      (tpm12class *)phHash,
      (void **)*(unsigned __int16 *)(a4 + 56),
      *(_QWORD *)(a4 + 64),
      v21);
    tpm12class::CryptUpdateDigest((tpm12class *)phHash, (void **)(unsigned int)a5, a6, v22);
    tpm12class::CryptCompleteHash((tpm12class *)phHash, (void **)(unsigned __int16)pbOutput, (unsigned __int16)v13, v23);
    *((_WORD *)v8 + 28) = pbOutput;
    *((_QWORD *)v8 + 8) = v13;
    goto LABEL_32;
  }
  if ( (Hash & 0xFFFF000) == 0x290000 )
  {
    v11 = Hash & 0xFFF | 0x80280000;
  }
  else if ( (Hash & 0xFFF0000) == 0x70000 )
  {
    v11 = (unsigned __int16)Hash;
    v20 = 0;
    if ( !(_WORD)Hash )
      goto LABEL_30;
    v11 = (unsigned __int16)Hash | 0x80070000;
  }
  else
  {
    v11 = Hash | 0x10000000;
  }
  v20 = v11 < 0;
LABEL_30:
  if ( !v20 )
    goto LABEL_31;
LABEL_32:
  v24 = v37;
  v25 = v16;
  if ( v37 )
  {
    do
    {
      *v25++ = 0;
      --v24;
    }
    while ( v24 );
  }
  operator delete(v16);
LABEL_36:
  tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER((tpm12class::TPMW82B_BUFFER *)v28);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140068c88  mov     rax, rsp
0x140068c8b  mov     [rax+18h], r8d
0x140068c8f  mov     [rax+10h], edx
0x140068c92  mov     [rax+8], cx
0x140068c96  push    rbp
0x140068c97  push    rbx
0x140068c98  push    rsi
0x140068c99  push    rdi
0x140068c9a  push    r12
0x140068c9c  push    r14
0x140068c9e  push    r15
0x140068ca0  lea     rbp, [rax-3Fh]
0x140068ca4  sub     rsp, 0A0h
0x140068cab  mov     rsi, [rbp+37h+arg_30]
0x140068caf  lea     rax, ??_7TPMW82B_BUFFER@tpm12class@@6B@; const tpm12class::TPMW82B_BUFFER::`vftable'
0x140068cb6  xor     r12d, r12d
0x140068cb9  mov     [rbp+37h+var_80], rax
0x140068cbd  mov     r15, r9
0x140068cc0  mov     [rbp+37h+phHash], r12
0x140068cc4  mov     [rbp+37h+arg_10], r12d
0x140068cc8  mov     [rbp+37h+pbOutput], r12d
0x140068ccc  mov     [rbp+37h+arg_38], r12d
0x140068cd0  mov     [rbp+37h+var_78], r12
0x140068cd4  mov     [rbp+37h+var_70], r12
0x140068cd8  mov     [rbp+37h+var_68], r12d
0x140068cdc  mov     [rbp+37h+var_60], r12
0x140068ce0  mov     [rbp+37h+var_58], r12
0x140068ce4  mov     [rbp+37h+var_50], r12b
0x140068ce8  mov     [rbp+37h+var_48], r12w
0x140068ced  mov     [rbp+37h+var_40], r12
0x140068cf1  cmp     [rsi+40h], r12
0x140068cf5  jnz     loc_140068EF6
0x140068cfb  cmp     [rsi+38h], r12w
0x140068d00  jnz     loc_140068EF6
0x140068d06  lea     rax, [rbp+37h+arg_38]
0x140068d0a  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x140068d0f  lea     r9d, [r12+4]; cbOutput
0x140068d14  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x140068d19  lea     r8, [rbp+37h+pbOutput]; pbOutput
0x140068d1d  lea     rdx, pszProperty; "HashDigestLength"
0x140068d24  lea     ecx, [r12+41h]; hObject
0x140068d29  call    cs:__imp_BCryptGetProperty
0x140068d2f  mov     ebx, eax
0x140068d31  mov     edi, 70000h
0x140068d36  test    eax, eax
0x140068d38  jz      short loc_140068D7A
0x140068d3a  and     eax, 0FFFF000h
0x140068d3f  cmp     eax, 290000h
0x140068d44  jnz     short loc_140068D54
0x140068d46  and     ebx, 0FFFh
0x140068d4c  or      ebx, 80280000h
0x140068d52  jmp     short loc_140068D72
0x140068d54  mov     eax, ebx
0x140068d56  and     eax, 0FFF0000h
0x140068d5b  cmp     eax, edi
0x140068d5d  jnz     short loc_140068D6E
0x140068d5f  movzx   ebx, bx
0x140068d62  test    ebx, ebx
0x140068d64  jz      short loc_140068D74
0x140068d66  or      ebx, 80070000h
0x140068d6c  jmp     short loc_140068D72
0x140068d6e  bts     ebx, 1Ch
0x140068d72  test    ebx, ebx
0x140068d74  js      loc_140068EFB
0x140068d7a  mov     ecx, [rbp+37h+pbOutput]; Size
0x140068d7d  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140068d82  mov     r8d, [rbp+37h+pbOutput]; Size
0x140068d86  xor     edx, edx; Val
0x140068d88  mov     rcx, rax; void *
0x140068d8b  mov     r14, rax
0x140068d8e  call    memset_0
0x140068d93  mov     r9d, 4; cbOutput
0x140068d99  mov     [rsp+0D0h+dwFlags], r12d; dwFlags
0x140068d9e  lea     rax, [rbp+37h+arg_38]
0x140068da2  lea     r8, [rbp+37h+arg_10]; pbOutput
0x140068da6  mov     [rsp+0D0h+pcbResult], rax; pcbResult
0x140068dab  lea     rdx, aObjectlength; "ObjectLength"
0x140068db2  lea     ecx, [r9+3Dh]; hObject
0x140068db6  call    cs:__imp_BCryptGetProperty
0x140068dbc  mov     ebx, eax
0x140068dbe  test    eax, eax
0x140068dc0  jz      short loc_140068E02
0x140068dc2  and     eax, 0FFFF000h
0x140068dc7  cmp     eax, 290000h
0x140068dcc  jnz     short loc_140068DDC
0x140068dce  and     ebx, 0FFFh
0x140068dd4  or      ebx, 80280000h
0x140068dda  jmp     short loc_140068DFA
0x140068ddc  mov     eax, ebx
0x140068dde  and     eax, 0FFF0000h
0x140068de3  cmp     eax, edi
0x140068de5  jnz     short loc_140068DF6
0x140068de7  movzx   ebx, bx
0x140068dea  test    ebx, ebx
0x140068dec  jz      short loc_140068DFC
0x140068dee  or      ebx, 80070000h
0x140068df4  jmp     short loc_140068DFA
0x140068df6  bts     ebx, 1Ch
0x140068dfa  test    ebx, ebx
0x140068dfc  js      loc_140068EFB
0x140068e02  mov     ecx, [rbp+37h+arg_10]; Size
0x140068e05  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x140068e0a  mov     r8d, [rbp+37h+arg_10]; Size
0x140068e0e  xor     edx, edx; Val
0x140068e10  mov     rcx, rax; void *
0x140068e13  mov     rdi, rax
0x140068e16  call    memset_0
0x140068e1b  mov     r9d, [rbp+37h+arg_10]; cbHashObject
0x140068e1f  lea     rdx, [rbp+37h+phHash]; phHash
0x140068e23  mov     [rsp+30h], r12d; dwFlags
0x140068e28  mov     r8, rdi; pbHashObject
0x140068e2b  mov     [rsp+0D0h+dwFlags], r12d; cbSecret
0x140068e30  mov     ecx, 41h ; 'A'; hAlgorithm
0x140068e35  mov     [rsp+0D0h+pcbResult], r12; pbSecret
0x140068e3a  call    cs:__imp_BCryptCreateHash
0x140068e40  mov     ebx, eax
0x140068e42  test    eax, eax
0x140068e44  jnz     short loc_140068E4B
0x140068e46  mov     ebx, r12d
0x140068e49  jmp     short loc_140068E8A
0x140068e4b  and     eax, 0FFFF000h
0x140068e50  cmp     eax, 290000h
0x140068e55  jnz     short loc_140068E65
0x140068e57  and     ebx, 0FFFh
0x140068e5d  or      ebx, 80280000h
0x140068e63  jmp     short loc_140068E86
0x140068e65  mov     eax, ebx
0x140068e67  and     eax, 0FFF0000h
0x140068e6c  cmp     eax, 70000h
0x140068e71  jnz     short loc_140068E82
0x140068e73  movzx   ebx, bx
0x140068e76  test    ebx, ebx
0x140068e78  jz      short loc_140068E88
0x140068e7a  or      ebx, 80070000h
0x140068e80  jmp     short loc_140068E86
0x140068e82  bts     ebx, 1Ch
0x140068e86  test    ebx, ebx
0x140068e88  js      short loc_140068ED5
0x140068e8a  mov     rcx, [rbp+37h+phHash]; this
0x140068e8e  lea     r8, [rbp+37h+arg_8]; unsigned int
0x140068e92  call    ?CryptUpdateDigestInt@tpm12class@@YAJPEAXI0@Z; tpm12class::CryptUpdateDigestInt(void *,uint,void *)
0x140068e97  movzx   edx, word ptr [r15+38h]; void **
0x140068e9c  lea     rcx, [rbp+37h+phHash]; this
0x140068ea0  mov     r8, [r15+40h]; unsigned int
0x140068ea4  call    ?CryptUpdateDigest@tpm12class@@YAJPEAPEAXIPEAE@Z; tpm12class::CryptUpdateDigest(void * *,uint,uchar *)
0x140068ea9  mov     r8, qword ptr [rbp+37h+arg_28]; unsigned int
0x140068ead  lea     rcx, [rbp+37h+phHash]; this
0x140068eb1  mov     edx, dword ptr [rbp+37h+arg_20]; void **
0x140068eb4  call    ?CryptUpdateDigest@tpm12class@@YAJPEAPEAXIPEAE@Z; tpm12class::CryptUpdateDigest(void * *,uint,uchar *)
0x140068eb9  movzx   edx, word ptr [rbp+37h+pbOutput]; void **
0x140068ebd  lea     rcx, [rbp+37h+phHash]; this
0x140068ec1  mov     r8, r14; unsigned __int16
0x140068ec4  call    ?CryptCompleteHash@tpm12class@@YAJPEAPEAXGPEAE@Z; tpm12class::CryptCompleteHash(void * *,ushort,uchar *)
0x140068ec9  movzx   eax, word ptr [rbp+37h+pbOutput]
0x140068ecd  mov     [rsi+38h], ax
0x140068ed1  mov     [rsi+40h], r14
0x140068ed5  mov     eax, [rbp+37h+arg_10]
0x140068ed8  mov     rcx, rdi
0x140068edb  test    rax, rax
0x140068ede  jz      short loc_140068EEC
0x140068ee0  mov     [rcx], r12b
0x140068ee3  inc     rcx
0x140068ee6  sub     rax, 1
0x140068eea  jnz     short loc_140068EE0
0x140068eec  mov     rcx, rdi; Block
0x140068eef  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140068ef4  jmp     short loc_140068EFB
0x140068ef6  mov     ebx, 80070057h
0x140068efb  lea     rcx, [rbp+37h+var_80]; this
0x140068eff  call    ??1TPMW82B_BUFFER@tpm12class@@UEAA@XZ; tpm12class::TPMW82B_BUFFER::~TPMW82B_BUFFER(void)
0x140068f04  mov     eax, ebx
0x140068f06  add     rsp, 0A0h
0x140068f0d  pop     r15
0x140068f0f  pop     r14
0x140068f11  pop     r12
0x140068f13  pop     rdi
0x140068f14  pop     rsi
0x140068f15  pop     rbx
0x140068f16  pop     rbp
0x140068f17  retn
```
