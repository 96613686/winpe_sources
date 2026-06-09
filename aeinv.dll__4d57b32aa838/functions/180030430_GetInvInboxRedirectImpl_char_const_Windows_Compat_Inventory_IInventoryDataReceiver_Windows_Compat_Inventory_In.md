# GetInvInboxRedirectImpl(char const *,Windows::Compat::Inventory::IInventoryDataReceiver *,Windows::Compat::Inventory::InventoryControlParams *,char const *)

- ea: `0x180030430`
- end: `0x18003075c`
- name: `?GetInvInboxRedirectImpl@@YAJPEBDPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAUInventoryControlParams@234@0@Z`
- size: `812`
- prototype: `__int64 __fastcall(LPCSTR lpProcName, struct Windows::Compat::Inventory::IInventoryDataReceiver *, struct Windows::Compat::Inventory::InventoryControlParams *, const char *)`
- caller_count: `1`
- callee_count: `10`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180031a40`

## callees

- `0x1800197d4`
- `0x18002e780`
- `0x180030430`
- `0x1800454f4`
- `0x18004f970`
- `0x18005451c`
- `0x180059920`
- `0x18005a8bc`
- `0x180114ef0`
- `0x180130010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180030604`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x180030604`
- `KERNEL32!GetModuleFileNameW` at `0x180030574`
- `KERNEL32!GetModuleFileNameW` at `0x180030574`
- `KERNEL32!GetSystemDirectoryW` at `0x1800304b3`
- `KERNEL32!GetSystemDirectoryW` at `0x1800304b3`
- `KERNEL32!LoadLibraryExW` at `0x18003064e`
- `KERNEL32!LoadLibraryExW` at `0x18003064e`
- `KERNEL32!FreeLibrary` at `0x1800306d4`
- `KERNEL32!FreeLibrary` at `0x1800306d4`
- `KERNEL32!GetProcAddress` at `0x180030666`
- `KERNEL32!GetProcAddress` at `0x180030666`
- `KERNEL32!GetLastError` at `0x18003053e`
- `KERNEL32!GetLastError` at `0x180030586`
- `KERNEL32!GetLastError` at `0x1800306dc`
- `KERNEL32!GetLastError` at `0x180030700`
- `KERNEL32!GetLastError` at `0x18003053e`
- `KERNEL32!GetLastError` at `0x180030586`
- `KERNEL32!GetLastError` at `0x1800306dc`
- `KERNEL32!GetLastError` at `0x180030700`
- `KERNEL32!GetModuleHandleExW` at `0x180030534`
- `KERNEL32!GetModuleHandleExW` at `0x180030534`
- `SHLWAPI!PathFindFileNameW` at `0x18003059c`
- `SHLWAPI!PathFindFileNameW` at `0x18003059c`

## string_xrefs

