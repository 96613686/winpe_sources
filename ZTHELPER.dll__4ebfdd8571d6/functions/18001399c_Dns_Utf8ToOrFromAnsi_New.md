# Dns_Utf8ToOrFromAnsi_New

- ea: `0x18001399c`
- end: `0x180013bce`
- name: `Dns_Utf8ToOrFromAnsi_New`
- size: `562`
- prototype: `__int64 __fastcall(_WORD *, unsigned int, _BYTE *, unsigned int, int, int)`
- caller_count: `5`
- callee_count: `9`
- tags: ``

## callers

- `0x180012d64`
- `0x180012dac`
- `0x180013344`
- `0x1800135ec`
- `0x180013944`

## callees

- `0x1800014b0`
- `0x180013538`
- `0x180013544`
- `0x1800135ec`
- `0x18001397c`
- `0x18001399c`
- `0x180013c44`
- `0x180013f19`
- `0x180016e8c`

## pseudocode

```c
__int64 __fastcall Dns_Utf8ToOrFromAnsi_New(_WORD *a1, unsigned int a2, _BYTE *a3, unsigned int a4, int a5, int a6)
{
  __int64 v7; // r8
  unsigned int v8; // edi
  _WORD *v9; // r14
  __int64 v10; // rbx
  __int64 v11; // rax
  unsigned int v12; // r8d
  unsigned int BufferLengthForStringCopy_New; // eax
  CHAR *New; // rbx
  unsigned int v16; // edi
  unsigned int v17[4]; // [rsp+50h] [rbp-B0h] BYREF
  __int128 v18; // [rsp+60h] [rbp-A0h] BYREF
  unsigned int v19[4]; // [rsp+70h] [rbp-90h] BYREF
  _WORD v20[264]; // [rsp+80h] [rbp-80h] BYREF

  v7 = a2;
  v17[0] = a2;
  v8 = a4;
  v9 = a1;
  v10 = -1;
  if ( (BYTE1(xmmword_18001F260) & 8) != 0 )
  {
    v18 = (unsigned __int64)a3;
    if ( !a3 )
      goto LABEL_10;
    LODWORD(v11) = a4;
    if ( a4 == -1 )
    {
      v11 = -1;
      do
        ++v11;
      while ( a3[v11] );
    }
    if ( (_DWORD)v11 )
    {
      LODWORD(a1) = 0xFFFF;
      if ( (unsigned int)v11 <= 0xFFFF )
        WORD4(v18) = v11;
      else
        WORD4(v18) = -1;
    }
    else
    {
LABEL_10:
      WORD4(v18) = 1;
      *(_QWORD *)&v18 = &qword_18001AD20;
    }
    WPP_SF_qdq_COUNTEDSTRING_ddd(
      (_DWORD)a1,
      10,
      (unsigned int)WPP_e9b3f03b65ba3ab9def3209b6bad21be_Traceguids,
      (_DWORD)v9,
      a2,
      (__int64)a3,
      (__int64)&v18);
    v7 = v17[0];
  }
  if ( !v8 )
  {
    do
      ++v10;
    while ( a3[v10] );
    v8 = v10;
  }
  if ( (unsigned int)Dns_IsStringAsciiEx_New(a3, v8, v7, 1) )
  {
    if ( !v9 )
      return v8 + 1;
    if ( v12 > v8 )
    {
      memcpy_0(v9, a3, v8);
      *((_BYTE *)v9 + v8) = 0;
      return v8 + 1;
    }
    return 0;
  }
  BufferLengthForStringCopy_New = Dns_GetBufferLengthForStringCopy_New(a3, v8);
  if ( BufferLengthForStringCopy_New <= 0x208 )
  {
    v19[0] = 520;
    if ( !BufferLengthForStringCopy_New )
      return 0;
    New = (CHAR *)v20;
    if ( !(unsigned int)Dns_StringCopyU(v20, v19, a3, v8, a5, 1) )
      return 0;
  }
  else
  {
    New = (CHAR *)Dns_StringCopyAllocate_New(a3, v8, a5, 1);
    if ( !New )
      goto LABEL_27;
  }
  if ( v9 )
  {
    v16 = Dns_StringCopyU(v9, v17, New, 0, 1, a6);
    if ( !v16 )
    {
LABEL_27:
      if ( New != (CHAR *)v20 )
        Rpc_Free(New);
      return 0;
    }
  }
  else
  {
    v16 = Dns_GetBufferLengthForStringCopy_New(New, 0);
  }
  if ( New != (CHAR *)v20 )
    Rpc_Free(New);
  return v16;
}

```

