# AppHashComputeImageHashInternal

- ea: `0x140029db4`
- end: `0x14002a2a6`
- name: `AppHashComputeImageHashInternal`
- size: `1266`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x140003598`

## callees

- `0x140006a20`
- `0x140006a60`
- `0x140029db4`
- `0x14002a38c`
- `0x14002a520`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140029f18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a270`
- `ntoskrnl!ExFreePoolWithTag` at `0x140029f18`
- `ntoskrnl!ExFreePoolWithTag` at `0x14002a270`
- `ntoskrnl!ExAllocatePool2` at `0x140029e56`
- `ntoskrnl!ExAllocatePool2` at `0x140029f31`
- `ntoskrnl!ExAllocatePool2` at `0x140029e56`
- `ntoskrnl!ExAllocatePool2` at `0x140029f31`
- `ksecdd!BCryptFinishHash` at `0x14002a252`
- `ksecdd!BCryptFinishHash` at `0x14002a252`

## pseudocode

```c
__int64 __fastcall AppHashComputeImageHashInternal(
        __int64 a1,
        __int64 (__fastcall **a2)(__int64, __int128 *),
        unsigned int a3,
        __int64 a4)
{
  UCHAR *v6; // r12
  NTSTATUS v7; // edi
  __int64 v8; // r9
  unsigned __int64 v9; // rbx
  void *pbInput; // r14
  ULONG cbInput; // esi
  unsigned __int64 i; // rdx
  ULONG v13; // ecx
  int IsPeImage; // eax
  __int64 v15; // r9
  __int64 Pool2; // rax
  int v17; // ecx
  int v18; // eax
  int v19; // r9d
  unsigned int j; // ecx
  unsigned __int64 v21; // rsi
  unsigned int v22; // edi
  ULONG v23; // r12d
  int v24; // esi
  int v25; // eax
  ULONG v26; // eax
  BOOL v27; // esi
  unsigned int k; // ebx
  __int64 v29; // rcx
  int v31; // [rsp+40h] [rbp-59h]
  int v32; // [rsp+44h] [rbp-55h] BYREF
  __int64 v33; // [rsp+48h] [rbp-51h] BYREF
  ULONG v34; // [rsp+50h] [rbp-49h] BYREF
  __int64 v35; // [rsp+58h] [rbp-41h]
  unsigned int v36; // [rsp+60h] [rbp-39h]
  unsigned __int64 v37; // [rsp+68h] [rbp-31h] BYREF
  UCHAR *v38; // [rsp+70h] [rbp-29h] BYREF
  __int64 v39; // [rsp+78h] [rbp-21h] BYREF
  unsigned __int64 v40; // [rsp+80h] [rbp-19h]
  __int64 (__fastcall **v41)(__int64, __int128 *); // [rsp+88h] [rbp-11h]
  __int64 v42; // [rsp+90h] [rbp-9h]
  UCHAR v43[8]; // [rsp+98h] [rbp-1h] BYREF
  __int128 v44; // [rsp+A0h] [rbp+7h] BYREF
  __int64 v45; // [rsp+B0h] [rbp+17h]

  v41 = a2;
  v42 = a1;
  v33 = 0;
  v39 = 0;
  v38 = 0;
  v45 = 0;
  v6 = 0;
  v32 = 0;
  v34 = 0;
  v36 = 0;
  LODWORD(v35) = 0;
  *(_QWORD *)v43 = 0;
  v44 = 0;
  if ( !a3 )
    return 0;
  v7 = (*a2)(a1, &v44);
  if ( v7 < 0 )
    return (unsigned int)v7;
  v9 = *((_QWORD *)&v44 + 1);
  v37 = *((_QWORD *)&v44 + 1);
  pbInput = (void *)ExAllocatePool2(66, 0x10000, 1215328321, v8);
  if ( !pbInput )
    return (unsigned int)-1073741801;
  v40 = v9;
  v31 = 0;
  cbInput = 0x10000;
  v33 = 0;
  for ( i = v9; i; v40 = i )
  {
    v13 = i;
    if ( cbInput <= i )
      v13 = cbInput;
    cbInput = v13;
    v7 = ((__int64 (__fastcall *)(__int64, __int64 *, _QWORD, void *))v41[1])(v42, &v33, v13, pbInput);
    if ( v7 < 0 )
      goto LABEL_71;
    if ( v33 )
    {
      v17 = v32;
    }
    else
    {
      IsPeImage = AppHashIsPeImage(
                    (_DWORD)pbInput,
                    cbInput,
                    (unsigned int)&v37,
                    (unsigned int)&v32,
                    (__int64)&v34,
                    (__int64)&v39,
                    (__int64)&v38);
      v31 = IsPeImage;
      if ( IsPeImage == -1073741789 )
      {
        cbInput = v34;
        if ( v34 > v40 )
          cbInput = v40;
        ExFreePoolWithTag(pbInput, 0);
        Pool2 = ExAllocatePool2(66, cbInput, 1215328321, v15);
        pbInput = (void *)Pool2;
        if ( !Pool2 )
          return (unsigned int)-1073741801;
        v7 = ((__int64 (__fastcall *)(__int64, __int64 *, _QWORD, __int64))v41[1])(v42, &v33, cbInput, Pool2);
        if ( v7 < 0 )
          goto LABEL_71;
        IsPeImage = AppHashIsPeImage(
                      (_DWORD)pbInput,
                      cbInput,
                      (unsigned int)&v37,
                      (unsigned int)&v32,
                      (__int64)&v34,
                      (__int64)&v39,
                      (__int64)&v38);
        v31 = IsPeImage;
      }
      v17 = v32;
      if ( !v32 && IsPeImage < 0 )
        goto LABEL_71;
      v9 = v37;
      v6 = v38;
    }
    if ( v33 )
    {
      v18 = v31;
LABEL_37:
      if ( v17 && v18 < 0 )
        v19 = 0;
      else
LABEL_40:
        v19 = 1;
      v7 = AppHashHashBytes(a3, a4, 1, v19, (PUCHAR)pbInput, cbInput);
      if ( v7 < 0 )
        goto LABEL_71;
      goto LABEL_42;
    }
    if ( !v17 )
      goto LABEL_40;
    v18 = v31;
    if ( v31 < 0 )
      goto LABEL_37;
    v35 = *(_QWORD *)v6;
    v36 = v35;
    if ( HIDWORD(v35) )
    {
      if ( (_DWORD)v35 )
      {
        if ( (unsigned int)v35 < v9 && (unsigned int)v35 >= (int)v6 - (int)pbInput + 8 )
        {
          v40 = (unsigned int)v35;
          if ( (unsigned int)v35 < cbInput )
            cbInput = v35;
        }
      }
    }
    v7 = AppHashHashBytes(a3, a4, 1, 0, (PUCHAR)pbInput, cbInput);
    if ( v7 < 0 )
      goto LABEL_71;
    v7 = AppHashHashBytes(a3, a4, 0, 1, (PUCHAR)pbInput, (int)v39 - (int)pbInput);
    if ( v7 < 0 )
      goto LABEL_71;
    v7 = AppHashHashBytes(a3, a4, 0, 1, (PUCHAR)(v39 + 4), (int)v6 - (int)v39 - 4);
    if ( v7 < 0 )
      goto LABEL_71;
    v7 = AppHashHashBytes(a3, a4, 0, 1, v6 + 8, cbInput + (_DWORD)pbInput - (_DWORD)v6 - 8);
    if ( v7 < 0 )
      goto LABEL_71;
    LODWORD(v35) = HIDWORD(v35);
LABEL_42:
    i = v40 - cbInput;
    v33 += cbInput;
  }
  for ( j = 0; j < a3; ++j )
  {
    if ( *(_DWORD *)(32LL * j + a4 + 16) )
    {
      if ( (_DWORD)v35 && v36 && v36 < v9 )
      {
        v33 = v36;
        v21 = v9 - v36;
        v22 = 0x10000;
        while ( v21 )
        {
          v23 = v21;
          if ( v22 <= v21 )
            v23 = v22;
          v7 = ((__int64 (__fastcall *)(__int64, __int64 *, _QWORD, void *))v41[1])(v42, &v33, v23, pbInput);
          if ( v7 < 0 )
            goto LABEL_71;
          v7 = AppHashHashBytes(a3, a4, 1, 0, (PUCHAR)pbInput, v23);
          if ( v7 < 0 )
            goto LABEL_71;
          v22 = v23;
          v21 -= v23;
          v33 += v23;
        }
      }
      break;
    }
  }
  v24 = v32;
  if ( v32 && (v25 = v31, v31 < 0) )
  {
LABEL_62:
    v27 = !v24 || v25 >= 0;
    v7 = 0;
    for ( k = 0; k < a3; ++k )
    {
      v29 = 32LL * k;
      if ( *(_DWORD *)(v29 + a4 + 16) || v27 )
      {
        v7 = BCryptFinishHash(
               *(BCRYPT_HASH_HANDLE *)(v29 + a4),
               *(PUCHAR *)(v29 + a4 + 24),
               *(unsigned __int16 *)(v29 + a4 + 20),
               0);
        if ( v7 < 0 )
          break;
      }
    }
  }
  else
  {
    v26 = ((v9 + 7) & 0xFFFFFFF8) - v9;
    if ( !v26 || (v7 = AppHashHashBytes(a3, a4, 0, 1, v43, v26), v7 >= 0) )
    {
      v25 = v31;
      goto LABEL_62;
    }
  }
LABEL_71:
  ExFreePoolWithTag(pbInput, 0);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x140029db4  mov     [rsp-8+arg_10], rbx
0x140029db9  push    rbp
0x140029dba  push    rsi
0x140029dbb  push    rdi
0x140029dbc  push    r12
0x140029dbe  push    r13
0x140029dc0  push    r14
0x140029dc2  push    r15
0x140029dc4  lea     rbp, [rsp-27h]
0x140029dc9  sub     rsp, 0C0h
0x140029dd0  mov     rax, cs:__security_cookie
0x140029dd7  xor     rax, rsp
0x140029dda  mov     [rbp+57h+var_38], rax
0x140029dde  xor     ebx, ebx
0x140029de0  mov     [rbp+57h+var_68], rdx
0x140029de4  xor     eax, eax
0x140029de6  mov     [rbp+57h+var_60], rcx
0x140029dea  mov     [rbp+57h+var_A8], rbx
0x140029dee  xorps   xmm0, xmm0
0x140029df1  mov     [rbp+57h+var_78], rbx
0x140029df5  mov     r15, r9
0x140029df8  mov     [rbp+57h+var_80], rbx
0x140029dfc  mov     r13d, r8d
0x140029dff  mov     [rbp+57h+var_40], rax
0x140029e03  mov     r12d, ebx
0x140029e06  mov     [rbp+57h+var_AC], ebx
0x140029e09  mov     [rbp+57h+var_A0], ebx
0x140029e0c  mov     [rbp+57h+var_90], ebx
0x140029e0f  mov     dword ptr [rbp+57h+var_98], ebx
0x140029e12  mov     qword ptr [rbp+57h+var_58], rbx
0x140029e16  movups  [rbp+57h+var_50], xmm0
0x140029e1a  test    r8d, r8d
0x140029e1d  jnz     short loc_140029E26
0x140029e1f  mov     edi, ebx
0x140029e21  jmp     loc_14002A27C
0x140029e26  mov     rax, [rdx]
0x140029e29  lea     rdx, [rbp+57h+var_50]
0x140029e2d  call    _guard_dispatch_icall
0x140029e32  mov     edi, eax
0x140029e34  test    eax, eax
0x140029e36  js      loc_14002A27C
0x140029e3c  mov     rbx, qword ptr [rbp+57h+var_50+8]
0x140029e40  mov     edi, 10000h
0x140029e45  mov     edx, edi
0x140029e47  mov     [rbp+57h+var_88], rbx
0x140029e4b  mov     r8d, 48707041h
0x140029e51  mov     ecx, 42h ; 'B'
0x140029e56  call    cs:__imp_ExAllocatePool2
0x140029e5d  nop     dword ptr [rax+rax+00h]
0x140029e62  mov     r14, rax
0x140029e65  test    rax, rax
0x140029e68  jnz     short loc_140029E74
0x140029e6a  mov     edi, 0C0000017h
0x140029e6f  jmp     loc_14002A27C
0x140029e74  xor     eax, eax
0x140029e76  mov     [rbp+57h+var_70], rbx
0x140029e7a  mov     [rbp+57h+var_B0], eax
0x140029e7d  mov     esi, edi
0x140029e7f  mov     [rbp+57h+var_A8], rax
0x140029e83  mov     rdx, rbx
0x140029e86  test    rdx, rdx
0x140029e89  jz      loc_14002A125
0x140029e8f  mov     ecx, edx
0x140029e91  mov     eax, esi
0x140029e93  cmp     rax, rdx
0x140029e96  mov     r9, r14
0x140029e99  mov     rax, [rbp+57h+var_68]
0x140029e9d  lea     rdx, [rbp+57h+var_A8]
0x140029ea1  cmovbe  ecx, esi
0x140029ea4  mov     esi, ecx
0x140029ea6  mov     r8d, ecx
0x140029ea9  mov     rcx, [rbp+57h+var_60]
0x140029ead  mov     rax, [rax+8]
0x140029eb1  call    _guard_dispatch_icall
0x140029eb6  mov     edi, eax
0x140029eb8  test    eax, eax
0x140029eba  js      loc_14002A26B
0x140029ec0  cmp     [rbp+57h+var_A8], 0
0x140029ec5  jnz     loc_140029FB7
0x140029ecb  lea     rax, [rbp+57h+var_80]
0x140029ecf  mov     edx, esi
0x140029ed1  mov     [rsp+0F0h+var_C0], rax
0x140029ed6  lea     r9, [rbp+57h+var_AC]
0x140029eda  lea     rax, [rbp+57h+var_78]
0x140029ede  mov     rcx, r14
0x140029ee1  mov     qword ptr [rsp+0F0h+cbInput], rax
0x140029ee6  lea     r8, [rbp+57h+var_88]
0x140029eea  lea     rax, [rbp+57h+var_A0]
0x140029eee  mov     [rsp+0F0h+pbInput], rax
0x140029ef3  call    AppHashIsPeImage
0x140029ef8  mov     [rbp+57h+var_B0], eax
0x140029efb  cmp     eax, 0C0000023h
0x140029f00  jnz     loc_140029F9E
0x140029f06  mov     rdx, [rbp+57h+var_70]
0x140029f0a  mov     rcx, r14; P
0x140029f0d  mov     esi, [rbp+57h+var_A0]
0x140029f10  cmp     rsi, rdx
0x140029f13  cmova   esi, edx
0x140029f16  xor     edx, edx; Tag
0x140029f18  call    cs:__imp_ExFreePoolWithTag
0x140029f1f  nop     dword ptr [rax+rax+00h]
0x140029f24  mov     edx, esi
0x140029f26  mov     ecx, 42h ; 'B'
0x140029f2b  mov     r8d, 48707041h
0x140029f31  call    cs:__imp_ExAllocatePool2
0x140029f38  nop     dword ptr [rax+rax+00h]
0x140029f3d  mov     r14, rax
0x140029f40  test    rax, rax
0x140029f43  jz      loc_140029E6A
0x140029f49  mov     rax, [rbp+57h+var_68]
0x140029f4d  lea     rdx, [rbp+57h+var_A8]
0x140029f51  mov     rcx, [rbp+57h+var_60]
0x140029f55  mov     r9, r14
0x140029f58  mov     r8d, esi
0x140029f5b  mov     rax, [rax+8]
0x140029f5f  call    _guard_dispatch_icall
0x140029f64  mov     edi, eax
0x140029f66  test    eax, eax
0x140029f68  js      loc_14002A26B
0x140029f6e  lea     rax, [rbp+57h+var_80]
0x140029f72  mov     edx, esi
0x140029f74  mov     [rsp+0F0h+var_C0], rax
0x140029f79  lea     r9, [rbp+57h+var_AC]
0x140029f7d  lea     rax, [rbp+57h+var_78]
0x140029f81  mov     rcx, r14
0x140029f84  mov     qword ptr [rsp+0F0h+cbInput], rax
0x140029f89  lea     r8, [rbp+57h+var_88]
0x140029f8d  lea     rax, [rbp+57h+var_A0]
0x140029f91  mov     [rsp+0F0h+pbInput], rax
0x140029f96  call    AppHashIsPeImage
0x140029f9b  mov     [rbp+57h+var_B0], eax
0x140029f9e  mov     ecx, [rbp+57h+var_AC]
0x140029fa1  test    ecx, ecx
0x140029fa3  jnz     short loc_140029FAD
0x140029fa5  test    eax, eax
0x140029fa7  js      loc_14002A26B
0x140029fad  mov     rbx, [rbp+57h+var_88]
0x140029fb1  mov     r12, [rbp+57h+var_80]
0x140029fb5  jmp     short loc_140029FBA
0x140029fb7  mov     ecx, [rbp+57h+var_AC]
0x140029fba  cmp     [rbp+57h+var_A8], 0
0x140029fbf  jnz     loc_14002A0D5
0x140029fc5  test    ecx, ecx
0x140029fc7  jz      loc_14002A0E5
0x140029fcd  mov     eax, [rbp+57h+var_B0]
0x140029fd0  test    eax, eax
0x140029fd2  js      loc_14002A0D8
0x140029fd8  mov     rax, [r12]
0x140029fdc  mov     [rbp+57h+var_98], rax
0x140029fe0  mov     ecx, dword ptr [rbp+57h+var_98]
0x140029fe3  shr     rax, 20h
0x140029fe7  mov     [rbp+57h+var_90], ecx
0x140029fea  test    eax, eax
0x140029fec  jz      short loc_14002A00D
0x140029fee  test    ecx, ecx
0x140029ff0  jz      short loc_14002A00D
0x140029ff2  cmp     rcx, rbx
0x140029ff5  jnb     short loc_14002A00D
0x140029ff7  mov     eax, r12d
0x140029ffa  sub     eax, r14d
0x140029ffd  add     eax, 8
0x14002a000  cmp     ecx, eax
0x14002a002  jb      short loc_14002A00D
0x14002a004  cmp     ecx, esi
0x14002a006  mov     [rbp+57h+var_70], rcx
0x14002a00a  cmovb   esi, ecx
0x14002a00d  xor     r9d, r9d; int
0x14002a010  mov     [rsp+0F0h+cbInput], esi; cbInput
0x14002a014  mov     rdx, r15; int
0x14002a017  mov     [rsp+0F0h+pbInput], r14; pbInput
0x14002a01c  mov     ecx, r13d; int
0x14002a01f  lea     r8d, [r9+1]; int
0x14002a023  call    AppHashHashBytes
0x14002a028  mov     edi, eax
0x14002a02a  test    eax, eax
0x14002a02c  js      loc_14002A26B
0x14002a032  mov     eax, dword ptr [rbp+57h+var_78]
0x14002a035  mov     r9d, 1; int
0x14002a03b  sub     eax, r14d
0x14002a03e  xor     r8d, r8d; int
0x14002a041  mov     [rsp+0F0h+cbInput], eax; cbInput
0x14002a045  mov     rdx, r15; int
0x14002a048  mov     ecx, r13d; int
0x14002a04b  mov     [rsp+0F0h+pbInput], r14; pbInput
0x14002a050  call    AppHashHashBytes
0x14002a055  mov     edi, eax
0x14002a057  test    eax, eax
0x14002a059  js      loc_14002A26B
0x14002a05f  mov     rax, [rbp+57h+var_78]
0x14002a063  mov     ecx, r12d
0x14002a066  sub     ecx, eax
0x14002a068  mov     r9d, 1; int
0x14002a06e  sub     ecx, 4
0x14002a071  add     rax, 4
0x14002a075  mov     [rsp+0F0h+cbInput], ecx; cbInput
0x14002a079  xor     r8d, r8d; int
0x14002a07c  mov     ecx, r13d; int
0x14002a07f  mov     [rsp+0F0h+pbInput], rax; pbInput
0x14002a084  mov     rdx, r15; int
0x14002a087  call    AppHashHashBytes
0x14002a08c  mov     edi, eax
0x14002a08e  test    eax, eax
0x14002a090  js      loc_14002A26B
0x14002a096  mov     ecx, r14d
0x14002a099  lea     rax, [r12+8]
0x14002a09e  sub     ecx, r12d
0x14002a0a1  mov     r9d, 1; int
0x14002a0a7  add     ecx, 0FFFFFFF8h
0x14002a0aa  xor     r8d, r8d; int
0x14002a0ad  add     ecx, esi
0x14002a0af  mov     rdx, r15; int
0x14002a0b2  mov     [rsp+0F0h+cbInput], ecx; cbInput
0x14002a0b6  mov     ecx, r13d; int
0x14002a0b9  mov     [rsp+0F0h+pbInput], rax; pbInput
0x14002a0be  call    AppHashHashBytes
0x14002a0c3  mov     edi, eax
0x14002a0c5  test    eax, eax
0x14002a0c7  js      loc_14002A26B
0x14002a0cd  mov     eax, dword ptr [rbp+57h+var_98+4]
0x14002a0d0  mov     dword ptr [rbp+57h+var_98], eax
0x14002a0d3  jmp     short loc_14002A10F
0x14002a0d5  mov     eax, [rbp+57h+var_B0]
0x14002a0d8  test    ecx, ecx
0x14002a0da  jz      short loc_14002A0E5
0x14002a0dc  test    eax, eax
0x14002a0de  jns     short loc_14002A0E5
0x14002a0e0  xor     r9d, r9d
0x14002a0e3  jmp     short loc_14002A0EB
0x14002a0e5  mov     r9d, 1; int
0x14002a0eb  mov     [rsp+0F0h+cbInput], esi; cbInput
0x14002a0ef  mov     r8d, 1; int
0x14002a0f5  mov     rdx, r15; int
0x14002a0f8  mov     [rsp+0F0h+pbInput], r14; pbInput
0x14002a0fd  mov     ecx, r13d; int
0x14002a100  call    AppHashHashBytes
0x14002a105  mov     edi, eax
0x14002a107  test    eax, eax
0x14002a109  js      loc_14002A26B
0x14002a10f  mov     rdx, [rbp+57h+var_70]
0x14002a113  mov     eax, esi
0x14002a115  sub     rdx, rax
0x14002a118  add     [rbp+57h+var_A8], rax
0x14002a11c  mov     [rbp+57h+var_70], rdx
0x14002a120  jmp     loc_140029E86
0x14002a125  xor     ecx, ecx
0x14002a127  cmp     ecx, r13d
0x14002a12a  jnb     loc_14002A1D2
0x14002a130  mov     eax, ecx
0x14002a132  shl     rax, 5
0x14002a136  cmp     dword ptr [rax+r15+10h], 0
0x14002a13c  jnz     short loc_14002A142
0x14002a13e  inc     ecx
0x14002a140  jmp     short loc_14002A127
0x14002a142  cmp     dword ptr [rbp+57h+var_98], 0
0x14002a146  jz      loc_14002A1D2
0x14002a14c  mov     eax, [rbp+57h+var_90]
0x14002a14f  test    eax, eax
0x14002a151  jz      short loc_14002A1D2
0x14002a153  cmp     rax, rbx
0x14002a156  jnb     short loc_14002A1D2
0x14002a158  mov     rsi, rbx
0x14002a15b  mov     [rbp+57h+var_A8], rax
0x14002a15f  sub     rsi, rax
0x14002a162  mov     edi, 10000h
0x14002a167  test    rsi, rsi
0x14002a16a  jz      short loc_14002A1D2
0x14002a16c  mov     rcx, [rbp+57h+var_60]
0x14002a170  lea     rdx, [rbp+57h+var_A8]
0x14002a174  mov     eax, edi
0x14002a176  mov     r12d, esi
0x14002a179  cmp     rax, rsi
0x14002a17c  mov     r9, r14
0x14002a17f  mov     rax, [rbp+57h+var_68]
0x14002a183  cmovbe  r12d, edi
0x14002a187  mov     r8d, r12d
0x14002a18a  mov     rax, [rax+8]
0x14002a18e  call    _guard_dispatch_icall
0x14002a193  mov     edi, eax
0x14002a195  test    eax, eax
0x14002a197  js      loc_14002A26B
0x14002a19d  xor     r9d, r9d; int
0x14002a1a0  mov     [rsp+0F0h+cbInput], r12d; cbInput
0x14002a1a5  mov     rdx, r15; int
0x14002a1a8  mov     [rsp+0F0h+pbInput], r14; pbInput
0x14002a1ad  mov     ecx, r13d; int
0x14002a1b0  lea     r8d, [r9+1]; int
0x14002a1b4  call    AppHashHashBytes
0x14002a1b9  mov     edi, eax
0x14002a1bb  test    eax, eax
0x14002a1bd  js      loc_14002A26B
0x14002a1c3  mov     eax, r12d
0x14002a1c6  mov     edi, r12d
0x14002a1c9  sub     rsi, rax
0x14002a1cc  add     [rbp+57h+var_A8], rax
0x14002a1d0  jmp     short loc_14002A167
0x14002a1d2  mov     esi, [rbp+57h+var_AC]
0x14002a1d5  test    esi, esi
0x14002a1d7  jz      short loc_14002A1E0
0x14002a1d9  mov     eax, [rbp+57h+var_B0]
0x14002a1dc  test    eax, eax
  ... truncated ...
```
