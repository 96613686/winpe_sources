# HvsiSystem::GetBabyWimPath(ushort *,ulong)

- ea: `0x180031d54`
- end: `0x180031ea0`
- name: `?GetBabyWimPath@HvsiSystem@@CAJPEAGK@Z`
- size: `332`
- prototype: `__int64 __fastcall(unsigned __int16 *, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, service_task`

## callers

- `0x1800321fc`

## callees

- `0x18000791c`
- `0x180031d54`
- `0x1800582a2`
- `0x1800582e0`

## import_xrefs

- `SHLWAPI!PathFileExistsW` at `0x180031de2`
- `SHLWAPI!PathFileExistsW` at `0x180031e20`
- `SHLWAPI!PathFileExistsW` at `0x180031e5a`
- `SHLWAPI!PathFileExistsW` at `0x180031de2`
- `SHLWAPI!PathFileExistsW` at `0x180031e20`
- `SHLWAPI!PathFileExistsW` at `0x180031e5a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e64`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180031e64`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180031d97`
- `api-ms-win-core-sysinfo-l1-1-0!GetWindowsDirectoryW` at `0x180031d97`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180031dcf`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180031e11`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180031e4b`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180031dcf`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180031e11`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x180031e4b`

## string_xrefs

- `0x180031dc3`: `Containers\Serviced\WindowsDefenderApplicationGuard.wim`

## pseudocode

```c
__int64 __fastcall HvsiSystem::GetBabyWimPath(unsigned __int16 *a1)
{
  HRESULT v2; // ebx
  signed int LastError; // eax
  WCHAR Buffer[264]; // [rsp+20h] [rbp-228h] BYREF

  memset_0(Buffer, 0, 0x208u);
  if ( !GetWindowsDirectoryW(Buffer, 0x103u)
    || (v2 = StringCchCopyW(a1, 0x104u, Buffer), v2 >= 0)
    && (v2 = PathCchAppend(a1, 0x104u, L"Containers\\Serviced\\WindowsDefenderApplicationGuard.wim"), v2 >= 0)
    && !PathFileExistsW(a1)
    && (v2 = StringCchCopyW(a1, 0x104u, Buffer), v2 >= 0)
    && (v2 = PathCchAppend(a1, 0x104u, L"Containers\\WindowsDefenderApplicationGuard.wim"), v2 >= 0)
    && !PathFileExistsW(a1)
    && (v2 = StringCchCopyW(a1, 0x104u, Buffer), v2 >= 0)
    && (v2 = PathCchAppend(a1, 0x104u, L"ContainerImages\\hvsi.wim"), v2 >= 0)
    && !PathFileExistsW(a1) )
  {
    LastError = GetLastError();
    v2 = LastError;
    if ( LastError > 0 )
      return (unsigned __int16)LastError | 0x80070000;
  }
  return (unsigned int)v2;
}

```

## disassembly

```asm
0x180031d54  mov     [rsp+arg_8], rbx
0x180031d59  mov     [rsp+arg_10], rsi
0x180031d5e  push    rdi
0x180031d5f  sub     rsp, 240h
0x180031d66  mov     rax, cs:__security_cookie
0x180031d6d  xor     rax, rsp
0x180031d70  mov     [rsp+248h+var_18], rax
0x180031d78  mov     rdi, rcx
0x180031d7b  xor     edx, edx; Val
0x180031d7d  lea     rcx, [rsp+248h+Buffer]; void *
0x180031d82  mov     r8d, 208h; Size
0x180031d88  call    memset_0
0x180031d8d  mov     edx, 103h; uSize
0x180031d92  lea     rcx, [rsp+248h+Buffer]; lpBuffer
0x180031d97  call    cs:__imp_GetWindowsDirectoryW
0x180031d9d  test    eax, eax
0x180031d9f  jz      loc_180031E64
0x180031da5  mov     esi, 104h
0x180031daa  lea     r8, [rsp+248h+Buffer]; unsigned __int16 *
0x180031daf  mov     edx, esi; unsigned __int64
0x180031db1  mov     rcx, rdi; unsigned __int16 *
0x180031db4  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031db9  mov     ebx, eax
0x180031dbb  test    eax, eax
0x180031dbd  js      loc_180031E79
0x180031dc3  lea     r8, aContainersServ; "Containers\\Serviced\\WindowsDefenderAp"...
0x180031dca  mov     edx, esi; cchPath
0x180031dcc  mov     rcx, rdi; pszPath
0x180031dcf  call    cs:__imp_PathCchAppend
0x180031dd5  mov     ebx, eax
0x180031dd7  test    eax, eax
0x180031dd9  js      loc_180031E79
0x180031ddf  mov     rcx, rdi; pszPath
0x180031de2  call    cs:__imp_PathFileExistsW
0x180031de8  test    eax, eax
0x180031dea  jnz     loc_180031E79
0x180031df0  lea     r8, [rsp+248h+Buffer]; unsigned __int16 *
0x180031df5  mov     edx, esi; unsigned __int64
0x180031df7  mov     rcx, rdi; unsigned __int16 *
0x180031dfa  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031dff  mov     ebx, eax
0x180031e01  test    eax, eax
0x180031e03  js      short loc_180031E79
0x180031e05  lea     r8, aContainersWind; "Containers\\WindowsDefenderApplicationG"...
0x180031e0c  mov     edx, esi; cchPath
0x180031e0e  mov     rcx, rdi; pszPath
0x180031e11  call    cs:__imp_PathCchAppend
0x180031e17  mov     ebx, eax
0x180031e19  test    eax, eax
0x180031e1b  js      short loc_180031E79
0x180031e1d  mov     rcx, rdi; pszPath
0x180031e20  call    cs:__imp_PathFileExistsW
0x180031e26  test    eax, eax
0x180031e28  jnz     short loc_180031E79
0x180031e2a  lea     r8, [rsp+248h+Buffer]; unsigned __int16 *
0x180031e2f  mov     edx, esi; unsigned __int64
0x180031e31  mov     rcx, rdi; unsigned __int16 *
0x180031e34  call    ?StringCchCopyW@@YAJPEAG_KPEBG@Z; StringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x180031e39  mov     ebx, eax
0x180031e3b  test    eax, eax
0x180031e3d  js      short loc_180031E79
0x180031e3f  lea     r8, aContainerimage; "ContainerImages\\hvsi.wim"
0x180031e46  mov     edx, esi; cchPath
0x180031e48  mov     rcx, rdi; pszPath
0x180031e4b  call    cs:__imp_PathCchAppend
0x180031e51  mov     ebx, eax
0x180031e53  test    eax, eax
0x180031e55  js      short loc_180031E79
0x180031e57  mov     rcx, rdi; pszPath
0x180031e5a  call    cs:__imp_PathFileExistsW
0x180031e60  test    eax, eax
0x180031e62  jnz     short loc_180031E79
0x180031e64  call    cs:__imp_GetLastError
0x180031e6a  mov     ebx, eax
0x180031e6c  test    eax, eax
0x180031e6e  jle     short loc_180031E79
0x180031e70  movzx   ebx, ax
0x180031e73  or      ebx, 80070000h
0x180031e79  mov     eax, ebx
0x180031e7b  mov     rcx, [rsp+248h+var_18]
0x180031e83  xor     rcx, rsp; StackCookie
0x180031e86  call    __security_check_cookie
0x180031e8b  lea     r11, [rsp+248h+var_8]
0x180031e93  mov     rbx, [r11+18h]
0x180031e97  mov     rsi, [r11+20h]
0x180031e9b  mov     rsp, r11
0x180031e9e  pop     rdi
0x180031e9f  retn
```
