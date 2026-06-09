# Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(char const *,ulong,Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock> &)

- ea: `0x18007c33c`
- end: `0x18007c513`
- name: `??$LoadProvider@VCFakeSRWLock@DelayLoad@Performance@@@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBDKAEAV?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@1@@Z`
- size: `471`
- prototype: `signed int __fastcall(__int64, const char *, unsigned int, __int64)`
- caller_count: `1`
- callee_count: `7`
- tags: `file_ops, registry_config, loader_planting, broker_com_uri`

## callers

- `0x18002daa0`

## callees

- `0x180009b40`
- `0x18002da28`
- `0x1800419e8`
- `0x18004ece0`
- `0x18007c33c`
- `0x18007db4c`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007c3a5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18007c3a5`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18007c38b`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18007c38b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c44f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18007c44f`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007c4e4`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x18007c4e4`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18007c425`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18007c445`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18007c425`
- `api-ms-win-core-file-l1-1-0!GetTempFileNameW` at `0x18007c445`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18007c3cf`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18007c3cf`

## string_xrefs

- `0x18007c384`: `kernelbase.dll`
- `0x18007c39b`: `GetTempPath2W`
- `0x18007c48d`: `TdhLoadManifest`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
signed int __fastcall Microsoft::Windows::Performance::CEventSourceHandler::LoadProvider<Performance::DelayLoad::CFakeSRWLock>(
        __int64 a1,
        const char *a2,
        unsigned int a3,
        __int64 a4)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax
  DWORD TempPathW; // eax
  DWORD v10; // ebx
  signed int result; // eax
  Microsoft::Windows::Performance::CEventSourceHandler *v12; // rcx
  __int64 (__fastcall *v13)(WCHAR *); // rax
  int v14; // eax
  unsigned int v15; // ebx
  WCHAR *v16; // [rsp+28h] [rbp-E0h] BYREF
  _QWORD v17[3]; // [rsp+30h] [rbp-D8h] BYREF
  __int64 v18; // [rsp+48h] [rbp-C0h]
  __int64 v19; // [rsp+50h] [rbp-B8h]
  WCHAR TempFileName[264]; // [rsp+58h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+268h] [rbp+160h] BYREF

  v19 = -2;
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v16 = (WCHAR *)Library;
  if ( Library && (ProcAddress = GetProcAddress(Library, "GetTempPath2W")) != 0 )
    TempPathW = ((__int64 (__fastcall *)(__int64, WCHAR *))ProcAddress)(260, Buffer);
  else
    TempPathW = GetTempPathW(0x104u, Buffer);
  v10 = TempPathW;
  Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(&v16);
  if ( v10 && v10 + 1 <= 0x104 || (result = StringCchCopyW(Buffer, 0x104u, L"."), result >= 0) )
  {
    if ( GetTempFileNameW(Buffer, L"xpf", 0, TempFileName) || GetTempFileNameW(L".", L"xpf", 0, TempFileName) )
    {
      result = Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(v12, TempFileName, a2, a3);
      if ( result >= 0 )
      {
        v16 = TempFileName;
        v17[0] = a4;
        v17[1] = "TdhLoadManifest";
        v17[2] = 0;
        LOBYTE(v18) = 0;
        if ( Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)(v17)
          && (v13 = (__int64 (__fastcall *)(WCHAR *))Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,unsigned short const *,unsigned long),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,unsigned short const *,unsigned long)(v17),
              v14 = v13(TempFileName),
              (v15 = v14) != 0) )
        {
          if ( v14 > 0 )
            v15 = (unsigned __int16)v14 | 0x80070000;
        }
        else
        {
          v15 = 0;
        }
        DeleteFileW(TempFileName);
        return v15;
      }
    }
    else
    {
      result = GetLastError();
      if ( result > 0 )
        return (unsigned __int16)result | 0x80070000;
    }
  }
  return result;
}

