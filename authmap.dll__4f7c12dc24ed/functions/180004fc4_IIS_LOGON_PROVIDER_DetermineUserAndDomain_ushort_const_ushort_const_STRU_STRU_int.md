# IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)

- ea: `0x180004fc4`
- end: `0x180005251`
- name: `?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z`
- size: `653`
- prototype: `__int64 __fastcall(IIS_LOGON_PROVIDER *this, const unsigned __int16 *, unsigned __int16 *, struct STRU *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180005aec`

## callees

- `0x180004fc4`
- `0x180006dd0`

## import_xrefs

- `msvcrt!wcspbrk` at `0x180005066`
- `msvcrt!wcspbrk` at `0x180005066`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005173`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800050e9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005158`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180005173`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800051c3`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x1800051c3`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005191`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800051b8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800051dc`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180005191`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800051b8`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800051dc`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800051ec`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800051f6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180005204`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000520e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000521c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180005226`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800051ec`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800051f6`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180005204`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000520e`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000521c`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180005226`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800050fb`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000510e`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x1800050fb`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000510e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800050db`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18000514e`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800050db`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x18000514e`

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
0x180004fc4  push    rbp
0x180004fc6  push    rbx
0x180004fc7  push    rsi
0x180004fc8  push    rdi
0x180004fc9  push    r12
0x180004fcb  push    r13
0x180004fcd  push    r14
0x180004fcf  push    r15
0x180004fd1  lea     rbp, [rsp-0Fh]
0x180004fd6  sub     rsp, 0C8h
0x180004fdd  mov     rax, cs:__security_cookie
0x180004fe4  xor     rax, rsp
0x180004fe7  mov     [rbp+47h+var_48], rax
0x180004feb  mov     r14, [rbp+47h+arg_20]
0x180004fef  mov     r12, rcx
0x180004ff2  mov     r13, [rbp+47h+arg_28]
0x180004ff6  lea     rcx, [rbp+47h+var_78]
0x180004ffa  mov     rdi, r8
0x180004ffd  mov     [rbp+47h+Sid], rcx
0x180005001  xor     r8d, r8d
0x180005004  mov     [rbp+47h+var_B0], r9
0x180005008  mov     [rbp+47h+var_78], r8
0x18000500c  mov     rsi, rdx
0x18000500f  mov     [rbp+47h+var_4C], 100h
0x180005015  lea     rcx, [rbp+47h+var_A8]
0x180005019  mov     [rbp+47h+var_A8], r8
0x18000501d  mov     [rbp+47h+var_88], rcx
0x180005021  lea     edx, [r8+20h]
0x180005025  mov     [rbp+47h+var_50], edx
0x180005028  lea     r15d, [r8+1]
0x18000502c  mov     [rbp+47h+var_80], edx
0x18000502f  mov     [rbp+47h+var_7C], 100h
0x180005035  mov     [rbp+47h+cbSid], r8d
0x180005039  mov     [rbp+47h+var_C0], r8d
0x18000503d  mov     [rbp+47h+var_B8], r8d
0x180005041  test    r9, r9
0x180005044  jz      loc_180005218
0x18000504a  test    r14, r14
0x18000504d  jz      loc_180005218
0x180005053  test    r13, r13
0x180005056  jz      loc_180005218
0x18000505c  lea     rdx, Control; "/\\"
0x180005063  mov     rcx, rsi; String
0x180005066  call    cs:__imp_wcspbrk
0x18000506c  mov     rbx, rax
0x18000506f  test    rax, rax
0x180005072  jnz     loc_1800051A0
0x180005078  xor     r15d, r15d
0x18000507b  test    rdi, rdi
0x18000507e  jz      short loc_180005088
0x180005080  movzx   eax, word ptr [rdi]
0x180005083  test    ax, ax
0x180005086  jnz     short loc_180005090
0x180005088  movzx   eax, word ptr [r12]
0x18000508d  mov     rdi, r12
0x180005090  cmp     ax, 5Ch ; '\'
0x180005094  jnz     loc_18000518B
0x18000509a  cmp     [rdi+2], r15w
0x18000509f  jnz     loc_18000518B
0x1800050a5  mov     eax, [rbp+47h+var_50]
0x1800050a8  lea     rcx, [rbp+47h+var_B8]
0x1800050ac  mov     r8, [rbp+47h+Sid]; Sid
0x1800050b0  lea     r9, [rbp+47h+cbSid]; cbSid
0x1800050b4  mov     [rsp+100h+peUse], rcx; peUse
0x1800050b9  mov     rdx, rsi; lpAccountName
0x1800050bc  mov     [rbp+47h+cbSid], eax
0x1800050bf  lea     rcx, [rbp+47h+var_C0]
0x1800050c3  mov     eax, [rbp+47h+var_80]
0x1800050c6  shr     eax, 1
0x1800050c8  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x1800050cd  xor     ecx, ecx; lpSystemName
0x1800050cf  mov     [rbp+47h+var_C0], eax
0x1800050d2  mov     rax, [rbp+47h+var_88]
0x1800050d6  mov     [rsp+100h+ReferencedDomainName], rax; ReferencedDomainName
0x1800050db  call    cs:__imp_LookupAccountNameW
0x1800050e1  test    eax, eax
0x1800050e3  jnz     loc_180005187
0x1800050e9  call    cs:__imp_GetLastError
0x1800050ef  cmp     eax, 7Ah ; 'z'
0x1800050f2  jnz     short loc_180005173
0x1800050f4  mov     edx, [rbp+47h+cbSid]
0x1800050f7  lea     rcx, [rbp+47h+var_78]
0x1800050fb  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180005101  test    al, al
0x180005103  jz      short loc_180005173
0x180005105  mov     edx, [rbp+47h+var_C0]
0x180005108  lea     rcx, [rbp+47h+var_A8]
0x18000510c  add     edx, edx
0x18000510e  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180005114  test    al, al
0x180005116  jz      short loc_180005173
0x180005118  mov     eax, [rbp+47h+var_50]
0x18000511b  lea     rcx, [rbp+47h+var_B8]
0x18000511f  mov     r8, [rbp+47h+Sid]; Sid
0x180005123  lea     r9, [rbp+47h+cbSid]; cbSid
0x180005127  mov     [rsp+100h+peUse], rcx; peUse
0x18000512c  mov     rdx, rsi; lpAccountName
0x18000512f  mov     [rbp+47h+cbSid], eax
0x180005132  lea     rcx, [rbp+47h+var_C0]
0x180005136  mov     eax, [rbp+47h+var_80]
0x180005139  shr     eax, 1
0x18000513b  mov     [rsp+100h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x180005140  xor     ecx, ecx; lpSystemName
0x180005142  mov     [rbp+47h+var_C0], eax
0x180005145  mov     rax, [rbp+47h+var_88]
0x180005149  mov     [rsp+100h+ReferencedDomainName], rax; ReferencedDomainName
0x18000514e  call    cs:__imp_LookupAccountNameW
0x180005154  test    eax, eax
0x180005156  jnz     short loc_180005187
0x180005158  call    cs:__imp_GetLastError
0x18000515e  mov     ebx, eax
0x180005160  test    eax, eax
0x180005162  jle     loc_1800051E8
0x180005168  movzx   ebx, ax
0x18000516b  or      ebx, 80070000h
0x180005171  jmp     short loc_1800051E8
0x180005173  call    cs:__imp_GetLastError
0x180005179  test    eax, eax
0x18000517b  jle     short loc_1800051E6
0x18000517d  movzx   eax, ax
0x180005180  or      eax, 80070000h
0x180005185  jmp     short loc_1800051E6
0x180005187  mov     rdi, [rbp+47h+var_88]
0x18000518b  mov     rdx, rdi
0x18000518e  mov     rcx, r14
0x180005191  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180005197  test    eax, eax
0x180005199  js      short loc_1800051E6
0x18000519b  mov     rbx, rsi
0x18000519e  jmp     short loc_1800051D1
0x1800051a0  mov     r8, rbx
0x1800051a3  mov     rcx, r14
0x1800051a6  sub     r8, rsi
0x1800051a9  sar     r8, 1
0x1800051ac  test    r8d, r8d
0x1800051af  jnz     short loc_1800051C0
0x1800051b1  lea     rdx, asc_18000A5EC; "."
0x1800051b8  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800051be  jmp     short loc_1800051C9
0x1800051c0  mov     rdx, rsi
0x1800051c3  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x1800051c9  test    eax, eax
0x1800051cb  js      short loc_1800051E6
0x1800051cd  add     rbx, 2
0x1800051d1  mov     rcx, [rbp+47h+var_B0]
0x1800051d5  mov     rdx, rbx
0x1800051d8  mov     [r13+0], r15d
0x1800051dc  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800051e2  test    eax, eax
0x1800051e4  jns     short loc_180005200
0x1800051e6  mov     ebx, eax
0x1800051e8  lea     rcx, [rbp+47h+var_A8]
0x1800051ec  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800051f2  lea     rcx, [rbp+47h+var_78]
0x1800051f6  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800051fc  mov     eax, ebx
0x1800051fe  jmp     short loc_180005231
0x180005200  lea     rcx, [rbp+47h+var_A8]
0x180005204  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000520a  lea     rcx, [rbp+47h+var_78]
0x18000520e  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180005214  xor     eax, eax
0x180005216  jmp     short loc_180005231
0x180005218  lea     rcx, [rbp+47h+var_A8]
0x18000521c  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180005222  lea     rcx, [rbp+47h+var_78]
0x180005226  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x18000522c  mov     eax, 80070057h
0x180005231  mov     rcx, [rbp+47h+var_48]
0x180005235  xor     rcx, rsp; StackCookie
0x180005238  call    __security_check_cookie
0x18000523d  add     rsp, 0C8h
0x180005244  pop     r15
0x180005246  pop     r14
0x180005248  pop     r13
0x18000524a  pop     r12
0x18000524c  pop     rdi
0x18000524d  pop     rsi
0x18000524e  pop     rbx
0x18000524f  pop     rbp
0x180005250  retn
```
