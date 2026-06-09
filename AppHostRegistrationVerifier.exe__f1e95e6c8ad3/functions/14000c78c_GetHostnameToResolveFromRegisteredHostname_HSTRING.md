# GetHostnameToResolveFromRegisteredHostname(HSTRING__ *)

- ea: `0x14000c78c`
- end: `0x14000c840`
- name: `?GetHostnameToResolveFromRegisteredHostname@@YA?AVHString@Wrappers@WRL@Microsoft@@PEAUHSTRING__@@@Z`
- size: `180`
- prototype: `HSTRING *__fastcall(HSTRING *, HSTRING)`
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000b114`

## callees

- `0x14000c78c`
- `0x14000fbb0`

## import_xrefs

- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14000c82b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDuplicateString` at `0x14000c82b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstring` at `0x14000c7e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsSubstring` at `0x14000c7e7`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c7cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c7cf`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x14000c818`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000c7bc`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x14000c7bc`

## pseudocode

```c
HSTRING *__fastcall GetHostnameToResolveFromRegisteredHostname(HSTRING *a1, HSTRING a2)
{
  HRESULT v4; // eax
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *a1 = 0;
  if ( *WindowsGetStringRawBuffer(a2, 0) == 42 )
  {
    WindowsDeleteString(*a1);
    *a1 = 0;
    v4 = WindowsSubstring(a2, 2u, a1);
    if ( v4 < 0 )
      wil::details::in1diag3::_Throw_Hr(
        retaddr,
        (void *)0x55,
        (unsigned int)"onecoreuap\\base\\appmodel\\apphostnameregistrationverifier\\lib\\hostnameverifier.cpp",
        (const char *)(unsigned int)v4,
        1);
  }
  else if ( !a2 || a2 != *a1 )
  {
    WindowsDeleteString(*a1);
    *a1 = 0;
    WindowsDuplicateString(a2, a1);
  }
  return a1;
}

```

## disassembly

```asm
0x14000c78c  mov     rax, rsp
0x14000c78f  mov     [rax+10h], rbx
0x14000c793  mov     [rax+8], rcx
0x14000c797  push    rdi
0x14000c798  sub     rsp, 30h
0x14000c79c  mov     rdi, rdx
0x14000c79f  mov     rbx, rcx
0x14000c7a2  mov     dword ptr [rax-18h], 0
0x14000c7a9  mov     qword ptr [rcx], 0
0x14000c7b0  mov     dword ptr [rax-18h], 1
0x14000c7b7  xor     edx, edx; length
0x14000c7b9  mov     rcx, rdi; string
0x14000c7bc  call    cs:__imp_WindowsGetStringRawBuffer
0x14000c7c2  mov     ecx, 2Ah ; '*'
0x14000c7c7  cmp     cx, [rax]
0x14000c7ca  jnz     short loc_14000C80B
0x14000c7cc  mov     rcx, [rbx]; string
0x14000c7cf  call    cs:__imp_WindowsDeleteString
0x14000c7d5  mov     qword ptr [rbx], 0
0x14000c7dc  mov     r8, rbx; newString
0x14000c7df  mov     edx, 2; startIndex
0x14000c7e4  mov     rcx, rdi; string
0x14000c7e7  call    cs:__imp_WindowsSubstring
0x14000c7ed  test    eax, eax
0x14000c7ef  jns     short loc_14000C831
0x14000c7f1  mov     rcx, [rsp+38h]; this
0x14000c7f6  mov     r9d, eax; char *
0x14000c7f9  lea     r8, aOnecoreuapBase_0; "onecoreuap\\base\\appmodel\\apphostname"...
0x14000c800  mov     edx, 55h ; 'U'; void *
0x14000c805  call    ?_Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::_Throw_Hr(void *,uint,char const *,long)
0x14000c80b  test    rdi, rdi
0x14000c80e  jz      short loc_14000C815
0x14000c810  cmp     rdi, [rbx]
0x14000c813  jz      short loc_14000C831
0x14000c815  mov     rcx, [rbx]; string
0x14000c818  call    cs:__imp_WindowsDeleteString
0x14000c81e  mov     qword ptr [rbx], 0
0x14000c825  mov     rdx, rbx; newString
0x14000c828  mov     rcx, rdi; string
0x14000c82b  call    cs:__imp_WindowsDuplicateString
0x14000c831  mov     rax, rbx
0x14000c834  mov     rbx, [rsp+38h+arg_8]
0x14000c839  add     rsp, 30h
0x14000c83d  pop     rdi
0x14000c83e  retn
```
