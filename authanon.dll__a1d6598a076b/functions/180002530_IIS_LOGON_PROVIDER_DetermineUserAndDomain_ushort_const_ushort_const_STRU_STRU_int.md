# IIS_LOGON_PROVIDER::DetermineUserAndDomain(ushort const *,ushort const *,STRU *,STRU *,int *)

- ea: `0x180002530`
- end: `0x1800027ee`
- name: `?DetermineUserAndDomain@IIS_LOGON_PROVIDER@@AEAAJPEBG0PEAVSTRU@@1PEAH@Z`
- size: `702`
- prototype: `int(IIS_LOGON_PROVIDER *__hidden this, const unsigned __int16 *, const unsigned __int16 *, struct STRU *, struct STRU *, int *)`
- caller_count: `1`
- callee_count: `2`
- tags: `file_ops, authz_impersonation, broker_com_uri`

## callers

- `0x180005354`

## callees

- `0x180002530`
- `0x180005b70`

## import_xrefs

- `msvcrt!wcspbrk` at `0x1800025b7`
- `msvcrt!wcspbrk` at `0x1800025b7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026e7`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180002642`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026d9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800026e7`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002658`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000266f`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x180002658`
- `iisutil!?Resize@BUFFER@@QEAA_NK@Z` at `0x18000266f`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800025fe`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000260b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002699`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800026a6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000273d`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800025fe`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000260b`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x180002699`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x1800026a6`
- `iisutil!?QueryPtr@BUFFER@@QEBAPEAXXZ` at `0x18000273d`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000274c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002778`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800027a5`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x18000274c`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x180002778`
- `iisutil!?Copy@STRU@@QEAAJPEBG@Z` at `0x1800027a5`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180002783`
- `iisutil!?Copy@STRU@@QEAAJPEBGK@Z` at `0x180002783`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800025e2`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800025ef`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000267d`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000268a`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800025e2`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x1800025ef`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000267d`
- `iisutil!?QuerySize@BUFFER@@QEBAKXZ` at `0x18000268a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002700`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000270a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800027b9`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800027c3`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800027d4`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800027de`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x180002700`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x18000270a`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800027b9`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800027c3`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800027d4`
- `iisutil!??1BUFFER@@QEAA@XZ` at `0x1800027de`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000256b`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180002575`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x18000256b`
- `iisutil!??0BUFFER@@QEAA@XZ` at `0x180002575`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180002634`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800026cf`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x180002634`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountNameW` at `0x1800026cf`

## pseudocode

