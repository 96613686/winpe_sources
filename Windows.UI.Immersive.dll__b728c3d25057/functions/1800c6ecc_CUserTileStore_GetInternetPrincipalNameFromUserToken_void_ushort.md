# CUserTileStore::_GetInternetPrincipalNameFromUserToken(void *,ushort * *)

- ea: `0x1800c6ecc`
- end: `0x1800c7062`
- name: `?_GetInternetPrincipalNameFromUserToken@CUserTileStore@@AEAAJPEAXPEAPEAG@Z`
- size: `406`
- prototype: `int(CUserTileStore *__hidden this, void *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800c6d24`

## callees

- `0x18003aa84`
- `0x180050ba0`
- `0x180051524`
- `0x1800c6ecc`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c6f2a`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x1800c6f2a`
- `ntdll!RtlNtStatusToDosError` at `0x1800c6fe1`
- `ntdll!RtlNtStatusToDosError` at `0x1800c6fe1`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800c702b`
- `api-ms-win-shcore-obsolete-l1-1-0!SHStrDupW` at `0x1800c702b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800c6f86`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x1800c6f86`
- `netutils!NetApiBufferFree` at `0x1800c7038`
- `netutils!NetApiBufferFree` at `0x1800c7038`
- `samcli!NetUserGetInfo` at `0x1800c6fb5`
- `samcli!NetUserGetInfo` at `0x1800c6fb5`

## pseudocode

```c
__int64 __fastcall CUserTileStore::_GetInternetPrincipalNameFromUserToken(
        CUserTileStore *this,
        void *a2,
        unsigned __int16 **a3)
{
  signed int Error; // ebx
  DWORD Info; // eax
  unsigned int i; // ecx
  NTSTATUS v8; // ecx
  signed int v9; // eax
  LPBYTE v10; // rcx
  __int64 v11; // r8
  __int64 v12; // rax
  HRESULT v13; // eax
  DWORD ReturnLength; // [rsp+40h] [rbp-C0h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+44h] [rbp-BCh] BYREF
  DWORD cchReferencedDomainName; // [rsp+48h] [rbp-B8h] BYREF
  DWORD cchName; // [rsp+4Ch] [rbp-B4h] BYREF
  LPBYTE bufptr; // [rsp+50h] [rbp-B0h] BYREF
  PSID TokenInformation[12]; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR Name[264]; // [rsp+C0h] [rbp-40h] BYREF
  WCHAR ReferencedDomainName[264]; // [rsp+2D0h] [rbp+1D0h] BYREF

  memset_0(TokenInformation, 0, 0x58u);
  ReturnLength = 88;
  if ( GetTokenInformation(a2, TokenUser, TokenInformation, 0x58u, &ReturnLength)
    || (Error = ResultFromKnownLastError(), Error >= 0) )
  {
    peUse = 0;
    cchName = 260;
    cchReferencedDomainName = 260;
    if ( LookupAccountSidW(
           0,
           TokenInformation[0],
           Name,
           &cchName,
           ReferencedDomainName,
           &cchReferencedDomainName,
           &peUse)
      || (Error = ResultFromKnownLastError(), Error >= 0) )
    {
      bufptr = 0;
      Info = NetUserGetInfo(0, Name, 0x18u, &bufptr);
      for ( i = 0; i < 0x7A; ++i )
      {
        if ( LODWORD(ErrorMap[i]) == Info )
        {
          v8 = HIDWORD(ErrorMap[i]);
          goto LABEL_11;
        }
      }
      v8 = -1073741595;
LABEL_11:
      v9 = RtlNtStatusToDosError(v8);
      Error = v9;
      if ( v9 > 0 )
        Error = (unsigned __int16)v9 | 0x80070000;
      if ( Error >= 0 )
      {
        v10 = bufptr;
        Error = -2147467259;
        if ( *(_DWORD *)bufptr == 1 )
        {
          v11 = *((_QWORD *)bufptr + 2);
          if ( v11 )
          {
            v12 = -1;
            do
              ++v12;
            while ( *(_WORD *)(v11 + 2 * v12) );
            if ( v12 )
            {
              v13 = SHStrDupW(*((LPCWSTR *)bufptr + 2), a3);
              v10 = bufptr;
              Error = v13;
            }
          }
        }
        NetApiBufferFree(v10);
      }
    }
  }
  return (unsigned int)Error;
}

```

## disassembly

