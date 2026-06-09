# CKernelReportDataCollection::GetSubmissionId(wchar_t *,wchar_t *,ulong)

- ea: `0x140044e6c`
- end: `0x14004506f`
- name: `?GetSubmissionId@CKernelReportDataCollection@@AEAAJPEA_W0K@Z`
- size: `515`
- prototype: `int(CKernelReportDataCollection *__hidden this, wchar_t *, wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x1400428f0`
- `0x140043cbc`

## callees

- `0x14000b50c`
- `0x1400372dc`
- `0x140044e6c`
- `0x14005f564`

## import_xrefs

- `CRYPTSP!CryptAcquireContextW` at `0x140044ee1`
- `CRYPTSP!CryptAcquireContextW` at `0x140044f1d`
- `CRYPTSP!CryptAcquireContextW` at `0x140044ee1`
- `CRYPTSP!CryptAcquireContextW` at `0x140044f1d`
- `CRYPTSP!CryptReleaseContext` at `0x140045044`
- `CRYPTSP!CryptReleaseContext` at `0x140045044`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044f2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044fc0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044ef5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044f2d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044f62`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140044fc0`
- `WINTRUST!CryptCATEnumerateCatAttr` at `0x140045013`
- `WINTRUST!CryptCATEnumerateCatAttr` at `0x140045013`
- `WINTRUST!CryptCATOpen` at `0x140044fac`
- `WINTRUST!CryptCATOpen` at `0x140044fac`
- `WINTRUST!CryptCATClose` at `0x14004502c`
- `WINTRUST!CryptCATClose` at `0x14004502c`

## string_xrefs

- `0x140044fe9`: `CryptCATOpen failed`

## pseudocode

```c
__int64 __fastcall CKernelReportDataCollection::GetSubmissionId(
        CKernelReportDataCollection *this,
        wchar_t *a2,
        wchar_t *a3,
        unsigned int a4)
{
  unsigned __int64 v4; // rbp
  unsigned int v7; // ebx
  const char *v8; // rax
  __int64 v9; // rdx
  signed int v10; // eax
  signed int LastError; // eax
  HANDLE v12; // rdi
  signed int v13; // eax
  CRYPTCATATTRIBUTE *i; // rdx
  CRYPTCATATTRIBUTE *v15; // rax
  CRYPTCATATTRIBUTE *v16; // rbx
  wil::details *dwFlags; // [rsp+20h] [rbp-38h]
  const char *v19; // [rsp+30h] [rbp-28h]
  wil::details::in1diag4 *retaddr; // [rsp+58h] [rbp+0h]
  HCRYPTPROV phProv; // [rsp+60h] [rbp+8h] BYREF

  v4 = a4;
  phProv = 0;
  if ( !a3 )
  {
    v7 = -2147467259;
    v8 = "lpszSubmissionId is NULL";
    v9 = 1745;
LABEL_3:
    LODWORD(dwFlags) = v7;
    wil::details::in1diag4::Log_HrMsg(
      retaddr,
      (void *)v9,
      (unsigned int)"onecore\\windows\\feedback\\core\\werfault\\kernel\\kerneldatacollection.cpp",
      "CKernelReportDataCollection::GetSubmissionId",
      dwFlags,
      (int)v8,
      v19);
    goto LABEL_29;
  }
  if ( !CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000000) )
  {
    if ( GetLastError() != -2146893802 )
    {
      LastError = GetLastError();
      if ( LastError > 0 )
        LastError = (unsigned __int16)LastError | 0x80070000;
      v9 = 1778;
      if ( LastError >= 0 )
        LastError = -2147467259;
      v7 = LastError;
      v8 = "CryptAcquireContext failed";
      goto LABEL_3;
    }
    if ( !CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000008) )
    {
      v10 = GetLastError();
      if ( v10 > 0 )
        v10 = (unsigned __int16)v10 | 0x80070000;
      v9 = 1771;
      if ( v10 >= 0 )
        v10 = -2147467259;
      v7 = v10;
      v8 = "CryptAcquireContext with CRYPT_NEWKEYSET failed";
      goto LABEL_3;
    }
  }
  v12 = CryptCATOpen(a2, 0, phProv, 0, 0);
  if ( !v12 )
  {
    v13 = GetLastError();
    if ( v13 > 0 )
      v13 = (unsigned __int16)v13 | 0x80070000;
    v9 = 1791;
    if ( v13 >= 0 )
      v13 = -2147467259;
    v7 = v13;
    v8 = "CryptCATOpen failed";
    goto LABEL_3;
  }
  for ( i = 0; ; i = v16 )
  {
    v15 = CryptCATEnumerateCatAttr(v12, i);
    v16 = v15;
    if ( !v15 )
    {
      v7 = 0;
      goto LABEL_28;
    }
    if ( !wcscmp_0(v15->pwszReferenceTag, L"Submission ID") )
      break;
  }
  v7 = StringCchCopyW(a3, v4, (const wchar_t *)v16->pbValue);
LABEL_28:
  CryptCATClose(v12);
LABEL_29:
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  return v7;
}

```

