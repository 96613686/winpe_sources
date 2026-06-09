# SystemSettings::WorkAccess::BuildUniqueIdFromAccountAndProviderId(HSTRING__ *,HSTRING__ *,HSTRING__ * *)

- ea: `0x180042b8c`
- end: `0x180042c80`
- name: `?BuildUniqueIdFromAccountAndProviderId@WorkAccess@SystemSettings@@YAJPEAUHSTRING__@@0PEAPEAU3@@Z`
- size: `244`
- prototype: `__int64 __fastcall(HSTRING string1, HSTRING string2, HSTRING newString, HSTRING *)`
- caller_count: `3`
- callee_count: `4`
- tags: `registry_config, loader_planting, broker_com_uri`

## callers

- `0x18001ed78`
- `0x18001f454`
- `0x1800431f8`

## callees

- `0x180002a60`
- `0x1800096ec`
- `0x18001197c`
- `0x180042b8c`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180042c04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180042c28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180042c04`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsConcatString` at `0x180042c28`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042bbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042c5c`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042bbe`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x180042c5c`

## string_xrefs

- `0x180042c44`: `shellcommon\shell\settingshandlers\workaccess\lib\sharedhelpers.cpp`

## pseudocode

```c
__int64 __fastcall SystemSettings::WorkAccess::BuildUniqueIdFromAccountAndProviderId(
        HSTRING string1,
        HSTRING string2,
        HSTRING *newString,
        HSTRING *a4)
{
  HRESULT v7; // eax
  unsigned int v8; // ebx
  __int64 v9; // rdx
  HSTRING newStringa; // [rsp+20h] [rbp-48h] BYREF
  HSTRING_HEADER hstringHeader; // [rsp+28h] [rbp-40h] BYREF
  HSTRING string2a; // [rsp+40h] [rbp-28h]
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+0h]

  *newString = 0;
  WindowsDeleteString(0);
  newStringa = 0;
  string2a = 0;
  Microsoft::WRL::Wrappers::HStringReference::CreateReference(&hstringHeader, L"_", 2u, 1u);
  v7 = WindowsConcatString(string1, string2a, &newStringa);
  v8 = v7;
  if ( v7 >= 0 )
  {
    v7 = WindowsConcatString(newStringa, string2, newString);
    v8 = v7;
    if ( v7 >= 0 )
    {
      v8 = 0;
      goto LABEL_7;
    }
    v9 = 26;
  }
  else
  {
    v9 = 25;
  }
  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)v9,
    (unsigned int)"shellcommon\\shell\\settingshandlers\\workaccess\\lib\\sharedhelpers.cpp",
    (const char *)(unsigned int)v7,
    (int)newStringa);
LABEL_7:
  WindowsDeleteString(newStringa);
  return v8;
}

```

## disassembly

```asm
0x180042b8c  push    rbx
0x180042b8e  push    rsi
0x180042b8f  push    rdi
0x180042b90  sub     rsp, 50h
0x180042b94  mov     rax, cs:__security_cookie
0x180042b9b  xor     rax, rsp
0x180042b9e  mov     [rsp+68h+var_20], rax
0x180042ba3  mov     rbx, rcx
0x180042ba6  mov     qword ptr [r8], 0
0x180042bad  xor     ecx, ecx; string
0x180042baf  mov     [rsp+68h+newString], 0
0x180042bb8  mov     rdi, r8
0x180042bbb  mov     rsi, rdx
0x180042bbe  call    cs:__imp_WindowsDeleteString
0x180042bc5  nop     dword ptr [rax+rax+00h]
0x180042bca  mov     r9d, 1; unsigned int
0x180042bd0  mov     [rsp+68h+newString], 0; int
0x180042bd9  lea     rdx, asc_18005E854; "_"
0x180042be0  mov     [rsp+68h+string2], 0
0x180042be9  lea     rcx, [rsp+68h+hstringHeader]; hstringHeader
0x180042bee  lea     r8d, [r9+1]; unsigned int
0x180042bf2  call    ?CreateReference@HStringReference@Wrappers@WRL@Microsoft@@AEAAXPEBGII@Z; Microsoft::WRL::Wrappers::HStringReference::CreateReference(ushort const *,uint,uint)
0x180042bf7  mov     rdx, [rsp+68h+string2]; string2
0x180042bfc  lea     r8, [rsp+68h+newString]; newString
0x180042c01  mov     rcx, rbx; string1
0x180042c04  call    cs:__imp_WindowsConcatString
0x180042c0b  nop     dword ptr [rax+rax+00h]
0x180042c10  mov     ebx, eax
0x180042c12  test    eax, eax
0x180042c14  jns     short loc_180042C1D
0x180042c16  mov     edx, 19h
0x180042c1b  jmp     short loc_180042C3F
0x180042c1d  mov     rcx, [rsp+68h+newString]; string1
0x180042c22  mov     r8, rdi; newString
0x180042c25  mov     rdx, rsi; string2
0x180042c28  call    cs:__imp_WindowsConcatString
0x180042c2f  nop     dword ptr [rax+rax+00h]
0x180042c34  mov     ebx, eax
0x180042c36  test    eax, eax
0x180042c38  jns     short loc_180042C55
0x180042c3a  mov     edx, 1Ah; void *
0x180042c3f  mov     rcx, [rsp+68h]; this
0x180042c44  lea     r8, aShellcommonShe_9; "shellcommon\\shell\\settingshandlers\\w"...
0x180042c4b  mov     r9d, eax; char *
0x180042c4e  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180042c53  jmp     short loc_180042C57
0x180042c55  xor     ebx, ebx
0x180042c57  mov     rcx, [rsp+68h+newString]; string
0x180042c5c  call    cs:__imp_WindowsDeleteString
0x180042c63  nop     dword ptr [rax+rax+00h]
0x180042c68  mov     eax, ebx
0x180042c6a  mov     rcx, [rsp+68h+var_20]
0x180042c6f  xor     rcx, rsp; StackCookie
0x180042c72  call    __security_check_cookie
0x180042c77  add     rsp, 50h
0x180042c7b  pop     rdi
0x180042c7c  pop     rsi
0x180042c7d  pop     rbx
0x180042c7e  retn
```
