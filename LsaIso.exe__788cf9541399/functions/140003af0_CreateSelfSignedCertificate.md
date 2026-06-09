# CreateSelfSignedCertificate

- ea: `0x140003af0`
- end: `0x140003e51`
- name: `CreateSelfSignedCertificate`
- size: `865`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: ``

## callers

- `0x140004b70`

## callees

- `0x140003af0`
- `0x140004d1c`
- `0x1400066f0`
- `0x140006720`
- `0x140038cd2`

## import_xrefs

- `iumcrypt!iumCryptSignAndEncodeCertificate` at `0x140003d0c`
- `iumcrypt!iumCryptSignAndEncodeCertificate` at `0x140003da7`
- `iumcrypt!iumCryptSignAndEncodeCertificate` at `0x140003d0c`
- `iumcrypt!iumCryptSignAndEncodeCertificate` at `0x140003da7`
- `iumcrypt!iumCryptEncodeObjectEx` at `0x140003bd0`
- `iumcrypt!iumCryptEncodeObjectEx` at `0x140003bd0`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140003e21`
- `api-ms-win-core-heap-obsolete-l1-1-0!LocalFree` at `0x140003e21`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003db1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003bda`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003d16`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140003db1`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003c6e`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x140003c6e`

## string_xrefs

- `0x140003c1c`: `CreateSelfSignedCertificate`
- `0x140003de6`: `CreateSelfSignedCertificate`

## pseudocode

