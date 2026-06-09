# PrintCore::TokenHelpers::GetUserSidFromToken(void *,void * *)

- ea: `0x180046a70`
- end: `0x180046c14`
- name: `?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXPEAPEAX@Z`
- size: `420`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180048158`

## callees

- `0x180046a70`
- `0x18004c474`
- `0x18004c4e8`
- `0x18004c5c4`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180046aee`
- `KERNEL32!GetLastError` at `0x180046aee`
- `KERNEL32!LocalFree` at `0x180046bf1`
- `KERNEL32!LocalFree` at `0x180046bf1`
- `KERNEL32!LocalAlloc` at `0x180046b2c`
- `KERNEL32!LocalAlloc` at `0x180046b9e`
- `KERNEL32!LocalAlloc` at `0x180046b2c`
- `KERNEL32!LocalAlloc` at `0x180046b9e`
- `ADVAPI32!CopySid` at `0x180046bba`
- `ADVAPI32!CopySid` at `0x180046bba`
- `ADVAPI32!GetLengthSid` at `0x180046b8c`
- `ADVAPI32!GetLengthSid` at `0x180046b8c`
- `ADVAPI32!GetTokenInformation` at `0x180046ab1`
- `ADVAPI32!GetTokenInformation` at `0x180046b58`
- `ADVAPI32!GetTokenInformation` at `0x180046ab1`
- `ADVAPI32!GetTokenInformation` at `0x180046b58`

## string_xrefs

- `0x180046b05`: `GetTokenInformation (size) failed!`
- `0x180046ac7`: `GetTokenInformation succeeded with an empty buffer!`
- `0x180046add`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180046b15`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180046b78`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180046bda`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180046bcb`: `Failed to copy user SID!`
- `0x180046b69`: `GetTokenInformation (token) failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintCore::TokenHelpers::GetUserSidFromToken(HANDLE TokenHandle, void **a2)
{
  BOOL TokenInformation; // eax
  char v5; // al
  DWORD LastError; // eax
  PSID *v7; // rdi
  unsigned int v8; // eax
  SIZE_T LengthSid; // rbx
  HLOCAL v10; // r14
  unsigned int v11; // eax
  const char *v12; // r9
  __int64 result; // rax
  char *v14; // [rsp+28h] [rbp-30h]
  char *v15; // [rsp+28h] [rbp-30h]
  char *v16; // [rsp+28h] [rbp-30h]
  wil::details::in1diag3 *retaddr; // [rsp+58h] [rbp+0h]
  SIZE_T uBytes; // [rsp+68h] [rbp+10h] BYREF
  PSID *v19; // [rsp+70h] [rbp+18h]
  HLOCAL v20; // [rsp+78h] [rbp+20h]

  *a2 = 0;
  LODWORD(uBytes) = 0;
  TokenInformation = GetTokenInformation(TokenHandle, TokenUser, 0, 0, (PDWORD)&uBytes);
  v5 = TokenInformation;
  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xC0,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)0x8000FFFFLL,
      v5,
      (int)"GetTokenInformation succeeded with an empty buffer!",
      (const char *)0xFFFFFFFFFFFFFFFELL);
    LastError = GetLastError();
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0xC2,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)(LastError != 122),
      (void *)"GetTokenInformation (size) failed!",
      v14);
    v7 = (PSID *)LocalAlloc(0, (unsigned int)uBytes);
    v19 = v7;
    v8 = GetTokenInformation(TokenHandle, TokenUser, v7, uBytes, (PDWORD)&uBytes);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xC5,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)v8,
      (void *)"GetTokenInformation (token) failed!",
      v15);
    LengthSid = GetLengthSid(*v7);
    v10 = LocalAlloc(0, LengthSid);
    v20 = v10;
    v11 = CopySid(LengthSid, v10, *v7);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xC9,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)v11,
      (void *)"Failed to copy user SID!",
      v16);
    *a2 = v10;
    LocalFree(v7);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xCF,
                           (int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
                           v12);
  }
  return result;
}

```

## disassembly

