# CheckDir

- ea: `0x180075e18`
- end: `0x180076104`
- name: `CheckDir`
- size: `748`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180076980`

## callees

- `0x180075e18`
- `0x180077058`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180075e95`
- `KERNEL32!GetLastError` at `0x180075f57`
- `KERNEL32!GetLastError` at `0x180075fe1`
- `KERNEL32!GetLastError` at `0x18007606c`
- `KERNEL32!GetLastError` at `0x180075e95`
- `KERNEL32!GetLastError` at `0x180075f57`
- `KERNEL32!GetLastError` at `0x180075fe1`
- `KERNEL32!GetLastError` at `0x18007606c`
- `KERNEL32!FindFirstFileW` at `0x180075f42`
- `KERNEL32!FindFirstFileW` at `0x180075f42`
- `KERNEL32!FindNextFileW` at `0x180075fd1`
- `KERNEL32!FindNextFileW` at `0x180075fd1`
- `KERNEL32!FindClose` at `0x1800760be`
- `KERNEL32!FindClose` at `0x1800760be`
- `KERNEL32!LocalFree` at `0x1800760a7`
- `KERNEL32!LocalFree` at `0x1800760a7`
- `KERNEL32!LocalAlloc` at `0x180075efa`
- `KERNEL32!LocalAlloc` at `0x180075efa`
- `KERNEL32!SetCurrentDirectoryW` at `0x180075e85`
- `KERNEL32!SetCurrentDirectoryW` at `0x18007605c`
- `KERNEL32!SetCurrentDirectoryW` at `0x180075e85`
- `KERNEL32!SetCurrentDirectoryW` at `0x18007605c`
- `KERNEL32!lstrcmpW` at `0x180075e33`
- `KERNEL32!lstrcmpW` at `0x180075e51`
- `KERNEL32!lstrcmpW` at `0x180075f9f`
- `KERNEL32!lstrcmpW` at `0x180075fba`
- `KERNEL32!lstrcmpW` at `0x180075e33`
- `KERNEL32!lstrcmpW` at `0x180075e51`
- `KERNEL32!lstrcmpW` at `0x180075f9f`
- `KERNEL32!lstrcmpW` at `0x180075fba`

## string_xrefs

- `0x1800760cf`: `[%ws] is not a directory\n`
- `0x180075ffa`: `Error %d attempting to scan in [%ws]\n`

## pseudocode

```c
char *__fastcall CheckDir(LPCWSTR lpPathName, __int16 a2)
{
  char *v4; // rax
  char *v5; // rdi
  __int64 FirstFileW; // r15
  DWORD LastError; // r14d

  if ( !lstrcmpW(lpPathName, L".") || !lstrcmpW(lpPathName, L"..") || (a2 & 0x416) == 1046 || (a2 & 0x10) == 0 )
  {
    dprintf(
      5,
      (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
      387,
      (unsigned int)L"[%ws] is not a directory\n");
    return 0;
  }
  if ( SetCurrentDirectoryW(lpPathName) )
  {
    dprintf(
      5,
      (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
      400,
      (unsigned int)L"Entering [%ws]\n");
    v4 = (char *)LocalAlloc(0x40u, 0x268u);
    v5 = v4;
    if ( v4 )
    {
      FirstFileW = (__int64)FindFirstFileW(L"*", (LPWIN32_FIND_DATAW)(v4 + 24));
      if ( FirstFileW == -1 )
      {
        LastError = GetLastError();
        dprintf(
          5,
          (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
          416,
          (unsigned int)L"Error %d. FindFirstFile on [%ws]\n");
      }
      else
      {
        LastError = 0;
        while ( !lstrcmpW((LPCWSTR)v5 + 34, L".") || !lstrcmpW((LPCWSTR)v5 + 34, L"..") )
        {
          if ( !FindNextFileW((HANDLE)FirstFileW, (LPWIN32_FIND_DATAW)(v5 + 24)) )
          {
            LastError = GetLastError();
            if ( LastError != 18 )
              dprintf(
                5,
                (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
                430,
                (unsigned int)L"Error %d attempting to scan in [%ws]\n");
            break;
          }
        }
        *((_QWORD *)v5 + 1) = FirstFileW;
        *((_QWORD *)v5 + 2) = lpPathName;
      }
      if ( !LastError )
        return v5;
    }
    else
    {
      FirstFileW = -1;
      dprintf(
        5,
        (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
        407,
        (unsigned int)L"Not enough memory\n");
    }
    dprintf(
      5,
      (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
      443,
      (unsigned int)L"Error %d scanning dir [%ws]\n");
    if ( !SetCurrentDirectoryW(L"..") )
    {
      GetLastError();
      dprintf(
        5,
        (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
        446,
        (unsigned int)L"Error %d leaving dir [%ws]\n");
    }
    if ( v5 )
    {
      LocalFree(v5);
      v5 = 0;
    }
    if ( FirstFileW != -1 )
      FindClose((HANDLE)FirstFileW);
    return v5;
  }
  GetLastError();
  dprintf(
    5,
    (unsigned int)L"onecore\\base\\subsys\\sm\\sfc\\wrpdisable\\wrpdisable.c",
    396,
    (unsigned int)L"Error %d. Could not set current dir to [%ws]\n");
  return 0;
}

```

