# SortCertificatesInPlace(_CERT_CONTEXT const * * const,ulong)

- ea: `0x180080874`
- end: `0x180080ac7`
- name: `?SortCertificatesInPlace@@YAJQEAPEBU_CERT_CONTEXT@@K@Z`
- size: `595`
- prototype: `__int64 __fastcall(const struct _CERT_CONTEXT **const, unsigned int)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, broker_com_uri`

## callers

- `0x18008004c`

## callees

- `0x180007db4`
- `0x1800084bc`
- `0x1800084c8`
- `0x180008fdc`
- `0x180079004`
- `0x18007d17c`
- `0x18007d1b8`
- `0x18007d2a4`
- `0x180080754`
- `0x180080874`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180080a0a`
- `api-ms-win-core-file-l1-1-0!CompareFileTime` at `0x180080a0a`

## string_xrefs

- `0x180080a8f`: `StringCompare`

## pseudocode

```c
__int64 __fastcall SortCertificatesInPlace(const struct _CERT_CONTEXT **const a1, unsigned int a2)
{
  unsigned __int16 **v2; // r14
  __int64 v3; // r12
  unsigned int v5; // ebp
  unsigned __int64 v7; // rax
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
  unsigned int v24; // [rsp+20h] [rbp-48h]
  int v25; // [rsp+70h] [rbp+8h] BYREF
  const unsigned __int16 *v26; // [rsp+80h] [rbp+18h]
  const struct _CERT_CONTEXT *v27; // [rsp+88h] [rbp+20h]

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
        v26 = v19;
        v27 = v18;
        do
        {
          v25 = 0;
          TenantId = CompareStringInternal(v2[v17], v9, v19, v10, v24, (enum COMPARE_STR_RESULT *)&v25);
          v5 = TenantId;
          if ( TenantId < 0 )
          {
            v13 = L"StringCompare";
            goto LABEL_14;
          }
          if ( v25 == 1 || v25 == 2 && CompareFileTime(&a1[v17]->pCertInfo->NotBefore, &v18->pCertInfo->NotBefore) <= 0 )
            break;
          --v17;
          v19 = v26;
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
          a1[v21 + 1] = v27;
          v2[v21 + 1] = (unsigned __int16 *)v26;
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
        operator delete(v15[v14]);
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
  operator delete(v2);
  return v5;
}

```

## disassembly

```asm
0x180080874  mov     [rsp+arg_8], rbx
0x180080879  push    rbp
0x18008087a  push    rsi
0x18008087b  push    rdi
0x18008087c  push    r12
0x18008087e  push    r13
0x180080880  push    r14
0x180080882  push    r15
0x180080884  sub     rsp, 30h
0x180080888  xor     r14d, r14d
0x18008088b  mov     r12d, edx
0x18008088e  mov     r13, rcx
0x180080891  test    rcx, rcx
0x180080894  jnz     short loc_1800808E7
0x180080896  lea     r8, aPcertcontexts; "pCertContexts"
0x18008089d  mov     ebp, 80070057h
0x1800808a2  lea     rdx, aSortcertificat; "SortCertificatesInPlace"
0x1800808a9  lea     rcx, aSSShouldNotBeN; "%s: \"%s\" should not be null."
0x1800808b0  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x1800808b5  lea     rdx, aPcertcontexts; "pCertContexts"
0x1800808bc  lea     rcx, aSortcertificat; "SortCertificatesInPlace"
0x1800808c3  call    ?WriteNullOrEmptyParameterFailureEvent@Logger@@SAJPEBG0@Z; Logger::WriteNullOrEmptyParameterFailureEvent(ushort const *,ushort const *)
0x1800808c8  mov     rcx, r14; Block
0x1800808cb  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800808d0  mov     rbx, [rsp+68h+arg_8]
0x1800808d5  mov     eax, ebp
0x1800808d7  add     rsp, 30h
0x1800808db  pop     r15
0x1800808dd  pop     r14
0x1800808df  pop     r13
0x1800808e1  pop     r12
0x1800808e3  pop     rdi
0x1800808e4  pop     rsi
0x1800808e5  pop     rbp
0x1800808e6  retn
0x1800808e7  xor     ebp, ebp
0x1800808e9  cmp     r12d, 1
0x1800808ed  jz      loc_180080A9B
0x1800808f3  lea     rcx, [rbp-1]
0x1800808f7  lea     eax, [rbp+8]
0x1800808fa  mul     r12
0x1800808fd  lea     rdx, ?nothrow@std@@3Unothrow_t@1@B; struct std::nothrow_t *
0x180080904  cmovb   rax, rcx
0x180080908  mov     rcx, rax; unsigned __int64
0x18008090b  call    ??_U@YAPEAX_KAEBUnothrow_t@std@@@Z; operator new[](unsigned __int64,std::nothrow_t const &)
0x180080910  mov     r14, rax
0x180080913  test    rax, rax
0x180080916  jnz     short loc_180080932
0x180080918  lea     rdx, aSortcertificat; "SortCertificatesInPlace"
0x18008091f  mov     ebp, 8007000Eh
0x180080924  lea     rcx, aSOutOfMemoryAl; "%s: Out of memory. Allocation failed."
0x18008092b  call    ?TraceCritical@Logger@@SAJPEBGZZ; Logger::TraceCritical(ushort const *,...)
0x180080930  jmp     short loc_1800808C8
0x180080932  lea     r8, ds:0[r12*8]; Size
0x18008093a  xor     edx, edx; Val
0x18008093c  mov     rcx, r14; void *
0x18008093f  call    memset_0
0x180080944  xor     ebx, ebx
0x180080946  cmp     ebx, r12d
0x180080949  jnb     short loc_18008098D
0x18008094b  mov     rcx, [r13+rbx*8+0]; struct _CERT_CONTEXT *
0x180080950  lea     rdx, [r14+rbx*8]; unsigned __int16 **
0x180080954  xor     r8d, r8d; int *
0x180080957  call    ?GetTenantId@RegistrationCertStatus@@SAJPEBU_CERT_CONTEXT@@PEAPEAGPEAH@Z; RegistrationCertStatus::GetTenantId(_CERT_CONTEXT const *,ushort * *,int *)
0x18008095c  mov     ebp, eax
0x18008095e  test    eax, eax
0x180080960  js      short loc_180080966
0x180080962  inc     ebx
0x180080964  jmp     short loc_180080946
0x180080966  lea     r8, aRegistrationce_3; "RegistrationCertStatus::GetTenantId"
0x18008096d  mov     r9d, eax
0x180080970  lea     rdx, aSortcertificat; "SortCertificatesInPlace"
0x180080977  lea     rcx, aSSFailedWithEr_1; "%s: %s failed with error code: 0x%08x."
0x18008097e  call    ?TraceError@Logger@@SAJPEBGZZ; Logger::TraceError(ushort const *,...)
0x180080983  xor     edi, edi
0x180080985  mov     rsi, r14
0x180080988  jmp     loc_180080AA9
0x18008098d  mov     r15d, 1
0x180080993  cmp     r15d, r12d
0x180080996  jge     loc_180080A9B
0x18008099c  movsxd  rax, r15d
0x18008099f  lea     ebx, [r15-1]
0x1800809a3  mov     rsi, [r13+rax*8+0]
0x1800809a8  mov     rax, [r14+rax*8]
0x1800809ac  mov     [rsp+68h+arg_10], rax
0x1800809b4  mov     [rsp+68h+arg_18], rsi
0x1800809bc  lea     rcx, [rsp+68h+arg_0]
0x1800809c1  movsxd  rdi, ebx
0x1800809c4  mov     [rsp+68h+var_40], rcx; enum COMPARE_STR_RESULT *
0x1800809c9  mov     r8, rax; unsigned __int16 *
0x1800809cc  mov     [rsp+68h+arg_0], 0
0x1800809d4  mov     rcx, [r14+rdi*8]; lpString1
0x1800809d8  call    ?CompareStringInternal@@YAJPEBGH0HKPEAW4COMPARE_STR_RESULT@@@Z; CompareStringInternal(ushort const *,int,ushort const *,int,ulong,COMPARE_STR_RESULT *)
0x1800809dd  mov     ebp, eax
0x1800809df  test    eax, eax
0x1800809e1  js      loc_180080A8F
0x1800809e7  cmp     [rsp+68h+arg_0], 1
0x1800809ec  jz      short loc_180080A21
0x1800809ee  cmp     [rsp+68h+arg_0], 2
0x1800809f3  jnz     short loc_180080A14
0x1800809f5  mov     rax, [r13+rdi*8+0]
0x1800809fa  mov     rdx, [rsi+18h]
0x1800809fe  add     rdx, 40h ; '@'; lpFileTime2
0x180080a02  mov     rcx, [rax+18h]
0x180080a06  add     rcx, 40h ; '@'; lpFileTime1
0x180080a0a  call    cs:__imp_CompareFileTime
0x180080a10  test    eax, eax
0x180080a12  jle     short loc_180080A21
0x180080a14  sub     ebx, 1
0x180080a17  mov     rax, [rsp+68h+arg_10]
0x180080a1f  jns     short loc_1800809BC
0x180080a21  lea     ecx, [rbx+1]
0x180080a24  cmp     ecx, r15d
0x180080a27  jz      short loc_180080A87
0x180080a29  mov     eax, r15d
0x180080a2c  movsxd  rsi, ebx
0x180080a2f  sub     eax, ecx
0x180080a31  lea     rdx, [r13+8]
0x180080a35  movsxd  rdi, eax
0x180080a38  lea     eax, [rcx+1]
0x180080a3b  movsxd  rbx, eax
0x180080a3e  shl     rdi, 3
0x180080a42  lea     rdx, [rdx+rsi*8]; Src
0x180080a46  mov     r8, rdi; Size
0x180080a49  lea     rcx, ds:0[rbx*8]
0x180080a51  add     rcx, r13; void *
0x180080a54  call    memmove_0
0x180080a59  lea     rdx, [r14+8]
0x180080a5d  mov     r8, rdi; Size
0x180080a60  lea     rdx, [rdx+rsi*8]; Src
0x180080a64  lea     rcx, [r14+rbx*8]; void *
0x180080a68  call    memmove_0
0x180080a6d  mov     rax, [rsp+68h+arg_18]
0x180080a75  mov     [r13+rsi*8+8], rax
0x180080a7a  mov     rax, [rsp+68h+arg_10]
0x180080a82  mov     [r14+rsi*8+8], rax
0x180080a87  inc     r15d
0x180080a8a  jmp     loc_180080993
0x180080a8f  lea     r8, aStringcompare; "StringCompare"
0x180080a96  jmp     loc_18008096D
0x180080a9b  xor     edi, edi
0x180080a9d  mov     rsi, r14
0x180080aa0  test    r14, r14
0x180080aa3  jz      loc_1800808C8
0x180080aa9  cmp     edi, r12d
0x180080aac  jnb     loc_1800808C8
0x180080ab2  mov     rcx, [rsi+rdi*8]; Block
0x180080ab6  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180080abb  mov     qword ptr [rsi+rdi*8], 0
0x180080ac3  inc     edi
0x180080ac5  jmp     short loc_180080AA9
```
