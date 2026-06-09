# LiveConvertIdentityToSid(ushort const *,uchar *,ulong *)

- ea: `0x18000fd0c`
- end: `0x18001003a`
- name: `?LiveConvertIdentityToSid@@YAJPEBGPEAEPEAK@Z`
- size: `814`
- prototype: `__int64 __fastcall(PCWSTR SourceString, PSID Sid, unsigned int *)`
- caller_count: `4`
- callee_count: `5`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18000a4a0`
- `0x180010320`
- `0x180010860`
- `0x180012a4c`

## callees

- `0x180003160`
- `0x180003b14`
- `0x180008440`
- `0x18000baac`
- `0x18000fd0c`

## import_xrefs

- `RPCRT4!UuidFromStringW` at `0x18000fdee`
- `RPCRT4!UuidFromStringW` at `0x18000fdee`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe41`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe55`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe65`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe75`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe88`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe9c`
- `ntdll!RtlSubAuthoritySid` at `0x18000ff87`
- `ntdll!RtlSubAuthoritySid` at `0x18000ff99`
- `ntdll!RtlSubAuthoritySid` at `0x18000ffae`
- `ntdll!RtlSubAuthoritySid` at `0x18000ffc3`
- `ntdll!RtlSubAuthoritySid` at `0x18000ffd8`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe41`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe55`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe65`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe75`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe88`
- `ntdll!RtlSubAuthoritySid` at `0x18000fe9c`
- `ntdll!RtlSubAuthoritySid` at `0x18000ff87`
- `ntdll!RtlSubAuthoritySid` at `0x18000ff99`
- `ntdll!RtlSubAuthoritySid` at `0x18000ffae`
- `ntdll!RtlSubAuthoritySid` at `0x18000ffc3`
- `ntdll!RtlSubAuthoritySid` at `0x18000ffd8`
- `ntdll!RtlInitializeSid` at `0x18000fe36`
- `ntdll!RtlInitializeSid` at `0x18000fe36`
- `ntdll!RtlInitUnicodeString` at `0x18000fedf`
- `ntdll!RtlInitUnicodeString` at `0x18000fedf`
- `ntdll!RtlUpcaseUnicodeString` at `0x18000fef0`
- `ntdll!RtlUpcaseUnicodeString` at `0x18000fef0`
- `ntdll!RtlFreeUnicodeString` at `0x18000ffff`
- `ntdll!RtlFreeUnicodeString` at `0x18000ffff`
- `ntdll!RtlLengthRequiredSid` at `0x18000fdc2`
- `ntdll!RtlLengthRequiredSid` at `0x18000fdc2`
- `bcrypt!BCryptDestroyHash` at `0x18000ff72`
- `bcrypt!BCryptDestroyHash` at `0x18000ff72`
- `bcrypt!BCryptFinishHash` at `0x18000ff5f`
- `bcrypt!BCryptFinishHash` at `0x18000ff5f`
- `bcrypt!BCryptHashData` at `0x18000ff41`
- `bcrypt!BCryptHashData` at `0x18000ff41`
- `bcrypt!BCryptCreateHash` at `0x18000ff1e`
- `bcrypt!BCryptCreateHash` at `0x18000ff1e`

## string_xrefs

- `0x18000fd5f`: `LiveConvertIdentityToSid`
- `0x18000fd79`: `onecoreuap\ds\ext\live\identity\cloudapplugin\utils.cpp`

## pseudocode