## disassembly

```asm
0x180075e18  push    rbx
0x180075e1a  push    rdi
0x180075e1b  push    r12
0x180075e1d  push    r13
0x180075e1f  push    r14
0x180075e21  push    r15
0x180075e23  sub     rsp, 38h
0x180075e27  mov     edi, edx
0x180075e29  mov     rbx, rcx
0x180075e2c  lea     rdx, asc_1800B0D58; "."
0x180075e33  call    cs:__imp_lstrcmpW
0x180075e3a  nop     dword ptr [rax+rax+00h]
0x180075e3f  test    eax, eax
0x180075e41  jz      loc_1800760CF
0x180075e47  lea     rdx, PathName; ".."
0x180075e4e  mov     rcx, rbx; lpString1
0x180075e51  call    cs:__imp_lstrcmpW
0x180075e58  nop     dword ptr [rax+rax+00h]
0x180075e5d  test    eax, eax
0x180075e5f  jz      loc_1800760CF
0x180075e65  mov     ecx, 416h
0x180075e6a  mov     eax, edi
0x180075e6c  and     eax, ecx
0x180075e6e  cmp     eax, ecx
0x180075e70  setnz   cl
0x180075e73  test    dil, 10h
0x180075e77  setnz   al
0x180075e7a  test    al, cl
0x180075e7c  jz      loc_1800760CF
0x180075e82  mov     rcx, rbx; lpPathName
0x180075e85  call    cs:__imp_SetCurrentDirectoryW
0x180075e8c  nop     dword ptr [rax+rax+00h]
0x180075e91  test    eax, eax
0x180075e93  jnz     short loc_180075ECD
0x180075e95  call    cs:__imp_GetLastError
0x180075e9c  nop     dword ptr [rax+rax+00h]
0x180075ea1  lea     r9, aErrorDCouldNot; "Error %d. Could not set current dir to "...
0x180075ea8  mov     [rsp+68h+var_40], rbx
0x180075ead  mov     r8d, 18Ch
0x180075eb3  mov     dword ptr [rsp+68h+var_48], eax
0x180075eb7  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075ebe  mov     ecx, 5
0x180075ec3  call    dprintf
0x180075ec8  jmp     loc_1800760F2
0x180075ecd  lea     r9, aEnteringWs; "Entering [%ws]\n"
0x180075ed4  mov     [rsp+68h+var_48], rbx
0x180075ed9  mov     r8d, 190h
0x180075edf  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075ee6  mov     ecx, 5
0x180075eeb  call    dprintf
0x180075ef0  mov     edx, 268h; uBytes
0x180075ef5  mov     ecx, 40h ; '@'; uFlags
0x180075efa  call    cs:__imp_LocalAlloc
0x180075f01  nop     dword ptr [rax+rax+00h]
0x180075f06  mov     rdi, rax
0x180075f09  test    rax, rax
0x180075f0c  jnz     short loc_180075F37
0x180075f0e  or      r15, 0FFFFFFFFFFFFFFFFh
0x180075f12  lea     r9, aNotEnoughMemor; "Not enough memory\n"
0x180075f19  mov     r8d, 197h
0x180075f1f  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075f26  lea     ecx, [rax+5]
0x180075f29  lea     r14d, [rax+8]
0x180075f2d  call    dprintf
0x180075f32  jmp     loc_18007602D
0x180075f37  lea     rdx, [rax+18h]; lpFindFileData
0x180075f3b  lea     rcx, asc_1800B0FC8; "*"
0x180075f42  call    cs:__imp_FindFirstFileW
0x180075f49  nop     dword ptr [rax+rax+00h]
0x180075f4e  mov     r15, rax
0x180075f51  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180075f55  jnz     short loc_180075F91
0x180075f57  call    cs:__imp_GetLastError
0x180075f5e  nop     dword ptr [rax+rax+00h]
0x180075f63  lea     r9, aErrorDFindfirs; "Error %d. FindFirstFile on [%ws]\n"
0x180075f6a  mov     [rsp+68h+var_40], rbx
0x180075f6f  mov     r8d, 1A0h
0x180075f75  mov     dword ptr [rsp+68h+var_48], eax
0x180075f79  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075f80  mov     r14d, eax
0x180075f83  lea     ecx, [r15+6]
0x180075f87  call    dprintf
0x180075f8c  jmp     loc_180076024
0x180075f91  xor     r14d, r14d
0x180075f94  lea     rdx, asc_1800B0D58; "."
0x180075f9b  lea     rcx, [rdi+44h]; lpString1
0x180075f9f  call    cs:__imp_lstrcmpW
0x180075fa6  nop     dword ptr [rax+rax+00h]
0x180075fab  test    eax, eax
0x180075fad  jz      short loc_180075FCA
0x180075faf  lea     rdx, PathName; ".."
0x180075fb6  lea     rcx, [rdi+44h]; lpString1
0x180075fba  call    cs:__imp_lstrcmpW
0x180075fc1  nop     dword ptr [rax+rax+00h]
0x180075fc6  test    eax, eax
0x180075fc8  jnz     short loc_18007601C
0x180075fca  lea     rdx, [rdi+18h]; lpFindFileData
0x180075fce  mov     rcx, r15; hFindFile
0x180075fd1  call    cs:__imp_FindNextFileW
0x180075fd8  nop     dword ptr [rax+rax+00h]
0x180075fdd  test    eax, eax
0x180075fdf  jnz     short loc_180075F94
0x180075fe1  call    cs:__imp_GetLastError
0x180075fe8  nop     dword ptr [rax+rax+00h]
0x180075fed  mov     r14d, eax
0x180075ff0  cmp     eax, 12h
0x180075ff3  jz      short loc_18007601C
0x180075ff5  mov     [rsp+68h+var_40], rbx
0x180075ffa  lea     r9, aErrorDAttempti; "Error %d attempting to scan in [%ws]\n"
0x180076001  mov     r8d, 1AEh
0x180076007  mov     dword ptr [rsp+68h+var_48], eax
0x18007600b  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180076012  mov     ecx, 5
0x180076017  call    dprintf
0x18007601c  mov     [rdi+8], r15
0x180076020  mov     [rdi+10h], rbx
0x180076024  test    r14d, r14d
0x180076027  jz      loc_1800760CA
0x18007602d  mov     [rsp+68h+var_40], rbx
0x180076032  lea     r9, aErrorDScanning; "Error %d scanning dir [%ws]\n"
0x180076039  mov     r8d, 1BBh
0x18007603f  mov     dword ptr [rsp+68h+var_48], r14d
0x180076044  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x18007604b  mov     ecx, 5
0x180076050  call    dprintf
0x180076055  lea     rcx, PathName; ".."
0x18007605c  call    cs:__imp_SetCurrentDirectoryW
0x180076063  nop     dword ptr [rax+rax+00h]
0x180076068  test    eax, eax
0x18007606a  jnz     short loc_18007609F
0x18007606c  call    cs:__imp_GetLastError
0x180076073  nop     dword ptr [rax+rax+00h]
0x180076078  lea     r9, aErrorDLeavingD_0; "Error %d leaving dir [%ws]\n"
0x18007607f  mov     [rsp+68h+var_40], rbx
0x180076084  mov     r8d, 1BEh
0x18007608a  mov     dword ptr [rsp+68h+var_48], eax
0x18007608e  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180076095  mov     ecx, 5
0x18007609a  call    dprintf
0x18007609f  test    rdi, rdi
0x1800760a2  jz      short loc_1800760B5
0x1800760a4  mov     rcx, rdi; hMem
0x1800760a7  call    cs:__imp_LocalFree
0x1800760ae  nop     dword ptr [rax+rax+00h]
0x1800760b3  xor     edi, edi
0x1800760b5  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x1800760b9  jz      short loc_1800760CA
0x1800760bb  mov     rcx, r15; hFindFile
0x1800760be  call    cs:__imp_FindClose
0x1800760c5  nop     dword ptr [rax+rax+00h]
0x1800760ca  mov     rax, rdi
0x1800760cd  jmp     short loc_1800760F4
0x1800760cf  lea     r9, aWsIsNotADirect; "[%ws] is not a directory\n"
0x1800760d6  mov     [rsp+68h+var_48], rbx
0x1800760db  mov     r8d, 183h
0x1800760e1  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x1800760e8  mov     ecx, 5
0x1800760ed  call    dprintf
0x1800760f2  xor     eax, eax
0x1800760f4  add     rsp, 38h
0x1800760f8  pop     r15
0x1800760fa  pop     r14
0x1800760fc  pop     r13
0x1800760fe  pop     r12
0x180076100  pop     rdi
0x180076101  pop     rbx
0x180076102  retn
```
