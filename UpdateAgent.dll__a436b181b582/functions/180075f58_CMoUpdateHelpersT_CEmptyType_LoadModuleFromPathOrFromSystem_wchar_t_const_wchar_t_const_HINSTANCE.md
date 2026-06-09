# CMoUpdateHelpersT<CEmptyType>::LoadModuleFromPathOrFromSystem(wchar_t const *,wchar_t const *,HINSTANCE__ * *)

- ea: `0x180075f58`
- end: `0x1800761a6`
- name: `?LoadModuleFromPathOrFromSystem@?$CMoUpdateHelpersT@VCEmptyType@@@@SAJPEB_W0PEAPEAUHINSTANCE__@@@Z`
- size: `590`
- prototype: ``
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, loader_planting, installer_update, broker_com_uri`

## callers

- `0x180029064`

## callees

- `0x1800059d0`
- `0x180006a18`
- `0x180039f90`
- `0x18003c418`
- `0x180075f58`
- `0x180077664`
- `0x180096b60`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180075ff8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007609a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x180075ff8`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18007609a`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180076109`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x180076109`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076159`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180076159`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007616e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18007616e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007604c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007611a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007604c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007611a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180076037`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x180076037`

## string_xrefs

- `0x180075fca`: `DrvServicing.dll`
- `0x180076077`: `DrvServicing.dll`

## pseudocode

```c
__int64 __fastcall CMoUpdateHelpersT<CEmptyType>::LoadModuleFromPathOrFromSystem(__int64 a1, __int64 a2, HMODULE *a3)
{
  __int64 v5; // rdx
  const wchar_t *v6; // rbx
  unsigned int v7; // edi
  __int64 v8; // rcx
  int v9; // eax
  __int64 v10; // rdx
  DWORD FileAttributesW; // eax
  BOOL v12; // edi
  signed int LastError; // eax
  DWORD v14; // eax
  BOOL v15; // edi
  int v16; // eax
  HMODULE Library; // rax
  signed int v18; // eax
  HANDLE ProcessHeap; // rax
  LPCWSTR lpFileName; // [rsp+20h] [rbp-E0h] BYREF
  int v22; // [rsp+28h] [rbp-D8h] BYREF
  WCHAR Buffer[264]; // [rsp+30h] [rbp-D0h] BYREF

  v22 = 0;
  memset_0(Buffer, 0, 0x208u);
  v6 = 0;
  lpFileName = 0;
  if ( !a3 )
  {
    v7 = -2147024809;
LABEL_3:
    v8 = v7;
LABEL_4:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8, v5);
    goto LABEL_32;
  }
  if ( !a1 )
    goto LABEL_15;
  v9 = CMiscHelpersT<CEmptyType>::CombinePath(a1, L"DrvServicing.dll", 0, &lpFileName);
  v7 = v9;
  if ( v9 < 0 )
  {
LABEL_7:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v9, v10);
    v6 = lpFileName;
    goto LABEL_32;
  }
  v6 = lpFileName;
  FileAttributesW = GetFileAttributesW(lpFileName);
  v12 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v12 )
  {
LABEL_15:
    if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
    {
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError > 0 )
        v7 = (unsigned __int16)LastError | 0x80070000;
      if ( (v7 & 0x80000000) != 0 )
        goto LABEL_3;
    }
    v9 = CMiscHelpersT<CEmptyType>::CombinePath(Buffer, L"DrvServicing.dll", 0, &lpFileName);
    v7 = v9;
    if ( v9 < 0 )
      goto LABEL_7;
    v6 = lpFileName;
    v14 = GetFileAttributesW(lpFileName);
    v15 = v14 != -1 && (v14 & 0x10) == 0;
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    if ( !v15 )
    {
      v7 = -2147024894;
      goto LABEL_3;
    }
  }
  v16 = VerifyFileSignature(v6, &v22);
  v7 = v16;
  if ( v16 < 0 )
  {
    v8 = (unsigned int)v16;
    goto LABEL_4;
  }
  if ( !v22 )
  {
    v7 = -2147024210;
    goto LABEL_3;
  }
  Library = LoadLibraryExW(v6, 0, 8u);
  if ( !Library )
  {
    v18 = GetLastError();
    v7 = v18;
    if ( v18 )
    {
      if ( v18 > 0 )
        v7 = (unsigned __int16)v18 | 0x80070000;
    }
    else
    {
      v7 = -2147467259;
    }
    goto LABEL_3;
  }
  *a3 = Library;
