# GameInputModule::LoadModule(GameInputModule::ModuleKind,GameInputVersion const &)

- ea: `0x18002c6fc`
- end: `0x18002c8d1`
- name: `?LoadModule@GameInputModule@@AEAAJW4ModuleKind@1@AEBUGameInputVersion@@@Z`
- size: `469`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x180003710`
- `0x180003750`
- `0x1800038d0`

## callees

- `0x18000c11c`
- `0x18002c4d8`
- `0x18002c6fc`
- `0x18002c8d8`
- `0x18002cba0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c779`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c89c`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c779`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18002c89c`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c726`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18002c726`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002c78c`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002c78c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c7cb`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18002c7cb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c7f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c817`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c835`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c7f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c817`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002c835`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c867`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18002c867`

## string_xrefs

- `0x18002c751`: `GameInputRedist.dll`
- `0x18002c7ef`: `GameInputCreate`
- `0x18002c80d`: `DllCanUnloadNow`
- `0x18002c82b`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall GameInputModule::LoadModule(__int64 a1, __int64 a2, const WCHAR *a3)
{
  int v3; // ebx
  const struct std::nothrow_t *v4; // rdx
  signed int SystemDirPath; // ebx
  DWORD FileAttributesW; // eax
  const struct GameInputVersion *v8; // rdx
  HMODULE Library; // rax
  HMODULE v10; // rbx
  FARPROC ProcAddress; // rsi
  FARPROC v12; // rbp
  FARPROC v13; // rax
  LPCWSTR lpFileName; // [rsp+40h] [rbp+18h] BYREF

  lpFileName = a3;
  v3 = g_redistModule;
  if ( g_redistModule )
    goto LABEL_20;
  EnterCriticalSection(&CriticalSection);
  v3 = g_redistModule;
  if ( g_redistModule )
  {
LABEL_19:
    LeaveCriticalSection(&CriticalSection);
LABEL_20:
    if ( v3 == 2 )
      return qword_1800698D0 == 0;
    else
      return 2147549183LL;
  }
  lpFileName = 0;
  SystemDirPath = GameInputModule::GetSystemDirPath(
                    (__int64)L"GameInputRedist.dll",
                    (const struct std::nothrow_t *)&lpFileName,
                    0);
  if ( SystemDirPath >= 0 )
  {
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW != -1
      && (FileAttributesW & 0x550) == 0
      && (int)GameInputModule::ValidateModuleCertChain(lpFileName) >= 0 )
    {
      Library = LoadLibraryExW(lpFileName, 0, 0x800u);
      v10 = Library;
      if ( Library )
      {
        if ( GameInputModule::ValidateModuleVersion(Library, v8)
          && (ProcAddress = GetProcAddress(v10, "GameInputCreate")) != 0
          && (v12 = GetProcAddress(v10, "DllCanUnloadNow")) != 0
          && (v13 = GetProcAddress(v10, "DllGetClassObject")) != 0 )
        {
          qword_1800698B8 = (__int64)ProcAddress;
          *(_QWORD *)&xmmword_1800698C0 = v12;
          *((_QWORD *)&xmmword_1800698C0 + 1) = v13;
          qword_1800698D0 = (__int64)v10;
        }
        else
        {
          FreeLibrary(v10);
        }
      }
    }
    g_redistModule = 2;
    v3 = 2;
    if ( lpFileName )
      operator delete((PVOID)lpFileName, v8);
    goto LABEL_19;
  }
  if ( lpFileName )
    operator delete((PVOID)lpFileName, v4);
  LeaveCriticalSection(&CriticalSection);
  return (unsigned int)SystemDirPath;
}

