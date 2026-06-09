# CDlpCabHelperT<CEmptyType>::ExtractFromCabinet(ushort const *,ushort const *,ushort const *)

- ea: `0x14000c9d8`
- end: `0x14000d155`
- name: `?ExtractFromCabinet@?$CDlpCabHelperT@VCEmptyType@@@@SAJPEBG00@Z`
- size: `1917`
- prototype: `__int64 __fastcall(LPCWSTR lpFileName, LPCWSTR)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x1400166d8`

## callees

- `0x1400076c8`
- `0x140007cb0`
- `0x14000c9d8`
- `0x14000f33c`
- `0x140010d84`
- `0x1400135b8`
- `0x140018a38`
- `0x140020804`
- `0x140080d70`
- `0x140082010`

## import_xrefs

- `KERNEL32!LoadLibraryW` at `0x14000caef`
- `KERNEL32!LoadLibraryW` at `0x14000caef`
- `KERNEL32!FreeLibrary` at `0x14000cc00`
- `KERNEL32!FreeLibrary` at `0x14000cc00`
- `KERNEL32!HeapFree` at `0x14000cc2a`
- `KERNEL32!HeapFree` at `0x14000cc50`
- `KERNEL32!HeapFree` at `0x14000cc7e`
- `KERNEL32!HeapFree` at `0x14000ccb3`
- `KERNEL32!HeapFree` at `0x14000cce1`
- `KERNEL32!HeapFree` at `0x14000cd0f`
- `KERNEL32!HeapFree` at `0x14000cd3e`
- `KERNEL32!HeapFree` at `0x14000cd73`
- `KERNEL32!HeapFree` at `0x14000cda8`
- `KERNEL32!HeapFree` at `0x14000cddd`
- `KERNEL32!HeapFree` at `0x14000ce12`
- `KERNEL32!HeapFree` at `0x14000cc2a`
- `KERNEL32!HeapFree` at `0x14000cc50`
- `KERNEL32!HeapFree` at `0x14000cc7e`
- `KERNEL32!HeapFree` at `0x14000ccb3`
- `KERNEL32!HeapFree` at `0x14000cce1`
- `KERNEL32!HeapFree` at `0x14000cd0f`
- `KERNEL32!HeapFree` at `0x14000cd3e`
- `KERNEL32!HeapFree` at `0x14000cd73`
- `KERNEL32!HeapFree` at `0x14000cda8`
- `KERNEL32!HeapFree` at `0x14000cddd`
- `KERNEL32!HeapFree` at `0x14000ce12`
- `KERNEL32!GetProcAddress` at `0x14000cb37`
- `KERNEL32!GetProcAddress` at `0x14000cb55`
- `KERNEL32!GetProcAddress` at `0x14000cba0`
- `KERNEL32!GetProcAddress` at `0x14000cb37`
- `KERNEL32!GetProcAddress` at `0x14000cb55`
- `KERNEL32!GetProcAddress` at `0x14000cba0`
- `KERNEL32!GetProcessHeap` at `0x14000cc16`
- `KERNEL32!GetProcessHeap` at `0x14000cc3c`
- `KERNEL32!GetProcessHeap` at `0x14000cc6a`
- `KERNEL32!GetProcessHeap` at `0x14000cc9f`
- `KERNEL32!GetProcessHeap` at `0x14000cccc`
- `KERNEL32!GetProcessHeap` at `0x14000ccfa`
- `KERNEL32!GetProcessHeap` at `0x14000cd28`
- `KERNEL32!GetProcessHeap` at `0x14000cd5f`
- `KERNEL32!GetProcessHeap` at `0x14000cd94`
- `KERNEL32!GetProcessHeap` at `0x14000cdc9`
- `KERNEL32!GetProcessHeap` at `0x14000cdfe`
- `KERNEL32!GetProcessHeap` at `0x14000cc16`
- `KERNEL32!GetProcessHeap` at `0x14000cc3c`
- `KERNEL32!GetProcessHeap` at `0x14000cc6a`
- `KERNEL32!GetProcessHeap` at `0x14000cc9f`
- `KERNEL32!GetProcessHeap` at `0x14000cccc`
- `KERNEL32!GetProcessHeap` at `0x14000ccfa`
- `KERNEL32!GetProcessHeap` at `0x14000cd28`
- `KERNEL32!GetProcessHeap` at `0x14000cd5f`
- `KERNEL32!GetProcessHeap` at `0x14000cd94`
- `KERNEL32!GetProcessHeap` at `0x14000cdc9`
- `KERNEL32!GetProcessHeap` at `0x14000cdfe`
- `KERNEL32!GetLastError` at `0x14000cb03`
- `KERNEL32!GetLastError` at `0x14000cb69`
- `KERNEL32!GetLastError` at `0x14000cbb8`
- `KERNEL32!GetLastError` at `0x14000cb03`
- `KERNEL32!GetLastError` at `0x14000cb69`
- `KERNEL32!GetLastError` at `0x14000cbb8`
- `KERNEL32!GetFileAttributesW` at `0x14000ca81`
- `KERNEL32!GetFileAttributesW` at `0x14000ca81`

