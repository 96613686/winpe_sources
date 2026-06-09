# GetFunctionFromDLL(char const *,char const *,bool)

- ea: `0x183068c50`
- end: `0x183068cec`
- name: `?GetFunctionFromDLL@@YAPEAXPEBD0_N@Z`
- size: `156`
- prototype: `void *(const char *, const char *, bool)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting`

## callees

- `0x182dcc6d0`
- `0x183068c50`

## import_xrefs

- `KERNEL32!FreeLibrary` at `0x183068cb0`
- `KERNEL32!FreeLibrary` at `0x183068cb0`
- `KERNEL32!GetProcAddress` at `0x183068c88`
- `KERNEL32!GetProcAddress` at `0x183068c88`
- `KERNEL32!LoadLibraryA` at `0x183068c6f`
- `KERNEL32!LoadLibraryA` at `0x183068c6f`

## pseudocode

```c
FARPROC __fastcall GetFunctionFromDLL(const char *a1, const char *a2, char a3)
{
  HMODULE LibraryA; // rax
  HMODULE v7; // rbp
  FARPROC result; // rax

  LibraryA = LoadLibraryA(a1);
  v7 = LibraryA;
  if ( LibraryA )
  {
    result = GetProcAddress(LibraryA, a2);
    if ( !result )
    {
      if ( a3 )
      {
        CxReportError("GetProcAddress for '%s' in '%s' failed.", a2, a1);
        FreeLibrary(v7);
        return 0;
      }
    }
  }
  else
  {
    if ( a3 )
      CxReportError("Failed to load '%s'.", a1);
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x183068c50  mov     [rsp+arg_8], rbp
0x183068c55  mov     [rsp+arg_10], rsi
0x183068c5a  mov     [rsp+arg_18], rdi
0x183068c5f  push    r14
0x183068c61  sub     rsp, 20h
0x183068c65  movzx   edi, r8b
0x183068c69  mov     r14, rdx
0x183068c6c  mov     rsi, rcx
0x183068c6f  call    cs:__imp_LoadLibraryA
0x183068c75  mov     rbp, rax
0x183068c78  test    rax, rax
0x183068c7b  jz      short loc_183068CD4
0x183068c7d  mov     rdx, r14; lpProcName
0x183068c80  mov     [rsp+28h+arg_0], rbx
0x183068c85  mov     rcx, rax; hModule
0x183068c88  call    cs:__imp_GetProcAddress
0x183068c8e  mov     rbx, rax
0x183068c91  test    rax, rax
0x183068c94  jnz     short loc_183068CB9
0x183068c96  test    dil, dil
0x183068c99  jz      short loc_183068CB9
0x183068c9b  mov     r8, rsi
0x183068c9e  lea     rcx, aGetprocaddress; "GetProcAddress for '%s' in '%s' failed."
0x183068ca5  mov     rdx, r14
0x183068ca8  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x183068cad  mov     rcx, rbp; hLibModule
0x183068cb0  call    cs:__imp_FreeLibrary
0x183068cb6  mov     rax, rbx
0x183068cb9  mov     rbx, [rsp+28h+arg_0]
0x183068cbe  mov     rbp, [rsp+28h+arg_8]
0x183068cc3  mov     rsi, [rsp+28h+arg_10]
0x183068cc8  mov     rdi, [rsp+28h+arg_18]
0x183068ccd  add     rsp, 20h
0x183068cd1  pop     r14
0x183068cd3  retn
0x183068cd4  test    dil, dil
0x183068cd7  jz      short loc_183068CE8
0x183068cd9  mov     rdx, rsi
0x183068cdc  lea     rcx, aFailedToLoadS; "Failed to load '%s'."
0x183068ce3  call    ?CxReportError@@YAXPEBDZZ; CxReportError(char const *,...)
0x183068ce8  xor     eax, eax
0x183068cea  jmp     short loc_183068CBE
```
