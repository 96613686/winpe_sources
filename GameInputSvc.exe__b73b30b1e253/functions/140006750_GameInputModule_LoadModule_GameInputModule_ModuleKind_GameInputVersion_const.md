# GameInputModule::LoadModule(GameInputModule::ModuleKind,GameInputVersion const &)

- ea: `0x140006750`
- end: `0x1400068d7`
- name: `?LoadModule@GameInputModule@@AEAAJW4ModuleKind@1@AEBUGameInputVersion@@@Z`
- size: `391`
- prototype: `__int64 __fastcall(struct _RTL_CRITICAL_SECTION *, int, const WCHAR *)`
- caller_count: `1`
- callee_count: `5`
- tags: `file_ops, loader_planting`

## callers

- `0x14000199c`

## callees

- `0x140006578`
- `0x140006750`
- `0x1400068e0`
- `0x140006a78`
- `0x140006b48`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400067d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400068af`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400067d5`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x1400068af`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006779`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x140006779`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400067e2`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x1400067e2`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000681b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x14000681b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000683f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006857`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000686f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000683f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006857`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000686f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000688f`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x14000688f`

## string_xrefs

- `0x1400067a8`: `GameInput.dll`
- `0x140006795`: `GameInputRedist.dll`
- `0x140006835`: `GameInputCreate`
- `0x14000684d`: `DllCanUnloadNow`
- `0x140006865`: `DllGetClassObject`

## pseudocode

```c
__int64 __fastcall GameInputModule::LoadModule(struct _RTL_CRITICAL_SECTION *a1, int a2, const WCHAR *a3)
{
  int DebugInfo; // edi
  struct _RTL_CRITICAL_SECTION *v6; // r14
  const wchar_t *v7; // rcx
  int SystemDirPath; // edi
  DWORD FileAttributesW; // eax
  HMODULE Library; // rax
  const struct GameInputVersion *v12; // rdx
  HMODULE v13; // rdi
  FARPROC ProcAddress; // r15
  FARPROC v15; // r12
  FARPROC v16; // rax
  bool v17; // zf
  LPCWSTR lpFileName; // [rsp+70h] [rbp+18h] BYREF

  lpFileName = a3;
  DebugInfo = (int)a1->DebugInfo;
  if ( LODWORD(a1->DebugInfo) )
    goto LABEL_23;
  v6 = a1 + 1;
  EnterCriticalSection(a1 + 1);
  DebugInfo = (int)a1->DebugInfo;
  if ( LODWORD(a1->DebugInfo) || (unsigned int)(a2 - 1) > 1 )
  {
LABEL_22:
    LeaveCriticalSection(v6);
LABEL_23:
    if ( DebugInfo == a2 )
      return a1->SpinCount == 0;
    else
      return 2147549183LL;
  }
  lpFileName = 0;
  v7 = L"GameInput.dll";
  if ( a2 != 1 )
    v7 = L"GameInputRedist.dll";
  SystemDirPath = GameInputModule::GetSystemDirPath(v7, &lpFileName);
  if ( SystemDirPath >= 0 )
  {
    FileAttributesW = GetFileAttributesW(lpFileName);
    if ( FileAttributesW != -1
      && (FileAttributesW & 0x550) == 0
      && (int)GameInputModule::ValidateModuleCertChain(lpFileName) >= 0 )
    {
      Library = LoadLibraryExW(lpFileName, 0, 0x800u);
      v13 = Library;
      if ( Library )
      {
        if ( GameInputModule::ValidateModuleVersion(Library, v12)
          && (ProcAddress = GetProcAddress(v13, "GameInputCreate")) != 0
          && (v15 = GetProcAddress(v13, "DllCanUnloadNow")) != 0
          && (v16 = GetProcAddress(v13, "DllGetClassObject")) != 0 )
        {
          *(_QWORD *)&a1->LockCount = ProcAddress;
          a1->OwningThread = v15;
          a1->LockSemaphore = v16;
          a1->SpinCount = (ULONG_PTR)v13;
        }
        else
        {
          FreeLibrary(v13);
        }
      }
    }
    v17 = lpFileName == 0;
    LODWORD(a1->DebugInfo) = a2;
    DebugInfo = a2;
    if ( !v17 )
      operator delete[]((PVOID)lpFileName);
    goto LABEL_22;
  }
  if ( lpFileName )
    operator delete[]((PVOID)lpFileName);
  LeaveCriticalSection(v6);
  return (unsigned int)SystemDirPath;
}

