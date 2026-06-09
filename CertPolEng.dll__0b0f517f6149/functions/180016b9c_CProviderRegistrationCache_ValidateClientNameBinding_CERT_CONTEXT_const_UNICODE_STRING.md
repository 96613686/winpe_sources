# CProviderRegistrationCache::ValidateClientNameBinding(_CERT_CONTEXT const *,_UNICODE_STRING *)

- ea: `0x180016b9c`
- end: `0x180016eba`
- name: `?ValidateClientNameBinding@CProviderRegistrationCache@@AEAAKPEBU_CERT_CONTEXT@@PEAU_UNICODE_STRING@@@Z`
- size: `798`
- prototype: `__int64 __fastcall(CProviderRegistrationCache *this, const struct _CERT_CONTEXT *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `14`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000d51c`

## callees

- `0x180003dc0`
- `0x1800062a0`
- `0x180007bc0`
- `0x180007c90`
- `0x180007da0`
- `0x180007ea0`
- `0x18000bd58`
- `0x18000c344`
- `0x180016b9c`
- `0x180016f18`
- `0x18001830c`
- `0x18001856c`
- `0x18001a336`
- `0x18001a380`

## import_xrefs

- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e82`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e4b`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e59`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e71`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180016e82`
- `ntdll!RtlFreeUnicodeString` at `0x180016e63`
- `ntdll!RtlFreeUnicodeString` at `0x180016e63`
- `ntdll!RtlEqualUnicodeString` at `0x180016dc2`
- `ntdll!RtlEqualUnicodeString` at `0x180016dc2`
- `ntdll!RtlDowncaseUnicodeString` at `0x180016c51`
- `ntdll!RtlDowncaseUnicodeString` at `0x180016c51`
- `ntdll!RtlInitUnicodeString` at `0x180016db1`
- `ntdll!RtlInitUnicodeString` at `0x180016db1`

## string_xrefs

- `0x180016bed`: `CProviderRegistrationCache::ValidateClientNameBinding`

## pseudocode

```c
__int64 __fastcall CProviderRegistrationCache::ValidateClientNameBinding(
        CProviderRegistrationCache *this,
        const struct _CERT_CONTEXT *a2,
        struct _UNICODE_STRING *a3)
{
  void *v3; // rdi
  WCHAR *v4; // rbx
  __int64 v7; // rcx
  unsigned int CertName; // eax
  char *v9; // rdx
  unsigned int v10; // r8d
  char *v11; // r9
  void *v12; // r14
  unsigned int ClientNameHash; // eax
  __int64 v14; // rdx
  __int64 v15; // rcx
  int v16; // ecx
  int v17; // r8d
  unsigned int v18; // eax
  unsigned int CertNameFromSAN; // eax
  int v20; // ecx
  int v21; // r8d
  __int64 v22; // rcx
  unsigned int v23; // ebx
  unsigned int v25; // [rsp+30h] [rbp-59h] BYREF
  HLOCAL hMem; // [rsp+38h] [rbp-51h] BYREF
  size_t Size; // [rsp+40h] [rbp-49h] BYREF
  void *Buf2; // [rsp+48h] [rbp-41h] BYREF
  PCWSTR SourceString; // [rsp+50h] [rbp-39h] BYREF
  unsigned int v30; // [rsp+58h] [rbp-31h] BYREF
  unsigned int v31; // [rsp+5Ch] [rbp-2Dh] BYREF
  struct _UNICODE_STRING UniDest; // [rsp+60h] [rbp-29h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+70h] [rbp-19h] BYREF
  _BYTE v34[32]; // [rsp+80h] [rbp-9h] BYREF
  void *Buf1[2]; // [rsp+A0h] [rbp+17h] BYREF

