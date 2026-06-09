# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18001e668`
- end: `0x18001e868`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001e5dc`

## callees

- `0x18001e668`
- `0x180050db0`
- `0x1800517cc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e74a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18001e74a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001e729`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18001e729`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e762`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18001e762`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7b9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18001e7b9`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e842`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800aa5ff`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x18001e842`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800aa5ff`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18001e7a8`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x18001e7a8`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x18001e6dc`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x18001e6dc`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18001e823`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x18001e823`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18001e7e8`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x18001e7e8`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001e834`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18001e834`

## string_xrefs

- `0x18001e814`: `Comctl32.dll`
- `0x18001e82d`: `Comctl32.dll`

## pseudocode

```c
__int64 WinbaseIsolationAwarePrivatetRgzlnPgpgk()
{
  unsigned int v0; // ebx
  HANDLE ActCtxW; // rax
  DWORD ModuleFileNameW; // eax
  DWORD LastError; // eax
  HMODULE phModule; // [rsp+40h] [rbp-2B8h] BYREF
  ULONG_PTR Cookie; // [rsp+48h] [rbp-2B0h] BYREF
  HANDLE hActCtx[2]; // [rsp+50h] [rbp-2A8h] BYREF
  struct tagACTCTX_SECTION_KEYED_DATA pActCtx; // [rsp+60h] [rbp-298h] BYREF
  WCHAR Filename[264]; // [rsp+D0h] [rbp-228h] BYREF

  *(_OWORD *)hActCtx = 0;
  Cookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || WinbaseIsolationAwarePrivateT_UnPgpgk != (HANDLE)-1LL )
    return 1;
  v0 = 0;
  if ( QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, hActCtx, 0x10u, 0) )
  {
    ActCtxW = hActCtx[0];
    if ( hActCtx[0] )
      goto LABEL_13;
    memset(&pActCtx, 0, 56);
    phModule = 0;
    if ( GetModuleHandleExW(6u, (LPCWSTR)&WinbaseIsolationAwarePrivateT_UnPgpgk, &phModule) )
    {
      ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x105u);
      if ( ModuleFileNameW )
      {
        if ( ModuleFileNameW >= 0x105 )
        {
          SetLastError(0x6Fu);
          return v0;
        }
        pActCtx.cbSize = 56;
        pActCtx.ulDataFormatVersion = 136;
        pActCtx.lpData = Filename;
        *(_QWORD *)&pActCtx.ulSectionGlobalDataLength = 3;
        *(_QWORD *)&pActCtx.ulSectionTotalLength = phModule;
        ActCtxW = CreateActCtxW((PCACTCTXW)&pActCtx);
        hActCtx[0] = ActCtxW;
        if ( ActCtxW != (HANDLE)-1LL )
          goto LABEL_13;
        LastError = GetLastError();
        if ( LastError - 1812 <= 3 || LastError - 2 <= 1 )
        {
          ActCtxW = 0;
          hActCtx[0] = 0;
LABEL_13:
          WinbaseIsolationAwarePrivateT_UnPgpgk = ActCtxW;
          if ( ActivateActCtx(ActCtxW, &Cookie) )
          {
            memset_0(&pActCtx, 0, sizeof(pActCtx));
            pActCtx.cbSize = 112;
            if ( FindActCtxSectionStringW(0, 0, 2u, L"Comctl32.dll", &pActCtx) )
              LoadLibraryW(L"Comctl32.dll");
            DeactivateActCtx(0, Cookie);
          }
          return 1;
        }
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x18001e668  push    rbx
0x18001e66a  sub     rsp, 2F0h
0x18001e671  mov     rax, cs:__security_cookie
0x18001e678  xor     rax, rsp
0x18001e67b  mov     [rsp+2F8h+var_18], rax
0x18001e683  xorps   xmm0, xmm0
0x18001e686  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18001e68b  mov     [rsp+2F8h+Cookie], 0
0x18001e694  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18001e69b  jnz     loc_18001E848
0x18001e6a1  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18001e6a9  jnz     loc_18001E848
0x18001e6af  xor     ebx, ebx
0x18001e6b1  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18001e6b6  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18001e6bf  lea     rax, [rsp+2F8h+hActCtx]
0x18001e6c4  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18001e6c9  lea     r9d, [rbx+1]; ulInfoClass
0x18001e6cd  xor     r8d, r8d; pvSubInstance
0x18001e6d0  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18001e6d7  mov     ecx, 80000010h; dwFlags
0x18001e6dc  call    cs:__imp_QueryActCtxW
0x18001e6e2  test    eax, eax
0x18001e6e4  jz      loc_18001E84D
0x18001e6ea  mov     rax, [rsp+2F8h+hActCtx]
0x18001e6ef  test    rax, rax
0x18001e6f2  jnz     loc_18001E7D9
0x18001e6f8  xorps   xmm0, xmm0
0x18001e6fb  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18001e700  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18001e705  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18001e70d  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18001e715  mov     [rsp+2F8h+phModule], rax
0x18001e71a  lea     r8, [rsp+2F8h+phModule]; phModule
0x18001e71f  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18001e726  lea     ecx, [rbx+6]; dwFlags
0x18001e729  call    cs:__imp_GetModuleHandleExW
0x18001e72f  test    eax, eax
0x18001e731  jz      loc_18001E84D
0x18001e737  mov     r8d, 105h; nSize
0x18001e73d  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18001e745  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18001e74a  call    cs:__imp_GetModuleFileNameW
0x18001e750  test    eax, eax
0x18001e752  jz      loc_18001E84D
0x18001e758  cmp     eax, 105h
0x18001e75d  jb      short loc_18001E76D
0x18001e75f  lea     ecx, [rbx+6Fh]; dwErrCode
0x18001e762  call    cs:__imp_SetLastError
0x18001e768  jmp     loc_18001E84D
0x18001e76d  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18001e775  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18001e77d  lea     rax, [rsp+2F8h+Filename]
0x18001e785  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18001e78a  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18001e796  mov     rax, [rsp+2F8h+phModule]
0x18001e79b  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18001e7a3  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18001e7a8  call    cs:__imp_CreateActCtxW
0x18001e7ae  mov     [rsp+2F8h+hActCtx], rax
0x18001e7b3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18001e7b7  jnz     short loc_18001E7D9
0x18001e7b9  call    cs:__imp_GetLastError
0x18001e7bf  lea     ecx, [rax-714h]
0x18001e7c5  cmp     ecx, 3
0x18001e7c8  jbe     short loc_18001E7D2
0x18001e7ca  add     eax, 0FFFFFFFEh
0x18001e7cd  cmp     eax, 1
0x18001e7d0  ja      short loc_18001E84D
0x18001e7d2  xor     eax, eax
0x18001e7d4  mov     [rsp+2F8h+hActCtx], rax
0x18001e7d9  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18001e7e0  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18001e7e5  mov     rcx, rax; hActCtx
0x18001e7e8  call    cs:__imp_ActivateActCtx
0x18001e7ee  test    eax, eax
0x18001e7f0  jz      short loc_18001E848
0x18001e7f2  mov     ebx, 70h ; 'p'
0x18001e7f7  mov     r8d, ebx; Size
0x18001e7fa  xor     edx, edx; Val
0x18001e7fc  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18001e801  call    memset_0
0x18001e806  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18001e80a  lea     rax, [rsp+2F8h+pActCtx]
0x18001e80f  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18001e814  lea     r9, LibFileName; "Comctl32.dll"
0x18001e81b  xor     edx, edx; lpExtensionGuid
0x18001e81d  lea     r8d, [rbx-6Eh]; ulSectionId
0x18001e821  xor     ecx, ecx; dwFlags
0x18001e823  call    cs:__imp_FindActCtxSectionStringW
0x18001e829  test    eax, eax
0x18001e82b  jz      short loc_18001E83B
0x18001e82d  lea     rcx, LibFileName; "Comctl32.dll"
0x18001e834  call    cs:__imp_LoadLibraryW
0x18001e83a  nop
0x18001e83b  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18001e840  xor     ecx, ecx; dwFlags
0x18001e842  call    cs:__imp_DeactivateActCtx
0x18001e848  mov     ebx, 1
0x18001e84d  mov     eax, ebx
0x18001e84f  mov     rcx, [rsp+2F8h+var_18]
0x18001e857  xor     rcx, rsp; StackCookie
0x18001e85a  call    __security_check_cookie
0x18001e85f  add     rsp, 2F0h
0x18001e866  pop     rbx
0x18001e867  retn
0x1800aa5f0  push    rbp
0x1800aa5f2  sub     rsp, 40h
0x1800aa5f6  mov     rbp, rdx
0x1800aa5f9  mov     rdx, [rbp+48h]; ulCookie
0x1800aa5fd  xor     ecx, ecx; dwFlags
0x1800aa5ff  call    cs:__imp_DeactivateActCtx
0x1800aa605  nop
0x1800aa606  add     rsp, 40h
0x1800aa60a  pop     rbp
0x1800aa60b  retn
```
