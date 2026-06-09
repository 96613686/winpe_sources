# HLoadResourceDLL

- ea: `0x180044538`
- end: `0x1800445d4`
- name: `HLoadResourceDLL`
- size: `156`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x18000225c`
- `0x18002176c`
- `0x180025618`

## callees

- `0x180024554`
- `0x18003ed80`
- `0x180044538`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180044594`
- `KERNEL32!LoadLibraryExW` at `0x180044594`
- `KERNEL32!GetLastError` at `0x1800445a2`
- `KERNEL32!GetLastError` at `0x1800445a2`

## string_xrefs

- `0x180044569`: `HLoadResourceDLL:Failed to load resource DLL '%ws'`
- `0x180044573`: `HLoadResourceDLL`
- `0x1800445b5`: `HLoadResourceDLL`
- `0x1800445ab`: `HLoadResourceDLL:Failed to load resource DLL '%ws': Error = %d`

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
        "HLoadResourceDLL",
        L"HLoadResourceDLL:Failed to load resource DLL '%ws': Error = %d",
        v2,
        LastError);
    }
  }
  else
  {
    Library = 0;
    WriteDbgTraceWarning("HLoadResourceDLL", L"HLoadResourceDLL:Failed to load resource DLL '%ws'", a2);
  }
  return Library;
}

```

## disassembly

```asm
0x180044538  mov     [rsp+arg_0], rbx
0x18004453d  mov     [rsp+arg_8], rsi
0x180044542  push    rdi
0x180044543  sub     rsp, 20h
0x180044547  lea     rdi, [rcx+410h]
0x18004454e  mov     rbx, rcx
0x180044551  mov     rcx, [rcx+620h]; void *
0x180044558  mov     r8, rdi; pszDest
0x18004455b  mov     rsi, rdx
0x18004455e  call    GetFullPathFromFilename
0x180044563  test    eax, eax
0x180044565  jns     short loc_180044581
0x180044567  xor     ebx, ebx
0x180044569  lea     rdx, aHloadresourced_0; "HLoadResourceDLL:Failed to load resourc"...
0x180044570  mov     r8, rsi
0x180044573  lea     rcx, aHloadresourced_1; "HLoadResourceDLL"
0x18004457a  call    WriteDbgTraceWarning
0x18004457f  jmp     short loc_1800445C1
0x180044581  mov     r8d, [rbx+628h]
0x180044588  xor     edx, edx; hFile
0x18004458a  and     r8d, 1
0x18004458e  mov     rcx, rdi; lpLibFileName
0x180044591  add     r8d, r8d; dwFlags
0x180044594  call    cs:__imp_LoadLibraryExW
0x18004459a  mov     rbx, rax
0x18004459d  test    rax, rax
0x1800445a0  jnz     short loc_1800445C1
0x1800445a2  call    cs:__imp_GetLastError
0x1800445a8  mov     r8, rdi
0x1800445ab  lea     rdx, aHloadresourced; "HLoadResourceDLL:Failed to load resourc"...
0x1800445b2  mov     r9d, eax
0x1800445b5  lea     rcx, aHloadresourced_1; "HLoadResourceDLL"
0x1800445bc  call    WriteDbgTraceWarning
0x1800445c1  mov     rsi, [rsp+28h+arg_8]
0x1800445c6  mov     rax, rbx
0x1800445c9  mov     rbx, [rsp+28h+arg_0]
0x1800445ce  add     rsp, 20h
0x1800445d2  pop     rdi
0x1800445d3  retn
```
