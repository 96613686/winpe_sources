# SpUtilsSetTargetWindowsDir

- ea: `0x180040654`
- end: `0x180040720`
- name: `SpUtilsSetTargetWindowsDir`
- size: `204`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x18004088c`

## callees

- `0x18001af70`
- `0x18003f6b8`
- `0x180040654`
- `0x180040bc4`
- `0x180040c78`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040686`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180040686`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800406a7`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x1800406a7`

## pseudocode

```c
__int64 SpUtilsSetTargetWindowsDir()
{
  unsigned int v0; // ebx
  void *v1; // rax
  WCHAR Buffer[296]; // [rsp+20h] [rbp-268h] BYREF

  v0 = 0;
  if ( g_sputils_WindowsDirectory )
  {
    HeapFree(hHeap, 0, g_sputils_WindowsDirectory);
    g_sputils_WindowsDirectory = 0;
  }
  g_sputils_IsOnlineWindowsDirectory = 1;
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 > 0x103 )
    return v0;
  v1 = (void *)pSetupDuplicateString(Buffer);
  g_sputils_WindowsDirectory = v1;
  if ( !v1 )
    return v0;
  if ( !g_sputils_LogInitialized )
    return 1;
  if ( !g_sputils_IsOnlineWindowsDirectory )
    goto LABEL_9;
  if ( pSpUtilsSetLogPathFromRegKey() )
    return 1;
  v1 = g_sputils_WindowsDirectory;
LABEL_9:
  if ( (unsigned int)pSpUtilsSetLogPath((STRSAFE_LPCWSTR)v1) )
    return 1;
  return v0;
}

```

## disassembly

```asm
0x180040654  push    rbx
0x180040656  sub     rsp, 280h
0x18004065d  mov     rax, cs:__security_cookie
0x180040664  xor     rax, rsp
0x180040667  mov     [rsp+288h+var_18], rax
0x18004066f  mov     r8, cs:g_sputils_WindowsDirectory; lpMem
0x180040676  xor     ebx, ebx
0x180040678  test    r8, r8
0x18004067b  jz      short loc_180040693
0x18004067d  mov     rcx, cs:hHeap; hHeap
0x180040684  xor     edx, edx; dwFlags
0x180040686  call    cs:__imp_HeapFree
0x18004068c  mov     cs:g_sputils_WindowsDirectory, rbx
0x180040693  mov     edx, 104h; uSize
0x180040698  mov     cs:g_sputils_IsOnlineWindowsDirectory, 1
0x1800406a2  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x1800406a7  call    cs:__imp_GetSystemWindowsDirectoryW
0x1800406ad  dec     eax
0x1800406af  cmp     eax, 103h
0x1800406b4  ja      short loc_180040705
0x1800406b6  lea     rcx, [rsp+288h+Buffer]; pszSrc
0x1800406bb  call    pSetupDuplicateString
0x1800406c0  mov     cs:g_sputils_WindowsDirectory, rax
0x1800406c7  test    rax, rax
0x1800406ca  jz      short loc_180040705
0x1800406cc  cmp     cs:g_sputils_LogInitialized, ebx
0x1800406d2  jz      short loc_180040700
0x1800406d4  mov     edx, cs:g_sputils_IsOnlineWindowsDirectory
0x1800406da  test    edx, edx
0x1800406dc  jz      short loc_1800406F4
0x1800406de  call    pSpUtilsSetLogPathFromRegKey
0x1800406e3  test    eax, eax
0x1800406e5  jnz     short loc_180040700
0x1800406e7  mov     rax, cs:g_sputils_WindowsDirectory
0x1800406ee  mov     edx, cs:g_sputils_IsOnlineWindowsDirectory
0x1800406f4  mov     rcx, rax; pszSrc
0x1800406f7  call    pSpUtilsSetLogPath
0x1800406fc  test    eax, eax
0x1800406fe  jz      short loc_180040705
0x180040700  mov     ebx, 1
0x180040705  mov     eax, ebx
0x180040707  mov     rcx, [rsp+288h+var_18]
0x18004070f  xor     rcx, rsp; StackCookie
0x180040712  call    __security_check_cookie
0x180040717  add     rsp, 280h
0x18004071e  pop     rbx
0x18004071f  retn
```
