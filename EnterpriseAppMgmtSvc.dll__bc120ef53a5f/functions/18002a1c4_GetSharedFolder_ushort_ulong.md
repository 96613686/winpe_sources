# GetSharedFolder(ushort *,ulong *)

- ea: `0x18002a1c4`
- end: `0x18002a2d7`
- name: `?GetSharedFolder@@YAJPEAGPEAK@Z`
- size: `275`
- prototype: `__int64 __fastcall(wchar_t *Destination, unsigned int *)`
- caller_count: `3`
- callee_count: `3`
- tags: `reparse_path, service_task, broker_com_uri`

## callers

- `0x180013eb4`
- `0x180029f90`
- `0x18002aac8`

## callees

- `0x18002a1c4`
- `0x18006c8d2`
- `0x18006c910`

## import_xrefs

- `msvcrt!wcscpy_s` at `0x18002a270`
- `msvcrt!wcscpy_s` at `0x18002a270`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a2a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002a2a5`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002a22c`
- `ext-ms-win-shell32-shellfolders-l1-1-0!SHGetKnownFolderPath` at `0x18002a22c`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002a254`
- `api-ms-win-core-path-l1-1-0!PathCchCombine` at `0x18002a254`

## pseudocode

```c
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
0x18002a1c4  mov     [rsp+arg_10], rbx
0x18002a1c9  push    rbp
0x18002a1ca  push    rsi
0x18002a1cb  push    rdi
0x18002a1cc  sub     rsp, 250h
0x18002a1d3  mov     rax, cs:__security_cookie
0x18002a1da  xor     rax, rsp
0x18002a1dd  mov     [rsp+268h+var_28], rax
0x18002a1e5  mov     rdi, rdx
0x18002a1e8  mov     rsi, rcx
0x18002a1eb  xor     ebp, ebp
0x18002a1ed  lea     rcx, [rsp+268h+pszPathOut]; void *
0x18002a1f2  xor     edx, edx; Val
0x18002a1f4  mov     [rsp+268h+ppszPath], rbp
0x18002a1f9  mov     r8d, 20Ah; Size
0x18002a1ff  call    memset_0
0x18002a204  test    rsi, rsi
0x18002a207  jnz     short loc_18002A213
0x18002a209  mov     ebx, 80070057h
0x18002a20e  jmp     loc_18002A2B1
0x18002a213  test    rdi, rdi
0x18002a216  jz      short loc_18002A209
0x18002a218  lea     r9, [rsp+268h+ppszPath]; ppszPath
0x18002a21d  xor     r8d, r8d; hToken
0x18002a220  mov     edx, 8000h; dwFlags
0x18002a225  lea     rcx, FOLDERID_SharedData; rfid
0x18002a22c  call    cs:__imp_SHGetKnownFolderPath
0x18002a233  nop     dword ptr [rax+rax+00h]
0x18002a238  mov     ebx, eax
0x18002a23a  test    eax, eax
0x18002a23c  js      short loc_18002A29B
0x18002a23e  mov     r8, [rsp+268h+ppszPath]; pszPathIn
0x18002a243  lea     r9, ?ENTERPRISE_SHARED_FOLDER@@3QBGB; "Enterprise"
0x18002a24a  mov     edx, 105h; cchPathOut
0x18002a24f  lea     rcx, [rsp+268h+pszPathOut]; pszPathOut
0x18002a254  call    cs:__imp_PathCchCombine
0x18002a25b  nop     dword ptr [rax+rax+00h]
0x18002a260  mov     ebx, eax
0x18002a262  test    eax, eax
0x18002a264  js      short loc_18002A29B
0x18002a266  mov     edx, [rdi]; SizeInWords
0x18002a268  lea     r8, [rsp+268h+pszPathOut]; Source
0x18002a26d  mov     rcx, rsi; Destination
0x18002a270  call    cs:__imp_wcscpy_s
0x18002a277  nop     dword ptr [rax+rax+00h]
0x18002a27c  test    eax, eax
0x18002a27e  jz      short loc_18002A287
0x18002a280  mov     ebx, 80004005h
0x18002a285  jmp     short loc_18002A29B
0x18002a287  lea     rcx, [rsp+268h+pszPathOut]
0x18002a28c  or      rax, 0FFFFFFFFFFFFFFFFh
0x18002a290  inc     rax
0x18002a293  cmp     [rcx+rax*2], bp
0x18002a297  jnz     short loc_18002A290
0x18002a299  mov     [rdi], eax
0x18002a29b  mov     rcx, [rsp+268h+ppszPath]; pv
0x18002a2a0  test    rcx, rcx
0x18002a2a3  jz      short loc_18002A2B1
0x18002a2a5  call    cs:__imp_CoTaskMemFree
0x18002a2ac  nop     dword ptr [rax+rax+00h]
0x18002a2b1  mov     eax, ebx
0x18002a2b3  mov     rcx, [rsp+268h+var_28]
0x18002a2bb  xor     rcx, rsp; StackCookie
0x18002a2be  call    __security_check_cookie
0x18002a2c3  mov     rbx, [rsp+268h+arg_10]
0x18002a2cb  add     rsp, 250h
0x18002a2d2  pop     rdi
0x18002a2d3  pop     rsi
0x18002a2d4  pop     rbp
0x18002a2d5  retn
```
