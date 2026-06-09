# PrintCore::TokenHelpers::GetUserSidFromToken(void *,void * *)

- ea: `0x180044ecc`
- end: `0x180045040`
- name: `?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXPEAPEAX@Z`
- size: `372`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, void **)`
- caller_count: `1`
- callee_count: `4`
- tags: `file_ops, authz_impersonation`

## callers

- `0x180046450`

## callees

- `0x180044ecc`
- `0x18004a588`
- `0x18004a5fc`
- `0x18004a6d8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180044f44`
- `KERNEL32!GetLastError` at `0x180044f44`
- `KERNEL32!LocalFree` at `0x180045023`
- `KERNEL32!LocalFree` at `0x180045023`
- `KERNEL32!LocalAlloc` at `0x180044f7c`
- `KERNEL32!LocalAlloc` at `0x180044fdc`
- `KERNEL32!LocalAlloc` at `0x180044f7c`
- `KERNEL32!LocalAlloc` at `0x180044fdc`
- `ADVAPI32!CopySid` at `0x180044ff2`
- `ADVAPI32!CopySid` at `0x180044ff2`
- `ADVAPI32!GetLengthSid` at `0x180044fd0`
- `ADVAPI32!GetLengthSid` at `0x180044fd0`
- `ADVAPI32!GetTokenInformation` at `0x180044f0d`
- `ADVAPI32!GetTokenInformation` at `0x180044fa2`
- `ADVAPI32!GetTokenInformation` at `0x180044f0d`
- `ADVAPI32!GetTokenInformation` at `0x180044fa2`

## string_xrefs

- `0x180044f55`: `GetTokenInformation (size) failed!`
- `0x180044f1d`: `GetTokenInformation succeeded with an empty buffer!`
- `0x180044f33`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180044f65`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180044fbc`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x18004500c`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180044ffd`: `Failed to copy user SID!`
- `0x180044fad`: `GetTokenInformation (token) failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintCore::TokenHelpers::GetUserSidFromToken(HANDLE TokenHandle, void **a2)
{
  BOOL TokenInformation; // eax
  DWORD LastError; // eax
  PSID *v6; // rdi
  unsigned int v7; // eax
  SIZE_T LengthSid; // rbx
  HLOCAL v9; // r14
  unsigned int v10; // eax
  const char *v11; // r9
  __int64 result; // rax
  int ReturnLength; // [rsp+20h] [rbp-38h]
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
  LOBYTE(TokenInformation) = TokenInformation;
  LOBYTE(ReturnLength) = TokenInformation;
  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xC0,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)0x8000FFFFLL,
      ReturnLength,
      (bool)"GetTokenInformation succeeded with an empty buffer!",
      (const char *)0xFFFFFFFFFFFFFFFELL);
    LastError = GetLastError();
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0xC2,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)(LastError != 122),
      (bool)"GetTokenInformation (size) failed!",
      v14);
    v6 = (PSID *)LocalAlloc(0, (unsigned int)uBytes);
    v19 = v6;
    v7 = GetTokenInformation(TokenHandle, TokenUser, v6, uBytes, (PDWORD)&uBytes);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xC5,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)v7,
      (__int64)"GetTokenInformation (token) failed!",
      v15);
    LengthSid = GetLengthSid(*v6);
    v9 = LocalAlloc(0, LengthSid);
    v20 = v9;
    v10 = CopySid(LengthSid, v9, *v6);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xC9,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)v10,
      (__int64)"Failed to copy user SID!",
      v16);
    *a2 = v9;
    LocalFree(v6);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xCF,
                           (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
                           v11);
  }
  return result;
}

