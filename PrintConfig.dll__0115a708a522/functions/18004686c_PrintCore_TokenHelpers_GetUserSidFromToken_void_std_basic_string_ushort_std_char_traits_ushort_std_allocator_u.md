# PrintCore::TokenHelpers::GetUserSidFromToken(void *,std::basic_string<ushort,std::char_traits<ushort>,std::allocator<ushort>> &)

- ea: `0x18004686c`
- end: `0x180046a68`
- name: `?GetUserSidFromToken@TokenHelpers@PrintCore@@SAJPEAXAEAV?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@@Z`
- size: `508`
- prototype: `__int64 __fastcall(HANDLE TokenHandle, _QWORD *)`
- caller_count: `1`
- callee_count: `6`
- tags: `authz_impersonation`

## callers

- `0x1800470d4`

## callees

- `0x18000ded0`
- `0x18004686c`
- `0x18004c474`
- `0x18004c4e8`
- `0x18004c5c4`
- `0x1801b56c8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800468f5`
- `KERNEL32!GetLastError` at `0x1800468f5`
- `KERNEL32!LocalFree` at `0x180046a32`
- `KERNEL32!LocalFree` at `0x180046a47`
- `KERNEL32!LocalFree` at `0x180046a32`
- `KERNEL32!LocalFree` at `0x180046a47`
- `KERNEL32!LocalAlloc` at `0x180046933`
- `KERNEL32!LocalAlloc` at `0x180046933`
- `ADVAPI32!GetTokenInformation` at `0x1800468b8`
- `ADVAPI32!GetTokenInformation` at `0x180046964`
- `ADVAPI32!GetTokenInformation` at `0x1800468b8`
- `ADVAPI32!GetTokenInformation` at `0x180046964`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800469a9`
- `ADVAPI32!ConvertSidToStringSidW` at `0x1800469a9`

## string_xrefs

- `0x18004690c`: `GetTokenInformation (size) failed!`
- `0x1800468ce`: `GetTokenInformation succeeded with an empty buffer!`
- `0x1800468e4`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x18004691c`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x180046984`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x1800469c9`: `OneCoreUap\Internal\PrintScan\inc\TokenHelpers.h`
- `0x1800469ba`: `ConvertSidToStringSid failed!`
- `0x180046975`: `GetTokenInformation (token) failed!`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall PrintCore::TokenHelpers::GetUserSidFromToken(HANDLE TokenHandle, _QWORD *a2)
{
  char *v2; // rdi
  unsigned __int64 *v4; // rbx
  BOOL TokenInformation; // eax
  char v6; // al
  DWORD LastError; // eax
  PSID *v8; // rsi
  unsigned int v9; // eax
  unsigned int v10; // eax
  __int64 v11; // r8
  LPWSTR v12; // r9
  unsigned __int64 v13; // rdx
  __int64 v14; // rbx
  const char *v15; // r9
  __int64 result; // rax
  char *v17; // [rsp+28h] [rbp-40h]
  char *v18; // [rsp+28h] [rbp-40h]
  char *v19; // [rsp+28h] [rbp-40h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]
  DWORD TokenInformationLength; // [rsp+78h] [rbp+10h] BYREF
  LPWSTR StringSid; // [rsp+80h] [rbp+18h] BYREF
  PSID *v23; // [rsp+88h] [rbp+20h]

  v2 = (char *)a2;
  v4 = a2 + 2;
  a2[2] = 0;
  if ( a2[3] > 7u )
    a2 = (_QWORD *)*a2;
  *(_WORD *)a2 = 0;
  TokenInformationLength = 0;
  TokenInformation = GetTokenInformation(TokenHandle, TokenUser, 0, 0, &TokenInformationLength);
  v6 = TokenInformation;
  try
  {
    wil::details::in1diag3::Throw_HrIfMsg(
      retaddr,
      (void *)0xAA,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)0x8000FFFFLL,
      v6,
      (int)"GetTokenInformation succeeded with an empty buffer!",
      (const char *)0xFFFFFFFFFFFFFFFELL);
    LastError = GetLastError();
    wil::details::in1diag3::Throw_GetLastErrorIfMsg(
      retaddr,
      (void *)0xAC,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)(LastError != 122),
      (void *)"GetTokenInformation (size) failed!",
      v17);
    v8 = (PSID *)LocalAlloc(0, TokenInformationLength);
    v23 = v8;
    v9 = GetTokenInformation(TokenHandle, TokenUser, v8, TokenInformationLength, &TokenInformationLength);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xAF,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)v9,
      (void *)"GetTokenInformation (token) failed!",
      v18);
    StringSid = 0;
    v10 = ConvertSidToStringSidW(*v8, &StringSid);
    wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
      retaddr,
      (void *)0xB2,
      (unsigned int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
      (const char *)v10,
      (void *)"ConvertSidToStringSid failed!",
      v19);
    v12 = StringSid;
    v13 = -1;
    do
      ++v13;
    while ( StringSid[v13] );
    if ( v13 > *((_QWORD *)v2 + 3) )
    {
      std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,unsigned short const *>(
        (char **)v2,
        v13,
        v11,
        StringSid);
    }
    else
    {
      if ( *((_QWORD *)v2 + 3) > 7u )
        v2 = *(char **)v2;
      *v4 = v13;
      v14 = 2 * v13;
      memmove_0(v2, v12, 2 * v13);
      *(_WORD *)&v2[v14] = 0;
    }
    if ( StringSid )
      LocalFree(StringSid);
    if ( v8 )
      LocalFree(v8);
    result = 0;
  }
  catch ( ... )
  {
    return (unsigned int)wil::details::in1diag3::Return_CaughtException(
                           retaddr,
                           (void *)0xB7,
                           (int)"OneCoreUap\\Internal\\PrintScan\\inc\\TokenHelpers.h",
                           v15);
  }
  return result;
}

