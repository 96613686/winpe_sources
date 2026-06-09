# GetSharedFolder(ushort *,ulong *)

- ea: `0x180027fe8`
- end: `0x1800280e2`
- name: `?GetSharedFolder@@YAJPEAGPEAK@Z`
- size: `250`
- prototype: `__int64 __fastcall(wchar_t *Destination, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180013400`
- `0x180027dc0`
- `0x1800287d0`

## callees

- `0x180027fe8`
- `0x180066db2`
- `0x180066df0`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x180028088`
- `msvcrt!wcscpy_s` at `0x180028088`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280b7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800280b7`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180028050`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x180028050`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180028072`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x180028072`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall GetSharedFolder(wchar_t *Destination, unsigned int *a2)
{
  HRESULT v4; // ebx
  __int64 v5; // rax
  PWSTR ppszPath; // [rsp+20h] [rbp-248h] BYREF
  wchar_t pszPathOut[264]; // [rsp+30h] [rbp-238h] BYREF

  ppszPath = 0;
  memset_0(pszPathOut, 0, 0x20Au);
  if ( Destination && a2 )
  {
    v4 = SHGetKnownFolderPath(&FOLDERID_SharedData, 0x8000u, 0, &ppszPath);
    if ( v4 >= 0 )
    {
      v4 = PathCchCombine(pszPathOut, 0x105u, ppszPath, L"Enterprise");
      if ( v4 >= 0 )
      {
        if ( wcscpy_s(Destination, *a2, pszPathOut) )
        {
          v4 = -2147467259;
        }
        else
        {
          v5 = -1;
          do
            ++v5;
          while ( pszPathOut[v5] );
          *a2 = v5;
        }
      }
    }
    if ( ppszPath )
      CoTaskMemFree(ppszPath);
  }
  else
  {
    return (unsigned int)-2147024809;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x180027fe8  mov     [rsp+arg_10], rbx
0x180027fed  push    rbp
0x180027fee  push    rsi
0x180027fef  push    rdi
0x180027ff0  sub     rsp, 250h
0x180027ff7  mov     rax, cs:__security_cookie
0x180027ffe  xor     rax, rsp
0x180028001  mov     [rsp+268h+var_28], rax
0x180028009  mov     rdi, rdx
0x18002800c  mov     rsi, rcx
0x18002800f  xor     ebp, ebp
0x180028011  lea     rcx, [rsp+268h+pszPathOut]; void *
0x180028016  xor     edx, edx; Val
0x180028018  mov     [rsp+268h+ppszPath], rbp
0x18002801d  mov     r8d, 20Ah; Size
0x180028023  call    memset_0
0x180028028  test    rsi, rsi
0x18002802b  jnz     short loc_180028037
0x18002802d  mov     ebx, 80070057h
0x180028032  jmp     loc_1800280BD
0x180028037  test    rdi, rdi
0x18002803a  jz      short loc_18002802D
0x18002803c  lea     r9, [rsp+268h+ppszPath]; ppszPath
0x180028041  xor     r8d, r8d; hToken
0x180028044  mov     edx, 8000h; dwFlags
0x180028049  lea     rcx, FOLDERID_SharedData; rfid
0x180028050  call    cs:__imp_SHGetKnownFolderPath
0x180028056  mov     ebx, eax
0x180028058  test    eax, eax
0x18002805a  js      short loc_1800280AD
0x18002805c  mov     r8, [rsp+268h+ppszPath]; pszPathIn
0x180028061  lea     r9, ?ENTERPRISE_SHARED_FOLDER@@3QBGB; "Enterprise"
0x180028068  mov     edx, 105h; cchPathOut
0x18002806d  lea     rcx, [rsp+268h+pszPathOut]; pszPathOut
0x180028072  call    cs:__imp_PathCchCombine
0x180028078  mov     ebx, eax
0x18002807a  test    eax, eax
0x18002807c  js      short loc_1800280AD
0x18002807e  mov     edx, [rdi]; SizeInWords
0x180028080  lea     r8, [rsp+268h+pszPathOut]; Source
0x180028085  mov     rcx, rsi; Destination
0x180028088  call    cs:__imp_wcscpy_s
0x18002808e  test    eax, eax
0x180028090  jz      short loc_180028099
0x180028092  mov     ebx, 80004005h
0x180028097  jmp     short loc_1800280AD
0x180028099  lea     rcx, [rsp+268h+pszPathOut]
0x18002809e  or      rax, 0FFFFFFFFFFFFFFFFh
0x1800280a2  inc     rax
0x1800280a5  cmp     [rcx+rax*2], bp
0x1800280a9  jnz     short loc_1800280A2
0x1800280ab  mov     [rdi], eax
0x1800280ad  mov     rcx, [rsp+268h+ppszPath]; pv
0x1800280b2  test    rcx, rcx
0x1800280b5  jz      short loc_1800280BD
0x1800280b7  call    cs:__imp_CoTaskMemFree
0x1800280bd  mov     eax, ebx
0x1800280bf  mov     rcx, [rsp+268h+var_28]
0x1800280c7  xor     rcx, rsp; StackCookie
0x1800280ca  call    __security_check_cookie
0x1800280cf  mov     rbx, [rsp+268h+arg_10]
0x1800280d7  add     rsp, 250h
0x1800280de  pop     rdi
0x1800280df  pop     rsi
0x1800280e0  pop     rbp
0x1800280e1  retn
```
