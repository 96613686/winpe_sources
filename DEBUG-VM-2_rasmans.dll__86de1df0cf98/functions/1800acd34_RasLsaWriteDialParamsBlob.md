# RasLsaWriteDialParamsBlob

- ea: `0x1800acd34`
- end: `0x1800acf4a`
- name: `RasLsaWriteDialParamsBlob`
- size: `534`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800acf50`
- `0x1800ad418`

## callees

- `0x1800abbc0`
- `0x1800ac98c`
- `0x1800acd34`

## import_xrefs

- `ntdll!RtlNtStatusToDosError` at `0x1800ace15`
- `ntdll!RtlNtStatusToDosError` at `0x1800acf40`
- `ntdll!RtlNtStatusToDosError` at `0x1800ace15`
- `ntdll!RtlNtStatusToDosError` at `0x1800acf40`
- `ntdll!RtlInitUnicodeString` at `0x1800ace67`
- `ntdll!RtlInitUnicodeString` at `0x1800acedc`
- `ntdll!RtlInitUnicodeString` at `0x1800ace67`
- `ntdll!RtlInitUnicodeString` at `0x1800acedc`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acdb5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800acdb5`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800acda7`
- `api-ms-win-core-heap-l2-1-0!LocalAlloc` at `0x1800acda7`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ace0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acf11`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800ace0d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x1800acf11`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800acdea`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaOpenPolicy` at `0x1800acdea`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800ace96`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800aceed`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800ace96`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaStorePrivateData` at `0x1800aceed`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800acf1b`
- `api-ms-win-security-lsapolicy-l1-1-0!LsaClose` at `0x1800acf1b`

## pseudocode

```c
ULONG __fastcall RasLsaWriteDialParamsBlob(__int64 a1, __int64 a2, WCHAR *a3, unsigned int a4, int a5)
{
  __int64 v5; // rax
  unsigned int v9; // r12d
  SIZE_T v10; // rbx
  _BYTE *v11; // rdi
  NTSTATUS v13; // esi
  _BYTE *i; // rcx
  unsigned int v15; // esi
  unsigned int v16; // r12d
  NTSTATUS v17; // eax
  __int64 v18; // r9
  ULONG v19; // esi
  _BYTE *j; // rax
  PVOID PolicyHandle; // [rsp+30h] [rbp-41h] BYREF
  struct _LSA_UNICODE_STRING PrivateData; // [rsp+38h] [rbp-39h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-29h] BYREF
  struct _LSA_OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-19h] BYREF
  unsigned int v25; // [rsp+D0h] [rbp+5Fh]

  LODWORD(v5) = 0;
  PolicyHandle = 0;
  DestinationString = 0;
  PrivateData = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( a1 )
  {
    v5 = -1;
    do
      ++v5;
    while ( *(_WORD *)(a1 + 2 * v5) );
  }
  v9 = v5 + 64;
  v10 = 2LL * (unsigned int)(v5 + 64);
  v25 = v5 + 64;
  v11 = LocalAlloc(0x40u, v10);
  if ( !v11 )
    return GetLastError();
  ObjectAttributes.Length = 48;
  memset(&ObjectAttributes.RootDirectory, 0, 20);
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v13 = LsaOpenPolicy(0, &ObjectAttributes, 0x207F8u, &PolicyHandle);
  if ( v13 )
  {
    for ( i = v11; v10; --v10 )
      *i++ = 0;
    LocalFree(v11);
    return RtlNtStatusToDosError(v13);
  }
  else
  {
    v15 = 0;
    if ( a3 && !(unsigned int)RasLsaIsPasswordSavingDisabled() && a4 )
    {
      while ( !(unsigned int)FormatKey(v11, v9, a1, v15, a5) )
      {
        RtlInitUnicodeString(&DestinationString, (PCWSTR)v11);
        PrivateData.Buffer = a3;
        v16 = a4;
        if ( a4 > 0xFFFF )
          v16 = 0xFFFF;
        PrivateData.MaximumLength = v16;
        PrivateData.Length = v16;
        v17 = LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, &PrivateData);
        if ( v17 )
        {
          v19 = RtlNtStatusToDosError(v17);
          goto LABEL_21;
        }
        ++v15;
        a3 = (WCHAR *)((char *)a3 + v16);
        a4 -= v16;
        v9 = v25;
        if ( !a4 )
          goto LABEL_18;
      }
    }
    else
    {
      do
      {
LABEL_18:
        v18 = v15++;
        if ( (unsigned int)FormatKey(v11, v9, a1, v18, a5) )
          break;
        RtlInitUnicodeString(&DestinationString, (PCWSTR)v11);
      }
      while ( !LsaStorePrivateData(PolicyHandle, (PLSA_UNICODE_STRING)&DestinationString, 0) );
    }
    v19 = 0;
LABEL_21:
    for ( j = v11; v10; --v10 )
      *j++ = 0;
    LocalFree(v11);
    LsaClose(PolicyHandle);
    return v19;
  }
}

```

