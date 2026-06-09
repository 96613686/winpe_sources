# DloadResolve

- ea: `0x1800105bc`
- end: `0x180010669`
- name: `DloadResolve`
- size: `173`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `loader_planting`

## callers

- `0x180010548`

## callees

- `0x1800105bc`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800105ef`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180010604`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800105ef`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180010604`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180010621`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001063d`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180010621`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18001063d`

## string_xrefs

- `0x1800105fd`: `KERNEL32.DLL`
- `0x1800105e8`: `api-ms-win-core-delayload-l1-1-1.dll`
- `0x180010633`: `ResolveDelayLoadsFromDll`

## pseudocode

```c
bool DloadResolve()
{
  __int64 ModuleHandleW; // rbx

  if ( DloadKernel32 == 1 )
    return 0;
  if ( DloadKernel32 )
    return 1;
  ModuleHandleW = (__int64)GetModuleHandleW(L"api-ms-win-core-delayload-l1-1-1.dll");
  if ( (ModuleHandleW || (ModuleHandleW = (__int64)GetModuleHandleW(L"KERNEL32.DLL")) != 0)
    && (DloadResolveDelayLoadedAPI = (__int64)GetProcAddress((HMODULE)ModuleHandleW, "ResolveDelayLoadedAPI")) != 0 )
  {
    DloadResolveDelayLoadsFromDll = (__int64)GetProcAddress((HMODULE)ModuleHandleW, "ResolveDelayLoadsFromDll");
    if ( !DloadResolveDelayLoadsFromDll )
      ModuleHandleW = 1;
  }
  else
  {
    ModuleHandleW = 1;
  }
  DloadKernel32 = ModuleHandleW;
  return ModuleHandleW != 1;
}

```

## disassembly

```asm
0x1800105bc  mov     [rsp+arg_0], rbx
0x1800105c1  push    rdi
0x1800105c2  sub     rsp, 20h
0x1800105c6  mov     rax, cs:DloadKernel32
0x1800105cd  mov     edi, 1
0x1800105d2  cmp     rax, rdi
0x1800105d5  jnz     short loc_1800105DE
0x1800105d7  xor     al, al
0x1800105d9  jmp     loc_18001065E
0x1800105de  test    rax, rax
0x1800105e1  jz      short loc_1800105E8
0x1800105e3  mov     al, dil
0x1800105e6  jmp     short loc_18001065E
0x1800105e8  lea     rcx, aApiMsWinCoreDe_1; "api-ms-win-core-delayload-l1-1-1.dll"
0x1800105ef  call    cs:__imp_GetModuleHandleW
0x1800105f5  mov     rbx, rax
0x1800105f8  test    rax, rax
0x1800105fb  jnz     short loc_180010617
0x1800105fd  lea     rcx, aKernel32Dll; "KERNEL32.DLL"
0x180010604  call    cs:__imp_GetModuleHandleW
0x18001060a  mov     rbx, rax
0x18001060d  test    rax, rax
0x180010610  jnz     short loc_180010617
0x180010612  mov     rbx, rdi
0x180010615  jmp     short loc_180010651
0x180010617  lea     rdx, aResolvedelaylo; "ResolveDelayLoadedAPI"
0x18001061e  mov     rcx, rbx; hModule
0x180010621  call    cs:__imp_GetProcAddress
0x180010627  mov     cs:DloadResolveDelayLoadedAPI, rax
0x18001062e  test    rax, rax
0x180010631  jz      short loc_180010612
0x180010633  lea     rdx, aResolvedelaylo_0; "ResolveDelayLoadsFromDll"
0x18001063a  mov     rcx, rbx; hModule
0x18001063d  call    cs:__imp_GetProcAddress
0x180010643  test    rax, rax
0x180010646  mov     cs:DloadResolveDelayLoadsFromDll, rax
0x18001064d  cmovz   rbx, rdi
0x180010651  cmp     rbx, rdi
0x180010654  mov     cs:DloadKernel32, rbx
0x18001065b  setnz   al
0x18001065e  mov     rbx, [rsp+28h+arg_0]
0x180010663  add     rsp, 20h
0x180010667  pop     rdi
0x180010668  retn
```