```c
__int64 __fastcall IIS_LOGON_PROVIDER::DetermineUserAndDomain(
        IIS_LOGON_PROVIDER *this,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3,
        struct STRU *a4,
        struct STRU *a5,
        int *a6)
{
  wchar_t *v9; // rax
  wchar_t *v10; // rdi
  WCHAR *ReferencedDomainName; // rbx
  void *Ptr; // rax
  WCHAR *v13; // rbx
  void *v14; // rax
  signed int LastError; // eax
  signed int v16; // ebx
  const unsigned __int16 *v18; // rdi
  int v19; // eax
  __int64 v20; // r8
  int v21; // eax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-69h] BYREF
  DWORD cbSid; // [rsp+44h] [rbp-65h] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-61h] BYREF
  _BYTE v25[48]; // [rsp+50h] [rbp-59h] BYREF
  _BYTE v26[48]; // [rsp+80h] [rbp-29h] BYREF

  BUFFER::BUFFER((BUFFER *)v26);
  BUFFER::BUFFER((BUFFER *)v25);
  cbSid = 0;
  cchReferencedDomainName = 0;
  peUse = 0;
  if ( a4 && a5 && a6 )
  {
    v9 = wcspbrk(a2, L"/\\");
    v10 = v9;
    if ( v9 )
    {
      v20 = v9 - a2;
      if ( (_DWORD)v20 )
        v21 = STRU::Copy(a5, a2, v20);
      else
        v21 = STRU::Copy(a5, L".");
      v16 = v21;
      if ( v21 < 0 )
        goto LABEL_16;
      v18 = v10 + 1;
      v19 = 1;
    }
    else
    {
      if ( *(_WORD *)this == 92 && !*((_WORD *)this + 1) )
      {
        cbSid = BUFFER::QuerySize((BUFFER *)v26);
        cchReferencedDomainName = BUFFER::QuerySize((BUFFER *)v25) >> 1;
        ReferencedDomainName = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v25);
        Ptr = BUFFER::QueryPtr((BUFFER *)v26);
        if ( !LookupAccountNameW(0, a2, Ptr, &cbSid, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
        {
          if ( GetLastError() != 122
            || !BUFFER::Resize((BUFFER *)v26, cbSid)
            || !BUFFER::Resize((BUFFER *)v25, 2 * cchReferencedDomainName) )
          {
            LastError = GetLastError();
            v16 = LastError;
            if ( LastError <= 0 )
            {
LABEL_16:
              BUFFER::~BUFFER((BUFFER *)v25);
              BUFFER::~BUFFER((BUFFER *)v26);
              return (unsigned int)v16;
            }
LABEL_15:
            v16 = (unsigned __int16)LastError | 0x80070000;
            goto LABEL_16;
          }
          cbSid = BUFFER::QuerySize((BUFFER *)v26);
          cchReferencedDomainName = BUFFER::QuerySize((BUFFER *)v25) >> 1;
          v13 = (WCHAR *)BUFFER::QueryPtr((BUFFER *)v25);
          v14 = BUFFER::QueryPtr((BUFFER *)v26);
          if ( !LookupAccountNameW(0, a2, v14, &cbSid, v13, &cchReferencedDomainName, &peUse) )
          {
            LastError = GetLastError();
            v16 = LastError;
            if ( LastError <= 0 )
              goto LABEL_16;
            goto LABEL_15;
          }
        }
        this = (IIS_LOGON_PROVIDER *)BUFFER::QueryPtr((BUFFER *)v25);
      }
      v16 = STRU::Copy(a5, (const unsigned __int16 *)this);
      if ( v16 < 0 )
        goto LABEL_16;
      v18 = a2;
      v19 = 0;
    }
    *a6 = v19;
    v16 = STRU::Copy(a4, v18);
    if ( v16 < 0 )
      goto LABEL_16;
    BUFFER::~BUFFER((BUFFER *)v25);
    BUFFER::~BUFFER((BUFFER *)v26);
    return 0;
  }
  else
  {
    BUFFER::~BUFFER((BUFFER *)v25);
    BUFFER::~BUFFER((BUFFER *)v26);
    return 2147942487LL;
  }
}

```

## disassembly