## disassembly

```asm
0x1800acd34  mov     [rsp-8+arg_10], rbx
0x1800acd39  mov     [rsp-8+arg_8], edx
0x1800acd3d  push    rbp
0x1800acd3e  push    rsi
0x1800acd3f  push    rdi
0x1800acd40  push    r12
0x1800acd42  push    r13
0x1800acd44  push    r14
0x1800acd46  push    r15
0x1800acd48  lea     rbp, [rsp-1Fh]
0x1800acd4d  sub     rsp, 90h
0x1800acd54  xorps   xmm0, xmm0
0x1800acd57  xor     esi, esi
0x1800acd59  xor     eax, eax
0x1800acd5b  mov     [rbp+4Fh+PolicyHandle], rsi
0x1800acd5f  xorps   xmm1, xmm1
0x1800acd62  mov     r15d, r9d
0x1800acd65  mov     r13, r8
0x1800acd68  mov     r14, rcx
0x1800acd6b  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.ObjectName], xmm0
0x1800acd6f  movups  xmmword ptr [rbp+4Fh+ObjectAttributes+1Ch], xmm0
0x1800acd73  movups  xmmword ptr [rbp+4Fh+DestinationString.Length], xmm0
0x1800acd77  movups  xmmword ptr [rbp+4Fh+PrivateData.Length], xmm1
0x1800acd7b  movups  xmmword ptr [rbp+4Fh+ObjectAttributes.Length], xmm0
0x1800acd7f  test    rcx, rcx
0x1800acd82  jz      short loc_1800ACD91
0x1800acd84  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800acd88  inc     rax
0x1800acd8b  cmp     [rcx+rax*2], si
0x1800acd8f  jnz     short loc_1800ACD88
0x1800acd91  lea     r12d, [rax+40h]
0x1800acd95  mov     ecx, 40h ; '@'; uFlags
0x1800acd9a  mov     ebx, r12d
0x1800acd9d  add     rbx, rbx
0x1800acda0  mov     [rbp+4Fh+arg_0], r12d
0x1800acda4  mov     rdx, rbx; uBytes
0x1800acda7  call    cs:__imp_LocalAlloc
0x1800acdad  mov     rdi, rax
0x1800acdb0  test    rax, rax
0x1800acdb3  jnz     short loc_1800ACDC0
0x1800acdb5  call    cs:__imp_GetLastError
0x1800acdbb  jmp     loc_1800ACF23
0x1800acdc0  xorps   xmm0, xmm0
0x1800acdc3  mov     [rbp+4Fh+ObjectAttributes.Length], 30h ; '0'
0x1800acdca  lea     r9, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800acdce  mov     [rbp+4Fh+ObjectAttributes.RootDirectory], rsi
0x1800acdd2  mov     r8d, 207F8h; DesiredAccess
0x1800acdd8  mov     [rbp+4Fh+ObjectAttributes.Attributes], esi
0x1800acddb  lea     rdx, [rbp+4Fh+ObjectAttributes]; ObjectAttributes
0x1800acddf  mov     [rbp+4Fh+ObjectAttributes.ObjectName], rsi
0x1800acde3  xor     ecx, ecx; SystemName
0x1800acde5  movdqu  xmmword ptr [rbp+4Fh+ObjectAttributes.SecurityDescriptor], xmm0
0x1800acdea  call    cs:__imp_LsaOpenPolicy
0x1800acdf0  mov     esi, eax
0x1800acdf2  test    eax, eax
0x1800acdf4  jz      short loc_1800ACE20
0x1800acdf6  mov     rcx, rdi
0x1800acdf9  test    rbx, rbx
0x1800acdfc  jz      short loc_1800ACE0A
0x1800acdfe  mov     byte ptr [rcx], 0
0x1800ace01  inc     rcx
0x1800ace04  sub     rbx, 1
0x1800ace08  jnz     short loc_1800ACDFE
0x1800ace0a  mov     rcx, rdi; hMem
0x1800ace0d  call    cs:__imp_LocalFree
0x1800ace13  mov     ecx, esi; Status
0x1800ace15  call    cs:__imp_RtlNtStatusToDosError
0x1800ace1b  jmp     loc_1800ACF23
0x1800ace20  xor     esi, esi
0x1800ace22  mov     [rbp+4Fh+arg_8], 0
0x1800ace29  test    r13, r13
0x1800ace2c  jz      loc_1800ACEB5
0x1800ace32  call    RasLsaIsPasswordSavingDisabled
0x1800ace37  test    eax, eax
0x1800ace39  jnz     short loc_1800ACEB5
0x1800ace3b  test    r15d, r15d
0x1800ace3e  jz      short loc_1800ACEB5
0x1800ace40  mov     eax, [rbp+4Fh+arg_20]
0x1800ace43  mov     r9d, esi
0x1800ace46  mov     r8, r14
0x1800ace49  mov     [rsp+0C0h+var_A0], eax
0x1800ace4d  mov     edx, r12d
0x1800ace50  mov     rcx, rdi
0x1800ace53  call    FormatKey
0x1800ace58  test    eax, eax
0x1800ace5a  jnz     loc_1800ACEF7
0x1800ace60  mov     rdx, rdi; SourceString
0x1800ace63  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800ace67  call    cs:__imp_RtlInitUnicodeString
0x1800ace6d  mov     rcx, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800ace71  lea     r8, [rbp+4Fh+PrivateData]; PrivateData
0x1800ace75  mov     eax, 0FFFFh
0x1800ace7a  mov     [rbp+4Fh+PrivateData.Buffer], r13
0x1800ace7e  cmp     r15d, eax
0x1800ace81  lea     rdx, [rbp+4Fh+DestinationString]; KeyName
0x1800ace85  mov     r12d, r15d
0x1800ace88  cmova   r12d, eax
0x1800ace8c  mov     [rbp+4Fh+PrivateData.MaximumLength], r12w
0x1800ace91  mov     [rbp+4Fh+PrivateData.Length], r12w
0x1800ace96  call    cs:__imp_LsaStorePrivateData
0x1800ace9c  test    eax, eax
0x1800ace9e  jnz     loc_1800ACF3E
0x1800acea4  mov     eax, r12d
0x1800acea7  inc     esi
0x1800acea9  add     r13, rax
0x1800aceac  sub     r15d, r12d
0x1800aceaf  mov     r12d, [rbp+4Fh+arg_0]
0x1800aceb3  jnz     short loc_1800ACE40
0x1800aceb5  mov     r15d, [rbp+4Fh+arg_20]
0x1800aceb9  mov     r9d, esi
0x1800acebc  mov     [rsp+0C0h+var_A0], r15d
0x1800acec1  mov     r8, r14
0x1800acec4  mov     edx, r12d
0x1800acec7  mov     rcx, rdi
0x1800aceca  inc     esi
0x1800acecc  call    FormatKey
0x1800aced1  test    eax, eax
0x1800aced3  jnz     short loc_1800ACEF7
0x1800aced5  mov     rdx, rdi; SourceString
0x1800aced8  lea     rcx, [rbp+4Fh+DestinationString]; DestinationString
0x1800acedc  call    cs:__imp_RtlInitUnicodeString
0x1800acee2  mov     rcx, [rbp+4Fh+PolicyHandle]; PolicyHandle
0x1800acee6  lea     rdx, [rbp+4Fh+DestinationString]; KeyName
0x1800aceea  xor     r8d, r8d; PrivateData
0x1800aceed  call    cs:__imp_LsaStorePrivateData
0x1800acef3  test    eax, eax
0x1800acef5  jz      short loc_1800ACEB9
0x1800acef7  mov     esi, [rbp+4Fh+arg_8]
0x1800acefa  mov     rax, rdi
0x1800acefd  test    rbx, rbx
0x1800acf00  jz      short loc_1800ACF0E
0x1800acf02  mov     byte ptr [rax], 0
0x1800acf05  inc     rax
0x1800acf08  sub     rbx, 1
0x1800acf0c  jnz     short loc_1800ACF02
0x1800acf0e  mov     rcx, rdi; hMem
0x1800acf11  call    cs:__imp_LocalFree
0x1800acf17  mov     rcx, [rbp+4Fh+PolicyHandle]; ObjectHandle
0x1800acf1b  call    cs:__imp_LsaClose
0x1800acf21  mov     eax, esi
0x1800acf23  mov     rbx, [rsp+0C0h+arg_10]
0x1800acf2b  add     rsp, 90h
0x1800acf32  pop     r15
0x1800acf34  pop     r14
0x1800acf36  pop     r13
0x1800acf38  pop     r12
0x1800acf3a  pop     rdi
0x1800acf3b  pop     rsi
0x1800acf3c  pop     rbp
0x1800acf3d  retn
0x1800acf3e  mov     ecx, eax; Status
0x1800acf40  call    cs:__imp_RtlNtStatusToDosError
0x1800acf46  mov     esi, eax
0x1800acf48  jmp     short loc_1800ACEFA
```