```

## disassembly

```asm
0x18002c6fc  mov     [rsp+arg_0], rbx
0x18002c701  mov     [rsp+arg_8], rbp
0x18002c706  mov     [rsp+lpFileName], r8
0x18002c70b  push    rsi
0x18002c70c  sub     rsp, 20h
0x18002c710  mov     ebx, cs:?g_redistModule@@3VGameInputModule@@A; GameInputModule g_redistModule
0x18002c716  nop
0x18002c717  test    ebx, ebx
0x18002c719  jnz     loc_18002C8A8
0x18002c71f  lea     rcx, CriticalSection; lpCriticalSection
0x18002c726  call    cs:__imp_EnterCriticalSection
0x18002c72d  nop     dword ptr [rax+rax+00h]
0x18002c732  mov     ebx, cs:?g_redistModule@@3VGameInputModule@@A; GameInputModule g_redistModule
0x18002c738  test    ebx, ebx
0x18002c73a  jnz     loc_18002C895
0x18002c740  xor     r8d, r8d
0x18002c743  mov     [rsp+28h+lpFileName], 0
0x18002c74c  lea     rdx, [rsp+28h+lpFileName]
0x18002c751  lea     rcx, aGameinputredis; "GameInputRedist.dll"
0x18002c758  call    ?GetSystemDirPath@GameInputModule@@CAJPEBGAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@PEA_K@Z; GameInputModule::GetSystemDirPath(ushort const *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &,unsigned __int64 *)
0x18002c75d  mov     rcx, [rsp+28h+lpFileName]; P
0x18002c762  mov     ebx, eax
0x18002c764  test    eax, eax
0x18002c766  jns     short loc_18002C78C
0x18002c768  test    rcx, rcx
0x18002c76b  jz      short loc_18002C772
0x18002c76d  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c772  lea     rcx, CriticalSection; lpCriticalSection
0x18002c779  call    cs:__imp_LeaveCriticalSection
0x18002c780  nop     dword ptr [rax+rax+00h]
0x18002c785  mov     eax, ebx
0x18002c787  jmp     loc_18002C8C0
0x18002c78c  call    cs:__imp_GetFileAttributesW
0x18002c793  nop     dword ptr [rax+rax+00h]
0x18002c798  cmp     eax, 0FFFFFFFFh
0x18002c79b  jz      loc_18002C873
0x18002c7a1  test    eax, 550h
0x18002c7a6  jnz     loc_18002C873
0x18002c7ac  mov     rcx, [rsp+28h+lpFileName]; unsigned __int16 *
0x18002c7b1  call    ?ValidateModuleCertChain@GameInputModule@@CAJPEBG@Z; GameInputModule::ValidateModuleCertChain(ushort const *)
0x18002c7b6  test    eax, eax
0x18002c7b8  js      loc_18002C873
0x18002c7be  mov     rcx, [rsp+28h+lpFileName]; lpLibFileName
0x18002c7c3  xor     edx, edx; hFile
0x18002c7c5  mov     r8d, 800h; dwFlags
0x18002c7cb  call    cs:__imp_LoadLibraryExW
0x18002c7d2  nop     dword ptr [rax+rax+00h]
0x18002c7d7  mov     rbx, rax
0x18002c7da  test    rax, rax
0x18002c7dd  jz      loc_18002C873
0x18002c7e3  mov     rcx, rax; HINSTANCE
0x18002c7e6  call    ?ValidateModuleVersion@GameInputModule@@CA_NPEAUHINSTANCE__@@AEBUGameInputVersion@@@Z; GameInputModule::ValidateModuleVersion(HINSTANCE__ *,GameInputVersion const &)
0x18002c7eb  test    al, al
0x18002c7ed  jz      short loc_18002C864
0x18002c7ef  lea     rdx, aGameinputcreat_0; "GameInputCreate"
0x18002c7f6  mov     rcx, rbx; hModule
0x18002c7f9  call    cs:__imp_GetProcAddress
0x18002c800  nop     dword ptr [rax+rax+00h]
0x18002c805  mov     rsi, rax
0x18002c808  test    rax, rax
0x18002c80b  jz      short loc_18002C864
0x18002c80d  lea     rdx, aDllcanunloadno_0; "DllCanUnloadNow"
0x18002c814  mov     rcx, rbx; hModule
0x18002c817  call    cs:__imp_GetProcAddress
0x18002c81e  nop     dword ptr [rax+rax+00h]
0x18002c823  mov     rbp, rax
0x18002c826  test    rax, rax
0x18002c829  jz      short loc_18002C864
0x18002c82b  lea     rdx, aDllgetclassobj_0; "DllGetClassObject"
0x18002c832  mov     rcx, rbx; hModule
0x18002c835  call    cs:__imp_GetProcAddress
0x18002c83c  nop     dword ptr [rax+rax+00h]
0x18002c841  test    rax, rax
0x18002c844  jz      short loc_18002C864
0x18002c846  mov     cs:qword_1800698B8, rsi
0x18002c84d  mov     qword ptr cs:xmmword_1800698C0, rbp
0x18002c854  mov     qword ptr cs:xmmword_1800698C0+8, rax
0x18002c85b  mov     cs:qword_1800698D0, rbx
0x18002c862  jmp     short loc_18002C873
0x18002c864  mov     rcx, rbx; hLibModule
0x18002c867  call    cs:__imp_FreeLibrary
0x18002c86e  nop     dword ptr [rax+rax+00h]
0x18002c873  cmp     [rsp+28h+lpFileName], 0
0x18002c879  nop
0x18002c87a  mov     cs:?g_redistModule@@3VGameInputModule@@A, 2; GameInputModule g_redistModule
0x18002c884  mov     ebx, 2
0x18002c889  jz      short loc_18002C895
0x18002c88b  mov     rcx, [rsp+28h+lpFileName]; P
0x18002c890  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002c895  lea     rcx, CriticalSection; lpCriticalSection
0x18002c89c  call    cs:__imp_LeaveCriticalSection
0x18002c8a3  nop     dword ptr [rax+rax+00h]
0x18002c8a8  cmp     ebx, 2
0x18002c8ab  jnz     short loc_18002C8BB
0x18002c8ad  xor     eax, eax
0x18002c8af  cmp     cs:qword_1800698D0, rax
0x18002c8b6  setz    al
0x18002c8b9  jmp     short loc_18002C8C0
0x18002c8bb  mov     eax, 8000FFFFh
0x18002c8c0  mov     rbx, [rsp+28h+arg_0]
0x18002c8c5  mov     rbp, [rsp+28h+arg_8]
0x18002c8ca  add     rsp, 20h
0x18002c8ce  pop     rsi
0x18002c8cf  retn
```
