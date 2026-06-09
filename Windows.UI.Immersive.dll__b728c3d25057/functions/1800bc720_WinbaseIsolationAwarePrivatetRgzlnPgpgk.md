# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x1800bc720`
- end: `0x1800bc91f`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800bc628`

## callees

- `0x180050ba0`
- `0x180051524`
- `0x1800bc720`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800bc802`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800bc802`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800bc7e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800bc7e1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bc81a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800bc81a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc871`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800bc871`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800bc8eb`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x1800bc8eb`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800bc860`
- `api-ms-win-core-sidebyside-l1-1-0!CreateActCtxW` at `0x1800bc860`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800bc8f9`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800e3ca6`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800bc8f9`
- `api-ms-win-core-sidebyside-l1-1-0!DeactivateActCtx` at `0x1800e3ca6`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x1800bc8da`
- `api-ms-win-core-sidebyside-l1-1-0!FindActCtxSectionStringW` at `0x1800bc8da`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800bc794`
- `api-ms-win-core-sidebyside-l1-1-0!QueryActCtxW` at `0x1800bc794`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800bc89f`
- `api-ms-win-core-sidebyside-l1-1-0!ActivateActCtx` at `0x1800bc89f`

## string_xrefs

- `0x1800bc8cb`: `Comctl32.dll`
- `0x1800bc8e4`: `Comctl32.dll`

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
        if ( LastError - 2 <= 1 || LastError - 1812 <= 3 )
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
0x1800bc720  push    rbx
0x1800bc722  sub     rsp, 2F0h
0x1800bc729  mov     rax, cs:__security_cookie
0x1800bc730  xor     rax, rsp
0x1800bc733  mov     [rsp+2F8h+var_18], rax
0x1800bc73b  xorps   xmm0, xmm0
0x1800bc73e  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x1800bc743  mov     [rsp+2F8h+Cookie], 0
0x1800bc74c  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x1800bc753  jnz     loc_1800BC8FF
0x1800bc759  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x1800bc761  jnz     loc_1800BC8FF
0x1800bc767  xor     ebx, ebx
0x1800bc769  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x1800bc76e  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x1800bc777  lea     rax, [rsp+2F8h+hActCtx]
0x1800bc77c  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x1800bc781  lea     r9d, [rbx+1]; ulInfoClass
0x1800bc785  xor     r8d, r8d; pvSubInstance
0x1800bc788  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x1800bc78f  mov     ecx, 80000010h; dwFlags
0x1800bc794  call    cs:__imp_QueryActCtxW
0x1800bc79a  test    eax, eax
0x1800bc79c  jz      loc_1800BC904
0x1800bc7a2  mov     rax, [rsp+2F8h+hActCtx]
0x1800bc7a7  test    rax, rax
0x1800bc7aa  jnz     loc_1800BC890
0x1800bc7b0  xorps   xmm0, xmm0
0x1800bc7b3  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x1800bc7b8  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x1800bc7bd  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x1800bc7c5  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800bc7cd  mov     [rsp+2F8h+phModule], rax
0x1800bc7d2  lea     r8, [rsp+2F8h+phModule]; phModule
0x1800bc7d7  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x1800bc7de  lea     ecx, [rbx+6]; dwFlags
0x1800bc7e1  call    cs:__imp_GetModuleHandleExW
0x1800bc7e7  test    eax, eax
0x1800bc7e9  jz      loc_1800BC904
0x1800bc7ef  mov     r8d, 105h; nSize
0x1800bc7f5  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x1800bc7fd  mov     rcx, [rsp+2F8h+phModule]; hModule
0x1800bc802  call    cs:__imp_GetModuleFileNameW
0x1800bc808  test    eax, eax
0x1800bc80a  jz      loc_1800BC904
0x1800bc810  cmp     eax, 105h
0x1800bc815  jb      short loc_1800BC825
0x1800bc817  lea     ecx, [rbx+6Fh]; dwErrCode
0x1800bc81a  call    cs:__imp_SetLastError
0x1800bc820  jmp     loc_1800BC904
0x1800bc825  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x1800bc82d  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x1800bc835  lea     rax, [rsp+2F8h+Filename]
0x1800bc83d  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x1800bc842  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x1800bc84e  mov     rax, [rsp+2F8h+phModule]
0x1800bc853  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800bc85b  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x1800bc860  call    cs:__imp_CreateActCtxW
0x1800bc866  mov     [rsp+2F8h+hActCtx], rax
0x1800bc86b  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x1800bc86f  jnz     short loc_1800BC890
0x1800bc871  call    cs:__imp_GetLastError
0x1800bc877  lea     ecx, [rax-2]
0x1800bc87a  cmp     ecx, 1
0x1800bc87d  jbe     short loc_1800BC889
0x1800bc87f  add     eax, 0FFFFF8ECh
0x1800bc884  cmp     eax, 3
0x1800bc887  ja      short loc_1800BC904
0x1800bc889  xor     eax, eax
0x1800bc88b  mov     [rsp+2F8h+hActCtx], rax
0x1800bc890  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x1800bc897  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x1800bc89c  mov     rcx, rax; hActCtx
0x1800bc89f  call    cs:__imp_ActivateActCtx
0x1800bc8a5  test    eax, eax
0x1800bc8a7  jz      short loc_1800BC8FF
0x1800bc8a9  mov     ebx, 70h ; 'p'
0x1800bc8ae  mov     r8d, ebx; Size
0x1800bc8b1  xor     edx, edx; Val
0x1800bc8b3  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x1800bc8b8  call    memset_0
0x1800bc8bd  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x1800bc8c1  lea     rax, [rsp+2F8h+pActCtx]
0x1800bc8c6  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x1800bc8cb  lea     r9, StringToFind; "Comctl32.dll"
0x1800bc8d2  xor     edx, edx; lpExtensionGuid
0x1800bc8d4  lea     r8d, [rbx-6Eh]; ulSectionId
0x1800bc8d8  xor     ecx, ecx; dwFlags
0x1800bc8da  call    cs:__imp_FindActCtxSectionStringW
0x1800bc8e0  test    eax, eax
0x1800bc8e2  jz      short loc_1800BC8F2
0x1800bc8e4  lea     rcx, StringToFind; "Comctl32.dll"
0x1800bc8eb  call    cs:__imp_LoadLibraryW
0x1800bc8f1  nop
0x1800bc8f2  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x1800bc8f7  xor     ecx, ecx; dwFlags
0x1800bc8f9  call    cs:__imp_DeactivateActCtx
0x1800bc8ff  mov     ebx, 1
0x1800bc904  mov     eax, ebx
0x1800bc906  mov     rcx, [rsp+2F8h+var_18]
0x1800bc90e  xor     rcx, rsp; StackCookie
0x1800bc911  call    __security_check_cookie
0x1800bc916  add     rsp, 2F0h
0x1800bc91d  pop     rbx
0x1800bc91e  retn
0x1800e3c97  push    rbp
0x1800e3c99  sub     rsp, 40h
0x1800e3c9d  mov     rbp, rdx
0x1800e3ca0  mov     rdx, [rbp+48h]; ulCookie
0x1800e3ca4  xor     ecx, ecx; dwFlags
0x1800e3ca6  call    cs:__imp_DeactivateActCtx
0x1800e3cac  nop
0x1800e3cad  add     rsp, 40h
0x1800e3cb1  pop     rbp
0x1800e3cb2  retn
```
