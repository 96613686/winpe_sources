# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18000bea8`
- end: `0x18000c0a8`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `512`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000bb28`

## callees

- `0x18000bea8`
- `0x18000c966`
- `0x18000c990`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000bf69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000bf69`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bf8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000bf8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bfa2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000bfa2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bff9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000bff9`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000c074`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000c074`
- `KERNEL32!FindActCtxSectionStringW` at `0x18000c063`
- `KERNEL32!FindActCtxSectionStringW` at `0x18000c063`
- `KERNEL32!QueryActCtxW` at `0x18000bf1c`
- `KERNEL32!QueryActCtxW` at `0x18000bf1c`
- `KERNEL32!DeactivateActCtx` at `0x18000c082`
- `KERNEL32!DeactivateActCtx` at `0x18000cecc`
- `KERNEL32!DeactivateActCtx` at `0x18000c082`
- `KERNEL32!DeactivateActCtx` at `0x18000cecc`
- `KERNEL32!ActivateActCtx` at `0x18000c028`
- `KERNEL32!ActivateActCtx` at `0x18000c028`
- `KERNEL32!CreateActCtxW` at `0x18000bfe8`
- `KERNEL32!CreateActCtxW` at `0x18000bfe8`

## string_xrefs

- `0x18000c054`: `Comctl32.dll`
- `0x18000c06d`: `Comctl32.dll`

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
0x18000bea8  push    rbx
0x18000beaa  sub     rsp, 2F0h
0x18000beb1  mov     rax, cs:__security_cookie
0x18000beb8  xor     rax, rsp
0x18000bebb  mov     [rsp+2F8h+var_18], rax
0x18000bec3  xorps   xmm0, xmm0
0x18000bec6  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18000becb  mov     [rsp+2F8h+Cookie], 0
0x18000bed4  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000bedb  jnz     loc_18000C088
0x18000bee1  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18000bee9  jnz     loc_18000C088
0x18000beef  xor     ebx, ebx
0x18000bef1  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18000bef6  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18000beff  lea     rax, [rsp+2F8h+hActCtx]
0x18000bf04  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18000bf09  lea     r9d, [rbx+1]; ulInfoClass
0x18000bf0d  xor     r8d, r8d; pvSubInstance
0x18000bf10  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000bf17  mov     ecx, 80000010h; dwFlags
0x18000bf1c  call    cs:__imp_QueryActCtxW
0x18000bf22  test    eax, eax
0x18000bf24  jz      loc_18000C08D
0x18000bf2a  mov     rax, [rsp+2F8h+hActCtx]
0x18000bf2f  test    rax, rax
0x18000bf32  jnz     loc_18000C019
0x18000bf38  xorps   xmm0, xmm0
0x18000bf3b  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18000bf40  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18000bf45  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18000bf4d  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000bf55  mov     [rsp+2F8h+phModule], rax
0x18000bf5a  lea     r8, [rsp+2F8h+phModule]; phModule
0x18000bf5f  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18000bf66  lea     ecx, [rbx+6]; dwFlags
0x18000bf69  call    cs:__imp_GetModuleHandleExW
0x18000bf6f  test    eax, eax
0x18000bf71  jz      loc_18000C08D
0x18000bf77  mov     r8d, 105h; nSize
0x18000bf7d  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18000bf85  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18000bf8a  call    cs:__imp_GetModuleFileNameW
0x18000bf90  test    eax, eax
0x18000bf92  jz      loc_18000C08D
0x18000bf98  cmp     eax, 105h
0x18000bf9d  jb      short loc_18000BFAD
0x18000bf9f  lea     ecx, [rbx+6Fh]; dwErrCode
0x18000bfa2  call    cs:__imp_SetLastError
0x18000bfa8  jmp     loc_18000C08D
0x18000bfad  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18000bfb5  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18000bfbd  lea     rax, [rsp+2F8h+Filename]
0x18000bfc5  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18000bfca  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18000bfd6  mov     rax, [rsp+2F8h+phModule]
0x18000bfdb  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000bfe3  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18000bfe8  call    cs:__imp_CreateActCtxW
0x18000bfee  mov     [rsp+2F8h+hActCtx], rax
0x18000bff3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000bff7  jnz     short loc_18000C019
0x18000bff9  call    cs:__imp_GetLastError
0x18000bfff  lea     ecx, [rax-714h]
0x18000c005  cmp     ecx, 3
0x18000c008  jbe     short loc_18000C012
0x18000c00a  add     eax, 0FFFFFFFEh
0x18000c00d  cmp     eax, 1
0x18000c010  ja      short loc_18000C08D
0x18000c012  xor     eax, eax
0x18000c014  mov     [rsp+2F8h+hActCtx], rax
0x18000c019  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18000c020  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18000c025  mov     rcx, rax; hActCtx
0x18000c028  call    cs:__imp_ActivateActCtx
0x18000c02e  test    eax, eax
0x18000c030  jz      short loc_18000C088
0x18000c032  mov     ebx, 70h ; 'p'
0x18000c037  mov     r8d, ebx; Size
0x18000c03a  xor     edx, edx; Val
0x18000c03c  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18000c041  call    memset_0
0x18000c046  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18000c04a  lea     rax, [rsp+2F8h+pActCtx]
0x18000c04f  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18000c054  lea     r9, LibFileName; "Comctl32.dll"
0x18000c05b  xor     edx, edx; lpExtensionGuid
0x18000c05d  lea     r8d, [rbx-6Eh]; ulSectionId
0x18000c061  xor     ecx, ecx; dwFlags
0x18000c063  call    cs:__imp_FindActCtxSectionStringW
0x18000c069  test    eax, eax
0x18000c06b  jz      short loc_18000C07B
0x18000c06d  lea     rcx, LibFileName; "Comctl32.dll"
0x18000c074  call    cs:__imp_LoadLibraryW
0x18000c07a  nop
0x18000c07b  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18000c080  xor     ecx, ecx; dwFlags
0x18000c082  call    cs:__imp_DeactivateActCtx
0x18000c088  mov     ebx, 1
0x18000c08d  mov     eax, ebx
0x18000c08f  mov     rcx, [rsp+2F8h+var_18]
0x18000c097  xor     rcx, rsp; StackCookie
0x18000c09a  call    __security_check_cookie
0x18000c09f  add     rsp, 2F0h
0x18000c0a6  pop     rbx
0x18000c0a7  retn
0x18000cebd  push    rbp
0x18000cebf  sub     rsp, 40h
0x18000cec3  mov     rbp, rdx
0x18000cec6  mov     rdx, [rbp+48h]; ulCookie
0x18000ceca  xor     ecx, ecx; dwFlags
0x18000cecc  call    cs:__imp_DeactivateActCtx
0x18000ced2  nop
0x18000ced3  add     rsp, 40h
0x18000ced7  pop     rbp
0x18000ced8  retn
```
