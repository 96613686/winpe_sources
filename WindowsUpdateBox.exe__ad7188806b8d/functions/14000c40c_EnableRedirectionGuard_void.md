# EnableRedirectionGuard(void)

- ea: `0x14000c40c`
- end: `0x14000c593`
- name: `?EnableRedirectionGuard@@YAJXZ`
- size: `391`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `registry_config, loader_planting`

## callers

- `0x140021744`

## callees

- `0x1400076c8`
- `0x14000c40c`
- `0x1400135b8`
- `0x140016bb4`
- `0x140082010`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x14000c579`
- `KERNEL32!FreeLibrary` at `0x14000c579`
- `KERNEL32!LoadLibraryExW` at `0x14000c439`
- `KERNEL32!LoadLibraryExW` at `0x14000c439`
- `KERNEL32!GetProcAddress` at `0x14000c48c`
- `KERNEL32!GetProcAddress` at `0x14000c48c`
- `KERNEL32!GetLastError` at `0x14000c44d`
- `KERNEL32!GetLastError` at `0x14000c4f3`
- `KERNEL32!GetLastError` at `0x14000c44d`
- `KERNEL32!GetLastError` at `0x14000c4f3`

## string_xrefs

- `0x14000c432`: `Kernel32.dll`

## pseudocode

```c
__int64 EnableRedirectionGuard(void)
{
  unsigned int v0; // edi
  HMODULE Library; // rax
  HMODULE v2; // rbx
  signed int LastError; // eax
  FARPROC ProcAddress; // rax
  HANDLE v5; // rcx
  __int64 v6; // rcx
  signed int v7; // eax
  char *v8; // rax
  HANDLE v9; // rcx
  HANDLE v10; // rcx
  int v12; // [rsp+40h] [rbp+8h] BYREF
  HMODULE v13; // [rsp+48h] [rbp+10h]

  v12 = 0;
  v0 = 0;
  Library = LoadLibraryExW(L"Kernel32.dll", 0, 0x800u);
  v2 = Library;
  if ( !Library )
  {
    LastError = GetLastError();
    v0 = LastError;
    if ( LastError )
    {
      if ( LastError > 0 )
        v0 = (unsigned __int16)LastError | 0x80070000;
    }
    else
    {
      v0 = -2147467259;
    }
LABEL_21:
    v6 = v0;
    goto LABEL_22;
  }
  v13 = Library;
  ProcAddress = GetProcAddress(Library, "SetProcessMitigationPolicy");
  if ( !ProcAddress )
  {
    v5 = 0;
    if ( (char *)g_shLogFile - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
      v5 = g_shLogFile;
    OutputMsg(v5, g_shLogEvent, L"SetProcessMitigationPolicy is not supported");
LABEL_10:
    v6 = 2147942450LL;
    v0 = -2147024846;
LABEL_22:
    CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(v6);
    goto LABEL_23;
  }
  v12 |= 1u;
  if ( ((unsigned int (__fastcall *)(__int64, int *))ProcAddress)(16, &v12) )
    goto LABEL_23;
  v7 = GetLastError();
  v0 = v7;
  if ( v7 > 0 )
    v0 = (unsigned __int16)v7 | 0x80070000;
  v8 = (char *)g_shLogFile - 1;
  if ( v0 == -2147024809 )
  {
    v9 = 0;
    if ( (unsigned __int64)v8 <= 0xFFFFFFFFFFFFFFFDuLL )
      v9 = g_shLogFile;
    OutputMsg(v9, g_shLogEvent, L"SetProcessMitigationPolicy does not support this mitigation policy");
    goto LABEL_10;
  }
  v10 = 0;
  if ( (unsigned __int64)v8 <= 0xFFFFFFFFFFFFFFFDuLL )
    v10 = g_shLogFile;
  OutputMsg(v10, g_shLogEvent, L"SetProcessMitigationPolicy failed with error [0x%08x]", v0, -2);
  if ( (v0 & 0x80000000) != 0 )
    goto LABEL_21;
LABEL_23:
  CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(v0);
  if ( v2 )
    FreeLibrary(v2);
  return v0;
}

```

## disassembly

```asm
0x14000c40c  push    rdi
0x14000c40e  sub     rsp, 30h
0x14000c412  mov     [rsp+38h+var_18], 0FFFFFFFFFFFFFFFEh
0x14000c41b  mov     [rsp+38h+arg_10], rbx
0x14000c420  mov     [rsp+38h+arg_0], 0
0x14000c428  xor     edi, edi
0x14000c42a  xor     edx, edx; hFile
0x14000c42c  mov     r8d, 800h; dwFlags
0x14000c432  lea     rcx, LibFileName; "Kernel32.dll"
0x14000c439  call    cs:__imp_LoadLibraryExW
0x14000c440  nop     dword ptr [rax+rax+00h]
0x14000c445  mov     rbx, rax
0x14000c448  test    rax, rax
0x14000c44b  jnz     short loc_14000C47D
0x14000c44d  call    cs:__imp_GetLastError
0x14000c454  nop     dword ptr [rax+rax+00h]
0x14000c459  mov     edi, eax
0x14000c45b  test    eax, eax
0x14000c45d  jnz     short loc_14000C469
0x14000c45f  mov     edi, 80004005h
0x14000c464  jmp     loc_14000C562
0x14000c469  jle     loc_14000C562
0x14000c46f  movzx   edi, ax
0x14000c472  or      edi, 80070000h
0x14000c478  jmp     loc_14000C562
0x14000c47d  mov     [rsp+38h+arg_8], rax
0x14000c482  lea     rdx, aSetprocessmiti_0; "SetProcessMitigationPolicy"
0x14000c489  mov     rcx, rax; hModule
0x14000c48c  call    cs:__imp_GetProcAddress
0x14000c493  nop     dword ptr [rax+rax+00h]
0x14000c498  test    rax, rax
0x14000c49b  jnz     short loc_14000C4D6
0x14000c49d  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14000c4a4  lea     rax, [r8-1]
0x14000c4a8  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000c4ac  setnbe  al
0x14000c4af  xor     ecx, ecx
0x14000c4b1  test    al, al
0x14000c4b3  cmovz   rcx, r8; hFile
0x14000c4b7  lea     r8, aSetprocessmiti_1; "SetProcessMitigationPolicy is not suppo"...
0x14000c4be  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14000c4c5  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14000c4ca  mov     ecx, 80070032h
0x14000c4cf  mov     edi, ecx
0x14000c4d1  jmp     loc_14000C564
0x14000c4d6  or      [rsp+38h+arg_0], 1
0x14000c4db  mov     r8d, 4
0x14000c4e1  lea     rdx, [rsp+38h+arg_0]
0x14000c4e6  lea     ecx, [r8+0Ch]
0x14000c4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c4ef  test    eax, eax
0x14000c4f1  jnz     short loc_14000C569
0x14000c4f3  call    cs:__imp_GetLastError
0x14000c4fa  nop     dword ptr [rax+rax+00h]
0x14000c4ff  mov     edi, eax
0x14000c501  test    eax, eax
0x14000c503  jle     short loc_14000C50E
0x14000c505  movzx   edi, ax
0x14000c508  or      edi, 80070000h
0x14000c50e  mov     r8, cs:?g_shLogFile@@3VSH_FILENT@@A; SH_FILENT g_shLogFile
0x14000c515  mov     rdx, cs:?g_shLogEvent@@3VSH_HANDLE@@A; hEvent
0x14000c51c  lea     rax, [r8-1]
0x14000c520  cmp     edi, 80070057h
0x14000c526  jnz     short loc_14000C540
0x14000c528  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000c52c  setnbe  al
0x14000c52f  xor     ecx, ecx
0x14000c531  test    al, al
0x14000c533  cmovz   rcx, r8
0x14000c537  lea     r8, aSetprocessmiti_2; "SetProcessMitigationPolicy does not sup"...
0x14000c53e  jmp     short loc_14000C4C5
0x14000c540  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x14000c544  setnbe  al
0x14000c547  xor     ecx, ecx
0x14000c549  test    al, al
0x14000c54b  cmovz   rcx, r8; hFile
0x14000c54f  mov     r9d, edi
0x14000c552  lea     r8, aSetprocessmiti; "SetProcessMitigationPolicy failed with "...
0x14000c559  call    ?OutputMsg@@YAXPEAX0PEBGZZ; OutputMsg(void *,void *,ushort const *,...)
0x14000c55e  test    edi, edi
0x14000c560  jns     short loc_14000C569
0x14000c562  mov     ecx, edi
0x14000c564  call    ?CheckToBreakOnFailure@?$CBreakOnFailureT@VCEmptyType@@@@SAXJ@Z; CBreakOnFailureT<CEmptyType>::CheckToBreakOnFailure(long)
0x14000c569  mov     ecx, edi
0x14000c56b  call    ?LogHResultEvent@?$CChkMacroETWLoggerT@VCEmptyType@@@@SAXJ@Z; CChkMacroETWLoggerT<CEmptyType>::LogHResultEvent(long)
0x14000c570  nop
0x14000c571  test    rbx, rbx
0x14000c574  jz      short loc_14000C585
0x14000c576  mov     rcx, rbx; hLibModule
0x14000c579  call    cs:__imp_FreeLibrary
0x14000c580  nop     dword ptr [rax+rax+00h]
0x14000c585  mov     eax, edi
0x14000c587  mov     rbx, [rsp+38h+arg_10]
0x14000c58c  add     rsp, 30h
0x14000c590  pop     rdi
0x14000c591  retn
```
