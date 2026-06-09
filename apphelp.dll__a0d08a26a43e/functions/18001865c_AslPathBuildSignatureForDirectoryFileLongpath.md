# AslPathBuildSignatureForDirectoryFileLongpath

- ea: `0x18001865c`
- end: `0x1800188c8`
- name: `AslPathBuildSignatureForDirectoryFileLongpath`
- size: `620`
- prototype: `__int64 __fastcall(_QWORD *, __int64)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting`

## callers

- `0x180016dc0`

## callees

- `0x18000f114`
- `0x18001577c`
- `0x1800159e0`
- `0x18001865c`
- `0x180018f20`
- `0x1800225e0`
- `0x180039a72`
- `0x180039aba`
- `0x180059175`
- `0x1800591b0`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x1800187ed`
- `ntdll!RtlAllocateHeap` at `0x1800187ed`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180018795`
- `api-ms-win-core-file-l1-1-0!FindClose` at `0x180018795`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180018784`
- `api-ms-win-core-file-l1-1-0!FindNextFileW` at `0x180018784`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180018715`
- `api-ms-win-core-file-l1-1-0!FindFirstFileW` at `0x180018715`

## string_xrefs

- `0x180018744`: `AslPathBuildSignatureForDirectoryFileLongpath`
- `0x18001885b`: `AslPathBuildSignatureForDirectoryFileLongpath`

## pseudocode

```c
__int64 __fastcall AslPathBuildSignatureForDirectoryFileLongpath(_QWORD *a1, __int64 a2)
{
  PVOID Heap; // rbp
  int v5; // eax
  wchar_t *v6; // rsi
  unsigned int v7; // ebx
  wchar_t *v8; // rax
  wchar_t *v9; // rcx
  HANDLE FirstFileW; // r15
  int v11; // ebx
  DWORD v12; // r14d
  int v13; // eax
  const char *v14; // r9
  __int64 v15; // r8
  unsigned __int64 v16; // rbx
  int v17; // eax
  __int64 v19; // [rsp+20h] [rbp-2B8h]
  DWORD LastError_0; // [rsp+28h] [rbp-2B0h]
  wchar_t *Str; // [rsp+30h] [rbp-2A8h] BYREF
  unsigned __int64 v22; // [rsp+38h] [rbp-2A0h] BYREF
  _WIN32_FIND_DATAW FindFileData; // [rsp+40h] [rbp-298h] BYREF

  *a1 = 0;
  v22 = 0;
  Str = 0;
  Heap = 0;
  memset_0(&FindFileData, 0, sizeof(FindFileData));
  v5 = AslStringDuplicate(&Str, a2);
  v6 = Str;
  v7 = v5;
  if ( v5 < 0 )
  {
    AslLogCallPrintf(1, "AslPathBuildSignatureForDirectoryFileLongpath", 734, "AslStringDuplicate failed [%x]", v5);
    goto LABEL_27;
  }
  v8 = wcsrchr_0(Str, 0x5Cu);
  if ( v8 )
    v9 = v8 + 1;
  else
    v9 = v6;
  if ( !*v9 && v9 != v6 )
    *(_DWORD *)v9 = 42;
  FirstFileW = FindFirstFileW(v6, &FindFileData);
  if ( FirstFileW == (HANDLE)-1LL )
  {
    v7 = -1073741811;
    LastError_0 = GetLastError_0();
    AslLogCallPrintf(
      1,
      "AslPathBuildSignatureForDirectoryFileLongpath",
      757,
      "FindFirstFile failed for %ws [GLE: %x]",
      v6,
      LastError_0);
    goto LABEL_27;
  }
  v11 = 9;
  v12 = 0;
  do
  {
    if ( (FindFileData.dwFileAttributes & 0x10) == 0 && FindFileData.nFileSizeLow )
    {
      v12 = FindFileData.nFileSizeLow ^ __ROR4__(v12, 31);
      --v11;
    }
  }
  while ( FindNextFileW(FirstFileW, &FindFileData) && v11 > 0 );
  FindClose(FirstFileW);
  v13 = RtlStringCchLengthW(a2, 0x7FFFFFFF, &v22);
  v7 = v13;
  if ( v13 >= 0 )
  {
    v16 = v22 + 21;
    if ( v22 + 21 < v22 )
    {
      v7 = -1073741675;
      v14 = "RtlSizeTAdd failed [%x]";
      LODWORD(v19) = -1073741675;
      v15 = 797;
    }
    else
    {
      Heap = RtlAllocateHeap(NtCurrentPeb()->ProcessHeap, 8u, 2 * v16);
      if ( !Heap )
      {
        v7 = -1073741801;
        goto LABEL_27;
      }
      v17 = RtlStringCchPrintfW(Heap, v16, L"SIGN.MEDIA=%X %s", v12, a2 + 6);
      v7 = v17;
      if ( v17 >= 0 )
      {
        *a1 = Heap;
        Heap = 0;
        v7 = 0;
        goto LABEL_27;
      }
      LODWORD(v19) = v17;
      v14 = "RtlStringCchPrintfW failed [%x]";
      v15 = 823;
    }
  }
  else
  {
    LODWORD(v19) = v13;
    v14 = "RtlStringCchLengthW failed [%x]";
    v15 = 784;
  }
  AslLogCallPrintf(1, "AslPathBuildSignatureForDirectoryFileLongpath", v15, v14, v19);
LABEL_27:
  if ( v6 )
    AslFree(NtCurrentPeb()->ProcessHeap, v6);
  if ( Heap )
    AslFree(NtCurrentPeb()->ProcessHeap, Heap);
  return v7;
}

```