```c
__int64 __fastcall CreateSelfSignedCertificate(void *a1, __int128 *a2, __int64 a3, _DWORD *a4, unsigned __int8 **a5)
{
  __int64 v9; // rax
  unsigned __int8 **v10; // r14
  signed int LastError; // ebx
  int v12; // r8d
  _QWORD *v13; // rcx
  char v14; // al
  int v15; // edx
  __int128 v16; // xmm0
  __int128 v17; // xmm1
  __int128 v18; // xmm0
  unsigned __int8 *v19; // rax
  unsigned __int8 *v20; // rdi
  int v21; // r8d
  int v22; // eax
  HLOCAL hMem; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME SystemTimeAsFileTime; // [rsp+60h] [rbp-A0h] BYREF
  _QWORD v26[2]; // [rsp+68h] [rbp-98h] BYREF
  int v27; // [rsp+78h] [rbp-88h] BYREF
  const char **v28; // [rsp+80h] [rbp-80h]
  const char *v29; // [rsp+88h] [rbp-78h] BYREF
  int v30; // [rsp+90h] [rbp-70h]
  int v31; // [rsp+98h] [rbp-68h]
  __int64 v32; // [rsp+A0h] [rbp-60h]
  _DWORD v33[4]; // [rsp+B0h] [rbp-50h] BYREF
  char *v34; // [rsp+C0h] [rbp-40h]
  struct _CRYPT_ALGORITHM_IDENTIFIER v35; // [rsp+C8h] [rbp-38h] BYREF
  int v36; // [rsp+E0h] [rbp-20h]
  HLOCAL v37; // [rsp+E8h] [rbp-18h]
  struct _FILETIME v38; // [rsp+F0h] [rbp-10h]
  __int64 v39; // [rsp+F8h] [rbp-8h]
  int v40; // [rsp+100h] [rbp+0h]
  HLOCAL v41; // [rsp+108h] [rbp+8h]
  __int128 v42; // [rsp+110h] [rbp+10h]
  __int128 v43; // [rsp+120h] [rbp+20h]
  __int128 v44; // [rsp+130h] [rbp+30h]
  char v45; // [rsp+1D0h] [rbp+D0h] BYREF
  size_t size; // [rsp+1D8h] [rbp+D8h] BYREF

  LODWORD(size) = 0;
  memset_0(v33, 0, 0xD0u);
  SystemTimeAsFileTime = 0;
  v29 = "2.5.4.3";
  v9 = -1;
  v45 = 1;
  hMem = 0;
  v30 = 13;
  do
    ++v9;
  while ( *(_WORD *)(a3 + 2 * v9) );
  v10 = a5;
  v32 = a3;
  v31 = 2 * v9;
  v27 = 1;
  v28 = &v29;
  *a5 = 0;
  v26[1] = &v27;
  v26[0] = 1;
  *a4 = 0;
  LODWORD(a5) = 0;
  if ( iumCryptEncodeObjectEx(1u, (const char *)7, v26, 0x8000u, 0, &hMem, (unsigned int *)&a5) )
  {
    v33[2] = 1;
    v34 = &v45;
    v35.pszObjId = "1.2.840.113549.1.1.11";
    v37 = hMem;
    v36 = (int)a5;
    v33[0] = 2;
    GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
    v16 = *a2;
    v17 = a2[1];
    v38 = SystemTimeAsFileTime;
    v42 = v16;
    v18 = a2[2];
    v39 = *(_QWORD *)&SystemTimeAsFileTime + 31536000000000000LL;
    v41 = hMem;
    v40 = (int)a5;
    v43 = v17;
    v44 = v18;
    if ( iumCryptSignAndEncodeCertificate(a1, 0, 1u, (const char *)2, v33, &v35, 0, 0, (unsigned int *)&size) )
    {
      v19 = (unsigned __int8 *)MIDL_user_allocate((unsigned int)size);
      v20 = v19;
      if ( v19 )
      {
        if ( iumCryptSignAndEncodeCertificate(a1, 0, 1u, (const char *)2, v33, &v35, 0, v19, (unsigned int *)&size) )
        {
          v22 = size;
          LastError = 0;
          *v10 = v20;
          *a4 = v22;
        }
        else
        {
          LastError = GetLastError();
          if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
            WPP_SF_sdD(
              *((_QWORD *)WPP_GLOBAL_Control + 2),
              18,
              v21,
              (unsigned int)"CreateSelfSignedCertificate",
              LastError,
              LastError);
          SafeAllocaFreeToHeap(v20);
        }
      }
      else
      {
        LastError = 8;
      }
    }
    else
    {
      LastError = GetLastError();
      v13 = WPP_GLOBAL_Control;
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      {
        v14 = LastError;
        v15 = 17;
        goto LABEL_7;
      }
    }
  }
  else
  {
    LastError = GetLastError();
    v13 = WPP_GLOBAL_Control;
    if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      v14 = LastError;
      v15 = 16;
LABEL_7:
      WPP_SF_sdD(v13[2], v15, v12, (unsigned int)"CreateSelfSignedCertificate", LastError, v14);
    }
  }
  if ( hMem )
    LocalFree(hMem);
  if ( LastError > 0 )
    return (unsigned __int16)LastError | 0xC0070000;
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x140003af0  mov     [rsp-8+arg_0], rbx
0x140003af5  push    rbp
0x140003af6  push    rsi
0x140003af7  push    rdi
0x140003af8  push    r12
0x140003afa  push    r13
0x140003afc  push    r14
0x140003afe  push    r15
0x140003b00  lea     rbp, [rsp-80h]
0x140003b05  sub     rsp, 180h
0x140003b0c  mov     rbx, r8
0x140003b0f  mov     rdi, rdx
0x140003b12  mov     r15, rcx
0x140003b15  xor     r12d, r12d
0x140003b18  xor     edx, edx; Val
0x140003b1a  mov     dword ptr [rbp+0B0h+size], r12d
0x140003b21  mov     r8d, 0D0h; Size
0x140003b27  lea     rcx, [rbp+0B0h+var_100]; void *
0x140003b2b  mov     rsi, r9
0x140003b2e  call    memset_0
0x140003b33  lea     rax, a2543; "2.5.4.3"
0x140003b3a  mov     qword ptr [rsp+1B0h+SystemTimeAsFileTime.dwLowDateTime], r12
0x140003b3f  lea     r13d, [r12+1]
0x140003b44  mov     [rbp+0B0h+var_128], rax
0x140003b48  or      rax, 0FFFFFFFFFFFFFFFFh
0x140003b4c  mov     [rbp+0B0h+arg_10], r13b
0x140003b53  mov     [rsp+1B0h+hMem], r12
0x140003b58  mov     [rbp+0B0h+var_120], 0Dh
0x140003b5f  inc     rax
0x140003b62  cmp     [rbx+rax*2], r12w
0x140003b67  jnz     short loc_140003B5F
0x140003b69  mov     r14, [rbp+0B0h+arg_20]
0x140003b70  lea     r8, [rsp+1B0h+var_148]
0x140003b75  add     eax, eax
0x140003b77  mov     [rbp+0B0h+var_110], rbx
0x140003b7b  mov     [rbp+0B0h+var_118], eax
0x140003b7e  mov     r9d, 8000h
0x140003b84  lea     rax, [rbp+0B0h+var_128]
0x140003b88  mov     [rsp+1B0h+var_138], r13d
0x140003b8d  mov     [rbp+0B0h+var_130], rax
0x140003b91  mov     edx, 7
0x140003b96  lea     rax, [rsp+1B0h+var_138]
0x140003b9b  mov     [r14], r12
0x140003b9e  mov     [rsp+1B0h+var_140], rax
0x140003ba3  mov     ecx, r13d
0x140003ba6  lea     rax, [rbp+0B0h+arg_20]
0x140003bad  mov     [rsp+1B0h+var_148], r13
0x140003bb2  mov     [rsp+1B0h+var_180], rax
0x140003bb7  lea     rax, [rsp+1B0h+hMem]
0x140003bbc  mov     [rsp+1B0h+var_188], rax
0x140003bc1  mov     [rsp+1B0h+var_190], r12
0x140003bc6  mov     [rsi], r12d
0x140003bc9  mov     dword ptr [rbp+0B0h+arg_20], r12d
0x140003bd0  call    cs:__imp_?iumCryptEncodeObjectEx@@YAHKPEBDPEBXKPEAU_CRYPT_ENCODE_PARA@@PEAXPEAK@Z; iumCryptEncodeObjectEx(ulong,char const *,void const *,ulong,_CRYPT_ENCODE_PARA *,void *,ulong *)
0x140003bd6  test    eax, eax
0x140003bd8  jnz     short loc_140003C35
0x140003bda  call    cs:__imp_GetLastError
0x140003be0  mov     ebx, eax
0x140003be2  mov     rcx, cs:WPP_GLOBAL_Control
0x140003be9  lea     rax, WPP_GLOBAL_Control
0x140003bf0  cmp     rcx, rax
0x140003bf3  jz      loc_140003E17
0x140003bf9  test    [rcx+1Ch], r13b
0x140003bfd  jz      loc_140003E17
0x140003c03  test    ebx, ebx
0x140003c05  jg      short loc_140003C0B
0x140003c07  mov     eax, ebx
0x140003c09  jmp     short loc_140003C13
0x140003c0b  movzx   eax, bx
0x140003c0e  or      eax, 0C0070000h
0x140003c13  mov     edx, 10h
0x140003c18  mov     rcx, [rcx+10h]
0x140003c1c  lea     r9, aCreateselfsign; "CreateSelfSignedCertificate"
0x140003c23  mov     dword ptr [rsp+1B0h+var_188], eax
0x140003c27  mov     dword ptr [rsp+1B0h+var_190], ebx
0x140003c2b  call    WPP_SF_sdD
0x140003c30  jmp     loc_140003E17
0x140003c35  lea     rax, [rbp+0B0h+arg_10]
0x140003c3c  mov     [rbp+0B0h+var_F8], r13d
0x140003c40  mov     [rbp+0B0h+var_F0], rax
0x140003c44  lea     rcx, [rsp+1B0h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x140003c49  lea     rax, a12840113549111; "1.2.840.113549.1.1.11"
0x140003c50  mov     ebx, 2
0x140003c55  mov     qword ptr [rbp+0B0h+var_E8], rax
0x140003c59  mov     rax, [rsp+1B0h+hMem]
0x140003c5e  mov     [rbp+0B0h+var_C8], rax
0x140003c62  mov     eax, dword ptr [rbp+0B0h+arg_20]
0x140003c68  mov     [rbp+0B0h+var_D0], eax
0x140003c6b  mov     [rbp+0B0h+var_100], ebx
0x140003c6e  call    cs:__imp_GetSystemTimeAsFileTime
0x140003c74  mov     rax, qword ptr [rsp+1B0h+SystemTimeAsFileTime.dwLowDateTime]
0x140003c79  mov     r9d, ebx
0x140003c7c  mov     ecx, [rsp+1B0h+SystemTimeAsFileTime.dwHighDateTime]
0x140003c80  mov     r8d, r13d
0x140003c83  movups  xmm0, xmmword ptr [rdi]
0x140003c86  mov     dword ptr [rsp+1B0h+var_160], eax
0x140003c8a  xor     edx, edx
0x140003c8c  movups  xmm1, xmmword ptr [rdi+10h]
0x140003c90  mov     [rbp+0B0h+var_C0], eax
0x140003c93  mov     dword ptr [rsp+1B0h+var_160+4], ecx
0x140003c97  mov     rax, [rsp+1B0h+var_160]
0x140003c9c  mov     [rbp+0B0h+var_BC], ecx
0x140003c9f  mov     rcx, 7009D32DA30000h
0x140003ca9  add     rax, rcx
0x140003cac  movaps  [rbp+0B0h+var_A0], xmm0
0x140003cb0  movups  xmm0, xmmword ptr [rdi+20h]
0x140003cb4  mov     [rsp+1B0h+var_160], rax
0x140003cb9  mov     rcx, r15
0x140003cbc  shr     rax, 20h
0x140003cc0  mov     dword ptr [rbp+0B0h+var_B8+4], eax
0x140003cc3  mov     eax, dword ptr [rsp+1B0h+var_160]
0x140003cc7  mov     dword ptr [rbp+0B0h+var_B8], eax
0x140003cca  mov     rax, [rsp+1B0h+hMem]
0x140003ccf  mov     [rbp+0B0h+var_A8], rax
0x140003cd3  mov     eax, dword ptr [rbp+0B0h+arg_20]
0x140003cd9  mov     [rbp+0B0h+var_B0], eax
0x140003cdc  lea     rax, [rbp+0B0h+size]
0x140003ce3  mov     [rsp+1B0h+var_170], rax
0x140003ce8  lea     rax, [rbp+0B0h+var_E8]
0x140003cec  mov     [rsp+1B0h+var_178], r12
0x140003cf1  mov     [rsp+1B0h+var_180], r12
0x140003cf6  mov     [rsp+1B0h+var_188], rax
0x140003cfb  lea     rax, [rbp+0B0h+var_100]
0x140003cff  mov     [rsp+1B0h+var_190], rax
0x140003d04  movaps  [rbp+0B0h+var_90], xmm1
0x140003d08  movaps  [rbp+0B0h+var_80], xmm0
0x140003d0c  call    cs:__imp_?iumCryptSignAndEncodeCertificate@@YAHPEAXKKPEBDPEBXPEAU_CRYPT_ALGORITHM_IDENTIFIER@@2PEAEPEAK@Z; iumCryptSignAndEncodeCertificate(void *,ulong,ulong,char const *,void const *,_CRYPT_ALGORITHM_IDENTIFIER *,void const *,uchar *,ulong *)
0x140003d12  test    eax, eax
0x140003d14  jnz     short loc_140003D59
0x140003d16  call    cs:__imp_GetLastError
0x140003d1c  mov     ebx, eax
0x140003d1e  mov     rcx, cs:WPP_GLOBAL_Control
0x140003d25  lea     rax, WPP_GLOBAL_Control
0x140003d2c  cmp     rcx, rax
0x140003d2f  jz      loc_140003E17
0x140003d35  test    [rcx+1Ch], r13b
0x140003d39  jz      loc_140003E17
0x140003d3f  test    ebx, ebx
0x140003d41  jg      short loc_140003D47
0x140003d43  mov     eax, ebx
0x140003d45  jmp     short loc_140003D4F
0x140003d47  movzx   eax, bx
0x140003d4a  or      eax, 0C0070000h
0x140003d4f  mov     edx, 11h
0x140003d54  jmp     loc_140003C18
0x140003d59  mov     ecx, dword ptr [rbp+0B0h+size]; size
0x140003d5f  call    MIDL_user_allocate
0x140003d64  mov     rdi, rax
0x140003d67  test    rax, rax
0x140003d6a  jnz     short loc_140003D74
0x140003d6c  lea     ebx, [rax+8]
0x140003d6f  jmp     loc_140003E17
0x140003d74  lea     rax, [rbp+0B0h+size]
0x140003d7b  mov     r9, rbx
0x140003d7e  mov     [rsp+1B0h+var_170], rax
0x140003d83  mov     r8d, r13d
0x140003d86  mov     [rsp+1B0h+var_178], rdi
0x140003d8b  lea     rax, [rbp+0B0h+var_E8]
0x140003d8f  mov     [rsp+1B0h+var_180], r12
0x140003d94  xor     edx, edx
0x140003d96  mov     [rsp+1B0h+var_188], rax
0x140003d9b  mov     rcx, r15
0x140003d9e  lea     rax, [rbp+0B0h+var_100]
0x140003da2  mov     [rsp+1B0h+var_190], rax
0x140003da7  call    cs:__imp_?iumCryptSignAndEncodeCertificate@@YAHPEAXKKPEBDPEBXPEAU_CRYPT_ALGORITHM_IDENTIFIER@@2PEAEPEAK@Z; iumCryptSignAndEncodeCertificate(void *,ulong,ulong,char const *,void const *,_CRYPT_ALGORITHM_IDENTIFIER *,void const *,uchar *,ulong *)
0x140003dad  test    eax, eax
0x140003daf  jnz     short loc_140003E09
0x140003db1  call    cs:__imp_GetLastError
0x140003db7  mov     ebx, eax
0x140003db9  mov     rcx, cs:WPP_GLOBAL_Control
0x140003dc0  lea     rax, WPP_GLOBAL_Control
0x140003dc7  cmp     rcx, rax
0x140003dca  jz      short loc_140003DFF
0x140003dcc  test    [rcx+1Ch], r13b
0x140003dd0  jz      short loc_140003DFF
0x140003dd2  test    ebx, ebx
0x140003dd4  jg      short loc_140003DDA
0x140003dd6  mov     eax, ebx
0x140003dd8  jmp     short loc_140003DE2
0x140003dda  movzx   eax, bx
0x140003ddd  or      eax, 0C0070000h
0x140003de2  mov     rcx, [rcx+10h]
0x140003de6  lea     r9, aCreateselfsign; "CreateSelfSignedCertificate"
0x140003ded  mov     dword ptr [rsp+1B0h+var_188], eax
0x140003df1  mov     edx, 12h
0x140003df6  mov     dword ptr [rsp+1B0h+var_190], ebx
0x140003dfa  call    WPP_SF_sdD
0x140003dff  mov     rcx, rdi; void *
0x140003e02  call    SafeAllocaFreeToHeap
0x140003e07  jmp     short loc_140003E17
0x140003e09  mov     eax, dword ptr [rbp+0B0h+size]
0x140003e0f  mov     ebx, r12d
0x140003e12  mov     [r14], rdi
0x140003e15  mov     [rsi], eax
0x140003e17  mov     rcx, [rsp+1B0h+hMem]; hMem
0x140003e1c  test    rcx, rcx
0x140003e1f  jz      short loc_140003E27
0x140003e21  call    cs:__imp_LocalFree
0x140003e27  test    ebx, ebx
0x140003e29  jle     short loc_140003E34
0x140003e2b  movzx   ebx, bx
0x140003e2e  or      ebx, 0C0070000h
0x140003e34  mov     eax, ebx
0x140003e36  mov     rbx, [rsp+1B0h+arg_0]
0x140003e3e  add     rsp, 180h
0x140003e45  pop     r15
0x140003e47  pop     r14
0x140003e49  pop     r13
0x140003e4b  pop     r12
0x140003e4d  pop     rdi
0x140003e4e  pop     rsi
0x140003e4f  pop     rbp
0x140003e50  retn
```
