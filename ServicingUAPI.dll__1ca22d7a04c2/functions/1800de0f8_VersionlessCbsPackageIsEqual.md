# VersionlessCbsPackageIsEqual

- ea: `0x1800de0f8`
- end: `0x1800de35f`
- name: `VersionlessCbsPackageIsEqual`
- size: `615`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800cea18`

## callees

- `0x1800031d0`
- `0x1800062b8`
- `0x18000fe74`
- `0x18003ddc8`
- `0x180067014`
- `0x1800de0f8`
- `0x1800ebb74`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800de264`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800de28a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800de2b0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800de2d6`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800de264`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800de28a`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800de2b0`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800de2d6`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
char VersionlessCbsPackageIsEqual()
{
  int v0; // eax
  int v1; // eax
  int v2; // eax
  int v3; // eax
  LPCWCH v5; // [rsp+48h] [rbp-19h] BYREF
  LPCWCH lpString2; // [rsp+50h] [rbp-11h] BYREF
  LPCWCH lpString1; // [rsp+58h] [rbp-9h] BYREF
  LPCWCH v8; // [rsp+60h] [rbp-1h] BYREF
  LPCWCH v9; // [rsp+68h] [rbp+7h] BYREF
  LPCWCH v10; // [rsp+70h] [rbp+Fh] BYREF
  LPCWCH v11; // [rsp+78h] [rbp+17h] BYREF
  LPCWCH v12; // [rsp+80h] [rbp+1Fh] BYREF
  wchar_t *v13[2]; // [rsp+88h] [rbp+27h] BYREF
  wchar_t *v14; // [rsp+98h] [rbp+37h] BYREF
  wchar_t *v15; // [rsp+A0h] [rbp+3Fh] BYREF

  v13[1] = (wchar_t *)-2LL;
  v15 = 0;
  v0 = SczAllocFromSz(&v15);
  if ( v0 < 0 )
  {
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v0, "Failed to allocate memory");
LABEL_15:
    if ( v15 )
      operator delete(v15 - 4);
    return 0;
  }
  lpString1 = 0;
  v9 = 0;
  v11 = 0;
  v12 = 0;
  v5 = 0;
  v1 = ShredStringIdIntoAttributes(v15, 0x7Eu, &lpString1, &v9, &v12, &v11, &v5);
  if ( v1 < 0 )
  {
    LogAdapter::TraceAtLevelHr<long,AutoScz>(3, (unsigned int)v1, "Failed to shred keyform: {0}", &v15);
    goto LABEL_15;
  }
  v14 = 0;
  v2 = SczAllocFromSz(&v14);
  if ( v2 < 0 )
  {
    LogAdapter::TraceAtLevelHr<long,>(3, (unsigned int)v2, "Failed to allocate memory");
    goto LABEL_13;
  }
  lpString2 = 0;
  v8 = 0;
  v10 = 0;
  v5 = 0;
  v13[0] = 0;
  v3 = ShredStringIdIntoAttributes(v14, 0x7Eu, &lpString2, &v8, &v5, &v10, (const wchar_t **)v13);
  if ( v3 < 0 )
  {
    LogAdapter::TraceAtLevelHr<long,AutoScz>(3, (unsigned int)v3, "Failed to shred keyform: {0}", &v14);
    goto LABEL_13;
  }
  if ( CompareStringOrdinal(lpString1, -1, lpString2, -1, 1) != 2
    || CompareStringOrdinal(v9, -1, v8, -1, 1) != 2
    || CompareStringOrdinal(v11, -1, v10, -1, 1) != 2
    || CompareStringOrdinal(v12, -1, v5, -1, 1) != 2 )
  {
LABEL_13:
    if ( v14 )
    {
      operator delete(v14 - 4);
      v14 = 0;
    }
    goto LABEL_15;
  }
  if ( v14 )
  {
    operator delete(v14 - 4);
    v14 = 0;
  }
  if ( v15 )
    operator delete(v15 - 4);
  return 1;
}

```

## disassembly

