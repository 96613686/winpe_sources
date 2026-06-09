# PathCreateDirectoryRecursive

- ea: `0x1800953e4`
- end: `0x1800954f8`
- name: `PathCreateDirectoryRecursive`
- size: `276`
- prototype: `__int64 __fastcall(LPCWSTR lpPathName)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x180095374`
- `0x1800953e4`

## callees

- `0x1800952d0`
- `0x1800953e4`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009543a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800954cf`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18009543a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800954cf`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180095429`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800954c1`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180095429`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x1800954c1`

## pseudocode

```c
signed int __fastcall PathCreateDirectoryRecursive(LPCWSTR lpPathName, int a2, unsigned int a3)
{
  signed int result; // eax
  int v6; // r9d
  __int64 v7; // rdi
  int v8; // [rsp+50h] [rbp+8h] BYREF
  unsigned int v9; // [rsp+68h] [rbp+20h] BYREF

  v9 = 0;
  v8 = 0;
  if ( !lpPathName || !a2 || a3 >= 0x80 )
    return -2147024809;
  if ( CreateDirectoryW(lpPathName, 0) )
    return 0;
  result = GetLastError();
  if ( result == 183 )
    return 0;
  if ( result != 3 )
  {
LABEL_8:
    if ( result > 0 )
      return (unsigned __int16)result | 0x80070000;
    return result;
  }
  result = StringFindChar((_DWORD)lpPathName, 92, a2, v6, (__int64)&v9, (__int64)&v8);
  if ( result < 0 )
    return result;
  if ( !v8 )
    return -2147024893;
  v7 = v9;
  lpPathName[v9] = 0;
  result = PathCreateDirectoryRecursive(lpPathName);
  if ( result >= 0 )
  {
    lpPathName[v7] = 92;
    if ( !CreateDirectoryW(lpPathName, 0) )
    {
      result = GetLastError();
      if ( result != 183 )
        goto LABEL_8;
    }
    return 0;
  }
  return result;
}

```

## disassembly

```asm
0x1800953e4  mov     [rsp+arg_8], rbx
0x1800953e9  push    rsi
0x1800953ea  push    rdi
0x1800953eb  push    r15
0x1800953ed  sub     rsp, 30h
0x1800953f1  mov     [rsp+48h+arg_18], 0
0x1800953f9  mov     esi, r8d
0x1800953fc  mov     [rsp+48h+arg_0], 0
0x180095404  mov     edi, edx
0x180095406  mov     rbx, rcx
0x180095409  test    rcx, rcx
0x18009540c  jz      loc_1800954E5
0x180095412  test    edx, edx
0x180095414  jz      loc_1800954E5
0x18009541a  cmp     r8d, 80h
0x180095421  jnb     loc_1800954E5
0x180095427  xor     edx, edx; lpSecurityAttributes
0x180095429  call    cs:__imp_CreateDirectoryW
0x18009542f  test    eax, eax
0x180095431  jz      short loc_18009543A
0x180095433  xor     eax, eax
0x180095435  jmp     loc_1800954EA
0x18009543a  call    cs:__imp_GetLastError
0x180095440  cmp     eax, 0B7h
0x180095445  jz      short loc_180095433
0x180095447  cmp     eax, 3
0x18009544a  jz      short loc_180095461
0x18009544c  test    eax, eax
0x18009544e  jle     loc_1800954EA
0x180095454  movzx   eax, ax
0x180095457  or      eax, 80070000h
0x18009545c  jmp     loc_1800954EA
0x180095461  lea     rax, [rsp+48h+arg_0]
0x180095466  mov     r15d, 5Ch ; '\'
0x18009546c  mov     [rsp+48h+var_20], rax
0x180095471  mov     edx, r15d
0x180095474  lea     rax, [rsp+48h+arg_18]
0x180095479  mov     r8d, edi
0x18009547c  mov     rcx, rbx
0x18009547f  mov     [rsp+48h+var_28], rax
0x180095484  call    StringFindChar
0x180095489  test    eax, eax
0x18009548b  js      short loc_1800954EA
0x18009548d  cmp     [rsp+48h+arg_0], 0
0x180095492  jnz     short loc_18009549B
0x180095494  mov     eax, 80070003h
0x180095499  jmp     short loc_1800954EA
0x18009549b  mov     edx, [rsp+48h+arg_18]
0x18009549f  lea     r8d, [rsi+1]
0x1800954a3  xor     eax, eax
0x1800954a5  mov     rcx, rbx; lpPathName
0x1800954a8  mov     edi, edx
0x1800954aa  mov     [rbx+rdx*2], ax
0x1800954ae  call    PathCreateDirectoryRecursive
0x1800954b3  test    eax, eax
0x1800954b5  js      short loc_1800954EA
0x1800954b7  xor     edx, edx; lpSecurityAttributes
0x1800954b9  mov     [rbx+rdi*2], r15w
0x1800954be  mov     rcx, rbx; lpPathName
0x1800954c1  call    cs:__imp_CreateDirectoryW
0x1800954c7  test    eax, eax
0x1800954c9  jnz     loc_180095433
0x1800954cf  call    cs:__imp_GetLastError
0x1800954d5  cmp     eax, 0B7h
0x1800954da  jz      loc_180095433
0x1800954e0  jmp     loc_18009544C
0x1800954e5  mov     eax, 80070057h
0x1800954ea  mov     rbx, [rsp+48h+arg_8]
0x1800954ef  add     rsp, 30h
0x1800954f3  pop     r15
0x1800954f5  pop     rdi
0x1800954f6  pop     rsi
0x1800954f7  retn
```
