# SortCertificatesInPlace(_CERT_CONTEXT const * * const,ulong)

- ea: `0x180090ae4`
- end: `0x180090d41`
- name: `?SortCertificatesInPlace@@YAJQEAPEBU_CERT_CONTEXT@@K@Z`
- size: `605`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT **const, unsigned int)`
- caller_count: `2`
- callee_count: `9`
- tags: `broker_com_uri`

## callers

- `0x18008fdec`
- `0x1800905d0`

## callees

- `0x180004a24`
- `0x180005f24`
- `0x180006061`
- `0x1800859bc`
- `0x18008a9ec`
- `0x18008aa28`
- `0x18008aecc`
- `0x1800909c4`
- `0x180090ae4`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090b3b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090d2f`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090b3b`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180090d2f`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180090c83`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180090c83`

## string_xrefs

- `0x180090d08`: `StringCompare`

## pseudocode

```c
__int64 __fastcall SortCertificatesInPlace(const struct _CERT_CONTEXT **const a1, unsigned int a2)
{
  unsigned __int16 **v2; // r14
  __int64 v3; // r12
  unsigned int v5; // ebp
  size_t v7; // rax
  unsigned __int16 **v8; // rax
  __int64 v9; // rdx
  __int64 v10; // r9
  __int64 i; // rbx
  int TenantId; // eax
  const unsigned __int16 *v13; // r8
  __int64 v14; // rdi
  unsigned __int16 **v15; // rsi
  int j; // r15d
  int v17; // ebx
  const struct _CERT_CONTEXT *v18; // rsi
  const unsigned __int16 *v19; // rax
  int v20; // ecx
  __int64 v21; // rsi
  __int64 v22; // rbx
  size_t v23; // rdi
  int v24; // [rsp+70h] [rbp+8h] BYREF
  const unsigned __int16 *v25; // [rsp+80h] [rbp+18h]
  const struct _CERT_CONTEXT *v26; // [rsp+88h] [rbp+20h]

  v2 = 0;
  v3 = a2;
  if ( a1 )
  {
    v5 = 0;
    if ( a2 != 1 )
    {
      v7 = 8LL * a2;
      if ( !is_mul_ok(a2, 8u) )
        v7 = -1;
      v8 = (unsigned __int16 **)operator new[](v7, (const struct std::nothrow_t *)std::nothrow);
      v2 = v8;
      if ( !v8 )
      {
        v5 = -2147024882;
        Logger::TraceCritical(L"%s: Out of memory. Allocation failed.", L"SortCertificatesInPlace");
        goto LABEL_3;
      }
      memset_0(v8, 0, 8 * v3);
      for ( i = 0; (unsigned int)i < (unsigned int)v3; i = (unsigned int)(i + 1) )
      {
        TenantId = RegistrationCertStatus::GetTenantId(a1[i], &v2[i], 0);
        v5 = TenantId;
        if ( TenantId < 0 )
        {
          v13 = L"RegistrationCertStatus::GetTenantId";
LABEL_14:
          Logger::TraceError(
            L"%s: %s failed with error code: 0x%08x.",
            L"SortCertificatesInPlace",
            v13,
            (unsigned int)TenantId);
          v14 = 0;
          v15 = v2;
          goto LABEL_28;
        }
      }
      for ( j = 1; j < (int)v3; ++j )
      {
        v17 = j - 1;
        v18 = a1[j];
        v19 = v2[j];
        v25 = v19;
        v26 = v18;
        do
        {
          v24 = 0;
          TenantId = CompareStringInternal(v2[v17], v9, v19, v10, 1u, (enum COMPARE_STR_RESULT *)&v24);
          v5 = TenantId;
          if ( TenantId < 0 )
          {
            v13 = L"StringCompare";
            goto LABEL_14;
          }
          if ( v24 == 1 || v24 == 2 && CompareFileTime(&a1[v17]->pCertInfo->NotBefore, &v18->pCertInfo->NotBefore) <= 0 )
            break;
          --v17;
          v19 = v25;
        }
        while ( v17 >= 0 );
        v20 = v17 + 1;
        if ( v17 + 1 != j )
        {
          v21 = v17;
          v22 = v17 + 2;
          v23 = 8LL * (j - v20);
          memmove_0(&a1[v22], &a1[v21 + 1], v23);
          memmove_0(&v2[v22], &v2[v21 + 1], v23);
          a1[v21 + 1] = v26;
          v2[v21 + 1] = (unsigned __int16 *)v25;
        }
      }
    }
    v14 = 0;
    v15 = v2;
    if ( v2 )
    {
LABEL_28:
      while ( (unsigned int)v14 < (unsigned int)v3 )
      {
        free(v15[v14]);
        v15[v14] = 0;
        v14 = (unsigned int)(v14 + 1);
      }
    }
  }
  else
  {
    v5 = -2147024809;
    Logger::TraceError(L"%s: \"%s\" should not be null.", L"SortCertificatesInPlace", L"pCertContexts");
    Logger::WriteNullOrEmptyParameterFailureEvent(L"SortCertificatesInPlace", L"pCertContexts");
  }
LABEL_3:
  free(v2);
  return v5;
}

```