```c
__int64 __fastcall LiveConvertIdentityToSid(PCWSTR SourceString, PSID Sid, unsigned int *a3)
{
  __int64 v6; // rdx
  int v7; // r8d
  unsigned int v8; // ecx
  unsigned int v9; // eax
  unsigned int v10; // ebx
  ULONG Data1; // ebx
  ULONG Data2; // edi
  ULONG Data3; // esi
  unsigned int v14; // r14d
  unsigned int v15; // r15d
  __int64 v16; // rax
  const unsigned __int16 *pbSecret; // [rsp+20h] [rbp-79h]
  NTSTATUS v19; // [rsp+40h] [rbp-59h] BYREF
  BCRYPT_HASH_HANDLE phHash; // [rsp+48h] [rbp-51h] BYREF
  UCHAR SubAuthorityCount[4]; // [rsp+50h] [rbp-49h]
  struct _UNICODE_STRING UnicodeString; // [rsp+58h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp-31h] BYREF
  _QWORD v24[4]; // [rsp+78h] [rbp-21h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+98h] [rbp-1h] BYREF
  UCHAR pbOutput[4]; // [rsp+A0h] [rbp+7h] BYREF
  unsigned int v27; // [rsp+A4h] [rbp+Bh]
  unsigned int v28; // [rsp+A8h] [rbp+Fh]
  unsigned int v29; // [rsp+ACh] [rbp+13h]
  unsigned int v30; // [rsp+B0h] [rbp+17h]

  *(_WORD *)&IdentifierAuthority.Value[4] = 2816;
  v19 = 0;
  *(_DWORD *)IdentifierAuthority.Value = 0;
  phHash = 0;
  v24[2] = 0;
  v24[3] = 0;
  v24[0] = "LiveConvertIdentityToSid";
  v24[1] = &v19;
  DestinationString = 0;
  UnicodeString = 0;
  MsaTracingInternal::TraceFunctionEnter(
    (MsaTracingInternal *)"onecoreuap\\ds\\ext\\live\\identity\\cloudapplugin\\utils.cpp",
    "LiveConvertIdentityToSid",
    (const char *)0x67,
    0,
    pbSecret);
  if ( !a3 )
    goto LABEL_24;
  if ( !Sid
    || (memset_0(Sid, 0, *a3),
        *(_DWORD *)SubAuthorityCount = (unsigned __int8)(SourceString != 0 ? 11 : 6),
        v8 = (unsigned __int16)RtlLengthRequiredSid(*(ULONG *)SubAuthorityCount),
        v9 = *a3,
        *a3 = v8,
        v9 < v8) )
  {
    v10 = -1073741789;
    goto LABEL_25;
  }
  if ( byte_18004DB1C )
  {
LABEL_8:
    Data1 = Uuid.Data1;
    Data2 = Uuid.Data2;
    Data3 = Uuid.Data3;
    v14 = *(_DWORD *)Uuid.Data4;
    v15 = *(_DWORD *)&Uuid.Data4[4];
    RtlInitializeSid(Sid, &IdentifierAuthority, SubAuthorityCount[0]);
    *RtlSubAuthoritySid(Sid, 0) = 96;
    *RtlSubAuthoritySid(Sid, 1u) = Data1;
    *RtlSubAuthoritySid(Sid, 2u) = Data2;
    *RtlSubAuthoritySid(Sid, 3u) = Data3;
    *RtlSubAuthoritySid(Sid, 4u) = _byteswap_ulong(v14);
    *RtlSubAuthoritySid(Sid, 5u) = _byteswap_ulong(v15);
    if ( !SourceString )
      goto LABEL_22;
    v16 = -1;
    do
      ++v16;
    while ( SourceString[v16] );
    if ( (_DWORD)v16 )
    {
      if ( (unsigned int)v16 > 0x7FFF )
      {
        v10 = -2147483643;
        goto LABEL_25;
      }
      RtlInitUnicodeString(&DestinationString, SourceString);
      v19 = RtlUpcaseUnicodeString(&UnicodeString, &DestinationString, 1u);
      v10 = v19;
      if ( v19 < 0 )
        goto LABEL_26;
      if ( BCryptCreateHash((BCRYPT_ALG_HANDLE)0x31, &phHash, 0, 0, 0, 0, 0) < 0 )
        __fastfail(7u);
      if ( BCryptHashData(phHash, (PUCHAR)UnicodeString.Buffer, UnicodeString.Length, 0) < 0 )
        __fastfail(7u);
      if ( BCryptFinishHash(phHash, pbOutput, 0x14u, 0) < 0 )
        __fastfail(7u);
      BCryptDestroyHash(phHash);
      phHash = 0;
      *RtlSubAuthoritySid(Sid, 6u) = _byteswap_ulong(*(unsigned int *)pbOutput);
      *RtlSubAuthoritySid(Sid, 7u) = _byteswap_ulong(v27);
      *RtlSubAuthoritySid(Sid, 8u) = _byteswap_ulong(v28);
      *RtlSubAuthoritySid(Sid, 9u) = _byteswap_ulong(v29);
      *RtlSubAuthoritySid(Sid, 0xAu) = _byteswap_ulong(v30);
LABEL_22:
      v10 = 0;
      goto LABEL_25;
    }
LABEL_24:
    v10 = -1073741811;
    goto LABEL_25;
  }
  if ( !UuidFromStringW((RPC_WSTR)L"D7F9888F-E3FC-49b0-9EA6-A85B5F392A4F", &Uuid) )
  {
    byte_18004DB1C = 1;
    goto LABEL_8;
  }
  v10 = -1073739509;
LABEL_25:
  v19 = v10;
LABEL_26:
  if ( UnicodeString.Buffer )
  {
    RtlFreeUnicodeString(&UnicodeString);
    v10 = v19;
  }
  CTraceFuncW<long>::~CTraceFuncW<long>((__int64)v24, v6, v7);
  return v10;
}

```

