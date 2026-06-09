# ConvertSidToString(void *,ushort *)

- ea: `0x180012b24`
- end: `0x180012cc6`
- name: `?ConvertSidToString@@YAJPEAXPEAG@Z`
- size: `418`
- prototype: `__int64 __fastcall(PSID pSid, wchar_t *Destination)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation`

## callers

- `0x18001297c`

## callees

- `0x180012b24`
- `0x18001d6c0`

## import_xrefs

- `msvcrt!swprintf_s` at `0x180012b7f`
- `msvcrt!swprintf_s` at `0x180012bec`
- `msvcrt!swprintf_s` at `0x180012c33`
- `msvcrt!swprintf_s` at `0x180012c7d`
- `msvcrt!swprintf_s` at `0x180012b7f`
- `msvcrt!swprintf_s` at `0x180012bec`
- `msvcrt!swprintf_s` at `0x180012c33`
- `msvcrt!swprintf_s` at `0x180012c7d`
- `msvcrt!wcscat_s` at `0x180012c44`
- `msvcrt!wcscat_s` at `0x180012c8e`
- `msvcrt!wcscat_s` at `0x180012c44`
- `msvcrt!wcscat_s` at `0x180012c8e`
- `msvcrt!wcscpy_s` at `0x180012b94`
- `msvcrt!wcscpy_s` at `0x180012b94`
- `ADVAPI32!GetSidSubAuthority` at `0x180012c65`
- `ADVAPI32!GetSidSubAuthority` at `0x180012c65`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180012c4d`
- `ADVAPI32!GetSidSubAuthorityCount` at `0x180012c4d`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x180012b9d`
- `ADVAPI32!GetSidIdentifierAuthority` at `0x180012b9d`
- `ADVAPI32!IsValidSid` at `0x180012b4f`
- `ADVAPI32!IsValidSid` at `0x180012b4f`

## pseudocode

```c
__int64 __fastcall ConvertSidToString(unsigned __int8 *pSid, wchar_t *Destination)
{
  PSID_IDENTIFIER_AUTHORITY SidIdentifierAuthority; // rax
  BYTE *v6; // r9
  UCHAR v7; // si
  PUCHAR SidSubAuthorityCount; // rbp
  PDWORD SidSubAuthority; // rax
  int v10; // [rsp+20h] [rbp-268h]
  int v11; // [rsp+28h] [rbp-260h]
  int v12; // [rsp+30h] [rbp-258h]
  int v13; // [rsp+38h] [rbp-250h]
  int v14; // [rsp+40h] [rbp-248h]
  wchar_t Buffer[256]; // [rsp+50h] [rbp-238h] BYREF

  if ( IsValidSid(pSid) )
  {
    swprintf_s(Buffer, 0x100u, L"S-%u-", *pSid);
    wcscpy_s(Destination, 0x104u, Buffer);
    SidIdentifierAuthority = GetSidIdentifierAuthority(pSid);
    v6 = &SidIdentifierAuthority->Value[1];
    if ( SidIdentifierAuthority->Value[0] || *v6 )
    {
      v14 = SidIdentifierAuthority->Value[5];
      v13 = SidIdentifierAuthority->Value[4];
      v12 = SidIdentifierAuthority->Value[3];
      v11 = SidIdentifierAuthority->Value[2];
      v10 = *v6;
      swprintf_s(
        Buffer,
        0x100u,
        L"0x%02hx%02hx%02hx%02hx%02hx%02hx",
        SidIdentifierAuthority->Value[0],
        v10,
        v11,
        v12,
        v13,
        v14);
    }
    else
    {
      swprintf_s(
        Buffer,
        0x100u,
        L"%lu",
        SidIdentifierAuthority->Value[5]
      + (SidIdentifierAuthority->Value[4] << 8)
      + (SidIdentifierAuthority->Value[3] << 16)
      + (SidIdentifierAuthority->Value[2] << 24));
    }
    wcscat_s(Destination, 0x104u, Buffer);
    v7 = 0;
    SidSubAuthorityCount = GetSidSubAuthorityCount(pSid);
    if ( *SidSubAuthorityCount )
    {
      do
      {
        SidSubAuthority = GetSidSubAuthority(pSid, v7);
        swprintf_s(Buffer, 0x100u, L"-%lu", *SidSubAuthority);
        wcscat_s(Destination, 0x104u, Buffer);
        ++v7;
      }
      while ( v7 < *SidSubAuthorityCount );
    }
    return 0;
  }
  else
  {
    *Destination = 0;
    return 2147943737LL;
  }
}

```

## disassembly

