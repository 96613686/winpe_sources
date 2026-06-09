# HLoadResourceDLL

- ea: `0x1800457e8`
- end: `0x180045891`
- name: `HLoadResourceDLL`
- size: `169`
- prototype: `HMODULE __fastcall(__int64, wchar_t *)`
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800020b4`
- `0x180021c54`
- `0x180025c34`

## callees

- `0x180024ad4`
- `0x18003fe9c`
- `0x1800457e8`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180045844`
- `KERNEL32!LoadLibraryExW` at `0x180045844`
- `KERNEL32!GetLastError` at `0x180045858`
- `KERNEL32!GetLastError` at `0x180045858`

## string_xrefs

- `0x180045819`: `HLoadResourceDLL:Failed to load resource DLL '%ws'`
- `0x180045823`: `HLoadResourceDLL`
- `0x180045871`: `HLoadResourceDLL`
- `0x180045867`: `HLoadResourceDLL:Failed to load resource DLL '%ws': Error = %d`

## pseudocode

```c
HMODULE __fastcall HLoadResourceDLL(__int64 a1, wchar_t *a2)
{
  const WCHAR *v2; // rdi
  HMODULE Library; // rbx
  DWORD LastError; // eax

  v2 = (const WCHAR *)(a1 + 1040);
  if ( (int)GetFullPathFromFilename(*(void **)(a1 + 1568), a2, (STRSAFE_LPWSTR)(a1 + 1040)) >= 0 )
  {
    Library = LoadLibraryExW(v2, 0, 2 * (*(_DWORD *)(a1 + 1576) & 1u));
    if ( !Library )
    {
      LastError = GetLastError();
      WriteDbgTraceWarning(
        (__int64)"HLoadResourceDLL",
        (__int64)L"HLoadResourceDLL:Failed to load resource DLL '%ws': Error = %d",
        v2,
        LastError);
    }
  }
  else
  {
    Library = 0;
    WriteDbgTraceWarning(
      (__int64)"HLoadResourceDLL",
      (__int64)L"HLoadResourceDLL:Failed to load resource DLL '%ws'",
      a2);
  }
  return Library;
}

```

## disassembly

```asm
0x1800457e8  mov     [rsp+arg_0], rbx
0x1800457ed  mov     [rsp+arg_8], rsi
0x1800457f2  push    rdi
0x1800457f3  sub     rsp, 20h
0x1800457f7  lea     rdi, [rcx+410h]
0x1800457fe  mov     rbx, rcx
0x180045801  mov     rcx, [rcx+620h]; void *
0x180045808  mov     r8, rdi; pszDest
0x18004580b  mov     rsi, rdx
0x18004580e  call    GetFullPathFromFilename
0x180045813  test    eax, eax
0x180045815  jns     short loc_180045831
0x180045817  xor     ebx, ebx
0x180045819  lea     rdx, aHloadresourced_0; "HLoadResourceDLL:Failed to load resourc"...
0x180045820  mov     r8, rsi
0x180045823  lea     rcx, aHloadresourced_1; "HLoadResourceDLL"
0x18004582a  call    WriteDbgTraceWarning
0x18004582f  jmp     short loc_18004587D
0x180045831  mov     r8d, [rbx+628h]
0x180045838  xor     edx, edx; hFile
0x18004583a  and     r8d, 1
0x18004583e  mov     rcx, rdi; lpLibFileName
0x180045841  add     r8d, r8d; dwFlags
0x180045844  call    cs:__imp_LoadLibraryExW
0x18004584b  nop     dword ptr [rax+rax+00h]
0x180045850  mov     rbx, rax
0x180045853  test    rax, rax
0x180045856  jnz     short loc_18004587D
0x180045858  call    cs:__imp_GetLastError
0x18004585f  nop     dword ptr [rax+rax+00h]
0x180045864  mov     r8, rdi
0x180045867  lea     rdx, aHloadresourced; "HLoadResourceDLL:Failed to load resourc"...
0x18004586e  mov     r9d, eax
0x180045871  lea     rcx, aHloadresourced_1; "HLoadResourceDLL"
0x180045878  call    WriteDbgTraceWarning
0x18004587d  mov     rsi, [rsp+28h+arg_8]
0x180045882  mov     rax, rbx
0x180045885  mov     rbx, [rsp+28h+arg_0]
0x18004588a  add     rsp, 20h
0x18004588e  pop     rdi
0x18004588f  retn
```
