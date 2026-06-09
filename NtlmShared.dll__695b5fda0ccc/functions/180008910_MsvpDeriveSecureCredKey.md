# MsvpDeriveSecureCredKey

- ea: `0x180008910`
- end: `0x180008a7d`
- name: `MsvpDeriveSecureCredKey`
- size: `365`
- prototype: `__int64 __fastcall(PSID Sid, PUCHAR pbPassword, PUCHAR pbDerivedKey)`
- caller_count: `0`
- callee_count: `2`
- tags: `authz_impersonation, loader_planting`

## callees

- `0x180008910`
- `0x18000c560`

## import_xrefs

- `ntdll!RtlFreeUnicodeString` at `0x180008a4f`
- `ntdll!RtlFreeUnicodeString` at `0x180008a4f`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180008974`
- `ntdll!RtlConvertSidToUnicodeString` at `0x180008974`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180008a45`
- `bcrypt!BCryptCloseAlgorithmProvider` at `0x180008a45`
- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x1800089e3`
- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x180008a32`
- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x1800089e3`
- `bcrypt!BCryptDeriveKeyPBKDF2` at `0x180008a32`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180008998`
- `bcrypt!BCryptOpenAlgorithmProvider` at `0x180008998`

## pseudocode

```c
__int64 __fastcall MsvpDeriveSecureCredKey(PSID Sid, PUCHAR pbPassword, UCHAR *pbDerivedKey)
{
  NTSTATUS v5; // ebx
  UCHAR *Buffer; // r9
  BCRYPT_ALG_HANDLE v7; // rcx
  BCRYPT_ALG_HANDLE phAlgorithm; // [rsp+50h] [rbp+7h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+58h] [rbp+Fh] BYREF
  UCHAR pbPassworda[16]; // [rsp+68h] [rbp+1Fh] BYREF
  __int128 v12; // [rsp+78h] [rbp+2Fh]

  *(_OWORD *)pbPassworda = 0;
  v12 = 0;
  if ( !Sid || !pbPassword || !pbDerivedKey )
    return 3221225485LL;
  phAlgorithm = 0;
  UnicodeString = 0;
  v5 = RtlConvertSidToUnicodeString(&UnicodeString, Sid, 1u);
  if ( v5 >= 0 )
  {
    v5 = BCryptOpenAlgorithmProvider(&phAlgorithm, L"SHA256", 0, 8u);
    if ( v5 >= 0 )
    {
      v5 = BCryptDeriveKeyPBKDF2(
             phAlgorithm,
             pbPassword,
             0x10u,
             (PUCHAR)UnicodeString.Buffer,
             UnicodeString.Length,
             0x2710u,
             pbPassworda,
             0x20u,
             0);
      if ( v5 >= 0 )
      {
        Buffer = (UCHAR *)UnicodeString.Buffer;
        v7 = phAlgorithm;
        *(_OWORD *)pbDerivedKey = 0;
        *((_DWORD *)pbDerivedKey + 4) = 0;
        v5 = BCryptDeriveKeyPBKDF2(v7, pbPassworda, 0x20u, Buffer, UnicodeString.Length, 1u, pbDerivedKey, 0x10u, 0);
      }
    }
  }
  if ( phAlgorithm )
    BCryptCloseAlgorithmProvider(phAlgorithm, 0);
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180008910  mov     [rsp-8+arg_18], rbx
0x180008915  push    rbp
0x180008916  push    rsi
0x180008917  push    rdi
0x180008918  lea     rbp, [rsp-47h]
0x18000891d  sub     rsp, 90h
0x180008924  mov     rax, cs:__security_cookie
0x18000892b  xor     rax, rsp
0x18000892e  mov     [rbp+57h+var_18], rax
0x180008932  xorps   xmm0, xmm0
0x180008935  mov     rdi, r8
0x180008938  mov     rsi, rdx
0x18000893b  movups  xmmword ptr [rbp+57h+pbPassword], xmm0
0x18000893f  movups  [rbp+57h+var_28], xmm0
0x180008943  test    rcx, rcx
0x180008946  jz      loc_180008A59
0x18000894c  test    rdx, rdx
0x18000894f  jz      loc_180008A59
0x180008955  test    r8, r8
0x180008958  jz      loc_180008A59
0x18000895e  mov     rdx, rcx; Sid
0x180008961  mov     [rbp+57h+phAlgorithm], 0
0x180008969  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x18000896d  mov     r8b, 1; AllocateDestinationString
0x180008970  movups  xmmword ptr [rbp+57h+UnicodeString.Length], xmm0
0x180008974  call    cs:__imp_RtlConvertSidToUnicodeString
0x18000897a  mov     ebx, eax
0x18000897c  test    eax, eax
0x18000897e  js      loc_180008A3A
0x180008984  mov     r9d, 8; dwFlags
0x18000898a  lea     rdx, pszAlgId; "SHA256"
0x180008991  xor     r8d, r8d; pszImplementation
0x180008994  lea     rcx, [rbp+57h+phAlgorithm]; phAlgorithm
0x180008998  call    cs:__imp_BCryptOpenAlgorithmProvider
0x18000899e  mov     ebx, eax
0x1800089a0  test    eax, eax
0x1800089a2  js      loc_180008A3A
0x1800089a8  movzx   eax, [rbp+57h+UnicodeString.Length]
0x1800089ac  lea     rcx, [rbp+57h+pbPassword]
0x1800089b0  mov     r9, [rbp+57h+UnicodeString.Buffer]; pbSalt
0x1800089b4  mov     r8d, 10h; cbPassword
0x1800089ba  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x1800089c2  mov     rdx, rsi; pbPassword
0x1800089c5  mov     [rsp+0A0h+cbDerivedKey], 20h ; ' '; cbDerivedKey
0x1800089cd  mov     [rsp+0A0h+pbDerivedKey], rcx; pbDerivedKey
0x1800089d2  mov     rcx, [rbp+57h+phAlgorithm]; hPrf
0x1800089d6  mov     [rsp+0A0h+cIterations], 2710h; cIterations
0x1800089df  mov     [rsp+0A0h+cbSalt], eax; cbSalt
0x1800089e3  call    cs:__imp_BCryptDeriveKeyPBKDF2
0x1800089e9  mov     ebx, eax
0x1800089eb  test    eax, eax
0x1800089ed  js      short loc_180008A3A
0x1800089ef  mov     r9, [rbp+57h+UnicodeString.Buffer]; pbSalt
0x1800089f3  lea     rdx, [rbp+57h+pbPassword]; pbPassword
0x1800089f7  mov     rcx, [rbp+57h+phAlgorithm]; hPrf
0x1800089fb  xor     eax, eax
0x1800089fd  mov     [rsp+0A0h+dwFlags], 0; dwFlags
0x180008a05  xorps   xmm0, xmm0
0x180008a08  mov     [rsp+0A0h+cbDerivedKey], 10h; cbDerivedKey
0x180008a10  mov     r8d, 20h ; ' '; cbPassword
0x180008a16  movups  xmmword ptr [rdi], xmm0
0x180008a19  mov     [rdi+10h], eax
0x180008a1c  movzx   eax, [rbp+57h+UnicodeString.Length]
0x180008a20  mov     [rsp+0A0h+pbDerivedKey], rdi; pbDerivedKey
0x180008a25  mov     [rsp+0A0h+cIterations], 1; cIterations
0x180008a2e  mov     [rsp+0A0h+cbSalt], eax; cbSalt
0x180008a32  call    cs:__imp_BCryptDeriveKeyPBKDF2
0x180008a38  mov     ebx, eax
0x180008a3a  mov     rcx, [rbp+57h+phAlgorithm]; hAlgorithm
0x180008a3e  test    rcx, rcx
0x180008a41  jz      short loc_180008A4B
0x180008a43  xor     edx, edx; dwFlags
0x180008a45  call    cs:__imp_BCryptCloseAlgorithmProvider
0x180008a4b  lea     rcx, [rbp+57h+UnicodeString]; UnicodeString
0x180008a4f  call    cs:__imp_RtlFreeUnicodeString
0x180008a55  mov     eax, ebx
0x180008a57  jmp     short loc_180008A5E
0x180008a59  mov     eax, 0C000000Dh
0x180008a5e  mov     rcx, [rbp+57h+var_18]
0x180008a62  xor     rcx, rsp; StackCookie
0x180008a65  call    __security_check_cookie
0x180008a6a  mov     rbx, [rsp+0A0h+arg_18]
0x180008a72  add     rsp, 90h
0x180008a79  pop     rdi
0x180008a7a  pop     rsi
0x180008a7b  pop     rbp
0x180008a7c  retn
```
