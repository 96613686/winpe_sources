# FontCacheStorage::Flush(DWrite::RefString const &,wchar_t const *)

- ea: `0x180067e1c`
- end: `0x18006809f`
- name: `?Flush@FontCacheStorage@@QEAAJAEBVRefString@DWrite@@PEB_W@Z`
- size: `643`
- prototype: `__int64 __fastcall(HANDLE *this, const struct DWrite::RefString *, const wchar_t *)`
- caller_count: `2`
- callee_count: `8`
- tags: `file_ops, broker_com_uri`

## callers

- `0x1800680b0`
- `0x18006a2dc`

## callees

- `0x1800086ac`
- `0x18000d55c`
- `0x18000e920`
- `0x18000f6bc`
- `0x180028c50`
- `0x180067e1c`
- `0x18009f830`
- `0x1800a56f0`

## import_xrefs

- `api-ms-win-core-memory-l1-1-0!FlushViewOfFile` at `0x180067f29`
- `api-ms-win-core-memory-l1-1-0!FlushViewOfFile` at `0x180067f29`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180067f69`
- `api-ms-win-core-file-l1-1-0!FlushFileBuffers` at `0x180067f69`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180067fc2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180067ff8`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180067fc2`
- `api-ms-win-core-file-l2-1-0!MoveFileExW` at `0x180067ff8`

## pseudocode

```c
__int64 __fastcall FontCacheStorage::Flush(HANDLE *this, const struct DWrite::RefString *a2, const wchar_t *a3)
{
  bool IsOpenState; // al
  __int64 v7; // rcx
  __int64 v8; // r8
  __int64 result; // rax
  char *v10; // r14
  __int64 v11; // rbx
  __int64 v12; // rdx
  __int64 v13; // rcx
  __int64 v14; // r8
  __int64 v15; // rcx
  unsigned int v16; // ebx
  unsigned int v17; // ebx
  unsigned int Error; // ebx
  struct DWrite::RefString::Data *v19; // [rsp+20h] [rbp-88h] BYREF
  __int64 v20; // [rsp+28h] [rbp-80h]
  _QWORD v21[2]; // [rsp+30h] [rbp-78h] BYREF
  const wchar_t *v22; // [rsp+40h] [rbp-68h]
  __int64 v23; // [rsp+48h] [rbp-60h]
  _QWORD v24[11]; // [rsp+50h] [rbp-58h] BYREF
  struct DWrite::RefString::Data *v26; // [rsp+C8h] [rbp+20h] BYREF

  v20 = 0x6873756C66LL;
  IsOpenState = FontCacheStorage::IsOpenState((FontCacheStorage *)this);
  try
  {
    if ( !IsOpenState )
      return 0;
    if ( !*(_QWORD *)(v7 + 32) )
    {
      v10 = (char *)(v7 + 16);
      EventLogger::LogEvent<EventTag>(v7 + 16, 0x656761726F7453LL, 0x6873756C66LL, 0x656C69666F6ELL);
LABEL_18:
      this[3] = (HANDLE)0x64656873756C66LL;
      EventLogger::LogEvent<EventTag>(v10, 0x656761726F7453LL, 0x6574617473LL, 0x64656873756C66LL);
      return 0;
    }
    v11 = -1;
    v12 = -1;
    do
      ++v12;
    while ( *(_WORD *)(v8 + 2 * v12) );
    v13 = *(_QWORD *)a2;
    v21[0] = *(_QWORD *)a2 + 8LL;
    v21[1] = *(unsigned int *)(v13 + 4);
    v22 = a3;
    v23 = v12;
    DWrite::RefString::RefString(&v26, v21);
    do
      ++v11;
    while ( a3[v11] );
    v15 = *(_QWORD *)a2;
    LOWORD(v22) = 126;
    v24[0] = v15 + 8;
    v24[1] = *(unsigned int *)(v15 + 4);
    v24[2] = v22;
    v24[3] = a3;
    v24[4] = v11;
    DWrite::RefString::RefString(&v19, v24, v14);
    if ( FlushViewOfFile(*((LPCVOID *)this[12] + 9), 0) )
    {
      if ( FlushFileBuffers(this[4]) )
      {
        if ( MoveFileExW((LPCWSTR)v19 + 4, (LPCWSTR)v26 + 4, 1u)
          || (FontCache::TryRenameAsObsolete((LPCWSTR)v26 + 4, a2), MoveFileExW((LPCWSTR)v19 + 4, (LPCWSTR)v26 + 4, 1u)) )
        {
          DWrite::RefString::DecrementRef(v19);
          DWrite::RefString::DecrementRef(v26);
          v10 = (char *)(this + 2);
          goto LABEL_18;
        }
        Error = EventSource<ComInterfaceList<FontCacheStorage,IFontCacheStorage,IFontCacheStorageInternal>,IFontCacheStorageInternal>::LogLastError(
                  this,
                  0x6873756C66LL,
                  425);
        DWrite::RefString::DecrementRef(v19);
        DWrite::RefString::DecrementRef(v26);
        result = Error;
      }
      else
      {
        v17 = EventSource<ComInterfaceList<FontCacheStorage,IFontCacheStorage,IFontCacheStorageInternal>,IFontCacheStorageInternal>::LogLastError(
                this,
                0x6873756C66LL,
                409);
        DWrite::RefString::DecrementRef(v19);
        DWrite::RefString::DecrementRef(v26);
        result = v17;
      }
    }
    else
    {
      v16 = EventSource<ComInterfaceList<FontCacheStorage,IFontCacheStorage,IFontCacheStorageInternal>,IFontCacheStorageInternal>::LogLastError(
              this,
              0x6873756C66LL,
              404);
      DWrite::RefString::DecrementRef(v19);
      DWrite::RefString::DecrementRef(v26);
      result = v16;
    }
  }
  catch ( ... )
  {
    EventSource<ComInterfaceList<FontCacheStorage,IFontCacheStorage,IFontCacheStorageInternal>,IFontCacheStorageInternal>::LogCurrentException<>(
      this,
      v20,
      436);
  }
  return result;
}

