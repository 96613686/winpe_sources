# LoadDownloadManagerModule(void)

- ea: `0x1800b2140`
- end: `0x1800b220c`
- name: `?LoadDownloadManagerModule@@YAPEAUHINSTANCE__@@XZ`
- size: `204`
- prototype: `HINSTANCE(void)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting`

## callers

- `0x1800b2020`

## callees

- `0x1800aa650`
- `0x1800b2140`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800b2175`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleExW` at `0x1800b2175`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b21e9`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800b21e9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800b2191`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleFileNameW` at `0x1800b2191`

## pseudocode

```c
HINSTANCE LoadDownloadManagerModule(void)
{
  DWORD ModuleFileNameW; // eax
  __int64 v1; // rdx
  HMODULE phModule; // [rsp+20h] [rbp-238h] BYREF
  WCHAR Filename[8]; // [rsp+30h] [rbp-228h] BYREF
  _OWORD v5[32]; // [rsp+40h] [rbp-218h]

  phModule = 0;
  if ( !GetModuleHandleExW(6u, (LPCWSTR)LoadDownloadManagerModule, &phModule) )
    return 0;
  ModuleFileNameW = GetModuleFileNameW(phModule, Filename, 0x104u);
  if ( ModuleFileNameW >= 0x104 )
    return 0;
  if ( ModuleFileNameW )
  {
    do
    {
      v1 = ModuleFileNameW - 1;
      if ( Filename[v1] == 92 )
        break;
      --ModuleFileNameW;
    }
    while ( (_DWORD)v1 );
  }
  if ( 260 - (unsigned __int64)ModuleFileNameW < 0x11 )
    return 0;
  *(_OWORD *)&Filename[ModuleFileNameW] = xmmword_180101678;
  *(_OWORD *)((char *)v5 + 2 * ModuleFileNameW) = xmmword_180101688;
  *((_WORD *)&v5[1] + ModuleFileNameW) = 0;
  return LoadLibraryExW(Filename, 0, 0);
}

```

## disassembly

```asm
0x1800b2140  push    rbx
0x1800b2142  sub     rsp, 250h
0x1800b2149  mov     rax, cs:__security_cookie
0x1800b2150  xor     rax, rsp
0x1800b2153  mov     [rsp+258h+var_18], rax
0x1800b215b  lea     r8, [rsp+258h+phModule]; phModule
0x1800b2160  mov     [rsp+258h+phModule], 0
0x1800b2169  lea     rdx, ?LoadDownloadManagerModule@@YAPEAUHINSTANCE__@@XZ; lpModuleName
0x1800b2170  mov     ecx, 6; dwFlags
0x1800b2175  call    cs:__imp_GetModuleHandleExW
0x1800b217b  test    eax, eax
0x1800b217d  jz      short loc_1800B21F1
0x1800b217f  mov     rcx, [rsp+258h+phModule]; hModule
0x1800b2184  lea     rdx, [rsp+258h+Filename]; lpFilename
0x1800b2189  mov     ebx, 104h
0x1800b218e  mov     r8d, ebx; nSize
0x1800b2191  call    cs:__imp_GetModuleFileNameW
0x1800b2197  cmp     eax, ebx
0x1800b2199  jnb     short loc_1800B21F1
0x1800b219b  test    eax, eax
0x1800b219d  jz      short loc_1800B21B0
0x1800b219f  lea     edx, [rax-1]
0x1800b21a2  cmp     [rsp+rdx*2+258h+Filename], 5Ch ; '\'
0x1800b21a8  jz      short loc_1800B21B0
0x1800b21aa  mov     eax, edx
0x1800b21ac  test    edx, edx
0x1800b21ae  jnz     short loc_1800B219F
0x1800b21b0  mov     ecx, eax
0x1800b21b2  sub     rbx, rcx
0x1800b21b5  cmp     rbx, 11h
0x1800b21b9  jb      short loc_1800B21F1
0x1800b21bb  movups  xmm0, cs:xmmword_180101678
0x1800b21c2  movzx   eax, cs:word_180101698
0x1800b21c9  xor     r8d, r8d; dwFlags
0x1800b21cc  movups  xmm1, cs:xmmword_180101688
0x1800b21d3  xor     edx, edx; hFile
0x1800b21d5  movups  xmmword ptr [rsp+rcx*2+258h+Filename], xmm0
0x1800b21da  movups  [rsp+rcx*2+258h+var_218], xmm1
0x1800b21df  mov     [rsp+rcx*2+258h+var_208], ax
0x1800b21e4  lea     rcx, [rsp+258h+Filename]; lpLibFileName
0x1800b21e9  call    cs:__imp_LoadLibraryExW
0x1800b21ef  jmp     short loc_1800B21F3
0x1800b21f1  xor     eax, eax
0x1800b21f3  mov     rcx, [rsp+258h+var_18]
0x1800b21fb  xor     rcx, rsp; StackCookie
0x1800b21fe  call    __security_check_cookie
0x1800b2203  add     rsp, 250h
0x1800b220a  pop     rbx
0x1800b220b  retn
```
