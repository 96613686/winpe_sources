# UpdatePrinterDriverEntry

- ea: `0x180001780`
- end: `0x1800018de`
- name: `UpdatePrinterDriverEntry`
- size: `350`
- prototype: `DWORD __fastcall(__int64, __int64, const CHAR *)`
- caller_count: `0`
- callee_count: `4`
- tags: `file_ops, loader_planting, installer_update`

## callees

- `0x180001008`
- `0x180001048`
- `0x180001780`
- `0x180002010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800017ee`
- `KERNEL32!GetProcAddress` at `0x1800017ee`
- `KERNEL32!MultiByteToWideChar` at `0x180001824`
- `KERNEL32!MultiByteToWideChar` at `0x180001878`
- `KERNEL32!MultiByteToWideChar` at `0x180001824`
- `KERNEL32!MultiByteToWideChar` at `0x180001878`
- `KERNEL32!GetLastError` at `0x1800017d3`
- `KERNEL32!GetLastError` at `0x180001853`
- `KERNEL32!GetLastError` at `0x1800018a8`
- `KERNEL32!GetLastError` at `0x1800017d3`
- `KERNEL32!GetLastError` at `0x180001853`
- `KERNEL32!GetLastError` at `0x1800018a8`
- `KERNEL32!LoadLibraryA` at `0x1800017bf`
- `KERNEL32!LoadLibraryA` at `0x1800017bf`
- `KERNEL32!FreeLibrary` at `0x1800018b9`
- `KERNEL32!FreeLibrary` at `0x1800018b9`

## string_xrefs

- `0x1800017b8`: `ntprint.dll`
- `0x1800017e4`: `PSetupDownloadAndInstallLegacyDriverW`

## pseudocode

```c
DWORD __fastcall UpdatePrinterDriverEntry(__int64 a1, __int64 a2, const CHAR *a3)
{
  __int64 v5; // rax
  HMODULE LibraryA; // rax
  HMODULE v7; // rdi
  FARPROC ProcAddress; // rbp
  unsigned int v10; // eax
  int cchWideChar; // r14d
  WCHAR *lpWideCharStr; // rax
  WCHAR *v13; // rsi
  DWORD LastError; // eax
  DWORD v15; // ebx

  if ( !a3 )
    return 87;
  v5 = -1;
  do
    ++v5;
  while ( a3[v5] );
  if ( !v5 )
    return 87;
  LibraryA = LoadLibraryA("ntprint.dll");
  v7 = LibraryA;
  if ( !LibraryA )
    return GetLastError();
  ProcAddress = GetProcAddress(LibraryA, "PSetupDownloadAndInstallLegacyDriverW");
  if ( ProcAddress && (v10 = MultiByteToWideChar(0xFDE9u, 0, a3, -1, 0, 0), (cchWideChar = v10) != 0) )
  {
    lpWideCharStr = (WCHAR *)operator new(saturated_mul(v10, 2u));
    v13 = lpWideCharStr;
    if ( lpWideCharStr && MultiByteToWideChar(0xFDE9u, 0, a3, -1, lpWideCharStr, cchWideChar) )
      LastError = ((__int64 (__fastcall *)(__int64, WCHAR *, __int64))ProcAddress)(a1, v13, 2);
    else
      LastError = GetLastError();
    v15 = LastError;
    operator delete(v13);
  }
  else
  {
    v15 = GetLastError();
  }
  FreeLibrary(v7);
  return v15;
}

```

## disassembly

