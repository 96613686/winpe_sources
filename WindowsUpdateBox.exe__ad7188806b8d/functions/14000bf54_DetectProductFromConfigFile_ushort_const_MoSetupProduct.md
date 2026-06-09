# DetectProductFromConfigFile(ushort const *,MoSetupProduct *)

- ea: `0x14000bf54`
- end: `0x14000c204`
- name: `?DetectProductFromConfigFile@@YAJPEBGPEAW4MoSetupProduct@@@Z`
- size: `688`
- prototype: `__int64 __fastcall(const unsigned __int16 *, enum MoSetupProduct *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, registry_config, loader_planting, installer_update, broker_com_uri`

## callers

- `0x140016fa8`

## callees

- `0x1400076c8`
- `0x140007cb0`
- `0x14000bf54`
- `0x1400135b8`
- `0x140016bb4`
- `0x140027950`

## import_xrefs

- `KERNEL32!CloseHandle` at `0x14000c1dd`
- `KERNEL32!CloseHandle` at `0x14000c1dd`
- `KERNEL32!HeapFree` at `0x14000c195`
- `KERNEL32!HeapFree` at `0x14000c1bc`
- `KERNEL32!HeapFree` at `0x14000c195`
- `KERNEL32!HeapFree` at `0x14000c1bc`
- `KERNEL32!GetProcessHeap` at `0x14000c181`
- `KERNEL32!GetProcessHeap` at `0x14000c1a7`
- `KERNEL32!GetProcessHeap` at `0x14000c181`
- `KERNEL32!GetProcessHeap` at `0x14000c1a7`
- `KERNEL32!GetLastError` at `0x14000c096`
- `KERNEL32!GetLastError` at `0x14000c096`
- `KERNEL32!GetFileAttributesW` at `0x14000bfe3`
- `KERNEL32!GetFileAttributesW` at `0x14000bfe3`
- `KERNEL32!CreateFileW` at `0x14000c079`
- `KERNEL32!CreateFileW` at `0x14000c079`
- `KERNEL32!CompareStringW` at `0x14000c156`
- `KERNEL32!CompareStringW` at `0x14000c156`

## string_xrefs

- `0x14000c039`: `DetectProductFromConfigFile`
- `0x14000c0e5`: `DetectProductFromConfigFile`
- `0x14000c040`: `%s: Reading file: [%s]`

## pseudocode

```c
// Hidden C++ exception states: #wind=3
__int64 __fastcall DetectProductFromConfigFile(const unsigned __int16 *a1, enum MoSetupProduct *a2)
{
  int v3; // r12d
  __int64 FileW; // rdi
  WCHAR *Str; // rbx
  int v6; // ecx
  unsigned int v7; // esi
  int v8; // eax
  DWORD FileAttributesW; // eax
  BOOL v10; // ebp
  HANDLE v11; // rcx
  signed int LastError; // eax
  char *v13; // rax
  HANDLE v14; // rcx
  HANDLE v15; // rcx
  HANDLE ProcessHeap; // rax

  v3 = 0;
  FileW = -1;
  Str = 0;
  if ( !a1 || !a2 )
  {
    v6 = -2147024809;
    v7 = -2147024809;
LABEL_3:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_27;
  }
  v8 = CMiscHelpersT<CEmptyType>::CombinePath((__int64)a1, (__int64)L"setupmedia.cfg", 0);
  v7 = v8;
  if ( v8 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v8);
    goto LABEL_27;
  }
  FileAttributesW = GetFileAttributesW(0);
  v10 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v7 = 0;
  if ( v10 )
  {
    v11 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v11 = g_shLogFile;
    OutputMsg(v11, g_shLogEvent, L"%s: Reading file: [%s]", L"DetectProductFromConfigFile", 0);
    FileW = (__int64)CreateFileW(0, 0x80000000, 1u, 0, 3u, 0x80u, 0);
    if ( ((FileW + 1) & 0xFFFFFFFFFFFFFFFEuLL) == 0 )
    {
      FileW = -1;
      LastError = GetLastError();
      v7 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v7 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v7 = -2147467259;
      }
      v6 = v7;
      goto LABEL_3;
    }
    Str = (WCHAR *)IniGetStr(0);
    v13 = (char *)g_shLogFile - 1;
    if ( Str )
    {
      v15 = 0;
      if ( (unsigned __int64)v13 <= 0xFFFFFFFFFFFFFFFDuLL )
        v15 = g_shLogFile;
      OutputMsg(v15, g_shLogEvent, L"%s: Product value: [%s]", L"DetectProductFromConfigFile", Str);
      v3 = CompareStringW(0x409u, 1u, L"azshci", -1, Str, -1) == 2 ? 4 : 0;
    }
    else
    {
      Str = 0;
      v14 = 0;
      if ( (unsigned __int64)v13 <= 0xFFFFFFFFFFFFFFFDuLL )
        v14 = g_shLogFile;
      OutputMsg(v14, g_shLogEvent, L"%s: No Product value found.", L"DetectProductFromConfigFile");
    }
  }
  *(_DWORD *)a2 = v3;
LABEL_27:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v7);
  if ( Str )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, Str);
  }
  if ( (unsigned __int64)(FileW - 1) <= 0xFFFFFFFFFFFFFFFDuLL )
    CloseHandle((HANDLE)FileW);
  return v7;
}

```