  v3 = 0;
  v25 = 0;
  v4 = 0;
  Buf2 = 0;
  Buf1[0] = 0;
  Size = 0;
  SourceString = 0;
  v31 = 0;
  v30 = 0;
  UniDest = 0;
  hMem = 0;
  DestinationString = 0;
  CLogETWBlock::CLogETWBlock(
    (CLogETWBlock *)v34,
    "CProviderRegistrationCache::ValidateClientNameBinding",
    (int *)a3,
    0,
    &v25);
  IDUnicodeStringToString((unsigned __int16 **)&hMem, a3);
  if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
    McTemplateU0z_EtwEventWriteTransfer(v7, ValidateClientName, hMem);
  if ( RtlDowncaseUnicodeString(&UniDest, a3, 1u) < 0 )
  {
    v25 = 14;
    goto LABEL_38;
  }
  CertName = GetCertName(a2, 1, "1.3.6.1.4.1.311.66", (unsigned __int8 **)Buf1, (unsigned int *)&Size, &v30);
  v12 = Buf1[0];
  v25 = CertName;
  if ( CertName != 14 )
  {
    if ( CertName )
    {
      if ( CertName != 1168 )
        goto LABEL_34;
      CertNameFromSAN = GetCertNameFromSAN(a2, v9, v10, v11, (unsigned __int16 **)&SourceString, &v31);
      v25 = CertNameFromSAN;
      if ( CertNameFromSAN )
      {
        if ( CertNameFromSAN == 1168 )
        {
          if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
            McGenEventWrite_EtwEventWriteTransfer(v20, (unsigned int)ClientValidationSkipped, v21, 1, (__int64)Buf1);
          v25 = 0;
        }
        v4 = (WCHAR *)SourceString;
        goto LABEL_34;
      }
      v4 = (WCHAR *)SourceString;
      RtlInitUnicodeString(&DestinationString, SourceString);
      if ( RtlEqualUnicodeString(&DestinationString, &UniDest, 1u) )
      {
        if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
          McTemplateU0zz_EtwEventWriteTransfer(v22, CertUPNMatched, v4, hMem);
        v18 = 0;
        goto LABEL_18;
      }
      if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
        McTemplateU0zz_EtwEventWriteTransfer(v22, CertUPNNotMatched, v4, hMem);
    }
    else
    {
      ClientNameHash = GetClientNameHash(a2, &UniDest, (unsigned __int8 **)&Buf2, (unsigned int *)&Size + 1);
      v25 = ClientNameHash;
      if ( ClientNameHash )
      {
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McTemplateU0sq_EtwEventWriteTransfer(v15, v14, "GetClientNameHash", ClientNameHash);
        v3 = Buf2;
        goto LABEL_34;
      }
      v3 = Buf2;
      if ( (_DWORD)Size == HIDWORD(Size) )
      {
        if ( !memcmp_0(v12, Buf2, (unsigned int)Size) )
        {
          v25 = 0;
          if ( (Microsoft_Windows_CertPolEngEnableBits & 1) != 0 )
            McGenEventWrite_EtwEventWriteTransfer(v16, (unsigned int)"*", v17, 1, (__int64)Buf1);
          goto LABEL_34;
        }
        if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
          McGenEventWrite_EtwEventWriteTransfer(v16, (unsigned int)CertHashFailure, v17, 1, (__int64)Buf1);
      }
      else if ( (Microsoft_Windows_CertPolEngEnableBits & 2) != 0 )
      {
        McTemplateU0qq_EtwEventWriteTransfer(v15, CertHashLenNotMatch, (unsigned int)Size, HIDWORD(Size));
      }
    }
    v18 = 1326;
LABEL_18:
    v25 = v18;
  }
LABEL_34:
  if ( v12 )
    LocalFree(v12);
  if ( v3 )
    LocalFree(v3);
LABEL_38:
  RtlFreeUnicodeString(&UniDest);
  if ( v4 )
    LocalFree(v4);
  if ( hMem )
    LocalFree(hMem);
  v23 = v25;
  CLogETWBlock::~CLogETWBlock((CLogETWBlock *)v34);
  return v23;
}

