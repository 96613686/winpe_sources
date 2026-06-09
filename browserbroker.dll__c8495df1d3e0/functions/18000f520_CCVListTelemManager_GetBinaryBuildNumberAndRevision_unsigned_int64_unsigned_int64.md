# CCVListTelemManager::GetBinaryBuildNumberAndRevision(unsigned __int64 *,unsigned __int64 *)

- ea: `0x18000f520`
- end: `0x18000f704`
- name: `?GetBinaryBuildNumberAndRevision@CCVListTelemManager@@CAJPEA_K0@Z`
- size: `484`
- prototype: `__int64 __fastcall(unsigned __int64 *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, loader_planting, broker_com_uri`

## callers

- `0x18000f1a4`

## callees

- `0x180002ce0`
- `0x180002d04`
- `0x180003170`
- `0x1800037ac`
- `0x18000d17c`
- `0x18000f520`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6a1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f588`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000f6a1`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000f5fe`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x18000f5fe`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000f57c`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemDirectoryW` at `0x18000f57c`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18000f615`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoSizeW` at `0x18000f615`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18000f63e`
- `api-ms-win-core-version-l1-1-1!GetFileVersionInfoW` at `0x18000f63e`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000f669`
- `api-ms-win-core-version-l1-1-0!VerQueryValueW` at `0x18000f669`

## string_xrefs

- `0x18000f550`: `edgehtml.dll`
- `0x18000f564`: `urlmon.dll`

## pseudocode

```c
__int64 __fastcall CCVListTelemManager::GetBinaryBuildNumberAndRevision(unsigned __int64 *a1, unsigned __int64 *a2)
{
  signed int v3; // eax
  int v4; // ebx
  unsigned __int16 v5; // di
  unsigned __int16 v6; // r15
  unsigned int i; // r14d
  DWORD FileVersionInfoSizeW; // eax
  DWORD v9; // r12d
  void *v10; // rsi
  unsigned __int16 v11; // r12
  signed int LastError; // eax
  unsigned __int64 *v13; // rcx
  unsigned int puLen; // [rsp+20h] [rbp-E0h] BYREF
  LPVOID lpBuffer; // [rsp+28h] [rbp-D8h] BYREF
  unsigned __int64 *v17; // [rsp+30h] [rbp-D0h]
  PCWSTR pszMore[3]; // [rsp+38h] [rbp-C8h]
  WCHAR pszPath[264]; // [rsp+50h] [rbp-B0h] BYREF
  WCHAR Buffer[264]; // [rsp+260h] [rbp+160h] BYREF

  v17 = a2;
  pszMore[0] = L"edgehtml.dll";
  pszMore[1] = L"urlmon.dll";
  if ( GetSystemDirectoryW(Buffer, 0x104u) )
  {
    v4 = 0;
    v5 = 0;
    v6 = 0;
    for ( i = 0; ; ++i )
    {
      if ( i >= 2 )
      {
        v13 = v17;
        *a1 = v5;
        *v13 = v6;
        return (unsigned int)v4;
      }
      memset_0(pszPath, 0, 0x208u);
      v4 = StringCchCopyW(pszPath, 0x104u, Buffer);
      if ( v4 < 0 )
        return (unsigned int)v4;
      v4 = PathCchAppend(pszPath, 0x104u, pszMore[i]);
      if ( v4 < 0 )
        return (unsigned int)v4;
      FileVersionInfoSizeW = GetFileVersionInfoSizeW(pszPath, 0);
      v9 = FileVersionInfoSizeW;
      if ( !FileVersionInfoSizeW )
        goto LABEL_2;
      v10 = operator new[](FileVersionInfoSizeW);
      if ( !GetFileVersionInfoW(pszPath, 0, v9, v10) )
        break;
      puLen = 0;
      lpBuffer = 0;
      if ( !VerQueryValueW(v10, L"\\", &lpBuffer, &puLen) )
        break;
      v11 = *((_WORD *)lpBuffer + 6);
      if ( !v6 )
        v6 = *((_WORD *)lpBuffer + 7);
      operator delete(v10);
      if ( v11 > v5 )
        v5 = v11;
    }
    LastError = GetLastError();
    v4 = LastError;
    if ( LastError > 0 )
      v4 = (unsigned __int16)LastError | 0x80070000;
    if ( v10 )
      operator delete(v10);
  }
  else
  {
LABEL_2:
    v3 = GetLastError();
    v4 = v3;
    if ( v3 > 0 )
      return (unsigned __int16)v3 | 0x80070000;
  }
  return (unsigned int)v4;
}

```

## disassembly

