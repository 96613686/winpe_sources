# RasLsaReadDialParamsBlob

- ea: `0x1800aca40`
- end: `0x1800accca`
- name: `RasLsaReadDialParamsBlob`
- size: `650`
- prototype: ``
- caller_count: `4`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800ac034`
- `0x1800ac1b0`
- `0x1800acf50`
- `0x1800ad418`

## callees

- `0x1800abbc0`
- `0x1800aca40`
- `0x1800e71ee`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800acab7`
- `ntdll!RtlNtStatusToDosError` at `0x1800acc36`
- `ntdll!RtlNtStatusToDosError` at `0x1800acab7`
- `ntdll!RtlNtStatusToDosError` at `0x1800acc36`
- `ntdll!RtlInitUnicodeString` at `0x1800acb42`
- `ntdll!RtlInitUnicodeString` at `0x1800acb42`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acb06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acc1f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acb06`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acc1f`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800acaee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800acb81`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800acaee`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800acb81`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acbc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acc5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acc9a`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acbc0`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acc5f`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acc9a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800acbf1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800acc70`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800acbf1`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaFreeMemory` at `0x1800acc70`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800acaab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800acaab`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800acb54`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaRetrievePrivateData` at `0x1800acb54`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800acb00`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800acc7a`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800acb00`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800acc7a`

## pseudocode

```c
ULONG __fastcall RasLsaReadDialParamsBlob(__int64 a1, __int64 a2, char **a3, unsigned int *a4, int a5)
{
  char *v5; // rbx
  NTSTATUS v7; // eax
  __int64 v9; // rax
  unsigned int v10; // r15d
  WCHAR *v11; // r14
  int v12; // edi
  unsigned int v13; // esi
  unsigned int v14; // r12d
  NTSTATUS v15; // eax
  unsigned int v16; // ecx
  char *v17; // rax
  __int64 v18; // r15
  char *v19; // rcx
  DWORD LastError; // eax
  __int64 v21; // rax
  char *v22; // rcx
  WCHAR *v23; // rcx
  __int64 i; // rax
  PLSA_UNICODE_STRING PrivateData; // [rsp+38h] [rbp-41h] BYREF
  PVOID PolicyHandle; // [rsp+40h] [rbp-39h] BYREF
  char *v27; // [rsp+48h] [rbp-31h]
  struct _UNICODE_STRING DestinationString; // [rsp+50h] [rbp-29h] BYREF
  _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+60h] [rbp-19h] BYREF
  unsigned int v30; // [rsp+E0h] [rbp+67h]

  v5 = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *a3 = 0;
  *a4 = 0;
  PrivateData = 0;
  PolicyHandle = 0;
  memset(&ObjectAttributes.RootDirectory, 0, 40);
  DestinationString = 0;
  v7 = LsaOpenPolicy(0, &ObjectAttributes, 0x20006u, &PolicyHandle);
  if ( v7 )
    return RtlNtStatusToDosError(v7);
  if ( a1 )
  {
    v9 = -1;
    do
      ++v9;
    while ( *(_WORD *)(a1 + 2 * v9) );
  }
  else
  {
    LODWORD(v9) = 0;
  }
  v10 = v9 + 64;
  v30 = v9 + 64;
  v11 = (WCHAR *)LocalAlloc(0x40u, 2LL * (unsigned int)(v9 + 64));
  if ( v11 )
  {
    v12 = 0;
    v13 = 0;
    v14 = 1;
    if ( !(unsigned int)FormatKey(v11, v10, a1, 0, a5) )
    {
      while ( 1 )
      {
        RtlInitUnicodeString(&DestinationString, v11);
        v15 = LsaRetrievePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, &PrivateData);
        if ( v15 )
          break;
        if ( !PrivateData )
          goto LABEL_32;
        v16 = v13 + PrivateData->Length;
        if ( v16 < v13 )
        {
          v12 = 534;
          goto LABEL_26;
        }
        v17 = (char *)LocalAlloc(0x40u, v16);
        v27 = v17;
        if ( !v17 )
        {
          LastError = GetLastError();
          goto LABEL_25;
        }
        if ( v5 )
        {
          v18 = v13;
          memcpy_0(v17, v5, v13);
          v19 = v5;
          if ( v13 )
          {
            do
            {
              *v19++ = 0;
              --v18;
            }
            while ( v18 );
          }
          LocalFree(v5);
          v17 = v27;
          v10 = v30;
        }
        memcpy_0(&v17[v13], PrivateData->Buffer, PrivateData->Length);
        v5 = v27;
        v13 += PrivateData->Length;
        LsaFreeMemory(PrivateData);
        PrivateData = 0;
        if ( (unsigned int)FormatKey(v11, v10, a1, v14, a5) )
          goto LABEL_30;
        ++v14;
      }
      if ( v14 > 1 )
        goto LABEL_30;
      LastError = RtlNtStatusToDosError(v15);
LABEL_25:
      v12 = LastError;
      if ( !LastError )
        goto LABEL_30;
LABEL_26:
      if ( v5 )
      {
        v21 = v13;
        v22 = v5;
        if ( v13 )
        {
          do
          {
            *v22++ = 0;
            --v21;
          }
          while ( v21 );
        }
        LocalFree(v5);
        v5 = 0;
      }
    }
LABEL_30:
    if ( PrivateData )
      LsaFreeMemory(PrivateData);
LABEL_32:
    LsaClose(PolicyHandle);
    v23 = v11;
    for ( i = 2LL * v10; i; --i )
    {
      *(_BYTE *)v23 = 0;
      v23 = (WCHAR *)((char *)v23 + 1);
    }
    LocalFree(v11);
    *a3 = v5;
    *a4 = v13;
    return v12;
  }
  else
  {
    LsaClose(PolicyHandle);
    return GetLastError();
  }
}

```

