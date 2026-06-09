# WindowsPerformanceRecorder::Impl::GetTempDirectoryPath(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> &)

- ea: `0x18005aa04`
- end: `0x18005aaf2`
- name: `?GetTempDirectoryPath@Impl@WindowsPerformanceRecorder@@YAJAEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@Z`
- size: `238`
- prototype: ``
- caller_count: `3`
- callee_count: `5`
- tags: `loader_planting`

## callers

- `0x180032adc`
- `0x18004ac00`
- `0x180059e74`

## callees

- `0x18001c458`
- `0x18004ece0`
- `0x18004f964`
- `0x18005aa04`
- `0x18008c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18005aac5`
- `api-ms-win-core-libraryloader-l1-1-0!FreeLibrary` at `0x18005aac5`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18005aa75`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18005aa75`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18005aa58`
- `api-ms-win-core-libraryloader-l1-1-0!LoadLibraryExW` at `0x18005aa58`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18005aa91`
- `api-ms-win-core-file-l1-2-0!GetTempPathW` at `0x18005aa91`

## string_xrefs

- `0x18005aa51`: `kernelbase.dll`
- `0x18005aa6b`: `GetTempPath2W`

## pseudocode

```c
__int64 __fastcall WindowsPerformanceRecorder::Impl::GetTempDirectoryPath(__int64 a1)
{
  unsigned int v2; // ebx
  HMODULE Library; // rax
  HMODULE v4; // rdi
  FARPROC ProcAddress; // rax
  DWORD TempPathW; // eax
  HMODULE v8; // [rsp+28h] [rbp-440h]
  ATL::CAtlException *v10; // [rsp+38h] [rbp-430h] BYREF
  WCHAR Buffer[520]; // [rsp+40h] [rbp-428h] BYREF

  v2 = 0;
  memset_0(Buffer, 0, sizeof(Buffer));
  Library = LoadLibraryExW(L"kernelbase.dll", 0, 0x800u);
  v4 = Library;
  v8 = Library;
  if ( Library )
  {
    ProcAddress = GetProcAddress(Library, "GetTempPath2W");
    if ( ProcAddress )
      TempPathW = ((__int64 (__fastcall *)(__int64, WCHAR *))ProcAddress)(520, Buffer);
    else
      TempPathW = GetTempPathW(0x208u, Buffer);
    try
    {
      v2 = TempPathW == 0 ? 0xC5586006 : 0;
      if ( TempPathW )
        ATL::CSimpleStringT<unsigned short,0>::SetString(a1, Buffer);
    }
    catch ( ATL::CAtlException *v10 )
    {
      v2 = *(_DWORD *)v10;
      v4 = v8;
    }
    FreeLibrary(v4);
  }
  return v2;
}

```

## disassembly

```asm
0x18005aa04  mov     rax, rsp
0x18005aa07  push    rdi
0x18005aa08  sub     rsp, 460h
0x18005aa0f  mov     [rsp+468h+var_438], 0FFFFFFFFFFFFFFFEh
0x18005aa18  mov     [rax+10h], rbx
0x18005aa1c  mov     [rax+18h], rsi
0x18005aa20  mov     rax, cs:__security_cookie
0x18005aa27  xor     rax, rsp
0x18005aa2a  mov     [rsp+468h+var_18], rax
0x18005aa32  mov     rsi, rcx
0x18005aa35  xor     ebx, ebx
0x18005aa37  xor     edx, edx; Val
0x18005aa39  mov     r8d, 410h; Size
0x18005aa3f  lea     rcx, [rsp+468h+Buffer]; void *
0x18005aa44  call    memset_0
0x18005aa49  xor     edx, edx; hFile
0x18005aa4b  mov     r8d, 800h; dwFlags
0x18005aa51  lea     rcx, aKernelbaseDll; "kernelbase.dll"
0x18005aa58  call    cs:__imp_LoadLibraryExW
0x18005aa5e  mov     rdi, rax
0x18005aa61  mov     [rsp+468h+var_440], rax
0x18005aa66  test    rax, rax
0x18005aa69  jz      short loc_18005AACB
0x18005aa6b  lea     rdx, aGettemppath2w; "GetTempPath2W"
0x18005aa72  mov     rcx, rax; hModule
0x18005aa75  call    cs:__imp_GetProcAddress
0x18005aa7b  lea     rdx, [rsp+468h+Buffer]; lpBuffer
0x18005aa80  mov     ecx, 208h; nBufferLength
0x18005aa85  test    rax, rax
0x18005aa88  jz      short loc_18005AA91
0x18005aa8a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18005aa8f  jmp     short loc_18005AA97
0x18005aa91  call    cs:__imp_GetTempPathW
0x18005aa97  mov     ecx, eax
0x18005aa99  neg     eax
0x18005aa9b  sbb     ebx, ebx
0x18005aa9d  not     ebx
0x18005aa9f  and     ebx, 0C5586006h
0x18005aaa5  test    ecx, ecx
0x18005aaa7  jz      short loc_18005AAB7
0x18005aaa9  lea     rdx, [rsp+468h+Buffer]
0x18005aaae  mov     rcx, rsi
0x18005aab1  call    ?SetString@?$CSimpleStringT@G$0A@@ATL@@QEAAXPEBG@Z; ATL::CSimpleStringT<ushort,0>::SetString(ushort const *)
0x18005aab6  nop
0x18005aab7  jmp     short loc_18005AAC2
0x18005aab9  mov     ebx, [rsp+468h+var_448]
0x18005aabd  mov     rdi, [rsp+468h+var_440]
0x18005aac2  mov     rcx, rdi; hLibModule
0x18005aac5  call    cs:__imp_FreeLibrary
0x18005aacb  mov     eax, ebx
0x18005aacd  mov     rcx, [rsp+468h+var_18]
0x18005aad5  xor     rcx, rsp; StackCookie
0x18005aad8  call    __security_check_cookie
0x18005aadd  lea     r11, [rsp+468h+var_8]
0x18005aae5  mov     rbx, [r11+18h]
0x18005aae9  mov     rsi, [r11+20h]
0x18005aaed  mov     rsp, r11
0x18005aaf0  pop     rdi
0x18005aaf1  retn
```