```asm
0x180002530  push    rbp
0x180002532  push    rbx
0x180002533  push    rsi
0x180002534  push    r12
0x180002536  push    r13
0x180002538  push    r14
0x18000253a  push    r15
0x18000253c  lea     rbp, [rsp-17h]
0x180002541  sub     rsp, 0C0h
0x180002548  mov     rax, cs:__security_cookie
0x18000254f  xor     rax, rsp
0x180002552  mov     [rbp+47h+var_40], rax
0x180002556  mov     r14, [rbp+47h+arg_20]
0x18000255a  mov     rbx, rcx
0x18000255d  mov     r15, [rbp+47h+arg_28]
0x180002561  lea     rcx, [rbp+47h+var_70]
0x180002565  mov     r12, r9
0x180002568  mov     rsi, rdx
0x18000256b  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x180002571  lea     rcx, [rbp+47h+var_A0]
0x180002575  call    cs:__imp_??0BUFFER@@QEAA@XZ; BUFFER::BUFFER(void)
0x18000257b  xor     r13d, r13d
0x18000257e  mov     [rbp+47h+cbSid], r13d
0x180002582  mov     [rbp+47h+var_B0], r13d
0x180002586  mov     [rbp+47h+var_A8], r13d
0x18000258a  test    r12, r12
0x18000258d  jz      loc_1800027D0
0x180002593  test    r14, r14
0x180002596  jz      loc_1800027D0
0x18000259c  test    r15, r15
0x18000259f  jz      loc_1800027D0
0x1800025a5  lea     rdx, Control; "/\\"
0x1800025ac  mov     [rsp+0F0h+arg_10], rdi
0x1800025b4  mov     rcx, rsi; String
0x1800025b7  call    cs:__imp_wcspbrk
0x1800025bd  mov     rdi, rax
0x1800025c0  test    rax, rax
0x1800025c3  jnz     loc_180002760
0x1800025c9  cmp     word ptr [rbx], 5Ch ; '\'
0x1800025cd  jnz     loc_180002746
0x1800025d3  cmp     [rbx+2], r13w
0x1800025d8  jnz     loc_180002746
0x1800025de  lea     rcx, [rbp+47h+var_70]
0x1800025e2  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800025e8  lea     rcx, [rbp+47h+var_A0]
0x1800025ec  mov     [rbp+47h+cbSid], eax
0x1800025ef  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x1800025f5  shr     eax, 1
0x1800025f7  lea     rcx, [rbp+47h+var_A0]
0x1800025fb  mov     [rbp+47h+var_B0], eax
0x1800025fe  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180002604  lea     rcx, [rbp+47h+var_70]
0x180002608  mov     rbx, rax
0x18000260b  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180002611  lea     rcx, [rbp+47h+var_A8]
0x180002615  mov     rdx, rsi; lpAccountName
0x180002618  mov     [rsp+0F0h+peUse], rcx; peUse
0x18000261d  lea     r9, [rbp+47h+cbSid]; cbSid
0x180002621  lea     rcx, [rbp+47h+var_B0]
0x180002625  mov     r8, rax; Sid
0x180002628  mov     [rsp+0F0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18000262d  xor     ecx, ecx; lpSystemName
0x18000262f  mov     [rsp+0F0h+ReferencedDomainName], rbx; ReferencedDomainName
0x180002634  call    cs:__imp_LookupAccountNameW
0x18000263a  test    eax, eax
0x18000263c  jnz     loc_180002739
0x180002642  call    cs:__imp_GetLastError
0x180002648  cmp     eax, 7Ah ; 'z'
0x18000264b  jnz     loc_1800026E7
0x180002651  mov     edx, [rbp+47h+cbSid]
0x180002654  lea     rcx, [rbp+47h+var_70]
0x180002658  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x18000265e  test    al, al
0x180002660  jz      loc_1800026E7
0x180002666  mov     edx, [rbp+47h+var_B0]
0x180002669  lea     rcx, [rbp+47h+var_A0]
0x18000266d  add     edx, edx
0x18000266f  call    cs:__imp_?Resize@BUFFER@@QEAA_NK@Z; BUFFER::Resize(ulong)
0x180002675  test    al, al
0x180002677  jz      short loc_1800026E7
0x180002679  lea     rcx, [rbp+47h+var_70]
0x18000267d  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180002683  lea     rcx, [rbp+47h+var_A0]
0x180002687  mov     [rbp+47h+cbSid], eax
0x18000268a  call    cs:__imp_?QuerySize@BUFFER@@QEBAKXZ; BUFFER::QuerySize(void)
0x180002690  shr     eax, 1
0x180002692  lea     rcx, [rbp+47h+var_A0]
0x180002696  mov     [rbp+47h+var_B0], eax
0x180002699  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x18000269f  lea     rcx, [rbp+47h+var_70]
0x1800026a3  mov     rbx, rax
0x1800026a6  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x1800026ac  lea     rcx, [rbp+47h+var_A8]
0x1800026b0  mov     rdx, rsi; lpAccountName
0x1800026b3  mov     [rsp+0F0h+peUse], rcx; peUse
0x1800026b8  lea     r9, [rbp+47h+cbSid]; cbSid
0x1800026bc  lea     rcx, [rbp+47h+var_B0]
0x1800026c0  mov     r8, rax; Sid
0x1800026c3  mov     [rsp+0F0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x1800026c8  xor     ecx, ecx; lpSystemName
0x1800026ca  mov     [rsp+0F0h+ReferencedDomainName], rbx; ReferencedDomainName
0x1800026cf  call    cs:__imp_LookupAccountNameW
0x1800026d5  test    eax, eax
0x1800026d7  jnz     short loc_180002739
0x1800026d9  call    cs:__imp_GetLastError
0x1800026df  mov     ebx, eax
0x1800026e1  test    eax, eax
0x1800026e3  jg      short loc_1800026F3
0x1800026e5  jmp     short loc_1800026FC
0x1800026e7  call    cs:__imp_GetLastError
0x1800026ed  mov     ebx, eax
0x1800026ef  test    eax, eax
0x1800026f1  jle     short loc_1800026FC
0x1800026f3  movzx   ebx, ax
0x1800026f6  or      ebx, 80070000h
0x1800026fc  lea     rcx, [rbp+47h+var_A0]
0x180002700  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002706  lea     rcx, [rbp+47h+var_70]
0x18000270a  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x180002710  mov     eax, ebx
0x180002712  mov     rdi, [rsp+0F0h+arg_10]
0x18000271a  mov     rcx, [rbp+47h+var_40]
0x18000271e  xor     rcx, rsp; StackCookie
0x180002721  call    __security_check_cookie
0x180002726  add     rsp, 0C0h
0x18000272d  pop     r15
0x18000272f  pop     r14
0x180002731  pop     r13
0x180002733  pop     r12
0x180002735  pop     rsi
0x180002736  pop     rbx
0x180002737  pop     rbp
0x180002738  retn
0x180002739  lea     rcx, [rbp+47h+var_A0]
0x18000273d  call    cs:__imp_?QueryPtr@BUFFER@@QEBAPEAXXZ; BUFFER::QueryPtr(void)
0x180002743  mov     rbx, rax
0x180002746  mov     rdx, rbx
0x180002749  mov     rcx, r14
0x18000274c  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x180002752  mov     ebx, eax
0x180002754  test    eax, eax
0x180002756  js      short loc_1800026FC
0x180002758  mov     rdi, rsi
0x18000275b  mov     eax, r13d
0x18000275e  jmp     short loc_18000279C
0x180002760  mov     r8, rdi
0x180002763  mov     rcx, r14
0x180002766  sub     r8, rsi
0x180002769  sar     r8, 1
0x18000276c  test    r8d, r8d
0x18000276f  jnz     short loc_180002780
0x180002771  lea     rdx, asc_1800084B4; "."
0x180002778  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x18000277e  jmp     short loc_180002789
0x180002780  mov     rdx, rsi
0x180002783  call    cs:__imp_?Copy@STRU@@QEAAJPEBGK@Z; STRU::Copy(ushort const *,ulong)
0x180002789  mov     ebx, eax
0x18000278b  test    eax, eax
0x18000278d  js      loc_1800026FC
0x180002793  add     rdi, 2
0x180002797  mov     eax, 1
0x18000279c  mov     rdx, rdi
0x18000279f  mov     [r15], eax
0x1800027a2  mov     rcx, r12
0x1800027a5  call    cs:__imp_?Copy@STRU@@QEAAJPEBG@Z; STRU::Copy(ushort const *)
0x1800027ab  lea     rcx, [rbp+47h+var_A0]
0x1800027af  mov     ebx, eax
0x1800027b1  test    eax, eax
0x1800027b3  js      loc_180002700
0x1800027b9  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800027bf  lea     rcx, [rbp+47h+var_70]
0x1800027c3  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800027c9  xor     eax, eax
0x1800027cb  jmp     loc_180002712
0x1800027d0  lea     rcx, [rbp+47h+var_A0]
0x1800027d4  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800027da  lea     rcx, [rbp+47h+var_70]
0x1800027de  call    cs:__imp_??1BUFFER@@QEAA@XZ; BUFFER::~BUFFER(void)
0x1800027e4  mov     eax, 80070057h
0x1800027e9  jmp     loc_18000271A
```
