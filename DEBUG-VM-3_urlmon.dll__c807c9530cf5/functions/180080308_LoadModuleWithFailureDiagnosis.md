# LoadModuleWithFailureDiagnosis

- ea: `0x180080308`
- end: `0x1800804ab`
- name: `LoadModuleWithFailureDiagnosis`
- size: `419`
- prototype: ``
- caller_count: `2`
- callee_count: `4`
- tags: `loader_planting, service_task`

## callers

- `0x18007f9d0`
- `0x180080308`

## callees

- `0x180080308`
- `0x1800a7d38`
- `0x180108644`
- `0x18011ba3e`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180080325`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExA` at `0x180080325`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008041c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180080334`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18008041c`
- `imagehlp!ImageNtHeader` at `0x1800803ba`
- `imagehlp!ImageNtHeader` at `0x1800803ba`
- `imagehlp!UnMapAndLoad` at `0x1800803f0`
- `imagehlp!UnMapAndLoad` at `0x1800803f0`
- `imagehlp!ImageDirectoryEntryToData` at `0x180080394`
- `imagehlp!ImageDirectoryEntryToData` at `0x180080394`
- `imagehlp!MapAndLoad` at `0x180080369`
- `imagehlp!MapAndLoad` at `0x180080369`
- `imagehlp!ImageRvaToVa` at `0x1800803ce`
- `imagehlp!ImageRvaToVa` at `0x1800803ce`

## pseudocode

```c
HMODULE __fastcall LoadModuleWithFailureDiagnosis(const CHAR *a1)
{
  HMODULE result; // rax
  signed int LastError; // eax
  _DWORD *v4; // rax
  _DWORD *v5; // rdi
  ULONG v6; // ebx
  struct _IMAGE_NT_HEADERS64 *v7; // rax
  PVOID v8; // rax
  signed int v9; // eax
  _LOADED_IMAGE LoadedImage; // [rsp+30h] [rbp-68h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+98h] [rbp+0h]
  ULONG Size; // [rsp+A8h] [rbp+10h] BYREF

  result = LoadLibraryExA(a1, 0, 0x800u);
  if ( !result )
  {
    LastError = GetLastError();
    if ( LastError == 126 )
    {
      memset_0(&LoadedImage, 0, sizeof(LoadedImage));
      if ( MapAndLoad(a1, 0, &LoadedImage, 1, 1) )
      {
        Size = 0;
        v4 = ImageDirectoryEntryToData(LoadedImage.MappedAddress, 0, 1u, &Size);
        v5 = v4;
        if ( v4 && Size && v4[3] )
        {
          do
          {
            v6 = v5[3];
            v7 = ImageNtHeader(LoadedImage.MappedAddress);
            v8 = ImageRvaToVa(v7, LoadedImage.MappedAddress, v6, 0);
            if ( v8 )
              LoadModuleWithFailureDiagnosis(v8);
            v5 += 5;
          }
          while ( v5[3] );
        }
        UnMapAndLoad(&LoadedImage);
        wil::details::in1diag3::FailFast_UnexpectedMsg(
          retaddr,
          (void *)0x2F,
          (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
          "%hs",
          a1);
      }
      v9 = GetLastError();
      if ( v9 > 0 )
        v9 = (unsigned __int16)v9 | 0x80070000;
      wil::details::in1diag3::FailFast_HrMsg(
        retaddr,
        (void *)0x33,
        (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
        (const char *)(unsigned int)v9,
        (int)"%hs",
        a1);
    }
    if ( LastError > 0 )
      LastError = (unsigned __int16)LastError | 0x80070000;
    wil::details::in1diag3::FailFast_HrMsg(
      retaddr,
      (void *)0x38,
      (unsigned int)"onecoreuap\\inetcore\\lib\\isolation\\isoforwarder\\initonceimplementation.cpp",
      (const char *)(unsigned int)LastError,
      (int)"%hs",
      a1);
  }
  return result;
}

```

## disassembly

