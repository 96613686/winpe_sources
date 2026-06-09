# Windows::Compat::Appraiser::Utilities::ExtractResourceToFile(ulong,ushort const *,ushort const *)

- ea: `0x18008762c`
- end: `0x180087a03`
- name: `?ExtractResourceToFile@Utilities@Appraiser@Compat@Windows@@SAJKPEBG0@Z`
- size: `983`
- prototype: `static int(unsigned int, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `2`
- callee_count: `4`
- tags: `file_ops, loader_planting, broker_com_uri`

## callers

- `0x180039538`
- `0x18003b600`

## callees

- `0x180008570`
- `0x18002ebb8`
- `0x1800301d0`
- `0x18008762c`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008768e`
- `api-ms-win-crt-private-l1-1-0!_o__wcsicmp` at `0x18008768e`
- `KERNEL32!SizeofResource` at `0x1800877eb`
- `KERNEL32!SizeofResource` at `0x1800877eb`
- `KERNEL32!LoadResource` at `0x18008779d`
- `KERNEL32!LoadResource` at `0x18008779d`
- `KERNEL32!FindResourceW` at `0x18008774a`
- `KERNEL32!FindResourceW` at `0x18008774a`
- `KERNEL32!GetFullPathNameW` at `0x180087673`
- `KERNEL32!GetFullPathNameW` at `0x180087673`
- `KERNEL32!CreateFileW` at `0x18008789d`
- `KERNEL32!CreateFileW` at `0x18008789d`
- `KERNEL32!WriteFile` at `0x1800878ff`
- `KERNEL32!WriteFile` at `0x1800878ff`
- `KERNEL32!LoadLibraryExW` at `0x1800876e6`
- `KERNEL32!LoadLibraryExW` at `0x1800876e6`
- `KERNEL32!FreeLibrary` at `0x180087969`
- `KERNEL32!FreeLibrary` at `0x180087969`
- `KERNEL32!CloseHandle` at `0x180087978`
- `KERNEL32!CloseHandle` at `0x180087978`
- `KERNEL32!GetLastError` at `0x1800876f4`
- `KERNEL32!GetLastError` at `0x180087713`
- `KERNEL32!GetLastError` at `0x180087758`
- `KERNEL32!GetLastError` at `0x180087777`
- `KERNEL32!GetLastError` at `0x1800877ab`
- `KERNEL32!GetLastError` at `0x1800877ca`
- `KERNEL32!GetLastError` at `0x1800877f7`
- `KERNEL32!GetLastError` at `0x180087816`
- `KERNEL32!GetLastError` at `0x1800878ac`
- `KERNEL32!GetLastError` at `0x1800878cb`
- `KERNEL32!GetLastError` at `0x180087913`
- `KERNEL32!GetLastError` at `0x180087932`
- `KERNEL32!GetLastError` at `0x180087980`
- `KERNEL32!GetLastError` at `0x18008799f`
- `KERNEL32!GetLastError` at `0x1800876f4`
- `KERNEL32!GetLastError` at `0x180087713`
- `KERNEL32!GetLastError` at `0x180087758`
- `KERNEL32!GetLastError` at `0x180087777`
- `KERNEL32!GetLastError` at `0x1800877ab`
- `KERNEL32!GetLastError` at `0x1800877ca`
- `KERNEL32!GetLastError` at `0x1800877f7`
- `KERNEL32!GetLastError` at `0x180087816`
- `KERNEL32!GetLastError` at `0x1800878ac`
- `KERNEL32!GetLastError` at `0x1800878cb`
- `KERNEL32!GetLastError` at `0x180087913`
- `KERNEL32!GetLastError` at `0x180087932`
- `KERNEL32!GetLastError` at `0x180087980`
- `KERNEL32!GetLastError` at `0x18008799f`
- `KERNEL32!LockResource` at `0x180087834`
- `KERNEL32!LockResource` at `0x180087834`

## string_xrefs