```

## disassembly

```asm
0x18007c33c  mov     rax, rsp
0x18007c33f  push    rbp
0x18007c340  push    rdi
0x18007c341  push    r14
0x18007c343  lea     rbp, [rax-398h]
0x18007c34a  sub     rsp, 480h
0x18007c351  mov     [rsp+490h+var_448], 0FFFFFFFFFFFFFFFEh
0x18007c35a  mov     [rax+8], rbx
0x18007c35e  mov     [rax+20h], rsi
0x18007c362  mov     rax, cs:__security_cookie
0x18007c369  xor     rax, rsp
0x18007c36c  mov     [rbp+390h+var_20], rax
0x18007c373  mov     rdi, r9
0x18007c376  mov     r14d, r8d
0x18007c379  mov     rsi, rdx
0x18007c37c  xor     edx, edx; hFile
0x18007c37e  mov     r8d, 800h; dwFlags
0x18007c384  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18007c38b  call    cs:__imp_LoadLibraryExW
0x18007c391  mov     [rsp+490h+var_470], rax
0x18007c396  test    rax, rax
0x18007c399  jz      short loc_18007C3C3
0x18007c39b  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18007c3a2  mov     rcx, rax; hModule
0x18007c3a5  call    cs:__imp_GetProcAddress
0x18007c3ab  test    rax, rax
0x18007c3ae  jz      short loc_18007C3C3
0x18007c3b0  lea     rdx, [rbp+390h+Buffer]
0x18007c3b7  mov     ecx, 104h
0x18007c3bc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c3c1  jmp     short loc_18007C3D5
0x18007c3c3  lea     rdx, [rbp+390h+Buffer]; lpBuffer
0x18007c3ca  mov     ecx, 104h; nBufferLength
0x18007c3cf  call    cs:__imp_GetTempPathW
0x18007c3d5  mov     ebx, eax
0x18007c3d7  lea     rcx, [rsp+490h+var_470]
0x18007c3dc  call    ??1?$CDelayLoadedModule@VCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAA@XZ; Performance::DelayLoad::CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>::~CDelayLoadedModule<Performance::DelayLoad::CFakeSRWLock>(void)
0x18007c3e1  test    ebx, ebx
0x18007c3e3  jz      short loc_18007C3EF
0x18007c3e5  lea     eax, [rbx+1]
0x18007c3e8  cmp     eax, 104h
0x18007c3ed  jbe     short loc_18007C40F
0x18007c3ef  lea     r8, PathName; "."
0x18007c3f6  mov     edx, 104h; unsigned __int64
0x18007c3fb  lea     rcx, [rbp+390h+Buffer]; unsigned __int16 *
0x18007c402  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18007c407  test    eax, eax
0x18007c409  js      loc_18007C4EC
0x18007c40f  lea     r9, [rsp+490h+TempFileName]; lpTempFileName
0x18007c414  xor     r8d, r8d; uUnique
0x18007c417  lea     rdx, aXpf; "xpf"
0x18007c41e  lea     rcx, [rbp+390h+Buffer]; lpPathName
0x18007c425  call    cs:__imp_GetTempFileNameW
0x18007c42b  test    eax, eax
0x18007c42d  jnz     short loc_18007C46A
0x18007c42f  lea     r9, [rsp+490h+TempFileName]; lpTempFileName
0x18007c434  xor     r8d, r8d; uUnique
0x18007c437  lea     rdx, aXpf; "xpf"
0x18007c43e  lea     rcx, PathName; "."
0x18007c445  call    cs:__imp_GetTempFileNameW
0x18007c44b  test    eax, eax
0x18007c44d  jnz     short loc_18007C46A
0x18007c44f  call    cs:__imp_GetLastError
0x18007c455  test    eax, eax
0x18007c457  jle     loc_18007C4EC
0x18007c45d  movzx   eax, ax
0x18007c460  or      eax, 80070000h
0x18007c465  jmp     loc_18007C4EC
0x18007c46a  mov     r9d, r14d; unsigned int
0x18007c46d  mov     r8, rsi; char *
0x18007c470  lea     rdx, [rsp+490h+TempFileName]; unsigned __int16 *
0x18007c475  call    ?WriteManifestFile@CEventSourceHandler@Performance@Windows@Microsoft@@AEAAJPEBGPEBDK@Z; Microsoft::Windows::Performance::CEventSourceHandler::WriteManifestFile(ushort const *,char const *,ulong)
0x18007c47a  test    eax, eax
0x18007c47c  js      short loc_18007C4EC
0x18007c47e  lea     rax, [rsp+490h+TempFileName]
0x18007c483  mov     [rsp+490h+var_470], rax
0x18007c488  mov     [rsp+490h+var_468], rdi
0x18007c48d  lea     rax, aTdhloadmanifes; "TdhLoadManifest"
0x18007c494  mov     [rsp+490h+var_460], rax
0x18007c499  mov     qword ptr [rsp+490h+var_458], 0
0x18007c4a2  mov     byte ptr [rsp+490h+var_450], 0
0x18007c4a7  lea     rcx, [rsp+490h+var_468]
0x18007c4ac  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x18007c4b1  test    rax, rax
0x18007c4b4  jz      short loc_18007C4DD
0x18007c4b6  lea     rcx, [rsp+490h+var_468]
0x18007c4bb  call    ??B?$CDelayLoadedImport@P6APEAXPEAXPEBGK@ZVCFakeSRWLock@DelayLoad@Performance@@@DelayLoad@Performance@@QEAAP6APEAXPEAXPEBGK@ZXZ; Performance::DelayLoad::CDelayLoadedImport<void * (*)(void *,ushort const *,ulong),Performance::DelayLoad::CFakeSRWLock>::operator void * (*)(void *,ushort const *,ulong)(void)
0x18007c4c0  lea     rcx, [rsp+490h+TempFileName]
0x18007c4c5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18007c4ca  mov     ebx, eax
0x18007c4cc  test    eax, eax
0x18007c4ce  jz      short loc_18007C4DD
0x18007c4d0  jle     short loc_18007C4DF
0x18007c4d2  movzx   ebx, ax
0x18007c4d5  or      ebx, 80070000h
0x18007c4db  jmp     short loc_18007C4DF
0x18007c4dd  xor     ebx, ebx
0x18007c4df  lea     rcx, [rsp+490h+TempFileName]; lpFileName
0x18007c4e4  call    cs:__imp_DeleteFileW
0x18007c4ea  mov     eax, ebx
0x18007c4ec  mov     rcx, [rbp+390h+var_20]
0x18007c4f3  xor     rcx, rsp; StackCookie
0x18007c4f6  call    __security_check_cookie
0x18007c4fb  lea     r11, [rsp+490h+var_10]
0x18007c503  mov     rbx, [r11+20h]
0x18007c507  mov     rsi, [r11+38h]
0x18007c50b  mov     rsp, r11
0x18007c50e  pop     r14
0x18007c510  pop     rdi
0x18007c511  pop     rbp
0x18007c512  retn
```