- `0x180030715`: `GetSystemDirectory failed %#x`
- `0x1800304da`: `GetInvModuleInPath failed %#x`
- `0x1800305fa`: `aeinv.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=35
__int64 __fastcall GetInvInboxRedirectImpl(
        LPCSTR lpProcName,
        struct Windows::Compat::Inventory::IInventoryDataReceiver *a2,
        struct Windows::Compat::Inventory::InventoryControlParams *a3,
        const char *a4)
{
  int InvModuleInPath; // eax
  unsigned __int64 v8; // rdx
  signed int v9; // ebx
  const char *v10; // r9
  int v11; // r8d
  signed int v12; // eax
  DWORD ModuleFileNameW; // eax
  const unsigned __int16 *FileNameW; // rdi
  unsigned __int64 v15; // rdx
  int v16; // eax
  unsigned int v17; // ebx
  HMODULE Library; // rax
  HMODULE v19; // rsi
  FARPROC ProcAddress; // r14
  signed int v21; // eax
  signed int LastError; // eax
  int v24; // [rsp+30h] [rbp-D0h] BYREF
  unsigned int v25; // [rsp+34h] [rbp-CCh] BYREF
  int v26; // [rsp+38h] [rbp-C8h] BYREF
  HMODULE phModule; // [rsp+40h] [rbp-C0h] BYREF
  const char *v28; // [rsp+48h] [rbp-B8h]
  WCHAR Buffer[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Filename[264]; // [rsp+260h] [rbp+160h] BYREF

  v28 = a4;
  memset_0(Filename, 0, 0x208u);
  memset_0(Buffer, 0, 0x208u);
  v24 = 0;
  v26 = 0;
  v25 = 0;
  phModule = 0;
  if ( GetSystemDirectoryW(Buffer, 0x104u) - 1 > 0x102 )
  {
    LastError = GetLastError();
    v9 = LastError;
    if ( LastError > 0 )
      v9 = (unsigned __int16)LastError | 0x80070000;
    v10 = "GetSystemDirectory failed %#x";
    v11 = 171;
    goto LABEL_36;
  }
  InvModuleInPath = GetInvModuleInPath(Buffer);
  v9 = InvModuleInPath;
  if ( InvModuleInPath < 0 )
  {
    v10 = "GetInvModuleInPath failed %#x";
    v11 = 178;
LABEL_36:
    AslLogCallPrintf(1, (unsigned int)"GetInvInboxRedirectImpl", v11, (_DWORD)v10);
    return (unsigned int)v9;
  }
  if ( !InvModuleInPath )
    return 1;
  v9 = StringCchCatW(Buffer, v8, L"\\");
  if ( v9 < 0 )
  {
    v10 = "StringCchCat failed %#x";
    v11 = 194;
    goto LABEL_36;
  }
  if ( !GetModuleHandleExW(6u, (LPCWSTR)GetInvInboxRedirectImpl, &phModule) )
  {
    v12 = GetLastError();
    v9 = v12;
    if ( v12 > 0 )
      v9 = (unsigned __int16)v12 | 0x80070000;
    v10 = "GetModuleHandleEx failed %#x";
    v11 = 201;
    goto LABEL_36;
  }
  ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x104u);
  if ( !ModuleFileNameW || ModuleFileNameW >= 0x104 && GetLastError() == 122 )
  {
    v21 = GetLastError();
    v9 = v21;
    if ( v21 > 0 )
      v9 = (unsigned __int16)v21 | 0x80070000;
    v10 = "GetModuleFileName failed %#x";
    v11 = 210;
    goto LABEL_36;
  }
  FileNameW = PathFindFileNameW(Filename);
  v9 = StringCchCatW(Buffer, v15, FileNameW);
  if ( v9 < 0 )
  {
    v10 = "StringCchCat failed %#x";
    v11 = 219;
    goto LABEL_36;
  }
  if ( (int)AslFileGetVersionForPath(&v24, &v26, &v25, Buffer) >= 0
    && v24 == 10
    && ((v16 = _o__wcsicmp(FileNameW, L"aeinv.dll"), v17 = v25, v16)
     || v25 - 16350 > 9 && v25 - 15157 > 0x468 && v25 - 18895 > 0x24)
    && (Library = LoadLibraryExW(Buffer, 0, 0x800u), (v19 = Library) != 0) )
  {
    ProcAddress = GetProcAddress(Library, lpProcName);
    if ( ProcAddress )
    {
      v9 = ShouldRedirectProceed(FileNameW, v17);
      if ( !v9 )
      {
        v9 = ((__int64 (__fastcall *)(struct Windows::Compat::Inventory::IInventoryDataReceiver *, struct Windows::Compat::Inventory::InventoryControlParams *, const char *))ProcAddress)(
               a2,
               a3,
               v28);
        ClearAbortRedirect(FileNameW);
        if ( v9 < 0 )
          AslLogCallPrintf(1, (unsigned int)"GetInvInboxRedirectImpl", 288, (unsigned int)"%s failed %#x");
      }
    }
    else
    {
      v9 = 1;
    }
    FreeLibrary(v19);
  }
  else
  {
    return 1;
  }
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x180030430  push    rbp
0x180030432  push    rbx
0x180030433  push    rsi
0x180030434  push    rdi
0x180030435  push    r12
0x180030437  push    r13
0x180030439  push    r14
0x18003043b  push    r15
0x18003043d  lea     rbp, [rsp-388h]
0x180030445  sub     rsp, 488h
0x18003044c  mov     rax, cs:__security_cookie
0x180030453  xor     rax, rsp
0x180030456  mov     [rbp+3C0h+var_50], rax
0x18003045d  mov     r13, r8
0x180030460  mov     [rsp+4C0h+var_478], r9
0x180030465  mov     r12, rdx
0x180030468  mov     r15, rcx
0x18003046b  mov     ebx, 208h
0x180030470  lea     rcx, [rbp+3C0h+Filename]; void *
0x180030477  mov     r8d, ebx; Size
0x18003047a  xor     edx, edx; Val
0x18003047c  call    memset_0
0x180030481  mov     r8d, ebx; Size
0x180030484  lea     rcx, [rsp+4C0h+Buffer]; void *
0x180030489  xor     edx, edx; Val
0x18003048b  call    memset_0
0x180030490  xor     r14d, r14d
0x180030493  lea     rcx, [rsp+4C0h+Buffer]; lpBuffer
0x180030498  mov     edi, 104h
0x18003049d  mov     [rsp+4C0h+var_490], r14d
0x1800304a2  mov     edx, edi; uSize
0x1800304a4  mov     [rsp+4C0h+var_488], r14d
0x1800304a9  mov     [rsp+4C0h+var_48C], r14d
0x1800304ae  mov     [rsp+4C0h+phModule], r14
0x1800304b3  call    cs:__imp_GetSystemDirectoryW
0x1800304b9  dec     eax
0x1800304bb  cmp     eax, 102h
0x1800304c0  ja      loc_180030700
0x1800304c6  lea     rcx, [rsp+4C0h+Buffer]; pszFile2
0x1800304cb  call    ?GetInvModuleInPath@@YAJPEBG@Z; GetInvModuleInPath(ushort const *)
0x1800304d0  mov     ebx, eax
0x1800304d2  test    eax, eax
0x1800304d4  jns     short loc_1800304EA
0x1800304d6  mov     dword ptr [rsp+4C0h+var_4A0], eax
0x1800304da  lea     r9, aGetinvmodulein; "GetInvModuleInPath failed %#x"
0x1800304e1  lea     r8d, [rdi-52h]
0x1800304e5  jmp     loc_180030726
0x1800304ea  jnz     short loc_1800304F6
0x1800304ec  mov     ebx, 1
0x1800304f1  jmp     loc_180030737
0x1800304f6  lea     r8, SubBlock; "\\"
0x1800304fd  lea     rcx, [rsp+4C0h+Buffer]; unsigned __int16 *
0x180030502  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x180030507  mov     ebx, eax
0x180030509  test    eax, eax
0x18003050b  jns     short loc_180030523
0x18003050d  mov     dword ptr [rsp+4C0h+var_4A0], eax
0x180030511  lea     r9, aStringcchcatFa; "StringCchCat failed %#x"
0x180030518  mov     r8d, 0C2h
0x18003051e  jmp     loc_180030726
0x180030523  lea     r8, [rsp+4C0h+phModule]; phModule
0x180030528  mov     ecx, 6; dwFlags
0x18003052d  lea     rdx, ?GetInvInboxRedirectImpl@@YAJPEBDPEAVIInventoryDataReceiver@Inventory@Compat@Windows@@PEAUInventoryControlParams@234@0@Z; lpModuleName
0x180030534  call    cs:__imp_GetModuleHandleExW
0x18003053a  test    eax, eax
0x18003053c  jnz     short loc_180030565
0x18003053e  call    cs:__imp_GetLastError
0x180030544  mov     ebx, eax
0x180030546  test    eax, eax
0x180030548  jle     short loc_180030553
0x18003054a  movzx   ebx, ax
0x18003054d  or      ebx, 80070000h
0x180030553  lea     r9, aGetmodulehandl; "GetModuleHandleEx failed %#x"
0x18003055a  mov     r8d, 0C9h
0x180030560  jmp     loc_180030722
0x180030565  mov     rcx, [rsp+4C0h+phModule]; hModule
0x18003056a  lea     rdx, [rbp+3C0h+Filename]; lpFilename
0x180030571  mov     r8d, edi; nSize
0x180030574  call    cs:__imp_GetModuleFileNameW
0x18003057a  test    eax, eax
0x18003057c  jz      loc_1800306DC
0x180030582  cmp     eax, edi
0x180030584  jb      short loc_180030595
0x180030586  call    cs:__imp_GetLastError
0x18003058c  cmp     eax, 7Ah ; 'z'
0x18003058f  jz      loc_1800306DC
0x180030595  lea     rcx, [rbp+3C0h+Filename]; pszPath
0x18003059c  call    cs:__imp_PathFindFileNameW
0x1800305a2  mov     r8, rax; unsigned __int16 *
0x1800305a5  lea     rcx, [rsp+4C0h+Buffer]; unsigned __int16 *
0x1800305aa  mov     rdi, rax
0x1800305ad  call    ?StringCchCatW@@YAJPEAG_KPEBG@Z; StringCchCatW(ushort *,unsigned __int64,ushort const *)
0x1800305b2  mov     ebx, eax
0x1800305b4  test    eax, eax
0x1800305b6  jns     short loc_1800305CE
0x1800305b8  mov     dword ptr [rsp+4C0h+var_4A0], eax
0x1800305bc  lea     r9, aStringcchcatFa; "StringCchCat failed %#x"
0x1800305c3  mov     r8d, 0DBh
0x1800305c9  jmp     loc_180030726
0x1800305ce  lea     r9, [rsp+4C0h+Buffer]
0x1800305d3  lea     r8, [rsp+4C0h+var_48C]
0x1800305d8  lea     rdx, [rsp+4C0h+var_488]
0x1800305dd  lea     rcx, [rsp+4C0h+var_490]
0x1800305e2  call    AslFileGetVersionForPath
0x1800305e7  test    eax, eax
0x1800305e9  js      loc_1800304EC
0x1800305ef  cmp     [rsp+4C0h+var_490], 0Ah
0x1800305f4  jnz     loc_1800304EC
0x1800305fa  lea     rdx, aAeinvDll_0; "aeinv.dll"
0x180030601  mov     rcx, rdi
0x180030604  call    cs:__imp__o__wcsicmp
0x18003060a  mov     ebx, [rsp+4C0h+var_48C]
0x18003060e  test    eax, eax
0x180030610  jnz     short loc_180030641
0x180030612  lea     eax, [rbx-3FDEh]
0x180030618  cmp     eax, 9
0x18003061b  jbe     loc_1800304EC
0x180030621  lea     eax, [rbx-3B35h]
0x180030627  cmp     eax, 468h
0x18003062c  jbe     loc_1800304EC
0x180030632  lea     eax, [rbx-49CFh]
0x180030638  cmp     eax, 24h ; '$'
0x18003063b  jbe     loc_1800304EC
0x180030641  xor     edx, edx; hFile
0x180030643  lea     rcx, [rsp+4C0h+Buffer]; lpLibFileName
0x180030648  mov     r8d, 800h; dwFlags
0x18003064e  call    cs:__imp_LoadLibraryExW
0x180030654  mov     rsi, rax
0x180030657  test    rax, rax
0x18003065a  jz      loc_1800304EC
0x180030660  mov     rdx, r15; lpProcName
0x180030663  mov     rcx, rax; hModule
0x180030666  call    cs:__imp_GetProcAddress
0x18003066c  mov     r14, rax
0x18003066f  test    rax, rax
0x180030672  jnz     short loc_180030679
0x180030674  lea     ebx, [rax+1]
0x180030677  jmp     short loc_1800306D1
0x180030679  mov     edx, ebx; unsigned int
0x18003067b  mov     rcx, rdi; unsigned __int16 *
0x18003067e  call    ?ShouldRedirectProceed@@YAJPEBGK@Z; ShouldRedirectProceed(ushort const *,ulong)
0x180030683  mov     ebx, eax
0x180030685  test    eax, eax
0x180030687  jnz     short loc_1800306D1
0x180030689  mov     r8, [rsp+4C0h+var_478]
0x18003068e  mov     rdx, r13
0x180030691  mov     rcx, r12
0x180030694  mov     rax, r14
0x180030697  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003069c  mov     rcx, rdi; unsigned __int16 *
0x18003069f  mov     ebx, eax
0x1800306a1  call    ?ClearAbortRedirect@@YAXPEBG@Z; ClearAbortRedirect(ushort const *)
0x1800306a6  test    ebx, ebx
0x1800306a8  jns     short loc_1800306D1
0x1800306aa  mov     [rsp+4C0h+var_498], ebx
0x1800306ae  lea     r9, aSFailedX; "%s failed %#x"
0x1800306b5  mov     r8d, 120h
0x1800306bb  mov     [rsp+4C0h+var_4A0], r15
0x1800306c0  lea     rdx, aGetinvinboxred; "GetInvInboxRedirectImpl"
0x1800306c7  mov     ecx, 1
0x1800306cc  call    AslLogCallPrintf
0x1800306d1  mov     rcx, rsi; hLibModule
0x1800306d4  call    cs:__imp_FreeLibrary
0x1800306da  jmp     short loc_180030737
0x1800306dc  call    cs:__imp_GetLastError
0x1800306e2  mov     ebx, eax
0x1800306e4  test    eax, eax
0x1800306e6  jle     short loc_1800306F1
0x1800306e8  movzx   ebx, ax
0x1800306eb  or      ebx, 80070000h
0x1800306f1  lea     r9, aGetmodulefilen; "GetModuleFileName failed %#x"
0x1800306f8  mov     r8d, 0D2h
0x1800306fe  jmp     short loc_180030722
0x180030700  call    cs:__imp_GetLastError
0x180030706  mov     ebx, eax
0x180030708  test    eax, eax
0x18003070a  jle     short loc_180030715
0x18003070c  movzx   ebx, ax
0x18003070f  or      ebx, 80070000h
0x180030715  lea     r9, aGetsystemdirec; "GetSystemDirectory failed %#x"
0x18003071c  mov     r8d, 0ABh
0x180030722  mov     dword ptr [rsp+4C0h+var_4A0], ebx
0x180030726  lea     rdx, aGetinvinboxred; "GetInvInboxRedirectImpl"
0x18003072d  mov     ecx, 1
0x180030732  call    AslLogCallPrintf
0x180030737  mov     eax, ebx
0x180030739  mov     rcx, [rbp+3C0h+var_50]
0x180030740  xor     rcx, rsp; StackCookie
0x180030743  call    __security_check_cookie
0x180030748  add     rsp, 488h
0x18003074f  pop     r15
0x180030751  pop     r14
0x180030753  pop     r13
0x180030755  pop     r12
0x180030757  pop     rdi
0x180030758  pop     rsi
0x180030759  pop     rbx
0x18003075a  pop     rbp
0x18003075b  retn
```