```asm
0x180046a70  mov     rax, rsp
0x180046a73  push    rsi
0x180046a74  push    rdi
0x180046a75  push    r14
0x180046a77  sub     rsp, 40h
0x180046a7b  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180046a83  mov     [rax+8], rbx
0x180046a87  mov     rsi, rdx
0x180046a8a  mov     rbx, rcx
0x180046a8d  mov     qword ptr [rdx], 0
0x180046a94  mov     dword ptr [rax+10h], 0
0x180046a9b  lea     rax, [rax+10h]
0x180046a9f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180046aa4  xor     r9d, r9d; TokenInformationLength
0x180046aa7  xor     r8d, r8d; TokenInformation
0x180046aaa  lea     r14d, [r9+1]
0x180046aae  mov     edx, r14d; TokenInformationClass
0x180046ab1  call    cs:__imp_GetTokenInformation
0x180046ab8  nop     dword ptr [rax+rax+00h]
0x180046abd  test    eax, eax
0x180046abf  setnz   al
0x180046ac2  mov     rcx, [rsp+58h]; this
0x180046ac7  lea     rdx, aGettokeninform; "GetTokenInformation succeeded with an e"...
0x180046ace  mov     [rsp+58h+var_30], rdx; char *
0x180046ad3  mov     byte ptr [rsp+58h+ReturnLength], al; int
0x180046ad7  mov     r9d, 8000FFFFh; char *
0x180046add  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180046ae4  mov     edx, 0C0h; void *
0x180046ae9  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180046aee  call    cs:__imp_GetLastError
0x180046af5  nop     dword ptr [rax+rax+00h]
0x180046afa  cmp     eax, 7Ah ; 'z'
0x180046afd  setnz   al
0x180046b00  mov     rcx, [rsp+58h]; this
0x180046b05  lea     rdx, aGettokeninform_0; "GetTokenInformation (size) failed!"
0x180046b0c  mov     [rsp+58h+ReturnLength], rdx; bool
0x180046b11  movzx   r9d, al; char *
0x180046b15  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180046b1c  mov     edx, 0C2h; void *
0x180046b21  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180046b26  mov     edx, dword ptr [rsp+58h+uBytes]; uBytes
0x180046b2a  xor     ecx, ecx; uFlags
0x180046b2c  call    cs:__imp_LocalAlloc
0x180046b33  nop     dword ptr [rax+rax+00h]
0x180046b38  mov     rdi, rax
0x180046b3b  mov     [rsp+58h+arg_10], rax
0x180046b40  lea     rax, [rsp+58h+uBytes]
0x180046b45  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180046b4a  mov     r9d, dword ptr [rsp+58h+uBytes]; TokenInformationLength
0x180046b4f  mov     r8, rdi; TokenInformation
0x180046b52  mov     edx, r14d; TokenInformationClass
0x180046b55  mov     rcx, rbx; TokenHandle
0x180046b58  call    cs:__imp_GetTokenInformation
0x180046b5f  nop     dword ptr [rax+rax+00h]
0x180046b64  mov     rcx, [rsp+58h]; this
0x180046b69  lea     rdx, aGettokeninform_1; "GetTokenInformation (token) failed!"
0x180046b70  mov     [rsp+58h+ReturnLength], rdx; __int64
0x180046b75  mov     r9d, eax; char *
0x180046b78  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180046b7f  mov     edx, 0C5h; void *
0x180046b84  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180046b89  mov     rcx, [rdi]; pSid
0x180046b8c  call    cs:__imp_GetLengthSid
0x180046b93  nop     dword ptr [rax+rax+00h]
0x180046b98  mov     ebx, eax
0x180046b9a  mov     edx, eax; uBytes
0x180046b9c  xor     ecx, ecx; uFlags
0x180046b9e  call    cs:__imp_LocalAlloc
0x180046ba5  nop     dword ptr [rax+rax+00h]
0x180046baa  mov     r14, rax
0x180046bad  mov     [rsp+58h+arg_18], rax
0x180046bb2  mov     r8, [rdi]; pSourceSid
0x180046bb5  mov     rdx, rax; pDestinationSid
0x180046bb8  mov     ecx, ebx; nDestinationSidLength
0x180046bba  call    cs:__imp_CopySid
0x180046bc1  nop     dword ptr [rax+rax+00h]
0x180046bc6  mov     rcx, [rsp+58h]; this
0x180046bcb  lea     rdx, aFailedToCopyUs; "Failed to copy user SID!"
0x180046bd2  mov     [rsp+58h+ReturnLength], rdx; __int64
0x180046bd7  mov     r9d, eax; char *
0x180046bda  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180046be1  mov     edx, 0C9h; void *
0x180046be6  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180046beb  mov     [rsi], r14
0x180046bee  mov     rcx, rdi; hMem
0x180046bf1  call    cs:__imp_LocalFree
0x180046bf8  nop     dword ptr [rax+rax+00h]
0x180046bfd  xor     eax, eax
0x180046bff  jmp     short loc_180046C05
0x180046c01  mov     eax, dword ptr [rsp+58h+uBytes]
0x180046c05  mov     rbx, [rsp+58h+arg_0]
0x180046c0a  add     rsp, 40h
0x180046c0e  pop     r14
0x180046c10  pop     rdi
0x180046c11  pop     rsi
0x180046c12  retn
```