## disassembly

```asm
0x140044e6c  mov     [rsp+phProv], rcx
0x140044e71  push    rbx
0x140044e72  push    rbp
0x140044e73  push    rsi
0x140044e74  push    rdi
0x140044e75  sub     rsp, 38h
0x140044e79  mov     ebp, r9d
0x140044e7c  mov     rsi, r8
0x140044e7f  mov     [rsp+58h+phProv], 0
0x140044e88  mov     rbx, rdx
0x140044e8b  test    r8, r8
0x140044e8e  jnz     short loc_140044EC7
0x140044e90  mov     ebx, 80004005h
0x140044e95  lea     rax, aLpszsubmission; "lpszSubmissionId is NULL"
0x140044e9c  mov     edx, 6D1h; void *
0x140044ea1  mov     rcx, [rsp+58h]; this
0x140044ea6  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x140044ead  mov     qword ptr [rsp+58h+var_30], rax; int
0x140044eb2  lea     r9, aCkernelreportd_7; "CKernelReportDataCollection::GetSubmiss"...
0x140044eb9  mov     dword ptr [rsp+58h+dwFlags], ebx; wil::details *
0x140044ebd  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x140044ec2  jmp     loc_140045038
0x140044ec7  mov     edi, 1
0x140044ecc  mov     dword ptr [rsp+58h+dwFlags], 0F0000000h; dwFlags
0x140044ed4  mov     r9d, edi; dwProvType
0x140044ed7  lea     rcx, [rsp+58h+phProv]; phProv
0x140044edc  xor     r8d, r8d; szProvider
0x140044edf  xor     edx, edx; szContainer
0x140044ee1  call    cs:__imp_CryptAcquireContextW
0x140044ee8  nop     dword ptr [rax+rax+00h]
0x140044eed  test    eax, eax
0x140044eef  jnz     loc_140044F97
0x140044ef5  call    cs:__imp_GetLastError
0x140044efc  nop     dword ptr [rax+rax+00h]
0x140044f01  cmp     eax, 80090016h
0x140044f06  jnz     short loc_140044F62
0x140044f08  mov     r9d, edi; dwProvType
0x140044f0b  mov     dword ptr [rsp+58h+dwFlags], 0F0000008h; dwFlags
0x140044f13  xor     r8d, r8d; szProvider
0x140044f16  lea     rcx, [rsp+58h+phProv]; phProv
0x140044f1b  xor     edx, edx; szContainer
0x140044f1d  call    cs:__imp_CryptAcquireContextW
0x140044f24  nop     dword ptr [rax+rax+00h]
0x140044f29  test    eax, eax
0x140044f2b  jnz     short loc_140044F97
0x140044f2d  call    cs:__imp_GetLastError
0x140044f34  nop     dword ptr [rax+rax+00h]
0x140044f39  test    eax, eax
0x140044f3b  jle     short loc_140044F45
0x140044f3d  movzx   eax, ax
0x140044f40  or      eax, 80070000h
0x140044f45  test    eax, eax
0x140044f47  mov     ebx, 80004005h
0x140044f4c  mov     edx, 6EBh
0x140044f51  cmovns  eax, ebx
0x140044f54  mov     ebx, eax
0x140044f56  lea     rax, aCryptacquireco; "CryptAcquireContext with CRYPT_NEWKEYSE"...
0x140044f5d  jmp     loc_140044EA1
0x140044f62  call    cs:__imp_GetLastError
0x140044f69  nop     dword ptr [rax+rax+00h]
0x140044f6e  test    eax, eax
0x140044f70  jle     short loc_140044F7A
0x140044f72  movzx   eax, ax
0x140044f75  or      eax, 80070000h
0x140044f7a  test    eax, eax
0x140044f7c  mov     ebx, 80004005h
0x140044f81  mov     edx, 6F2h
0x140044f86  cmovns  eax, ebx
0x140044f89  mov     ebx, eax
0x140044f8b  lea     rax, aCryptacquireco_0; "CryptAcquireContext failed"
0x140044f92  jmp     loc_140044EA1
0x140044f97  mov     r8, [rsp+58h+phProv]; hProv
0x140044f9c  xor     r9d, r9d; dwPublicVersion
0x140044f9f  xor     edx, edx; fdwOpenFlags
0x140044fa1  mov     dword ptr [rsp+58h+dwFlags], 0; dwEncodingType
0x140044fa9  mov     rcx, rbx; pwszFileName
0x140044fac  call    cs:__imp_CryptCATOpen
0x140044fb3  nop     dword ptr [rax+rax+00h]
0x140044fb8  mov     rdi, rax
0x140044fbb  test    rax, rax
0x140044fbe  jnz     short loc_140044FF5
0x140044fc0  call    cs:__imp_GetLastError
0x140044fc7  nop     dword ptr [rax+rax+00h]
0x140044fcc  test    eax, eax
0x140044fce  jle     short loc_140044FD8
0x140044fd0  movzx   eax, ax
0x140044fd3  or      eax, 80070000h
0x140044fd8  test    eax, eax
0x140044fda  mov     ebx, 80004005h
0x140044fdf  mov     edx, 6FFh
0x140044fe4  cmovns  eax, ebx
0x140044fe7  mov     ebx, eax
0x140044fe9  lea     rax, aCryptcatopenFa; "CryptCATOpen failed"
0x140044ff0  jmp     loc_140044EA1
0x140044ff5  xor     edx, edx
0x140044ff7  jmp     short loc_140045010
0x140044ff9  mov     rcx, [rbx+8]; String1
0x140044ffd  lea     rdx, aSubmissionId; "Submission ID"
0x140045004  call    wcscmp_0
0x140045009  test    eax, eax
0x14004500b  jz      short loc_14004505C
0x14004500d  mov     rdx, rbx; pPrevAttr
0x140045010  mov     rcx, rdi; hCatalog
0x140045013  call    cs:__imp_CryptCATEnumerateCatAttr
0x14004501a  nop     dword ptr [rax+rax+00h]
0x14004501f  mov     rbx, rax
0x140045022  test    rax, rax
0x140045025  jnz     short loc_140044FF9
0x140045027  xor     ebx, ebx
0x140045029  mov     rcx, rdi; hCatalog
0x14004502c  call    cs:__imp_CryptCATClose
0x140045033  nop     dword ptr [rax+rax+00h]
0x140045038  mov     rcx, [rsp+58h+phProv]; hProv
0x14004503d  test    rcx, rcx
0x140045040  jz      short loc_140045050
0x140045042  xor     edx, edx; dwFlags
0x140045044  call    cs:__imp_CryptReleaseContext
0x14004504b  nop     dword ptr [rax+rax+00h]
0x140045050  mov     eax, ebx
0x140045052  add     rsp, 38h
0x140045056  pop     rdi
0x140045057  pop     rsi
0x140045058  pop     rbp
0x140045059  pop     rbx
0x14004505a  retn
0x14004505c  mov     r8, [rbx+18h]; wchar_t *
0x140045060  mov     rdx, rbp; unsigned __int64
0x140045063  mov     rcx, rsi; wchar_t *
0x140045066  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x14004506b  mov     ebx, eax
0x14004506d  jmp     short loc_140045029
```