LABEL_32:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( v6 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v6 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v7;
}

```

## disassembly

```asm
0x180075f58  mov     [rsp-8+arg_8], rbx
0x180075f5d  push    rbp
0x180075f5e  push    rsi
0x180075f5f  push    rdi
0x180075f60  lea     rbp, [rsp-150h]
0x180075f68  sub     rsp, 250h
0x180075f6f  mov     rax, cs:__security_cookie
0x180075f76  xor     rax, rsp
0x180075f79  mov     [rbp+160h+var_20], rax
0x180075f80  mov     rsi, r8
0x180075f83  mov     [rsp+260h+var_238], 0
0x180075f8b  mov     rdi, rcx
0x180075f8e  mov     r8d, 208h; Size
0x180075f94  lea     rcx, [rsp+260h+Buffer]; void *
0x180075f99  xor     edx, edx; Val
0x180075f9b  call    memset_0
0x180075fa0  xor     ebx, ebx
0x180075fa2  mov     [rsp+260h+lpFileName], rbx
0x180075fa7  test    rsi, rsi
0x180075faa  jnz     short loc_180075FBD
0x180075fac  mov     edi, 80070057h
0x180075fb1  mov     ecx, edi
0x180075fb3  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180075fb8  jmp     loc_18007614D
0x180075fbd  test    rdi, rdi
0x180075fc0  jz      short loc_18007602D
0x180075fc2  lea     r9, [rsp+260h+lpFileName]
0x180075fc7  xor     r8d, r8d
0x180075fca  lea     rdx, aDrvservicingDl; "DrvServicing.dll"
0x180075fd1  mov     rcx, rdi
0x180075fd4  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180075fd9  mov     edi, eax
0x180075fdb  test    eax, eax
0x180075fdd  jns     short loc_180075FF0
0x180075fdf  mov     ecx, eax
0x180075fe1  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180075fe6  mov     rbx, [rsp+260h+lpFileName]
0x180075feb  jmp     loc_18007614D
0x180075ff0  mov     rbx, [rsp+260h+lpFileName]
0x180075ff5  mov     rcx, rbx; lpFileName
0x180075ff8  call    cs:__imp_GetFileAttributesW
0x180075fff  nop     dword ptr [rax+rax+00h]
0x180076004  mov     edi, eax
0x180076006  cmp     eax, 0FFFFFFFFh
0x180076009  jz      short loc_180076015
0x18007600b  shr     edi, 4
0x18007600e  not     edi
0x180076010  and     edi, 1
0x180076013  jmp     short loc_180076017
0x180076015  xor     edi, edi
0x180076017  xor     ecx, ecx
0x180076019  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x18007601e  xor     ecx, ecx
0x180076020  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180076025  test    edi, edi
0x180076027  jnz     loc_1800760D5
0x18007602d  mov     edx, 104h; uSize
0x180076032  lea     rcx, [rsp+260h+Buffer]; lpBuffer
0x180076037  call    cs:__imp_GetSystemDirectoryW
0x18007603e  nop     dword ptr [rax+rax+00h]
0x180076043  dec     eax
0x180076045  cmp     eax, 102h
0x18007604a  jbe     short loc_18007606F
0x18007604c  call    cs:__imp_GetLastError
0x180076053  nop     dword ptr [rax+rax+00h]
0x180076058  mov     edi, eax
0x18007605a  test    eax, eax
0x18007605c  jle     short loc_180076067
0x18007605e  movzx   edi, ax
0x180076061  or      edi, 80070000h
0x180076067  test    edi, edi
0x180076069  js      loc_180075FB1
0x18007606f  lea     r9, [rsp+260h+lpFileName]
0x180076074  xor     r8d, r8d
0x180076077  lea     rdx, aDrvservicingDl; "DrvServicing.dll"
0x18007607e  lea     rcx, [rsp+260h+Buffer]
0x180076083  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180076088  mov     edi, eax
0x18007608a  test    eax, eax
0x18007608c  js      loc_180075FDF
0x180076092  mov     rbx, [rsp+260h+lpFileName]
0x180076097  mov     rcx, rbx; lpFileName
0x18007609a  call    cs:__imp_GetFileAttributesW
0x1800760a1  nop     dword ptr [rax+rax+00h]
0x1800760a6  mov     edi, eax
0x1800760a8  cmp     eax, 0FFFFFFFFh
0x1800760ab  jz      short loc_1800760B7
0x1800760ad  shr     edi, 4
0x1800760b0  not     edi
0x1800760b2  and     edi, 1
0x1800760b5  jmp     short loc_1800760B9
0x1800760b7  xor     edi, edi
0x1800760b9  xor     ecx, ecx
0x1800760bb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800760c0  xor     ecx, ecx
0x1800760c2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800760c7  test    edi, edi
0x1800760c9  jnz     short loc_1800760D5
0x1800760cb  mov     edi, 80070002h
0x1800760d0  jmp     loc_180075FB1
0x1800760d5  lea     rdx, [rsp+260h+var_238]; int *
0x1800760da  mov     rcx, rbx; wchar_t *
0x1800760dd  call    ?VerifyFileSignature@@YAJPEB_WPEAH@Z; VerifyFileSignature(wchar_t const *,int *)
0x1800760e2  mov     edi, eax
0x1800760e4  test    eax, eax
0x1800760e6  jns     short loc_1800760EF
0x1800760e8  mov     ecx, eax
0x1800760ea  jmp     loc_180075FB3
0x1800760ef  cmp     [rsp+260h+var_238], 0
0x1800760f4  jnz     short loc_180076100
0x1800760f6  mov     edi, 800702AEh
0x1800760fb  jmp     loc_180075FB1
0x180076100  xor     edx, edx; hFile
0x180076102  mov     rcx, rbx; lpLibFileName
0x180076105  lea     r8d, [rdx+8]; dwFlags
0x180076109  call    cs:__imp_LoadLibraryExW
0x180076110  nop     dword ptr [rax+rax+00h]
0x180076115  test    rax, rax
0x180076118  jnz     short loc_18007614A
0x18007611a  call    cs:__imp_GetLastError
0x180076121  nop     dword ptr [rax+rax+00h]
0x180076126  mov     edi, eax
0x180076128  test    eax, eax
0x18007612a  jnz     short loc_180076136
0x18007612c  mov     edi, 80004005h
0x180076131  jmp     loc_180075FB1
0x180076136  jle     loc_180075FB1
0x18007613c  movzx   edi, ax
0x18007613f  or      edi, 80070000h
0x180076145  jmp     loc_180075FB1
0x18007614a  mov     [rsi], rax
0x18007614d  mov     ecx, edi
0x18007614f  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180076154  test    rbx, rbx
0x180076157  jz      short loc_180076181
0x180076159  call    cs:__imp_GetProcessHeap
0x180076160  nop     dword ptr [rax+rax+00h]
0x180076165  lea     r8, [rbx-4]; lpMem
0x180076169  xor     edx, edx; dwFlags
0x18007616b  mov     rcx, rax; hHeap
0x18007616e  call    cs:__imp_HeapFree
0x180076175  nop     dword ptr [rax+rax+00h]
0x18007617a  xor     ecx, ecx
0x18007617c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180076181  mov     eax, edi
0x180076183  mov     rcx, [rbp+160h+var_20]
0x18007618a  xor     rcx, rsp; StackCookie
0x18007618d  call    __security_check_cookie
0x180076192  mov     rbx, [rsp+260h+arg_8]
0x18007619a  add     rsp, 250h
0x1800761a1  pop     rdi
0x1800761a2  pop     rsi
0x1800761a3  pop     rbp
0x1800761a4  retn
```
