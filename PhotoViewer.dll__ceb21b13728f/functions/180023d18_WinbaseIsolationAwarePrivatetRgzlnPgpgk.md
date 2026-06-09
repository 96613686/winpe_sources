# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180023d18`
- end: `0x180023f17`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `511`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000f780`
- `0x180022af0`

## callees

- `0x180023d18`
- `0x18003f800`
- `0x180040264`

## import_xrefs

- `KERNEL32!QueryActCtxW` at `0x180023d8c`
- `KERNEL32!QueryActCtxW` at `0x180023d8c`
- `KERNEL32!GetModuleHandleExW` at `0x180023dd9`
- `KERNEL32!GetModuleHandleExW` at `0x180023dd9`
- `KERNEL32!GetModuleFileNameW` at `0x180023dfa`
- `KERNEL32!GetModuleFileNameW` at `0x180023dfa`
- `KERNEL32!CreateActCtxW` at `0x180023e58`
- `KERNEL32!CreateActCtxW` at `0x180023e58`
- `KERNEL32!FindActCtxSectionStringW` at `0x180023ed2`
- `KERNEL32!FindActCtxSectionStringW` at `0x180023ed2`
- `KERNEL32!ActivateActCtx` at `0x180023e97`
- `KERNEL32!ActivateActCtx` at `0x180023e97`
- `KERNEL32!LoadLibraryW` at `0x180023ee3`
- `KERNEL32!LoadLibraryW` at `0x180023ee3`
- `KERNEL32!GetLastError` at `0x180023e69`
- `KERNEL32!GetLastError` at `0x180023e69`
- `KERNEL32!DeactivateActCtx` at `0x180023ef1`
- `KERNEL32!DeactivateActCtx` at `0x18007c5de`
- `KERNEL32!DeactivateActCtx` at `0x180023ef1`
- `KERNEL32!DeactivateActCtx` at `0x18007c5de`
- `KERNEL32!SetLastError` at `0x180023e12`
- `KERNEL32!SetLastError` at `0x180023e12`

## string_xrefs

- `0x180023ec3`: `Comctl32.dll`
- `0x180023edc`: `Comctl32.dll`

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
0x180023d18  push    rbx
0x180023d1a  sub     rsp, 2F0h
0x180023d21  mov     rax, cs:__security_cookie
0x180023d28  xor     rax, rsp
0x180023d2b  mov     [rsp+2F8h+var_18], rax
0x180023d33  xorps   xmm0, xmm0
0x180023d36  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180023d3b  mov     [rsp+2F8h+Cookie], 0
0x180023d44  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x180023d4b  jnz     loc_180023EF7
0x180023d51  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180023d59  jnz     loc_180023EF7
0x180023d5f  xor     ebx, ebx
0x180023d61  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x180023d66  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180023d6f  lea     rax, [rsp+2F8h+hActCtx]
0x180023d74  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180023d79  lea     r9d, [rbx+1]; ulInfoClass
0x180023d7d  xor     r8d, r8d; pvSubInstance
0x180023d80  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180023d87  mov     ecx, 80000010h; dwFlags
0x180023d8c  call    cs:__imp_QueryActCtxW
0x180023d92  test    eax, eax
0x180023d94  jz      loc_180023EFC
0x180023d9a  mov     rax, [rsp+2F8h+hActCtx]
0x180023d9f  test    rax, rax
0x180023da2  jnz     loc_180023E88
0x180023da8  xorps   xmm0, xmm0
0x180023dab  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x180023db0  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x180023db5  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x180023dbd  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180023dc5  mov     [rsp+2F8h+phModule], rax
0x180023dca  lea     r8, [rsp+2F8h+phModule]; phModule
0x180023dcf  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180023dd6  lea     ecx, [rbx+6]; dwFlags
0x180023dd9  call    cs:__imp_GetModuleHandleExW
0x180023ddf  test    eax, eax
0x180023de1  jz      loc_180023EFC
0x180023de7  mov     r8d, 105h; nSize
0x180023ded  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180023df5  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180023dfa  call    cs:__imp_GetModuleFileNameW
0x180023e00  test    eax, eax
0x180023e02  jz      loc_180023EFC
0x180023e08  cmp     eax, 105h
0x180023e0d  jb      short loc_180023E1D
0x180023e0f  lea     ecx, [rbx+6Fh]; dwErrCode
0x180023e12  call    cs:__imp_SetLastError
0x180023e18  jmp     loc_180023EFC
0x180023e1d  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180023e25  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180023e2d  lea     rax, [rsp+2F8h+Filename]
0x180023e35  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180023e3a  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180023e46  mov     rax, [rsp+2F8h+phModule]
0x180023e4b  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180023e53  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180023e58  call    cs:__imp_CreateActCtxW
0x180023e5e  mov     [rsp+2F8h+hActCtx], rax
0x180023e63  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180023e67  jnz     short loc_180023E88
0x180023e69  call    cs:__imp_GetLastError
0x180023e6f  lea     ecx, [rax-2]
0x180023e72  cmp     ecx, 1
0x180023e75  jbe     short loc_180023E81
0x180023e77  add     eax, 0FFFFF8ECh
0x180023e7c  cmp     eax, 3
0x180023e7f  ja      short loc_180023EFC
0x180023e81  xor     eax, eax
0x180023e83  mov     [rsp+2F8h+hActCtx], rax
0x180023e88  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180023e8f  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180023e94  mov     rcx, rax; hActCtx
0x180023e97  call    cs:__imp_ActivateActCtx
0x180023e9d  test    eax, eax
0x180023e9f  jz      short loc_180023EF7
0x180023ea1  mov     ebx, 70h ; 'p'
0x180023ea6  mov     r8d, ebx; Size
0x180023ea9  xor     edx, edx; Val
0x180023eab  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180023eb0  call    memset_0
0x180023eb5  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x180023eb9  lea     rax, [rsp+2F8h+pActCtx]
0x180023ebe  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180023ec3  lea     r9, StringToFind; "Comctl32.dll"
0x180023eca  xor     edx, edx; lpExtensionGuid
0x180023ecc  lea     r8d, [rbx-6Eh]; ulSectionId
0x180023ed0  xor     ecx, ecx; dwFlags
0x180023ed2  call    cs:__imp_FindActCtxSectionStringW
0x180023ed8  test    eax, eax
0x180023eda  jz      short loc_180023EEA
0x180023edc  lea     rcx, StringToFind; "Comctl32.dll"
0x180023ee3  call    cs:__imp_LoadLibraryW
0x180023ee9  nop
0x180023eea  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180023eef  xor     ecx, ecx; dwFlags
0x180023ef1  call    cs:__imp_DeactivateActCtx
0x180023ef7  mov     ebx, 1
0x180023efc  mov     eax, ebx
0x180023efe  mov     rcx, [rsp+2F8h+var_18]
0x180023f06  xor     rcx, rsp; StackCookie
0x180023f09  call    __security_check_cookie
0x180023f0e  add     rsp, 2F0h
0x180023f15  pop     rbx
0x180023f16  retn
0x18007c5cf  push    rbp
0x18007c5d1  sub     rsp, 40h
0x18007c5d5  mov     rbp, rdx
0x18007c5d8  mov     rdx, [rbp+48h]; ulCookie
0x18007c5dc  xor     ecx, ecx; dwFlags
0x18007c5de  call    cs:__imp_DeactivateActCtx
0x18007c5e4  nop
0x18007c5e5  add     rsp, 40h
0x18007c5e9  pop     rbp
0x18007c5ea  retn
```
