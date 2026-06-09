# PackageSid::FamilyMonikerStringToSid(Common::COMMON_STRING const *,void * *)

- ea: `0x18000d9ec`
- end: `0x18000dc4b`
- name: `?FamilyMonikerStringToSid@PackageSid@@SAJPEBUCOMMON_STRING@Common@@PEAPEAX@Z`
- size: `607`
- prototype: `static int(const struct Common::COMMON_STRING *, void **)`
- caller_count: `1`
- callee_count: `9`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18000d800`

## callees

- `0x18000d9ec`
- `0x18000de90`
- `0x18000e050`
- `0x18000e3c8`
- `0x18001685c`
- `0x180017f50`
- `0x18001a520`
- `0x18004c972`
- `0x18004c9d0`

## import_xrefs

- `ntdll!RtlAllocateAndInitializeSid` at `0x18000dbe8`
- `ntdll!RtlAllocateAndInitializeSid` at `0x18000dbe8`
- `ntdll!RtlDowncaseUnicodeString` at `0x18000da52`
- `ntdll!RtlDowncaseUnicodeString` at `0x18000da52`
- `ntdll!RtlFreeUnicodeString` at `0x18000dab1`
- `ntdll!RtlFreeUnicodeString` at `0x18000daf4`
- `ntdll!RtlFreeUnicodeString` at `0x18000dc04`
- `ntdll!RtlFreeUnicodeString` at `0x18000dc1c`
- `ntdll!RtlFreeUnicodeString` at `0x18000dab1`
- `ntdll!RtlFreeUnicodeString` at `0x18000daf4`
- `ntdll!RtlFreeUnicodeString` at `0x18000dc04`
- `ntdll!RtlFreeUnicodeString` at `0x18000dc1c`
- `ntdll!RtlInitUnicodeString` at `0x18000da41`
- `ntdll!RtlInitUnicodeString` at `0x18000da41`

## string_xrefs

- `0x18000da90`: `onecore\base\appmodel\package\packagesid.cpp`
- `0x18000dad9`: `onecore\base\appmodel\package\packagesid.cpp`

## pseudocode

```c
int __fastcall PackageSid::FamilyMonikerStringToSid(const struct Common::COMMON_STRING *a1, void **a2)
{
  const WCHAR *v4; // rdx
  NTSTATUS v5; // eax
  int v6; // eax
  int v7; // ebx
  unsigned int v8; // edx
  Common::CryptoProvider *v9; // rbx
  int started; // edi
  __int64 v11; // rdx
  unsigned int v12; // edx
  char *v13; // r12
  unsigned int v14; // r14d
  unsigned int v15; // r15d
  unsigned int v16; // esi
  unsigned int v17; // edx
  NTSTATUS v18; // edi
  struct Common::CryptoProvider *v19; // [rsp+60h] [rbp-49h] BYREF
  struct _UNICODE_STRING UniDest; // [rsp+68h] [rbp-41h] BYREF
  void *Src[2]; // [rsp+78h] [rbp-31h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+88h] [rbp-21h] BYREF
  _SID_IDENTIFIER_AUTHORITY IdentifierAuthority; // [rsp+98h] [rbp-11h] BYREF
  ULONG SubAuthority0[4]; // [rsp+A0h] [rbp-9h] BYREF
  ULONG SubAuthority4[4]; // [rsp+B0h] [rbp+7h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  if ( *(_DWORD *)a1 > 0xFFFFu )
    return -2147024809;
  v4 = (const WCHAR *)*((_QWORD *)a1 + 1);
  UniDest = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, v4);
  v5 = RtlDowncaseUnicodeString(&UniDest, &DestinationString, 1u);
  if ( v5 < 0 )
    return v5 | 0x10000000;
  Src[1] = UniDest.Buffer;
  Src[0] = (void *)UniDest.Length;
  v19 = 0;
  v6 = Common::CryptoProvider::Create(&v19);
  v7 = v6;
  if ( v6 < 0 )
  {
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)0x36,
      (int)"onecore\\base\\appmodel\\package\\packagesid.cpp",
      (const char *)(unsigned int)v6);
    Common::AutoPtrDeallocate<Common::CryptoProvider>(v19, v8);
    RtlFreeUnicodeString(&UniDest);
    return v7;
  }
  v9 = v19;
  started = Common::CryptoProvider::StartDigest(v19);
  if ( started < 0 )
  {
    v11 = 55;
LABEL_9:
    wil::details::in1diag3::_Log_Hr(
      retaddr,
      (void *)v11,
      (int)"onecore\\base\\appmodel\\package\\packagesid.cpp",
      (const char *)(unsigned int)started);
    Common::AutoPtrDeallocate<Common::CryptoProvider>(v9, v12);
    RtlFreeUnicodeString(&UniDest);
    return started;
  }
  started = Common::CryptoProvider::DigestData(v9, (const struct Common::COMMON_BYTES *)Src);
  if ( started < 0 )
  {
    v11 = 56;
    goto LABEL_9;
  }
  *(_OWORD *)Src = 0;
  started = Common::CryptoProvider::GetDigest(v9, (struct Common::COMMON_BYTES *)Src);
  if ( started < 0 )
  {
    v11 = 59;
    goto LABEL_9;
  }
  v13 = (char *)Src[1];
  v14 = 28;
  if ( LODWORD(Src[0]) < 0x1C )
    v14 = (unsigned int)Src[0];
  *(_OWORD *)SubAuthority0 = 0;
  SubAuthority0[0] = 2;
  v15 = 1;
  *(_OWORD *)SubAuthority4 = 0;
  do
  {
    if ( !v14 )
      break;
    v16 = v14;
    if ( v14 > 4 )
      v16 = 4;
    memcpy_0(&SubAuthority0[v15], v13, v16);
    v13 += v16;
    v14 -= v16;
    ++v15;
  }
  while ( v15 < 8 );
  *(_DWORD *)IdentifierAuthority.Value = 0;
  *(_WORD *)&IdentifierAuthority.Value[4] = 3840;
  v18 = RtlAllocateAndInitializeSid(
          &IdentifierAuthority,
          v15,
          SubAuthority0[0],
          SubAuthority0[1],
          SubAuthority0[2],
          SubAuthority0[3],
          SubAuthority4[0],
          SubAuthority4[1],
          SubAuthority4[2],
          SubAuthority4[3],
          a2);
  if ( v18 < 0 )
  {
    Common::AutoPtrDeallocate<Common::CryptoProvider>(v19, v17);
    RtlFreeUnicodeString(&UniDest);
    return v18 | 0x10000000;
  }
  Common::AutoPtrDeallocate<Common::CryptoProvider>(v19, v17);
  RtlFreeUnicodeString(&UniDest);
  return 0;
}

