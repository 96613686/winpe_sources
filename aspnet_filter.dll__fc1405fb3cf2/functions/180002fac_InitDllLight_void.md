# InitDllLight(void)

- ea: `0x180002fac`
- end: `0x1800030a3`
- name: `?InitDllLight@@YAJXZ`
- size: `247`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting`

## callers

- `0x1800030a4`

## callees

- `0x180002fac`
- `0x1800030d4`
- `0x180003950`

## import_xrefs

- `KERNEL32!GetModuleFileNameW` at `0x180003029`
- `KERNEL32!GetModuleFileNameW` at `0x180003029`
- `KERNEL32!HeapCreate` at `0x180002fef`
- `KERNEL32!HeapCreate` at `0x180002fef`
- `KERNEL32!HeapDestroy` at `0x180003072`
- `KERNEL32!HeapDestroy` at `0x180003072`
- `KERNEL32!GetProcessHeap` at `0x180003001`
- `KERNEL32!GetProcessHeap` at `0x180003001`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180002fe2`
- `KERNEL32!DisableThreadLibraryCalls` at `0x180002fe2`
- `KERNEL32!LoadLibraryW` at `0x18000304f`
- `KERNEL32!LoadLibraryW` at `0x18000304f`
- `KERNEL32!GetLastError` at `0x180003037`
- `KERNEL32!GetLastError` at `0x180003037`

## pseudocode

```c
__int64 InitDllLight(void)
{
  int LastWin32Error; // edi
  int v1; // esi
  DWORD ModuleFileNameW; // eax
  WCHAR Filename[264]; // [rsp+20h] [rbp-228h] BYREF

  LastWin32Error = 0;
  v1 = 0;
  DisableThreadLibraryCalls(g_DllInstance);
  g_hXSPHeap = HeapCreate(0, 0, 0);
  if ( g_hXSPHeap )
    v1 = 1;
  else
    g_hXSPHeap = GetProcessHeap();
  ModuleFileNameW = GetModuleFileNameW(g_DllInstance, Filename, 0x105u);
  if ( !ModuleFileNameW
    || ModuleFileNameW == 261 && GetLastError() == 122
    || (Filename[260] = 0, !LoadLibraryW(Filename)) )
  {
    LastWin32Error = GetLastWin32Error();
    if ( LastWin32Error < 0 && v1 )
      HeapDestroy(g_hXSPHeap);
  }
  return (unsigned int)LastWin32Error;
}

```

## disassembly

```asm
0x180002fac  mov     [rsp+arg_0], rbx
0x180002fb1  mov     [rsp+arg_8], rbp
0x180002fb6  mov     [rsp+arg_10], rsi
0x180002fbb  push    rdi
0x180002fbc  sub     rsp, 240h
0x180002fc3  mov     rax, cs:__security_cookie
0x180002fca  xor     rax, rsp
0x180002fcd  mov     [rsp+248h+var_18], rax
0x180002fd5  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hLibModule
0x180002fdc  xor     ebp, ebp
0x180002fde  mov     edi, ebp
0x180002fe0  mov     esi, ebp
0x180002fe2  call    cs:__imp_DisableThreadLibraryCalls
0x180002fe8  xor     r8d, r8d; dwMaximumSize
0x180002feb  xor     edx, edx; dwInitialSize
0x180002fed  xor     ecx, ecx; flOptions
0x180002fef  call    cs:__imp_HeapCreate
0x180002ff5  mov     cs:?g_hXSPHeap@@3PEAXEA, rax; void * g_hXSPHeap
0x180002ffc  test    rax, rax
0x180002fff  jnz     short loc_180003010
0x180003001  call    cs:__imp_GetProcessHeap
0x180003007  mov     cs:?g_hXSPHeap@@3PEAXEA, rax; void * g_hXSPHeap
0x18000300e  jmp     short loc_180003015
0x180003010  mov     esi, 1
0x180003015  mov     rcx, cs:?g_DllInstance@@3PEAUHINSTANCE__@@EA; hModule
0x18000301c  lea     rdx, [rsp+248h+Filename]; lpFilename
0x180003021  mov     ebx, 105h
0x180003026  mov     r8d, ebx; nSize
0x180003029  call    cs:__imp_GetModuleFileNameW
0x18000302f  test    eax, eax
0x180003031  jz      short loc_18000305A
0x180003033  cmp     eax, ebx
0x180003035  jnz     short loc_180003042
0x180003037  call    cs:__imp_GetLastError
0x18000303d  cmp     eax, 7Ah ; 'z'
0x180003040  jz      short loc_18000305A
0x180003042  lea     rcx, [rsp+248h+Filename]; lpLibFileName
0x180003047  mov     [rsp+248h+var_20], bp
0x18000304f  call    cs:__imp_LoadLibraryW
0x180003055  test    rax, rax
0x180003058  jnz     short loc_180003078
0x18000305a  call    ?GetLastWin32Error@@YAJXZ; GetLastWin32Error(void)
0x18000305f  mov     ebx, eax
0x180003061  mov     edi, eax
0x180003063  test    eax, eax
0x180003065  jns     short loc_180003078
0x180003067  test    esi, esi
0x180003069  jz      short loc_180003078
0x18000306b  mov     rcx, cs:?g_hXSPHeap@@3PEAXEA; hHeap
0x180003072  call    cs:__imp_HeapDestroy
0x180003078  mov     eax, edi
0x18000307a  mov     rcx, [rsp+248h+var_18]
0x180003082  xor     rcx, rsp; StackCookie
0x180003085  call    __security_check_cookie
0x18000308a  lea     r11, [rsp+248h+var_8]
0x180003092  mov     rbx, [r11+10h]
0x180003096  mov     rbp, [r11+18h]
0x18000309a  mov     rsi, [r11+20h]
0x18000309e  mov     rsp, r11
0x1800030a1  pop     rdi
0x1800030a2  retn
```
