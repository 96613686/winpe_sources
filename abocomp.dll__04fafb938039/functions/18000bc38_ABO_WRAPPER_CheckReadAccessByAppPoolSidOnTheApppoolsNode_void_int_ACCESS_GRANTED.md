# ABO_WRAPPER::CheckReadAccessByAppPoolSidOnTheApppoolsNode(void *,int *,ACCESS_GRANTED *)

- ea: `0x18000bc38`
- end: `0x18000be55`
- name: `?CheckReadAccessByAppPoolSidOnTheApppoolsNode@ABO_WRAPPER@@AEAAJPEAXPEAHPEAW4ACCESS_GRANTED@@@Z`
- size: `541`
- prototype: `int(ABO_WRAPPER *__hidden this, void *, int *, enum ACCESS_GRANTED *)`
- caller_count: `1`
- callee_count: `4`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18000baec`

## callees

- `0x18000341a`
- `0x180003426`
- `0x180003460`
- `0x18000bc38`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd48`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd3d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bd48`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000bd2f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000bdd9`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000bd2f`
- `api-ms-win-security-lsalookup-l2-1-0!LookupAccountSidW` at `0x18000bdd9`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000bd70`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000bd8b`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000bd70`
- `iisutil!?Resize@STRU@@QEAAJK@Z` at `0x18000bd8b`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000bc93`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000bcc3`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000bc93`
- `iisutil!?QueryCCH@STRU@@QEBAKXZ` at `0x18000bcc3`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bc89`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bcb8`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bc89`
- `iisutil!??0STRU@@QEAA@PEAGK@Z` at `0x18000bcb8`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000be26`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000be30`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000be26`
- `iisutil!??1STRU@@QEAA@XZ` at `0x18000be30`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bcf6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bd03`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bda0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bdad`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bdf3`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bcf6`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bd03`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bda0`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bdad`
- `iisutil!?QueryStr@STRU@@QEAAPEAGXZ` at `0x18000bdf3`

## pseudocode

```c
__int64 __fastcall ABO_WRAPPER::CheckReadAccessByAppPoolSidOnTheApppoolsNode(
        ABO_WRAPPER *this,
        void *a2,
        int *a3,
        enum ACCESS_GRANTED *a4)
{
  signed int v7; // edi
  WCHAR *ReferencedDomainName; // rbx
  WCHAR *Str; // rax
  signed int LastError; // eax
  WCHAR *v11; // rbx
  WCHAR *v12; // rax
  const wchar_t *v13; // rax
  DWORD cchReferencedDomainName; // [rsp+40h] [rbp-C0h] BYREF
  DWORD cchName; // [rsp+44h] [rbp-BCh] BYREF
  enum _SID_NAME_USE peUse; // [rsp+48h] [rbp-B8h] BYREF
  _BYTE v18[56]; // [rsp+50h] [rbp-B0h] BYREF
  _BYTE v19[56]; // [rsp+88h] [rbp-78h] BYREF
  unsigned __int16 v20[64]; // [rsp+C0h] [rbp-40h] BYREF
  unsigned __int16 v21[64]; // [rsp+140h] [rbp+40h] BYREF

  memset_0(v20, 0, sizeof(v20));
  STRU::STRU((STRU *)v19, v20, 0x40u);
  cchName = STRU::QueryCCH((STRU *)v19);
  memset_0(v21, 0, sizeof(v21));
  STRU::STRU((STRU *)v18, v21, 0x40u);
  peUse = 0;
  cchReferencedDomainName = STRU::QueryCCH((STRU *)v18);
  if ( !a2 || !a4 )
  {
    v7 = -2147024809;
    goto LABEL_15;
  }
  v7 = 0;
  *a3 = 0;
  *(_DWORD *)a4 = 3;
  ReferencedDomainName = STRU::QueryStr((STRU *)v18);
  Str = STRU::QueryStr((STRU *)v19);
  if ( LookupAccountSidW(0, a2, Str, &cchName, ReferencedDomainName, &cchReferencedDomainName, &peUse) )
    goto LABEL_18;
  if ( GetLastError() != 122 )
    goto LABEL_5;
  v7 = STRU::Resize((STRU *)v19, 2 * cchName);
  if ( v7 < 0 )
    goto LABEL_15;
  v7 = STRU::Resize((STRU *)v18, 2 * cchReferencedDomainName);
  if ( v7 < 0 )
    goto LABEL_15;
  v11 = STRU::QueryStr((STRU *)v18);
  v12 = STRU::QueryStr((STRU *)v19);
  if ( LookupAccountSidW(0, a2, v12, &cchName, v11, &cchReferencedDomainName, &peUse) )
  {
LABEL_18:
    if ( peUse == SidTypeWellKnownGroup && (v13 = STRU::QueryStr((STRU *)v18), !wcscmp_0(v13, L"IIS APPPOOL")) )
      *(_DWORD *)a4 = 2;
    else
      *(_DWORD *)a4 = 3;
  }
  else
  {
LABEL_5:
    LastError = GetLastError();
    v7 = LastError;
    if ( LastError > 0 )
      v7 = (unsigned __int16)LastError | 0x80070000;
  }
LABEL_15:
  STRU::~STRU((STRU *)v18);
  STRU::~STRU((STRU *)v19);
  return (unsigned int)v7;
}

```