```asm
0x1800c6ecc  mov     [rsp-8+arg_0], rbx
0x1800c6ed1  push    rbp
0x1800c6ed2  push    rsi
0x1800c6ed3  push    rdi
0x1800c6ed4  lea     rbp, [rsp-3F0h]
0x1800c6edc  sub     rsp, 4F0h
0x1800c6ee3  mov     rax, cs:__security_cookie
0x1800c6eea  xor     rax, rsp
0x1800c6eed  mov     [rbp+400h+var_20], rax
0x1800c6ef4  mov     rdi, r8
0x1800c6ef7  lea     rcx, [rsp+500h+TokenInformation]; void *
0x1800c6efc  mov     rbx, rdx
0x1800c6eff  mov     esi, 58h ; 'X'
0x1800c6f04  mov     r8d, esi; Size
0x1800c6f07  xor     edx, edx; Val
0x1800c6f09  call    memset_0
0x1800c6f0e  lea     rax, [rsp+500h+var_4C0]
0x1800c6f13  mov     [rsp+500h+var_4C0], esi
0x1800c6f17  mov     r9d, esi; TokenInformationLength
0x1800c6f1a  mov     [rsp+500h+ReturnLength], rax; ReturnLength
0x1800c6f1f  lea     r8, [rsp+500h+TokenInformation]; TokenInformation
0x1800c6f24  mov     rcx, rbx; TokenHandle
0x1800c6f27  lea     edx, [rsi-57h]; TokenInformationClass
0x1800c6f2a  call    cs:__imp_GetTokenInformation
0x1800c6f30  xor     esi, esi
0x1800c6f32  test    eax, eax
0x1800c6f34  jnz     short loc_1800C6F45
0x1800c6f36  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c6f3b  mov     ebx, eax
0x1800c6f3d  test    eax, eax
0x1800c6f3f  js      loc_1800C703E
0x1800c6f45  mov     rdx, [rsp+500h+TokenInformation]; Sid
0x1800c6f4a  lea     r9, [rsp+500h+cchName]; cchName
0x1800c6f4f  mov     eax, 104h
0x1800c6f54  mov     [rsp+500h+var_4BC], esi
0x1800c6f58  mov     [rsp+500h+cchName], eax
0x1800c6f5c  lea     r8, [rbp+400h+Name]; Name
0x1800c6f60  mov     [rsp+500h+var_4B8], eax
0x1800c6f64  xor     ecx, ecx; lpSystemName
0x1800c6f66  lea     rax, [rsp+500h+var_4BC]
0x1800c6f6b  mov     [rsp+500h+peUse], rax; peUse
0x1800c6f70  lea     rax, [rsp+500h+var_4B8]
0x1800c6f75  mov     [rsp+500h+cchReferencedDomainName], rax; cchReferencedDomainName
0x1800c6f7a  lea     rax, [rbp+400h+ReferencedDomainName]
0x1800c6f81  mov     [rsp+500h+ReturnLength], rax; ReferencedDomainName
0x1800c6f86  call    cs:__imp_LookupAccountSidW
0x1800c6f8c  test    eax, eax
0x1800c6f8e  jnz     short loc_1800C6F9F
0x1800c6f90  call    ?ResultFromKnownLastError@@YAJXZ; ResultFromKnownLastError(void)
0x1800c6f95  mov     ebx, eax
0x1800c6f97  test    eax, eax
0x1800c6f99  js      loc_1800C703E
0x1800c6f9f  lea     r9, [rsp+500h+bufptr]; bufptr
0x1800c6fa4  mov     [rsp+500h+bufptr], rsi
0x1800c6fa9  mov     r8d, 18h; level
0x1800c6faf  lea     rdx, [rbp+400h+Name]; username
0x1800c6fb3  xor     ecx, ecx; servername
0x1800c6fb5  call    cs:__imp_NetUserGetInfo
0x1800c6fbb  mov     ecx, esi
0x1800c6fbd  lea     r8, ErrorMap
0x1800c6fc4  cmp     ecx, 7Ah ; 'z'
0x1800c6fc7  jnb     short loc_1800C6FDC
0x1800c6fc9  mov     edx, ecx
0x1800c6fcb  cmp     [r8+rdx*8], eax
0x1800c6fcf  jz      short loc_1800C6FD5
0x1800c6fd1  inc     ecx
0x1800c6fd3  jmp     short loc_1800C6FC4
0x1800c6fd5  mov     ecx, [r8+rdx*8+4]
0x1800c6fda  jmp     short loc_1800C6FE1
0x1800c6fdc  mov     ecx, 0C00000E5h; Status
0x1800c6fe1  call    cs:__imp_RtlNtStatusToDosError
0x1800c6fe7  mov     ebx, eax
0x1800c6fe9  test    eax, eax
0x1800c6feb  jle     short loc_1800C6FF6
0x1800c6fed  movzx   ebx, ax
0x1800c6ff0  or      ebx, 80070000h
0x1800c6ff6  test    ebx, ebx
0x1800c6ff8  js      short loc_1800C703E
0x1800c6ffa  mov     rcx, [rsp+500h+bufptr]
0x1800c6fff  mov     ebx, 80004005h
0x1800c7004  cmp     dword ptr [rcx], 1
0x1800c7007  jnz     short loc_1800C7038
0x1800c7009  mov     r8, [rcx+10h]
0x1800c700d  test    r8, r8
0x1800c7010  jz      short loc_1800C7038
0x1800c7012  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800c7016  inc     rax
0x1800c7019  cmp     [r8+rax*2], si
0x1800c701e  jnz     short loc_1800C7016
0x1800c7020  test    rax, rax
0x1800c7023  jz      short loc_1800C7038
0x1800c7025  mov     rdx, rdi; ppwsz
0x1800c7028  mov     rcx, r8; psz
0x1800c702b  call    cs:__imp_SHStrDupW
0x1800c7031  mov     rcx, [rsp+500h+bufptr]; Buffer
0x1800c7036  mov     ebx, eax
0x1800c7038  call    cs:__imp_NetApiBufferFree
0x1800c703e  mov     eax, ebx
0x1800c7040  mov     rcx, [rbp+400h+var_20]
0x1800c7047  xor     rcx, rsp; StackCookie
0x1800c704a  call    __security_check_cookie
0x1800c704f  mov     rbx, [rsp+500h+arg_0]
0x1800c7057  add     rsp, 4F0h
0x1800c705e  pop     rdi
0x1800c705f  pop     rsi
0x1800c7060  pop     rbp
0x1800c7061  retn
```
