# GetNextDirEntry

- ea: `0x180076078`
- end: `0x18007623a`
- name: `GetNextDirEntry`
- size: `450`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180076610`

## callees

- `0x180076078`
- `0x180076ce8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x1800760eb`
- `KERNEL32!GetLastError` at `0x180076191`
- `KERNEL32!GetLastError` at `0x1800760eb`
- `KERNEL32!GetLastError` at `0x180076191`
- `KERNEL32!FindNextFileW` at `0x1800760a0`
- `KERNEL32!FindNextFileW` at `0x1800760a0`
- `KERNEL32!FindClose` at `0x180076171`
- `KERNEL32!FindClose` at `0x180076206`
- `KERNEL32!FindClose` at `0x180076171`
- `KERNEL32!FindClose` at `0x180076206`
- `KERNEL32!LocalFree` at `0x180076180`
- `KERNEL32!LocalFree` at `0x180076215`
- `KERNEL32!LocalFree` at `0x180076180`
- `KERNEL32!LocalFree` at `0x180076215`
- `KERNEL32!SetCurrentDirectoryW` at `0x180076130`
- `KERNEL32!SetCurrentDirectoryW` at `0x180076130`
- `KERNEL32!lstrcmpW` at `0x1800760bb`
- `KERNEL32!lstrcmpW` at `0x1800760d6`
- `KERNEL32!lstrcmpW` at `0x1800760bb`
- `KERNEL32!lstrcmpW` at `0x1800760d6`

## string_xrefs

- `0x18007619d`: `Error %d leaving directory [%ws]\n`
- `0x1800761d5`: `Error %d leaving directory [%ws]\n`

## pseudocode

```c
char *__fastcall GetNextDirEntry(char *hMem)
{
  DWORD LastError; // esi
  HANDLE *v3; // rbx
  HANDLE *v4; // rbx

  LastError = 18;
  while ( hMem )
  {
    while ( FindNextFileW(*((HANDLE *)hMem + 1), (LPWIN32_FIND_DATAW)(hMem + 24)) )
    {
      if ( lstrcmpW((LPCWSTR)hMem + 34, L".") && lstrcmpW((LPCWSTR)hMem + 34, L"..") )
        return hMem;
    }
    LastError = GetLastError();
    if ( LastError != 18 )
      dprintf(
        5,
        (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
        513,
        (unsigned int)L"Error %d while scanning [%ws]\n");
    if ( !SetCurrentDirectoryW(L"..") )
    {
      LastError = GetLastError();
      dprintf(
        5,
        (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
        519,
        (unsigned int)L"Error %d leaving directory [%ws]\n");
      break;
    }
    dprintf(
      5,
      (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
      523,
      (unsigned int)L"Leaving  [%ws]\n");
    v3 = (HANDLE *)hMem;
    hMem = *(char **)hMem;
    FindClose(v3[1]);
    LocalFree(v3);
  }
  if ( LastError != 18 )
  {
    while ( hMem )
    {
      dprintf(
        5,
        (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
        539,
        (unsigned int)L"Error %d leaving directory [%ws]\n");
      v4 = (HANDLE *)hMem;
      hMem = *(char **)hMem;
      FindClose(v4[1]);
      LocalFree(v4);
    }
  }
  return hMem;
}

```

## disassembly

```asm
0x180076078  mov     [rsp+arg_0], rbx
0x18007607d  mov     [rsp+arg_8], rsi
0x180076082  push    rdi
0x180076083  sub     rsp, 30h
0x180076087  mov     rdi, rcx
0x18007608a  mov     esi, 12h
0x18007608f  test    rdi, rdi
0x180076092  jz      loc_1800761CA
0x180076098  mov     rcx, [rdi+8]; hFindFile
0x18007609c  lea     rdx, [rdi+18h]; lpFindFileData
0x1800760a0  call    cs:__imp_FindNextFileW
0x1800760a7  nop     dword ptr [rax+rax+00h]
0x1800760ac  test    eax, eax
0x1800760ae  jz      short loc_1800760EB
0x1800760b0  lea     rdx, asc_1800B07A0; "."
0x1800760b7  lea     rcx, [rdi+44h]; lpString1
0x1800760bb  call    cs:__imp_lstrcmpW
0x1800760c2  nop     dword ptr [rax+rax+00h]
0x1800760c7  test    eax, eax
0x1800760c9  jz      short loc_180076098
0x1800760cb  lea     rdx, PathName; ".."
0x1800760d2  lea     rcx, [rdi+44h]; lpString1
0x1800760d6  call    cs:__imp_lstrcmpW
0x1800760dd  nop     dword ptr [rax+rax+00h]
0x1800760e2  test    eax, eax
0x1800760e4  jz      short loc_180076098
0x1800760e6  jmp     loc_180076226
0x1800760eb  call    cs:__imp_GetLastError
0x1800760f2  nop     dword ptr [rax+rax+00h]
0x1800760f7  mov     esi, eax
0x1800760f9  cmp     eax, 12h
0x1800760fc  jz      short loc_180076129
0x1800760fe  mov     rax, [rdi+10h]
0x180076102  lea     r9, aErrorDWhileSca; "Error %d while scanning [%ws]\n"
0x180076109  mov     [rsp+38h+var_10], rax
0x18007610e  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180076115  mov     r8d, 201h
0x18007611b  mov     dword ptr [rsp+38h+var_18], esi
0x18007611f  mov     ecx, 5
0x180076124  call    dprintf
0x180076129  lea     rcx, PathName; ".."
0x180076130  call    cs:__imp_SetCurrentDirectoryW
0x180076137  nop     dword ptr [rax+rax+00h]
0x18007613c  test    eax, eax
0x18007613e  jz      short loc_180076191
0x180076140  mov     rax, [rdi+10h]
0x180076144  lea     r9, aLeavingWs; "Leaving  [%ws]\n"
0x18007614b  mov     r8d, 20Bh
0x180076151  mov     [rsp+38h+var_18], rax
0x180076156  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x18007615d  mov     ecx, 5
0x180076162  call    dprintf
0x180076167  mov     rbx, rdi
0x18007616a  mov     rdi, [rdi]
0x18007616d  mov     rcx, [rbx+8]; hFindFile
0x180076171  call    cs:__imp_FindClose
0x180076178  nop     dword ptr [rax+rax+00h]
0x18007617d  mov     rcx, rbx; hMem
0x180076180  call    cs:__imp_LocalFree
0x180076187  nop     dword ptr [rax+rax+00h]
0x18007618c  jmp     loc_18007608F
0x180076191  call    cs:__imp_GetLastError
0x180076198  nop     dword ptr [rax+rax+00h]
0x18007619d  lea     r9, aErrorDLeavingD; "Error %d leaving directory [%ws]\n"
0x1800761a4  mov     r8d, 207h
0x1800761aa  mov     esi, eax
0x1800761ac  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800761b3  mov     rax, [rdi+10h]
0x1800761b7  mov     ecx, 5
0x1800761bc  mov     [rsp+38h+var_10], rax
0x1800761c1  mov     dword ptr [rsp+38h+var_18], esi
0x1800761c5  call    dprintf
0x1800761ca  cmp     esi, 12h
0x1800761cd  jz      short loc_180076226
0x1800761cf  jmp     short loc_180076221
0x1800761d1  mov     rax, [rdi+10h]
0x1800761d5  lea     r9, aErrorDLeavingD; "Error %d leaving directory [%ws]\n"
0x1800761dc  mov     [rsp+38h+var_10], rax
0x1800761e1  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800761e8  mov     r8d, 21Bh
0x1800761ee  mov     dword ptr [rsp+38h+var_18], esi
0x1800761f2  mov     ecx, 5
0x1800761f7  call    dprintf
0x1800761fc  mov     rbx, rdi
0x1800761ff  mov     rdi, [rdi]
0x180076202  mov     rcx, [rbx+8]; hFindFile
0x180076206  call    cs:__imp_FindClose
0x18007620d  nop     dword ptr [rax+rax+00h]
0x180076212  mov     rcx, rbx; hMem
0x180076215  call    cs:__imp_LocalFree
0x18007621c  nop     dword ptr [rax+rax+00h]
0x180076221  test    rdi, rdi
0x180076224  jnz     short loc_1800761D1
0x180076226  mov     rbx, [rsp+38h+arg_0]
0x18007622b  mov     rax, rdi
0x18007622e  mov     rsi, [rsp+38h+arg_8]
0x180076233  add     rsp, 30h
0x180076237  pop     rdi
0x180076238  retn
```
