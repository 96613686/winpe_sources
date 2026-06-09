# CUpdateDiagnostics::CheckExistingLogFile(wchar_t const *)

- ea: `0x180039114`
- end: `0x18003932d`
- name: `?CheckExistingLogFile@CUpdateDiagnostics@@AEAAXPEB_W@Z`
- size: `537`
- prototype: `void __fastcall(CUpdateDiagnostics *__hidden this, const wchar_t *)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, service_task, installer_update, broker_com_uri`

## callers

- `0x18006cf10`

## callees

- `0x1800059d0`
- `0x180039114`
- `0x180039f90`
- `0x18003c418`
- `0x18005e9e8`
- `0x1800674f0`
- `0x180077664`

## import_xrefs

- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003926a`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18003926a`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003919d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18003919d`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800392b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800392de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800392b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800392de`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800392c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800392f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800392c6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800392f3`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003927a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18003927a`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180039257`
- `api-ms-win-core-kernel32-legacy-l1-1-0!CopyFileW` at `0x180039257`

## string_xrefs

- `0x18003916f`: `UpdateAgent.log`
- `0x180039226`: `UpdateAgent.Old.log`

## pseudocode

```c
void __fastcall CUpdateDiagnostics::CheckExistingLogFile(CUpdateDiagnostics *this, const wchar_t *a2)
{
  const WCHAR *v3; // rsi
  LPCWSTR v4; // r14
  unsigned int v5; // edi
  int v6; // eax
  DWORD FileAttributesW; // eax
  BOOL v8; // ebx
  __int64 v9; // rcx
  __int64 v10; // rbx
  int FileSize; // eax
  __int64 v12; // rcx
  int v13; // eax
  signed int LastError; // eax
  HANDLE ProcessHeap; // rax
  HANDLE v16; // rax
  unsigned int v17; // [rsp+20h] [rbp-48h] BYREF
  LPCWSTR lpFileName; // [rsp+28h] [rbp-40h] BYREF
  LPCWSTR lpNewFileName[2]; // [rsp+30h] [rbp-38h] BYREF
  __int64 v20; // [rsp+40h] [rbp-28h] BYREF

  lpNewFileName[1] = (LPCWSTR)-2LL;
  v3 = 0;
  lpFileName = 0;
  v4 = 0;
  lpNewFileName[0] = 0;
  v20 = 0;
  v17 = 0;
  if ( !a2 )
  {
    v5 = -2147024809;
LABEL_22:
    v12 = v5;
    goto LABEL_23;
  }
  v6 = CMiscHelpersT<CEmptyType>::CombinePath(a2, L"UpdateAgent.log", 0, &lpFileName);
  v5 = v6;
  if ( v6 < 0 )
  {
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v6);
    v3 = lpFileName;
    goto LABEL_24;
  }
  v3 = lpFileName;
  FileAttributesW = GetFileAttributesW(lpFileName);
  v8 = FileAttributesW != -1 && (FileAttributesW & 0x10) == 0;
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  v5 = 0;
  if ( v8 )
  {
    v10 = 5242880;
    if ( (int)CRegUtilT<unsigned long,CRegType,0,1>::GetValue(v9, L"SYSTEM\\Setup\\MoSetup", L"UAMaxLogFileSize", &v17) >= 0 )
      v10 = v17;
    FileSize = CMoUpdateHelpersT<CEmptyType>::GetFileSize(v3, &v20);
    v5 = FileSize;
    if ( FileSize < 0 )
    {
      v12 = (unsigned int)FileSize;
LABEL_23:
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v12);
      goto LABEL_24;
    }
    if ( v10 >= v20 )
      goto LABEL_24;
    v13 = CMiscHelpersT<CEmptyType>::CombinePath(a2, L"UpdateAgent.Old.log", 0, lpNewFileName);
    v5 = v13;
    if ( v13 < 0 )
    {
      CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure((unsigned int)v13);
      v4 = lpNewFileName[0];
      goto LABEL_24;
    }
    v4 = lpNewFileName[0];
    if ( !CopyFileW(v3, lpNewFileName[0], 0) || !DeleteFileW(v3) )
    {
      LastError = GetLastError();
      v5 = LastError;
      if ( LastError )
      {
        if ( LastError > 0 )
          v5 = (unsigned __int16)LastError | 0x80070000;
      }
      else
      {
        v5 = -2147467259;
      }
      goto LABEL_22;
    }
  }
