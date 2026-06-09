# GetEdpProcs(void)

- ea: `0x180146168`
- end: `0x180146224`
- name: `?GetEdpProcs@@YA_NXZ`
- size: `188`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x180128080`
- `0x1801f60ac`

## callees

- `0x18002ab44`
- `0x18002abb0`
- `0x180146168`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801461f3`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1801461f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801461c6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1801461c6`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801461aa`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1801461aa`

## string_xrefs

- `0x18014619d`: `edputil.dll`

## pseudocode

```c
char GetEdpProcs(void)
{
  char v0; // bl
  HMODULE Library; // rax
  int (*ProcAddress)(void); // rcx
  unsigned int v4; // [rsp+30h] [rbp+8h] BYREF

  CWriteLock::CWriteLock(&v4, 0);
  v0 = 0;
  if ( g_pfnEdpGetIsManaged )
    goto LABEL_11;
  Library = qword_1802DF268;
  if ( qword_1802DF268 != (HMODULE)-1LL )
  {
    if ( qword_1802DF268 )
      goto LABEL_9;
    Library = LoadLibraryExW(L"edputil.dll", 0, 0x800u);
    qword_1802DF268 = Library;
    if ( Library )
    {
      ProcAddress = (int (*)(void))GetProcAddress(Library, "EdpGetIsManaged");
      g_pfnEdpGetIsManaged = ProcAddress;
      Library = qword_1802DF268;
    }
    else
    {
      ProcAddress = g_pfnEdpGetIsManaged;
    }
    if ( ProcAddress )
      goto LABEL_11;
    if ( Library )
    {
LABEL_9:
      FreeLibrary(Library);
      ProcAddress = g_pfnEdpGetIsManaged;
    }
    qword_1802DF268 = (HMODULE)-1LL;
    if ( ProcAddress )
LABEL_11:
      v0 = 1;
  }
  CWriteLock::~CWriteLock((CWriteLock *)&v4);
  return v0;
}

```

## disassembly

```asm
0x180146168  push    rbx
0x18014616a  sub     rsp, 20h
0x18014616e  xor     edx, edx
0x180146170  lea     rcx, [rsp+28h+arg_0]
0x180146175  call    ??0CWriteLock@@QEAA@W4LOCK_TYPE@@@Z; CWriteLock::CWriteLock(LOCK_TYPE)
0x18014617a  xor     ebx, ebx
0x18014617c  cmp     cs:?g_pfnEdpGetIsManaged@@3P6AHXZEA, rbx; int (*g_pfnEdpGetIsManaged)(void)
0x180146183  jnz     loc_180146210
0x180146189  mov     rax, cs:qword_1802DF268
0x180146190  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180146194  jz      short loc_180146212
0x180146196  test    rax, rax
0x180146199  jnz     short loc_1801461F0
0x18014619b  xor     edx, edx; hFile
0x18014619d  lea     rcx, aEdputilDll; "edputil.dll"
0x1801461a4  mov     r8d, 800h; dwFlags
0x1801461aa  call    cs:__imp_LoadLibraryExW
0x1801461b0  mov     cs:qword_1802DF268, rax
0x1801461b7  test    rax, rax
0x1801461ba  jz      short loc_1801461DF
0x1801461bc  lea     rdx, aEdpgetismanage; "EdpGetIsManaged"
0x1801461c3  mov     rcx, rax; hModule
0x1801461c6  call    cs:__imp_GetProcAddress
0x1801461cc  mov     rcx, rax
0x1801461cf  mov     cs:?g_pfnEdpGetIsManaged@@3P6AHXZEA, rax; int (*g_pfnEdpGetIsManaged)(void)
0x1801461d6  mov     rax, cs:qword_1802DF268
0x1801461dd  jmp     short loc_1801461E6
0x1801461df  mov     rcx, cs:?g_pfnEdpGetIsManaged@@3P6AHXZEA; int (*g_pfnEdpGetIsManaged)(void)
0x1801461e6  test    rcx, rcx
0x1801461e9  jnz     short loc_180146210
0x1801461eb  test    rax, rax
0x1801461ee  jz      short loc_180146200
0x1801461f0  mov     rcx, rax; hLibModule
0x1801461f3  call    cs:__imp_FreeLibrary
0x1801461f9  mov     rcx, cs:?g_pfnEdpGetIsManaged@@3P6AHXZEA; int (*g_pfnEdpGetIsManaged)(void)
0x180146200  mov     cs:qword_1802DF268, 0FFFFFFFFFFFFFFFFh
0x18014620b  test    rcx, rcx
0x18014620e  jz      short loc_180146212
0x180146210  mov     bl, 1
0x180146212  lea     rcx, [rsp+28h+arg_0]; this
0x180146217  call    ??1CWriteLock@@QEAA@XZ; CWriteLock::~CWriteLock(void)
0x18014621c  mov     al, bl
0x18014621e  add     rsp, 20h
0x180146222  pop     rbx
0x180146223  retn
```