## disassembly

```asm
0x18000fd0c  mov     [rsp-8+arg_18], rbx
0x18000fd11  push    rbp
0x18000fd12  push    rsi
0x18000fd13  push    rdi
0x18000fd14  push    r12
0x18000fd16  push    r13
0x18000fd18  push    r14
0x18000fd1a  push    r15
0x18000fd1c  lea     rbp, [rsp-27h]
0x18000fd21  sub     rsp, 0C0h
0x18000fd28  mov     rax, cs:__security_cookie
0x18000fd2f  xor     rax, rsp
0x18000fd32  mov     [rbp+57h+var_38], rax
0x18000fd36  xor     edi, edi
0x18000fd38  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 0B00h
0x18000fd3e  mov     r12, rdx
0x18000fd41  mov     [rbp+57h+var_B0], edi
0x18000fd44  mov     rbx, r8
0x18000fd47  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], edi
0x18000fd4a  mov     r13, rcx
0x18000fd4d  mov     [rbp+57h+phHash], rdi
0x18000fd51  xorps   xmm0, xmm0
0x18000fd54  mov     [rbp+57h+var_68], rdi
0x18000fd58  xorps   xmm1, xmm1
0x18000fd5b  mov     [rbp+57h+var_60], rdi
0x18000fd5f  lea     rdx, aLiveconvertide; "LiveConvertIdentityToSid"
0x18000fd66  xor     r9d, r9d; unsigned int
0x18000fd69  lea     rax, [rbp+57h+var_B0]
0x18000fd6d  mov     [rbp+57h+var_78], rdx
0x18000fd71  lea     r8d, [rdi+67h]; char *
0x18000fd75  mov     [rbp+57h+var_70], rax
0x18000fd79  lea     rcx, aOnecoreuapDsEx_0; "onecoreuap\\ds\\ext\\live\\identity\\cl"...
0x18000fd80  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x18000fd84  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm1
0x18000fd88  call    ?TraceFunctionEnter@MsaTracingInternal@@YAKPEBD0KPEBG@Z; MsaTracingInternal::TraceFunctionEnter(char const *,char const *,ulong,ushort const *)
0x18000fd8d  test    rbx, rbx
0x18000fd90  jz      loc_18000FFED
0x18000fd96  test    r12, r12
0x18000fd99  jz      loc_18000FFE6
0x18000fd9f  mov     r8d, [rbx]; Size
0x18000fda2  xor     edx, edx; Val
0x18000fda4  mov     rcx, r12; void *
0x18000fda7  call    memset_0
0x18000fdac  mov     rax, r13
0x18000fdaf  neg     rax
0x18000fdb2  sbb     cl, cl
0x18000fdb4  and     cl, 5
0x18000fdb7  add     cl, 6
0x18000fdba  movzx   eax, cl
0x18000fdbd  mov     ecx, eax; SubAuthorityCount
0x18000fdbf  mov     dword ptr [rbp+57h+SubAuthorityCount], eax
0x18000fdc2  call    cs:__imp_RtlLengthRequiredSid
0x18000fdc8  movzx   ecx, ax
0x18000fdcb  mov     eax, [rbx]
0x18000fdcd  mov     [rbx], ecx
0x18000fdcf  cmp     eax, ecx
0x18000fdd1  jb      loc_18000FFE6
0x18000fdd7  cmp     cs:byte_18004DB1C, dil
0x18000fdde  jnz     short loc_18000FE09
0x18000fde0  lea     rdx, Uuid; Uuid
0x18000fde7  lea     rcx, StringUuid; "D7F9888F-E3FC-49b0-9EA6-A85B5F392A4F"
0x18000fdee  call    cs:__imp_UuidFromStringW
0x18000fdf4  test    eax, eax
0x18000fdf6  jz      short loc_18000FE02
0x18000fdf8  mov     ebx, 0C000090Bh
0x18000fdfd  jmp     loc_18000FFF2
0x18000fe02  mov     cs:byte_18004DB1C, 1
0x18000fe09  mov     r8b, [rbp+57h+SubAuthorityCount]; SubAuthorityCount
0x18000fe0d  lea     rdx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18000fe11  mov     ebx, cs:Uuid.Data1
0x18000fe17  mov     rcx, r12; Sid
0x18000fe1a  movzx   edi, cs:Uuid.Data2
0x18000fe21  movzx   esi, cs:Uuid.Data3
0x18000fe28  mov     r14d, dword ptr cs:Uuid.Data4
0x18000fe2f  mov     r15d, dword ptr cs:Uuid.Data4+4
0x18000fe36  call    cs:__imp_RtlInitializeSid
0x18000fe3c  xor     edx, edx; SubAuthority
0x18000fe3e  mov     rcx, r12; Sid
0x18000fe41  call    cs:__imp_RtlSubAuthoritySid
0x18000fe47  mov     edx, 1; SubAuthority
0x18000fe4c  mov     rcx, r12; Sid
0x18000fe4f  mov     dword ptr [rax], 60h ; '`'
0x18000fe55  call    cs:__imp_RtlSubAuthoritySid
0x18000fe5b  mov     edx, 2; SubAuthority
0x18000fe60  mov     rcx, r12; Sid
0x18000fe63  mov     [rax], ebx
0x18000fe65  call    cs:__imp_RtlSubAuthoritySid
0x18000fe6b  mov     edx, 3; SubAuthority
0x18000fe70  mov     rcx, r12; Sid
0x18000fe73  mov     [rax], edi
0x18000fe75  call    cs:__imp_RtlSubAuthoritySid
0x18000fe7b  mov     edx, 4; SubAuthority
0x18000fe80  mov     rcx, r12; Sid
0x18000fe83  bswap   r14d
0x18000fe86  mov     [rax], esi
0x18000fe88  call    cs:__imp_RtlSubAuthoritySid
0x18000fe8e  mov     edx, 5; SubAuthority
0x18000fe93  mov     rcx, r12; Sid
0x18000fe96  bswap   r15d
0x18000fe99  mov     [rax], r14d
0x18000fe9c  call    cs:__imp_RtlSubAuthoritySid
0x18000fea2  xor     edi, edi
0x18000fea4  mov     [rax], r15d
0x18000fea7  test    r13, r13
0x18000feaa  jz      loc_18000FFE2
0x18000feb0  or      rax, 0FFFFFFFFFFFFFFFFh
0x18000feb4  inc     rax
0x18000feb7  cmp     [r13+rax*2+0], di
0x18000febd  jnz     short loc_18000FEB4
0x18000febf  test    eax, eax
0x18000fec1  jz      loc_18000FFED
0x18000fec7  cmp     eax, 7FFFh
0x18000fecc  jbe     short loc_18000FED8
0x18000fece  mov     ebx, 80000005h
0x18000fed3  jmp     loc_18000FFF2
0x18000fed8  mov     rdx, r13; SourceString
0x18000fedb  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000fedf  call    cs:__imp_RtlInitUnicodeString
0x18000fee5  mov     r8b, 1; AllocateDestinationString
0x18000fee8  lea     rdx, [rbp+57h+DestinationString]; SourceString
0x18000feec  lea     rcx, [rbp+57h+UnicodeString]; DestinationString
0x18000fef0  call    cs:__imp_RtlUpcaseUnicodeString
0x18000fef6  mov     [rbp+57h+var_B0], eax
0x18000fef9  mov     ebx, eax
0x18000fefb  test    eax, eax
0x18000fefd  js      loc_18000FFF5
0x18000ff03  xor     r9d, r9d; cbHashObject
0x18000ff06  mov     [rsp+0F0h+dwFlags], edi; dwFlags
0x18000ff0a  mov     [rsp+0F0h+cbSecret], edi; cbSecret
0x18000ff0e  lea     rdx, [rbp+57h+phHash]; phHash
0x18000ff12  xor     r8d, r8d; pbHashObject
0x18000ff15  mov     [rsp+0F0h+pbSecret], rdi; pbSecret
0x18000ff1a  lea     ecx, [r9+31h]; hAlgorithm
0x18000ff1e  call    cs:__imp_BCryptCreateHash
0x18000ff24  mov     esi, 7
0x18000ff29  test    eax, eax
0x18000ff2b  jns     short loc_18000FF31
0x18000ff2d  mov     ecx, esi
0x18000ff2f  int     29h; Win8: RtlFailFast(ecx)
0x18000ff31  movzx   r8d, [rbp+57h+UnicodeString.Length]; cbInput
0x18000ff36  xor     r9d, r9d; dwFlags
0x18000ff39  mov     rdx, [rbp+57h+UnicodeString.Buffer]; pbInput
0x18000ff3d  mov     rcx, [rbp+57h+phHash]; hHash
0x18000ff41  call    cs:__imp_BCryptHashData
0x18000ff47  test    eax, eax
0x18000ff49  jns     short loc_18000FF50
0x18000ff4b  mov     rcx, rsi
0x18000ff4e  int     29h; Win8: RtlFailFast(ecx)
0x18000ff50  mov     rcx, [rbp+57h+phHash]; hHash
0x18000ff54  lea     rdx, [rbp+57h+pbOutput]; pbOutput
0x18000ff58  xor     r9d, r9d; dwFlags
0x18000ff5b  lea     r8d, [r9+14h]; cbOutput
0x18000ff5f  call    cs:__imp_BCryptFinishHash
0x18000ff65  test    eax, eax
0x18000ff67  jns     short loc_18000FF6E
0x18000ff69  mov     rcx, rsi
0x18000ff6c  int     29h; Win8: RtlFailFast(ecx)
0x18000ff6e  mov     rcx, [rbp+57h+phHash]; hHash
0x18000ff72  call    cs:__imp_BCryptDestroyHash
0x18000ff78  mov     ebx, dword ptr [rbp+57h+pbOutput]
0x18000ff7b  mov     edx, 6; SubAuthority
0x18000ff80  mov     rcx, r12; Sid
0x18000ff83  mov     [rbp+57h+phHash], rdi
0x18000ff87  call    cs:__imp_RtlSubAuthoritySid
0x18000ff8d  bswap   ebx
0x18000ff8f  mov     edx, esi; SubAuthority
0x18000ff91  mov     rcx, r12; Sid
0x18000ff94  mov     [rax], ebx
0x18000ff96  mov     ebx, [rbp+57h+var_4C]
0x18000ff99  call    cs:__imp_RtlSubAuthoritySid
0x18000ff9f  bswap   ebx
0x18000ffa1  mov     edx, 8; SubAuthority
0x18000ffa6  mov     rcx, r12; Sid
0x18000ffa9  mov     [rax], ebx
0x18000ffab  mov     ebx, [rbp+57h+var_48]
0x18000ffae  call    cs:__imp_RtlSubAuthoritySid
0x18000ffb4  bswap   ebx
0x18000ffb6  mov     edx, 9; SubAuthority
0x18000ffbb  mov     rcx, r12; Sid
0x18000ffbe  mov     [rax], ebx
0x18000ffc0  mov     ebx, [rbp+57h+var_44]
0x18000ffc3  call    cs:__imp_RtlSubAuthoritySid
0x18000ffc9  bswap   ebx
0x18000ffcb  mov     edx, 0Ah; SubAuthority
0x18000ffd0  mov     rcx, r12; Sid
0x18000ffd3  mov     [rax], ebx
0x18000ffd5  mov     ebx, [rbp+57h+var_40]
0x18000ffd8  call    cs:__imp_RtlSubAuthoritySid
0x18000ffde  bswap   ebx
0x18000ffe0  mov     [rax], ebx
0x18000ffe2  mov     ebx, edi
0x18000ffe4  jmp     short loc_18000FFF2
0x18000ffe6  mov     ebx, 0C0000023h
0x18000ffeb  jmp     short loc_18000FFF2
0x18000ffed  mov     ebx, 0C000000Dh
0x18000fff2  mov     [rbp+57h+var_B0], ebx
0x18000fff5  cmp     [rbp+57h+UnicodeString.Buffer], rdi
0x18000fff9  jz      short loc_180010008
0x18000fffb  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18000ffff  call    cs:__imp_RtlFreeUnicodeString
0x180010005  mov     ebx, [rbp+57h+var_B0]
0x180010008  lea     rcx, [rbp+57h+var_78]
0x18001000c  call    ??1?$CTraceFuncW@J@@QEAA@XZ; CTraceFuncW<long>::~CTraceFuncW<long>(void)
0x180010011  mov     eax, ebx
0x180010013  mov     rcx, [rbp+57h+var_38]
0x180010017  xor     rcx, rsp; StackCookie
0x18001001a  call    __security_check_cookie
0x18001001f  mov     rbx, [rsp+0F0h+arg_18]
0x180010027  add     rsp, 0C0h
0x18001002e  pop     r15
0x180010030  pop     r14
0x180010032  pop     r13
0x180010034  pop     r12
0x180010036  pop     rdi
0x180010037  pop     rsi
0x180010038  pop     rbp
0x180010039  retn
```