```

## disassembly

```asm
0x18004686c  push    rbx
0x18004686e  push    rsi
0x18004686f  push    rdi
0x180046870  push    r14
0x180046872  push    r15
0x180046874  sub     rsp, 40h
0x180046878  mov     [rsp+68h+var_38], 0FFFFFFFFFFFFFFFEh; char *
0x180046881  mov     rdi, rdx
0x180046884  mov     r14, rcx
0x180046887  lea     rbx, [rdx+10h]
0x18004688b  xor     r15d, r15d
0x18004688e  mov     [rbx], r15
0x180046891  cmp     qword ptr [rdx+18h], 7
0x180046896  jbe     short loc_18004689B
0x180046898  mov     rdx, [rdx]
0x18004689b  mov     [rdx], r15w
0x18004689f  mov     [rsp+68h+TokenInformationLength], r15d
0x1800468a4  lea     rax, [rsp+68h+TokenInformationLength]
0x1800468a9  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x1800468ae  xor     r9d, r9d; TokenInformationLength
0x1800468b1  xor     r8d, r8d; TokenInformation
0x1800468b4  lea     edx, [r9+1]; TokenInformationClass
0x1800468b8  call    cs:__imp_GetTokenInformation
0x1800468bf  nop     dword ptr [rax+rax+00h]
0x1800468c4  test    eax, eax
0x1800468c6  setnz   al
0x1800468c9  mov     rcx, [rsp+68h]; this
0x1800468ce  lea     rdx, aGettokeninform; "GetTokenInformation succeeded with an e"...
0x1800468d5  mov     [rsp+68h+var_40], rdx; char *
0x1800468da  mov     byte ptr [rsp+68h+ReturnLength], al; int
0x1800468de  mov     r9d, 8000FFFFh; char *
0x1800468e4  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x1800468eb  mov     edx, 0AAh; void *
0x1800468f0  call    ?Throw_HrIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBDJ_N1ZZ; wil::details::in1diag3::Throw_HrIfMsg(void *,uint,char const *,long,bool,char const *,...)
0x1800468f5  call    cs:__imp_GetLastError
0x1800468fc  nop     dword ptr [rax+rax+00h]
0x180046901  cmp     eax, 7Ah ; 'z'
0x180046904  setnz   al
0x180046907  mov     rcx, [rsp+68h]; this
0x18004690c  lea     rdx, aGettokeninform_0; "GetTokenInformation (size) failed!"
0x180046913  mov     [rsp+68h+ReturnLength], rdx; bool
0x180046918  movzx   r9d, al; char *
0x18004691c  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x180046923  mov     edx, 0ACh; void *
0x180046928  call    ?Throw_GetLastErrorIfMsg@in1diag3@details@wil@@YA_NPEAXIPEBD_N1ZZ; wil::details::in1diag3::Throw_GetLastErrorIfMsg(void *,uint,char const *,bool,char const *,...)
0x18004692d  mov     edx, [rsp+68h+TokenInformationLength]; uBytes
0x180046931  xor     ecx, ecx; uFlags
0x180046933  call    cs:__imp_LocalAlloc
0x18004693a  nop     dword ptr [rax+rax+00h]
0x18004693f  mov     rsi, rax
0x180046942  mov     [rsp+68h+arg_18], rax
0x18004694a  lea     rax, [rsp+68h+TokenInformationLength]
0x18004694f  mov     [rsp+68h+ReturnLength], rax; ReturnLength
0x180046954  mov     r9d, [rsp+68h+TokenInformationLength]; TokenInformationLength
0x180046959  mov     r8, rsi; TokenInformation
0x18004695c  mov     edx, 1; TokenInformationClass
0x180046961  mov     rcx, r14; TokenHandle
0x180046964  call    cs:__imp_GetTokenInformation
0x18004696b  nop     dword ptr [rax+rax+00h]
0x180046970  mov     rcx, [rsp+68h]; this
0x180046975  lea     rdx, aGettokeninform_1; "GetTokenInformation (token) failed!"
0x18004697c  mov     [rsp+68h+ReturnLength], rdx; __int64
0x180046981  mov     r9d, eax; char *
0x180046984  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x18004698b  mov     edx, 0AFh; void *
0x180046990  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x180046995  nop
0x180046996  mov     [rsp+68h+StringSid], r15
0x18004699e  lea     rdx, [rsp+68h+StringSid]; StringSid
0x1800469a6  mov     rcx, [rsi]; Sid
0x1800469a9  call    cs:__imp_ConvertSidToStringSidW
0x1800469b0  nop     dword ptr [rax+rax+00h]
0x1800469b5  mov     rcx, [rsp+68h]; this
0x1800469ba  lea     rdx, aConvertsidtost; "ConvertSidToStringSid failed!"
0x1800469c1  mov     [rsp+68h+ReturnLength], rdx; __int64
0x1800469c6  mov     r9d, eax; char *
0x1800469c9  lea     r8, aOnecoreuapInte_4; "OneCoreUap\\Internal\\PrintScan\\inc\\T"...
0x1800469d0  mov     edx, 0B2h; void *
0x1800469d5  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800469da  mov     r9, [rsp+68h+StringSid]
0x1800469e2  or      rdx, 0FFFFFFFFFFFFFFFFh
0x1800469e6  inc     rdx
0x1800469e9  cmp     [r9+rdx*2], r15w
0x1800469ee  jnz     short loc_1800469E6
0x1800469f0  cmp     rdx, [rdi+18h]
0x1800469f4  ja      short loc_180046A1C
0x1800469f6  cmp     qword ptr [rdi+18h], 7
0x1800469fb  jbe     short loc_180046A00
0x1800469fd  mov     rdi, [rdi]
0x180046a00  mov     [rbx], rdx
0x180046a03  lea     rbx, [rdx+rdx]
0x180046a07  mov     r8, rbx; Size
0x180046a0a  mov     rdx, r9; Src
0x180046a0d  mov     rcx, rdi; void *
0x180046a10  call    memmove_0
0x180046a15  mov     [rbx+rdi], r15w
0x180046a1a  jmp     short loc_180046A25
0x180046a1c  mov     rcx, rdi
0x180046a1f  call    ??$_Reallocate_for@V_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@AEAAAEAV01@_KV_lambda_b937b2caa9f02d8112e55f88cfbf4197_@@PEBG@Z; std::wstring::_Reallocate_for<_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *>(unsigned __int64,_lambda_b937b2caa9f02d8112e55f88cfbf4197_,ushort const *)
0x180046a24  nop
0x180046a25  mov     rcx, [rsp+68h+StringSid]; hMem
0x180046a2d  test    rcx, rcx
0x180046a30  jz      short loc_180046A3F
0x180046a32  call    cs:__imp_LocalFree
0x180046a39  nop     dword ptr [rax+rax+00h]
0x180046a3e  nop
0x180046a3f  test    rsi, rsi
0x180046a42  jz      short loc_180046A53
0x180046a44  mov     rcx, rsi; hMem
0x180046a47  call    cs:__imp_LocalFree
0x180046a4e  nop     dword ptr [rax+rax+00h]
0x180046a53  xor     eax, eax
0x180046a55  jmp     short loc_180046A5B
0x180046a57  mov     eax, [rsp+68h+TokenInformationLength]
0x180046a5b  add     rsp, 40h
0x180046a5f  pop     r15
0x180046a61  pop     r14
0x180046a63  pop     rdi
0x180046a64  pop     rsi
0x180046a65  pop     rbx
0x180046a66  retn
```