## disassembly

```asm
0x180090ae4  mov     [rsp+arg_8], rbx
0x180090ae9  push    rbp
0x180090aea  push    rsi
0x180090aeb  push    rdi
0x180090aec  push    r12
0x180090aee  push    r13
0x180090af0  push    r14
0x180090af2  push    r15
0x180090af4  sub     rsp, 30h
0x180090af8  xor     r14d, r14d
0x180090afb  mov     r12d, edx
0x180090afe  mov     r13, rcx
0x180090b01  test    rcx, rcx
0x180090b04  jnz     short loc_180090B58
0x180090b06  lea     r8, aPcertcontexts; "pCertContexts"
0x180090b0d  mov     ebp, 80070057h
0x180090b12  lea     rdx, aSortcertificat; "SortCertificatesInPlace"
0x180090b19  lea     rcx, aSSShouldNotBeN_0; "%s: \"%s\" should not be null."
0x180090b20  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180090b25  lea     rdx, aPcertcontexts; "pCertContexts"
0x180090b2c  lea     rcx, aSortcertificat; "SortCertificatesInPlace"
0x180090b33  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x180090b38  mov     rcx, r14; Block
0x180090b3b  call    cs:__imp_free
0x180090b41  mov     rbx, [rsp+68h+arg_8]
0x180090b46  mov     eax, ebp
0x180090b48  add     rsp, 30h
0x180090b4c  pop     r15
0x180090b4e  pop     r14
0x180090b50  pop     r13
0x180090b52  pop     r12
0x180090b54  pop     rdi
0x180090b55  pop     rsi
0x180090b56  pop     rbp
0x180090b57  retn
0x180090b58  xor     ebp, ebp
0x180090b5a  cmp     r12d, 1
0x180090b5e  jz      loc_180090D14
0x180090b64  lea     rcx, [rbp-1]
0x180090b68  lea     eax, [rbp+8]
0x180090b6b  mul     r12
0x180090b6e  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180090b75  cmovb   rax, rcx
0x180090b79  mov     rcx, rax; unsigned __int64
0x180090b7c  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180090b81  mov     r14, rax
0x180090b84  test    rax, rax
0x180090b87  jnz     short loc_180090BA3
0x180090b89  lea     rdx, aSortcertificat; "SortCertificatesInPlace"
0x180090b90  mov     ebp, 8007000Eh
0x180090b95  lea     rcx, aSOutOfMemoryAl_0; "%s: Out of memory. Allocation failed."
0x180090b9c  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180090ba1  jmp     short loc_180090B38
0x180090ba3  lea     r8, ds:0[r12*8]; Size
0x180090bab  xor     edx, edx; Val
0x180090bad  mov     rcx, r14; void *
0x180090bb0  call    memset_0
0x180090bb5  xor     ebx, ebx
0x180090bb7  cmp     ebx, r12d
0x180090bba  jnb     short loc_180090BFE
0x180090bbc  mov     rcx, [r13+rbx*8+0]; struct _CERT_CONTEXT *
0x180090bc1  lea     rdx, [r14+rbx*8]; unsigned __int16 **
0x180090bc5  xor     r8d, r8d; int *
0x180090bc8  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x180090bcd  mov     ebp, eax
0x180090bcf  test    eax, eax
0x180090bd1  js      short loc_180090BD7
0x180090bd3  inc     ebx
0x180090bd5  jmp     short loc_180090BB7
0x180090bd7  lea     r8, aRegistrationce_7; "RegistrationCertStatus::GetTenantId"
0x180090bde  mov     r9d, eax
0x180090be1  lea     rdx, aSortcertificat; "SortCertificatesInPlace"
0x180090be8  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x180090bef  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180090bf4  xor     edi, edi
0x180090bf6  mov     rsi, r14
0x180090bf9  jmp     loc_180090D22
0x180090bfe  mov     r15d, 1
0x180090c04  cmp     r15d, r12d
0x180090c07  jge     loc_180090D14
0x180090c0d  movsxd  rax, r15d
0x180090c10  lea     ebx, [r15-1]
0x180090c14  mov     rsi, [r13+rax*8+0]
0x180090c19  mov     rax, [r14+rax*8]
0x180090c1d  mov     [rsp+68h+arg_10], rax
0x180090c25  mov     [rsp+68h+arg_18], rsi
0x180090c2d  lea     rcx, [rsp+68h+arg_0]
0x180090c32  movsxd  rdi, ebx
0x180090c35  mov     [rsp+68h+var_40], rcx; enum COMPARE_STR_RESULT *
0x180090c3a  mov     r8, rax; unsigned __int16 *
0x180090c3d  mov     [rsp+68h+arg_0], 0
0x180090c45  mov     [rsp+68h+var_48], 1; unsigned int
0x180090c4d  mov     rcx, [r14+rdi*8]; lpString1
0x180090c51  call    ?CompareStringInternal@@YAJPEBGH0HKPEAW4COMPARE_STR_RESULT@@@Z; CompareStringInternal(ushort const *,int,ushort const *,int,ulong,COMPARE_STR_RESULT *)
0x180090c56  mov     ebp, eax
0x180090c58  test    eax, eax
0x180090c5a  js      loc_180090D08
0x180090c60  cmp     [rsp+68h+arg_0], 1
0x180090c65  jz      short loc_180090C9A
0x180090c67  cmp     [rsp+68h+arg_0], 2
0x180090c6c  jnz     short loc_180090C8D
0x180090c6e  mov     rax, [r13+rdi*8+0]
0x180090c73  mov     rdx, [rsi+18h]
0x180090c77  add     rdx, 40h ; '@'; lpFileTime2
0x180090c7b  mov     rcx, [rax+18h]
0x180090c7f  add     rcx, 40h ; '@'; lpFileTime1
0x180090c83  call    cs:__imp_CompareFileTime
0x180090c89  test    eax, eax
0x180090c8b  jle     short loc_180090C9A
0x180090c8d  sub     ebx, 1
0x180090c90  mov     rax, [rsp+68h+arg_10]
0x180090c98  jns     short loc_180090C2D
0x180090c9a  lea     ecx, [rbx+1]
0x180090c9d  cmp     ecx, r15d
0x180090ca0  jz      short loc_180090D00
0x180090ca2  mov     eax, r15d
0x180090ca5  movsxd  rsi, ebx
0x180090ca8  sub     eax, ecx
0x180090caa  lea     rdx, [r13+8]
0x180090cae  movsxd  rdi, eax
0x180090cb1  lea     eax, [rcx+1]
0x180090cb4  movsxd  rbx, eax
0x180090cb7  shl     rdi, 3
0x180090cbb  lea     rdx, [rdx+rsi*8]; Src
0x180090cbf  mov     r8, rdi; Size
0x180090cc2  lea     rcx, ds:0[rbx*8]
0x180090cca  add     rcx, r13; void *
0x180090ccd  call    memmove_0
0x180090cd2  lea     rdx, [r14+8]
0x180090cd6  mov     r8, rdi; Size
0x180090cd9  lea     rdx, [rdx+rsi*8]; Src
0x180090cdd  lea     rcx, [r14+rbx*8]; void *
0x180090ce1  call    memmove_0
0x180090ce6  mov     rax, [rsp+68h+arg_18]
0x180090cee  mov     [r13+rsi*8+8], rax
0x180090cf3  mov     rax, [rsp+68h+arg_10]
0x180090cfb  mov     [r14+rsi*8+8], rax
0x180090d00  inc     r15d
0x180090d03  jmp     loc_180090C04
0x180090d08  lea     r8, aStringcompare; "StringCompare"
0x180090d0f  jmp     loc_180090BDE
0x180090d14  xor     edi, edi
0x180090d16  mov     rsi, r14
0x180090d19  test    r14, r14
0x180090d1c  jz      loc_180090B38
0x180090d22  cmp     edi, r12d
0x180090d25  jnb     loc_180090B38
0x180090d2b  mov     rcx, [rsi+rdi*8]; Block
0x180090d2f  call    cs:__imp_free
0x180090d35  mov     qword ptr [rsi+rdi*8], 0
0x180090d3d  inc     edi
0x180090d3f  jmp     short loc_180090D22
```