## string_xrefs

- `0x14000cad5`: `system32\cabinet.dll`
- `0x14000cb2d`: `FDICreate`
- `0x14000cb4b`: `FDICopy`

## pseudocode

```c
__int64 __fastcall CDlpCabHelperT<CEmptyType>::ExtractFromCabinet(LPCWSTR lpFileName, LPCWSTR a2)
{
  __int64 v4; // r12
  LPCWCH v5; // r14
  const WCHAR *v6; // r13
  HMODULE v7; // rbx
  __int64 v8; // rcx
  unsigned int v9; // edi
  DWORD FileAttributesW; // eax
  BOOL v11; // edi
  int WindowsPath; // eax
  HMODULE LibraryW; // rax
  signed int LastError; // eax
  FARPROC ProcAddress; // rdi
  FARPROC v16; // r14
  signed int v17; // eax
  FARPROC v18; // r12
  signed int v19; // eax
  void *v20; // rbx
  HANDLE ProcessHeap; // rax
  void *v22; // rbx
  HANDLE v23; // rax
  unsigned __int16 *v24; // rbx
  HANDLE v25; // rax
  HANDLE v26; // rax
  HANDLE v27; // rax
  HANDLE v28; // rax
  void *v29; // rbx
  HANDLE v30; // rax
  void *v31; // rbx
  HANDLE v32; // rax
  WCHAR *v33; // rbx
  HANDLE v34; // rax
  void *v35; // rbx
  HANDLE v36; // rax
  int FullPath; // eax
  __int64 v39; // rsi
  int v40; // eax
  const WCHAR *v41; // rsi
  __int64 v42; // [rsp+60h] [rbp-81h]
  LPCWCH lpWideCharStr; // [rsp+68h] [rbp-79h] BYREF
  __int64 v44; // [rsp+70h] [rbp-71h]
  LPCWCH v45; // [rsp+78h] [rbp-69h] BYREF
  LPVOID lpMem; // [rsp+80h] [rbp-61h]
  __int64 v47; // [rsp+88h] [rbp-59h]
  unsigned __int16 *Src; // [rsp+90h] [rbp-51h]
  __int64 v49; // [rsp+98h] [rbp-49h] BYREF
  __int64 v50; // [rsp+A0h] [rbp-41h]
  LPCWSTR lpLibFileName; // [rsp+A8h] [rbp-39h] BYREF
  __int64 v52; // [rsp+B0h] [rbp-31h] BYREF
  __int128 v53; // [rsp+B8h] [rbp-29h] BYREF
  __int64 v54; // [rsp+C8h] [rbp-19h]
  __int64 v55; // [rsp+D0h] [rbp-11h]
  __int64 v56; // [rsp+D8h] [rbp-9h]
  HMODULE v57; // [rsp+E0h] [rbp-1h]
  __int64 v58; // [rsp+E8h] [rbp+7h] BYREF
  int v59; // [rsp+F0h] [rbp+Fh]

  v55 = -2;
  v52 = 0;
  lpLibFileName = 0;
  v50 = 0;
  v49 = 0;
  v4 = 0;
  v44 = 0;
  v5 = 0;
  lpWideCharStr = 0;
  v6 = 0;
  v45 = 0;
  Src = 0;
  v56 = 0;
  v47 = 0;
  lpMem = 0;
  v7 = 0;
  v58 = 0;
  v59 = 0;
  v53 = 0;
  v54 = 0;
  if ( !lpFileName || !a2 )
  {
    v8 = 2147942487LL;
    v9 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_34;
  }
  FileAttributesW = GetFileAttributesW(lpFileName);
  v11 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  if ( !v11 )
  {
    v9 = -2147024894;
LABEL_10:
    v8 = v9;
    goto LABEL_3;
  }
  WindowsPath = CDlpHelpersT<CEmptyType>::GetWindowsPath(&v52);
  v9 = WindowsPath;
  if ( WindowsPath < 0
    || (WindowsPath = CMiscHelpersT<CEmptyType>::CombinePath(v52, L"system32\\cabinet.dll", 0, &lpLibFileName),
        v9 = WindowsPath,
        WindowsPath < 0) )
  {
    v8 = (unsigned int)WindowsPath;
    goto LABEL_3;
  }
  LibraryW = LoadLibraryW(lpLibFileName);
  v7 = LibraryW;
  if ( !LibraryW || (v57 = LibraryW, (ProcAddress = GetProcAddress(LibraryW, "FDICreate")) == 0) )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v9 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v9 = -2147467259;
    }
    goto LABEL_10;
  }
  v16 = GetProcAddress(v7, "FDICopy");
  if ( !v16 )
  {
    v17 = GetLastError();
    v9 = v17;
    if ( v17 )
    {
      if ( v17 > 0 )
        v9 = (unsigned __int16)v17 | 0x80070000;
    }
    else
    {
      v9 = -2147467259;
    }
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
    goto LABEL_33;
  }
  v18 = GetProcAddress(v7, "FDIDestroy");
  if ( !v18 )
  {
    v19 = GetLastError();
    v9 = v19;
    if ( v19 )
    {
      if ( v19 > 0 )
        v9 = (unsigned __int16)v19 | 0x80070000;
    }
    else
    {
      v9 = -2147467259;
    }
LABEL_31:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
LABEL_32:
    v4 = v44;
LABEL_33:
    v5 = lpWideCharStr;
    goto LABEL_34;
  }
  v42 = ((__int64 (__fastcall *)(void *(__cdecl *)(ULONG), void (__fastcall *)(void *), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), __int64 (__fastcall *)(), int, __int64 *))ProcAddress)(
          CDlpCabHelperT<CEmptyType>::FdiAlloc,
          operator delete,
          CDlpCabHelperT<CEmptyType>::FdiOpen,
          CDlpCabHelperT<CEmptyType>::FdiRead,
          CDlpCabHelperT<CEmptyType>::FdiWrite,
          CDlpCabHelperT<CEmptyType>::FdiClose,
          CDlpCabHelperT<CEmptyType>::FdiSeek,
          -1,
          &v58);
  if ( !v42 )
  {
    if ( (int)v58 > 6 )
    {
      if ( (_DWORD)v58 != 7 )
      {
        if ( (_DWORD)v58 == 8 )
        {
          v9 = 29;
          goto LABEL_80;
        }
        if ( (_DWORD)v58 != 9 && (_DWORD)v58 != 10 )
        {
          if ( (_DWORD)v58 == 11 )
          {
            v9 = 1235;
            goto LABEL_80;
          }
          if ( (_DWORD)v58 == 12 )
          {
            v9 = 38;
            goto LABEL_80;
          }
        }
      }
    }
    else if ( (_DWORD)v58 != 6 )
    {
      switch ( (_DWORD)v58 )
      {
        case 0:
          v9 = 0;
          goto LABEL_80;
        case 1:
          v9 = 2;
          goto LABEL_80;
        case 2:
          v9 = 114;
          goto LABEL_80;
        case 3:
          v9 = 777;
          goto LABEL_80;
        case 5:
          v9 = 8;
          goto LABEL_80;
      }
    }
    v9 = 13;
LABEL_80:
    if ( v9 )
      v9 |= 0x80070000;
    if ( (v9 & 0x80000000) == 0 )
      goto LABEL_32;
    goto LABEL_31;
  }
  FullPath = CDlpHelpersT<CEmptyType>::GetFullPath(lpFileName);
  v9 = FullPath;
  if ( FullPath < 0 )
    goto LABEL_85;
  FullPath = CMiscHelpersT<CEmptyType>::ParseFileName(Src, (__int64)&v49);
  v9 = FullPath;
  if ( FullPath < 0 )
    goto LABEL_85;
  v40 = CMiscHelpersT<CEmptyType>::CombinePath(0, v50, v49, &v45);
  v9 = v40;
  if ( v40 < 0
    || (v40 = CMiscHelpersT<CEmptyType>::CombinePath(v44, &dword_1400860C4, 0, &lpWideCharStr), v9 = v40, v40 < 0)
    || (v41 = lpWideCharStr,
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0),
        v40 = CStringConvertT<unsigned long>::W2A(v41),
        v9 = v40,
        v40 < 0) )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v40);
    v6 = v45;
    goto LABEL_86;
  }
  v6 = v45;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  FullPath = CStringConvertT<unsigned long>::W2A(v6);
  v9 = FullPath;
  if ( FullPath < 0 || (FullPath = CDlpHelpersT<CEmptyType>::GetFullPath(a2), v9 = FullPath, FullPath < 0) )
  {
LABEL_85:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)FullPath);
LABEL_86:
    v39 = v42;
    goto LABEL_124;
  }
  *((_QWORD *)&v53 + 1) = v47;
  LODWORD(v54) = 0;
  v39 = v42;
  if ( !((unsigned int (__fastcall *)(__int64, _QWORD, LPVOID, _QWORD, __int64 (__fastcall *)(), _QWORD, __int128 *))v16)(
          v42,
          0,
          lpMem,
          0,
          CDlpCabHelperT<CEmptyType>::FdiNotify,
          0,
          &v53) )
  {
    if ( (int)v58 > 6 )
    {
      if ( (_DWORD)v58 != 7 )
      {
        if ( (_DWORD)v58 == 8 )
        {
          v9 = 29;
          goto LABEL_117;
        }
        if ( (_DWORD)v58 != 9 && (_DWORD)v58 != 10 )
        {
          if ( (_DWORD)v58 == 11 )
          {
            v9 = 1235;
            goto LABEL_117;
          }
          if ( (_DWORD)v58 == 12 )
          {
            v9 = 38;
            goto LABEL_117;
          }
        }
      }
    }
    else if ( (_DWORD)v58 != 6 )
    {
      switch ( (_DWORD)v58 )
      {
        case 0:
          v9 = 0;
          goto LABEL_117;
        case 1:
          v9 = 2;
          goto LABEL_117;
        case 2:
          v9 = 114;
          goto LABEL_117;
        case 3:
          v9 = 777;
          goto LABEL_117;
        case 5:
          v9 = 8;
          goto LABEL_117;
      }
    }
    v9 = 13;
LABEL_117:
    if ( v9 )
      v9 |= 0x80070000;
    if ( (v9 & 0x80000000) == 0 )
      goto LABEL_124;
    goto LABEL_123;
  }
  if ( !(_DWORD)v54 )
  {
    v9 = -2147023728;
LABEL_123:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v9);
  }
LABEL_124:
  ((void (__fastcall *)(__int64))v18)(v39);
  v5 = lpWideCharStr;
  v4 = v44;
LABEL_34:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v9);
  if ( v7 )
    FreeLibrary(v7);
  v20 = lpMem;
  if ( lpMem )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v20);
  }
  if ( v47 )
  {
    v22 = (void *)(v47 - 4);
    v23 = GetProcessHeap();
    HeapFree(v23, 0, v22);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( Src )
  {
    v24 = Src - 2;
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v6 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, (LPVOID)(v6 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v5 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, (LPVOID)(v5 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v4 )
  {
    v28 = GetProcessHeap();
    HeapFree(v28, 0, (LPVOID)(v4 - 4));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v49 )
  {
    v29 = (void *)(v49 - 4);
    v30 = GetProcessHeap();
    HeapFree(v30, 0, v29);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v50 )
  {
    v31 = (void *)(v50 - 4);
    v32 = GetProcessHeap();
    HeapFree(v32, 0, v31);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( lpLibFileName )
  {
    v33 = (WCHAR *)(lpLibFileName - 2);
    v34 = GetProcessHeap();
    HeapFree(v34, 0, v33);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v52 )
  {
    v35 = (void *)(v52 - 4);
    v36 = GetProcessHeap();
    HeapFree(v36, 0, v35);
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  return v9;
}

```

