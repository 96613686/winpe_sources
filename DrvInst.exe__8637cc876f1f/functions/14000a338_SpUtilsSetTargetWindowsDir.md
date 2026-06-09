# SpUtilsSetTargetWindowsDir

- ea: `0x14000a338`
- end: `0x14000a3f2`
- name: `SpUtilsSetTargetWindowsDir`
- size: `186`
- prototype: ``
- caller_count: `1`
- callee_count: `5`
- tags: `installer_update`

## callers

- `0x14000a6bc`

## callees

- `0x14000a338`
- `0x14000a9f4`
- `0x14000aab0`
- `0x14000bc40`
- `0x140045f30`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a36a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000a36a`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14000a38b`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemWindowsDirectoryW` at `0x14000a38b`

## pseudocode

```c
__int64 SpUtilsSetTargetWindowsDir()
{
  unsigned int v0; // ebx
  WCHAR Buffer[296]; // [rsp+20h] [rbp-268h] BYREF

  v0 = 0;
  if ( g_sputils_WindowsDirectory )
  {
    HeapFree(hHeap, 0, g_sputils_WindowsDirectory);
    g_sputils_WindowsDirectory = 0;
  }
  g_sputils_IsOnlineWindowsDirectory = 1;
  if ( GetSystemWindowsDirectoryW(Buffer, 0x104u) - 1 <= 0x103 )
  {
    g_sputils_WindowsDirectory = (unsigned __int16 *)pSetupDuplicateString(Buffer);
    if ( g_sputils_WindowsDirectory )
    {
      if ( !g_sputils_LogInitialized
        || g_sputils_IsOnlineWindowsDirectory && (unsigned int)pSpUtilsSetLogPathFromRegKey()
        || (unsigned int)pSpUtilsSetLogPath() )
      {
        return 1;
      }
    }
  }
  return v0;
}

```

## disassembly

```asm
0x14000a338  push    rbx
0x14000a33a  sub     rsp, 280h
0x14000a341  mov     rax, cs:__security_cookie
0x14000a348  xor     rax, rsp
0x14000a34b  mov     [rsp+288h+var_18], rax
0x14000a353  mov     r8, cs:g_sputils_WindowsDirectory; lpMem
0x14000a35a  xor     ebx, ebx
0x14000a35c  test    r8, r8
0x14000a35f  jz      short loc_14000A377
0x14000a361  mov     rcx, cs:hHeap; hHeap
0x14000a368  xor     edx, edx; dwFlags
0x14000a36a  call    cs:__imp_HeapFree
0x14000a370  mov     cs:g_sputils_WindowsDirectory, rbx
0x14000a377  mov     edx, 104h; uSize
0x14000a37c  mov     cs:g_sputils_IsOnlineWindowsDirectory, 1
0x14000a386  lea     rcx, [rsp+288h+Buffer]; lpBuffer
0x14000a38b  call    cs:__imp_GetSystemWindowsDirectoryW
0x14000a391  dec     eax
0x14000a393  cmp     eax, 103h
0x14000a398  ja      short loc_14000A3D7
0x14000a39a  lea     rcx, [rsp+288h+Buffer]; unsigned __int16 *
0x14000a39f  call    pSetupDuplicateString
0x14000a3a4  mov     cs:g_sputils_WindowsDirectory, rax
0x14000a3ab  test    rax, rax
0x14000a3ae  jz      short loc_14000A3D7
0x14000a3b0  cmp     cs:g_sputils_LogInitialized, ebx
0x14000a3b6  jz      short loc_14000A3D2
0x14000a3b8  cmp     cs:g_sputils_IsOnlineWindowsDirectory, ebx
0x14000a3be  jz      short loc_14000A3C9
0x14000a3c0  call    pSpUtilsSetLogPathFromRegKey
0x14000a3c5  test    eax, eax
0x14000a3c7  jnz     short loc_14000A3D2
0x14000a3c9  call    pSpUtilsSetLogPath
0x14000a3ce  test    eax, eax
0x14000a3d0  jz      short loc_14000A3D7
0x14000a3d2  mov     ebx, 1
0x14000a3d7  mov     eax, ebx
0x14000a3d9  mov     rcx, [rsp+288h+var_18]
0x14000a3e1  xor     rcx, rsp; StackCookie
0x14000a3e4  call    __security_check_cookie
0x14000a3e9  add     rsp, 280h
0x14000a3f0  pop     rbx
0x14000a3f1  retn
```
