# CDlpCabHelperT<CEmptyType>::FdiNotify(FDINOTIFICATIONTYPE,FDINOTIFICATION *)

- ea: `0x14000d200`
- end: `0x14000d514`
- name: `?FdiNotify@?$CDlpCabHelperT@VCEmptyType@@@@CA_JW4FDINOTIFICATIONTYPE@@PEAUFDINOTIFICATION@@@Z`
- size: `788`
- prototype: `__int64 __fastcall(int, __int64)`
- caller_count: `0`
- callee_count: `6`
- tags: `file_ops, broker_com_uri`

## callees

- `0x140007cb0`
- `0x140009700`
- `0x14000d200`
- `0x1400135b8`
- `0x14001608c`
- `0x140018a38`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000d297`
- `KERNEL32!CloseHandle` at `0x14000d297`
- `KERNEL32!DosDateTimeToFileTime` at `0x14000d252`
- `KERNEL32!DosDateTimeToFileTime` at `0x14000d252`
- `KERNEL32!HeapFree` at `0x14000d45e`
- `KERNEL32!HeapFree` at `0x14000d48b`
- `KERNEL32!HeapFree` at `0x14000d4b3`
- `KERNEL32!HeapFree` at `0x14000d4e5`
- `KERNEL32!HeapFree` at `0x14000d45e`
- `KERNEL32!HeapFree` at `0x14000d48b`
- `KERNEL32!HeapFree` at `0x14000d4b3`
- `KERNEL32!HeapFree` at `0x14000d4e5`
- `KERNEL32!GetProcessHeap` at `0x14000d449`
- `KERNEL32!GetProcessHeap` at `0x14000d476`
- `KERNEL32!GetProcessHeap` at `0x14000d49e`
- `KERNEL32!GetProcessHeap` at `0x14000d4d0`
- `KERNEL32!GetProcessHeap` at `0x14000d449`
- `KERNEL32!GetProcessHeap` at `0x14000d476`
- `KERNEL32!GetProcessHeap` at `0x14000d49e`
- `KERNEL32!GetProcessHeap` at `0x14000d4d0`
- `KERNEL32!LocalFileTimeToFileTime` at `0x14000d26a`
- `KERNEL32!LocalFileTimeToFileTime` at `0x14000d26a`
- `KERNEL32!GetFileAttributesW` at `0x14000d338`
- `KERNEL32!GetFileAttributesW` at `0x14000d3c6`
- `KERNEL32!GetFileAttributesW` at `0x14000d338`
- `KERNEL32!GetFileAttributesW` at `0x14000d3c6`
- `KERNEL32!CreateFileW` at `0x14000d424`
- `KERNEL32!CreateFileW` at `0x14000d424`
- `KERNEL32!SetFileTime` at `0x14000d287`
- `KERNEL32!SetFileTime` at `0x14000d287`
- `KERNEL32!CompareStringW` at `0x14000d305`
- `KERNEL32!CompareStringW` at `0x14000d305`

## pseudocode

```c
__int64 __fastcall CDlpCabHelperT<CEmptyType>::FdiNotify(int a1, __int64 a2)
{
  PCNZWCH v2; // rbx
  const WCHAR *v3; // r13
  __int64 v5; // rcx
  WORD v6; // dx
  WORD v7; // cx
  __int64 v9; // r15
  __int64 v10; // rdx
  __int64 v11; // rsi
  DWORD FileAttributesW; // edi
  BOOL v13; // edi
  HANDLE FileW; // rax
  int v15; // eax
  DWORD v16; // edi
  BOOL v17; // edi
  HANDLE v18; // rax
  HANDLE v19; // rax
  HANDLE ProcessHeap; // rax
  struct _FILETIME FileTime; // [rsp+40h] [rbp-20h] BYREF
  FILETIME LastWriteTime; // [rsp+48h] [rbp-18h] BYREF
  PCNZWCH lpString1[2]; // [rsp+50h] [rbp-10h] BYREF
  LPCWSTR v24; // [rsp+A8h] [rbp+48h] BYREF

  v2 = 0;
  v3 = 0;
  lpString1[0] = 0;
  v24 = 0;
  v5 = (unsigned int)(a1 - 2);
  if ( (_DWORD)v5 )
  {
    if ( (_DWORD)v5 == 1 )
    {
      v6 = *(_WORD *)(a2 + 50);
      v7 = *(_WORD *)(a2 + 48);
      FileTime = 0;
      LastWriteTime = 0;
      if ( DosDateTimeToFileTime(v7, v6, &FileTime) )
      {
        if ( LocalFileTimeToFileTime(&FileTime, &LastWriteTime) )
          SetFileTime(*(HANDLE *)(a2 + 40), 0, 0, &LastWriteTime);
      }
      CloseHandle(*(HANDLE *)(a2 + 40));
      return 1;
    }
    return 0;
  }
  v9 = *(_QWORD *)(a2 + 32);
  v10 = *(_QWORD *)(a2 + 8);
  if ( !v10 )
    goto LABEL_34;
  CMiscHelpersT<CEmptyType>::MultiByteToWideCharWrap(v5, v10, lpString1);
  v2 = lpString1[0];
  if ( !lpString1[0] )
    return 0;
  if ( !*(_QWORD *)(v9 + 8) )
  {
LABEL_34:
    if ( v2 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, (LPVOID)(v2 - 2));
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
    }
    return 0;
  }
  v11 = -1;
  if ( *(_QWORD *)v9 && CompareStringW(0x409u, 1u, lpString1[0], -1, *(PCNZWCH *)v9, -1) == 2 )
  {
    if ( (int)CMiscHelpersT<CEmptyType>::ParseFileName(*(unsigned __int16 **)(v9 + 8), 0) >= 0 )
    {
      FileAttributesW = GetFileAttributesW(0);
      v13 = FileAttributesW != -1 && (FileAttributesW >> 4) & 1;
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
      if ( !v13 )
        CMiscHelpersT<CEmptyType>::CreateFolderPath(0);
    }
    FileW = CreateFileW(*(LPCWSTR *)(v9 + 8), 0xC0000000, 0, 0, 2u, 0x80u, 0);
LABEL_28:
    if ( FileW != (HANDLE)-1LL )
    {
      *(_DWORD *)(v9 + 16) = 1;
      v11 = (__int64)FileW;
    }
    goto LABEL_31;
  }
  if ( !*(_QWORD *)v9 )
  {
    v15 = CMiscHelpersT<CEmptyType>::CombinePath(*(_QWORD *)(v9 + 8), v2, 0, &v24);
    v3 = v24;
    if ( v15 >= 0 )
    {
      if ( (int)CMiscHelpersT<CEmptyType>::ParseFileName((unsigned __int16 *)v24, 0) >= 0 )
      {
        v16 = GetFileAttributesW(0);
        v17 = v16 != -1 && (v16 >> 4) & 1;
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
        if ( !v17 )
          CMiscHelpersT<CEmptyType>::CreateFolderPath(0);
      }
      FileW = CreateFileW(v3, 0xC0000000, 0, 0, 2u, 0x80u, 0);
      goto LABEL_28;
    }
  }
  v11 = 0;
