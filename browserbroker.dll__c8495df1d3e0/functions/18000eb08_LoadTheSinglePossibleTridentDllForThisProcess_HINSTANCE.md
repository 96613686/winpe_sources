# LoadTheSinglePossibleTridentDllForThisProcess(HINSTANCE__ * *)

- ea: `0x18000eb08`
- end: `0x18000eba4`
- name: `?LoadTheSinglePossibleTridentDllForThisProcess@@YAJPEAPEAUHINSTANCE__@@@Z`
- size: `156`
- prototype: `__int64 __fastcall(HINSTANCE *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180008530`
- `0x180008d70`
- `0x180008e20`

## callees

- `0x18000a2dc`
- `0x18000eb08`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb78`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000eb78`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000eb2c`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18000eb2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000eb5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000eb5d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000eb47`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x18000eb47`

## string_xrefs

- `0x18000eb23`: `edgehtml.dll`

## pseudocode

```c
__int64 __fastcall LoadTheSinglePossibleTridentDllForThisProcess(HINSTANCE *a1)
{
  unsigned int v1; // ebx
  HMODULE Library; // rax
  __int64 (*ProcAddress)(void); // rax
  unsigned int ErrorError; // eax
  signed int LastError; // eax
  __int64 result; // rax

  v1 = 0;
  if ( !hModule )
  {
    Library = LoadLibraryExW(L"edgehtml.dll", 0, 0);
    if ( Library )
    {
      if ( _InterlockedCompareExchange64((volatile signed __int64 *)&hModule, (signed __int64)Library, 0) )
      {
        FreeLibrary(Library);
      }
      else
      {
        ProcAddress = GetProcAddress(hModule, "InitializeLocalHtmlEngine");
        if ( ProcAddress )
          ErrorError = ProcAddress();
        else
          ErrorError = HRESULTFromLastErrorError();
        v1 = ErrorError;
      }
    }
    else
    {
      LastError = GetLastError();
      v1 = LastError;
      if ( LastError > 0 )
        v1 = (unsigned __int16)LastError | 0x80070000;
    }
  }
  result = v1;
  *a1 = hModule;
  return result;
}

```

## disassembly

```asm
0x18000eb08  mov     [rsp+arg_0], rbx
0x18000eb0d  push    rdi
0x18000eb0e  sub     rsp, 20h
0x18000eb12  xor     ebx, ebx
0x18000eb14  mov     rdi, rcx
0x18000eb17  cmp     cs:hModule, rbx
0x18000eb1e  jnz     short loc_18000EB8D
0x18000eb20  xor     r8d, r8d; dwFlags
0x18000eb23  lea     rcx, aEdgehtmlDll; "edgehtml.dll"
0x18000eb2a  xor     edx, edx; hFile
0x18000eb2c  call    cs:__imp_LoadLibraryExW
0x18000eb32  mov     rcx, rax; hLibModule
0x18000eb35  test    rax, rax
0x18000eb38  jz      short loc_18000EB78
0x18000eb3a  xor     eax, eax
0x18000eb3c  lock cmpxchg cs:hModule, rcx
0x18000eb45  jz      short loc_18000EB4F
0x18000eb47  call    cs:__imp_FreeLibrary
0x18000eb4d  jmp     short loc_18000EB8D
0x18000eb4f  mov     rcx, cs:hModule; hModule
0x18000eb56  lea     rdx, aInitializeloca; "InitializeLocalHtmlEngine"
0x18000eb5d  call    cs:__imp_GetProcAddress
0x18000eb63  test    rax, rax
0x18000eb66  jz      short loc_18000EB6F
0x18000eb68  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000eb6d  jmp     short loc_18000EB74
0x18000eb6f  call    ?HRESULTFromLastErrorError@@YAJXZ; HRESULTFromLastErrorError(void)
0x18000eb74  mov     ebx, eax
0x18000eb76  jmp     short loc_18000EB8D
0x18000eb78  call    cs:__imp_GetLastError
0x18000eb7e  mov     ebx, eax
0x18000eb80  test    eax, eax
0x18000eb82  jle     short loc_18000EB8D
0x18000eb84  movzx   ebx, ax
0x18000eb87  or      ebx, 80070000h
0x18000eb8d  mov     rcx, cs:hModule
0x18000eb94  mov     eax, ebx
0x18000eb96  mov     rbx, [rsp+28h+arg_0]
0x18000eb9b  mov     [rdi], rcx
0x18000eb9e  add     rsp, 20h
0x18000eba2  pop     rdi
0x18000eba3  retn
```
