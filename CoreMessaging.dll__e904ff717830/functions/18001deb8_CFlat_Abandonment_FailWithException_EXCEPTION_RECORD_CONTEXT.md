# CFlat::Abandonment::FailWithException(_EXCEPTION_RECORD *,_CONTEXT *)

- ea: `0x18001deb8`
- end: `0x18001df4f`
- name: `?FailWithException@Abandonment@CFlat@@SAXPEAU_EXCEPTION_RECORD@@PEAU_CONTEXT@@@Z`
- size: `151`
- prototype: `void __fastcall(struct _EXCEPTION_RECORD *, struct _CONTEXT *)`
- caller_count: `11`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18001dca0`
- `0x180020df8`
- `0x18003950c`
- `0x180090c40`
- `0x1800a236c`
- `0x1800a2560`
- `0x1800a25a0`
- `0x1800a25e0`
- `0x1800a2660`
- `0x1800a2710`
- `0x1800b94cc`

## callees

- `0x18001deb8`
- `0x1800cf010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001df0b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001df0b`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001def9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x18001def9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df20`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001df20`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001dedb`
- `api-ms-win-core-debug-l1-1-0!DebugBreak` at `0x18001dedb`

## string_xrefs

- `0x18001def2`: `api-ms-win-core-errorhandling-l1-1-2.dll`
- `0x18001df04`: `kernel32.dll`

## pseudocode

```c
void __fastcall CFlat::Abandonment::FailWithException(struct _EXCEPTION_RECORD *a1, struct _CONTEXT *a2)
{
  HMODULE Library; // rax
  FARPROC ProcAddress; // rax

  if ( Cn::Process::FailFastDebug )
    DebugBreak();
  Library = LoadLibraryExW(L"api-ms-win-core-errorhandling-l1-1-2.dll", 0, 0);
  if ( Library || (Library = GetModuleHandleW(L"kernel32.dll")) != 0 )
  {
    ProcAddress = GetProcAddress(Library, "RaiseFailFastException");
    if ( ProcAddress )
      ((void (__fastcall *)(struct _EXCEPTION_RECORD *, struct _CONTEXT *, _QWORD))ProcAddress)(a1, a2, 0);
  }
  MEMORY[0] = 0;
}

```

## disassembly

```asm
0x18001deb8  mov     [rsp+arg_10], rbx
0x18001debd  mov     [rsp+arg_8], rdx
0x18001dec2  mov     [rsp+arg_0], rcx
0x18001dec7  push    rdi
0x18001dec8  sub     rsp, 20h
0x18001decc  mov     rbx, rdx
0x18001decf  mov     rdi, rcx
0x18001ded2  cmp     cs:?FailFastDebug@Process@Cn@@2_NA, 0; bool Cn::Process::FailFastDebug
0x18001ded9  jz      short loc_18001DEED
0x18001dedb  call    cs:__imp_DebugBreak
0x18001dee1  jmp     short loc_18001DEED
0x18001dee3  mov     rbx, [rsp+28h+arg_8]
0x18001dee8  mov     rdi, [rsp+28h+arg_0]
0x18001deed  xor     r8d, r8d; dwFlags
0x18001def0  xor     edx, edx; hFile
0x18001def2  lea     rcx, LibFileName; "api-ms-win-core-errorhandling-l1-1-2.dl"...
0x18001def9  call    cs:__imp_LoadLibraryExW
0x18001deff  test    rax, rax
0x18001df02  jnz     short loc_18001DF16
0x18001df04  lea     rcx, aKernel32Dll; "kernel32.dll"
0x18001df0b  call    cs:__imp_GetModuleHandleW
0x18001df11  test    rax, rax
0x18001df14  jz      short loc_18001DF39
0x18001df16  lea     rdx, ProcName; "RaiseFailFastException"
0x18001df1d  mov     rcx, rax; hModule
0x18001df20  call    cs:__imp_GetProcAddress
0x18001df26  test    rax, rax
0x18001df29  jz      short loc_18001DF39
0x18001df2b  xor     r8d, r8d
0x18001df2e  mov     rdx, rbx
0x18001df31  mov     rcx, rdi
0x18001df34  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001df39  mov     dword ptr ds:0, 0
0x18001df44  mov     rbx, [rsp+28h+arg_10]
0x18001df49  add     rsp, 20h
0x18001df4d  pop     rdi
0x18001df4e  retn
```
