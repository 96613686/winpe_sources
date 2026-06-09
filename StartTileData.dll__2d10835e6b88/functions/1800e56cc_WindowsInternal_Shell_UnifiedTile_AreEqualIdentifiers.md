# WindowsInternal::Shell::UnifiedTile::AreEqualIdentifiers

- ea: `0x1800e56cc`
- end: `0x1800e5841`
- name: `WindowsInternal::Shell::UnifiedTile::AreEqualIdentifiers`
- size: `373`
- prototype: ``
- caller_count: `3`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x1800e5690`
- `0x1802dd3a0`
- `0x1802dd3e0`

## callees

- `0x18001aca4`
- `0x1800e56cc`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e57df`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e57df`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e570a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e575a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e57ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e57bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e570a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e575a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e57ab`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e57bd`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5809`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e5830`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5790`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5740`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e5790`

## string_xrefs

- `0x1800e57f3`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifier.cpp`
- `0x1800e581a`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifier.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::AreEqualIdentifiers(__int64 a1, __int64 a2, char *a3)
{
  __int64 (__fastcall *v6)(__int64, HSTRING *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  const WCHAR *StringRawBuffer; // rdi
  __int64 (__fastcall *v10)(__int64, HSTRING *); // rbx
  int v11; // eax
  const WCHAR *v12; // rax
  char v13; // bl
  BOOL bIgnoreCase; // [rsp+20h] [rbp-20h]
  HSTRING string[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  UINT32 length; // [rsp+70h] [rbp+30h] BYREF
  UINT32 v19; // [rsp+80h] [rbp+40h] BYREF
  HSTRING v20; // [rsp+88h] [rbp+48h] BYREF

  *a3 = 0;
  if ( !a1 || !a2 )
    return 0;
  string[0] = 0;
  v6 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a1 + 56LL);
  WindowsDeleteString(0);
  string[0] = 0;
  v7 = v6(a1, string);
  v8 = v7;
  if ( v7 < 0 )
  {
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x9F,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifier.cpp",
      (const char *)(unsigned int)v7,
      bIgnoreCase);
  }
  else
  {
    length = 0;
    StringRawBuffer = WindowsGetStringRawBuffer(string[0], &length);
    v20 = 0;
    v10 = *(__int64 (__fastcall **)(__int64, HSTRING *))(*(_QWORD *)a2 + 56LL);
    WindowsDeleteString(0);
    v20 = 0;
    v11 = v10(a2, &v20);
    v8 = v11;
    if ( v11 >= 0 )
    {
      v19 = 0;
      v12 = WindowsGetStringRawBuffer(v20, &v19);
      if ( length != v19 || (v13 = 1, CompareStringOrdinal(StringRawBuffer, length, v12, v19, 1) != 2) )
        v13 = 0;
      *a3 = v13;
      WindowsDeleteString(v20);
      v20 = 0;
      WindowsDeleteString(string[0]);
      return 0;
    }
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0xA4,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifier.cpp",
      (const char *)(unsigned int)v11,
      bIgnoreCase);
    WindowsDeleteString(v20);
    v20 = 0;
  }
  WindowsDeleteString(string[0]);
  return v8;
}

```

## disassembly

