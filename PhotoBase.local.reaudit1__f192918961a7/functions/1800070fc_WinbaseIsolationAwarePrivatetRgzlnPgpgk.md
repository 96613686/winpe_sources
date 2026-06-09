# WinbaseIsolationAwarePrivatetRgzlnPgpgk

- ea: `0x1800070fc`
- end: `0x1800072fc`
- name: `WinbaseIsolationAwarePrivatetRgzlnPgpgk`
- size: `512`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x180006fc4`

## callees

- `0x180001480`
- `0x180002172`
- `0x1800070fc`

## import_xrefs

- `KERNEL32!QueryActCtxW` at `0x180007170`
- `KERNEL32!QueryActCtxW` at `0x180007170`
- `KERNEL32!GetModuleHandleExW` at `0x1800071bd`
- `KERNEL32!GetModuleHandleExW` at `0x1800071bd`
- `KERNEL32!GetModuleFileNameW` at `0x1800071de`
- `KERNEL32!GetModuleFileNameW` at `0x1800071de`
- `KERNEL32!CreateActCtxW` at `0x18000723c`
- `KERNEL32!CreateActCtxW` at `0x18000723c`
- `KERNEL32!FindActCtxSectionStringW` at `0x1800072b7`
- `KERNEL32!FindActCtxSectionStringW` at `0x1800072b7`
- `KERNEL32!ActivateActCtx` at `0x18000727c`
- `KERNEL32!ActivateActCtx` at `0x18000727c`
- `KERNEL32!LoadLibraryW` at `0x1800072c8`
- `KERNEL32!LoadLibraryW` at `0x1800072c8`
- `KERNEL32!DeactivateActCtx` at `0x1800072d6`
- `KERNEL32!DeactivateActCtx` at `0x180007a11`
- `KERNEL32!DeactivateActCtx` at `0x1800072d6`
- `KERNEL32!DeactivateActCtx` at `0x180007a11`
- `KERNEL32!SetLastError` at `0x1800071f6`
- `KERNEL32!SetLastError` at `0x1800071f6`
- `KERNEL32!GetLastError` at `0x18000724d`
- `KERNEL32!GetLastError` at `0x18000724d`

## string_xrefs

- `0x1800072a8`: `Comctl32.dll`
- `0x1800072c1`: `Comctl32.dll`

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
0x1800070fc  push    rbx
0x1800070fe  sub     rsp, 2F0h
0x180007105  mov     rax, cs:__security_cookie
0x18000710c  xor     rax, rsp
0x18000710f  mov     [rsp+2F8h+var_18], rax
0x180007117  xorps   xmm0, xmm0
0x18000711a  movups  xmmword ptr [rsp+2F8h+hActCtx], xmm0
0x18000711f  mov     [rsp+2F8h+Cookie], 0
0x180007128  cmp     cs:IsolationAwarePrivateT_SqbjaYRiRY, 0
0x18000712f  jnz     loc_1800072DC
0x180007135  cmp     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, 0FFFFFFFFFFFFFFFFh
0x18000713d  jnz     loc_1800072DC
0x180007143  xor     ebx, ebx
0x180007145  mov     [rsp+2F8h+pcbWrittenOrRequired], rbx; pcbWrittenOrRequired
0x18000714a  mov     [rsp+2F8h+cbBuffer], 10h; cbBuffer
0x180007153  lea     rax, [rsp+2F8h+hActCtx]
0x180007158  mov     [rsp+2F8h+pvBuffer], rax; pvBuffer
0x18000715d  lea     r9d, [rbx+1]; ulInfoClass
0x180007161  xor     r8d, r8d; pvSubInstance
0x180007164  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; hActCtx
0x18000716b  mov     ecx, 80000010h; dwFlags
0x180007170  call    cs:__imp_QueryActCtxW
0x180007176  test    eax, eax
0x180007178  jz      loc_1800072E1
0x18000717e  mov     rax, [rsp+2F8h+hActCtx]
0x180007183  test    rax, rax
0x180007186  jnz     loc_18000726D
0x18000718c  xorps   xmm0, xmm0
0x18000718f  movups  xmmword ptr [rsp+2F8h+pActCtx], xmm0
0x180007194  movups  xmmword ptr [rsp+2F8h+pActCtx+10h], xmm0
0x180007199  movups  xmmword ptr [rsp+2F8h+pActCtx+20h], xmm0
0x1800071a1  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x1800071a9  mov     [rsp+2F8h+phModule], rax
0x1800071ae  lea     r8, [rsp+2F8h+phModule]; phModule
0x1800071b3  lea     rdx, WinbaseIsolationAwarePrivateT_UnPgpgk; lpModuleName
0x1800071ba  lea     ecx, [rbx+6]; dwFlags
0x1800071bd  call    cs:__imp_GetModuleHandleExW
0x1800071c3  test    eax, eax
0x1800071c5  jz      loc_1800072E1
0x1800071cb  mov     r8d, 105h; nSize
0x1800071d1  lea     rdx, [rsp+2F8h+Filename]; lpFilename
0x1800071d9  mov     rcx, [rsp+2F8h+phModule]; hModule
0x1800071de  call    cs:__imp_GetModuleFileNameW
0x1800071e4  test    eax, eax
0x1800071e6  jz      loc_1800072E1
0x1800071ec  cmp     eax, 105h
0x1800071f1  jb      short loc_180007201
0x1800071f3  lea     ecx, [rbx+6Fh]; dwErrCode
0x1800071f6  call    cs:__imp_SetLastError
0x1800071fc  jmp     loc_1800072E1
0x180007201  mov     dword ptr [rsp+2F8h+pActCtx], 38h ; '8'
0x180007209  mov     dword ptr [rsp+2F8h+pActCtx+4], 88h
0x180007211  lea     rax, [rsp+2F8h+Filename]
0x180007219  mov     qword ptr [rsp+2F8h+pActCtx+8], rax
0x18000721e  mov     qword ptr [rsp+2F8h+pActCtx+20h], 3
0x18000722a  mov     rax, [rsp+2F8h+phModule]
0x18000722f  mov     qword ptr [rsp+2F8h+pActCtx+30h], rax
0x180007237  lea     rcx, [rsp+2F8h+pActCtx]; pActCtx
0x18000723c  call    cs:__imp_CreateActCtxW
0x180007242  mov     [rsp+2F8h+hActCtx], rax
0x180007247  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x18000724b  jnz     short loc_18000726D
0x18000724d  call    cs:__imp_GetLastError
0x180007253  lea     ecx, [rax-714h]
0x180007259  cmp     ecx, 3
0x18000725c  jbe     short loc_180007266
0x18000725e  add     eax, 0FFFFFFFEh
0x180007261  cmp     eax, 1
0x180007264  ja      short loc_1800072E1
0x180007266  xor     eax, eax
0x180007268  mov     [rsp+2F8h+hActCtx], rax
0x18000726d  mov     cs:WinbaseIsolationAwarePrivateT_UnPgpgk, rax
0x180007274  lea     rdx, [rsp+2F8h+Cookie]; lpCookie
0x180007279  mov     rcx, rax; hActCtx
0x18000727c  call    cs:__imp_ActivateActCtx
0x180007282  test    eax, eax
0x180007284  jz      short loc_1800072DC
0x180007286  mov     ebx, 70h ; 'p'
0x18000728b  mov     r8d, ebx; Size
0x18000728e  xor     edx, edx; Val
0x180007290  lea     rcx, [rsp+2F8h+pActCtx]; void *
0x180007295  call    memset_0
0x18000729a  mov     dword ptr [rsp+2F8h+pActCtx], ebx
0x18000729e  lea     rax, [rsp+2F8h+pActCtx]
0x1800072a3  mov     [rsp+2F8h+pvBuffer], rax; ReturnedData
0x1800072a8  lea     r9, StringToFind; "Comctl32.dll"
0x1800072af  xor     edx, edx; lpExtensionGuid
0x1800072b1  lea     r8d, [rbx-6Eh]; ulSectionId
0x1800072b5  xor     ecx, ecx; dwFlags
0x1800072b7  call    cs:__imp_FindActCtxSectionStringW
0x1800072bd  test    eax, eax
0x1800072bf  jz      short loc_1800072CF
0x1800072c1  lea     rcx, StringToFind; "Comctl32.dll"
0x1800072c8  call    cs:__imp_LoadLibraryW
0x1800072ce  nop
0x1800072cf  mov     rdx, [rsp+2F8h+Cookie]; ulCookie
0x1800072d4  xor     ecx, ecx; dwFlags
0x1800072d6  call    cs:__imp_DeactivateActCtx
0x1800072dc  mov     ebx, 1
0x1800072e1  mov     eax, ebx
0x1800072e3  mov     rcx, [rsp+2F8h+var_18]
0x1800072eb  xor     rcx, rsp; StackCookie
0x1800072ee  call    __security_check_cookie
0x1800072f3  add     rsp, 2F0h
0x1800072fa  pop     rbx
0x1800072fb  retn
0x180007a02  push    rbp
0x180007a04  sub     rsp, 40h
0x180007a08  mov     rbp, rdx
0x180007a0b  mov     rdx, [rbp+48h]; ulCookie
0x180007a0f  xor     ecx, ecx; dwFlags
0x180007a11  call    cs:__imp_DeactivateActCtx
0x180007a17  nop
0x180007a18  add     rsp, 40h
0x180007a1c  pop     rbp
0x180007a1d  retn
```
