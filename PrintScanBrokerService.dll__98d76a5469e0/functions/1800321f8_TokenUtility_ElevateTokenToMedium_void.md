# TokenUtility::_ElevateTokenToMedium(void *)

- ea: `0x1800321f8`
- end: `0x1800322ed`
- name: `?_ElevateTokenToMedium@TokenUtility@@AEAAXPEAX@Z`
- size: `245`
- prototype: `void(TokenUtility *__hidden this, void *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x180030a60`
- `0x180030cb0`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18001d0a0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180032241`
- `api-ms-win-security-base-l1-1-0!CreateWellKnownSid` at `0x180032241`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800322a6`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800322a6`

## string_xrefs

- `0x18003225b`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x1800322c0`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x1800322b4`: `SetTokenInformation (TokenIntegrityLevel) failed!`
- `0x18003224f`: `CreateWellKnownSid failed!`

## pseudocode

```c
void __fastcall TokenUtility::_ElevateTokenToMedium(TokenUtility *this, void *a2)
{
  unsigned int WellKnownSid; // eax
  unsigned int v4; // eax
  const char *v5; // [rsp+28h] [rbp-E0h]
  const char *v6; // [rsp+28h] [rbp-E0h]
  DWORD cbSid[4]; // [rsp+30h] [rbp-D8h] BYREF
  _BYTE *TokenInformation; // [rsp+40h] [rbp-C8h] BYREF
  int v9; // [rsp+48h] [rbp-C0h]
  _BYTE pSid[80]; // [rsp+A0h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+0h]

  memset_0(pSid, 0, 0x44u);
  cbSid[0] = 68;
  WellKnownSid = CreateWellKnownSid(WinMediumLabelSid, 0, pSid, cbSid);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x10D,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)WellKnownSid,
    (int)"CreateWellKnownSid failed!",
    v5);
  memset_0(&TokenInformation, 0, 0x58u);
  v9 = 96;
  TokenInformation = pSid;
  v4 = SetTokenInformation(a2, TokenIntegrityLevel, &TokenInformation, 0x58u);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x114,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v4,
    (int)"SetTokenInformation (TokenIntegrityLevel) failed!",
    v6);
}

```

## disassembly

```asm
0x1800321f8  mov     r11, rsp
0x1800321fb  push    rbx
0x1800321fc  sub     rsp, 100h
0x180032203  mov     rax, cs:__security_cookie
0x18003220a  xor     rax, rsp
0x18003220d  mov     [rsp+108h+var_18], rax
0x180032215  mov     rbx, rdx
0x180032218  lea     rcx, [r11-68h]; void *
0x18003221c  xor     edx, edx; Val
0x18003221e  lea     r8d, [rdx+44h]; Size
0x180032222  call    memset_0
0x180032227  xor     edx, edx; DomainSid
0x180032229  mov     [rsp+108h+cbSid], 44h ; 'D'
0x180032231  lea     r9, [rsp+108h+cbSid]; cbSid
0x180032236  lea     r8, [rsp+108h+pSid]; pSid
0x18003223e  lea     ecx, [rdx+43h]; WellKnownSidType
0x180032241  call    cs:__imp_CreateWellKnownSid
0x180032247  mov     rcx, [rsp+108h]; this
0x18003224f  lea     rdx, aCreatewellknow; "CreateWellKnownSid failed!"
0x180032256  mov     qword ptr [rsp+108h+var_E8], rdx; int
0x18003225b  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180032262  mov     edx, 10Dh; void *
0x180032267  mov     r9d, eax; char *
0x18003226a  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18003226f  xor     edx, edx; Val
0x180032271  lea     rcx, [rsp+108h+TokenInformation]; void *
0x180032276  lea     r8d, [rdx+58h]; Size
0x18003227a  call    memset_0
0x18003227f  mov     r9d, 58h ; 'X'; TokenInformationLength
0x180032285  mov     [rsp+108h+var_C0], 60h ; '`'
0x18003228d  lea     rax, [rsp+108h+pSid]
0x180032295  mov     rcx, rbx; TokenHandle
0x180032298  lea     r8, [rsp+108h+TokenInformation]; TokenInformation
0x18003229d  mov     [rsp+108h+TokenInformation], rax
0x1800322a2  lea     edx, [r9-3Fh]; TokenInformationClass
0x1800322a6  call    cs:__imp_SetTokenInformation
0x1800322ac  mov     rcx, [rsp+108h]; this
0x1800322b4  lea     rdx, aSettokeninform_1; "SetTokenInformation (TokenIntegrityLeve"...
0x1800322bb  mov     qword ptr [rsp+108h+var_E8], rdx; int
0x1800322c0  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x1800322c7  mov     edx, 114h; void *
0x1800322cc  mov     r9d, eax; char *
0x1800322cf  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800322d4  mov     rcx, [rsp+108h+var_18]
0x1800322dc  xor     rcx, rsp; StackCookie
0x1800322df  call    __security_check_cookie
0x1800322e4  add     rsp, 100h
0x1800322eb  pop     rbx
0x1800322ec  retn
```