```asm
0x1800e56cc  push    rbp
0x1800e56ce  push    rbx
0x1800e56cf  push    rsi
0x1800e56d0  push    rdi
0x1800e56d1  push    r14
0x1800e56d3  mov     rbp, rsp
0x1800e56d6  sub     rsp, 40h
0x1800e56da  mov     r14, r8
0x1800e56dd  mov     rsi, rdx
0x1800e56e0  mov     rdi, rcx
0x1800e56e3  mov     byte ptr [r8], 0
0x1800e56e7  test    rcx, rcx
0x1800e56ea  jz      loc_1800E57C3
0x1800e56f0  test    rdx, rdx
0x1800e56f3  jz      loc_1800E57C3
0x1800e56f9  mov     [rbp+string], 0
0x1800e5701  mov     rax, [rcx]
0x1800e5704  mov     rbx, [rax+38h]
0x1800e5708  xor     ecx, ecx; string
0x1800e570a  call    cs:__imp_WindowsDeleteString
0x1800e5710  mov     [rbp+string], 0
0x1800e5718  lea     rdx, [rbp+string]
0x1800e571c  mov     rcx, rdi
0x1800e571f  mov     rax, rbx
0x1800e5722  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5727  mov     ebx, eax
0x1800e5729  test    eax, eax
0x1800e572b  js      loc_1800E57EC
0x1800e5731  mov     [rbp+length], 0
0x1800e5738  lea     rdx, [rbp+length]; length
0x1800e573c  mov     rcx, [rbp+string]; string
0x1800e5740  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5746  mov     rdi, rax
0x1800e5749  mov     [rbp+arg_18], 0
0x1800e5751  mov     rcx, [rsi]
0x1800e5754  mov     rbx, [rcx+38h]
0x1800e5758  xor     ecx, ecx; string
0x1800e575a  call    cs:__imp_WindowsDeleteString
0x1800e5760  mov     [rbp+arg_18], 0
0x1800e5768  lea     rdx, [rbp+arg_18]
0x1800e576c  mov     rcx, rsi
0x1800e576f  mov     rax, rbx
0x1800e5772  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e5777  mov     ebx, eax
0x1800e5779  test    eax, eax
0x1800e577b  js      loc_1800E5813
0x1800e5781  mov     [rbp+arg_10], 0
0x1800e5788  lea     rdx, [rbp+arg_10]; length
0x1800e578c  mov     rcx, [rbp+arg_18]; string
0x1800e5790  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e5796  mov     edx, [rbp+length]; cchCount1
0x1800e5799  mov     r9d, [rbp+arg_10]; cchCount2
0x1800e579d  cmp     edx, r9d
0x1800e57a0  jz      short loc_1800E57D0
0x1800e57a2  xor     bl, bl
0x1800e57a4  mov     [r14], bl
0x1800e57a7  mov     rcx, [rbp+arg_18]; string
0x1800e57ab  call    cs:__imp_WindowsDeleteString
0x1800e57b1  mov     [rbp+arg_18], 0
0x1800e57b9  mov     rcx, [rbp+string]; string
0x1800e57bd  call    cs:__imp_WindowsDeleteString
0x1800e57c3  xor     eax, eax
0x1800e57c5  add     rsp, 40h
0x1800e57c9  pop     r14
0x1800e57cb  pop     rdi
0x1800e57cc  pop     rsi
0x1800e57cd  pop     rbx
0x1800e57ce  pop     rbp
0x1800e57cf  retn
0x1800e57d0  mov     ebx, 1
0x1800e57d5  mov     [rsp+40h+bIgnoreCase], ebx; bIgnoreCase
0x1800e57d9  mov     r8, rax; lpString2
0x1800e57dc  mov     rcx, rdi; lpString1
0x1800e57df  call    cs:__imp_CompareStringOrdinal
0x1800e57e5  cmp     eax, 2
0x1800e57e8  jz      short loc_1800E57A4
0x1800e57ea  jmp     short loc_1800E57A2
0x1800e57ec  mov     rcx, [rbp+28h]; this
0x1800e57f0  mov     r9d, eax; char *
0x1800e57f3  lea     r8, aShellcommonShe_227; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800e57fa  mov     edx, 9Fh; void *
0x1800e57ff  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e5804  nop
0x1800e5805  mov     rcx, [rbp+string]; string
0x1800e5809  call    cs:__imp_WindowsDeleteString
0x1800e580f  mov     eax, ebx
0x1800e5811  jmp     short loc_1800E57C5
0x1800e5813  mov     rcx, [rbp+28h]; this
0x1800e5817  mov     r9d, eax; char *
0x1800e581a  lea     r8, aShellcommonShe_227; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800e5821  mov     edx, 0A4h; void *
0x1800e5826  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e582b  nop
0x1800e582c  mov     rcx, [rbp+arg_18]; string
0x1800e5830  call    cs:__imp_WindowsDeleteString
0x1800e5836  mov     [rbp+arg_18], 0
0x1800e583e  jmp     short loc_1800E5805
```