```asm
0x1800de0f8  mov     rax, rsp
0x1800de0fb  push    rbp
0x1800de0fc  lea     rbp, [rax-5Fh]
0x1800de100  sub     rsp, 0B0h
0x1800de107  mov     [rbp+57h+var_28], 0FFFFFFFFFFFFFFFEh
0x1800de10f  mov     [rax+18h], rbx
0x1800de113  mov     [rax+20h], rdi
0x1800de117  mov     rax, cs:__security_cookie
0x1800de11e  xor     rax, rsp
0x1800de121  mov     [rbp+57h+var_10], rax
0x1800de125  mov     rbx, rdx
0x1800de128  xor     edi, edi
0x1800de12a  mov     [rbp+57h+var_18], rdi
0x1800de12e  mov     rdx, [rcx+8]
0x1800de132  lea     rcx, [rbp+57h+var_18]
0x1800de136  call    SczAllocFromSz
0x1800de13b  test    eax, eax
0x1800de13d  jns     short loc_1800DE155
0x1800de13f  lea     r8, aFailedToAlloca; "Failed to allocate memory"
0x1800de146  mov     edx, eax
0x1800de148  lea     ecx, [rdi+3]
0x1800de14b  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800de150  jmp     loc_1800DE2FD
0x1800de155  mov     [rbp+57h+lpString1], rdi
0x1800de159  mov     [rbp+57h+var_50], rdi
0x1800de15d  mov     [rbp+57h+var_40], rdi
0x1800de161  mov     [rbp+57h+var_38], rdi
0x1800de165  mov     [rbp+57h+var_70], rdi
0x1800de169  mov     edx, 7Eh ; '~'; wchar_t
0x1800de16e  lea     rax, [rbp+57h+var_70]
0x1800de172  mov     [rsp+0B0h+var_80], rax; wchar_t **
0x1800de177  lea     rax, [rbp+57h+var_40]
0x1800de17b  mov     [rsp+0B0h+var_88], rax; wchar_t **
0x1800de180  lea     rax, [rbp+57h+var_38]
0x1800de184  mov     qword ptr [rsp+0B0h+bIgnoreCase], rax; wchar_t **
0x1800de189  lea     r9, [rbp+57h+var_50]; wchar_t **
0x1800de18d  lea     r8, [rbp+57h+lpString1]; wchar_t **
0x1800de191  mov     rcx, [rbp+57h+var_18]; wchar_t *
0x1800de195  call    ?ShredStringIdIntoAttributes@@YAJPEA_W_WPEAPEB_W2222@Z; ShredStringIdIntoAttributes(wchar_t *,wchar_t,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *)
0x1800de19a  test    eax, eax
0x1800de19c  jns     short loc_1800DE1BA
0x1800de19e  lea     r9, [rbp+57h+var_18]
0x1800de1a2  lea     r8, aFailedToShredK; "Failed to shred keyform: {0}"
0x1800de1a9  mov     edx, eax
0x1800de1ab  mov     ecx, 3
0x1800de1b0  call    ??$TraceAtLevelHr@JVAutoScz@@@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBVAutoScz@@@Z; LogAdapter::TraceAtLevelHr<long,AutoScz>(LogAdapter::LogLevel,long,char const * const,AutoScz const &)
0x1800de1b5  jmp     loc_1800DE2FD
0x1800de1ba  mov     [rbp+57h+var_20], rdi
0x1800de1be  mov     rdx, [rbx+8]
0x1800de1c2  lea     rcx, [rbp+57h+var_20]
0x1800de1c6  call    SczAllocFromSz
0x1800de1cb  test    eax, eax
0x1800de1cd  jns     short loc_1800DE1E7
0x1800de1cf  lea     r8, aFailedToAlloca; "Failed to allocate memory"
0x1800de1d6  mov     edx, eax
0x1800de1d8  mov     ecx, 3
0x1800de1dd  call    ??$TraceAtLevelHr@J$$V@LogAdapter@@YAXW4LogLevel@0@JQEBD@Z; LogAdapter::TraceAtLevelHr<long,>(LogAdapter::LogLevel,long,char const * const)
0x1800de1e2  jmp     loc_1800DE2E7
0x1800de1e7  mov     [rbp+57h+lpString2], rdi
0x1800de1eb  mov     [rbp+57h+var_58], rdi
0x1800de1ef  mov     [rbp+57h+var_48], rdi
0x1800de1f3  mov     [rbp+57h+var_70], rdi
0x1800de1f7  mov     [rbp+57h+var_30], rdi
0x1800de1fb  mov     edx, 7Eh ; '~'; wchar_t
0x1800de200  lea     rax, [rbp+57h+var_30]
0x1800de204  mov     [rsp+0B0h+var_80], rax; wchar_t **
0x1800de209  lea     rax, [rbp+57h+var_48]
0x1800de20d  mov     [rsp+0B0h+var_88], rax; wchar_t **
0x1800de212  lea     rax, [rbp+57h+var_70]
0x1800de216  mov     qword ptr [rsp+0B0h+bIgnoreCase], rax; wchar_t **
0x1800de21b  lea     r9, [rbp+57h+var_58]; wchar_t **
0x1800de21f  lea     r8, [rbp+57h+lpString2]; wchar_t **
0x1800de223  mov     rcx, [rbp+57h+var_20]; wchar_t *
0x1800de227  call    ?ShredStringIdIntoAttributes@@YAJPEA_W_WPEAPEB_W2222@Z; ShredStringIdIntoAttributes(wchar_t *,wchar_t,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *,wchar_t const * *)
0x1800de22c  test    eax, eax
0x1800de22e  jns     short loc_1800DE24C
0x1800de230  lea     r9, [rbp+57h+var_20]
0x1800de234  lea     r8, aFailedToShredK; "Failed to shred keyform: {0}"
0x1800de23b  mov     edx, eax
0x1800de23d  mov     ecx, 3
0x1800de242  call    ??$TraceAtLevelHr@JVAutoScz@@@LogAdapter@@YAXW4LogLevel@0@JQEBDAEBVAutoScz@@@Z; LogAdapter::TraceAtLevelHr<long,AutoScz>(LogAdapter::LogLevel,long,char const * const,AutoScz const &)
0x1800de247  jmp     loc_1800DE2E7
0x1800de24c  mov     [rsp+0B0h+bIgnoreCase], 1; bIgnoreCase
0x1800de254  or      ebx, 0FFFFFFFFh
0x1800de257  mov     r9d, ebx; cchCount2
0x1800de25a  mov     r8, [rbp+57h+lpString2]; lpString2
0x1800de25e  mov     edx, ebx; cchCount1
0x1800de260  mov     rcx, [rbp+57h+lpString1]; lpString1
0x1800de264  call    cs:__imp_CompareStringOrdinal
0x1800de26b  nop     dword ptr [rax+rax+00h]
0x1800de270  cmp     eax, 2
0x1800de273  jnz     short loc_1800DE2E7
0x1800de275  mov     [rsp+0B0h+bIgnoreCase], 1; bIgnoreCase
0x1800de27d  mov     r9d, ebx; cchCount2
0x1800de280  mov     r8, [rbp+57h+var_58]; lpString2
0x1800de284  mov     edx, ebx; cchCount1
0x1800de286  mov     rcx, [rbp+57h+var_50]; lpString1
0x1800de28a  call    cs:__imp_CompareStringOrdinal
0x1800de291  nop     dword ptr [rax+rax+00h]
0x1800de296  cmp     eax, 2
0x1800de299  jnz     short loc_1800DE2E7
0x1800de29b  mov     [rsp+0B0h+bIgnoreCase], 1; bIgnoreCase
0x1800de2a3  mov     r9d, ebx; cchCount2
0x1800de2a6  mov     r8, [rbp+57h+var_48]; lpString2
0x1800de2aa  mov     edx, ebx; cchCount1
0x1800de2ac  mov     rcx, [rbp+57h+var_40]; lpString1
0x1800de2b0  call    cs:__imp_CompareStringOrdinal
0x1800de2b7  nop     dword ptr [rax+rax+00h]
0x1800de2bc  cmp     eax, 2
0x1800de2bf  jnz     short loc_1800DE2E7
0x1800de2c1  mov     [rsp+0B0h+bIgnoreCase], 1; bIgnoreCase
0x1800de2c9  mov     r9d, ebx; cchCount2
0x1800de2cc  mov     r8, [rbp+57h+var_70]; lpString2
0x1800de2d0  mov     edx, ebx; cchCount1
0x1800de2d2  mov     rcx, [rbp+57h+var_38]; lpString1
0x1800de2d6  call    cs:__imp_CompareStringOrdinal
0x1800de2dd  nop     dword ptr [rax+rax+00h]
0x1800de2e2  cmp     eax, 2
0x1800de2e5  jz      short loc_1800DE313
0x1800de2e7  mov     rcx, [rbp+57h+var_20]
0x1800de2eb  test    rcx, rcx
0x1800de2ee  jz      short loc_1800DE2FD
0x1800de2f0  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800de2f4  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800de2f9  mov     [rbp+57h+var_20], rdi
0x1800de2fd  mov     rcx, [rbp+57h+var_18]
0x1800de301  test    rcx, rcx
0x1800de304  jz      short loc_1800DE30F
0x1800de306  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800de30a  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800de30f  xor     al, al
0x1800de311  jmp     short loc_1800DE33D
0x1800de313  mov     rcx, [rbp+57h+var_20]
0x1800de317  test    rcx, rcx
0x1800de31a  jz      short loc_1800DE329
0x1800de31c  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800de320  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800de325  mov     [rbp+57h+var_20], rdi
0x1800de329  mov     rcx, [rbp+57h+var_18]
0x1800de32d  test    rcx, rcx
0x1800de330  jz      short loc_1800DE33B
0x1800de332  add     rcx, 0FFFFFFFFFFFFFFF8h; Block
0x1800de336  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x1800de33b  mov     al, 1
0x1800de33d  mov     rcx, [rbp+57h+var_10]
0x1800de341  xor     rcx, rsp; StackCookie
0x1800de344  call    __security_check_cookie
0x1800de349  lea     r11, [rsp+0B0h+var_s0]
0x1800de351  mov     rbx, [r11+20h]
0x1800de355  mov     rdi, [r11+28h]
0x1800de359  mov     rsp, r11
0x1800de35c  pop     rbp
0x1800de35d  retn
```