```

## disassembly

```asm
0x140006750  mov     [rsp+lpFileName], r8
0x140006755  push    rbx
0x140006756  push    rsi
0x140006757  push    rdi
0x140006758  push    r12
0x14000675a  push    r14
0x14000675c  push    r15
0x14000675e  sub     rsp, 28h
0x140006762  mov     edi, [rcx]
0x140006764  mov     esi, edx
0x140006766  mov     rbx, rcx
0x140006769  nop
0x14000676a  test    edi, edi
0x14000676c  jnz     loc_1400068B5
0x140006772  lea     r14, [rcx+28h]
0x140006776  mov     rcx, r14; lpCriticalSection
0x140006779  call    cs:__imp_EnterCriticalSection
0x14000677f  mov     edi, [rbx]
0x140006781  test    edi, edi
0x140006783  jnz     loc_1400068AC
0x140006789  lea     eax, [rsi-1]
0x14000678c  cmp     eax, 1
0x14000678f  ja      loc_1400068AC
0x140006795  lea     rax, aGameinputredis; "GameInputRedist.dll"
0x14000679c  mov     [rsp+58h+lpFileName], 0
0x1400067a5  cmp     esi, 1
0x1400067a8  lea     rcx, aGameinputDll; "GameInput.dll"
0x1400067af  lea     rdx, [rsp+58h+lpFileName]
0x1400067b4  cmovnz  rcx, rax
0x1400067b8  call    ?GetSystemDirPath@GameInputModule@@CAJPEBGAEAV?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@utl@@@utl@@PEA_K@Z; GameInputModule::GetSystemDirPath(ushort const *,utl::unique_ptr<ushort [0],utl::default_delete<ushort [0]>> &,unsigned __int64 *)
0x1400067bd  mov     rcx, [rsp+58h+lpFileName]; P
0x1400067c2  mov     edi, eax
0x1400067c4  test    eax, eax
0x1400067c6  jns     short loc_1400067E2
0x1400067c8  test    rcx, rcx
0x1400067cb  jz      short loc_1400067D2
0x1400067cd  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1400067d2  mov     rcx, r14; lpCriticalSection
0x1400067d5  call    cs:__imp_LeaveCriticalSection
0x1400067db  mov     eax, edi
0x1400067dd  jmp     loc_1400068C9
0x1400067e2  call    cs:__imp_GetFileAttributesW
0x1400067e8  cmp     eax, 0FFFFFFFFh
0x1400067eb  jz      loc_140006895
0x1400067f1  test    eax, 550h
0x1400067f6  jnz     loc_140006895
0x1400067fc  mov     rcx, [rsp+58h+lpFileName]; unsigned __int16 *
0x140006801  call    ?ValidateModuleCertChain@GameInputModule@@CAJPEBG@Z; GameInputModule::ValidateModuleCertChain(ushort const *)
0x140006806  test    eax, eax
0x140006808  js      loc_140006895
0x14000680e  mov     rcx, [rsp+58h+lpFileName]; lpLibFileName
0x140006813  xor     edx, edx; hFile
0x140006815  mov     r8d, 800h; dwFlags
0x14000681b  call    cs:__imp_LoadLibraryExW
0x140006821  mov     rdi, rax
0x140006824  test    rax, rax
0x140006827  jz      short loc_140006895
0x140006829  mov     rcx, rax; HINSTANCE
0x14000682c  call    ?ValidateModuleVersion@GameInputModule@@CA_NPEAUHINSTANCE__@@AEBUGameInputVersion@@@Z; GameInputModule::ValidateModuleVersion(HINSTANCE__ *,GameInputVersion const &)
0x140006831  test    al, al
0x140006833  jz      short loc_14000688C
0x140006835  lea     rdx, ProcName; "GameInputCreate"
0x14000683c  mov     rcx, rdi; hModule
0x14000683f  call    cs:__imp_GetProcAddress
0x140006845  mov     r15, rax
0x140006848  test    rax, rax
0x14000684b  jz      short loc_14000688C
0x14000684d  lea     rdx, aDllcanunloadno; "DllCanUnloadNow"
0x140006854  mov     rcx, rdi; hModule
0x140006857  call    cs:__imp_GetProcAddress
0x14000685d  mov     r12, rax
0x140006860  test    rax, rax
0x140006863  jz      short loc_14000688C
0x140006865  lea     rdx, aDllgetclassobj; "DllGetClassObject"
0x14000686c  mov     rcx, rdi; hModule
0x14000686f  call    cs:__imp_GetProcAddress
0x140006875  test    rax, rax
0x140006878  jz      short loc_14000688C
0x14000687a  mov     [rbx+8], r15
0x14000687e  mov     [rbx+10h], r12
0x140006882  mov     [rbx+18h], rax
0x140006886  mov     [rbx+20h], rdi
0x14000688a  jmp     short loc_140006895
0x14000688c  mov     rcx, rdi; hLibModule
0x14000688f  call    cs:__imp_FreeLibrary
0x140006895  cmp     [rsp+58h+lpFileName], 0
0x14000689b  nop
0x14000689c  mov     [rbx], esi
0x14000689e  mov     edi, esi
0x1400068a0  jz      short loc_1400068AC
0x1400068a2  mov     rcx, [rsp+58h+lpFileName]; P
0x1400068a7  call    ??_V@YAXPEAX@Z; operator delete[](void *)
0x1400068ac  mov     rcx, r14; lpCriticalSection
0x1400068af  call    cs:__imp_LeaveCriticalSection
0x1400068b5  cmp     edi, esi
0x1400068b7  jnz     short loc_1400068C4
0x1400068b9  xor     eax, eax
0x1400068bb  cmp     [rbx+20h], rax
0x1400068bf  setz    al
0x1400068c2  jmp     short loc_1400068C9
0x1400068c4  mov     eax, 8000FFFFh
0x1400068c9  add     rsp, 28h
0x1400068cd  pop     r15
0x1400068cf  pop     r14
0x1400068d1  pop     r12
0x1400068d3  pop     rdi
0x1400068d4  pop     rsi
0x1400068d5  pop     rbx
0x1400068d6  retn
```