LABEL_31:
  if ( v3 )
  {
    v18 = GetProcessHeap();
    HeapFree(v18, 0, (LPVOID)(v3 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  v19 = GetProcessHeap();
  HeapFree(v19, 0, (LPVOID)(v2 - 2));
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  return v11;
}

```

## disassembly

```asm
0x14000d200  mov     [rsp-28h+arg_0], rbx
0x14000d205  mov     [rsp-28h+arg_8], rsi
0x14000d20a  push    rbp
0x14000d20b  push    rdi
0x14000d20c  push    r13
0x14000d20e  push    r14
0x14000d210  push    r15
0x14000d212  mov     rbp, rsp
0x14000d215  sub     rsp, 60h
0x14000d219  xor     ebx, ebx
0x14000d21b  xor     r13d, r13d
0x14000d21e  xor     r14d, r14d
0x14000d221  mov     [rbp+lpString1], rbx
0x14000d225  mov     [rbp+arg_18], r13
0x14000d229  mov     rdi, rdx
0x14000d22c  mov     [rbp+lpFileName], r14
0x14000d230  sub     ecx, 2
0x14000d233  jz      short loc_14000D2AD
0x14000d235  cmp     ecx, 1
0x14000d238  jnz     loc_14000D4F8
0x14000d23e  movzx   edx, word ptr [rdx+32h]; wFatTime
0x14000d242  lea     r8, [rbp+FileTime]; lpFileTime
0x14000d246  movzx   ecx, word ptr [rdi+30h]; wFatDate
0x14000d24a  mov     qword ptr [rbp+FileTime.dwLowDateTime], rbx
0x14000d24e  mov     qword ptr [rbp+LastWriteTime.dwLowDateTime], rbx
0x14000d252  call    cs:__imp_DosDateTimeToFileTime
0x14000d259  nop     dword ptr [rax+rax+00h]
0x14000d25e  test    eax, eax
0x14000d260  jz      short loc_14000D293
0x14000d262  lea     rdx, [rbp+LastWriteTime]; lpFileTime
0x14000d266  lea     rcx, [rbp+FileTime]; lpLocalFileTime
0x14000d26a  call    cs:__imp_LocalFileTimeToFileTime
0x14000d271  nop     dword ptr [rax+rax+00h]
0x14000d276  test    eax, eax
0x14000d278  jz      short loc_14000D293
0x14000d27a  mov     rcx, [rdi+28h]; hFile
0x14000d27e  lea     r9, [rbp+LastWriteTime]; lpLastWriteTime
0x14000d282  xor     r8d, r8d; lpLastAccessTime
0x14000d285  xor     edx, edx; lpCreationTime
0x14000d287  call    cs:__imp_SetFileTime
0x14000d28e  nop     dword ptr [rax+rax+00h]
0x14000d293  mov     rcx, [rdi+28h]; hObject
0x14000d297  call    cs:__imp_CloseHandle
0x14000d29e  nop     dword ptr [rax+rax+00h]
0x14000d2a3  mov     eax, 1
0x14000d2a8  jmp     loc_14000D4FA
0x14000d2ad  mov     r15, [rdx+20h]
0x14000d2b1  mov     rdx, [rdx+8]
0x14000d2b5  test    rdx, rdx
0x14000d2b8  jz      loc_14000D4CB
0x14000d2be  lea     r8, [rbp+lpString1]
0x14000d2c2  call    ?MultiByteToWideCharWrap@?$CMiscHelpersT@VCEmptyType@@@@SAJIPEBDPEAPEAG@Z; CMiscHelpersT<CEmptyType>::MultiByteToWideCharWrap(uint,char const *,ushort * *)
0x14000d2c7  mov     rbx, [rbp+lpString1]
0x14000d2cb  test    rbx, rbx
0x14000d2ce  jz      loc_14000D4F8
0x14000d2d4  cmp     [r15+8], r13
0x14000d2d8  jz      loc_14000D4CB
0x14000d2de  mov     rax, [r15]
0x14000d2e1  or      rsi, 0FFFFFFFFFFFFFFFFh
0x14000d2e5  test    rax, rax
0x14000d2e8  jz      loc_14000D37D
0x14000d2ee  mov     [rsp+60h+cchCount2], esi; cchCount2
0x14000d2f2  lea     edx, [rsi+2]; dwCmpFlags
0x14000d2f5  mov     r9d, esi; cchCount1
0x14000d2f8  mov     [rsp+60h+lpString2], rax; lpString2
0x14000d2fd  mov     r8, rbx; lpString1
0x14000d300  mov     ecx, 409h; Locale
0x14000d305  call    cs:__imp_CompareStringW
0x14000d30c  nop     dword ptr [rax+rax+00h]
0x14000d311  cmp     eax, 2
0x14000d314  jnz     short loc_14000D37D
0x14000d316  mov     rcx, [r15+8]; Src
0x14000d31a  lea     r8, [rbp+lpFileName]
0x14000d31e  xor     r9d, r9d
0x14000d321  mov     [rsp+60h+lpString2], r13; __int64
0x14000d326  xor     edx, edx
0x14000d328  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
0x14000d32d  mov     r14, [rbp+lpFileName]
0x14000d331  test    eax, eax
0x14000d333  js      short loc_14000D36F
0x14000d335  mov     rcx, r14; lpFileName
0x14000d338  call    cs:__imp_GetFileAttributesW
0x14000d33f  nop     dword ptr [rax+rax+00h]
0x14000d344  mov     edi, eax
0x14000d346  cmp     eax, 0FFFFFFFFh
0x14000d349  jz      short loc_14000D353
0x14000d34b  shr     edi, 4
0x14000d34e  and     edi, 1
0x14000d351  jmp     short loc_14000D355
0x14000d353  xor     edi, edi
0x14000d355  xor     ecx, ecx
0x14000d357  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000d35c  xor     ecx, ecx
0x14000d35e  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000d363  test    edi, edi
0x14000d365  jnz     short loc_14000D36F
0x14000d367  mov     rcx, r14
0x14000d36a  call    ?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)
0x14000d36f  mov     rcx, [r15+8]
0x14000d373  mov     [rsp+60h+hTemplateFile], r13
0x14000d378  jmp     loc_14000D409
0x14000d37d  cmp     [r15], r13
0x14000d380  jnz     loc_14000D442
0x14000d386  mov     rcx, [r15+8]
0x14000d38a  lea     r9, [rbp+arg_18]
0x14000d38e  xor     r8d, r8d
0x14000d391  mov     rdx, rbx
0x14000d394  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14000d399  mov     r13, [rbp+arg_18]
0x14000d39d  test    eax, eax
0x14000d39f  js      loc_14000D442
0x14000d3a5  xor     r9d, r9d
0x14000d3a8  mov     [rsp+60h+lpString2], r14; __int64
0x14000d3ad  lea     r8, [rbp+lpFileName]
0x14000d3b1  xor     edx, edx
0x14000d3b3  mov     rcx, r13; Src
0x14000d3b6  call    ?ParseFileName@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAHPEAPEAG22@Z; CMiscHelpersT<CEmptyType>::ParseFileName(ushort const *,int *,ushort * *,ushort * *,ushort * *)
0x14000d3bb  mov     r14, [rbp+lpFileName]
0x14000d3bf  test    eax, eax
0x14000d3c1  js      short loc_14000D3FD
0x14000d3c3  mov     rcx, r14; lpFileName
0x14000d3c6  call    cs:__imp_GetFileAttributesW
0x14000d3cd  nop     dword ptr [rax+rax+00h]
0x14000d3d2  mov     edi, eax
0x14000d3d4  cmp     eax, 0FFFFFFFFh
0x14000d3d7  jz      short loc_14000D3E1
0x14000d3d9  shr     edi, 4
0x14000d3dc  and     edi, 1
0x14000d3df  jmp     short loc_14000D3E3
0x14000d3e1  xor     edi, edi
0x14000d3e3  xor     ecx, ecx
0x14000d3e5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000d3ea  xor     ecx, ecx
0x14000d3ec  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000d3f1  test    edi, edi
0x14000d3f3  jnz     short loc_14000D3FD
0x14000d3f5  mov     rcx, r14
0x14000d3f8  call    ?CreateFolderPath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBGPEAU_SECURITY_ATTRIBUTES@@@Z; CMiscHelpersT<CEmptyType>::CreateFolderPath(ushort const *,_SECURITY_ATTRIBUTES *)
0x14000d3fd  mov     [rsp+60h+hTemplateFile], 0; hTemplateFile
0x14000d406  mov     rcx, r13; lpFileName
0x14000d409  xor     r9d, r9d; lpSecurityAttributes
0x14000d40c  mov     [rsp+60h+cchCount2], 80h; dwFlagsAndAttributes
0x14000d414  mov     edx, 0C0000000h; dwDesiredAccess
0x14000d419  mov     dword ptr [rsp+60h+lpString2], 2; dwCreationDisposition
0x14000d421  xor     r8d, r8d; dwShareMode
0x14000d424  call    cs:__imp_CreateFileW
0x14000d42b  nop     dword ptr [rax+rax+00h]
0x14000d430  cmp     rax, rsi
0x14000d433  jz      short loc_14000D444
0x14000d435  mov     dword ptr [r15+10h], 1
0x14000d43d  mov     rsi, rax
0x14000d440  jmp     short loc_14000D444
0x14000d442  xor     esi, esi
0x14000d444  test    r14, r14
0x14000d447  jz      short loc_14000D471
0x14000d449  call    cs:__imp_GetProcessHeap
0x14000d450  nop     dword ptr [rax+rax+00h]
0x14000d455  lea     r8, [r14-4]; lpMem
0x14000d459  xor     edx, edx; dwFlags
0x14000d45b  mov     rcx, rax; hHeap
0x14000d45e  call    cs:__imp_HeapFree
0x14000d465  nop     dword ptr [rax+rax+00h]
0x14000d46a  xor     ecx, ecx
0x14000d46c  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000d471  test    r13, r13
0x14000d474  jz      short loc_14000D49E
0x14000d476  call    cs:__imp_GetProcessHeap
0x14000d47d  nop     dword ptr [rax+rax+00h]
0x14000d482  lea     r8, [r13-4]; lpMem
0x14000d486  xor     edx, edx; dwFlags
0x14000d488  mov     rcx, rax; hHeap
0x14000d48b  call    cs:__imp_HeapFree
0x14000d492  nop     dword ptr [rax+rax+00h]
0x14000d497  xor     ecx, ecx
0x14000d499  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000d49e  call    cs:__imp_GetProcessHeap
0x14000d4a5  nop     dword ptr [rax+rax+00h]
0x14000d4aa  lea     r8, [rbx-4]; lpMem
0x14000d4ae  xor     edx, edx; dwFlags
0x14000d4b0  mov     rcx, rax; hHeap
0x14000d4b3  call    cs:__imp_HeapFree
0x14000d4ba  nop     dword ptr [rax+rax+00h]
0x14000d4bf  xor     ecx, ecx
0x14000d4c1  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000d4c6  mov     rax, rsi
0x14000d4c9  jmp     short loc_14000D4FA
0x14000d4cb  test    rbx, rbx
0x14000d4ce  jz      short loc_14000D4F8
0x14000d4d0  call    cs:__imp_GetProcessHeap
0x14000d4d7  nop     dword ptr [rax+rax+00h]
0x14000d4dc  lea     r8, [rbx-4]; lpMem
0x14000d4e0  xor     edx, edx; dwFlags
0x14000d4e2  mov     rcx, rax; hHeap
0x14000d4e5  call    cs:__imp_HeapFree
0x14000d4ec  nop     dword ptr [rax+rax+00h]
0x14000d4f1  xor     ecx, ecx
0x14000d4f3  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000d4f8  xor     eax, eax
0x14000d4fa  lea     r11, [rsp+60h+var_s0]
0x14000d4ff  mov     rbx, [r11+30h]
0x14000d503  mov     rsi, [r11+38h]
0x14000d507  mov     rsp, r11
0x14000d50a  pop     r15
0x14000d50c  pop     r14
0x14000d50e  pop     r13
0x14000d510  pop     rdi
0x14000d511  pop     rbp
0x14000d512  retn
```