## disassembly

```asm
0x18001399c  push    rbp
0x18001399e  push    rbx
0x18001399f  push    rsi
0x1800139a0  push    rdi
0x1800139a1  push    r12
0x1800139a3  push    r14
0x1800139a5  push    r15
0x1800139a7  lea     rbp, [rsp-1A0h]
0x1800139af  sub     rsp, 2A0h
0x1800139b6  mov     rax, cs:__security_cookie
0x1800139bd  xor     rax, rsp
0x1800139c0  mov     [rbp+1D0h+var_40], rax
0x1800139c7  mov     r15d, [rbp+1D0h+arg_20]
0x1800139ce  mov     rsi, r8
0x1800139d1  mov     r8d, edx
0x1800139d4  mov     [rsp+2D0h+var_280], edx
0x1800139d8  mov     edi, r9d
0x1800139db  mov     r14, rcx
0x1800139de  mov     r12d, [rbp+1D0h+arg_28]
0x1800139e5  or      rbx, 0FFFFFFFFFFFFFFFFh
0x1800139e9  test    byte ptr cs:xmmword_18001F260+1, 8
0x1800139f0  lea     r9d, [rbx+2]
0x1800139f4  jz      loc_180013A98
0x1800139fa  xorps   xmm0, xmm0
0x1800139fd  movups  [rsp+2D0h+var_270], xmm0
0x180013a02  mov     qword ptr [rsp+2D0h+var_270], rsi
0x180013a07  test    rsi, rsi
0x180013a0a  jz      short loc_180013A3A
0x180013a0c  mov     eax, edi
0x180013a0e  cmp     edi, 0FFFFFFFFh
0x180013a11  jnz     short loc_180013A1F
0x180013a13  mov     rax, rbx
0x180013a16  inc     rax
0x180013a19  cmp     byte ptr [rsi+rax], 0
0x180013a1d  jnz     short loc_180013A16
0x180013a1f  test    eax, eax
0x180013a21  jz      short loc_180013A3A
0x180013a23  mov     ecx, 0FFFFh
0x180013a28  cmp     eax, ecx
0x180013a2a  jbe     short loc_180013A33
0x180013a2c  mov     word ptr [rsp+2D0h+var_270+8], cx
0x180013a31  jmp     short loc_180013A4C
0x180013a33  mov     word ptr [rsp+2D0h+var_270+8], ax
0x180013a38  jmp     short loc_180013A4C
0x180013a3a  lea     rax, qword_18001AD20
0x180013a41  mov     word ptr [rsp+2D0h+var_270+8], r9w
0x180013a47  mov     qword ptr [rsp+2D0h+var_270], rax
0x180013a4c  movaps  xmm0, [rsp+2D0h+var_270]
0x180013a51  lea     rax, [rsp+2D0h+var_270]
0x180013a56  mov     [rsp+2D0h+var_288], r12d
0x180013a5b  mov     edx, 0Ah
0x180013a60  mov     [rsp+2D0h+var_290], r15d
0x180013a65  mov     r9, r14
0x180013a68  mov     [rsp+2D0h+var_298], edi
0x180013a6c  mov     [rsp+2D0h+var_2A0], rax
0x180013a71  mov     qword ptr [rsp+2D0h+var_2A8], rsi
0x180013a76  mov     [rsp+2D0h+var_2B0], r8d
0x180013a7b  lea     r8, WPP_e9b3f03b65ba3ab9def3209b6bad21be_Traceguids
0x180013a82  movdqa  [rsp+2D0h+var_270], xmm0
0x180013a88  call    WPP_SF_qdq_COUNTEDSTRING_ddd
0x180013a8d  mov     r8d, [rsp+2D0h+var_280]
0x180013a92  mov     r9d, 1
0x180013a98  test    edi, edi
0x180013a9a  jnz     short loc_180013AA8
0x180013a9c  inc     rbx
0x180013a9f  cmp     byte ptr [rsi+rbx], 0
0x180013aa3  jnz     short loc_180013A9C
0x180013aa5  mov     rdi, rbx
0x180013aa8  mov     edx, edi
0x180013aaa  mov     rcx, rsi
0x180013aad  call    Dns_IsStringAsciiEx_New
0x180013ab2  test    eax, eax
0x180013ab4  jz      short loc_180013AE3
0x180013ab6  test    r14, r14
0x180013ab9  jnz     short loc_180013AC3
0x180013abb  lea     eax, [rdi+1]
0x180013abe  jmp     loc_180013B85
0x180013ac3  cmp     r8d, edi
0x180013ac6  jbe     loc_180013B83
0x180013acc  mov     r8d, edi; Size
0x180013acf  mov     rdx, rsi; Src
0x180013ad2  mov     rcx, r14; void *
0x180013ad5  mov     ebx, edi
0x180013ad7  call    memcpy_0
0x180013adc  mov     byte ptr [rbx+r14], 0
0x180013ae1  jmp     short loc_180013ABB
0x180013ae3  mov     r8d, r15d
0x180013ae6  mov     edx, edi
0x180013ae8  mov     rcx, rsi
0x180013aeb  call    Dns_GetBufferLengthForStringCopy_New
0x180013af0  mov     ecx, 208h
0x180013af5  cmp     eax, ecx
0x180013af7  jbe     short loc_180013B16
0x180013af9  mov     r9d, 1
0x180013aff  mov     r8d, r15d
0x180013b02  mov     edx, edi
0x180013b04  mov     rcx, rsi
0x180013b07  call    Dns_StringCopyAllocate_New
0x180013b0c  mov     rbx, rax
0x180013b0f  test    rax, rax
0x180013b12  jz      short loc_180013B72
0x180013b14  jmp     short loc_180013B47
0x180013b16  mov     [rsp+2D0h+var_260], ecx
0x180013b1a  test    eax, eax
0x180013b1c  jz      short loc_180013B83
0x180013b1e  mov     [rsp+2D0h+var_2A8], 1; int
0x180013b26  lea     rdx, [rsp+2D0h+var_260]
0x180013b2b  mov     r9d, edi
0x180013b2e  mov     [rsp+2D0h+var_2B0], r15d; int
0x180013b33  mov     r8, rsi
0x180013b36  lea     rcx, [rbp+1D0h+var_250]; void *
0x180013b3a  lea     rbx, [rbp+1D0h+var_250]
0x180013b3e  call    Dns_StringCopyU
0x180013b43  test    eax, eax
0x180013b45  jz      short loc_180013B83
0x180013b47  test    r14, r14
0x180013b4a  jz      short loc_180013BA6
0x180013b4c  mov     [rsp+2D0h+var_2A8], r12d; int
0x180013b51  lea     rdx, [rsp+2D0h+var_280]
0x180013b56  xor     r9d, r9d
0x180013b59  mov     [rsp+2D0h+var_2B0], 1; int
0x180013b61  mov     r8, rbx
0x180013b64  mov     rcx, r14; void *
0x180013b67  call    Dns_StringCopyU
0x180013b6c  mov     edi, eax
0x180013b6e  test    eax, eax
0x180013b70  jnz     short loc_180013BB9
0x180013b72  lea     rax, [rbp+1D0h+var_250]
0x180013b76  cmp     rbx, rax
0x180013b79  jz      short loc_180013B83
0x180013b7b  mov     rcx, rbx; lpMem
0x180013b7e  call    Rpc_Free
0x180013b83  xor     eax, eax
0x180013b85  mov     rcx, [rbp+1D0h+var_40]
0x180013b8c  xor     rcx, rsp; StackCookie
0x180013b8f  call    __security_check_cookie
0x180013b94  add     rsp, 2A0h
0x180013b9b  pop     r15
0x180013b9d  pop     r14
0x180013b9f  pop     r12
0x180013ba1  pop     rdi
0x180013ba2  pop     rsi
0x180013ba3  pop     rbx
0x180013ba4  pop     rbp
0x180013ba5  retn
0x180013ba6  xor     edx, edx
0x180013ba8  mov     r9d, r12d
0x180013bab  mov     rcx, rbx
0x180013bae  lea     r8d, [rdx+1]
0x180013bb2  call    Dns_GetBufferLengthForStringCopy_New
0x180013bb7  mov     edi, eax
0x180013bb9  lea     rax, [rbp+1D0h+var_250]
0x180013bbd  cmp     rbx, rax
0x180013bc0  jz      short loc_180013BCA
0x180013bc2  mov     rcx, rbx; lpMem
0x180013bc5  call    Rpc_Free
0x180013bca  mov     eax, edi
0x180013bcc  jmp     short loc_180013B85
```