```asm
0x180001780  push    rbx
0x180001782  push    rbp
0x180001783  push    rsi
0x180001784  push    rdi
0x180001785  push    r13
0x180001787  push    r14
0x180001789  push    r15
0x18000178b  sub     rsp, 30h
0x18000178f  mov     rbx, r8
0x180001792  mov     r15, rcx
0x180001795  test    r8, r8
0x180001798  jz      loc_1800018C9
0x18000179e  or      r13, 0FFFFFFFFFFFFFFFFh
0x1800017a2  mov     rax, r13
0x1800017a5  inc     rax
0x1800017a8  cmp     byte ptr [r8+rax], 0
0x1800017ad  jnz     short loc_1800017A5
0x1800017af  test    rax, rax
0x1800017b2  jz      loc_1800018C9
0x1800017b8  lea     rcx, LibFileName; "ntprint.dll"
0x1800017bf  call    cs:__imp_LoadLibraryA
0x1800017c6  nop     dword ptr [rax+rax+00h]
0x1800017cb  mov     rdi, rax
0x1800017ce  test    rax, rax
0x1800017d1  jnz     short loc_1800017E4
0x1800017d3  call    cs:__imp_GetLastError
0x1800017da  nop     dword ptr [rax+rax+00h]
0x1800017df  jmp     loc_1800018CE
0x1800017e4  lea     rdx, ProcName; "PSetupDownloadAndInstallLegacyDriverW"
0x1800017eb  mov     rcx, rdi; hModule
0x1800017ee  call    cs:__imp_GetProcAddress
0x1800017f5  nop     dword ptr [rax+rax+00h]
0x1800017fa  mov     rbp, rax
0x1800017fd  test    rax, rax
0x180001800  jz      loc_1800018A8
0x180001806  mov     [rsp+68h+cchWideChar], 0; cchWideChar
0x18000180e  mov     r9d, r13d; cbMultiByte
0x180001811  mov     r8, rbx; lpMultiByteStr
0x180001814  mov     [rsp+68h+lpWideCharStr], 0; lpWideCharStr
0x18000181d  xor     edx, edx; dwFlags
0x18000181f  mov     ecx, 0FDE9h; CodePage
0x180001824  call    cs:__imp_MultiByteToWideChar
0x18000182b  nop     dword ptr [rax+rax+00h]
0x180001830  mov     r14d, eax
0x180001833  test    eax, eax
0x180001835  jz      short loc_1800018A8
0x180001837  mov     eax, 2
0x18000183c  mul     r14
0x18000183f  cmovb   rax, r13
0x180001843  mov     rcx, rax; Size
0x180001846  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x18000184b  mov     rsi, rax
0x18000184e  test    rax, rax
0x180001851  jnz     short loc_180001861
0x180001853  call    cs:__imp_GetLastError
0x18000185a  nop     dword ptr [rax+rax+00h]
0x18000185f  jmp     short loc_18000189C
0x180001861  mov     [rsp+68h+cchWideChar], r14d; cchWideChar
0x180001866  mov     r9d, r13d; cbMultiByte
0x180001869  mov     r8, rbx; lpMultiByteStr
0x18000186c  mov     [rsp+68h+lpWideCharStr], rsi; lpWideCharStr
0x180001871  xor     edx, edx; dwFlags
0x180001873  mov     ecx, 0FDE9h; CodePage
0x180001878  call    cs:__imp_MultiByteToWideChar
0x18000187f  nop     dword ptr [rax+rax+00h]
0x180001884  test    eax, eax
0x180001886  jz      short loc_180001853
0x180001888  mov     r8d, 2
0x18000188e  mov     rdx, rsi
0x180001891  mov     rcx, r15
0x180001894  mov     rax, rbp
0x180001897  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000189c  mov     rcx, rsi; Block
0x18000189f  mov     ebx, eax
0x1800018a1  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800018a6  jmp     short loc_1800018B6
0x1800018a8  call    cs:__imp_GetLastError
0x1800018af  nop     dword ptr [rax+rax+00h]
0x1800018b4  mov     ebx, eax
0x1800018b6  mov     rcx, rdi; hLibModule
0x1800018b9  call    cs:__imp_FreeLibrary
0x1800018c0  nop     dword ptr [rax+rax+00h]
0x1800018c5  mov     eax, ebx
0x1800018c7  jmp     short loc_1800018CE
0x1800018c9  mov     eax, 57h ; 'W'
0x1800018ce  add     rsp, 30h
0x1800018d2  pop     r15
0x1800018d4  pop     r14
0x1800018d6  pop     r13
0x1800018d8  pop     rdi
0x1800018d9  pop     rsi
0x1800018da  pop     rbp
0x1800018db  pop     rbx
0x1800018dc  retn
```
