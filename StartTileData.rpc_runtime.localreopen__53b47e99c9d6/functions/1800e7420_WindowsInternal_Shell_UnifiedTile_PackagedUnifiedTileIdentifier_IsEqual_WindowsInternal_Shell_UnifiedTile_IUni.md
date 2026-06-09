# WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier::IsEqual(WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *,uchar *)

- ea: `0x1800e7420`
- end: `0x1800e75aa`
- name: `?IsEqual@PackagedUnifiedTileIdentifier@UnifiedTile@Shell@WindowsInternal@@UEAAJPEAUIUnifiedTileIdentifier@234@PEAE@Z`
- size: `394`
- prototype: `__int64 __fastcall(WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier *__hidden this, struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, unsigned __int8 *)`
- caller_count: `0`
- callee_count: `3`
- tags: `broker_com_uri`

## callees

- `0x18001aca4`
- `0x1800e7420`
- `0x1803c2010`

## import_xrefs

- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e7535`
- `api-ms-win-core-string-l1-1-0!CompareStringOrdinal` at `0x1800e7535`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e745e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e74ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e74ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e755e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e759a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e745e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e74ae`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e74ff`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e7511`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e755e`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x1800e759a`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e7494`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e74e4`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e7494`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x1800e74e4`

## string_xrefs

- `0x1800e7549`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifier.cpp`
- `0x1800e756b`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifier.cpp`
- `0x1800e7585`: `shellcommon\shell\tiles\unifiedtilemodel\lib\unifiedtileidentifier.cpp`

## pseudocode

```c
__int64 __fastcall WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier::IsEqual(
        WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier *this,
        struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *a2,
        unsigned __int8 *a3)
{
  __int64 (__fastcall *v6)(WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier *, HSTRING *); // rbx
  int v7; // eax
  unsigned int v8; // ebx
  const WCHAR *StringRawBuffer; // rdi
  __int64 (__fastcall *v10)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, HSTRING *); // rbx
  int v11; // eax
  const WCHAR *v12; // rax
  unsigned __int8 v13; // bl
  BOOL bIgnoreCase; // [rsp+20h] [rbp-20h]
  BOOL bIgnoreCasea; // [rsp+20h] [rbp-20h]
  HSTRING string[2]; // [rsp+30h] [rbp-10h] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+68h] [rbp+28h]
  UINT32 length; // [rsp+70h] [rbp+30h] BYREF
  UINT32 v20; // [rsp+80h] [rbp+40h] BYREF
  HSTRING v21; // [rsp+88h] [rbp+48h] BYREF

  *a3 = 0;
  if ( this && a2 )
  {
    string[0] = 0;
    v6 = *(__int64 (__fastcall **)(WindowsInternal::Shell::UnifiedTile::PackagedUnifiedTileIdentifier *, HSTRING *))(*(_QWORD *)this + 56LL);
    WindowsDeleteString(0);
    string[0] = 0;
    v7 = v6(this, string);
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
      v21 = 0;
      v10 = *(__int64 (__fastcall **)(struct WindowsInternal::Shell::UnifiedTile::IUnifiedTileIdentifier *, HSTRING *))(*(_QWORD *)a2 + 56LL);
      WindowsDeleteString(0);
      v21 = 0;
      v11 = v10(a2, &v21);
      v8 = v11;
      if ( v11 >= 0 )
      {
        v20 = 0;
        v12 = WindowsGetStringRawBuffer(v21, &v20);
        if ( length != v20 || (v13 = 1, CompareStringOrdinal(StringRawBuffer, length, v12, v20, 1) != 2) )
          v13 = 0;
        *a3 = v13;
        WindowsDeleteString(v21);
        v21 = 0;
        WindowsDeleteString(string[0]);
        return 0;
      }
      wil::details::in1diag3::Return_Hr(
        retaddr,
        (void *)0xA4,
        (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifier.cpp",
        (const char *)(unsigned int)v11,
        bIgnoreCase);
      WindowsDeleteString(v21);
      v21 = 0;
    }
    WindowsDeleteString(string[0]);
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x12E,
      (unsigned int)"shellcommon\\shell\\tiles\\unifiedtilemodel\\lib\\unifiedtileidentifier.cpp",
      (const char *)v8,
      bIgnoreCasea);
    return v8;
  }
  return 0;
}

```

## disassembly