## disassembly

```asm
0x14000c9d8  mov     rax, rsp
0x14000c9db  push    rbp
0x14000c9dc  push    rsi
0x14000c9dd  push    rdi
0x14000c9de  push    r12
0x14000c9e0  push    r13
0x14000c9e2  push    r14
0x14000c9e4  push    r15
0x14000c9e6  lea     rbp, [rax-5Fh]
0x14000c9ea  sub     rsp, 100h
0x14000c9f1  mov     [rbp+57h+var_68], 0FFFFFFFFFFFFFFFEh
0x14000c9f9  mov     [rax+18h], rbx
0x14000c9fd  mov     rax, cs:__security_cookie
0x14000ca04  xor     rax, rsp
0x14000ca07  mov     [rbp+57h+var_40], rax
0x14000ca0b  mov     r15, rdx
0x14000ca0e  mov     rsi, rcx
0x14000ca11  xor     ecx, ecx
0x14000ca13  mov     [rbp+57h+var_88], rcx
0x14000ca17  mov     [rbp+57h+lpLibFileName], rcx
0x14000ca1b  mov     [rbp+57h+var_98], rcx
0x14000ca1f  mov     [rbp+57h+var_A0], rcx
0x14000ca23  mov     r12d, ecx
0x14000ca26  mov     [rbp+57h+var_C8], rcx
0x14000ca2a  mov     r14d, ecx
0x14000ca2d  mov     [rbp+57h+lpWideCharStr], rcx
0x14000ca31  mov     r13d, ecx
0x14000ca34  mov     [rbp+57h+var_C0], rcx
0x14000ca38  mov     [rbp+57h+Src], rcx
0x14000ca3c  mov     [rbp+57h+var_60], rcx
0x14000ca40  mov     [rbp+57h+var_B0], rcx
0x14000ca44  mov     [rsp+130h+var_E0], rcx
0x14000ca49  mov     [rbp+57h+lpMem], rcx
0x14000ca4d  mov     ebx, ecx
0x14000ca4f  xor     eax, eax
0x14000ca51  mov     [rbp+57h+var_50], rax
0x14000ca55  mov     [rbp+57h+var_48], eax
0x14000ca58  xorps   xmm0, xmm0
0x14000ca5b  movups  [rbp+57h+var_80], xmm0
0x14000ca5f  mov     [rbp+57h+var_70], rax
0x14000ca63  test    rsi, rsi
0x14000ca66  jnz     short loc_14000CA79
0x14000ca68  mov     ecx, 80070057h
0x14000ca6d  mov     edi, ecx
0x14000ca6f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000ca74  jmp     loc_14000CBEB
0x14000ca79  test    r15, r15
0x14000ca7c  jz      short loc_14000CA68
0x14000ca7e  mov     rcx, rsi; lpFileName
0x14000ca81  call    cs:__imp_GetFileAttributesW
0x14000ca88  nop     dword ptr [rax+rax+00h]
0x14000ca8d  mov     edi, eax
0x14000ca8f  cmp     eax, 0FFFFFFFFh
0x14000ca92  jz      short loc_14000CA9E
0x14000ca94  shr     edi, 4
0x14000ca97  not     edi
0x14000ca99  and     edi, 1
0x14000ca9c  jmp     short loc_14000CAA0
0x14000ca9e  xor     edi, edi
0x14000caa0  xor     ecx, ecx
0x14000caa2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000caa7  xor     ecx, ecx
0x14000caa9  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000caae  test    edi, edi
0x14000cab0  jnz     short loc_14000CABB
0x14000cab2  mov     edi, 80070002h
0x14000cab7  mov     ecx, edi
0x14000cab9  jmp     short loc_14000CA6F
0x14000cabb  lea     rcx, [rbp+57h+var_88]
0x14000cabf  call    ?GetWindowsPath@?$CDlpHelpersT@VCEmptyType@@@@SAJPEAPEAG@Z; CDlpHelpersT<CEmptyType>::GetWindowsPath(ushort * *)
0x14000cac4  mov     edi, eax
0x14000cac6  test    eax, eax
0x14000cac8  jns     short loc_14000CACE
0x14000caca  mov     ecx, eax
0x14000cacc  jmp     short loc_14000CA6F
0x14000cace  lea     r9, [rbp+57h+lpLibFileName]
0x14000cad2  xor     r8d, r8d
0x14000cad5  lea     rdx, aSystem32Cabine; "system32\\cabinet.dll"
0x14000cadc  mov     rcx, [rbp+57h+var_88]
0x14000cae0  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14000cae5  mov     edi, eax
0x14000cae7  test    eax, eax
0x14000cae9  js      short loc_14000CACA
0x14000caeb  mov     rcx, [rbp+57h+lpLibFileName]; lpLibFileName
0x14000caef  call    cs:__imp_LoadLibraryW
0x14000caf6  nop     dword ptr [rax+rax+00h]
0x14000cafb  mov     rbx, rax
0x14000cafe  test    rax, rax
0x14000cb01  jnz     short loc_14000CB29
0x14000cb03  call    cs:__imp_GetLastError
0x14000cb0a  nop     dword ptr [rax+rax+00h]
0x14000cb0f  test    eax, eax
0x14000cb11  mov     edi, eax
0x14000cb13  jnz     short loc_14000CB1C
0x14000cb15  mov     edi, 80004005h
0x14000cb1a  jmp     short loc_14000CAB7
0x14000cb1c  jle     short loc_14000CAB7
0x14000cb1e  movzx   edi, ax
0x14000cb21  or      edi, 80070000h
0x14000cb27  jmp     short loc_14000CAB7
0x14000cb29  mov     [rbp+57h+var_58], rbx
0x14000cb2d  lea     rdx, aFdicreate; "FDICreate"
0x14000cb34  mov     rcx, rbx; hModule
0x14000cb37  call    cs:__imp_GetProcAddress
0x14000cb3e  nop     dword ptr [rax+rax+00h]
0x14000cb43  mov     rdi, rax
0x14000cb46  test    rax, rax
0x14000cb49  jz      short loc_14000CB03
0x14000cb4b  lea     rdx, aFdicopy; "FDICopy"
0x14000cb52  mov     rcx, rbx; hModule
0x14000cb55  call    cs:__imp_GetProcAddress
0x14000cb5c  nop     dword ptr [rax+rax+00h]
0x14000cb61  mov     r14, rax
0x14000cb64  test    rax, rax
0x14000cb67  jnz     short loc_14000CB96
0x14000cb69  call    cs:__imp_GetLastError
0x14000cb70  nop     dword ptr [rax+rax+00h]
0x14000cb75  mov     edi, eax
0x14000cb77  test    eax, eax
0x14000cb79  jnz     short loc_14000CB82
0x14000cb7b  mov     edi, 80004005h
0x14000cb80  jmp     short loc_14000CB8D
0x14000cb82  jle     short loc_14000CB8D
0x14000cb84  movzx   edi, ax
0x14000cb87  or      edi, 80070000h
0x14000cb8d  mov     ecx, edi
0x14000cb8f  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000cb94  jmp     short loc_14000CBE7
0x14000cb96  lea     rdx, aFdidestroy; "FDIDestroy"
0x14000cb9d  mov     rcx, rbx; hModule
0x14000cba0  call    cs:__imp_GetProcAddress
0x14000cba7  nop     dword ptr [rax+rax+00h]
0x14000cbac  mov     r12, rax
0x14000cbaf  test    rax, rax
0x14000cbb2  jnz     loc_14000CE4F
0x14000cbb8  call    cs:__imp_GetLastError
0x14000cbbf  nop     dword ptr [rax+rax+00h]
0x14000cbc4  mov     edi, eax
0x14000cbc6  test    eax, eax
0x14000cbc8  jnz     short loc_14000CBD1
0x14000cbca  mov     edi, 80004005h
0x14000cbcf  jmp     short loc_14000CBDC
0x14000cbd1  jle     short loc_14000CBDC
0x14000cbd3  movzx   edi, ax
0x14000cbd6  or      edi, 80070000h
0x14000cbdc  mov     ecx, edi
0x14000cbde  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000cbe3  mov     r12, [rbp+57h+var_C8]
0x14000cbe7  mov     r14, [rbp+57h+lpWideCharStr]
0x14000cbeb  mov     r15, [rsp+130h+var_E0]
0x14000cbf0  mov     ecx, edi
0x14000cbf2  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000cbf7  nop
0x14000cbf8  test    rbx, rbx
0x14000cbfb  jz      short loc_14000CC0D
0x14000cbfd  mov     rcx, rbx; hLibModule
0x14000cc00  call    cs:__imp_FreeLibrary
0x14000cc07  nop     dword ptr [rax+rax+00h]
0x14000cc0c  nop
0x14000cc0d  mov     rbx, [rbp+57h+lpMem]
0x14000cc11  test    rbx, rbx
0x14000cc14  jz      short loc_14000CC37
0x14000cc16  call    cs:__imp_GetProcessHeap
0x14000cc1d  nop     dword ptr [rax+rax+00h]
0x14000cc22  mov     rcx, rax; hHeap
0x14000cc25  mov     r8, rbx; lpMem
0x14000cc28  xor     edx, edx; dwFlags
0x14000cc2a  call    cs:__imp_HeapFree
0x14000cc31  nop     dword ptr [rax+rax+00h]
0x14000cc36  nop
0x14000cc37  test    r15, r15
0x14000cc3a  jz      short loc_14000CC5D
0x14000cc3c  call    cs:__imp_GetProcessHeap
0x14000cc43  nop     dword ptr [rax+rax+00h]
0x14000cc48  mov     rcx, rax; hHeap
0x14000cc4b  mov     r8, r15; lpMem
0x14000cc4e  xor     edx, edx; dwFlags
0x14000cc50  call    cs:__imp_HeapFree
0x14000cc57  nop     dword ptr [rax+rax+00h]
0x14000cc5c  nop
0x14000cc5d  mov     rax, [rbp+57h+var_B0]
0x14000cc61  test    rax, rax
0x14000cc64  jz      short loc_14000CC92
0x14000cc66  lea     rbx, [rax-4]
0x14000cc6a  call    cs:__imp_GetProcessHeap
0x14000cc71  nop     dword ptr [rax+rax+00h]
0x14000cc76  mov     rcx, rax; hHeap
0x14000cc79  mov     r8, rbx; lpMem
0x14000cc7c  xor     edx, edx; dwFlags
0x14000cc7e  call    cs:__imp_HeapFree
0x14000cc85  nop     dword ptr [rax+rax+00h]
0x14000cc8a  xor     ecx, ecx
0x14000cc8c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000cc91  nop
0x14000cc92  mov     rax, [rbp+57h+Src]
0x14000cc96  test    rax, rax
0x14000cc99  jz      short loc_14000CCC7
0x14000cc9b  lea     rbx, [rax-4]
0x14000cc9f  call    cs:__imp_GetProcessHeap
0x14000cca6  nop     dword ptr [rax+rax+00h]
0x14000ccab  mov     rcx, rax; hHeap
0x14000ccae  mov     r8, rbx; lpMem
0x14000ccb1  xor     edx, edx; dwFlags
0x14000ccb3  call    cs:__imp_HeapFree
0x14000ccba  nop     dword ptr [rax+rax+00h]
0x14000ccbf  xor     ecx, ecx
0x14000ccc1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000ccc6  nop
0x14000ccc7  test    r13, r13
0x14000ccca  jz      short loc_14000CCF5
0x14000cccc  call    cs:__imp_GetProcessHeap
0x14000ccd3  nop     dword ptr [rax+rax+00h]
0x14000ccd8  mov     rcx, rax; hHeap
0x14000ccdb  lea     r8, [r13-4]; lpMem
0x14000ccdf  xor     edx, edx; dwFlags
0x14000cce1  call    cs:__imp_HeapFree
0x14000cce8  nop     dword ptr [rax+rax+00h]
0x14000cced  xor     ecx, ecx
0x14000ccef  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000ccf4  nop
0x14000ccf5  test    r14, r14
0x14000ccf8  jz      short loc_14000CD23
0x14000ccfa  call    cs:__imp_GetProcessHeap
0x14000cd01  nop     dword ptr [rax+rax+00h]
0x14000cd06  mov     rcx, rax; hHeap
0x14000cd09  lea     r8, [r14-4]; lpMem
0x14000cd0d  xor     edx, edx; dwFlags
0x14000cd0f  call    cs:__imp_HeapFree
0x14000cd16  nop     dword ptr [rax+rax+00h]
0x14000cd1b  xor     ecx, ecx
0x14000cd1d  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000cd22  nop
0x14000cd23  test    r12, r12
0x14000cd26  jz      short loc_14000CD52
0x14000cd28  call    cs:__imp_GetProcessHeap
0x14000cd2f  nop     dword ptr [rax+rax+00h]
0x14000cd34  mov     rcx, rax; hHeap
0x14000cd37  lea     r8, [r12-4]; lpMem
0x14000cd3c  xor     edx, edx; dwFlags
0x14000cd3e  call    cs:__imp_HeapFree
0x14000cd45  nop     dword ptr [rax+rax+00h]
0x14000cd4a  xor     ecx, ecx
0x14000cd4c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000cd51  nop
0x14000cd52  mov     rax, [rbp+57h+var_A0]
0x14000cd56  test    rax, rax
0x14000cd59  jz      short loc_14000CD87
0x14000cd5b  lea     rbx, [rax-4]
0x14000cd5f  call    cs:__imp_GetProcessHeap
0x14000cd66  nop     dword ptr [rax+rax+00h]
0x14000cd6b  mov     rcx, rax; hHeap
0x14000cd6e  mov     r8, rbx; lpMem
0x14000cd71  xor     edx, edx; dwFlags
0x14000cd73  call    cs:__imp_HeapFree
0x14000cd7a  nop     dword ptr [rax+rax+00h]
0x14000cd7f  xor     ecx, ecx
0x14000cd81  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000cd86  nop
0x14000cd87  mov     rax, [rbp+57h+var_98]
0x14000cd8b  test    rax, rax
0x14000cd8e  jz      short loc_14000CDBC
0x14000cd90  lea     rbx, [rax-4]
0x14000cd94  call    cs:__imp_GetProcessHeap
0x14000cd9b  nop     dword ptr [rax+rax+00h]
0x14000cda0  mov     rcx, rax; hHeap
0x14000cda3  mov     r8, rbx; lpMem
0x14000cda6  xor     edx, edx; dwFlags
0x14000cda8  call    cs:__imp_HeapFree
0x14000cdaf  nop     dword ptr [rax+rax+00h]
0x14000cdb4  xor     ecx, ecx
0x14000cdb6  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000cdbb  nop
0x14000cdbc  mov     rax, [rbp+57h+lpLibFileName]
0x14000cdc0  test    rax, rax
0x14000cdc3  jz      short loc_14000CDF1
0x14000cdc5  lea     rbx, [rax-4]
0x14000cdc9  call    cs:__imp_GetProcessHeap
0x14000cdd0  nop     dword ptr [rax+rax+00h]
0x14000cdd5  mov     rcx, rax; hHeap
0x14000cdd8  mov     r8, rbx; lpMem
0x14000cddb  xor     edx, edx; dwFlags
0x14000cddd  call    cs:__imp_HeapFree
0x14000cde4  nop     dword ptr [rax+rax+00h]
0x14000cde9  xor     ecx, ecx
0x14000cdeb  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000cdf0  nop
0x14000cdf1  mov     rax, [rbp+57h+var_88]
0x14000cdf5  test    rax, rax
0x14000cdf8  jz      short loc_14000CE25
0x14000cdfa  lea     rbx, [rax-4]
0x14000cdfe  call    cs:__imp_GetProcessHeap
0x14000ce05  nop     dword ptr [rax+rax+00h]
0x14000ce0a  mov     rcx, rax; hHeap
0x14000ce0d  mov     r8, rbx; lpMem
0x14000ce10  xor     edx, edx; dwFlags
0x14000ce12  call    cs:__imp_HeapFree
0x14000ce19  nop     dword ptr [rax+rax+00h]
0x14000ce1e  xor     ecx, ecx
0x14000ce20  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000ce25  mov     eax, edi
  ... truncated ...
```
