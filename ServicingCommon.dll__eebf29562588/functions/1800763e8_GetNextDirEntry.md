# GetNextDirEntry

- ea: `0x1800763e8`
- end: `0x1800765aa`
- name: `GetNextDirEntry`
- size: `450`
- prototype: `__int64 __fastcall(HLOCAL hMem)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180076980`

## callees

- `0x1800763e8`
- `0x180077058`

## import_xrefs

- `KERNEL32!GetLastError` at `0x18007645b`
- `KERNEL32!GetLastError` at `0x180076501`
- `KERNEL32!GetLastError` at `0x18007645b`
- `KERNEL32!GetLastError` at `0x180076501`
- `KERNEL32!FindNextFileW` at `0x180076410`
- `KERNEL32!FindNextFileW` at `0x180076410`
- `KERNEL32!FindClose` at `0x1800764e1`
- `KERNEL32!FindClose` at `0x180076576`
- `KERNEL32!FindClose` at `0x1800764e1`
- `KERNEL32!FindClose` at `0x180076576`
- `KERNEL32!LocalFree` at `0x1800764f0`
- `KERNEL32!LocalFree` at `0x180076585`
- `KERNEL32!LocalFree` at `0x1800764f0`
- `KERNEL32!LocalFree` at `0x180076585`
- `KERNEL32!SetCurrentDirectoryW` at `0x1800764a0`
- `KERNEL32!SetCurrentDirectoryW` at `0x1800764a0`
- `KERNEL32!lstrcmpW` at `0x18007642b`
- `KERNEL32!lstrcmpW` at `0x180076446`
- `KERNEL32!lstrcmpW` at `0x18007642b`
- `KERNEL32!lstrcmpW` at `0x180076446`

## string_xrefs

- `0x18007650d`: `Error %d leaving directory [%ws]\n`
- `0x180076545`: `Error %d leaving directory [%ws]\n`

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
0x1800763e8  mov     [rsp+arg_0], rbx
0x1800763ed  mov     [rsp+arg_8], rsi
0x1800763f2  push    rdi
0x1800763f3  sub     rsp, 30h
0x1800763f7  mov     rdi, rcx
0x1800763fa  mov     esi, 12h
0x1800763ff  test    rdi, rdi
0x180076402  jz      loc_18007653A
0x180076408  mov     rcx, [rdi+8]; hFindFile
0x18007640c  lea     rdx, [rdi+18h]; lpFindFileData
0x180076410  call    cs:__imp_FindNextFileW
0x180076417  nop     dword ptr [rax+rax+00h]
0x18007641c  test    eax, eax
0x18007641e  jz      short loc_18007645B
0x180076420  lea     rdx, asc_1800B0D58; "."
0x180076427  lea     rcx, [rdi+44h]; lpString1
0x18007642b  call    cs:__imp_lstrcmpW
0x180076432  nop     dword ptr [rax+rax+00h]
0x180076437  test    eax, eax
0x180076439  jz      short loc_180076408
0x18007643b  lea     rdx, PathName; ".."
0x180076442  lea     rcx, [rdi+44h]; lpString1
0x180076446  call    cs:__imp_lstrcmpW
0x18007644d  nop     dword ptr [rax+rax+00h]
0x180076452  test    eax, eax
0x180076454  jz      short loc_180076408
0x180076456  jmp     loc_180076596
0x18007645b  call    cs:__imp_GetLastError
0x180076462  nop     dword ptr [rax+rax+00h]
0x180076467  mov     esi, eax
0x180076469  cmp     eax, 12h
0x18007646c  jz      short loc_180076499
0x18007646e  mov     rax, [rdi+10h]
0x180076472  lea     r9, aErrorDWhileSca; "Error %d while scanning [%ws]\n"
0x180076479  mov     [rsp+38h+var_10], rax
0x18007647e  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180076485  mov     r8d, 201h
0x18007648b  mov     dword ptr [rsp+38h+var_18], esi
0x18007648f  mov     ecx, 5
0x180076494  call    dprintf
0x180076499  lea     rcx, PathName; ".."
0x1800764a0  call    cs:__imp_SetCurrentDirectoryW
0x1800764a7  nop     dword ptr [rax+rax+00h]
0x1800764ac  test    eax, eax
0x1800764ae  jz      short loc_180076501
0x1800764b0  mov     rax, [rdi+10h]
0x1800764b4  lea     r9, aLeavingWs; "Leaving  [%ws]\n"
0x1800764bb  mov     r8d, 20Bh
0x1800764c1  mov     [rsp+38h+var_18], rax
0x1800764c6  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800764cd  mov     ecx, 5
0x1800764d2  call    dprintf
0x1800764d7  mov     rbx, rdi
0x1800764da  mov     rdi, [rdi]
0x1800764dd  mov     rcx, [rbx+8]; hFindFile
0x1800764e1  call    cs:__imp_FindClose
0x1800764e8  nop     dword ptr [rax+rax+00h]
0x1800764ed  mov     rcx, rbx; hMem
0x1800764f0  call    cs:__imp_LocalFree
0x1800764f7  nop     dword ptr [rax+rax+00h]
0x1800764fc  jmp     loc_1800763FF
0x180076501  call    cs:__imp_GetLastError
0x180076508  nop     dword ptr [rax+rax+00h]
0x18007650d  lea     r9, aErrorDLeavingD; "Error %d leaving directory [%ws]\n"
0x180076514  mov     r8d, 207h
0x18007651a  mov     esi, eax
0x18007651c  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180076523  mov     rax, [rdi+10h]
0x180076527  mov     ecx, 5
0x18007652c  mov     [rsp+38h+var_10], rax
0x180076531  mov     dword ptr [rsp+38h+var_18], esi
0x180076535  call    dprintf
0x18007653a  cmp     esi, 12h
0x18007653d  jz      short loc_180076596
0x18007653f  jmp     short loc_180076591
0x180076541  mov     rax, [rdi+10h]
0x180076545  lea     r9, aErrorDLeavingD; "Error %d leaving directory [%ws]\n"
0x18007654c  mov     [rsp+38h+var_10], rax
0x180076551  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180076558  mov     r8d, 21Bh
0x18007655e  mov     dword ptr [rsp+38h+var_18], esi
0x180076562  mov     ecx, 5
0x180076567  call    dprintf
0x18007656c  mov     rbx, rdi
0x18007656f  mov     rdi, [rdi]
0x180076572  mov     rcx, [rbx+8]; hFindFile
0x180076576  call    cs:__imp_FindClose
0x18007657d  nop     dword ptr [rax+rax+00h]
0x180076582  mov     rcx, rbx; hMem
0x180076585  call    cs:__imp_LocalFree
0x18007658c  nop     dword ptr [rax+rax+00h]
0x180076591  test    rdi, rdi
0x180076594  jnz     short loc_180076541
0x180076596  mov     rbx, [rsp+38h+arg_0]
0x18007659b  mov     rax, rdi
0x18007659e  mov     rsi, [rsp+38h+arg_8]
0x1800765a3  add     rsp, 30h
0x1800765a7  pop     rdi
0x1800765a8  retn
```
