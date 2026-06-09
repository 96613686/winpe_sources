# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x18000eb90`
- end: `0x18000ed8f`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000eaf0`

## callees

- `0x18000eb90`
- `0x18000f076`
- `0x18000f0a0`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ece1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000ece1`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ec8a`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18000ec8a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ec51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x18000ec51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000ec72`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x18000ec72`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000ed5b`
- `api-ms-win-core-libraryloader-l1-2-1!LoadLibraryW` at `0x18000ed5b`
- `KERNEL32!QueryActCtxW` at `0x18000ec04`
- `KERNEL32!QueryActCtxW` at `0x18000ec04`
- `KERNEL32!DeactivateActCtx` at `0x18000ed69`
- `KERNEL32!DeactivateActCtx` at `0x18000f74d`
- `KERNEL32!DeactivateActCtx` at `0x18000ed69`
- `KERNEL32!DeactivateActCtx` at `0x18000f74d`
- `KERNEL32!FindActCtxSectionStringW` at `0x18000ed4a`
- `KERNEL32!FindActCtxSectionStringW` at `0x18000ed4a`
- `KERNEL32!ActivateActCtx` at `0x18000ed0f`
- `KERNEL32!ActivateActCtx` at `0x18000ed0f`
- `KERNEL32!CreateActCtxW` at `0x18000ecd0`
- `KERNEL32!CreateActCtxW` at `0x18000ecd0`

## string_xrefs

- `0x18000ed3b`: `Comctl32.dll`
- `0x18000ed54`: `Comctl32.dll`

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
0x18000eb90  push    rbx
0x18000eb92  sub     rsp, 2F0h
0x18000eb99  mov     rax, cs:__security_cookie
0x18000eba0  xor     rax, rsp
0x18000eba3  mov     [rsp+2F8h+var_18], rax
0x18000ebab  xorps   xmm0, xmm0
0x18000ebae  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18000ebb3  mov     [rsp+2F8h+Cookie], 0
0x18000ebbc  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000ebc3  jnz     loc_18000ED6F
0x18000ebc9  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18000ebd1  jnz     loc_18000ED6F
0x18000ebd7  xor     ebx, ebx
0x18000ebd9  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18000ebde  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x18000ebe7  lea     rax, [rsp+2F8h+hActCtx]
0x18000ebec  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18000ebf1  lea     r9d, [rbx+1]; ulInfoClass
0x18000ebf5  xor     r8d, r8d; pvSubInstance
0x18000ebf8  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000ebff  mov     ecx, 80000010h; dwFlags
0x18000ec04  call    cs:__imp_QueryActCtxW
0x18000ec0a  test    eax, eax
0x18000ec0c  jz      loc_18000ED74
0x18000ec12  mov     rax, [rsp+2F8h+hActCtx]
0x18000ec17  test    rax, rax
0x18000ec1a  jnz     loc_18000ED00
0x18000ec20  xorps   xmm0, xmm0
0x18000ec23  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x18000ec28  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x18000ec2d  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x18000ec35  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000ec3d  mov     [rsp+2F8h+phModule], rax
0x18000ec42  lea     r8, [rsp+2F8h+phModule]; phModule
0x18000ec47  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x18000ec4e  lea     ecx, [rbx+6]; dwFlags
0x18000ec51  call    cs:__imp_GetModuleHandleExW
0x18000ec57  test    eax, eax
0x18000ec59  jz      loc_18000ED74
0x18000ec5f  mov     r8d, 105h; nSize
0x18000ec65  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x18000ec6d  mov     rcx, [rsp+2F8h+phModule]; hModule
0x18000ec72  call    cs:__imp_GetModuleFileNameW
0x18000ec78  test    eax, eax
0x18000ec7a  jz      loc_18000ED74
0x18000ec80  cmp     eax, 105h
0x18000ec85  jb      short loc_18000EC95
0x18000ec87  lea     ecx, [rbx+6Fh]; dwErrCode
0x18000ec8a  call    cs:__imp_SetLastError
0x18000ec90  jmp     loc_18000ED74
0x18000ec95  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x18000ec9d  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x18000eca5  lea     rax, [rsp+2F8h+Filename]
0x18000ecad  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18000ecb2  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18000ecbe  mov     rax, [rsp+2F8h+phModule]
0x18000ecc3  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x18000eccb  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18000ecd0  call    cs:__imp_CreateActCtxW
0x18000ecd6  mov     [rsp+2F8h+hActCtx], rax
0x18000ecdb  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000ecdf  jnz     short loc_18000ED00
0x18000ece1  call    cs:__imp_GetLastError
0x18000ece7  lea     ecx, [rax-2]
0x18000ecea  cmp     ecx, 1
0x18000eced  jbe     short loc_18000ECF9
0x18000ecef  add     eax, 0FFFFF8ECh
0x18000ecf4  cmp     eax, 3
0x18000ecf7  ja      short loc_18000ED74
0x18000ecf9  xor     eax, eax
0x18000ecfb  mov     [rsp+2F8h+hActCtx], rax
0x18000ed00  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x18000ed07  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x18000ed0c  mov     rcx, rax; hActCtx
0x18000ed0f  call    cs:__imp_ActivateActCtx
0x18000ed15  test    eax, eax
0x18000ed17  jz      short loc_18000ED6F
0x18000ed19  mov     ebx, 70h ; 'p'
0x18000ed1e  mov     r8d, ebx; Size
0x18000ed21  xor     edx, edx; Val
0x18000ed23  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x18000ed28  call    memset_0
0x18000ed2d  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18000ed31  lea     rax, [rsp+2F8h+pActCtx]
0x18000ed36  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x18000ed3b  lea     r9, LibFileName; "Comctl32.dll"
0x18000ed42  xor     edx, edx; lpExtensionGuid
0x18000ed44  lea     r8d, [rbx-6Eh]; ulSectionId
0x18000ed48  xor     ecx, ecx; dwFlags
0x18000ed4a  call    cs:__imp_FindActCtxSectionStringW
0x18000ed50  test    eax, eax
0x18000ed52  jz      short loc_18000ED62
0x18000ed54  lea     rcx, LibFileName; "Comctl32.dll"
0x18000ed5b  call    cs:__imp_LoadLibraryW
0x18000ed61  nop
0x18000ed62  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x18000ed67  xor     ecx, ecx; dwFlags
0x18000ed69  call    cs:__imp_DeactivateActCtx
0x18000ed6f  mov     ebx, 1
0x18000ed74  mov     eax, ebx
0x18000ed76  mov     rcx, [rsp+2F8h+var_18]
0x18000ed7e  xor     rcx, rsp; StackCookie
0x18000ed81  call    __security_check_cookie
0x18000ed86  add     rsp, 2F0h
0x18000ed8d  pop     rbx
0x18000ed8e  retn
0x18000f73e  push    rbp
0x18000f740  sub     rsp, 40h
0x18000f744  mov     rbp, rdx
0x18000f747  mov     rdx, [rbp+48h]; ulCookie
0x18000f74b  xor     ecx, ecx; dwFlags
0x18000f74d  call    cs:__imp_DeactivateActCtx
0x18000f753  nop
0x18000f754  add     rsp, 40h
0x18000f758  pop     rbp
0x18000f759  retn
```