## disassembly

```asm
0x18001865c  mov     [rsp+arg_10], rbx
0x180018661  push    rbp
0x180018662  push    rsi
0x180018663  push    rdi
0x180018664  push    r12
0x180018666  push    r13
0x180018668  push    r14
0x18001866a  push    r15
0x18001866c  sub     rsp, 2A0h
0x180018673  mov     rax, cs:__security_cookie
0x18001867a  xor     rax, rsp
0x18001867d  mov     [rsp+2D8h+var_48], rax
0x180018685  xor     edi, edi
0x180018687  mov     r13, rdx
0x18001868a  mov     [rcx], rdi
0x18001868d  mov     r12, rcx
0x180018690  lea     rcx, [rsp+2D8h+FindFileData]; void *
0x180018695  mov     [rsp+2D8h+var_2A0], rdi
0x18001869a  xor     edx, edx; Val
0x18001869c  mov     [rsp+2D8h+Str], rdi
0x1800186a1  mov     r8d, 250h; Size
0x1800186a7  mov     ebp, edi
0x1800186a9  call    memset_0
0x1800186ae  mov     rdx, r13
0x1800186b1  lea     rcx, [rsp+2D8h+Str]
0x1800186b6  call    AslStringDuplicate
0x1800186bb  mov     rsi, [rsp+2D8h+Str]
0x1800186c0  mov     ebx, eax
0x1800186c2  test    eax, eax
0x1800186c4  jns     short loc_1800186DF
0x1800186c6  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x1800186ca  lea     r9, aAslstringdupli_2; "AslStringDuplicate failed [%x]"
0x1800186d1  mov     r8d, 2DEh
0x1800186d7  lea     ecx, [rdi+1]
0x1800186da  jmp     loc_18001885B
0x1800186df  mov     edx, 5Ch ; '\'; Ch
0x1800186e4  mov     rcx, rsi; Str
0x1800186e7  call    wcsrchr_0
0x1800186ec  mov     rcx, rax
0x1800186ef  test    rax, rax
0x1800186f2  jz      short loc_1800186FA
0x1800186f4  add     rcx, 2
0x1800186f8  jmp     short loc_1800186FD
0x1800186fa  mov     rcx, rsi
0x1800186fd  cmp     [rcx], di
0x180018700  jnz     short loc_18001870D
0x180018702  cmp     rcx, rsi
0x180018705  jz      short loc_18001870D
0x180018707  mov     dword ptr [rcx], 2Ah ; '*'
0x18001870d  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x180018712  mov     rcx, rsi; lpFileName
0x180018715  call    cs:__imp_FindFirstFileW
0x18001871b  mov     r15, rax
0x18001871e  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180018722  jnz     short loc_180018759
0x180018724  mov     ebx, 0C000000Dh
0x180018729  call    GetLastError_0
0x18001872e  mov     [rsp+2D8h+var_2B0], eax
0x180018732  lea     r9, aFindfirstfileF; "FindFirstFile failed for %ws [GLE: %x]"
0x180018739  mov     r8d, 2F5h
0x18001873f  mov     [rsp+2D8h+var_2B8], rsi
0x180018744  lea     rdx, aAslpathbuildsi; "AslPathBuildSignatureForDirectoryFileLo"...
0x18001874b  lea     ecx, [r15+2]
0x18001874f  call    AslLogCallPrintf
0x180018754  jmp     loc_180018867
0x180018759  mov     ebx, 9
0x18001875e  mov     r14d, edi
0x180018761  lea     edi, [rbx-8]
0x180018764  test    byte ptr [rsp+2D8h+FindFileData.dwFileAttributes], 10h
0x180018769  jnz     short loc_18001877C
0x18001876b  mov     eax, [rsp+2D8h+FindFileData.nFileSizeLow]
0x18001876f  test    eax, eax
0x180018771  jz      short loc_18001877C
0x180018773  ror     r14d, 1Fh
0x180018777  xor     r14d, eax
0x18001877a  sub     ebx, edi
0x18001877c  lea     rdx, [rsp+2D8h+FindFileData]; lpFindFileData
0x180018781  mov     rcx, r15; hFindFile
0x180018784  call    cs:__imp_FindNextFileW
0x18001878a  test    eax, eax
0x18001878c  jz      short loc_180018792
0x18001878e  test    ebx, ebx
0x180018790  jg      short loc_180018764
0x180018792  mov     rcx, r15; hFindFile
0x180018795  call    cs:__imp_FindClose
0x18001879b  lea     r8, [rsp+2D8h+var_2A0]
0x1800187a0  mov     edx, 7FFFFFFFh
0x1800187a5  mov     rcx, r13
0x1800187a8  call    RtlStringCchLengthW
0x1800187ad  mov     ebx, eax
0x1800187af  test    eax, eax
0x1800187b1  jns     short loc_1800187C9
0x1800187b3  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x1800187b7  lea     r9, aRtlstringcchle; "RtlStringCchLengthW failed [%x]"
0x1800187be  mov     r8d, 310h
0x1800187c4  jmp     loc_180018859
0x1800187c9  mov     rax, [rsp+2D8h+var_2A0]
0x1800187ce  lea     rbx, [rax+15h]
0x1800187d2  cmp     rbx, rax
0x1800187d5  jb      short loc_180018843
0x1800187d7  mov     rcx, gs:60h
0x1800187e0  lea     r8, [rbx+rbx]; Size
0x1800187e4  mov     edx, 8; Flags
0x1800187e9  mov     rcx, [rcx+30h]; HeapHandle
0x1800187ed  call    cs:__imp_RtlAllocateHeap
0x1800187f3  mov     rbp, rax
0x1800187f6  test    rax, rax
0x1800187f9  jnz     short loc_180018802
0x1800187fb  mov     ebx, 0C0000017h
0x180018800  jmp     short loc_180018867
0x180018802  lea     rax, [r13+6]
0x180018806  mov     r9d, r14d
0x180018809  lea     r8, aSignMediaXS; "SIGN.MEDIA=%X %s"
0x180018810  mov     [rsp+2D8h+var_2B8], rax
0x180018815  mov     rdx, rbx
0x180018818  mov     rcx, rbp
0x18001881b  call    RtlStringCchPrintfW
0x180018820  mov     ebx, eax
0x180018822  test    eax, eax
0x180018824  jns     short loc_180018839
0x180018826  mov     dword ptr [rsp+2D8h+var_2B8], eax
0x18001882a  lea     r9, aRtlstringcchpr; "RtlStringCchPrintfW failed [%x]"
0x180018831  mov     r8d, 337h
0x180018837  jmp     short loc_180018859
0x180018839  mov     [r12], rbp
0x18001883d  xor     ebp, ebp
0x18001883f  xor     ebx, ebx
0x180018841  jmp     short loc_180018867
0x180018843  mov     ebx, 0C0000095h
0x180018848  lea     r9, aRtlsizetaddFai; "RtlSizeTAdd failed [%x]"
0x18001884f  mov     dword ptr [rsp+2D8h+var_2B8], ebx
0x180018853  mov     r8d, 31Dh
0x180018859  mov     ecx, edi
0x18001885b  lea     rdx, aAslpathbuildsi; "AslPathBuildSignatureForDirectoryFileLo"...
0x180018862  call    AslLogCallPrintf
0x180018867  test    rsi, rsi
0x18001886a  jz      short loc_180018881
0x18001886c  mov     rcx, gs:60h
0x180018875  mov     rdx, rsi
0x180018878  mov     rcx, [rcx+30h]
0x18001887c  call    AslFree
0x180018881  test    rbp, rbp
0x180018884  jz      short loc_18001889B
0x180018886  mov     rcx, gs:60h
0x18001888f  mov     rdx, rbp
0x180018892  mov     rcx, [rcx+30h]
0x180018896  call    AslFree
0x18001889b  mov     eax, ebx
0x18001889d  mov     rcx, [rsp+2D8h+var_48]
0x1800188a5  xor     rcx, rsp; StackCookie
0x1800188a8  call    __security_check_cookie
0x1800188ad  mov     rbx, [rsp+2D8h+arg_10]
0x1800188b5  add     rsp, 2A0h
0x1800188bc  pop     r15
0x1800188be  pop     r14
0x1800188c0  pop     r13
0x1800188c2  pop     r12
0x1800188c4  pop     rdi
0x1800188c5  pop     rsi
0x1800188c6  pop     rbp
0x1800188c7  retn
```
