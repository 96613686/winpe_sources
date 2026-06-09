# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x180005e30`
- end: `0x180006020`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `496`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006020`

## callees

- `0x180005e30`
- `0x18056bd00`
- `0x18056d14c`

## import_xrefs

- `KERNEL32!CreateActCtxW` at `0x180005f5f`
- `KERNEL32!CreateActCtxW` at `0x180005f5f`
- `KERNEL32!ActivateActCtx` at `0x180005fa0`
- `KERNEL32!ActivateActCtx` at `0x180005fa0`
- `KERNEL32!SetLastError` at `0x180005f19`
- `KERNEL32!SetLastError` at `0x180005f19`
- `KERNEL32!GetModuleHandleExW` at `0x180005ee0`
- `KERNEL32!GetModuleHandleExW` at `0x180005ee0`
- `KERNEL32!GetModuleFileNameW` at `0x180005f01`
- `KERNEL32!GetModuleFileNameW` at `0x180005f01`
- `KERNEL32!FindActCtxSectionStringW` at `0x180005fdb`
- `KERNEL32!FindActCtxSectionStringW` at `0x180005fdb`
- `KERNEL32!DeactivateActCtx` at `0x180005ffa`
- `KERNEL32!DeactivateActCtx` at `0x18056dd07`
- `KERNEL32!DeactivateActCtx` at `0x180005ffa`
- `KERNEL32!DeactivateActCtx` at `0x18056dd07`
- `KERNEL32!QueryActCtxW` at `0x180005e9f`
- `KERNEL32!QueryActCtxW` at `0x180005e9f`
- `KERNEL32!GetLastError` at `0x180005f70`
- `KERNEL32!GetLastError` at `0x180005f70`
- `KERNEL32!LoadLibraryW` at `0x180005fec`
- `KERNEL32!LoadLibraryW` at `0x180005fec`

## string_xrefs

- `0x180005fcc`: `Comctl32.dll`
- `0x180005fe5`: `Comctl32.dll`

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

  v0 = 0;
  *(_OWORD *)hActCtx = 0;
  Cookie = 0;
  if ( IsolationAwarePrivateT_SqbjaYRiRY || *(_QWORD *)&WinbaseIsolationAwarePrivateT_UnPgpgk != -1 )
    return 1;
  if ( QueryActCtxW(0x80000010, &WinbaseIsolationAwarePrivateT_UnPgpgk, 0, 1u, hActCtx, 0x10u, 0) )
  {
    ActCtxW = hActCtx[0];
    if ( hActCtx[0] )
      goto LABEL_13;
    *(_OWORD *)&pActCtx.ulLength = 0;
    pActCtx.lpSectionBase = 0;
    phModule = 0;
    if ( GetModuleHandleExW(6u, &WinbaseIsolationAwarePrivateT_UnPgpgk, &phModule) )
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
          *(_QWORD *)&WinbaseIsolationAwarePrivateT_UnPgpgk = ActCtxW;
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
0x180005e30  push    rbx
0x180005e32  sub     rsp, 2F0h
0x180005e39  mov     rax, cs:__security_cookie
0x180005e40  xor     rax, rsp
0x180005e43  mov     [rsp+2F8h+var_18], rax
0x180005e4b  xor     ebx, ebx
0x180005e4d  xorps   xmm0, xmm0
0x180005e50  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x180005e55  mov     [rsp+2F8h+Cookie], rbx
0x180005e5a  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, ebx
0x180005e60  jnz     loc_180006000
0x180005e66  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x180005e6e  jnz     loc_180006000
0x180005e74  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x180005e79  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180005e82  lea     rax, [rsp+2F8h+hActCtx]
0x180005e87  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x180005e8c  lea     r9d, [rbx+1]; ulInfoClass
0x180005e90  xor     r8d, r8d; pvSubInstance
0x180005e93  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x180005e9a  mov     ecx, 80000010h; dwFlags
0x180005e9f  call    cs:__imp_QueryActCtxW
0x180005ea5  test    eax, eax
0x180005ea7  jz      loc_180006005
0x180005ead  mov     rax, [rsp+2F8h+hActCtx]
0x180005eb2  test    rax, rax
0x180005eb5  jnz     loc_180005F91
0x180005ebb  xorps   xmm0, xmm0
0x180005ebe  movdqu  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x180005ec4  mov     qword ptr [rsp+2F8h+pActCtx+28h], rbx
0x180005ecc  mov     [rsp+2F8h+phModule], rbx
0x180005ed1  lea     r8, [rsp+2F8h+phModule]; phModule
0x180005ed6  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x180005edd  lea     ecx, [rbx+6]; dwFlags
0x180005ee0  call    cs:__imp_GetModuleHandleExW
0x180005ee6  test    eax, eax
0x180005ee8  jz      loc_180006005
0x180005eee  mov     r8d, 105h; nSize
0x180005ef4  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x180005efc  mov     rcx, [rsp+2F8h+phModule]; hModule
0x180005f01  call    cs:__imp_GetModuleFileNameW
0x180005f07  test    eax, eax
0x180005f09  jz      loc_180006005
0x180005f0f  cmp     eax, 105h
0x180005f14  jb      short loc_180005F24
0x180005f16  lea     ecx, [rbx+6Fh]; dwErrCode
0x180005f19  call    cs:__imp_SetLastError
0x180005f1f  jmp     loc_180006005
0x180005f24  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180005f2c  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180005f34  lea     rax, [rsp+2F8h+Filename]
0x180005f3c  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x180005f41  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x180005f4d  mov     rax, [rsp+2F8h+phModule]
0x180005f52  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180005f5a  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x180005f5f  call    cs:__imp_CreateActCtxW
0x180005f65  mov     [rsp+2F8h+hActCtx], rax
0x180005f6a  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180005f6e  jnz     short loc_180005F91
0x180005f70  call    cs:__imp_GetLastError
0x180005f76  lea     ecx, [rax-714h]
0x180005f7c  cmp     ecx, 3
0x180005f7f  jbe     short loc_180005F89
0x180005f81  add     eax, 0FFFFFFFEh
0x180005f84  cmp     eax, 1
0x180005f87  ja      short loc_180006005
0x180005f89  mov     rax, rbx
0x180005f8c  mov     [rsp+2F8h+hActCtx], rbx
0x180005f91  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180005f98  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180005f9d  mov     rcx, rax; hActCtx
0x180005fa0  call    cs:__imp_ActivateActCtx
0x180005fa6  test    eax, eax
0x180005fa8  jz      short loc_180006000
0x180005faa  xor     edx, edx; Val
0x180005fac  lea     r8d, [rdx+70h]; Size
0x180005fb0  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180005fb5  call    memset_0
0x180005fba  mov     dword ptr [rsp+2F8h+pActCtx], 70h ; 'p'
0x180005fc2  lea     rax, [rsp+2F8h+pActCtx]
0x180005fc7  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x180005fcc  lea     r9, LibFileName; "Comctl32.dll"
0x180005fd3  xor     edx, edx; lpExtensionGuid
0x180005fd5  xor     ecx, ecx; dwFlags
0x180005fd7  lea     r8d, [rdx+2]; ulSectionId
0x180005fdb  call    cs:__imp_FindActCtxSectionStringW
0x180005fe1  test    eax, eax
0x180005fe3  jz      short loc_180005FF3
0x180005fe5  lea     rcx, LibFileName; "Comctl32.dll"
0x180005fec  call    cs:__imp_LoadLibraryW
0x180005ff2  nop
0x180005ff3  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x180005ff8  xor     ecx, ecx; dwFlags
0x180005ffa  call    cs:__imp_DeactivateActCtx
0x180006000  mov     ebx, 1
0x180006005  mov     eax, ebx
0x180006007  mov     rcx, [rsp+2F8h+var_18]
0x18000600f  xor     rcx, rsp; StackCookie
0x180006012  call    __security_check_cookie
0x180006017  add     rsp, 2F0h
0x18000601e  pop     rbx
0x18000601f  retn
0x18056dcf8  push    rbp
0x18056dcfa  sub     rsp, 40h
0x18056dcfe  mov     rbp, rdx
0x18056dd01  mov     rdx, [rbp+48h]; ulCookie
0x18056dd05  xor     ecx, ecx; dwFlags
0x18056dd07  call    cs:__imp_DeactivateActCtx
0x18056dd0d  nop
0x18056dd0e  add     rsp, 40h
0x18056dd12  pop     rbp
0x18056dd13  retn
```