```

## disassembly

```asm
0x180016b9c  mov     [rsp-8+arg_0], rbx
0x180016ba1  push    rbp
0x180016ba2  push    rdi
0x180016ba3  push    r13
0x180016ba5  push    r14
0x180016ba7  push    r15
0x180016ba9  lea     rbp, [rsp-37h]
0x180016bae  sub     rsp, 0C0h
0x180016bb5  mov     rax, cs:__security_cookie
0x180016bbc  xor     rax, rsp
0x180016bbf  mov     [rbp+57h+var_30], rax
0x180016bc3  xor     edi, edi
0x180016bc5  mov     [rbp+57h+var_B0], 0
0x180016bcc  xor     ebx, ebx
0x180016bce  mov     [rbp+57h+Buf2], rdi
0x180016bd2  mov     r15, rdx
0x180016bd5  mov     dword ptr [rbp+57h+Size+4], edi
0x180016bd8  xorps   xmm0, xmm0
0x180016bdb  mov     [rbp+57h+Buf1], rdi
0x180016bdf  xorps   xmm1, xmm1
0x180016be2  mov     dword ptr [rbp+57h+Size], edi
0x180016be5  lea     rax, [rbp+57h+var_B0]
0x180016be9  mov     [rbp+57h+SourceString], rbx
0x180016bed  lea     rdx, aCproviderregis_13; "CProviderRegistrationCache::ValidateCli"...
0x180016bf4  mov     [rbp+57h+var_84], ebx
0x180016bf7  xor     r9d, r9d; int *
0x180016bfa  mov     [rbp+57h+var_88], ebx
0x180016bfd  lea     rcx, [rbp+57h+var_60]; this
0x180016c01  mov     [rsp+0E0h+var_C0], rax; unsigned int *
0x180016c06  movups  xmmword ptr [rbp+57h+UniDest.Length], xmm0
0x180016c0a  mov     r14, r8
0x180016c0d  mov     [rbp+57h+hMem], 0
0x180016c15  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x180016c19  call    ??0CLogETWBlock@@QEAA@PEBDPEAJ1PEAK@Z; CLogETWBlock::CLogETWBlock(char const *,long *,long *,ulong *)
0x180016c1e  mov     rdx, r14; struct _UNICODE_STRING *
0x180016c21  lea     rcx, [rbp+57h+hMem]; unsigned __int16 **
0x180016c25  call    ?IDUnicodeStringToString@@YAKPEAPEAGPEAU_UNICODE_STRING@@@Z; IDUnicodeStringToString(ushort * *,_UNICODE_STRING *)
0x180016c2a  lea     r13d, [rdi+1]
0x180016c2e  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, r13b
0x180016c35  jz      short loc_180016C47
0x180016c37  mov     r8, [rbp+57h+hMem]
0x180016c3b  lea     rdx, ValidateClientName
0x180016c42  call    McTemplateU0z_EtwEventWriteTransfer
0x180016c47  mov     r8b, r13b; AllocateDestinationString
0x180016c4a  lea     rcx, [rbp+57h+UniDest]; UniDest
0x180016c4e  mov     rdx, r14; UniSource
0x180016c51  call    cs:__imp_RtlDowncaseUnicodeString
0x180016c57  test    eax, eax
0x180016c59  jns     short loc_180016C67
0x180016c5b  mov     [rbp+57h+var_B0], 0Eh
0x180016c62  jmp     loc_180016E5F
0x180016c67  lea     rax, [rbp+57h+var_88]
0x180016c6b  mov     edx, r13d; int
0x180016c6e  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x180016c73  lea     r9, [rbp+57h+Buf1]; unsigned __int8 **
0x180016c77  lea     rax, [rbp+57h+Size]
0x180016c7b  mov     rcx, r15; struct _CERT_CONTEXT *
0x180016c7e  lea     r8, a13614131166; "1.3.6.1.4.1.311.66"
0x180016c85  mov     [rsp+0E0h+var_C0], rax; unsigned int *
0x180016c8a  call    ?GetCertName@@YAKPEBU_CERT_CONTEXT@@HPEADPEAPEAEPEAK3@Z; GetCertName(_CERT_CONTEXT const *,int,char *,uchar * *,ulong *,ulong *)
0x180016c8f  mov     r14, [rbp+57h+Buf1]
0x180016c93  mov     [rbp+57h+var_B0], eax
0x180016c96  cmp     eax, 0Eh
0x180016c99  jz      loc_180016E43
0x180016c9f  test    eax, eax
0x180016ca1  jnz     loc_180016D7A
0x180016ca7  lea     r9, [rbp+57h+Size+4]; unsigned int *
0x180016cab  mov     rcx, r15; struct _CERT_CONTEXT *
0x180016cae  lea     r8, [rbp+57h+Buf2]; unsigned __int8 **
0x180016cb2  lea     rdx, [rbp+57h+UniDest]; struct _UNICODE_STRING *
0x180016cb6  call    ?GetClientNameHash@@YAKPEBU_CERT_CONTEXT@@PEAU_UNICODE_STRING@@PEAPEAEPEAK@Z; GetClientNameHash(_CERT_CONTEXT const *,_UNICODE_STRING *,uchar * *,ulong *)
0x180016cbb  mov     [rbp+57h+var_B0], eax
0x180016cbe  test    eax, eax
0x180016cc0  jz      short loc_180016CE3
0x180016cc2  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180016cc9  jz      short loc_180016CDA
0x180016ccb  mov     r9d, eax
0x180016cce  lea     r8, aGetclientnameh; "GetClientNameHash"
0x180016cd5  call    McTemplateU0sq_EtwEventWriteTransfer
0x180016cda  mov     rdi, [rbp+57h+Buf2]
0x180016cde  jmp     loc_180016E43
0x180016ce3  mov     eax, dword ptr [rbp+57h+Size]
0x180016ce6  mov     r9d, dword ptr [rbp+57h+Size+4]
0x180016cea  mov     rdi, [rbp+57h+Buf2]
0x180016cee  cmp     eax, r9d
0x180016cf1  jz      short loc_180016D0D
0x180016cf3  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180016cfa  jz      short loc_180016D40
0x180016cfc  mov     r8d, eax
0x180016cff  lea     rdx, CertHashLenNotMatch
0x180016d06  call    McTemplateU0qq_EtwEventWriteTransfer
0x180016d0b  jmp     short loc_180016D40
0x180016d0d  mov     r8, rax; Size
0x180016d10  mov     rdx, rdi; Buf2
0x180016d13  mov     rcx, r14; Buf1
0x180016d16  call    memcmp_0
0x180016d1b  test    eax, eax
0x180016d1d  jz      short loc_180016D4D
0x180016d1f  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180016d26  jz      short loc_180016D40
0x180016d28  lea     rax, [rbp+57h+Buf1]
0x180016d2c  mov     r9d, r13d
0x180016d2f  lea     rdx, CertHashFailure
0x180016d36  mov     [rsp+0E0h+var_C0], rax
0x180016d3b  call    McGenEventWrite_EtwEventWriteTransfer
0x180016d40  mov     eax, 52Eh
0x180016d45  mov     [rbp+57h+var_B0], eax
0x180016d48  jmp     loc_180016E43
0x180016d4d  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, r13b
0x180016d54  mov     [rbp+57h+var_B0], ebx
0x180016d57  jz      loc_180016E43
0x180016d5d  lea     rax, [rbp+57h+Buf1]
0x180016d61  mov     r9d, r13d
0x180016d64  lea     rdx, CertHashMatched; "*"
0x180016d6b  mov     [rsp+0E0h+var_C0], rax
0x180016d70  call    McGenEventWrite_EtwEventWriteTransfer
0x180016d75  jmp     loc_180016E43
0x180016d7a  cmp     eax, 490h
0x180016d7f  jnz     loc_180016E43
0x180016d85  lea     rax, [rbp+57h+var_84]
0x180016d89  mov     rcx, r15; struct _CERT_CONTEXT *
0x180016d8c  mov     [rsp+0E0h+var_B8], rax; unsigned int *
0x180016d91  lea     rax, [rbp+57h+SourceString]
0x180016d95  mov     [rsp+0E0h+var_C0], rax; unsigned __int16 **
0x180016d9a  call    ?GetCertNameFromSAN@@YAKPEBU_CERT_CONTEXT@@PEADK1PEAPEAGPEAK@Z; GetCertNameFromSAN(_CERT_CONTEXT const *,char *,ulong,char *,ushort * *,ulong *)
0x180016d9f  mov     [rbp+57h+var_B0], eax
0x180016da2  test    eax, eax
0x180016da4  jnz     short loc_180016E14
0x180016da6  mov     rbx, [rbp+57h+SourceString]
0x180016daa  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x180016dae  mov     rdx, rbx; SourceString
0x180016db1  call    cs:__imp_RtlInitUnicodeString
0x180016db7  mov     r8b, r13b; CaseInsensitive
0x180016dba  lea     rdx, [rbp+57h+UniDest]; String2
0x180016dbe  lea     rcx, [rbp+57h+DestinationString]; String1
0x180016dc2  call    cs:__imp_RtlEqualUnicodeString
0x180016dc8  test    al, al
0x180016dca  jnz     short loc_180016DF1
0x180016dcc  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, 2
0x180016dd3  jz      loc_180016D40
0x180016dd9  mov     r9, [rbp+57h+hMem]
0x180016ddd  lea     rdx, CertUPNNotMatched
0x180016de4  mov     r8, rbx
0x180016de7  call    McTemplateU0zz_EtwEventWriteTransfer
0x180016dec  jmp     loc_180016D40
0x180016df1  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, r13b
0x180016df8  jz      short loc_180016E0D
0x180016dfa  mov     r9, [rbp+57h+hMem]
0x180016dfe  lea     rdx, CertUPNMatched
0x180016e05  mov     r8, rbx
0x180016e08  call    McTemplateU0zz_EtwEventWriteTransfer
0x180016e0d  xor     eax, eax
0x180016e0f  jmp     loc_180016D45
0x180016e14  cmp     eax, 490h
0x180016e19  jnz     short loc_180016E3F
0x180016e1b  test    byte ptr cs:Microsoft_Windows_CertPolEngEnableBits, r13b
0x180016e22  jz      short loc_180016E3C
0x180016e24  lea     rax, [rbp+57h+Buf1]
0x180016e28  mov     r9d, r13d
0x180016e2b  lea     rdx, ClientValidationSkipped
0x180016e32  mov     [rsp+0E0h+var_C0], rax
0x180016e37  call    McGenEventWrite_EtwEventWriteTransfer
0x180016e3c  mov     [rbp+57h+var_B0], ebx
0x180016e3f  mov     rbx, [rbp+57h+SourceString]
0x180016e43  test    r14, r14
0x180016e46  jz      short loc_180016E51
0x180016e48  mov     rcx, r14; hMem
0x180016e4b  call    cs:__imp_LocalFree
0x180016e51  test    rdi, rdi
0x180016e54  jz      short loc_180016E5F
0x180016e56  mov     rcx, rdi; hMem
0x180016e59  call    cs:__imp_LocalFree
0x180016e5f  lea     rcx, [rbp+57h+UniDest]; UnicodeString
0x180016e63  call    cs:__imp_RtlFreeUnicodeString
0x180016e69  test    rbx, rbx
0x180016e6c  jz      short loc_180016E77
0x180016e6e  mov     rcx, rbx; hMem
0x180016e71  call    cs:__imp_LocalFree
0x180016e77  cmp     [rbp+57h+hMem], 0
0x180016e7c  jz      short loc_180016E88
0x180016e7e  mov     rcx, [rbp+57h+hMem]; hMem
0x180016e82  call    cs:__imp_LocalFree
0x180016e88  mov     ebx, [rbp+57h+var_B0]
0x180016e8b  lea     rcx, [rbp+57h+var_60]; this
0x180016e8f  call    ??1CLogETWBlock@@QEAA@XZ; CLogETWBlock::~CLogETWBlock(void)
0x180016e94  mov     eax, ebx
0x180016e96  mov     rcx, [rbp+57h+var_30]
0x180016e9a  xor     rcx, rsp; StackCookie
0x180016e9d  call    __security_check_cookie
0x180016ea2  mov     rbx, [rsp+0E0h+arg_0]
0x180016eaa  add     rsp, 0C0h
0x180016eb1  pop     r15
0x180016eb3  pop     r14
0x180016eb5  pop     r13
0x180016eb7  pop     rdi
0x180016eb8  pop     rbp
0x180016eb9  retn
```
