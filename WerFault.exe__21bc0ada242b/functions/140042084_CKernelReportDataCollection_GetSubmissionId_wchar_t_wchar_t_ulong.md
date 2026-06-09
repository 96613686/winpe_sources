# CKernelReportDataCollection::GetSubmissionId(wchar_t *,wchar_t *,ulong)

- ea: `0x140042084`
- end: `0x14004224a`
- name: `?GetSubmissionId@CKernelReportDataCollection@@AEAAJPEA_W0K@Z`
- size: `454`
- prototype: `__int64 __fastcall(CKernelReportDataCollection *this, wchar_t *, wchar_t *, unsigned int)`
- caller_count: `2`
- callee_count: `4`
- tags: ``

## callers

- `0x14003fd78`
- `0x140040fc8`

## callees

- `0x14000b4cc`
- `0x140034d9c`
- `0x140042084`
- `0x14005b7c4`

## import_xrefs

- `CRYPTSP!CryptAcquireContextW` at `0x1400420f9`
- `CRYPTSP!CryptAcquireContextW` at `0x140042129`
- `CRYPTSP!CryptAcquireContextW` at `0x1400420f9`
- `CRYPTSP!CryptAcquireContextW` at `0x140042129`
- `CRYPTSP!CryptReleaseContext` at `0x140042226`
- `CRYPTSP!CryptReleaseContext` at `0x140042226`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400421b4`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042107`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042133`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140042162`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1400421b4`
- `WINTRUST!CryptCATEnumerateCatAttr` at `0x140042201`
- `WINTRUST!CryptCATEnumerateCatAttr` at `0x140042201`
- `WINTRUST!CryptCATOpen` at `0x1400421a6`
- `WINTRUST!CryptCATOpen` at `0x1400421a6`
- `WINTRUST!CryptCATClose` at `0x140042214`
- `WINTRUST!CryptCATClose` at `0x140042214`

## string_xrefs

- `0x1400421d7`: `CryptCATOpen failed`

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
0x140042084  mov     [rsp+phProv], rcx
0x140042089  push    rbx
0x14004208a  push    rbp
0x14004208b  push    rsi
0x14004208c  push    rdi
0x14004208d  sub     rsp, 38h
0x140042091  mov     ebp, r9d
0x140042094  mov     rsi, r8
0x140042097  mov     [rsp+58h+phProv], 0
0x1400420a0  mov     rbx, rdx
0x1400420a3  test    r8, r8
0x1400420a6  jnz     short loc_1400420DF
0x1400420a8  mov     ebx, 80004005h
0x1400420ad  lea     rax, aLpszsubmission; "lpszSubmissionId is NULL"
0x1400420b4  mov     edx, 6D1h; void *
0x1400420b9  mov     rcx, [rsp+58h]; this
0x1400420be  lea     r8, aOnecoreWindows_2; "onecore\\windows\\feedback\\core\\werfa"...
0x1400420c5  mov     qword ptr [rsp+58h+var_30], rax; int
0x1400420ca  lea     r9, aCkernelreportd_7; "CKernelReportDataCollection::GetSubmiss"...
0x1400420d1  mov     dword ptr [rsp+58h+dwFlags], ebx; wil::details *
0x1400420d5  call    ?Log_HrMsg@in1diag4@details@wil@@YAJPEAXIPEBD1J1ZZ; wil::details::in1diag4::Log_HrMsg(void *,uint,char const *,char const *,long,char const *,...)
0x1400420da  jmp     loc_14004221A
0x1400420df  mov     edi, 1
0x1400420e4  mov     dword ptr [rsp+58h+dwFlags], 0F0000000h; dwFlags
0x1400420ec  mov     r9d, edi; dwProvType
0x1400420ef  lea     rcx, [rsp+58h+phProv]; phProv
0x1400420f4  xor     r8d, r8d; szProvider
0x1400420f7  xor     edx, edx; szContainer
0x1400420f9  call    cs:__imp_CryptAcquireContextW
0x1400420ff  test    eax, eax
0x140042101  jnz     loc_140042191
0x140042107  call    cs:__imp_GetLastError
0x14004210d  cmp     eax, 80090016h
0x140042112  jnz     short loc_140042162
0x140042114  mov     r9d, edi; dwProvType
0x140042117  mov     dword ptr [rsp+58h+dwFlags], 0F0000008h; dwFlags
0x14004211f  xor     r8d, r8d; szProvider
0x140042122  lea     rcx, [rsp+58h+phProv]; phProv
0x140042127  xor     edx, edx; szContainer
0x140042129  call    cs:__imp_CryptAcquireContextW
0x14004212f  test    eax, eax
0x140042131  jnz     short loc_140042191
0x140042133  call    cs:__imp_GetLastError
0x140042139  test    eax, eax
0x14004213b  jle     short loc_140042145
0x14004213d  movzx   eax, ax
0x140042140  or      eax, 80070000h
0x140042145  test    eax, eax
0x140042147  mov     ebx, 80004005h
0x14004214c  mov     edx, 6EBh
0x140042151  cmovns  eax, ebx
0x140042154  mov     ebx, eax
0x140042156  lea     rax, aCryptacquireco; "CryptAcquireContext with CRYPT_NEWKEYSE"...
0x14004215d  jmp     loc_1400420B9
0x140042162  call    cs:__imp_GetLastError
0x140042168  test    eax, eax
0x14004216a  jle     short loc_140042174
0x14004216c  movzx   eax, ax
0x14004216f  or      eax, 80070000h
0x140042174  test    eax, eax
0x140042176  mov     ebx, 80004005h
0x14004217b  mov     edx, 6F2h
0x140042180  cmovns  eax, ebx
0x140042183  mov     ebx, eax
0x140042185  lea     rax, aCryptacquireco_0; "CryptAcquireContext failed"
0x14004218c  jmp     loc_1400420B9
0x140042191  mov     r8, [rsp+58h+phProv]; hProv
0x140042196  xor     r9d, r9d; dwPublicVersion
0x140042199  xor     edx, edx; fdwOpenFlags
0x14004219b  mov     dword ptr [rsp+58h+dwFlags], 0; dwEncodingType
0x1400421a3  mov     rcx, rbx; pwszFileName
0x1400421a6  call    cs:__imp_CryptCATOpen
0x1400421ac  mov     rdi, rax
0x1400421af  test    rax, rax
0x1400421b2  jnz     short loc_1400421E3
0x1400421b4  call    cs:__imp_GetLastError
0x1400421ba  test    eax, eax
0x1400421bc  jle     short loc_1400421C6
0x1400421be  movzx   eax, ax
0x1400421c1  or      eax, 80070000h
0x1400421c6  test    eax, eax
0x1400421c8  mov     ebx, 80004005h
0x1400421cd  mov     edx, 6FFh
0x1400421d2  cmovns  eax, ebx
0x1400421d5  mov     ebx, eax
0x1400421d7  lea     rax, aCryptcatopenFa; "CryptCATOpen failed"
0x1400421de  jmp     loc_1400420B9
0x1400421e3  xor     edx, edx
0x1400421e5  jmp     short loc_1400421FE
0x1400421e7  mov     rcx, [rbx+8]; String1
0x1400421eb  lea     rdx, aSubmissionId; "Submission ID"
0x1400421f2  call    wcscmp_0
0x1400421f7  test    eax, eax
0x1400421f9  jz      short loc_140042237
0x1400421fb  mov     rdx, rbx; pPrevAttr
0x1400421fe  mov     rcx, rdi; hCatalog
0x140042201  call    cs:__imp_CryptCATEnumerateCatAttr
0x140042207  mov     rbx, rax
0x14004220a  test    rax, rax
0x14004220d  jnz     short loc_1400421E7
0x14004220f  xor     ebx, ebx
0x140042211  mov     rcx, rdi; hCatalog
0x140042214  call    cs:__imp_CryptCATClose
0x14004221a  mov     rcx, [rsp+58h+phProv]; hProv
0x14004221f  test    rcx, rcx
0x140042222  jz      short loc_14004222C
0x140042224  xor     edx, edx; dwFlags
0x140042226  call    cs:__imp_CryptReleaseContext
0x14004222c  mov     eax, ebx
0x14004222e  add     rsp, 38h
0x140042232  pop     rdi
0x140042233  pop     rsi
0x140042234  pop     rbp
0x140042235  pop     rbx
0x140042236  retn
0x140042237  mov     r8, [rbx+18h]; wchar_t *
0x14004223b  mov     rdx, rbp; unsigned __int64
0x14004223e  mov     rcx, rsi; wchar_t *
0x140042241  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x140042246  mov     ebx, eax
0x140042248  jmp     short loc_140042211
```