LABEL_24:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v5);
  if ( v4 )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, (LPVOID)(v4 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
  if ( v3 )
  {
    v16 = GetProcessHeap();
    HeapFree(v16, 0, (LPVOID)(v3 - 2));
    CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(0);
  }
}

```

## disassembly

```asm
0x180039114  mov     r11, rsp
0x180039117  push    rdi
0x180039118  push    r14
0x18003911a  push    r15
0x18003911c  sub     rsp, 50h
0x180039120  mov     qword ptr [r11-30h], 0FFFFFFFFFFFFFFFEh
0x180039128  mov     [r11+8], rbx
0x18003912c  mov     [r11+18h], rsi
0x180039130  mov     rax, cs:__security_cookie
0x180039137  xor     rax, rsp
0x18003913a  mov     [rsp+68h+var_20], rax
0x18003913f  mov     r15, rdx
0x180039142  xor     esi, esi
0x180039144  mov     [rsp+68h+lpFileName], rsi
0x180039149  xor     r14d, r14d
0x18003914c  mov     [r11-38h], r14
0x180039150  mov     [r11-28h], rsi
0x180039154  mov     [rsp+68h+var_48], esi
0x180039158  test    rdx, rdx
0x18003915b  jnz     short loc_180039167
0x18003915d  mov     edi, 80070057h
0x180039162  jmp     loc_18003929E
0x180039167  lea     r9, [rsp+68h+lpFileName]
0x18003916c  xor     r8d, r8d
0x18003916f  lea     rdx, aUpdateagentLog; "UpdateAgent.log"
0x180039176  mov     rcx, r15
0x180039179  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x18003917e  mov     edi, eax
0x180039180  test    eax, eax
0x180039182  jns     short loc_180039195
0x180039184  mov     ecx, eax
0x180039186  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x18003918b  mov     rsi, [rsp+68h+lpFileName]
0x180039190  jmp     loc_1800392A5
0x180039195  mov     rsi, [rsp+68h+lpFileName]
0x18003919a  mov     rcx, rsi; lpFileName
0x18003919d  call    cs:__imp_GetFileAttributesW
0x1800391a4  nop     dword ptr [rax+rax+00h]
0x1800391a9  mov     ebx, eax
0x1800391ab  cmp     eax, 0FFFFFFFFh
0x1800391ae  jz      short loc_1800391BA
0x1800391b0  shr     ebx, 4
0x1800391b3  not     ebx
0x1800391b5  and     ebx, 1
0x1800391b8  jmp     short loc_1800391BC
0x1800391ba  xor     ebx, ebx
0x1800391bc  xor     ecx, ecx
0x1800391be  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800391c3  xor     ecx, ecx
0x1800391c5  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800391ca  xor     edi, edi
0x1800391cc  test    ebx, ebx
0x1800391ce  jz      loc_1800392A5
0x1800391d4  mov     ebx, 500000h
0x1800391d9  lea     r9, [rsp+68h+var_48]
0x1800391de  lea     r8, aUamaxlogfilesi; "UAMaxLogFileSize"
0x1800391e5  lea     rdx, aSystemSetupMos_0; "SYSTEM\\Setup\\MoSetup"
0x1800391ec  call    ?GetValue@?$CRegUtilT@KUCRegType@@$0A@$00@@SAJPEAUHKEY__@@PEB_W1PEAK@Z; CRegUtilT<ulong,CRegType,0,1>::GetValue(HKEY__ *,wchar_t const *,wchar_t const *,ulong *)
0x1800391f1  test    eax, eax
0x1800391f3  js      short loc_1800391F9
0x1800391f5  mov     ebx, [rsp+68h+var_48]
0x1800391f9  lea     rdx, [rsp+68h+var_28]
0x1800391fe  mov     rcx, rsi
0x180039201  call    ?GetFileSize@?$CMoUpdateHelpersT@VCEmptyType@@@@SAJPEB_WPEAT_LARGE_INTEGER@@@Z; CMoUpdateHelpersT<CEmptyType>::GetFileSize(wchar_t const *,_LARGE_INTEGER *)
0x180039206  mov     edi, eax
0x180039208  test    eax, eax
0x18003920a  jns     short loc_180039213
0x18003920c  mov     ecx, eax
0x18003920e  jmp     loc_1800392A0
0x180039213  cmp     rbx, [rsp+68h+var_28]
0x180039218  jge     loc_1800392A5
0x18003921e  lea     r9, [rsp+68h+lpNewFileName]
0x180039223  xor     r8d, r8d
0x180039226  lea     rdx, aUpdateagentOld; "UpdateAgent.Old.log"
0x18003922d  mov     rcx, r15
0x180039230  call    ?CombinePath@?$CMiscHelpersT@VCEmptyType@@@@SAJPEB_W00PEAPEA_W@Z; CMiscHelpersT<CEmptyType>::CombinePath(wchar_t const *,wchar_t const *,wchar_t const *,wchar_t * *)
0x180039235  mov     edi, eax
0x180039237  test    eax, eax
0x180039239  jns     short loc_180039249
0x18003923b  mov     ecx, eax
0x18003923d  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x180039242  mov     r14, [rsp+68h+lpNewFileName]
0x180039247  jmp     short loc_1800392A5
0x180039249  mov     r14, [rsp+68h+lpNewFileName]
0x18003924e  xor     r8d, r8d; bFailIfExists
0x180039251  mov     rdx, r14; lpNewFileName
0x180039254  mov     rcx, rsi; lpExistingFileName
0x180039257  call    cs:__imp_CopyFileW
0x18003925e  nop     dword ptr [rax+rax+00h]
0x180039263  test    eax, eax
0x180039265  jz      short loc_18003927A
0x180039267  mov     rcx, rsi; lpFileName
0x18003926a  call    cs:__imp_DeleteFileW
0x180039271  nop     dword ptr [rax+rax+00h]
0x180039276  test    eax, eax
0x180039278  jnz     short loc_1800392A5
0x18003927a  call    cs:__imp_GetLastError
0x180039281  nop     dword ptr [rax+rax+00h]
0x180039286  mov     edi, eax
0x180039288  test    eax, eax
0x18003928a  jnz     short loc_180039293
0x18003928c  mov     edi, 80004005h
0x180039291  jmp     short loc_18003929E
0x180039293  jle     short loc_18003929E
0x180039295  movzx   edi, ax
0x180039298  or      edi, 80070000h
0x18003929e  mov     ecx, edi
0x1800392a0  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x1800392a5  mov     ecx, edi
0x1800392a7  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800392ac  test    r14, r14
0x1800392af  jz      short loc_1800392D9
0x1800392b1  call    cs:__imp_GetProcessHeap
0x1800392b8  nop     dword ptr [rax+rax+00h]
0x1800392bd  mov     rcx, rax; hHeap
0x1800392c0  lea     r8, [r14-4]; lpMem
0x1800392c4  xor     edx, edx; dwFlags
0x1800392c6  call    cs:__imp_HeapFree
0x1800392cd  nop     dword ptr [rax+rax+00h]
0x1800392d2  xor     ecx, ecx
0x1800392d4  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x1800392d9  test    rsi, rsi
0x1800392dc  jz      short loc_180039307
0x1800392de  call    cs:__imp_GetProcessHeap
0x1800392e5  nop     dword ptr [rax+rax+00h]
0x1800392ea  mov     rcx, rax; hHeap
0x1800392ed  lea     r8, [rsi-4]; lpMem
0x1800392f1  xor     edx, edx; dwFlags
0x1800392f3  call    cs:__imp_HeapFree
0x1800392fa  nop     dword ptr [rax+rax+00h]
0x1800392ff  xor     ecx, ecx
0x180039301  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x180039306  nop
0x180039307  jmp     short $+2
0x180039309  mov     rcx, [rsp+68h+var_20]
0x18003930e  xor     rcx, rsp; StackCookie
0x180039311  call    __security_check_cookie
0x180039316  lea     r11, [rsp+68h+var_18]
0x18003931b  mov     rbx, [r11+20h]
0x18003931f  mov     rsi, [r11+30h]
0x180039323  mov     rsp, r11
0x180039326  pop     r15
0x180039328  pop     r14
0x18003932a  pop     rdi
0x18003932b  retn
```