```

## disassembly

```asm
0x180044ecc  mov     rax, rsp
0x180044ecf  push    rsi
0x180044ed0  push    rdi
0x180044ed1  push    r14
0x180044ed3  sub     rsp, 40h
0x180044ed7  mov     qword ptr [rax-28h], 0FFFFFFFFFFFFFFFEh
0x180044edf  mov     [rax+8], rbx
0x180044ee3  mov     rsi, rdx
0x180044ee6  mov     rbx, rcx
0x180044ee9  mov     qword ptr [rdx], 0
0x180044ef0  mov     dword ptr [rax+10h], 0
0x180044ef7  lea     rax, [rax+10h]
0x180044efb  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180044f00  xor     r9d, r9d; TokenInformationLength
0x180044f03  xor     r8d, r8d; TokenInformation
0x180044f06  lea     r14d, [r9+1]
0x180044f0a  mov     edx, r14d; TokenInformationClass
0x180044f0d  call    cs:__imp_GetTokenInformation
0x180044f13  test    eax, eax
0x180044f15  setnz   al
0x180044f18  mov     rcx, [rsp+58h]; this
0x180044f1d  lea     rdx, aGettokeninform; "GetTokenInformation succeeded with an e"...
0x180044f24  mov     [rsp+58h+var_30], rdx; char *
0x180044f29  mov     byte ptr [rsp+58h+ReturnLength], al; int
0x180044f2d  mov     r9d, 8000FFFFh; char *
0x180044f33  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180044f3a  mov     edx, 0C0h; void *
0x180044f3f  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x180044f44  call    cs:__imp_GetLastError
0x180044f4a  cmp     eax, 7Ah ; 'z'
0x180044f4d  setnz   al
0x180044f50  mov     rcx, [rsp+58h]; this
0x180044f55  lea     rdx, aGettokeninform_0; "GetTokenInformation (size) failed!"
0x180044f5c  mov     [rsp+58h+ReturnLength], rdx; bool
0x180044f61  movzx   r9d, al; char *
0x180044f65  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180044f6c  mov     edx, 0C2h; void *
0x180044f71  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x180044f76  mov     edx, dword ptr [rsp+58h+uBytes]; uBytes
0x180044f7a  xor     ecx, ecx; uFlags
0x180044f7c  call    cs:__imp_LocalAlloc
0x180044f82  mov     rdi, rax
0x180044f85  mov     [rsp+58h+arg_10], rax
0x180044f8a  lea     rax, [rsp+58h+uBytes]
0x180044f8f  mov     [rsp+58h+ReturnLength], rax; ReturnLength
0x180044f94  mov     r9d, dword ptr [rsp+58h+uBytes]; TokenInformationLength
0x180044f99  mov     r8, rdi; TokenInformation
0x180044f9c  mov     edx, r14d; TokenInformationClass
0x180044f9f  mov     rcx, rbx; TokenHandle
0x180044fa2  call    cs:__imp_GetTokenInformation
0x180044fa8  mov     rcx, [rsp+58h]; this
0x180044fad  lea     rdx, aGettokeninform_1; "GetTokenInformation (token) failed!"
0x180044fb4  mov     [rsp+58h+ReturnLength], rdx; __int64
0x180044fb9  mov     r9d, eax; char *
0x180044fbc  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180044fc3  mov     edx, 0C5h; void *
0x180044fc8  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180044fcd  mov     rcx, [rdi]; pSid
0x180044fd0  call    cs:__imp_GetLengthSid
0x180044fd6  mov     ebx, eax
0x180044fd8  mov     edx, eax; uBytes
0x180044fda  xor     ecx, ecx; uFlags
0x180044fdc  call    cs:__imp_LocalAlloc
0x180044fe2  mov     r14, rax
0x180044fe5  mov     [rsp+58h+arg_18], rax
0x180044fea  mov     r8, [rdi]; pSourceSid
0x180044fed  mov     rdx, rax; pDestinationSid
0x180044ff0  mov     ecx, ebx; nDestinationSidLength
0x180044ff2  call    cs:__imp_CopySid
0x180044ff8  mov     rcx, [rsp+58h]; this
0x180044ffd  lea     rdx, aFailedToCopyUs; "Failed to copy user SID!"
0x180045004  mov     [rsp+58h+ReturnLength], rdx; __int64
0x180045009  mov     r9d, eax; char *
0x18004500c  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180045013  mov     edx, 0C9h; void *
0x180045018  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18004501d  mov     [rsi], r14
0x180045020  mov     rcx, rdi; hMem
0x180045023  call    cs:__imp_LocalFree
0x180045029  xor     eax, eax
0x18004502b  jmp     short loc_180045031
0x18004502d  mov     eax, dword ptr [rsp+58h+uBytes]
0x180045031  mov     rbx, [rsp+58h+arg_0]
0x180045036  add     rsp, 40h
0x18004503a  pop     r14
0x18004503c  pop     rdi
0x18004503d  pop     rsi
0x18004503e  retn
```
