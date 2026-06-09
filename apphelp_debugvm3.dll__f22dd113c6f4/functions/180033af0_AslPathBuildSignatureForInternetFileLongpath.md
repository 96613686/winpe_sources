# AslPathBuildSignatureForInternetFileLongpath

- ea: `0x180033af0`
- end: `0x180033db7`
- name: `AslPathBuildSignatureForInternetFileLongpath`
- size: `711`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `loader_planting`

## callers

- `0x180016dc0`

## callees

- `0x18000f114`
- `0x18001577c`
- `0x1800159e0`
- `0x180018f20`
- `0x1800225e0`
- `0x180033af0`
- `0x180039a72`
- `0x180039aba`
- `0x180059169`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180033cd7`
- `ntdll!RtlAllocateHeap` at `0x180033cd7`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180033d82`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180033d82`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180033b4b`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180033b4b`

## string_xrefs

- `0x180033b82`: `AslPathBuildSignatureForInternetFileLongpath`
- `0x180033bc6`: `AslPathBuildSignatureForInternetFileLongpath`
- `0x180033c7e`: `AslPathBuildSignatureForInternetFileLongpath`
- `0x180033d24`: `AslPathBuildSignatureForInternetFileLongpath`

## pseudocode

```c
__int64 __fastcall AslPathBuildSignatureForInternetFileLongpath(_QWORD *a1, const WCHAR *a2)
{
  __int64 v4; // rdi
  HANDLE v5; // r14
  unsigned int v6; // ebx
  DWORD nFileSizeLow; // r12d
  DWORD nFileSizeHigh; // r13d
  int v9; // eax
  size_t v10; // r14
  wchar_t *v11; // rax
  wchar_t *v12; // rbx
  wchar_t *v13; // rax
  PVOID v14; // rdi
  wchar_t *v15; // rsi
  wchar_t *v16; // rax
  int v17; // eax
  unsigned __int64 v18; // rbx
  PVOID Heap; // rax
  int v20; // eax
  DWORD LastError_0; // [rsp+28h] [rbp-2B0h]
  wchar_t *Str; // [rsp+30h] [rbp-2A8h] BYREF
  HANDLE hFindFile; // [rsp+38h] [rbp-2A0h]
  unsigned __int64 v25; // [rsp+40h] [rbp-298h] BYREF
  struct _WIN32_FIND_DATAW FindFileData; // [rsp+50h] [rbp-288h] BYREF

  *a1 = 0;
  Str = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v25 = 0;
  v4 = -1;
  hFindFile = FindFirstFileW(a2, &FindFileData);
  v5 = hFindFile;
  if ( hFindFile == (HANDLE)-1LL )
  {
    v6 = -1073741811;
    LastError_0 = GetLastError_0();
    AslLogCallPrintf(
      1,
      "AslPathBuildSignatureForInternetFileLongpath",
      955,
      "FindFirstFile failed for %ws [GLE: %d]",
      a2,
      LastError_0);
    return v6;
  }
  nFileSizeLow = FindFileData.nFileSizeLow;
  nFileSizeHigh = FindFileData.nFileSizeHigh;
  v9 = AslStringDuplicate(&Str, a2);
  v6 = v9;
  if ( v9 < 0 )
  {
    AslLogCallPrintf(1, "AslPathBuildSignatureForInternetFileLongpath", 972, "AslStringDuplicate failed [%x]", v9);
LABEL_25:
    v14 = 0;
    goto LABEL_26;
  }
  v10 = 0;
  v11 = wcsrchr_0(Str, 0x2Eu);
  v12 = v11;
  if ( v11 )
  {
    do
      ++v4;
    while ( v11[v4] );
    v10 = 2 * v4 + 2;
  }
  v13 = wcsrchr_0(Str, 0x5Cu);
  v14 = 0;
  if ( v13 )
    v15 = v13 + 1;
  else
    v15 = Str;
  v16 = wcsrchr_0(Str, 0x5Bu);
  if ( v16 )
  {
    if ( v12 )
      memmove_0(v16, v12, v10);
    else
      *v16 = 0;
  }
  v17 = RtlStringCchLengthW(v15, 0x7FFFFFFF, &v25);
  v6 = v17;
  if ( v17 < 0 )
  {
    AslLogCallPrintf(
      1,
      "AslPathBuildSignatureForInternetFileLongpath",
      1007,
      "RtlStringCbLengthW failed to find the string end [%x]",
      v17);
LABEL_17:
    v5 = hFindFile;
    goto LABEL_26;
  }
  v18 = v25 + 26;
  if ( v25 + 26 < v25 )
  {
    v6 = -1073741675;
    AslLogCallPrintf(1, "AslPathBuildSignatureForInternetFileLongpath", 1017, "RtlSizeTAdd failed [%x]", -1073741675);
    goto LABEL_17;
  }
  Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v18);
  v14 = Heap;
  if ( !Heap )
  {
    v6 = -1073741801;
    goto LABEL_17;
  }
  v20 = RtlStringCchPrintfW(Heap, v18, L"SIGN.IE=%X%X %s", nFileSizeHigh, nFileSizeLow, v15);
  v6 = v20;
  if ( v20 >= 0 )
  {
    v5 = hFindFile;
    v6 = 0;
    *a1 = v14;
    goto LABEL_25;
  }
  AslLogCallPrintf(
    1,
    "AslPathBuildSignatureForInternetFileLongpath",
    1034,
    "RtlStringCchPrintfW failed when building internet file signature [%x]",
    v20);
  v5 = hFindFile;