```asm
0x180012b24  mov     [rsp+arg_10], rbx
0x180012b29  push    rbp
0x180012b2a  push    rsi
0x180012b2b  push    rdi
0x180012b2c  push    r14
0x180012b2e  push    r15
0x180012b30  sub     rsp, 260h
0x180012b37  mov     rax, cs:__security_cookie
0x180012b3e  xor     rax, rsp
0x180012b41  mov     [rsp+288h+var_38], rax
0x180012b49  mov     rdi, rdx
0x180012b4c  mov     rbx, rcx
0x180012b4f  call    cs:__imp_IsValidSid
0x180012b55  test    eax, eax
0x180012b57  jnz     short loc_180012B66
0x180012b59  mov     [rdi], ax
0x180012b5c  mov     eax, 80070539h
0x180012b61  jmp     loc_180012C9F
0x180012b66  movzx   r9d, byte ptr [rbx]
0x180012b6a  lea     r8, aSU; "S-%u-"
0x180012b71  mov     r14d, 100h
0x180012b77  lea     rcx, [rsp+288h+Buffer]; Buffer
0x180012b7c  mov     edx, r14d; BufferCount
0x180012b7f  call    cs:__imp_swprintf_s
0x180012b85  lea     r15d, [r14+4]
0x180012b89  mov     rcx, rdi; Destination
0x180012b8c  mov     edx, r15d; SizeInWords
0x180012b8f  lea     r8, [rsp+288h+Buffer]; Source
0x180012b94  call    cs:__imp_wcscpy_s
0x180012b9a  mov     rcx, rbx; pSid
0x180012b9d  call    cs:__imp_GetSidIdentifierAuthority
0x180012ba3  mov     r8, rax
0x180012ba6  movzx   r11d, byte ptr [rax]
0x180012baa  lea     r9, [rax+1]
0x180012bae  test    r11b, r11b
0x180012bb1  jnz     short loc_180012BF4
0x180012bb3  cmp     [r9], r11b
0x180012bb6  jnz     short loc_180012BF4
0x180012bb8  movzx   ecx, byte ptr [rax+3]
0x180012bbc  mov     edx, r14d; BufferCount
0x180012bbf  movzx   r9d, byte ptr [rax+2]
0x180012bc4  movzx   eax, byte ptr [rax+4]
0x180012bc8  shl     r9d, 18h
0x180012bcc  shl     ecx, 10h
0x180012bcf  add     r9d, ecx
0x180012bd2  shl     eax, 8
0x180012bd5  add     r9d, eax
0x180012bd8  lea     rcx, [rsp+288h+Buffer]; Buffer
0x180012bdd  movzx   eax, byte ptr [r8+5]
0x180012be2  lea     r8, aLu_0; "%lu"
0x180012be9  add     r9d, eax
0x180012bec  call    cs:__imp_swprintf_s
0x180012bf2  jmp     short loc_180012C39
0x180012bf4  movzx   ecx, byte ptr [r8+4]
0x180012bf9  movzx   edx, byte ptr [r8+3]
0x180012bfe  movzx   r8d, byte ptr [r8+2]
0x180012c03  movzx   r10d, byte ptr [r9]
0x180012c07  mov     r9d, r11d
0x180012c0a  movzx   eax, byte ptr [rax+5]
0x180012c0e  mov     [rsp+288h+var_248], eax
0x180012c12  mov     [rsp+288h+var_250], ecx
0x180012c16  lea     rcx, [rsp+288h+Buffer]; Buffer
0x180012c1b  mov     [rsp+288h+var_258], edx
0x180012c1f  mov     rdx, r14; BufferCount
0x180012c22  mov     [rsp+288h+var_260], r8d
0x180012c27  lea     r8, a0x02hx02hx02hx; "0x%02hx%02hx%02hx%02hx%02hx%02hx"
0x180012c2e  mov     [rsp+288h+var_268], r10d
0x180012c33  call    cs:__imp_swprintf_s
0x180012c39  lea     r8, [rsp+288h+Buffer]; Source
0x180012c3e  mov     rdx, r15; SizeInWords
0x180012c41  mov     rcx, rdi; Destination
0x180012c44  call    cs:__imp_wcscat_s
0x180012c4a  mov     rcx, rbx; pSid
0x180012c4d  call    cs:__imp_GetSidSubAuthorityCount
0x180012c53  xor     sil, sil
0x180012c56  mov     rbp, rax
0x180012c59  cmp     [rax], sil
0x180012c5c  jbe     short loc_180012C9D
0x180012c5e  movzx   edx, sil; nSubAuthority
0x180012c62  mov     rcx, rbx; pSid
0x180012c65  call    cs:__imp_GetSidSubAuthority
0x180012c6b  lea     r8, aLu; "-%lu"
0x180012c72  mov     rdx, r14; BufferCount
0x180012c75  lea     rcx, [rsp+288h+Buffer]; Buffer
0x180012c7a  mov     r9d, [rax]
0x180012c7d  call    cs:__imp_swprintf_s
0x180012c83  lea     r8, [rsp+288h+Buffer]; Source
0x180012c88  mov     rdx, r15; SizeInWords
0x180012c8b  mov     rcx, rdi; Destination
0x180012c8e  call    cs:__imp_wcscat_s
0x180012c94  inc     sil
0x180012c97  cmp     sil, [rbp+0]
0x180012c9b  jb      short loc_180012C5E
0x180012c9d  xor     eax, eax
0x180012c9f  mov     rcx, [rsp+288h+var_38]
0x180012ca7  xor     rcx, rsp; StackCookie
0x180012caa  call    __security_check_cookie
0x180012caf  mov     rbx, [rsp+288h+arg_10]
0x180012cb7  add     rsp, 260h
0x180012cbe  pop     r15
0x180012cc0  pop     r14
0x180012cc2  pop     rdi
0x180012cc3  pop     rsi
0x180012cc4  pop     rbp
0x180012cc5  retn
```
