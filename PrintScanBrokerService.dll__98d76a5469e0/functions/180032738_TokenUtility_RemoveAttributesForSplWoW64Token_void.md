# TokenUtility::_RemoveAttributesForSplWoW64Token(void *)

- ea: `0x180032738`
- end: `0x1800327e6`
- name: `?_RemoveAttributesForSplWoW64Token@TokenUtility@@AEAAXPEAX@Z`
- size: `174`
- prototype: `void(TokenUtility *__hidden this, void *)`
- caller_count: `1`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x180030cb0`

## callees

- `0x18001d0a0`

## import_xrefs

- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180032770`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800327b5`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180032770`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800327b5`

## string_xrefs

- `0x180032787`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x1800327cc`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x1800327c0`: `SetTokenInformation (TokenChildProcessFlags) failed!`
- `0x18003277b`: `SetTokenInformation (TokenSecurityAttributes) failed!`

## pseudocode

```c
void __fastcall TokenUtility::_RemoveAttributesForSplWoW64Token(TokenUtility *this, void *a2)
{
  unsigned int v3; // eax
  unsigned int v4; // eax
  const char *v5; // [rsp+28h] [rbp-20h]
  const char *v6; // [rsp+28h] [rbp-20h]
  _QWORD v7[3]; // [rsp+30h] [rbp-18h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+48h] [rbp+0h]
  int v9; // [rsp+50h] [rbp+8h] BYREF
  int v10; // [rsp+54h] [rbp+Ch]
  int TokenInformation; // [rsp+60h] [rbp+18h] BYREF

  v10 = HIDWORD(this);
  v9 = 1;
  v7[0] = 0;
  v7[1] = &v9;
  v3 = SetTokenInformation(a2, TokenSecurityAttributes, v7, 0x10u);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x11E,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v3,
    (int)"SetTokenInformation (TokenSecurityAttributes) failed!",
    v5);
  TokenInformation = 0;
  v4 = SetTokenInformation(a2, MaxTokenInfoClass|TokenOwner, &TokenInformation, 4u);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x122,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v4,
    (int)"SetTokenInformation (TokenChildProcessFlags) failed!",
    v6);
}

```

## disassembly

```asm
0x180032738  mov     r11, rsp
0x18003273b  mov     [r11+8], rcx
0x18003273f  push    rbx
0x180032740  sub     rsp, 40h
0x180032744  mov     rbx, rdx
0x180032747  mov     [rsp+48h+arg_0], 1
0x18003274f  mov     r9d, 10h; TokenInformationLength
0x180032755  mov     qword ptr [r11-18h], 0
0x18003275d  lea     rax, [r11+8]
0x180032761  mov     rcx, rbx; TokenHandle
0x180032764  lea     r8, [r11-18h]; TokenInformation
0x180032768  mov     [r11-10h], rax
0x18003276c  lea     edx, [r9+17h]; TokenInformationClass
0x180032770  call    cs:__imp_SetTokenInformation
0x180032776  mov     rcx, [rsp+48h]; this
0x18003277b  lea     rdx, aSettokeninform; "SetTokenInformation (TokenSecurityAttri"...
0x180032782  mov     qword ptr [rsp+48h+var_28], rdx; int
0x180032787  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x18003278e  mov     edx, 11Eh; void *
0x180032793  mov     r9d, eax; char *
0x180032796  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18003279b  mov     r9d, 4; TokenInformationLength
0x1800327a1  mov     [rsp+48h+TokenInformation], 0
0x1800327a9  lea     r8, [rsp+48h+TokenInformation]; TokenInformation
0x1800327ae  mov     rcx, rbx; TokenHandle
0x1800327b1  lea     edx, [r9+29h]; TokenInformationClass
0x1800327b5  call    cs:__imp_SetTokenInformation
0x1800327bb  mov     rcx, [rsp+48h]; this
0x1800327c0  lea     rdx, aSettokeninform_0; "SetTokenInformation (TokenChildProcessF"...
0x1800327c7  mov     qword ptr [rsp+48h+var_28], rdx; int
0x1800327cc  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x1800327d3  mov     edx, 122h; void *
0x1800327d8  mov     r9d, eax; char *
0x1800327db  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x1800327e0  add     rsp, 40h
0x1800327e4  pop     rbx
0x1800327e5  retn
```