## disassembly

```asm
0x18000bc38  push    rbp
0x18000bc3a  push    rbx
0x18000bc3b  push    rsi
0x18000bc3c  push    rdi
0x18000bc3d  push    r14
0x18000bc3f  lea     rbp, [rsp-0D0h]
0x18000bc47  sub     rsp, 1D0h
0x18000bc4e  mov     rax, cs:__security_cookie
0x18000bc55  xor     rax, rsp
0x18000bc58  mov     [rbp+0F0h+var_30], rax
0x18000bc5f  mov     rbx, r8
0x18000bc62  lea     rcx, [rbp+0F0h+var_130]; void *
0x18000bc66  mov     r14, rdx
0x18000bc69  mov     r8d, 80h; Size
0x18000bc6f  xor     edx, edx; Val
0x18000bc71  mov     rsi, r9
0x18000bc74  call    memset_0
0x18000bc79  mov     edi, 40h ; '@'
0x18000bc7e  lea     rdx, [rbp+0F0h+var_130]
0x18000bc82  mov     r8d, edi
0x18000bc85  lea     rcx, [rbp+0F0h+var_168]
0x18000bc89  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000bc8f  lea     rcx, [rbp+0F0h+var_168]
0x18000bc93  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000bc99  xor     edx, edx; Val
0x18000bc9b  lea     r8d, [rdi+40h]; Size
0x18000bc9f  lea     rcx, [rbp+0F0h+var_B0]; void *
0x18000bca3  mov     [rsp+1F0h+cchName], eax
0x18000bca7  call    memset_0
0x18000bcac  mov     r8d, edi
0x18000bcaf  lea     rdx, [rbp+0F0h+var_B0]
0x18000bcb3  lea     rcx, [rsp+1F0h+var_1A0]
0x18000bcb8  call    cs:__imp_??0STRU@@QEAA@PEAGK@Z; STRU::STRU(ushort *,ulong)
0x18000bcbe  lea     rcx, [rsp+1F0h+var_1A0]
0x18000bcc3  call    cs:__imp_?QueryCCH@STRU@@QEBAKXZ; STRU::QueryCCH(void)
0x18000bcc9  mov     [rsp+1F0h+var_1A8], 0
0x18000bcd1  mov     [rsp+1F0h+var_1B0], eax
0x18000bcd5  test    r14, r14
0x18000bcd8  jz      loc_18000BE1C
0x18000bcde  test    rsi, rsi
0x18000bce1  jz      loc_18000BE1C
0x18000bce7  xor     edi, edi
0x18000bce9  lea     rcx, [rsp+1F0h+var_1A0]
0x18000bcee  mov     [rbx], edi
0x18000bcf0  mov     dword ptr [rsi], 3
0x18000bcf6  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bcfc  lea     rcx, [rbp+0F0h+var_168]
0x18000bd00  mov     rbx, rax
0x18000bd03  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bd09  lea     rcx, [rsp+1F0h+var_1A8]
0x18000bd0e  mov     rdx, r14; Sid
0x18000bd11  mov     [rsp+1F0h+peUse], rcx; peUse
0x18000bd16  lea     r9, [rsp+1F0h+cchName]; cchName
0x18000bd1b  lea     rcx, [rsp+1F0h+var_1B0]
0x18000bd20  mov     r8, rax; Name
0x18000bd23  mov     [rsp+1F0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18000bd28  xor     ecx, ecx; lpSystemName
0x18000bd2a  mov     [rsp+1F0h+ReferencedDomainName], rbx; ReferencedDomainName
0x18000bd2f  call    cs:__imp_LookupAccountSidW
0x18000bd35  test    eax, eax
0x18000bd37  jnz     loc_18000BDE7
0x18000bd3d  call    cs:__imp_GetLastError
0x18000bd43  cmp     eax, 7Ah ; 'z'
0x18000bd46  jz      short loc_18000BD66
0x18000bd48  call    cs:__imp_GetLastError
0x18000bd4e  mov     edi, eax
0x18000bd50  test    eax, eax
0x18000bd52  jle     loc_18000BE21
0x18000bd58  movzx   edi, ax
0x18000bd5b  or      edi, 80070000h
0x18000bd61  jmp     loc_18000BE21
0x18000bd66  mov     edx, [rsp+1F0h+cchName]
0x18000bd6a  lea     rcx, [rbp+0F0h+var_168]
0x18000bd6e  add     edx, edx
0x18000bd70  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000bd76  mov     edi, eax
0x18000bd78  test    eax, eax
0x18000bd7a  js      loc_18000BE21
0x18000bd80  mov     edx, [rsp+1F0h+var_1B0]
0x18000bd84  lea     rcx, [rsp+1F0h+var_1A0]
0x18000bd89  add     edx, edx
0x18000bd8b  call    cs:__imp_?Resize@STRU@@QEAAJK@Z; STRU::Resize(ulong)
0x18000bd91  mov     edi, eax
0x18000bd93  test    eax, eax
0x18000bd95  js      loc_18000BE21
0x18000bd9b  lea     rcx, [rsp+1F0h+var_1A0]
0x18000bda0  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bda6  lea     rcx, [rbp+0F0h+var_168]
0x18000bdaa  mov     rbx, rax
0x18000bdad  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bdb3  lea     rcx, [rsp+1F0h+var_1A8]
0x18000bdb8  mov     rdx, r14; Sid
0x18000bdbb  mov     [rsp+1F0h+peUse], rcx; peUse
0x18000bdc0  lea     r9, [rsp+1F0h+cchName]; cchName
0x18000bdc5  lea     rcx, [rsp+1F0h+var_1B0]
0x18000bdca  mov     r8, rax; Name
0x18000bdcd  mov     [rsp+1F0h+cchReferencedDomainName], rcx; cchReferencedDomainName
0x18000bdd2  xor     ecx, ecx; lpSystemName
0x18000bdd4  mov     [rsp+1F0h+ReferencedDomainName], rbx; ReferencedDomainName
0x18000bdd9  call    cs:__imp_LookupAccountSidW
0x18000bddf  test    eax, eax
0x18000bde1  jz      loc_18000BD48
0x18000bde7  cmp     [rsp+1F0h+var_1A8], 5
0x18000bdec  jnz     short loc_18000BE14
0x18000bdee  lea     rcx, [rsp+1F0h+var_1A0]
0x18000bdf3  call    cs:__imp_?QueryStr@STRU@@QEAAPEAGXZ; STRU::QueryStr(void)
0x18000bdf9  mov     rcx, rax; String1
0x18000bdfc  lea     rdx, aIisApppool; "IIS APPPOOL"
0x18000be03  call    wcscmp_0
0x18000be08  test    eax, eax
0x18000be0a  jnz     short loc_18000BE14
0x18000be0c  mov     dword ptr [rsi], 2
0x18000be12  jmp     short loc_18000BE21
0x18000be14  mov     dword ptr [rsi], 3
0x18000be1a  jmp     short loc_18000BE21
0x18000be1c  mov     edi, 80070057h
0x18000be21  lea     rcx, [rsp+1F0h+var_1A0]
0x18000be26  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000be2c  lea     rcx, [rbp+0F0h+var_168]
0x18000be30  call    cs:__imp_??1STRU@@QEAA@XZ; STRU::~STRU(void)
0x18000be36  mov     eax, edi
0x18000be38  mov     rcx, [rbp+0F0h+var_30]
0x18000be3f  xor     rcx, rsp; StackCookie
0x18000be42  call    __security_check_cookie
0x18000be47  add     rsp, 1D0h
0x18000be4e  pop     r14
0x18000be50  pop     rdi
0x18000be51  pop     rsi
0x18000be52  pop     rbx
0x18000be53  pop     rbp
0x18000be54  retn
```