## disassembly

```asm
0x1800aca40  mov     rax, rsp
0x1800aca43  mov     [rax+8], rbx
0x1800aca47  mov     [rax+20h], r9
0x1800aca4b  mov     [rax+18h], r8
0x1800aca4f  mov     [rax+10h], edx
0x1800aca52  push    rbp
0x1800aca53  push    rsi
0x1800aca54  push    rdi
0x1800aca55  push    r12
0x1800aca57  push    r13
0x1800aca59  push    r14
0x1800aca5b  push    r15
0x1800aca5d  lea     rbp, [rax-57h]
0x1800aca61  sub     rsp, 90h
0x1800aca68  xor     ebx, ebx
0x1800aca6a  mov     qword ptr [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800aca72  xorps   xmm0, xmm0
0x1800aca75  mov     [r8], rbx
0x1800aca78  mov     [r9], ebx
0x1800aca7b  lea     rdx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800aca7f  mov     r13, rcx
0x1800aca82  mov     [rbp+4Fh+PrivateData], rbx
0x1800aca86  lea     r9, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800aca8a  mov     qword ptr [rbp+4Fh+ObjectAttributes.Attributes], rbx
0x1800aca8e  mov     r8d, 20006h; DesiredAccess
0x1800aca94  mov     [rbp+4Fh+PolicyHandle], rbx
0x1800aca98  xor     ecx, ecx; SystemName
0x1800aca9a  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rbx
0x1800aca9e  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800acaa2  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rbx
0x1800acaa6  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800acaab  call    cs:__imp_LsaOpenPolicy
0x1800acab1  test    eax, eax
0x1800acab3  jz      short loc_1800ACAC2
0x1800acab5  mov     ecx, eax; Status
0x1800acab7  call    cs:__imp_RtlNtStatusToDosError
0x1800acabd  jmp     loc_1800ACCAF
0x1800acac2  test    r13, r13
0x1800acac5  jz      short loc_1800ACAD8
0x1800acac7  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800acacb  inc     rax
0x1800acace  cmp     [r13+rax*2+0], bx
0x1800acad4  jnz     short loc_1800ACACB
0x1800acad6  jmp     short loc_1800ACADB
0x1800acad8  mov     rax, rbx
0x1800acadb  lea     r15d, [rax+40h]
0x1800acadf  mov     ecx, 40h ; '@'; uFlags
0x1800acae4  mov     edx, r15d
0x1800acae7  add     rdx, rdx; uBytes
0x1800acaea  mov     [rbp+4Fh+arg_8], r15d
0x1800acaee  call    cs:__imp_LocalAlloc
0x1800acaf4  mov     r14, rax
0x1800acaf7  test    rax, rax
0x1800acafa  jnz     short loc_1800ACB11
0x1800acafc  mov     rcx, [rbp+4Fh+PolicyHandle]; ObjectHandle
0x1800acb00  call    cs:__imp_LsaClose
0x1800acb06  call    cs:__imp_GetLastError
0x1800acb0c  jmp     loc_1800ACCAF
0x1800acb11  mov     eax, [rbp+4Fh+arg_20]
0x1800acb14  xor     r9d, r9d
0x1800acb17  mov     r8, r13
0x1800acb1a  mov     [rsp+20h], eax
0x1800acb1e  mov     edx, r15d
0x1800acb21  mov     rcx, r14
0x1800acb24  mov     edi, ebx
0x1800acb26  mov     esi, ebx
0x1800acb28  mov     r12d, 1
0x1800acb2e  call    FormatKey
0x1800acb33  test    eax, eax
0x1800acb35  jnz     loc_1800ACC67
0x1800acb3b  mov     rdx, r14; SourceString
0x1800acb3e  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800acb42  call    cs:__imp_RtlInitUnicodeString
0x1800acb48  mov     rcx, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800acb4c  lea     r8, [rbp+4Fh+PrivateData]; PrivateData
0x1800acb50  lea     rdx, [rbp+4Fh+DestinationString]; KeyName
0x1800acb54  call    cs:__imp_LsaRetrievePrivateData
0x1800acb5a  test    eax, eax
0x1800acb5c  jnz     loc_1800ACC2E
0x1800acb62  mov     rcx, [rbp+4Fh+PrivateData]
0x1800acb66  test    rcx, rcx
0x1800acb69  jz      loc_1800ACC76
0x1800acb6f  movzx   ecx, word ptr [rcx]
0x1800acb72  add     ecx, esi
0x1800acb74  cmp     ecx, esi
0x1800acb76  jb      loc_1800ACC27
0x1800acb7c  mov     edx, ecx; uBytes
0x1800acb7e  lea     ecx, [rax+40h]; uFlags
0x1800acb81  call    cs:__imp_LocalAlloc
0x1800acb87  mov     [rbp+4Fh+var_80], rax
0x1800acb8b  test    rax, rax
0x1800acb8e  jz      loc_1800ACC1F
0x1800acb94  test    rbx, rbx
0x1800acb97  jz      short loc_1800ACBCE
0x1800acb99  mov     r8d, esi; Size
0x1800acb9c  mov     rdx, rbx; Src
0x1800acb9f  mov     rcx, rax; void *
0x1800acba2  mov     r15d, esi
0x1800acba5  call    memcpy_0
0x1800acbaa  mov     rcx, rbx
0x1800acbad  test    esi, esi
0x1800acbaf  jz      short loc_1800ACBBD
0x1800acbb1  mov     [rcx], dil
0x1800acbb4  inc     rcx
0x1800acbb7  sub     r15, 1
0x1800acbbb  jnz     short loc_1800ACBB1
0x1800acbbd  mov     rcx, rbx; hMem
0x1800acbc0  call    cs:__imp_LocalFree
0x1800acbc6  mov     rax, [rbp+4Fh+var_80]
0x1800acbca  mov     r15d, [rbp+4Fh+arg_8]
0x1800acbce  mov     rdx, [rbp+4Fh+PrivateData]
0x1800acbd2  mov     ecx, esi
0x1800acbd4  add     rcx, rax; void *
0x1800acbd7  movzx   r8d, word ptr [rdx]; Size
0x1800acbdb  mov     rdx, [rdx+8]; Src
0x1800acbdf  call    memcpy_0
0x1800acbe4  mov     rcx, [rbp+4Fh+PrivateData]; Buffer
0x1800acbe8  mov     rbx, [rbp+4Fh+var_80]
0x1800acbec  movzx   eax, word ptr [rcx]
0x1800acbef  add     esi, eax
0x1800acbf1  call    cs:__imp_LsaFreeMemory
0x1800acbf7  mov     eax, [rbp+4Fh+arg_20]
0x1800acbfa  mov     r9d, r12d
0x1800acbfd  mov     r8, r13
0x1800acc00  mov     [rsp+20h], eax
0x1800acc04  mov     edx, r15d
0x1800acc07  mov     [rbp+4Fh+PrivateData], rdi
0x1800acc0b  mov     rcx, r14
0x1800acc0e  call    FormatKey
0x1800acc13  test    eax, eax
0x1800acc15  jnz     short loc_1800ACC67
0x1800acc17  inc     r12d
0x1800acc1a  jmp     loc_1800ACB3B
0x1800acc1f  call    cs:__imp_GetLastError
0x1800acc25  jmp     short loc_1800ACC3C
0x1800acc27  mov     edi, 216h
0x1800acc2c  jmp     short loc_1800ACC42
0x1800acc2e  cmp     r12d, 1
0x1800acc32  ja      short loc_1800ACC67
0x1800acc34  mov     ecx, eax; Status
0x1800acc36  call    cs:__imp_RtlNtStatusToDosError
0x1800acc3c  mov     edi, eax
0x1800acc3e  test    eax, eax
0x1800acc40  jz      short loc_1800ACC67
0x1800acc42  test    rbx, rbx
0x1800acc45  jz      short loc_1800ACC67
0x1800acc47  mov     eax, esi
0x1800acc49  mov     rcx, rbx
0x1800acc4c  test    esi, esi
0x1800acc4e  jz      short loc_1800ACC5C
0x1800acc50  mov     byte ptr [rcx], 0
0x1800acc53  inc     rcx
0x1800acc56  sub     rax, 1
0x1800acc5a  jnz     short loc_1800ACC50
0x1800acc5c  mov     rcx, rbx; hMem
0x1800acc5f  call    cs:__imp_LocalFree
0x1800acc65  xor     ebx, ebx
0x1800acc67  mov     rcx, [rbp+4Fh+PrivateData]; Buffer
0x1800acc6b  test    rcx, rcx
0x1800acc6e  jz      short loc_1800ACC76
0x1800acc70  call    cs:__imp_LsaFreeMemory
0x1800acc76  mov     rcx, [rbp+4Fh+PolicyHandle]; ObjectHandle
0x1800acc7a  call    cs:__imp_LsaClose
0x1800acc80  mov     eax, r15d
0x1800acc83  mov     rcx, r14
0x1800acc86  add     rax, rax
0x1800acc89  jz      short loc_1800ACC97
0x1800acc8b  mov     byte ptr [rcx], 0
0x1800acc8e  inc     rcx
0x1800acc91  sub     rax, 1
0x1800acc95  jnz     short loc_1800ACC8B
0x1800acc97  mov     rcx, r14; hMem
0x1800acc9a  call    cs:__imp_LocalFree
0x1800acca0  mov     rax, [rbp+4Fh+arg_10]
0x1800acca4  mov     [rax], rbx
0x1800acca7  mov     rax, [rbp+4Fh+arg_18]
0x1800accab  mov     [rax], esi
0x1800accad  mov     eax, edi
0x1800accaf  mov     rbx, [rsp+0C0h+arg_0]
0x1800accb7  add     rsp, 90h
0x1800accbe  pop     r15
0x1800accc0  pop     r14
0x1800accc2  pop     r13
0x1800accc4  pop     r12
0x1800accc6  pop     rdi
0x1800accc7  pop     rsi
0x1800accc8  pop     rbp
0x1800accc9  retn
```