```

## disassembly

```asm
0x180067e1c  mov     [rsp+arg_8], rbx
0x180067e21  mov     [rsp+arg_0], rcx
0x180067e26  push    rsi
0x180067e27  push    rdi
0x180067e28  push    r12
0x180067e2a  push    r14
0x180067e2c  push    r15
0x180067e2e  sub     rsp, 80h
0x180067e35  mov     r14, r8
0x180067e38  mov     r15, rdx
0x180067e3b  mov     rsi, rcx
0x180067e3e  mov     rdi, 6873756C66h
0x180067e48  mov     [rsp+0A8h+var_80], rdi
0x180067e4d  call    ?IsOpenState@FontCacheStorage@@QEBA_NXZ; FontCacheStorage::IsOpenState(void)
0x180067e52  xor     r12d, r12d
0x180067e55  test    al, al
0x180067e57  jnz     short loc_180067E60
0x180067e59  xor     eax, eax
0x180067e5b  jmp     loc_180068087
0x180067e60  cmp     [rcx+20h], r12
0x180067e64  jnz     short loc_180067E91
0x180067e66  mov     r9, 656C69666F6Eh
0x180067e70  lea     r14, [rcx+10h]
0x180067e74  mov     rbx, 656761726F7453h
0x180067e7e  mov     r8, rdi
0x180067e81  mov     rdx, rbx
0x180067e84  mov     rcx, r14
0x180067e87  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x180067e8c  jmp     loc_180068057
0x180067e91  or      rbx, 0FFFFFFFFFFFFFFFFh
0x180067e95  mov     rdx, rbx
0x180067e98  inc     rdx
0x180067e9b  cmp     [r8+rdx*2], r12w
0x180067ea0  jnz     short loc_180067E98
0x180067ea2  mov     rcx, [r15]
0x180067ea5  lea     rax, [rcx+8]
0x180067ea9  mov     [rsp+0A8h+var_78], rax
0x180067eae  mov     eax, [rcx+4]
0x180067eb1  mov     [rsp+0A8h+var_70], rax
0x180067eb6  mov     [rsp+0A8h+var_68], r14
0x180067ebb  mov     [rsp+0A8h+var_60], rdx
0x180067ec0  lea     rdx, [rsp+0A8h+var_78]
0x180067ec5  lea     rcx, [rsp+0A8h+arg_18]
0x180067ecd  call    ??$?0V?$StringSum@PEB_WPEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@PEB_WPEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<wchar_t const *,wchar_t const *>> const &)
0x180067ed2  nop
0x180067ed3  inc     rbx
0x180067ed6  cmp     [r14+rbx*2], r12w
0x180067edb  jnz     short loc_180067ED3
0x180067edd  mov     rcx, [r15]
0x180067ee0  mov     eax, 7Eh ; '~'
0x180067ee5  mov     word ptr [rsp+0A8h+var_68], ax
0x180067eea  lea     rax, [rcx+8]
0x180067eee  mov     [rsp+0A8h+var_58], rax
0x180067ef3  mov     eax, [rcx+4]
0x180067ef6  mov     [rsp+0A8h+var_50], rax
0x180067efb  mov     rax, [rsp+0A8h+var_68]
0x180067f00  mov     [rsp+0A8h+var_48], rax
0x180067f05  mov     [rsp+0A8h+var_40], r14
0x180067f0a  mov     [rsp+0A8h+var_38], rbx
0x180067f0f  lea     rdx, [rsp+0A8h+var_58]
0x180067f14  lea     rcx, [rsp+0A8h+var_88]
0x180067f19  call    ??$?0V?$StringSum@V?$StringSum@PEB_W_W@@PEB_W@@@RefString@DWrite@@QEAA@AEBV?$StringExpr@V?$StringSum@V?$StringSum@PEB_W_W@@PEB_W@@@@@Z; DWrite::RefString::RefString(StringExpr<StringSum<StringSum<wchar_t const *,wchar_t>,wchar_t const *>> const &)
0x180067f1e  nop
0x180067f1f  mov     rcx, [rsi+60h]
0x180067f23  xor     edx, edx; dwNumberOfBytesToFlush
0x180067f25  mov     rcx, [rcx+48h]; lpBaseAddress
0x180067f29  call    cs:__imp_FlushViewOfFile
0x180067f2f  test    eax, eax
0x180067f31  jnz     short loc_180067F65
0x180067f33  mov     r8d, 194h
0x180067f39  mov     rdx, rdi
0x180067f3c  mov     rcx, rsi
0x180067f3f  call    ?LogLastError@?$EventSource@V?$ComInterfaceList@VFontCacheStorage@@UIFontCacheStorage@@UIFontCacheStorageInternal@@@@UIFontCacheStorageInternal@@@@QEBAJVEventTag@@I@Z; EventSource<ComInterfaceList<FontCacheStorage,IFontCacheStorage,IFontCacheStorageInternal>,IFontCacheStorageInternal>::LogLastError(EventTag,uint)
0x180067f44  mov     ebx, eax
0x180067f46  mov     rcx, [rsp+0A8h+var_88]; struct DWrite::RefString::Data *
0x180067f4b  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180067f50  nop
0x180067f51  mov     rcx, [rsp+0A8h+arg_18]; struct DWrite::RefString::Data *
0x180067f59  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180067f5e  mov     eax, ebx
0x180067f60  jmp     loc_180068087
0x180067f65  mov     rcx, [rsi+20h]; hFile
0x180067f69  call    cs:__imp_FlushFileBuffers
0x180067f6f  test    eax, eax
0x180067f71  jnz     short loc_180067FA5
0x180067f73  mov     r8d, 199h
0x180067f79  mov     rdx, rdi
0x180067f7c  mov     rcx, rsi
0x180067f7f  call    ?LogLastError@?$EventSource@V?$ComInterfaceList@VFontCacheStorage@@UIFontCacheStorage@@UIFontCacheStorageInternal@@@@UIFontCacheStorageInternal@@@@QEBAJVEventTag@@I@Z; EventSource<ComInterfaceList<FontCacheStorage,IFontCacheStorage,IFontCacheStorageInternal>,IFontCacheStorageInternal>::LogLastError(EventTag,uint)
0x180067f84  mov     ebx, eax
0x180067f86  mov     rcx, [rsp+0A8h+var_88]; struct DWrite::RefString::Data *
0x180067f8b  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180067f90  nop
0x180067f91  mov     rcx, [rsp+0A8h+arg_18]; struct DWrite::RefString::Data *
0x180067f99  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180067f9e  mov     eax, ebx
0x180067fa0  jmp     loc_180068087
0x180067fa5  mov     rdx, [rsp+0A8h+arg_18]
0x180067fad  add     rdx, 8; lpNewFileName
0x180067fb1  mov     rcx, [rsp+0A8h+var_88]
0x180067fb6  add     rcx, 8; lpExistingFileName
0x180067fba  mov     ebx, 1
0x180067fbf  mov     r8d, ebx; dwFlags
0x180067fc2  call    cs:__imp_MoveFileExW
0x180067fc8  test    eax, eax
0x180067fca  jnz     short loc_180068031
0x180067fcc  mov     rcx, [rsp+0A8h+arg_18]
0x180067fd4  add     rcx, 8; lpExistingFileName
0x180067fd8  mov     rdx, r15; struct DWrite::RefString *
0x180067fdb  call    ?TryRenameAsObsolete@FontCache@@SAJPEB_WAEBVRefString@DWrite@@@Z; FontCache::TryRenameAsObsolete(wchar_t const *,DWrite::RefString const &)
0x180067fe0  mov     rdx, [rsp+0A8h+arg_18]
0x180067fe8  add     rdx, 8; lpNewFileName
0x180067fec  mov     rcx, [rsp+0A8h+var_88]
0x180067ff1  add     rcx, 8; lpExistingFileName
0x180067ff5  mov     r8d, ebx; dwFlags
0x180067ff8  call    cs:__imp_MoveFileExW
0x180067ffe  test    eax, eax
0x180068000  jnz     short loc_180068031
0x180068002  mov     r8d, 1A9h
0x180068008  mov     rdx, rdi
0x18006800b  mov     rcx, rsi
0x18006800e  call    ?LogLastError@?$EventSource@V?$ComInterfaceList@VFontCacheStorage@@UIFontCacheStorage@@UIFontCacheStorageInternal@@@@UIFontCacheStorageInternal@@@@QEBAJVEventTag@@I@Z; EventSource<ComInterfaceList<FontCacheStorage,IFontCacheStorage,IFontCacheStorageInternal>,IFontCacheStorageInternal>::LogLastError(EventTag,uint)
0x180068013  mov     ebx, eax
0x180068015  mov     rcx, [rsp+0A8h+var_88]; struct DWrite::RefString::Data *
0x18006801a  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18006801f  nop
0x180068020  mov     rcx, [rsp+0A8h+arg_18]; struct DWrite::RefString::Data *
0x180068028  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18006802d  mov     eax, ebx
0x18006802f  jmp     short loc_180068087
0x180068031  mov     rcx, [rsp+0A8h+var_88]; struct DWrite::RefString::Data *
0x180068036  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x18006803b  nop
0x18006803c  mov     rcx, [rsp+0A8h+arg_18]; struct DWrite::RefString::Data *
0x180068044  call    ?DecrementRef@RefString@DWrite@@CAXPEAUData@12@@Z; DWrite::RefString::DecrementRef(DWrite::RefString::Data *)
0x180068049  lea     r14, [rsi+10h]
0x18006804d  mov     rbx, 656761726F7453h
0x180068057  mov     r9, 64656873756C66h
0x180068061  mov     [rsi+18h], r9
0x180068065  mov     r8, 6574617473h
0x18006806f  mov     rdx, rbx
0x180068072  mov     rcx, r14
0x180068075  call    ??$LogEvent@VEventTag@@@EventLogger@@QEBAXVEventTag@@00@Z; EventLogger::LogEvent<EventTag>(EventTag,EventTag,EventTag)
0x18006807a  nop
0x18006807b  jmp     loc_180067E59
0x180068080  mov     eax, dword ptr [rsp+0A8h+arg_18]
0x180068087  mov     rbx, [rsp+0A8h+arg_8]
0x18006808f  add     rsp, 80h
0x180068096  pop     r15
0x180068098  pop     r14
0x18006809a  pop     r12
0x18006809c  pop     rdi
0x18006809d  pop     rsi
0x18006809e  retn
```