- `0x1800876a0`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800879bc`: `onecore\base\appcompat\appraiser\helpers\utilities.cpp`
- `0x1800878df`: `CreateFile failed for %ls: [%d].`
- `0x1800876c4`: `Must provide full path to extract, '%ls' has full path of '%ls'.`
- `0x1800879b0`: `Failed to get full path from resource path: [%d].`
- `0x180087694`: `Windows::Compat::Appraiser::Utilities::ExtractResourceToFile`
- `0x1800879a9`: `Windows::Compat::Appraiser::Utilities::ExtractResourceToFile`
- `0x180087720`: `Could not LoadLibrary to resource: [%d].`
- `0x180087941`: `WriteFile failed to write resource with id %d: [%d].`

## pseudocode

```c
__int64 __fastcall Windows::Compat::Appraiser::Utilities::ExtractResourceToFile(
        __int64 a1,
        const unsigned __int16 *a2,
        const unsigned __int16 *a3)
{
  HMODULE Library; // rax
  HMODULE v6; // r14
  signed int v7; // eax
  signed int v8; // ebx
  const char *v9; // rax
  char v10; // dl
  __int64 v11; // r15
  HRSRC ResourceW; // rax
  HRSRC v13; // rbx
  signed int v14; // eax
  char v15; // dl
  const char *v16; // rax
  HGLOBAL Resource; // r12
  signed int v18; // eax
  DWORD v19; // ebx
  signed int v20; // eax
  const void *v21; // r12
  HANDLE FileW; // rax
  signed int v23; // eax
  signed int v24; // eax
  signed int LastError; // eax
  const char *dwCreationDisposition; // [rsp+20h] [rbp-288h]
  const char *hTemplateFile; // [rsp+30h] [rbp-278h]
  DWORD v29; // [rsp+38h] [rbp-270h]
  DWORD NumberOfBytesWritten; // [rsp+40h] [rbp-268h] BYREF
  WCHAR Buffer[264]; // [rsp+50h] [rbp-258h] BYREF

  NumberOfBytesWritten = 0;
  if ( GetFullPathNameW(a2, 0x104u, Buffer, 0) - 1 > 0x103 )
  {
    LastError = GetLastError();
    v8 = LastError;
    if ( LastError > 0 )
      v8 = (unsigned __int16)LastError | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    LODWORD(hTemplateFile) = GetLastError();
    v9 = "Failed to get full path from resource path: [%d].";
    v10 = -17;
    goto LABEL_54;
  }
  if ( (unsigned int)_o__wcsicmp(a2, Buffer) && (Windows::Compat::Appraiser::WicaFactory::TestingFlags & 1) != 0 )
    Windows::Compat::Appraiser::WicaFactory::RunPrintf(
      0x3F5u,
      "onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::ExtractResourceToFile",
      "Must provide full path to extract, '%ls' has full path of '%ls'.",
      a2,
      Buffer);
  Library = LoadLibraryExW(a2, 0, 0x22u);
  v6 = Library;
  if ( !Library )
  {
    v7 = GetLastError();
    v8 = v7;
    if ( v7 > 0 )
      v8 = (unsigned __int16)v7 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    LODWORD(hTemplateFile) = GetLastError();
    v9 = "Could not LoadLibrary to resource: [%d].";
    v10 = -5;
LABEL_54:
    LODWORD(dwCreationDisposition) = v8;
    Windows::Compat::Appraiser::WriteLog(
      (Windows::Compat::Appraiser *)1,
      v10,
      (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
      "Windows::Compat::Appraiser::Utilities::ExtractResourceToFile",
      dwCreationDisposition,
      (int)v9,
      hTemplateFile);
    return (unsigned int)v8;
  }
  v11 = -1;
  ResourceW = FindResourceW(Library, (LPCWSTR)0x1F4, (LPCWSTR)0xA);
  v13 = ResourceW;
  if ( ResourceW )
  {
    Resource = LoadResource(v6, ResourceW);
    if ( Resource )
    {
      v19 = SizeofResource(v6, v13);
      if ( v19 )
      {
        v21 = LockResource(Resource);
        if ( !v21 )
        {
          LODWORD(hTemplateFile) = 500;
          v8 = -2147019890;
          LODWORD(dwCreationDisposition) = -2147019890;
          Windows::Compat::Appraiser::WriteLog(
            (Windows::Compat::Appraiser *)1,
            19,
            (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
            "Windows::Compat::Appraiser::Utilities::ExtractResourceToFile",
            dwCreationDisposition,
            (int)"Could not get stream for resource id %d.",
            hTemplateFile);
          goto LABEL_47;
        }
        FileW = CreateFileW(a3, 0x40000000u, 0, 0, 2u, 0x80u, 0);
        v11 = (__int64)FileW;
        if ( FileW == (HANDLE)-1LL )
        {
          v23 = GetLastError();
          v8 = v23;
          if ( v23 > 0 )
            v8 = (unsigned __int16)v23 | 0x80070000;
          if ( v8 >= 0 )
            v8 = -2147467259;
          v29 = GetLastError();
          v15 = 31;
          hTemplateFile = (const char *)a3;
          v16 = "CreateFile failed for %ls: [%d].";
          goto LABEL_46;
        }
        if ( WriteFile(FileW, v21, v19, &NumberOfBytesWritten, 0) && v19 == NumberOfBytesWritten )
        {
          v8 = 0;
          goto LABEL_47;
        }
        v24 = GetLastError();
        v8 = v24;
        if ( v24 > 0 )
          v8 = (unsigned __int16)v24 | 0x80070000;
        if ( v8 >= 0 )
          v8 = -2147467259;
        v29 = GetLastError();
        v15 = 41;
        v16 = "WriteFile failed to write resource with id %d: [%d].";
      }
      else
      {
        v20 = GetLastError();
        v8 = v20;
        if ( v20 > 0 )
          v8 = (unsigned __int16)v20 | 0x80070000;
        if ( v8 >= 0 )
          v8 = -2147467259;
        v29 = GetLastError();
        v15 = 13;
        v16 = "Could not get size for resource with id %d: [%d].";
      }
    }
    else
    {
      v18 = GetLastError();
      v8 = v18;
      if ( v18 > 0 )
        v8 = (unsigned __int16)v18 | 0x80070000;
      if ( v8 >= 0 )
        v8 = -2147467259;
      v29 = GetLastError();
      v15 = 7;
      v16 = "Could not load resource with id %d: [%d].";
    }
    LODWORD(hTemplateFile) = 500;
  }
  else
  {
    v14 = GetLastError();
    v8 = v14;
    if ( v14 > 0 )
      v8 = (unsigned __int16)v14 | 0x80070000;
    if ( v8 >= 0 )
      v8 = -2147467259;
    v29 = GetLastError();
    v15 = 1;
    LODWORD(hTemplateFile) = 500;
    v16 = "Could not find resource with id %d: [%d].";
  }
LABEL_46:
  LODWORD(dwCreationDisposition) = v8;
  Windows::Compat::Appraiser::WriteLog(
    (Windows::Compat::Appraiser *)1,
    v15,
    (unsigned int)"onecore\\base\\appcompat\\appraiser\\helpers\\utilities.cpp",
    "Windows::Compat::Appraiser::Utilities::ExtractResourceToFile",
    dwCreationDisposition,
    (int)v16,
    hTemplateFile,
    v29);
LABEL_47:
  FreeLibrary(v6);
  if ( v11 != -1 )
    CloseHandle((HANDLE)v11);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18008762c  mov     [rsp+arg_0], rbx
0x180087631  push    rbp
0x180087632  push    rsi
0x180087633  push    rdi
0x180087634  push    r12
0x180087636  push    r13
0x180087638  push    r14
0x18008763a  push    r15
0x18008763c  sub     rsp, 270h
0x180087643  mov     rax, cs:__security_cookie
0x18008764a  xor     rax, rsp
0x18008764d  mov     [rsp+2A8h+var_48], rax
0x180087655  mov     rbx, rdx
0x180087658  mov     [rsp+2A8h+NumberOfBytesWritten], 0
0x180087660  mov     r13, r8
0x180087663  mov     rcx, rbx; lpFileName
0x180087666  xor     r9d, r9d; lpFilePart
0x180087669  lea     r8, [rsp+2A8h+Buffer]; lpBuffer
0x18008766e  mov     edx, 104h; nBufferLength
0x180087673  call    cs:__imp_GetFullPathNameW
0x180087679  dec     eax
0x18008767b  cmp     eax, 103h
0x180087680  ja      loc_180087980
0x180087686  lea     rdx, [rsp+2A8h+Buffer]
0x18008768b  mov     rcx, rbx
0x18008768e  call    cs:__imp__o__wcsicmp
0x180087694  lea     rsi, aWindowsCompatA_430; "Windows::Compat::Appraiser::Utilities::"...
0x18008769b  mov     edi, 1
0x1800876a0  lea     rbp, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800876a7  test    eax, eax
0x1800876a9  jz      short loc_1800876DD
0x1800876ab  mov     eax, cs:?TestingFlags@WicaFactory@Appraiser@Compat@Windows@@2KA; ulong Windows::Compat::Appraiser::WicaFactory::TestingFlags
0x1800876b1  and     eax, edi
0x1800876b3  test    al, al
0x1800876b5  jz      short loc_1800876DD
0x1800876b7  lea     rax, [rsp+2A8h+Buffer]
0x1800876bc  mov     r8, rsi; char *
0x1800876bf  mov     qword ptr [rsp+2A8h+dwFlagsAndAttributes], rax
0x1800876c4  lea     r9, aMustProvideFul; "Must provide full path to extract, '%ls"...
0x1800876cb  mov     rdx, rbp; char *
0x1800876ce  mov     qword ptr [rsp+2A8h+dwCreationDisposition], rbx
0x1800876d3  mov     ecx, 3F5h; unsigned int
0x1800876d8  call    ?RunPrintf@WicaFactory@Appraiser@Compat@Windows@@SAXKPEBD00ZZ; Windows::Compat::Appraiser::WicaFactory::RunPrintf(ulong,char const *,char const *,char const *,...)
0x1800876dd  xor     edx, edx; hFile
0x1800876df  mov     rcx, rbx; lpLibFileName
0x1800876e2  lea     r8d, [rdx+22h]; dwFlags
0x1800876e6  call    cs:__imp_LoadLibraryExW
0x1800876ec  mov     r14, rax
0x1800876ef  test    rax, rax
0x1800876f2  jnz     short loc_180087736
0x1800876f4  call    cs:__imp_GetLastError
0x1800876fa  mov     ebx, eax
0x1800876fc  test    eax, eax
0x1800876fe  jle     short loc_180087709
0x180087700  movzx   ebx, ax
0x180087703  or      ebx, 80070000h
0x180087709  test    ebx, ebx
0x18008770b  mov     eax, 80004005h
0x180087710  cmovns  ebx, eax
0x180087713  call    cs:__imp_GetLastError
0x180087719  mov     dword ptr [rsp+2A8h+hTemplateFile], eax
0x18008771d  mov     r9, rsi
0x180087720  lea     rax, aCouldNotLoadli; "Could not LoadLibrary to resource: [%d]"...
0x180087727  mov     r8, rbp
0x18008772a  mov     edx, 3FBh
0x18008772f  mov     ecx, edi
0x180087731  jmp     loc_1800879C8
0x180087736  or      r15, 0FFFFFFFFFFFFFFFFh
0x18008773a  mov     r12d, 1F4h
0x180087740  mov     edx, r12d; lpName
0x180087743  mov     rcx, r14; hModule
0x180087746  lea     r8d, [r15+0Bh]; lpType
0x18008774a  call    cs:__imp_FindResourceW
0x180087750  mov     rbx, rax
0x180087753  test    rax, rax
0x180087756  jnz     short loc_180087797
0x180087758  call    cs:__imp_GetLastError
0x18008775e  mov     ebx, eax
0x180087760  test    eax, eax
0x180087762  jle     short loc_18008776D
0x180087764  movzx   ebx, ax
0x180087767  or      ebx, 80070000h
0x18008776d  test    ebx, ebx
0x18008776f  mov     eax, 80004005h
0x180087774  cmovns  ebx, eax
0x180087777  call    cs:__imp_GetLastError
0x18008777d  mov     [rsp+2A8h+var_270], eax
0x180087781  mov     edx, 401h
0x180087786  mov     dword ptr [rsp+2A8h+hTemplateFile], r12d
0x18008778b  lea     rax, aCouldNotFindRe; "Could not find resource with id %d: [%d"...
0x180087792  jmp     loc_180087950
0x180087797  mov     rdx, rbx; hResInfo
0x18008779a  mov     rcx, r14; hModule
0x18008779d  call    cs:__imp_LoadResource
0x1800877a3  mov     r12, rax
0x1800877a6  test    rax, rax
0x1800877a9  jnz     short loc_1800877E5
0x1800877ab  call    cs:__imp_GetLastError
0x1800877b1  mov     ebx, eax
0x1800877b3  test    eax, eax
0x1800877b5  jle     short loc_1800877C0
0x1800877b7  movzx   ebx, ax
0x1800877ba  or      ebx, 80070000h
0x1800877c0  test    ebx, ebx
0x1800877c2  mov     eax, 80004005h
0x1800877c7  cmovns  ebx, eax
0x1800877ca  call    cs:__imp_GetLastError
0x1800877d0  mov     [rsp+2A8h+var_270], eax
0x1800877d4  mov     edx, 407h
0x1800877d9  lea     rax, aCouldNotLoadRe; "Could not load resource with id %d: [%d"...
0x1800877e0  jmp     loc_180087948
0x1800877e5  mov     rdx, rbx; hResInfo
0x1800877e8  mov     rcx, r14; hModule
0x1800877eb  call    cs:__imp_SizeofResource
0x1800877f1  mov     ebx, eax
0x1800877f3  test    eax, eax
0x1800877f5  jnz     short loc_180087831
0x1800877f7  call    cs:__imp_GetLastError
0x1800877fd  mov     ebx, eax
0x1800877ff  test    eax, eax
0x180087801  jle     short loc_18008780C
0x180087803  movzx   ebx, ax
0x180087806  or      ebx, 80070000h
0x18008780c  test    ebx, ebx
0x18008780e  mov     eax, 80004005h
0x180087813  cmovns  ebx, eax
0x180087816  call    cs:__imp_GetLastError
0x18008781c  mov     [rsp+2A8h+var_270], eax
0x180087820  mov     edx, 40Dh
0x180087825  lea     rax, aCouldNotGetSiz; "Could not get size for resource with id"...
0x18008782c  jmp     loc_180087948
0x180087831  mov     rcx, r12; hResData
0x180087834  call    cs:__imp_LockResource
0x18008783a  mov     r12, rax
0x18008783d  test    rax, rax
0x180087840  jnz     short loc_180087876
0x180087842  lea     rax, aCouldNotGetStr; "Could not get stream for resource id %d"...
0x180087849  mov     dword ptr [rsp+2A8h+hTemplateFile], 1F4h; char *
0x180087851  mov     qword ptr [rsp+2A8h+dwFlagsAndAttributes], rax; int
0x180087856  mov     ebx, 8007138Eh
0x18008785b  mov     r9, rsi; char *
0x18008785e  mov     [rsp+2A8h+dwCreationDisposition], ebx; char *
0x180087862  mov     r8, rbp; unsigned int
0x180087865  mov     edx, 413h; bool
0x18008786a  mov     ecx, edi; this
0x18008786c  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180087871  jmp     loc_180087966
0x180087876  mov     [rsp+2A8h+hTemplateFile], 0; hTemplateFile
0x18008787f  xor     r9d, r9d; lpSecurityAttributes
0x180087882  mov     [rsp+2A8h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x18008788a  xor     r8d, r8d; dwShareMode
0x18008788d  mov     edx, 40000000h; dwDesiredAccess
0x180087892  mov     [rsp+2A8h+dwCreationDisposition], 2; dwCreationDisposition
0x18008789a  mov     rcx, r13; lpFileName
0x18008789d  call    cs:__imp_CreateFileW
0x1800878a3  mov     r15, rax
0x1800878a6  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800878aa  jnz     short loc_1800878E8
0x1800878ac  call    cs:__imp_GetLastError
0x1800878b2  mov     ebx, eax
0x1800878b4  test    eax, eax
0x1800878b6  jle     short loc_1800878C1
0x1800878b8  movzx   ebx, ax
0x1800878bb  or      ebx, 80070000h
0x1800878c1  test    ebx, ebx
0x1800878c3  mov     eax, 80004005h
0x1800878c8  cmovns  ebx, eax
0x1800878cb  call    cs:__imp_GetLastError
0x1800878d1  mov     [rsp+2A8h+var_270], eax
0x1800878d5  mov     edx, 41Fh
0x1800878da  mov     [rsp+2A8h+hTemplateFile], r13
0x1800878df  lea     rax, aCreatefileFail; "CreateFile failed for %ls: [%d]."
0x1800878e6  jmp     short loc_180087950
0x1800878e8  lea     r9, [rsp+2A8h+NumberOfBytesWritten]; lpNumberOfBytesWritten
0x1800878ed  mov     qword ptr [rsp+2A8h+dwCreationDisposition], 0; lpOverlapped
0x1800878f6  mov     r8d, ebx; nNumberOfBytesToWrite
0x1800878f9  mov     rdx, r12; lpBuffer
0x1800878fc  mov     rcx, rax; hFile
0x1800878ff  call    cs:__imp_WriteFile
0x180087905  test    eax, eax
0x180087907  jz      short loc_180087913
0x180087909  cmp     ebx, [rsp+2A8h+NumberOfBytesWritten]
0x18008790d  jnz     short loc_180087913
0x18008790f  xor     ebx, ebx
0x180087911  jmp     short loc_180087966
0x180087913  call    cs:__imp_GetLastError
0x180087919  mov     ebx, eax
0x18008791b  test    eax, eax
0x18008791d  jle     short loc_180087928
0x18008791f  movzx   ebx, ax
0x180087922  or      ebx, 80070000h
0x180087928  test    ebx, ebx
0x18008792a  mov     eax, 80004005h
0x18008792f  cmovns  ebx, eax
0x180087932  call    cs:__imp_GetLastError
0x180087938  mov     [rsp+2A8h+var_270], eax
0x18008793c  mov     edx, 429h; bool
0x180087941  lea     rax, aWritefileFaile; "WriteFile failed to write resource with"...
0x180087948  mov     dword ptr [rsp+2A8h+hTemplateFile], 1F4h; char *
0x180087950  mov     qword ptr [rsp+2A8h+dwFlagsAndAttributes], rax; int
0x180087955  mov     r9, rsi; char *
0x180087958  mov     r8, rbp; unsigned int
0x18008795b  mov     [rsp+2A8h+dwCreationDisposition], ebx; char *
0x18008795f  mov     ecx, edi; this
0x180087961  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x180087966  mov     rcx, r14; hLibModule
0x180087969  call    cs:__imp_FreeLibrary
0x18008796f  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180087973  jz      short loc_1800879D6
0x180087975  mov     rcx, r15; hObject
0x180087978  call    cs:__imp_CloseHandle
0x18008797e  jmp     short loc_1800879D6
0x180087980  call    cs:__imp_GetLastError
0x180087986  mov     ebx, eax
0x180087988  test    eax, eax
0x18008798a  jle     short loc_180087995
0x18008798c  movzx   ebx, ax
0x18008798f  or      ebx, 80070000h
0x180087995  test    ebx, ebx
0x180087997  mov     eax, 80004005h
0x18008799c  cmovns  ebx, eax
0x18008799f  call    cs:__imp_GetLastError
0x1800879a5  mov     dword ptr [rsp+2A8h+hTemplateFile], eax; char *
0x1800879a9  lea     r9, aWindowsCompatA_430; "Windows::Compat::Appraiser::Utilities::"...
0x1800879b0  lea     rax, aFailedToGetFul_0; "Failed to get full path from resource p"...
0x1800879b7  mov     edx, 3EFh; bool
0x1800879bc  lea     r8, aOnecoreBaseApp_7; "onecore\\base\\appcompat\\appraiser\\he"...
0x1800879c3  mov     ecx, 1; this
0x1800879c8  mov     qword ptr [rsp+2A8h+dwFlagsAndAttributes], rax; int
0x1800879cd  mov     [rsp+2A8h+dwCreationDisposition], ebx; char *
0x1800879d1  call    ?WriteLog@Appraiser@Compat@Windows@@YAX_NKPEBD1J1ZZ; Windows::Compat::Appraiser::WriteLog(bool,ulong,char const *,char const *,long,char const *,...)
0x1800879d6  mov     eax, ebx
0x1800879d8  mov     rcx, [rsp+2A8h+var_48]
0x1800879e0  xor     rcx, rsp; StackCookie
0x1800879e3  call    __security_check_cookie
0x1800879e8  mov     rbx, [rsp+2A8h+arg_0]
0x1800879f0  add     rsp, 270h
0x1800879f7  pop     r15
0x1800879f9  pop     r14
0x1800879fb  pop     r13
0x1800879fd  pop     r12
0x1800879ff  pop     rdi
0x180087a00  pop     rsi
0x180087a01  pop     rbp
0x180087a02  retn
```
