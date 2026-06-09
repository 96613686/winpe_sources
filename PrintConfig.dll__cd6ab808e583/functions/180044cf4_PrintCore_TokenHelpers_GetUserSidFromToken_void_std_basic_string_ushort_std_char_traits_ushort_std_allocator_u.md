# PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x180044cf4`
- end: `0x180044ec6`
- name: `?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `466`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800454d4`

## callees

- `0x18000dadc`
- `0x180044cf4`
- `0x18004a588`
- `0x18004a5fc`
- `0x18004a6d8`
- `0x1801adb58`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180044d77`
- `KERNEL32!GetLastError` at `0x180044d77`
- `KERNEL32!LocalFree` at `0x180044e9c`
- `KERNEL32!LocalFree` at `0x180044eab`
- `KERNEL32!LocalFree` at `0x180044e9c`
- `KERNEL32!LocalFree` at `0x180044eab`
- `KERNEL32!LocalAlloc` at `0x180044daf`
- `KERNEL32!LocalAlloc` at `0x180044daf`
- `ADVAPI32!GetTokenInformation` at `0x180044d40`
- `ADVAPI32!GetTokenInformation` at `0x180044dda`
- `ADVAPI32!GetTokenInformation` at `0x180044d40`
- `ADVAPI32!GetTokenInformation` at `0x180044dda`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180044e19`
- `ADVAPI32!ConvertSidToStringSidW` at `0x180044e19`

## string_xrefs

- `0x180044d88`: `GetTokenInformation (size) failed!`
- `0x180044d50`: `GetTokenInformation succeeded with an empty buffer!`
- `0x180044d66`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180044d98`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180044df4`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180044e33`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180044e24`: `ConvertSidToStringSid failed!`
- `0x180044de5`: `GetTokenInformation (token) failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintCore::TokenHelpers::GetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  _QWORD *v2; // rdi
  unsigned __int64 *v4; // rbx
  BOOL TokenInformation; // eax
  DWORD LastError; // eax
  PSID *v7; // rsi
  unsigned int v8; // eax
  unsigned int v9; // eax
  LPWSTR v10; // r9
  unsigned __int64 v11; // rdx
  __int64 v12; // rbx
  const char *v13; // r9
  __int64 result; // rax
  int ReturnLength; // [rsp+20h] [rbp-48h]
  char *v16; // [rsp+28h] [rbp-40h]
  char *v17; // [rsp+28h] [rbp-40h]
  char *v18; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+78h] [rbp+10h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp+18h] BYREF
  PSID *v22; // [rsp+88h] [rbp+20h]

  v2 = a2;
  v4 = a2 + 2;
  a2[2] = 0;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  *(_WORD *)a2 = 0;
  TokenInformationLength = 0;
  TokenInformation = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  LOBYTE(TokenInformation) = TokenInformation;
  LOBYTE(ReturnLength) = TokenInformation;
  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xAA,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)0x8000FFFFLL,
      ReturnLength,
      (bool)"GetTokenInformation succeeded with an empty buffer!",
      (const char *)0xFFFFFFFFFFFFFFFELL);
    LastError = GetLastError();
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0xAC,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)(LastError != 122),
      (bool)"GetTokenInformation (size) failed!",
      v16);
    v7 = (PSID *)LocalAlloc(0, TokenInformationLength);
    v22 = v7;
    v8 = GetTokenInformation(TokenHandle, TokenUser, v7, TokenInformationLength, &TokenInformationLength);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xAF,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)v8,
      (__int64)"GetTokenInformation (token) failed!",
      v17);
    StringSid = 0;
    v9 = ConvertSidToStringSidW(*v7, &StringSid);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xB2,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)v9,
      (__int64)"ConvertSidToStringSid failed!",
      v18);
    v10 = StringSid;
    v11 = -1;
    do
      ++v11;
    while ( StringSid[v11] );
    if ( v11 > v2[3] )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(v2);
    }
    else
    {
      if ( v2[3] > 7u )
        v2 = (_QWORD *)*v2;
      *v4 = v11;
      v12 = 2 * v11;
      memmove_0(v2, v10, 2 * v11);
      *(_WORD *)((char *)v2 + v12) = 0;
    }
    if ( StringSid )
      LocalFree(StringSid);
    if ( v7 )
      LocalFree(v7);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB7,
                           (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
                           v13);
  }
  return result;
}

```

## disassembly