LABEL_26:
  if ( Str )
    AslFree(NtCurrentPeb()->ProcessHeap, Str);
  if ( v14 )
    AslFree(NtCurrentPeb()->ProcessHeap, v14);
  FindClose(v5);
  return v6;
}

```

## disassembly

```asm
0x180033af0  mov     [rsp+arg_10], rbx
0x180033af5  mov     [rsp+arg_18], rsi
0x180033afa  push    rdi
0x180033afb  push    r12
0x180033afd  push    r13
0x180033aff  push    r14
0x180033b01  push    r15
0x180033b03  sub     rsp, 2B0h
0x180033b0a  mov     rax, cs:__security_cookie
0x180033b11  xor     rax, rsp
0x180033b14  mov     [rsp+2D8h+var_38], rax
0x180033b1c  xor     ebx, ebx
0x180033b1e  mov     rsi, rdx
0x180033b21  mov     [rcx], rbx
0x180033b24  mov     r15, rcx
0x180033b27  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x180033b2c  mov     [rsp+2D8h+Str], rbx
0x180033b31  xor     edx, edx; Val
0x180033b33  mov     r8d, 250h; Size
0x180033b39  call    memset_0
0x180033b3e  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x180033b43  mov     [rsp+2D8h+var_298], rbx
0x180033b48  mov     rcx, rsi; lpFileName
0x180033b4b  call    cs:__imp_FindFirstFileW
0x180033b51  or      rdi, 0FFFFFFFFFFFFFFFFh
0x180033b55  mov     [rsp+2D8h+hFindFile], rax
0x180033b5a  mov     r14, rax
0x180033b5d  cmp     rax, rdi
0x180033b60  jnz     short loc_180033B96
0x180033b62  mov     ebx, 0C000000Dh
0x180033b67  call    GetLastError_0
0x180033b6c  mov     dword ptr [rsp+2D8h+var_2B0], eax
0x180033b70  lea     r9, aFindfirstfileF_1; "FindFirstFile failed for %ws [GLE: %d]"
0x180033b77  mov     r8d, 3BBh
0x180033b7d  mov     [rsp+2D8h+var_2B8], rsi
0x180033b82  lea     rdx, aAslpathbuildsi_2; "AslPathBuildSignatureForInternetFileLon"...
0x180033b89  lea     ecx, [rdi+2]
0x180033b8c  call    AslLogCallPrintf
0x180033b91  jmp     loc_180033D88
0x180033b96  mov     r12d, [rsp+2D8h+FindFileData.nFileSizeLow]
0x180033b9b  lea     rcx, [rsp+2D8h+Str]
0x180033ba0  mov     r13d, [rsp+2D8h+FindFileData.nFileSizeHigh]
0x180033ba5  mov     rdx, rsi
0x180033ba8  call    AslStringDuplicate
0x180033bad  xor     esi, esi
0x180033baf  mov     ebx, eax
0x180033bb1  test    eax, eax
0x180033bb3  jns     short loc_180033BDA
0x180033bb5  lea     r9, aAslstringdupli_2; "AslStringDuplicate failed [%x]"
0x180033bbc  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x180033bc0  mov     r8d, 3CCh
0x180033bc6  lea     rdx, aAslpathbuildsi_2; "AslPathBuildSignatureForInternetFileLon"...
0x180033bcd  lea     ecx, [rsi+1]
0x180033bd0  call    AslLogCallPrintf
0x180033bd5  jmp     loc_180033D44
0x180033bda  mov     rcx, [rsp+2D8h+Str]; Str
0x180033bdf  mov     edx, 2Eh ; '.'; Ch
0x180033be4  mov     r14, rsi
0x180033be7  call    wcsrchr_0
0x180033bec  mov     rbx, rax
0x180033bef  test    rax, rax
0x180033bf2  jz      short loc_180033C05
0x180033bf4  inc     rdi
0x180033bf7  cmp     [rax+rdi*2], si
0x180033bfb  jnz     short loc_180033BF4
0x180033bfd  lea     r14, ds:2[rdi*2]
0x180033c05  mov     rcx, [rsp+2D8h+Str]; Str
0x180033c0a  mov     edx, 5Ch ; '\'; Ch
0x180033c0f  call    wcsrchr_0
0x180033c14  xor     edi, edi
0x180033c16  mov     rsi, rax
0x180033c19  test    rax, rax
0x180033c1c  jnz     short loc_180033C25
0x180033c1e  mov     rsi, [rsp+2D8h+Str]
0x180033c23  jmp     short loc_180033C29
0x180033c25  add     rsi, 2
0x180033c29  mov     rcx, [rsp+2D8h+Str]; Str
0x180033c2e  mov     edx, 5Bh ; '['; Ch
0x180033c33  call    wcsrchr_0
0x180033c38  mov     rcx, rax; void *
0x180033c3b  test    rax, rax
0x180033c3e  jz      short loc_180033C55
0x180033c40  test    rbx, rbx
0x180033c43  jz      short loc_180033C52
0x180033c45  mov     r8, r14; Size
0x180033c48  mov     rdx, rbx; Src
0x180033c4b  call    memmove_0
0x180033c50  jmp     short loc_180033C55
0x180033c52  mov     [rax], di
0x180033c55  lea     r8, [rsp+2D8h+var_298]
0x180033c5a  mov     edx, 7FFFFFFFh
0x180033c5f  mov     rcx, rsi
0x180033c62  call    RtlStringCchLengthW
0x180033c67  mov     ebx, eax
0x180033c69  test    eax, eax
0x180033c6b  jns     short loc_180033C9B
0x180033c6d  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x180033c71  lea     r9, aRtlstringcblen; "RtlStringCbLengthW failed to find the s"...
0x180033c78  mov     r8d, 3EFh
0x180033c7e  lea     rdx, aAslpathbuildsi_2; "AslPathBuildSignatureForInternetFileLon"...
0x180033c85  mov     ecx, 1
0x180033c8a  call    AslLogCallPrintf
0x180033c8f  mov     r14, [rsp+2D8h+hFindFile]
0x180033c94  xor     esi, esi
0x180033c96  jmp     loc_180033D47
0x180033c9b  mov     rax, [rsp+2D8h+var_298]
0x180033ca0  lea     rbx, [rax+1Ah]
0x180033ca4  cmp     rbx, rax
0x180033ca7  jnb     short loc_180033CC1
0x180033ca9  mov     ebx, 0C0000095h
0x180033cae  lea     r9, aRtlsizetaddFai; "RtlSizeTAdd failed [%x]"
0x180033cb5  mov     dword ptr [rsp+2D8h+var_2B8], ebx
0x180033cb9  mov     r8d, 3F9h
0x180033cbf  jmp     short loc_180033C7E
0x180033cc1  mov     rcx, gs:60h
0x180033cca  lea     r8, [rbx+rbx]; Size
0x180033cce  mov     edx, 8; Flags
0x180033cd3  mov     rcx, [rcx+30h]; HeapHandle
0x180033cd7  call    cs:__imp_RtlAllocateHeap
0x180033cdd  mov     rdi, rax
0x180033ce0  test    rax, rax
0x180033ce3  jnz     short loc_180033CEC
0x180033ce5  mov     ebx, 0C0000017h
0x180033cea  jmp     short loc_180033C8F
0x180033cec  mov     [rsp+2D8h+var_2B0], rsi
0x180033cf1  lea     r8, aSignIeXXS; "SIGN.IE=%X%X %s"
0x180033cf8  mov     r9d, r13d
0x180033cfb  mov     dword ptr [rsp+2D8h+var_2B8], r12d
0x180033d00  mov     rdx, rbx
0x180033d03  mov     rcx, rdi
0x180033d06  call    RtlStringCchPrintfW
0x180033d0b  xor     esi, esi
0x180033d0d  mov     ebx, eax
0x180033d0f  test    eax, eax
0x180033d11  jns     short loc_180033D3A
0x180033d13  lea     r9, aRtlstringcchpr_0; "RtlStringCchPrintfW failed when buildin"...
0x180033d1a  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x180033d1e  mov     r8d, 40Ah
0x180033d24  lea     rdx, aAslpathbuildsi_2; "AslPathBuildSignatureForInternetFileLon"...
0x180033d2b  lea     ecx, [rsi+1]
0x180033d2e  call    AslLogCallPrintf
0x180033d33  mov     r14, [rsp+2D8h+hFindFile]
0x180033d38  jmp     short loc_180033D47
0x180033d3a  mov     r14, [rsp+2D8h+hFindFile]
0x180033d3f  mov     ebx, esi
0x180033d41  mov     [r15], rdi
0x180033d44  mov     rdi, rsi
0x180033d47  cmp     [rsp+2D8h+Str], rsi
0x180033d4c  jz      short loc_180033D65
0x180033d4e  mov     rcx, gs:60h
0x180033d57  mov     rdx, [rsp+2D8h+Str]
0x180033d5c  mov     rcx, [rcx+30h]
0x180033d60  call    AslFree
0x180033d65  test    rdi, rdi
0x180033d68  jz      short loc_180033D7F
0x180033d6a  mov     rcx, gs:60h
0x180033d73  mov     rdx, rdi
0x180033d76  mov     rcx, [rcx+30h]
0x180033d7a  call    AslFree
0x180033d7f  mov     rcx, r14; hFindFile
0x180033d82  call    cs:__imp_FindClose
0x180033d88  mov     eax, ebx
0x180033d8a  mov     rcx, [rsp+2D8h+var_38]
0x180033d92  xor     rcx, rsp; StackCookie
0x180033d95  call    __security_check_cookie
0x180033d9a  lea     r11, [rsp+2D8h+var_28]
0x180033da2  mov     rbx, [r11+40h]
0x180033da6  mov     rsi, [r11+48h]
0x180033daa  mov     rsp, r11
0x180033dad  pop     r15
0x180033daf  pop     r14
0x180033db1  pop     r13
0x180033db3  pop     r12
0x180033db5  pop     rdi
0x180033db6  retn
```