```asm
0x1800e7420  push    rbp
0x1800e7422  push    rbx
0x1800e7423  push    rsi
0x1800e7424  push    rdi
0x1800e7425  push    r14
0x1800e7427  mov     rbp, rsp
0x1800e742a  sub     rsp, 40h
0x1800e742e  mov     r14, r8
0x1800e7431  mov     rsi, rdx
0x1800e7434  mov     rdi, rcx
0x1800e7437  mov     byte ptr [r8], 0
0x1800e743b  test    rcx, rcx
0x1800e743e  jz      loc_1800E7517
0x1800e7444  test    rdx, rdx
0x1800e7447  jz      loc_1800E7517
0x1800e744d  mov     [rbp+string], 0
0x1800e7455  mov     rax, [rcx]
0x1800e7458  mov     rbx, [rax+38h]
0x1800e745c  xor     ecx, ecx; string
0x1800e745e  call    cs:__imp_WindowsDeleteString
0x1800e7464  mov     [rbp+string], 0
0x1800e746c  lea     rdx, [rbp+string]
0x1800e7470  mov     rcx, rdi
0x1800e7473  mov     rax, rbx
0x1800e7476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e747b  mov     ebx, eax
0x1800e747d  test    eax, eax
0x1800e747f  js      loc_1800E7542
0x1800e7485  mov     [rbp+length], 0
0x1800e748c  lea     rdx, [rbp+length]; length
0x1800e7490  mov     rcx, [rbp+string]; string
0x1800e7494  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e749a  mov     rdi, rax
0x1800e749d  mov     [rbp+arg_18], 0
0x1800e74a5  mov     rcx, [rsi]
0x1800e74a8  mov     rbx, [rcx+38h]
0x1800e74ac  xor     ecx, ecx; string
0x1800e74ae  call    cs:__imp_WindowsDeleteString
0x1800e74b4  mov     [rbp+arg_18], 0
0x1800e74bc  lea     rdx, [rbp+arg_18]
0x1800e74c0  mov     rcx, rsi
0x1800e74c3  mov     rax, rbx
0x1800e74c6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800e74cb  mov     ebx, eax
0x1800e74cd  test    eax, eax
0x1800e74cf  js      loc_1800E757E
0x1800e74d5  mov     [rbp+arg_10], 0
0x1800e74dc  lea     rdx, [rbp+arg_10]; length
0x1800e74e0  mov     rcx, [rbp+arg_18]; string
0x1800e74e4  call    cs:__imp_WindowsGetStringRawBuffer
0x1800e74ea  mov     edx, [rbp+length]; cchCount1
0x1800e74ed  mov     r9d, [rbp+arg_10]; cchCount2
0x1800e74f1  cmp     edx, r9d
0x1800e74f4  jz      short loc_1800E7526
0x1800e74f6  xor     bl, bl
0x1800e74f8  mov     [r14], bl
0x1800e74fb  mov     rcx, [rbp+arg_18]; string
0x1800e74ff  call    cs:__imp_WindowsDeleteString
0x1800e7505  mov     [rbp+arg_18], 0
0x1800e750d  mov     rcx, [rbp+string]; string
0x1800e7511  call    cs:__imp_WindowsDeleteString
0x1800e7517  xor     ebx, ebx
0x1800e7519  mov     eax, ebx
0x1800e751b  add     rsp, 40h
0x1800e751f  pop     r14
0x1800e7521  pop     rdi
0x1800e7522  pop     rsi
0x1800e7523  pop     rbx
0x1800e7524  pop     rbp
0x1800e7525  retn
0x1800e7526  mov     ebx, 1
0x1800e752b  mov     [rsp+40h+bIgnoreCase], ebx; bIgnoreCase
0x1800e752f  mov     r8, rax; lpString2
0x1800e7532  mov     rcx, rdi; lpString1
0x1800e7535  call    cs:__imp_CompareStringOrdinal
0x1800e753b  cmp     eax, 2
0x1800e753e  jz      short loc_1800E74F8
0x1800e7540  jmp     short loc_1800E74F6
0x1800e7542  mov     rcx, [rbp+28h]; this
0x1800e7546  mov     r9d, eax; char *
0x1800e7549  lea     r8, aShellcommonShe_227; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800e7550  mov     edx, 9Fh; void *
0x1800e7555  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e755a  mov     rcx, [rbp+string]; string
0x1800e755e  call    cs:__imp_WindowsDeleteString
0x1800e7564  mov     rcx, [rbp+28h]; this
0x1800e7568  mov     r9d, ebx; char *
0x1800e756b  lea     r8, aShellcommonShe_227; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800e7572  mov     edx, 12Eh; void *
0x1800e7577  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e757c  jmp     short loc_1800E7519
0x1800e757e  mov     rcx, [rbp+28h]; this
0x1800e7582  mov     r9d, eax; char *
0x1800e7585  lea     r8, aShellcommonShe_227; "shellcommon\\shell\\tiles\\unifiedtilem"...
0x1800e758c  mov     edx, 0A4h; void *
0x1800e7591  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x1800e7596  mov     rcx, [rbp+arg_18]; string
0x1800e759a  call    cs:__imp_WindowsDeleteString
0x1800e75a0  mov     [rbp+arg_18], 0
0x1800e75a8  jmp     short loc_1800E755A
```