## disassembly

```asm
0x14000bf54  mov     rax, rsp
0x14000bf57  push    rbp
0x14000bf58  push    rsi
0x14000bf59  push    rdi
0x14000bf5a  push    r12
0x14000bf5c  push    r13
0x14000bf5e  push    r14
0x14000bf60  push    r15
0x14000bf62  sub     rsp, 50h
0x14000bf66  mov     qword ptr [rax-48h], 0FFFFFFFFFFFFFFFEh
0x14000bf6e  mov     [rax+10h], rbx
0x14000bf72  mov     r15, rdx
0x14000bf75  xor     r12d, r12d
0x14000bf78  or      r13, 0FFFFFFFFFFFFFFFFh
0x14000bf7c  mov     rdi, r13
0x14000bf7f  xor     r14d, r14d
0x14000bf82  mov     [rax+8], r14
0x14000bf86  xor     ebx, ebx
0x14000bf88  mov     [rax+18h], rbx
0x14000bf8c  test    rcx, rcx
0x14000bf8f  jnz     short loc_14000BFA2
0x14000bf91  mov     ecx, 80070057h
0x14000bf96  mov     esi, ecx
0x14000bf98  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000bf9d  jmp     loc_14000C174
0x14000bfa2  test    r15, r15
0x14000bfa5  jz      short loc_14000BF91
0x14000bfa7  lea     r9, [rsp+88h+lpFileName]
0x14000bfaf  xor     r8d, r8d
0x14000bfb2  lea     rdx, aSetupmediaCfg; "setupmedia.cfg"
0x14000bfb9  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEBG00PEAPEAG@Z; CMiscHelpersT<CEmptyType>::CombinePath(ushort const *,ushort const *,ushort const *,ushort * *)
0x14000bfbe  mov     esi, eax
0x14000bfc0  test    eax, eax
0x14000bfc2  jns     short loc_14000BFD8
0x14000bfc4  mov     ecx, eax
0x14000bfc6  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000bfcb  mov     r14, [rsp+88h+lpFileName]
0x14000bfd3  jmp     loc_14000C174
0x14000bfd8  mov     r14, [rsp+88h+lpFileName]
0x14000bfe0  mov     rcx, r14; lpFileName
0x14000bfe3  call    cs:__imp_GetFileAttributesW
0x14000bfea  nop     dword ptr [rax+rax+00h]
0x14000bfef  mov     ebp, eax
0x14000bff1  cmp     eax, 0FFFFFFFFh
0x14000bff4  jz      short loc_14000C000
0x14000bff6  shr     ebp, 4
0x14000bff9  not     ebp
0x14000bffb  and     ebp, 1
0x14000bffe  jmp     short loc_14000C002
0x14000c000  xor     ebp, ebp
0x14000c002  xor     ecx, ecx
0x14000c004  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000c009  xor     ecx, ecx
0x14000c00b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000c010  xor     esi, esi
0x14000c012  test    ebp, ebp
0x14000c014  jz      loc_14000C171
0x14000c01a  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14000c021  lea     rax, [r8-1]
0x14000c025  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000c029  setnbe  al
0x14000c02c  xor     ecx, ecx
0x14000c02e  test    al, al
0x14000c030  cmovz   rcx, r8; hFile
0x14000c034  mov     qword ptr [rsp+88h+dwCreationDisposition], r14
0x14000c039  lea     r9, aDetectproductf; "DetectProductFromConfigFile"
0x14000c040  lea     r8, aSReadingFileS; "%s: Reading file: [%s]"
0x14000c047  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14000c04e  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14000c053  mov     [rsp+88h+hTemplateFile], rsi; hTemplateFile
0x14000c058  mov     [rsp+88h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x14000c060  mov     [rsp+88h+dwCreationDisposition], 3; dwCreationDisposition
0x14000c068  xor     r9d, r9d; lpSecurityAttributes
0x14000c06b  lea     ebp, [rsi+1]
0x14000c06e  mov     r8d, ebp; dwShareMode
0x14000c071  mov     edx, 80000000h; dwDesiredAccess
0x14000c076  mov     rcx, r14; lpFileName
0x14000c079  call    cs:__imp_CreateFileW
0x14000c080  nop     dword ptr [rax+rax+00h]
0x14000c085  mov     rdi, rax
0x14000c088  inc     rax
0x14000c08b  test    rax, 0FFFFFFFFFFFFFFFEh
0x14000c091  jnz     short loc_14000C0C1
0x14000c093  mov     rdi, r13
0x14000c096  call    cs:__imp_GetLastError
0x14000c09d  nop     dword ptr [rax+rax+00h]
0x14000c0a2  mov     esi, eax
0x14000c0a4  test    eax, eax
0x14000c0a6  jnz     short loc_14000C0AF
0x14000c0a8  mov     esi, 80004005h
0x14000c0ad  jmp     short loc_14000C0BA
0x14000c0af  jle     short loc_14000C0BA
0x14000c0b1  movzx   esi, ax
0x14000c0b4  or      esi, 80070000h
0x14000c0ba  mov     ecx, esi
0x14000c0bc  jmp     loc_14000BF98
0x14000c0c1  mov     [rsp+88h+arg_18], rdi
0x14000c0c9  xor     r9d, r9d
0x14000c0cc  lea     r8, aProduct; "product"
0x14000c0d3  mov     rcx, r14; lpFileName
0x14000c0d6  call    IniGetStr
0x14000c0db  mov     rbx, rax
0x14000c0de  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14000c0e5  lea     r9, aDetectproductf; "DetectProductFromConfigFile"
0x14000c0ec  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14000c0f3  test    rax, rax
0x14000c0f6  lea     rax, [r8-1]
0x14000c0fa  jnz     short loc_14000C11B
0x14000c0fc  xor     ebx, ebx
0x14000c0fe  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000c102  setnbe  al
0x14000c105  xor     ecx, ecx
0x14000c107  test    al, al
0x14000c109  cmovz   rcx, r8; hFile
0x14000c10d  lea     r8, aSNoProductValu; "%s: No Product value found."
0x14000c114  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14000c119  jmp     short loc_14000C171
0x14000c11b  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000c11f  setnbe  al
0x14000c122  xor     ecx, ecx
0x14000c124  test    al, al
0x14000c126  cmovz   rcx, r8; hFile
0x14000c12a  mov     qword ptr [rsp+88h+dwCreationDisposition], rbx
0x14000c12f  lea     r8, aSProductValueS; "%s: Product value: [%s]"
0x14000c136  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14000c13b  mov     [rsp+88h+dwFlagsAndAttributes], r13d; cchCount2
0x14000c140  mov     qword ptr [rsp+88h+dwCreationDisposition], rbx; lpString2
0x14000c145  mov     r9d, r13d; cchCount1
0x14000c148  lea     r8, String1; "azshci"
0x14000c14f  mov     edx, ebp; dwCmpFlags
0x14000c151  mov     ecx, 409h; Locale
0x14000c156  call    cs:__imp_CompareStringW
0x14000c15d  nop     dword ptr [rax+rax+00h]
0x14000c162  sub     eax, 2
0x14000c165  neg     eax
0x14000c167  sbb     r12d, r12d
0x14000c16a  not     r12d
0x14000c16d  and     r12d, 4
0x14000c171  mov     [r15], r12d
0x14000c174  mov     ecx, esi
0x14000c176  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000c17b  nop
0x14000c17c  test    rbx, rbx
0x14000c17f  jz      short loc_14000C1A2
0x14000c181  call    cs:__imp_GetProcessHeap
0x14000c188  nop     dword ptr [rax+rax+00h]
0x14000c18d  mov     rcx, rax; hHeap
0x14000c190  mov     r8, rbx; lpMem
0x14000c193  xor     edx, edx; dwFlags
0x14000c195  call    cs:__imp_HeapFree
0x14000c19c  nop     dword ptr [rax+rax+00h]
0x14000c1a1  nop
0x14000c1a2  test    r14, r14
0x14000c1a5  jz      short loc_14000C1D0
0x14000c1a7  call    cs:__imp_GetProcessHeap
0x14000c1ae  nop     dword ptr [rax+rax+00h]
0x14000c1b3  mov     rcx, rax; hHeap
0x14000c1b6  lea     r8, [r14-4]; lpMem
0x14000c1ba  xor     edx, edx; dwFlags
0x14000c1bc  call    cs:__imp_HeapFree
0x14000c1c3  nop     dword ptr [rax+rax+00h]
0x14000c1c8  xor     ecx, ecx
0x14000c1ca  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000c1cf  nop
0x14000c1d0  lea     rax, [rdi-1]
0x14000c1d4  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000c1d8  ja      short loc_14000C1E9
0x14000c1da  mov     rcx, rdi; hObject
0x14000c1dd  call    cs:__imp_CloseHandle
0x14000c1e4  nop     dword ptr [rax+rax+00h]
0x14000c1e9  mov     eax, esi
0x14000c1eb  mov     rbx, [rsp+88h+arg_8]
0x14000c1f3  add     rsp, 50h
0x14000c1f7  pop     r15
0x14000c1f9  pop     r14
0x14000c1fb  pop     r13
0x14000c1fd  pop     r12
0x14000c1ff  pop     rdi
0x14000c200  pop     rsi
0x14000c201  pop     rbp
0x14000c202  retn
```