```asm
0x180080308  mov     [rsp+arg_0], rbx
0x18008030d  mov     [rsp+arg_10], rsi
0x180080312  push    rdi
0x180080313  sub     rsp, 90h
0x18008031a  xor     edx, edx; hFile
0x18008031c  mov     r8d, 800h; dwFlags
0x180080322  mov     rsi, rcx
0x180080325  call    cs:__imp_LoadLibraryExA
0x18008032b  test    rax, rax
0x18008032e  jnz     loc_180080496
0x180080334  call    cs:__imp_GetLastError
0x18008033a  cmp     eax, 7Eh ; '~'
0x18008033d  jnz     loc_18008045C
0x180080343  xor     edx, edx; Val
0x180080345  lea     r8d, [rax-26h]; Size
0x180080349  lea     rcx, [rsp+98h+LoadedImage]; void *
0x18008034e  call    memset_0
0x180080353  mov     ebx, 1
0x180080358  lea     r8, [rsp+98h+LoadedImage]; LoadedImage
0x18008035d  mov     r9d, ebx; DotDll
0x180080360  mov     [rsp+98h+ReadOnly], ebx; ReadOnly
0x180080364  xor     edx, edx; DllPath
0x180080366  mov     rcx, rsi; ImageName
0x180080369  call    cs:__imp_MapAndLoad
0x18008036f  test    eax, eax
0x180080371  jz      loc_18008041C
0x180080377  mov     rcx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x18008037c  lea     r9, [rsp+98h+Size]; Size
0x180080384  mov     r8d, ebx; DirectoryEntry
0x180080387  mov     [rsp+98h+Size], 0
0x180080392  xor     edx, edx; MappedAsImage
0x180080394  call    cs:__imp_ImageDirectoryEntryToData
0x18008039a  mov     rdi, rax
0x18008039d  test    rax, rax
0x1800803a0  jz      short loc_1800803EB
0x1800803a2  cmp     [rsp+98h+Size], 0
0x1800803aa  jz      short loc_1800803EB
0x1800803ac  cmp     dword ptr [rax+0Ch], 0
0x1800803b0  jz      short loc_1800803EB
0x1800803b2  mov     rcx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x1800803b7  mov     ebx, [rdi+0Ch]
0x1800803ba  call    cs:__imp_ImageNtHeader
0x1800803c0  mov     rdx, [rsp+98h+LoadedImage.MappedAddress]; Base
0x1800803c5  xor     r9d, r9d; LastRvaSection
0x1800803c8  mov     rcx, rax; NtHeaders
0x1800803cb  mov     r8d, ebx; Rva
0x1800803ce  call    cs:__imp_ImageRvaToVa
0x1800803d4  test    rax, rax
0x1800803d7  jz      short loc_1800803E1
0x1800803d9  mov     rcx, rax
0x1800803dc  call    LoadModuleWithFailureDiagnosis
0x1800803e1  add     rdi, 14h
0x1800803e5  cmp     dword ptr [rdi+0Ch], 0
0x1800803e9  jnz     short loc_1800803B2
0x1800803eb  lea     rcx, [rsp+98h+LoadedImage]; LoadedImage
0x1800803f0  call    cs:__imp_UnMapAndLoad
0x1800803f6  mov     rcx, [rsp+98h]; this
0x1800803fe  lea     r9, aHs; "%hs"
0x180080405  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x18008040c  mov     qword ptr [rsp+98h+ReadOnly], rsi; char *
0x180080411  mov     edx, 2Fh ; '/'; void *
0x180080416  call    ?FailFast_UnexpectedMsg@in1diag3@details@wil@@YAXPEAXIPEBD1ZZ; wil::details::in1diag3::FailFast_UnexpectedMsg(void *,uint,char const *,char const *,...)
0x18008041c  call    cs:__imp_GetLastError
0x180080422  test    eax, eax
0x180080424  jle     short loc_18008042E
0x180080426  movzx   eax, ax
0x180080429  or      eax, 80070000h
0x18008042e  mov     rcx, [rsp+98h]; this
0x180080436  lea     rdx, aHs; "%hs"
0x18008043d  mov     [rsp+98h+var_70], rsi; char *
0x180080442  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180080449  mov     qword ptr [rsp+98h+ReadOnly], rdx; int
0x18008044e  mov     r9d, eax; char *
0x180080451  mov     edx, 33h ; '3'; void *
0x180080456  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x18008045c  test    eax, eax
0x18008045e  jle     short loc_180080468
0x180080460  movzx   eax, ax
0x180080463  or      eax, 80070000h
0x180080468  mov     rcx, [rsp+98h]; this
0x180080470  lea     rdx, aHs; "%hs"
0x180080477  mov     [rsp+98h+var_70], rsi; char *
0x18008047c  lea     r8, aOnecoreuapInet_10; "onecoreuap\\inetcore\\lib\\isolation\\i"...
0x180080483  mov     qword ptr [rsp+98h+ReadOnly], rdx; int
0x180080488  mov     r9d, eax; char *
0x18008048b  mov     edx, 38h ; '8'; void *
0x180080490  call    ?FailFast_HrMsg@in1diag3@details@wil@@YAXPEAXIPEBDJ1ZZ; wil::details::in1diag3::FailFast_HrMsg(void *,uint,char const *,long,char const *,...)
0x180080496  lea     r11, [rsp+98h+var_8]
0x18008049e  mov     rbx, [r11+10h]
0x1800804a2  mov     rsi, [r11+20h]
0x1800804a6  mov     rsp, r11
0x1800804a9  pop     rdi
0x1800804aa  retn
```