```asm
0x18000f520  mov     [rsp-8+arg_10], rbx
0x18000f525  push    rbp
0x18000f526  push    rsi
0x18000f527  push    rdi
0x18000f528  push    r12
0x18000f52a  push    r13
0x18000f52c  push    r14
0x18000f52e  push    r15
0x18000f530  lea     rbp, [rsp-380h]
0x18000f538  sub     rsp, 480h
0x18000f53f  mov     rax, cs:__security_cookie
0x18000f546  xor     rax, rsp
0x18000f549  mov     [rbp+3B0h+var_40], rax
0x18000f550  lea     rax, aEdgehtmlDll; "edgehtml.dll"
0x18000f557  mov     [rsp+4B0h+var_480], rdx
0x18000f55c  mov     [rsp+4B0h+pszMore], rax
0x18000f561  mov     r13, rcx
0x18000f564  lea     rax, aUrlmonDll_0; "urlmon.dll"
0x18000f56b  mov     edx, 104h; uSize
0x18000f570  lea     rcx, [rbp+3B0h+Buffer]; lpBuffer
0x18000f577  mov     [rsp+4B0h+var_470], rax
0x18000f57c  call    cs:__imp_GetSystemDirectoryW
0x18000f582  xor     esi, esi
0x18000f584  test    eax, eax
0x18000f586  jnz     short loc_18000F5A6
0x18000f588  call    cs:__imp_GetLastError
0x18000f58e  mov     ebx, eax
0x18000f590  test    eax, eax
0x18000f592  jle     loc_18000F6D8
0x18000f598  movzx   ebx, ax
0x18000f59b  or      ebx, 80070000h
0x18000f5a1  jmp     loc_18000F6D8
0x18000f5a6  mov     ebx, esi
0x18000f5a8  mov     edi, esi
0x18000f5aa  mov     r15d, esi
0x18000f5ad  mov     r14d, esi
0x18000f5b0  cmp     r14d, 2
0x18000f5b4  jnb     loc_18000F6C5
0x18000f5ba  xor     edx, edx; Val
0x18000f5bc  lea     rcx, [rsp+4B0h+pszPath]; void *
0x18000f5c1  mov     r8d, 208h; Size
0x18000f5c7  call    memset_0
0x18000f5cc  lea     r8, [rbp+3B0h+Buffer]; unsigned __int16 *
0x18000f5d3  mov     edx, 104h; unsigned __int64
0x18000f5d8  lea     rcx, [rsp+4B0h+pszPath]; unsigned __int16 *
0x18000f5dd  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18000f5e2  mov     ebx, eax
0x18000f5e4  test    eax, eax
0x18000f5e6  js      loc_18000F6D8
0x18000f5ec  mov     r8d, r14d
0x18000f5ef  lea     rcx, [rsp+4B0h+pszPath]; pszPath
0x18000f5f4  mov     edx, 104h; cchPath
0x18000f5f9  mov     r8, [rsp+r8*8+4B0h+pszMore]; pszMore
0x18000f5fe  call    cs:__imp_PathCchAppend
0x18000f604  mov     ebx, eax
0x18000f606  test    eax, eax
0x18000f608  js      loc_18000F6D8
0x18000f60e  xor     edx, edx; lpdwHandle
0x18000f610  lea     rcx, [rsp+4B0h+pszPath]; lptstrFilename
0x18000f615  call    cs:__imp_GetFileVersionInfoSizeW
0x18000f61b  mov     r12d, eax
0x18000f61e  test    eax, eax
0x18000f620  jz      loc_18000F588
0x18000f626  mov     ecx, r12d; unsigned __int64
0x18000f629  call    ??_U@YAPEAX_K@Z; operator new[](unsigned __int64)
0x18000f62e  mov     r9, rax; lpData
0x18000f631  lea     rcx, [rsp+4B0h+pszPath]; lptstrFilename
0x18000f636  mov     r8d, r12d; dwLen
0x18000f639  xor     edx, edx; dwHandle
0x18000f63b  mov     rsi, rax
0x18000f63e  call    cs:__imp_GetFileVersionInfoW
0x18000f644  xor     r12d, r12d
0x18000f647  test    eax, eax
0x18000f649  jz      short loc_18000F6A1
0x18000f64b  lea     r9, [rsp+4B0h+puLen]; puLen
0x18000f650  mov     [rsp+4B0h+puLen], r12d
0x18000f655  lea     r8, [rsp+4B0h+lpBuffer]; lplpBuffer
0x18000f65a  mov     [rsp+4B0h+lpBuffer], r12
0x18000f65f  lea     rdx, SubBlock; "\\"
0x18000f666  mov     rcx, rsi; pBlock
0x18000f669  call    cs:__imp_VerQueryValueW
0x18000f66f  test    eax, eax
0x18000f671  jz      short loc_18000F6A1
0x18000f673  mov     rax, [rsp+4B0h+lpBuffer]
0x18000f678  movzx   r12d, word ptr [rax+0Ch]
0x18000f67d  test    r15w, r15w
0x18000f681  jnz     short loc_18000F688
0x18000f683  movzx   r15d, word ptr [rax+0Eh]
0x18000f688  mov     rcx, rsi; Block
0x18000f68b  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f690  cmp     r12w, di
0x18000f694  cmova   di, r12w
0x18000f699  inc     r14d
0x18000f69c  jmp     loc_18000F5B0
0x18000f6a1  call    cs:__imp_GetLastError
0x18000f6a7  mov     ebx, eax
0x18000f6a9  test    eax, eax
0x18000f6ab  jle     short loc_18000F6B6
0x18000f6ad  movzx   ebx, ax
0x18000f6b0  or      ebx, 80070000h
0x18000f6b6  test    rsi, rsi
0x18000f6b9  jz      short loc_18000F6D8
0x18000f6bb  mov     rcx, rsi; Block
0x18000f6be  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x18000f6c3  jmp     short loc_18000F6D8
0x18000f6c5  mov     rcx, [rsp+4B0h+var_480]
0x18000f6ca  movzx   eax, di
0x18000f6cd  mov     [r13+0], rax
0x18000f6d1  movzx   eax, r15w
0x18000f6d5  mov     [rcx], rax
0x18000f6d8  mov     eax, ebx
0x18000f6da  mov     rcx, [rbp+3B0h+var_40]
0x18000f6e1  xor     rcx, rsp; StackCookie
0x18000f6e4  call    __security_check_cookie
0x18000f6e9  mov     rbx, [rsp+4B0h+arg_10]
0x18000f6f1  add     rsp, 480h
0x18000f6f8  pop     r15
0x18000f6fa  pop     r14
0x18000f6fc  pop     r13
0x18000f6fe  pop     r12
0x18000f700  pop     rdi
0x18000f701  pop     rsi
0x18000f702  pop     rbp
0x18000f703  retn
```
