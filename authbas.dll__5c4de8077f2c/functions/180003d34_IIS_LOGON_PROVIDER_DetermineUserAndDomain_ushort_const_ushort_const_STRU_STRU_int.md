# IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)

- ea: `0x180003d34`
- end: `0x180003fc1`
- name: `?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z`
- size: `653`
- prototype: `int(IIS_LOGON_PROVIDER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct STRU *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x18000485c`

## callees

- `0x180003d34`
- `0x180005b30`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180003dd6`
- `msvcrt!wcspbrk` at `0x180003dd6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ee3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003e59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ec8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180003ee3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003f01`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003f28`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003f4c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003f01`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003f28`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180003f4c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f5c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f66`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f74`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f7e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f8c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f96`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f5c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f66`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f74`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f7e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f8c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180003f96`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003e6b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003e7e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003e6b`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180003e7e`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003f33`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180003f33`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180003e4b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180003ebe`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180003e4b`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180003ebe`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::DetermineUserAndDomain(
        IIS_LOGON_PROVIDER *this,
        const unsigned __int16 *a2,
        unsigned __int16 *a3,
        struct STRU *a4,
        struct STRU *a5,
        int *a6)
{
  int v9; // r15d
  wchar_t *v10; // rax
  wchar_t *v11; // rbx
  unsigned __int16 v12; // ax
  signed int v13; // eax
  unsigned int v14; // ebx
  signed int LastError; // eax
  const unsigned __int16 *v16; // rbx
  __int64 v17; // r8
  STRU *v18; // rcx
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-79h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-75h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-71h] BYREF
  struct STRU *v23; // [rsp+50h] [rbp-69h]
  _QWORD v24[4]; // [rsp+58h] [rbp-61h] BYREF
  LPWSTR ReferencedDomainName; // [rsp+78h] [rbp-41h]
  unsigned int v26; // [rsp+80h] [rbp-39h]
  __int16 v27; // [rsp+84h] [rbp-35h]
  _QWORD v28[4]; // [rsp+88h] [rbp-31h] BYREF
  PSID Sid; // [rsp+A8h] [rbp-11h]
  DWORD v30; // [rsp+B0h] [rbp-9h]
  __int16 v31; // [rsp+B4h] [rbp-5h]

  Sid = v28;
  v23 = a4;
  v28[0] = 0;
  v31 = 256;
  v24[0] = 0;
  ReferencedDomainName = (LPWSTR)v24;
  v30 = 32;
  v9 = 1;
  v26 = 32;
  v27 = 256;
  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( a4 && a5 && a6 )
  {
    v10 = wcspbrk(a2, L"/\\");
    v11 = v10;
    if ( v10 )
    {
      v17 = v10 - a2;
      if ( (_DWORD)v17 )
        LastError = STRU::Copy(a5, a2, v17);
      else
        LastError = STRU::Copy(a5, L".");
      if ( LastError < 0 )
        goto LABEL_28;
      v16 = v11 + 1;
    }
    else
    {
      v9 = 0;
      if ( !a3 || (v12 = *a3) == 0 )
      {
        v12 = *(_WORD *)this;
        a3 = (unsigned __int16 *)this;
      }
      if ( v12 == 92 && !a3[1] )
      {
        cbSid = v30;
        cchReferencedDomainName = v26 >> 1;
        if ( !LookupAccountNameW(0, a2, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        {
          if ( GetLastError() != 122
            || !BUFFER::Resize((BUFFER *)v28, cbSid)
            || !BUFFER::Resize((BUFFER *)v24, 2 * cchReferencedDomainName) )
          {
            LastError = GetLastError();
            if ( LastError > 0 )
              LastError = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_28;
          }
          cbSid = v30;
          cchReferencedDomainName = v26 >> 1;
          if ( !LookupAccountNameW(0, a2, Sid, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
          {
            v13 = GetLastError();
            v14 = v13;
            if ( v13 > 0 )
              v14 = (unsigned __int16)v13 | 0x80070000;
            goto LABEL_29;
          }
        }
        a3 = ReferencedDomainName;
      }
      LastError = STRU::Copy(a5, a3);
      if ( LastError < 0 )
      {
LABEL_28:
        v14 = LastError;
LABEL_29:
        BUFFER::~BUFFER((BUFFER *)v24);
        BUFFER::~BUFFER((BUFFER *)v28);
        return v14;
      }
      v16 = a2;
    }
    v18 = v23;
    *a6 = v9;
    LastError = STRU::Copy(v18, v16);
    if ( LastError < 0 )
      goto LABEL_28;
    BUFFER::~BUFFER((BUFFER *)v24);
    BUFFER::~BUFFER((BUFFER *)v28);
    return 0;
  }
  else
  {
    BUFFER::~BUFFER((BUFFER *)v24);
    BUFFER::~BUFFER((BUFFER *)v28);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180003d34  push    rbp
0x180003d36  push    rbx
0x180003d37  push    rsi
0x180003d38  push    rdi
0x180003d39  push    r12
0x180003d3b  push    r13
0x180003d3d  push    r14
0x180003d3f  push    r15
0x180003d41  lea     rbp, [rsp-0Fh]
0x180003d46  sub     rsp, 0C8h
0x180003d4d  mov     rax, cs:__security_cookie
0x180003d54  xor     rax, rsp
0x180003d57  mov     [rbp+47h+var_48], rax
0x180003d5b  mov     r14, [rbp+47h+arg_20]
0x180003d5f  mov     r12, rcx
0x180003d62  mov     r13, [rbp+47h+arg_28]
0x180003d66  lea     rcx, [rbp+47h+var_78]
0x180003d6a  mov     rdi, r8
0x180003d6d  mov     [rbp+47h+Sid], rcx
0x180003d71  xor     r8d, r8d
0x180003d74  mov     [rbp+47h+var_B0], r9
0x180003d78  mov     [rbp+47h+var_78], r8
0x180003d7c  mov     rsi, rdx
0x180003d7f  mov     [rbp+47h+var_4C], 100h
0x180003d85  lea     rcx, [rbp+47h+var_A8]
0x180003d89  mov     [rbp+47h+var_A8], r8
0x180003d8d  mov     [rbp+47h+var_88], rcx
0x180003d91  lea     edx, [r8+20h]
0x180003d95  mov     [rbp+47h+var_50], edx
0x180003d98  lea     r15d, [r8+1]
0x180003d9c  mov     [rbp+47h+var_80], edx
0x180003d9f  mov     [rbp+47h+var_7C], 100h
0x180003da5  mov     [rbp+47h+cbSid], r8d
0x180003da9  mov     [rbp+47h+var_C0], r8d
0x180003dad  mov     [rbp+47h+var_B8], r8d
0x180003db1  test    r9, r9
0x180003db4  jz      loc_180003F88
0x180003dba  test    r14, r14
0x180003dbd  jz      loc_180003F88
0x180003dc3  test    r13, r13
0x180003dc6  jz      loc_180003F88
0x180003dcc  lea     rdx, asc_1800082E4; "/\\"
0x180003dd3  mov     rcx, rsi; String
0x180003dd6  call    cs:__imp_wcspbrk
0x180003ddc  mov     rbx, rax
0x180003ddf  test    rax, rax
0x180003de2  jnz     loc_180003F10
0x180003de8  xor     r15d, r15d
0x180003deb  test    rdi, rdi
0x180003dee  jz      short loc_180003DF8
0x180003df0  movzx   eax, word ptr [rdi]
0x180003df3  test    ax, ax
0x180003df6  jnz     short loc_180003E00
0x180003df8  movzx   eax, word ptr [r12]
0x180003dfd  mov     rdi, r12
0x180003e00  cmp     ax, 5Ch ; '\'
0x180003e04  jnz     loc_180003EFB
0x180003e0a  cmp     [rdi+2], r15w
0x180003e0f  jnz     loc_180003EFB
0x180003e15  mov     eax, [rbp+47h+var_50]
0x180003e18  lea     rcx, [rbp+47h+var_B8]
0x180003e1c  mov     r8, [rbp+47h+Sid]; Sid
0x180003e20  lea     r9, [rbp+47h+cbSid]; cbSid
0x180003e24  mov     [rsp+100h+peUse], rcx; peUse
0x180003e29  mov     rdx, rsi; lpAccountName
0x180003e2c  mov     [rbp+47h+cbSid], eax
0x180003e2f  lea     rcx, [rbp+47h+var_C0]
0x180003e33  mov     eax, [rbp+47h+var_80]
0x180003e36  shr     eax, 1
0x180003e38  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180003e3d  xor     ecx, ecx; lpSystemName
0x180003e3f  mov     [rbp+47h+var_C0], eax
0x180003e42  mov     rax, [rbp+47h+var_88]
0x180003e46  mov     [rsp+100h+ReferencedDomainName], rax; ReferencedDomainName
0x180003e4b  call    cs:__imp_LookupAccountNameW
0x180003e51  test    eax, eax
0x180003e53  jnz     loc_180003EF7
0x180003e59  call    cs:__imp_GetLastError
0x180003e5f  cmp     eax, 7Ah ; 'z'
0x180003e62  jnz     short loc_180003EE3
0x180003e64  mov     edx, [rbp+47h+cbSid]
0x180003e67  lea     rcx, [rbp+47h+var_78]
0x180003e6b  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003e71  test    al, al
0x180003e73  jz      short loc_180003EE3
0x180003e75  mov     edx, [rbp+47h+var_C0]
0x180003e78  lea     rcx, [rbp+47h+var_A8]
0x180003e7c  add     edx, edx
0x180003e7e  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180003e84  test    al, al
0x180003e86  jz      short loc_180003EE3
0x180003e88  mov     eax, [rbp+47h+var_50]
0x180003e8b  lea     rcx, [rbp+47h+var_B8]
0x180003e8f  mov     r8, [rbp+47h+Sid]; Sid
0x180003e93  lea     r9, [rbp+47h+cbSid]; cbSid
0x180003e97  mov     [rsp+100h+peUse], rcx; peUse
0x180003e9c  mov     rdx, rsi; lpAccountName
0x180003e9f  mov     [rbp+47h+cbSid], eax
0x180003ea2  lea     rcx, [rbp+47h+var_C0]
0x180003ea6  mov     eax, [rbp+47h+var_80]
0x180003ea9  shr     eax, 1
0x180003eab  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180003eb0  xor     ecx, ecx; lpSystemName
0x180003eb2  mov     [rbp+47h+var_C0], eax
0x180003eb5  mov     rax, [rbp+47h+var_88]
0x180003eb9  mov     [rsp+100h+ReferencedDomainName], rax; ReferencedDomainName
0x180003ebe  call    cs:__imp_LookupAccountNameW
0x180003ec4  test    eax, eax
0x180003ec6  jnz     short loc_180003EF7
0x180003ec8  call    cs:__imp_GetLastError
0x180003ece  mov     ebx, eax
0x180003ed0  test    eax, eax
0x180003ed2  jle     loc_180003F58
0x180003ed8  movzx   ebx, ax
0x180003edb  or      ebx, 80070000h
0x180003ee1  jmp     short loc_180003F58
0x180003ee3  call    cs:__imp_GetLastError
0x180003ee9  test    eax, eax
0x180003eeb  jle     short loc_180003F56
0x180003eed  movzx   eax, ax
0x180003ef0  or      eax, 80070000h
0x180003ef5  jmp     short loc_180003F56
0x180003ef7  mov     rdi, [rbp+47h+var_88]
0x180003efb  mov     rdx, rdi
0x180003efe  mov     rcx, r14
0x180003f01  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003f07  test    eax, eax
0x180003f09  js      short loc_180003F56
0x180003f0b  mov     rbx, rsi
0x180003f0e  jmp     short loc_180003F41
0x180003f10  mov     r8, rbx
0x180003f13  mov     rcx, r14
0x180003f16  sub     r8, rsi
0x180003f19  sar     r8, 1
0x180003f1c  test    r8d, r8d
0x180003f1f  jnz     short loc_180003F30
0x180003f21  lea     rdx, asc_1800082EC; "."
0x180003f28  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003f2e  jmp     short loc_180003F39
0x180003f30  mov     rdx, rsi
0x180003f33  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180003f39  test    eax, eax
0x180003f3b  js      short loc_180003F56
0x180003f3d  add     rbx, 2
0x180003f41  mov     rcx, [rbp+47h+var_B0]
0x180003f45  mov     rdx, rbx
0x180003f48  mov     [r13+0], r15d
0x180003f4c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180003f52  test    eax, eax
0x180003f54  jns     short loc_180003F70
0x180003f56  mov     ebx, eax
0x180003f58  lea     rcx, [rbp+47h+var_A8]
0x180003f5c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003f62  lea     rcx, [rbp+47h+var_78]
0x180003f66  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003f6c  mov     eax, ebx
0x180003f6e  jmp     short loc_180003FA1
0x180003f70  lea     rcx, [rbp+47h+var_A8]
0x180003f74  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003f7a  lea     rcx, [rbp+47h+var_78]
0x180003f7e  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003f84  xor     eax, eax
0x180003f86  jmp     short loc_180003FA1
0x180003f88  lea     rcx, [rbp+47h+var_A8]
0x180003f8c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003f92  lea     rcx, [rbp+47h+var_78]
0x180003f96  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180003f9c  mov     eax, 80070057h
0x180003fa1  mov     rcx, [rbp+47h+var_48]
0x180003fa5  xor     rcx, rsp; StackCookie
0x180003fa8  call    __security_check_cookie
0x180003fad  add     rsp, 0C8h
0x180003fb4  pop     r15
0x180003fb6  pop     r14
0x180003fb8  pop     r13
0x180003fba  pop     r12
0x180003fbc  pop     rdi
0x180003fbd  pop     rsi
0x180003fbe  pop     rbx
0x180003fbf  pop     rbp
0x180003fc0  retn
```
