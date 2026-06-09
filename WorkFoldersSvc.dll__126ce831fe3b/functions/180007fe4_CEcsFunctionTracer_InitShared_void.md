# CEcsFunctionTracer::InitShared(void)

- ea: `0x180007fe4`
- end: `0x180008077`
- name: `?InitShared@CEcsFunctionTracer@@SAXXZ`
- size: `147`
- prototype: `void(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x18000ce40`

## callees

- `0x180007fe4`
- `0x180008108`

## import_xrefs

- `KERNEL32!LoadLibraryExW` at `0x180007ff7`
- `KERNEL32!LoadLibraryExW` at `0x18000801e`
- `KERNEL32!LoadLibraryExW` at `0x180007ff7`
- `KERNEL32!LoadLibraryExW` at `0x18000801e`
- `KERNEL32!GetLastError` at `0x180008009`
- `KERNEL32!GetLastError` at `0x180008030`
- `KERNEL32!GetLastError` at `0x180008009`
- `KERNEL32!GetLastError` at `0x180008030`

## string_xrefs

- `0x180007fec`: `SyncShareRes.dll`
- `0x180008011`: `WorkFoldersRes.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void CEcsFunctionTracer::InitShared(void)
{
  DWORD LastError; // ebx
  DWORD v1; // eax

  CEcsFunctionTracer::s_hResourceDll = LoadLibraryExW(L"SyncShareRes.dll", 0, 0x22u);
  if ( !CEcsFunctionTracer::s_hResourceDll )
  {
    LastError = GetLastError();
    CEcsFunctionTracer::s_hResourceDll = LoadLibraryExW(L"WorkFoldersRes.dll", 0, 0x22u);
    if ( !CEcsFunctionTracer::s_hResourceDll )
    {
      v1 = GetLastError();
      if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
        && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 1) != 0
        && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
      {
        WPP_SF_dd(
          *((_QWORD *)WPP_GLOBAL_Control + 7),
          15,
          &WPP_cfdd00ac916f3ee682261b67c705028c_Traceguids,
          LastError,
          v1);
      }
    }
  }
}

```

## disassembly

```asm
0x180007fe4  push    rbx
0x180007fe6  sub     rsp, 30h
0x180007fea  xor     edx, edx; hFile
0x180007fec  lea     rcx, LibFileName; "SyncShareRes.dll"
0x180007ff3  lea     r8d, [rdx+22h]; dwFlags
0x180007ff7  call    cs:__imp_LoadLibraryExW
0x180007ffd  mov     cs:?s_hResourceDll@CEcsFunctionTracer@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CEcsFunctionTracer::s_hResourceDll
0x180008004  test    rax, rax
0x180008007  jnz     short loc_180008071
0x180008009  call    cs:__imp_GetLastError
0x18000800f  xor     edx, edx; hFile
0x180008011  lea     rcx, aWorkfoldersres; "WorkFoldersRes.dll"
0x180008018  mov     ebx, eax
0x18000801a  lea     r8d, [rdx+22h]; dwFlags
0x18000801e  call    cs:__imp_LoadLibraryExW
0x180008024  mov     cs:?s_hResourceDll@CEcsFunctionTracer@@0PEAUHINSTANCE__@@EA, rax; HINSTANCE__ * CEcsFunctionTracer::s_hResourceDll
0x18000802b  test    rax, rax
0x18000802e  jnz     short loc_180008071
0x180008030  call    cs:__imp_GetLastError
0x180008036  mov     rcx, cs:WPP_GLOBAL_Control
0x18000803d  lea     rdx, WPP_GLOBAL_Control
0x180008044  cmp     rcx, rdx
0x180008047  jz      short loc_180008071
0x180008049  test    byte ptr [rcx+44h], 1
0x18000804d  jz      short loc_180008071
0x18000804f  cmp     byte ptr [rcx+41h], 2
0x180008053  jb      short loc_180008071
0x180008055  mov     rcx, [rcx+38h]
0x180008059  lea     r8, WPP_cfdd00ac916f3ee682261b67c705028c_Traceguids
0x180008060  mov     edx, 0Fh
0x180008065  mov     [rsp+38h+var_18], eax
0x180008069  mov     r9d, ebx
0x18000806c  call    WPP_SF_dd
0x180008071  add     rsp, 30h
0x180008075  pop     rbx
0x180008076  retn
```
