# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180006e88`
- end: `0x180007088`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006dfc`

## callees

- `0x180006e88`
- `0x18000a9a6`
- `0x18000a9d0`

## import_xrefs

- `KERNEL32!CreateActCtxW` at `0x180006fc8`
- `KERNEL32!CreateActCtxW` at `0x180006fc8`
- `KERNEL32!ActivateActCtx` at `0x180007008`
- `KERNEL32!ActivateActCtx` at `0x180007008`
- `KERNEL32!SetLastError` at `0x180006f82`
- `KERNEL32!SetLastError` at `0x180006f82`
- `KERNEL32!GetModuleHandleExW` at `0x180006f49`
- `KERNEL32!GetModuleHandleExW` at `0x180006f49`
- `KERNEL32!GetModuleFileNameW` at `0x180006f6a`
- `KERNEL32!GetModuleFileNameW` at `0x180006f6a`
- `KERNEL32!FindActCtxSectionStringW` at `0x180007043`
- `KERNEL32!FindActCtxSectionStringW` at `0x180007043`
- `KERNEL32!DeactivateActCtx` at `0x180007062`
- `KERNEL32!DeactivateActCtx` at `0x18000aff8`
- `KERNEL32!DeactivateActCtx` at `0x180007062`
- `KERNEL32!DeactivateActCtx` at `0x18000aff8`
- `KERNEL32!QueryActCtxW` at `0x180006efc`
- `KERNEL32!QueryActCtxW` at `0x180006efc`
- `KERNEL32!GetLastError` at `0x180006fd9`
- `KERNEL32!GetLastError` at `0x180006fd9`
- `KERNEL32!LoadLibraryW` at `0x180007054`
- `KERNEL32!LoadLibraryW` at `0x180007054`

## string_xrefs

- `0x180007034`: `Comctl32.dll`
- `0x18000704d`: `Comctl32.dll`

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
0x180006e88  push    rbx
0x180006e8a  sub     rsp, 2F0h
0x180006e91  mov     rax, cs:__security_cookie
0x180006e98  xor     rax, rsp
0x180006e9b  mov     [rsp+2F8h+var_18], rax
0x180006ea3  xorps   xmm0, xmm0
0x180006ea6  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180006eab  mov     [rsp+2F8h+Cookie], 0
0x180006eb4  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180006ebb  jnz     loc_180007068
0x180006ec1  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180006ec9  jnz     loc_180007068
0x180006ecf  xor     ebx, ebx
0x180006ed1  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x180006ed6  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180006edf  lea     rax, [rsp+2F8h+hActCtx]
0x180006ee4  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180006ee9  lea     r9d, [rbx+1]; ulInfoClass
0x180006eed  xor     r8d, r8d; pvSubInstance
0x180006ef0  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180006ef7  mov     ecx, 80000010h; dwFlags
0x180006efc  call    cs:__imp_QueryActCtxW
0x180006f02  test    eax, eax
0x180006f04  jz      loc_18000706D
0x180006f0a  mov     rax, [rsp+2F8h+hActCtx]
0x180006f0f  test    rax, rax
0x180006f12  jnz     loc_180006FF9
0x180006f18  xorps   xmm0, xmm0
0x180006f1b  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x180006f20  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x180006f25  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x180006f2d  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180006f35  mov     [rsp+2F8h+phModule], rax
0x180006f3a  lea     r8, [rsp+2F8h+phModule]; phModule
0x180006f3f  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180006f46  lea     ecx, [rbx+6]; dwFlags
0x180006f49  call    cs:__imp_GetModuleHandleExW
0x180006f4f  test    eax, eax
0x180006f51  jz      loc_18000706D
0x180006f57  mov     r8d, 105h; nSize
0x180006f5d  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180006f65  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180006f6a  call    cs:__imp_GetModuleFileNameW
0x180006f70  test    eax, eax
0x180006f72  jz      loc_18000706D
0x180006f78  cmp     eax, 105h
0x180006f7d  jb      short loc_180006F8D
0x180006f7f  lea     ecx, [rbx+6Fh]; dwErrCode
0x180006f82  call    cs:__imp_SetLastError
0x180006f88  jmp     loc_18000706D
0x180006f8d  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180006f95  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180006f9d  lea     rax, [rsp+2F8h+Filename]
0x180006fa5  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180006faa  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180006fb6  mov     rax, [rsp+2F8h+phModule]
0x180006fbb  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180006fc3  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180006fc8  call    cs:__imp_CreateActCtxW
0x180006fce  mov     [rsp+2F8h+hActCtx], rax
0x180006fd3  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180006fd7  jnz     short loc_180006FF9
0x180006fd9  call    cs:__imp_GetLastError
0x180006fdf  lea     ecx, [rax-714h]
0x180006fe5  cmp     ecx, 3
0x180006fe8  jbe     short loc_180006FF2
0x180006fea  add     eax, 0FFFFFFFEh
0x180006fed  cmp     eax, 1
0x180006ff0  ja      short loc_18000706D
0x180006ff2  xor     eax, eax
0x180006ff4  mov     [rsp+2F8h+hActCtx], rax
0x180006ff9  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180007000  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180007005  mov     rcx, rax; hActCtx
0x180007008  call    cs:__imp_ActivateActCtx
0x18000700e  test    eax, eax
0x180007010  jz      short loc_180007068
0x180007012  mov     ebx, 70h ; 'p'
0x180007017  mov     r8d, ebx; Size
0x18000701a  xor     edx, edx; Val
0x18000701c  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180007021  call    memset_0
0x180007026  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18000702a  lea     rax, [rsp+2F8h+pActCtx]
0x18000702f  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180007034  lea     r9, LibFileName; "Comctl32.dll"
0x18000703b  xor     edx, edx; lpExtensionGuid
0x18000703d  lea     r8d, [rbx-6Eh]; ulSectionId
0x180007041  xor     ecx, ecx; dwFlags
0x180007043  call    cs:__imp_FindActCtxSectionStringW
0x180007049  test    eax, eax
0x18000704b  jz      short loc_18000705B
0x18000704d  lea     rcx, LibFileName; "Comctl32.dll"
0x180007054  call    cs:__imp_LoadLibraryW
0x18000705a  nop
0x18000705b  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180007060  xor     ecx, ecx; dwFlags
0x180007062  call    cs:__imp_DeactivateActCtx
0x180007068  mov     ebx, 1
0x18000706d  mov     eax, ebx
0x18000706f  mov     rcx, [rsp+2F8h+var_18]
0x180007077  xor     rcx, rsp; StackCookie
0x18000707a  call    __security_check_cookie
0x18000707f  add     rsp, 2F0h
0x180007086  pop     rbx
0x180007087  retn
0x18000afe9  push    rbp
0x18000afeb  sub     rsp, 40h
0x18000afef  mov     rbp, rdx
0x18000aff2  mov     rdx, [rbp+48h]; ulCookie
0x18000aff6  xor     ecx, ecx; dwFlags
0x18000aff8  call    cs:__imp_DeactivateActCtx
0x18000affe  nop
0x18000afff  add     rsp, 40h
0x18000b003  pop     rbp
0x18000b004  retn
```