```

## disassembly

```asm
0x18000d9ec  mov     [rsp-8+arg_10], rbx
0x18000d9f1  push    rbp
0x18000d9f2  push    rsi
0x18000d9f3  push    rdi
0x18000d9f4  push    r12
0x18000d9f6  push    r13
0x18000d9f8  push    r14
0x18000d9fa  push    r15
0x18000d9fc  lea     rbp, [rsp-27h]
0x18000da01  sub     rsp, 0D0h
0x18000da08  mov     rax, cs:__security_cookie
0x18000da0f  xor     rax, rsp
0x18000da12  mov     [rbp+57h+var_40], rax
0x18000da16  cmp     dword ptr [rcx], 0FFFFh
0x18000da1c  mov     r13, rdx
0x18000da1f  jbe     short loc_18000DA2B
0x18000da21  mov     eax, 80070057h
0x18000da26  jmp     loc_18000DC24
0x18000da2b  mov     rdx, [rcx+8]; SourceString
0x18000da2f  xorps   xmm0, xmm0
0x18000da32  xorps   xmm1, xmm1
0x18000da35  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x18000da39  movups  xmmword ptr [rbp+57h+UniDest.Length], xmm0
0x18000da3d  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x18000da41  call    cs:__imp_RtlInitUnicodeString
0x18000da47  mov     r8b, 1; AllocateDestinationString
0x18000da4a  lea     rdx, [rbp+57h+DestinationString]; UniSource
0x18000da4e  lea     rcx, [rbp+57h+UniDest]; UniDest
0x18000da52  call    cs:__imp_RtlDowncaseUnicodeString
0x18000da58  xor     esi, esi
0x18000da5a  test    eax, eax
0x18000da5c  jns     short loc_18000DA67
0x18000da5e  bts     eax, 1Ch
0x18000da62  jmp     loc_18000DC24
0x18000da67  mov     rax, [rbp+57h+UniDest.Buffer]
0x18000da6b  lea     rcx, [rbp+57h+var_A0]; struct Common::CryptoProvider **
0x18000da6f  mov     [rbp+57h+Src+8], rax
0x18000da73  movzx   eax, [rbp+57h+UniDest.Length]
0x18000da77  mov     dword ptr [rbp+57h+Src], eax
0x18000da7a  mov     dword ptr [rbp+57h+Src+4], esi
0x18000da7d  mov     [rbp+57h+var_A0], rsi
0x18000da81  call    ?Create@CryptoProvider@Common@@SAJPEAPEAV12@@Z; Common::CryptoProvider::Create(Common::CryptoProvider * *)
0x18000da86  mov     ebx, eax
0x18000da88  test    eax, eax
0x18000da8a  jns     short loc_18000DABE
0x18000da8c  mov     rcx, [rbp+5Fh]; this
0x18000da90  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\package\\packa"...
0x18000da97  mov     r9d, eax; char *
0x18000da9a  mov     edx, 36h ; '6'; void *
0x18000da9f  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000daa4  mov     rcx, [rbp+57h+var_A0]
0x18000daa8  call    ??$AutoPtrDeallocate@VCryptoProvider@Common@@@Common@@YAXPEAVCryptoProvider@0@@Z; Common::AutoPtrDeallocate<Common::CryptoProvider>(Common::CryptoProvider *)
0x18000daad  lea     rcx, [rbp+57h+UniDest]; UnicodeString
0x18000dab1  call    cs:__imp_RtlFreeUnicodeString
0x18000dab7  mov     eax, ebx
0x18000dab9  jmp     loc_18000DC24
0x18000dabe  mov     rbx, [rbp+57h+var_A0]
0x18000dac2  mov     rcx, rbx; this
0x18000dac5  call    ?StartDigest@CryptoProvider@Common@@QEAAJXZ; Common::CryptoProvider::StartDigest(void)
0x18000daca  mov     edi, eax
0x18000dacc  test    eax, eax
0x18000dace  jns     short loc_18000DB01
0x18000dad0  mov     edx, 37h ; '7'; void *
0x18000dad5  mov     rcx, [rbp+5Fh]; this
0x18000dad9  lea     r8, aOnecoreBaseApp_3; "onecore\\base\\appmodel\\package\\packa"...
0x18000dae0  mov     r9d, edi; char *
0x18000dae3  call    ?_Log_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Log_Hr(void *,uint,char const *,long)
0x18000dae8  mov     rcx, rbx
0x18000daeb  call    ??$AutoPtrDeallocate@VCryptoProvider@Common@@@Common@@YAXPEAVCryptoProvider@0@@Z; Common::AutoPtrDeallocate<Common::CryptoProvider>(Common::CryptoProvider *)
0x18000daf0  lea     rcx, [rbp+57h+UniDest]; UnicodeString
0x18000daf4  call    cs:__imp_RtlFreeUnicodeString
0x18000dafa  mov     eax, edi
0x18000dafc  jmp     loc_18000DC24
0x18000db01  lea     rdx, [rbp+57h+Src]; struct Common::COMMON_BYTES *
0x18000db05  mov     rcx, rbx; this
0x18000db08  call    ?DigestData@CryptoProvider@Common@@QEAAJPEBUCOMMON_BYTES@2@@Z; Common::CryptoProvider::DigestData(Common::COMMON_BYTES const *)
0x18000db0d  mov     edi, eax
0x18000db0f  test    eax, eax
0x18000db11  jns     short loc_18000DB1A
0x18000db13  mov     edx, 38h ; '8'
0x18000db18  jmp     short loc_18000DAD5
0x18000db1a  xorps   xmm0, xmm0
0x18000db1d  lea     rdx, [rbp+57h+Src]; struct Common::COMMON_BYTES *
0x18000db21  mov     rcx, rbx; this
0x18000db24  movups  xmmword ptr [rbp+57h+Src], xmm0
0x18000db28  call    ?GetDigest@CryptoProvider@Common@@QEAAJPEAUCOMMON_BYTES@2@@Z; Common::CryptoProvider::GetDigest(Common::COMMON_BYTES *)
0x18000db2d  mov     edi, eax
0x18000db2f  test    eax, eax
0x18000db31  jns     short loc_18000DB3A
0x18000db33  mov     edx, 3Bh ; ';'
0x18000db38  jmp     short loc_18000DAD5
0x18000db3a  mov     r12, [rbp+57h+Src+8]
0x18000db3e  mov     r14d, 1Ch
0x18000db44  cmp     dword ptr [rbp+57h+Src], r14d
0x18000db48  xorps   xmm0, xmm0
0x18000db4b  mov     ebx, 4
0x18000db50  cmovb   r14d, dword ptr [rbp+57h+Src]
0x18000db55  movups  xmmword ptr [rbp+57h+SubAuthority0], xmm0
0x18000db59  mov     [rbp+57h+SubAuthority0], 2
0x18000db60  lea     r15d, [rbx-3]
0x18000db64  movups  xmmword ptr [rbp+57h+var_50], xmm0
0x18000db68  test    r14d, r14d
0x18000db6b  jz      short loc_18000DB9D
0x18000db6d  mov     eax, r15d
0x18000db70  lea     rcx, [rbp+57h+SubAuthority0]
0x18000db74  cmp     r14d, ebx
0x18000db77  mov     esi, r14d
0x18000db7a  mov     rdx, r12; Src
0x18000db7d  cmova   esi, ebx
0x18000db80  lea     rcx, [rcx+rax*4]; void *
0x18000db84  mov     r8d, esi; Size
0x18000db87  mov     edi, esi
0x18000db89  call    memcpy_0
0x18000db8e  add     r12, rdi
0x18000db91  sub     r14d, esi
0x18000db94  inc     r15d
0x18000db97  cmp     r15d, 8
0x18000db9b  jb      short loc_18000DB68
0x18000db9d  mov     eax, [rbp+57h+var_50+0Ch]
0x18000dba0  lea     rcx, [rbp+57h+IdentifierAuthority]; IdentifierAuthority
0x18000dba4  mov     r9d, [rbp+57h+SubAuthority0+4]; SubAuthority1
0x18000dba8  mov     dl, r15b; SubAuthorityCount
0x18000dbab  mov     r8d, [rbp+57h+SubAuthority0]; SubAuthority0
0x18000dbaf  mov     [rsp+100h+Sid], r13; Sid
0x18000dbb4  mov     [rsp+100h+SubAuthority7], eax; SubAuthority7
0x18000dbb8  mov     eax, [rbp+57h+var_50+8]
0x18000dbbb  mov     [rsp+100h+SubAuthority6], eax; SubAuthority6
0x18000dbbf  mov     eax, [rbp+57h+var_50+4]
0x18000dbc2  mov     [rsp+100h+SubAuthority5], eax; SubAuthority5
0x18000dbc6  mov     eax, [rbp+57h+var_50]
0x18000dbc9  mov     [rsp+100h+SubAuthority4], eax; SubAuthority4
0x18000dbcd  mov     eax, [rbp+57h+SubAuthority0+0Ch]
0x18000dbd0  mov     [rsp+100h+SubAuthority3], eax; SubAuthority3
0x18000dbd4  mov     eax, [rbp+57h+SubAuthority0+8]
0x18000dbd7  mov     [rsp+100h+SubAuthority2], eax; SubAuthority2
0x18000dbdb  mov     dword ptr [rbp+57h+IdentifierAuthority.Value], 0
0x18000dbe2  mov     word ptr [rbp+57h+IdentifierAuthority.Value+4], 0F00h
0x18000dbe8  call    cs:__imp_RtlAllocateAndInitializeSid
0x18000dbee  mov     rbx, [rbp+57h+var_A0]
0x18000dbf2  mov     edi, eax
0x18000dbf4  mov     rcx, rbx
0x18000dbf7  test    eax, eax
0x18000dbf9  jns     short loc_18000DC13
0x18000dbfb  call    ??$AutoPtrDeallocate@VCryptoProvider@Common@@@Common@@YAXPEAVCryptoProvider@0@@Z; Common::AutoPtrDeallocate<Common::CryptoProvider>(Common::CryptoProvider *)
0x18000dc00  lea     rcx, [rbp+57h+UniDest]; UnicodeString
0x18000dc04  call    cs:__imp_RtlFreeUnicodeString
0x18000dc0a  bts     edi, 1Ch
0x18000dc0e  jmp     loc_18000DAFA
0x18000dc13  call    ??$AutoPtrDeallocate@VCryptoProvider@Common@@@Common@@YAXPEAVCryptoProvider@0@@Z; Common::AutoPtrDeallocate<Common::CryptoProvider>(Common::CryptoProvider *)
0x18000dc18  lea     rcx, [rbp+57h+UniDest]; UnicodeString
0x18000dc1c  call    cs:__imp_RtlFreeUnicodeString
0x18000dc22  xor     eax, eax
0x18000dc24  mov     rcx, [rbp+57h+var_40]
0x18000dc28  xor     rcx, rsp; StackCookie
0x18000dc2b  call    __security_check_cookie
0x18000dc30  mov     rbx, [rsp+100h+arg_10]
0x18000dc38  add     rsp, 0D0h
0x18000dc3f  pop     r15
0x18000dc41  pop     r14
0x18000dc43  pop     r13
0x18000dc45  pop     r12
0x18000dc47  pop     rdi
0x18000dc48  pop     rsi
0x18000dc49  pop     rbp
0x18000dc4a  retn
```
