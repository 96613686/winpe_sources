# CompareXmlTextA(char const *,_WS_XML_TEXT const *)

- ea: `0x18001632c`
- end: `0x180016458`
- name: `?CompareXmlTextA@@YAHPEBDPEBU_WS_XML_TEXT@@@Z`
- size: `300`
- prototype: `__int64 __fastcall(PCNZCH lpString1, const struct _WS_XML_TEXT *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, broker_com_uri`

## callers

- `0x180006150`

## callees

- `0x18001632c`
- `0x180018625`
- `0x180018640`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800163a3`
- `api-ms-win-core-string-l1-1-0!WideCharToMultiByte` at `0x1800163a3`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800163b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800163f8`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800163b4`
- `api-ms-win-core-string-obsolete-l1-1-0!lstrlenA` at `0x1800163f8`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800163d8`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180016417`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x1800163d8`
- `api-ms-win-core-localization-obsolete-l1-2-0!CompareStringA` at `0x180016417`

## pseudocode

```c
__int64 __fastcall CompareXmlTextA(PCNZCH lpString1, const struct _WS_XML_TEXT *a2)
{
  unsigned int v4; // esi
  int v5; // ebx
  int v6; // eax
  WS_XML_TEXT_TYPE textType; // ebx
  const CHAR *v8; // rdi
  int v9; // eax
  CHAR MultiByteStr[256]; // [rsp+40h] [rbp-128h] BYREF

  v4 = 0;
  memset_0(MultiByteStr, 0, sizeof(MultiByteStr));
  if ( a2->textType == WS_XML_TEXT_TYPE_UTF8 )
  {
    textType = a2[2].textType;
    v8 = *(const CHAR **)&a2[4].textType;
    v9 = lstrlenA(lpString1);
    return CompareStringA(0, 0, lpString1, v9, v8, textType) == 2;
  }
  else if ( a2->textType == WS_XML_TEXT_TYPE_UTF16 )
  {
    v5 = WideCharToMultiByte(
           0xFDE9u,
           0,
           *(LPCWCH *)&a2[2].textType,
           (unsigned int)a2[4].textType >> 1,
           MultiByteStr,
           256,
           0,
           0);
    v6 = lstrlenA(lpString1);
    return CompareStringA(0, 0, lpString1, v6, MultiByteStr, v5) == 2;
  }
  return v4;
}

```

## disassembly

```asm
0x18001632c  mov     [rsp+arg_10], rbx
0x180016331  push    rbp
0x180016332  push    rsi
0x180016333  push    rdi
0x180016334  sub     rsp, 150h
0x18001633b  mov     rax, cs:__security_cookie
0x180016342  xor     rax, rsp
0x180016345  mov     [rsp+168h+var_28], rax
0x18001634d  mov     rdi, rdx
0x180016350  mov     rbp, rcx
0x180016353  mov     ebx, 100h
0x180016358  lea     rcx, [rsp+168h+MultiByteStr]; void *
0x18001635d  mov     r8d, ebx; Size
0x180016360  xor     edx, edx; Val
0x180016362  xor     esi, esi
0x180016364  call    memset_0
0x180016369  mov     ecx, [rdi]
0x18001636b  sub     ecx, 1
0x18001636e  jz      short loc_1800163EE
0x180016370  cmp     ecx, 1
0x180016373  jnz     loc_180016432
0x180016379  mov     r9d, [rdi+10h]
0x18001637d  lea     rax, [rsp+168h+MultiByteStr]
0x180016382  mov     r8, [rdi+8]; lpWideCharStr
0x180016386  xor     edx, edx; dwFlags
0x180016388  mov     [rsp+168h+lpUsedDefaultChar], rsi; lpUsedDefaultChar
0x18001638d  mov     ecx, 0FDE9h; CodePage
0x180016392  mov     [rsp+168h+lpDefaultChar], rsi; lpDefaultChar
0x180016397  shr     r9d, 1; cchWideChar
0x18001639a  mov     [rsp+168h+cbMultiByte], ebx; cbMultiByte
0x18001639e  mov     [rsp+168h+lpMultiByteStr], rax; lpMultiByteStr
0x1800163a3  call    cs:__imp_WideCharToMultiByte
0x1800163aa  nop     dword ptr [rax+rax+00h]
0x1800163af  mov     rcx, rbp; lpString
0x1800163b2  mov     ebx, eax
0x1800163b4  call    cs:__imp_lstrlenA
0x1800163bb  nop     dword ptr [rax+rax+00h]
0x1800163c0  mov     [rsp+168h+cbMultiByte], ebx; cchCount2
0x1800163c4  mov     r8, rbp; lpString1
0x1800163c7  mov     r9d, eax; cchCount1
0x1800163ca  xor     edx, edx; dwCmpFlags
0x1800163cc  lea     rax, [rsp+168h+MultiByteStr]
0x1800163d1  xor     ecx, ecx; Locale
0x1800163d3  mov     [rsp+168h+lpMultiByteStr], rax; lpString2
0x1800163d8  call    cs:__imp_CompareStringA
0x1800163df  nop     dword ptr [rax+rax+00h]
0x1800163e4  cmp     eax, 2
0x1800163e7  jnz     short loc_180016432
0x1800163e9  lea     esi, [rax-1]
0x1800163ec  jmp     short loc_180016432
0x1800163ee  mov     ebx, [rdi+8]
0x1800163f1  mov     rcx, rbp; lpString
0x1800163f4  mov     rdi, [rdi+10h]
0x1800163f8  call    cs:__imp_lstrlenA
0x1800163ff  nop     dword ptr [rax+rax+00h]
0x180016404  mov     [rsp+168h+cbMultiByte], ebx; cchCount2
0x180016408  mov     r8, rbp; lpString1
0x18001640b  mov     r9d, eax; cchCount1
0x18001640e  mov     [rsp+168h+lpMultiByteStr], rdi; lpString2
0x180016413  xor     edx, edx; dwCmpFlags
0x180016415  xor     ecx, ecx; Locale
0x180016417  call    cs:__imp_CompareStringA
0x18001641e  nop     dword ptr [rax+rax+00h]
0x180016423  mov     ecx, esi
0x180016425  mov     esi, 1
0x18001642a  cmp     eax, 2
0x18001642d  cmovz   ecx, esi
0x180016430  mov     esi, ecx
0x180016432  mov     eax, esi
0x180016434  mov     rcx, [rsp+168h+var_28]
0x18001643c  xor     rcx, rsp; StackCookie
0x18001643f  call    __security_check_cookie
0x180016444  mov     rbx, [rsp+168h+arg_10]
0x18001644c  add     rsp, 150h
0x180016453  pop     rdi
0x180016454  pop     rsi
0x180016455  pop     rbp
0x180016456  retn
```
