# TokenUtility::_RemoveAttributesForLowILToken(void *)

- ea: `0x180032588`
- end: `0x180032732`
- name: `?_RemoveAttributesForLowILToken@TokenUtility@@AEAAXPEAX@Z`
- size: `426`
- prototype: `void(TokenUtility *__hidden this, void *)`
- caller_count: `1`
- callee_count: `5`
- tags: `broker_com_uri`

## callers

- `0x180030a60`

## callees

- `0x180002d40`
- `0x180003a0c`
- `0x18001cf80`
- `0x18001d0a0`
- `0x180032588`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003269c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003269c`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180032692`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800326e3`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x180032692`
- `api-ms-win-security-base-l1-1-0!SetTokenInformation` at `0x1800326e3`

## string_xrefs

- `0x1800326b9`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x1800326f9`: `onecoreuap\printscan\print\printscanbroker\class\tokenutility.cpp`
- `0x1800326ed`: `SetTokenInformation (TokenChildProcessFlags) failed!`
- `0x1800326b2`: `SetTokenInformation (TokenSecurityAttributes) failed!`

## pseudocode

```c
void __fastcall TokenUtility::_RemoveAttributesForLowILToken(TokenUtility *this, void *a2)
{
  __int64 v3; // rbx
  unsigned int v4; // eax
  const char *v5; // [rsp+20h] [rbp-89h]
  const char *v6; // [rsp+28h] [rbp-81h]
  int v7; // [rsp+30h] [rbp-79h] BYREF
  int v8; // [rsp+34h] [rbp-75h] BYREF
  int v9; // [rsp+38h] [rbp-71h] BYREF
  _BYTE v10[12]; // [rsp+3Ch] [rbp-6Dh]
  _QWORD TokenInformation[3]; // [rsp+48h] [rbp-61h] BYREF
  _QWORD v12[2]; // [rsp+60h] [rbp-49h] BYREF
  __int16 v13; // [rsp+70h] [rbp-39h]
  int v14; // [rsp+78h] [rbp-31h]
  __int64 v15; // [rsp+80h] [rbp-29h]
  __int64 v16; // [rsp+88h] [rbp-21h]
  const WCHAR *v17; // [rsp+90h] [rbp-19h]
  __int16 v18; // [rsp+98h] [rbp-11h]
  int v19; // [rsp+A0h] [rbp-9h]
  __int64 v20; // [rsp+A8h] [rbp-1h]
  __int64 v21; // [rsp+B0h] [rbp+7h]
  const wchar_t *v22; // [rsp+B8h] [rbp+Fh]
  __int16 v23; // [rsp+C0h] [rbp+17h]
  int v24; // [rsp+C8h] [rbp+1Fh]
  __int64 v25; // [rsp+D0h] [rbp+27h]
  wil::details::in1diag3 *retaddr; // [rsp+108h] [rbp+5Fh]

  v7 = 3;
  memset_0(v12, 0, 0x78u);
  v12[0] = 1310738;
  v12[1] = L"WIN://PKG";
  v13 = 2;
  v17 = L"WIN://SYSAPPID";
  v15 = 0;
  v22 = L"WIN://PKGHOSTID";
  v3 = 0;
  v14 = 0;
  TokenInformation[0] = &v9;
  TokenInformation[1] = &v7;
  v16 = 1966108;
  v18 = 3;
  v20 = 0;
  v19 = 0;
  v21 = 2097182;
  v23 = 2;
  v25 = 0;
  v24 = 0;
  *(_DWORD *)&v10[8] = 0;
  v9 = 1;
  *(_QWORD *)v10 = 1;
  while ( (unsigned int)v3 < 3 )
  {
    *(_QWORD *)&v10[4] = &v12[5 * v3];
    if ( !SetTokenInformation(a2, TokenSecurityAttributes, TokenInformation, 0x10u) && GetLastError() != 1168 )
      wil::details::in1diag3::Throw_GetLastErrorMsg(
        retaddr,
        (void *)0x154,
        (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
        "SetTokenInformation (TokenSecurityAttributes) failed!",
        v5);
    v3 = (unsigned int)(v3 + 1);
  }
  v8 = 0;
  v4 = SetTokenInformation(a2, MaxTokenInfoClass|TokenOwner, &v8, 4u);
  wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(
    retaddr,
    (void *)0x15C,
    (unsigned int)"onecoreuap\\printscan\\print\\printscanbroker\\class\\tokenutility.cpp",
    (const char *)v4,
    (int)"SetTokenInformation (TokenChildProcessFlags) failed!",
    v6);
}

```

## disassembly

```asm
0x180032588  mov     [rsp-8+arg_0], rbx
0x18003258d  mov     [rsp-8+arg_10], rdi
0x180032592  push    rbp
0x180032593  push    r14
0x180032595  push    r15
0x180032597  lea     rbp, [rsp-47h]
0x18003259c  sub     rsp, 0F0h
0x1800325a3  mov     rax, cs:__security_cookie
0x1800325aa  xor     rax, rsp
0x1800325ad  mov     [rbp+57h+var_20], rax
0x1800325b1  mov     r14d, 3
0x1800325b7  lea     rcx, [rbp+57h+var_A0]; void *
0x1800325bb  mov     rdi, rdx
0x1800325be  mov     [rbp+57h+var_D0], r14d
0x1800325c2  xor     edx, edx; Val
0x1800325c4  lea     r8d, [r14+75h]; Size
0x1800325c8  call    memset_0
0x1800325cd  lea     rax, aWinPkg; "WIN://PKG"
0x1800325d4  mov     [rbp+57h+var_A0], 140012h
0x1800325dc  mov     [rbp+57h+var_98], rax
0x1800325e0  lea     r8d, [r14-1]
0x1800325e4  lea     rax, aWinSysappid; "WIN://SYSAPPID"
0x1800325eb  mov     [rbp+57h+var_90], r8w
0x1800325f0  mov     [rbp+57h+var_70], rax
0x1800325f4  lea     r15d, [r14-2]
0x1800325f8  lea     rax, aWinPkghostid; "WIN://PKGHOSTID"
0x1800325ff  mov     [rbp+57h+var_80], 0
0x180032607  mov     [rbp+57h+var_48], rax
0x18003260b  xor     ebx, ebx
0x18003260d  lea     rax, [rbp+57h+var_C8]
0x180032611  mov     [rbp+57h+var_88], 0
0x180032618  mov     [rbp+57h+TokenInformation], rax
0x18003261c  lea     rax, [rbp+57h+var_D0]
0x180032620  mov     [rbp+57h+var_B0], rax
0x180032624  mov     [rbp+57h+var_78], 1E001Ch
0x18003262c  mov     [rbp+57h+var_68], r14w
0x180032631  mov     [rbp+57h+var_58], 0
0x180032639  mov     [rbp+57h+var_60], 0
0x180032640  mov     [rbp+57h+var_50], 20001Eh
0x180032648  mov     [rbp+57h+var_40], r8w
0x18003264d  mov     [rbp+57h+var_30], 0
0x180032655  mov     [rbp+57h+var_38], 0
0x18003265c  mov     [rbp+57h+var_C0], 0
0x180032664  mov     [rbp+57h+var_C8], r15d
0x180032668  mov     [rbp+57h+var_C4], r15d
0x18003266c  cmp     ebx, r14d
0x18003266f  jnb     short loc_1800326CB
0x180032671  mov     r9d, 10h; TokenInformationLength
0x180032677  lea     rcx, [rbx+rbx*4]
0x18003267b  lea     rax, [rbp+57h+var_A0]
0x18003267f  lea     rax, [rax+rcx*8]
0x180032683  mov     rcx, rdi; TokenHandle
0x180032686  lea     r8, [rbp+57h+TokenInformation]; TokenInformation
0x18003268a  mov     [rbp+57h+var_C0], rax
0x18003268e  lea     edx, [r9+17h]; TokenInformationClass
0x180032692  call    cs:__imp_SetTokenInformation
0x180032698  test    eax, eax
0x18003269a  jnz     short loc_1800326A9
0x18003269c  call    cs:__imp_GetLastError
0x1800326a2  cmp     eax, 490h
0x1800326a7  jnz     short loc_1800326AE
0x1800326a9  add     ebx, r15d
0x1800326ac  jmp     short loc_18003266C
0x1800326ae  mov     rcx, [rbp+5Fh]; this
0x1800326b2  lea     r9, aSettokeninform; "SetTokenInformation (TokenSecurityAttri"...
0x1800326b9  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x1800326c0  mov     edx, 154h; void *
0x1800326c5  call    ?Throw_GetLastErrorMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::Throw_GetLastErrorMsg(void *,uint,char const *,char const *,...)
0x1800326cb  mov     r9d, 4; TokenInformationLength
0x1800326d1  mov     [rbp+57h+var_CC], 0
0x1800326d8  lea     r8, [rbp+57h+var_CC]; TokenInformation
0x1800326dc  mov     rcx, rdi; TokenHandle
0x1800326df  lea     edx, [r9+29h]; TokenInformationClass
0x1800326e3  call    cs:__imp_SetTokenInformation
0x1800326e9  mov     rcx, [rbp+5Fh]; this
0x1800326ed  lea     rdx, aSettokeninform_0; "SetTokenInformation (TokenChildProcessF"...
0x1800326f4  mov     qword ptr [rsp+100h+var_E0], rdx; int
0x1800326f9  lea     r8, aOnecoreuapPrin_5; "onecoreuap\\printscan\\print\\printscan"...
0x180032700  mov     edx, 15Ch; void *
0x180032705  mov     r9d, eax; char *
0x180032708  call    ?Throw_IfWin32BoolFalseMsg@in1diag3@details@wil@@YAHPEAXIPEBDH1ZZ; wil::details::in1diag3::Throw_IfWin32BoolFalseMsg(void *,uint,char const *,int,char const *,...)
0x18003270d  mov     rcx, [rbp+57h+var_20]
0x180032711  xor     rcx, rsp; StackCookie
0x180032714  call    __security_check_cookie
0x180032719  lea     r11, [rsp+100h+var_10]
0x180032721  mov     rbx, [r11+20h]
0x180032725  mov     rdi, [r11+30h]
0x180032729  mov     rsp, r11
0x18003272c  pop     r15
0x18003272e  pop     r14
0x180032730  pop     rbp
0x180032731  retn
```
