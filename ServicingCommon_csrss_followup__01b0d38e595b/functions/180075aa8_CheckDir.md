# CheckDir

- ea: `0x180075aa8`
- end: `0x180075d94`
- name: `CheckDir`
- size: `748`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x180076610`

## callees

- `0x180075aa8`
- `0x180076ce8`

## import_xrefs

- `KERNEL32!GetLastError` at `0x180075b25`
- `KERNEL32!GetLastError` at `0x180075be7`
- `KERNEL32!GetLastError` at `0x180075c71`
- `KERNEL32!GetLastError` at `0x180075cfc`
- `KERNEL32!GetLastError` at `0x180075b25`
- `KERNEL32!GetLastError` at `0x180075be7`
- `KERNEL32!GetLastError` at `0x180075c71`
- `KERNEL32!GetLastError` at `0x180075cfc`
- `KERNEL32!FindFirstFileW` at `0x180075bd2`
- `KERNEL32!FindFirstFileW` at `0x180075bd2`
- `KERNEL32!FindNextFileW` at `0x180075c61`
- `KERNEL32!FindNextFileW` at `0x180075c61`
- `KERNEL32!FindClose` at `0x180075d4e`
- `KERNEL32!FindClose` at `0x180075d4e`
- `KERNEL32!LocalFree` at `0x180075d37`
- `KERNEL32!LocalFree` at `0x180075d37`
- `KERNEL32!LocalAlloc` at `0x180075b8a`
- `KERNEL32!LocalAlloc` at `0x180075b8a`
- `KERNEL32!SetCurrentDirectoryW` at `0x180075b15`
- `KERNEL32!SetCurrentDirectoryW` at `0x180075cec`
- `KERNEL32!SetCurrentDirectoryW` at `0x180075b15`
- `KERNEL32!SetCurrentDirectoryW` at `0x180075cec`
- `KERNEL32!lstrcmpW` at `0x180075ac3`
- `KERNEL32!lstrcmpW` at `0x180075ae1`
- `KERNEL32!lstrcmpW` at `0x180075c2f`
- `KERNEL32!lstrcmpW` at `0x180075c4a`
- `KERNEL32!lstrcmpW` at `0x180075ac3`
- `KERNEL32!lstrcmpW` at `0x180075ae1`
- `KERNEL32!lstrcmpW` at `0x180075c2f`
- `KERNEL32!lstrcmpW` at `0x180075c4a`

## string_xrefs

- `0x180075d5f`: `[%ws] is not a directory\n`
- `0x180075c8a`: `Error %d attempting to scan in [%ws]\n`

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
0x180075aa8  push    rbx
0x180075aaa  push    rdi
0x180075aab  push    r12
0x180075aad  push    r13
0x180075aaf  push    r14
0x180075ab1  push    r15
0x180075ab3  sub     rsp, 38h
0x180075ab7  mov     edi, edx
0x180075ab9  mov     rbx, rcx
0x180075abc  lea     rdx, asc_1800B07A0; "."
0x180075ac3  call    cs:__imp_lstrcmpW
0x180075aca  nop     dword ptr [rax+rax+00h]
0x180075acf  test    eax, eax
0x180075ad1  jz      loc_180075D5F
0x180075ad7  lea     rdx, PathName; ".."
0x180075ade  mov     rcx, rbx; lpString1
0x180075ae1  call    cs:__imp_lstrcmpW
0x180075ae8  nop     dword ptr [rax+rax+00h]
0x180075aed  test    eax, eax
0x180075aef  jz      loc_180075D5F
0x180075af5  mov     ecx, 416h
0x180075afa  mov     eax, edi
0x180075afc  and     eax, ecx
0x180075afe  cmp     eax, ecx
0x180075b00  setnz   cl
0x180075b03  test    dil, 10h
0x180075b07  setnz   al
0x180075b0a  test    al, cl
0x180075b0c  jz      loc_180075D5F
0x180075b12  mov     rcx, rbx; lpPathName
0x180075b15  call    cs:__imp_SetCurrentDirectoryW
0x180075b1c  nop     dword ptr [rax+rax+00h]
0x180075b21  test    eax, eax
0x180075b23  jnz     short loc_180075B5D
0x180075b25  call    cs:__imp_GetLastError
0x180075b2c  nop     dword ptr [rax+rax+00h]
0x180075b31  lea     r9, aErrorDCouldNot; "Error %d. Could not set current dir to "...
0x180075b38  mov     [rsp+68h+var_40], rbx
0x180075b3d  mov     r8d, 18Ch
0x180075b43  mov     dword ptr [rsp+68h+var_48], eax
0x180075b47  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075b4e  mov     ecx, 5
0x180075b53  call    dprintf
0x180075b58  jmp     loc_180075D82
0x180075b5d  lea     r9, aEnteringWs; "Entering [%ws]\n"
0x180075b64  mov     [rsp+68h+var_48], rbx
0x180075b69  mov     r8d, 190h
0x180075b6f  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075b76  mov     ecx, 5
0x180075b7b  call    dprintf
0x180075b80  mov     edx, 268h; uBytes
0x180075b85  mov     ecx, 40h ; '@'; uFlags
0x180075b8a  call    cs:__imp_LocalAlloc
0x180075b91  nop     dword ptr [rax+rax+00h]
0x180075b96  mov     rdi, rax
0x180075b99  test    rax, rax
0x180075b9c  jnz     short loc_180075BC7
0x180075b9e  or      r15, 0FFFFFFFFFFFFFFFFh
0x180075ba2  lea     r9, aNotEnoughMemor; "Not enough memory\n"
0x180075ba9  mov     r8d, 197h
0x180075baf  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075bb6  lea     ecx, [rax+5]
0x180075bb9  lea     r14d, [rax+8]
0x180075bbd  call    dprintf
0x180075bc2  jmp     loc_180075CBD
0x180075bc7  lea     rdx, [rax+18h]; lpFindFileData
0x180075bcb  lea     rcx, asc_1800B0A10; "*"
0x180075bd2  call    cs:__imp_FindFirstFileW
0x180075bd9  nop     dword ptr [rax+rax+00h]
0x180075bde  mov     r15, rax
0x180075be1  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180075be5  jnz     short loc_180075C21
0x180075be7  call    cs:__imp_GetLastError
0x180075bee  nop     dword ptr [rax+rax+00h]
0x180075bf3  lea     r9, aErrorDFindfirs; "Error %d. FindFirstFile on [%ws]\n"
0x180075bfa  mov     [rsp+68h+var_40], rbx
0x180075bff  mov     r8d, 1A0h
0x180075c05  mov     dword ptr [rsp+68h+var_48], eax
0x180075c09  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075c10  mov     r14d, eax
0x180075c13  lea     ecx, [r15+6]
0x180075c17  call    dprintf
0x180075c1c  jmp     loc_180075CB4
0x180075c21  xor     r14d, r14d
0x180075c24  lea     rdx, asc_1800B07A0; "."
0x180075c2b  lea     rcx, [rdi+44h]; lpString1
0x180075c2f  call    cs:__imp_lstrcmpW
0x180075c36  nop     dword ptr [rax+rax+00h]
0x180075c3b  test    eax, eax
0x180075c3d  jz      short loc_180075C5A
0x180075c3f  lea     rdx, PathName; ".."
0x180075c46  lea     rcx, [rdi+44h]; lpString1
0x180075c4a  call    cs:__imp_lstrcmpW
0x180075c51  nop     dword ptr [rax+rax+00h]
0x180075c56  test    eax, eax
0x180075c58  jnz     short loc_180075CAC
0x180075c5a  lea     rdx, [rdi+18h]; lpFindFileData
0x180075c5e  mov     rcx, r15; hFindFile
0x180075c61  call    cs:__imp_FindNextFileW
0x180075c68  nop     dword ptr [rax+rax+00h]
0x180075c6d  test    eax, eax
0x180075c6f  jnz     short loc_180075C24
0x180075c71  call    cs:__imp_GetLastError
0x180075c78  nop     dword ptr [rax+rax+00h]
0x180075c7d  mov     r14d, eax
0x180075c80  cmp     eax, 12h
0x180075c83  jz      short loc_180075CAC
0x180075c85  mov     [rsp+68h+var_40], rbx
0x180075c8a  lea     r9, aErrorDAttempti; "Error %d attempting to scan in [%ws]\n"
0x180075c91  mov     r8d, 1AEh
0x180075c97  mov     dword ptr [rsp+68h+var_48], eax
0x180075c9b  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075ca2  mov     ecx, 5
0x180075ca7  call    dprintf
0x180075cac  mov     [rdi+8], r15
0x180075cb0  mov     [rdi+10h], rbx
0x180075cb4  test    r14d, r14d
0x180075cb7  jz      loc_180075D5A
0x180075cbd  mov     [rsp+68h+var_40], rbx
0x180075cc2  lea     r9, aErrorDScanning; "Error %d scanning dir [%ws]\n"
0x180075cc9  mov     r8d, 1BBh
0x180075ccf  mov     dword ptr [rsp+68h+var_48], r14d
0x180075cd4  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075cdb  mov     ecx, 5
0x180075ce0  call    dprintf
0x180075ce5  lea     rcx, PathName; ".."
0x180075cec  call    cs:__imp_SetCurrentDirectoryW
0x180075cf3  nop     dword ptr [rax+rax+00h]
0x180075cf8  test    eax, eax
0x180075cfa  jnz     short loc_180075D2F
0x180075cfc  call    cs:__imp_GetLastError
0x180075d03  nop     dword ptr [rax+rax+00h]
0x180075d08  lea     r9, aErrorDLeavingD_0; "Error %d leaving dir [%ws]\n"
0x180075d0f  mov     [rsp+68h+var_40], rbx
0x180075d14  mov     r8d, 1BEh
0x180075d1a  mov     dword ptr [rsp+68h+var_48], eax
0x180075d1e  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075d25  mov     ecx, 5
0x180075d2a  call    dprintf
0x180075d2f  test    rdi, rdi
0x180075d32  jz      short loc_180075D45
0x180075d34  mov     rcx, rdi; hMem
0x180075d37  call    cs:__imp_LocalFree
0x180075d3e  nop     dword ptr [rax+rax+00h]
0x180075d43  xor     edi, edi
0x180075d45  cmp     r15, 0FFFFFFFFFFFFFFFFh
0x180075d49  jz      short loc_180075D5A
0x180075d4b  mov     rcx, r15; hFindFile
0x180075d4e  call    cs:__imp_FindClose
0x180075d55  nop     dword ptr [rax+rax+00h]
0x180075d5a  mov     rax, rdi
0x180075d5d  jmp     short loc_180075D84
0x180075d5f  lea     r9, aWsIsNotADirect; "[%ws] is not a directory\n"
0x180075d66  mov     [rsp+68h+var_48], rbx
0x180075d6b  mov     r8d, 183h
0x180075d71  lea     rdx, aOnecoreBaseSub; "onecore\\base\\subsys\\sm\\sfc\\wrpdisa"...
0x180075d78  mov     ecx, 5
0x180075d7d  call    dprintf
0x180075d82  xor     eax, eax
0x180075d84  add     rsp, 38h
0x180075d88  pop     r15
0x180075d8a  pop     r14
0x180075d8c  pop     r13
0x180075d8e  pop     r12
0x180075d90  pop     rdi
0x180075d91  pop     rbx
0x180075d92  retn
```