```asm
0x180044cf4  push    rbx
0x180044cf6  push    rsi
0x180044cf7  push    rdi
0x180044cf8  push    r14
0x180044cfa  push    r15
0x180044cfc  sub     rsp, 40h
0x180044d00  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh; char *
0x180044d09  mov     rdi, rdx
0x180044d0c  mov     r14, rcx
0x180044d0f  lea     rbx, [rdx+10h]
0x180044d13  xor     r15d, r15d
0x180044d16  mov     [rbx], r15
0x180044d19  cmp     qword ptr [rdx+18h], 7
0x180044d1e  jbe     short loc_180044D23
0x180044d20  mov     rdx, [rdx]
0x180044d23  mov     [rdx], r15w
0x180044d27  mov     [rsp+68h+TokenInformationLength], r15d
0x180044d2c  lea     rax, [rsp+68h+TokenInformationLength]
0x180044d31  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180044d36  xor     r9d, r9d; TokenInformationLength
0x180044d39  xor     r8d, r8d; TokenInformation
0x180044d3c  lea     edx, [r9+1]; TokenInformationClass
0x180044d40  call    cs:__imp_GetTokenInformation
0x180044d46  test    eax, eax
0x180044d48  setnz   al
0x180044d4b  mov     rcx, [rsp+68h]; this
0x180044d50  lea     rdx, aGettokeninform; "GetTokenInformation succeeded with an e"...
0x180044d57  mov     [rsp+68h+var_40], rdx; char *
0x180044d5c  mov     byte ptr [rsp+68h+ReturnLength], al; int
0x180044d60  mov     r9d, 8000FFFFh; char *
0x180044d66  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180044d6d  mov     edx, 0AAh; void *
0x180044d72  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180044d77  call    cs:__imp_GetLastError
0x180044d7d  cmp     eax, 7Ah ; 'z'
0x180044d80  setnz   al
0x180044d83  mov     rcx, [rsp+68h]; this
0x180044d88  lea     rdx, aGettokeninform_0; "GetTokenInformation (size) failed!"
0x180044d8f  mov     [rsp+68h+ReturnLength], rdx; bool
0x180044d94  movzx   r9d, al; char *
0x180044d98  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180044d9f  mov     edx, 0ACh; void *
0x180044da4  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180044da9  mov     edx, [rsp+68h+TokenInformationLength]; uBytes
0x180044dad  xor     ecx, ecx; uFlags
0x180044daf  call    cs:__imp_LocalAlloc
0x180044db5  mov     rsi, rax
0x180044db8  mov     [rsp+68h+arg_18], rax
0x180044dc0  lea     rax, [rsp+68h+TokenInformationLength]
0x180044dc5  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180044dca  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x180044dcf  mov     r8, rsi; TokenInformation
0x180044dd2  mov     edx, 1; TokenInformationClass
0x180044dd7  mov     rcx, r14; TokenHandle
0x180044dda  call    cs:__imp_GetTokenInformation
0x180044de0  mov     rcx, [rsp+68h]; this
0x180044de5  lea     rdx, aGettokeninform_1; "GetTokenInformation (token) failed!"
0x180044dec  mov     [rsp+68h+ReturnLength], rdx; __int64
0x180044df1  mov     r9d, eax; char *
0x180044df4  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180044dfb  mov     edx, 0AFh; void *
0x180044e00  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180044e05  nop
0x180044e06  mov     [rsp+68h+StringSid], r15
0x180044e0e  lea     rdx, [rsp+68h+StringSid]; StringSid
0x180044e16  mov     rcx, [rsi]; Sid
0x180044e19  call    cs:__imp_ConvertSidToStringSidW
0x180044e1f  mov     rcx, [rsp+68h]; this
0x180044e24  lea     rdx, aConvertsidtost; "ConvertSidToStringSid failed!"
0x180044e2b  mov     [rsp+68h+ReturnLength], rdx; __int64
0x180044e30  mov     r9d, eax; char *
0x180044e33  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180044e3a  mov     edx, 0B2h; void *
0x180044e3f  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180044e44  mov     r9, [rsp+68h+StringSid]
0x180044e4c  or      rdx, 0FFFFFFFFFFFFFFFFh
0x180044e50  inc     rdx
0x180044e53  cmp     [r9+rdx*2], r15w
0x180044e58  jnz     short loc_180044E50
0x180044e5a  cmp     rdx, [rdi+18h]
0x180044e5e  ja      short loc_180044E86
0x180044e60  cmp     qword ptr [rdi+18h], 7
0x180044e65  jbe     short loc_180044E6A
0x180044e67  mov     rdi, [rdi]
0x180044e6a  mov     [rbx], rdx
0x180044e6d  lea     rbx, [rdx+rdx]
0x180044e71  mov     r8, rbx; Size
0x180044e74  mov     rdx, r9; Src
0x180044e77  mov     rcx, rdi; void *
0x180044e7a  call    memmove_0
0x180044e7f  mov     [rbx+rdi], r15w
0x180044e84  jmp     short loc_180044E8F
0x180044e86  mov     rcx, rdi
0x180044e89  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180044e8e  nop
0x180044e8f  mov     rcx, [rsp+68h+StringSid]; hMem
0x180044e97  test    rcx, rcx
0x180044e9a  jz      short loc_180044EA3
0x180044e9c  call    cs:__imp_LocalFree
0x180044ea2  nop
0x180044ea3  test    rsi, rsi
0x180044ea6  jz      short loc_180044EB1
0x180044ea8  mov     rcx, rsi; hMem
0x180044eab  call    cs:__imp_LocalFree
0x180044eb1  xor     eax, eax
0x180044eb3  jmp     short loc_180044EB9
0x180044eb5  mov     eax, [rsp+68h+TokenInformationLength]
0x180044eb9  add     rsp, 40h
0x180044ebd  pop     r15
0x180044ebf  pop     r14
0x180044ec1  pop     rdi
0x180044ec2  pop     rsi
0x180044ec3  pop     rbx
0x180044ec4  retn
```
