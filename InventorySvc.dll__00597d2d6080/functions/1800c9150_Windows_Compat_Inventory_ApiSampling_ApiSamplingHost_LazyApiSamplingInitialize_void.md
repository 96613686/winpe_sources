# Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::LazyApiSamplingInitialize(void)

- ea: `0x1800c9150`
- end: `0x1800c92af`
- name: `?LazyApiSamplingInitialize@ApiSamplingHost@ApiSampling@Inventory@Compat@Windows@@AEAAJXZ`
- size: `351`
- prototype: `__int64 __fastcall(Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *__hidden this)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800c860c`
- `0x1800c9ec0`

## callees

- `0x1800152d0`
- `0x1800c9150`
- `0x1800d1010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c91bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c91d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c91e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c91fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c9210`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c91bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c91d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c91e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c91fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800c9210`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c917d`
- `api-ms-win-core-libraryloader-l1-2-0!LoadLibraryExW` at `0x1800c917d`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c919a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c928b`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c919a`
- `api-ms-win-core-libraryloader-l1-2-0!FreeLibrary` at `0x1800c928b`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c91a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c9293`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c91a2`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x1800c9293`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c918f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c921f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9280`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c918f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c921f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800c9280`

## string_xrefs

- `0x1800c9229`: `LoadLibraryExW failed [%d]`
- `0x1800c9176`: `apisampling.dll`
- `0x1800c9236`: `Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::LoadApiSampling`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::LazyApiSamplingInitialize(
        Windows::Compat::Inventory::ApiSampling::ApiSamplingHost *this)
{
  unsigned int v2; // ebp
  HMODULE Library; // rsi
  HMODULE v4; // r14
  DWORD LastError; // ebx
  DWORD v6; // eax
  HMODULE v7; // rsi
  unsigned int (*v8)(void); // rax
  DWORD v9; // ebx

  v2 = -2147467259;
  if ( !*((_QWORD *)this + 11) )
  {
    Library = LoadLibraryExW(L"apisampling.dll", 0, 0x800u);
    v4 = (HMODULE)*((_QWORD *)this + 11);
    if ( v4 )
    {
      LastError = GetLastError();
      FreeLibrary(v4);
      SetLastError(LastError);
    }
    *((_QWORD *)this + 11) = Library;
    if ( Library )
    {
      *((_QWORD *)this + 12) = GetProcAddress(Library, "APISamplingInitialize");
      *((_QWORD *)this + 13) = GetProcAddress(*((HMODULE *)this + 11), "APISamplingUninitialize");
      *((_QWORD *)this + 14) = GetProcAddress(*((HMODULE *)this + 11), "APISamplingSetValue");
      *((_QWORD *)this + 15) = GetProcAddress(*((HMODULE *)this + 11), "APISamplingStart");
      *((_QWORD *)this + 16) = GetProcAddress(*((HMODULE *)this + 11), "APISamplingStop");
    }
    else
    {
      v6 = GetLastError();
      AslLogCallPrintf(
        1,
        "Windows::Compat::Inventory::ApiSampling::ApiSamplingHost::LoadApiSampling",
        103,
        "LoadLibraryExW failed [%d]",
        v6);
    }
  }
  v7 = (HMODULE)*((_QWORD *)this + 11);
  if ( !v7 )
    goto LABEL_15;
  v8 = (unsigned int (*)(void))*((_QWORD *)this + 12);
  if ( !v8 || !*((_QWORD *)this + 13) || !*((_QWORD *)this + 14) || !*((_QWORD *)this + 15) || !*((_QWORD *)this + 16) )
  {
    v9 = GetLastError();
    FreeLibrary(v7);
    SetLastError(v9);
LABEL_15:
    *((_QWORD *)this + 11) = 0;
    return v2;
  }
  return v8();
}

```

## disassembly

```asm
0x1800c9150  push    rbx
0x1800c9152  push    rbp
0x1800c9153  push    rsi
0x1800c9154  push    rdi
0x1800c9155  push    r14
0x1800c9157  sub     rsp, 30h
0x1800c915b  mov     rdi, rcx
0x1800c915e  mov     ebp, 80004005h
0x1800c9163  cmp     qword ptr [rcx+58h], 0
0x1800c9168  jnz     loc_1800C9246
0x1800c916e  xor     edx, edx; hFile
0x1800c9170  mov     r8d, 800h; dwFlags
0x1800c9176  lea     rcx, aApisamplingDll; "apisampling.dll"
0x1800c917d  call    cs:__imp_LoadLibraryExW
0x1800c9183  mov     rsi, rax
0x1800c9186  mov     r14, [rdi+58h]
0x1800c918a  test    r14, r14
0x1800c918d  jz      short loc_1800C91A9
0x1800c918f  call    cs:__imp_GetLastError
0x1800c9195  mov     ebx, eax
0x1800c9197  mov     rcx, r14; hLibModule
0x1800c919a  call    cs:__imp_FreeLibrary
0x1800c91a0  mov     ecx, ebx; dwErrCode
0x1800c91a2  call    cs:__imp_SetLastError
0x1800c91a8  nop
0x1800c91a9  mov     [rdi+58h], rsi
0x1800c91ad  test    rsi, rsi
0x1800c91b0  jz      short loc_1800C921F
0x1800c91b2  lea     rdx, aApisamplingini_0; "APISamplingInitialize"
0x1800c91b9  mov     rcx, rsi; hModule
0x1800c91bc  call    cs:__imp_GetProcAddress
0x1800c91c2  mov     [rdi+60h], rax
0x1800c91c6  lea     rdx, aApisamplinguni; "APISamplingUninitialize"
0x1800c91cd  mov     rcx, [rdi+58h]; hModule
0x1800c91d1  call    cs:__imp_GetProcAddress
0x1800c91d7  mov     [rdi+68h], rax
0x1800c91db  lea     rdx, aApisamplingset; "APISamplingSetValue"
0x1800c91e2  mov     rcx, [rdi+58h]; hModule
0x1800c91e6  call    cs:__imp_GetProcAddress
0x1800c91ec  mov     [rdi+70h], rax
0x1800c91f0  lea     rdx, aApisamplingsta_1; "APISamplingStart"
0x1800c91f7  mov     rcx, [rdi+58h]; hModule
0x1800c91fb  call    cs:__imp_GetProcAddress
0x1800c9201  mov     [rdi+78h], rax
0x1800c9205  lea     rdx, aApisamplingsto; "APISamplingStop"
0x1800c920c  mov     rcx, [rdi+58h]; hModule
0x1800c9210  call    cs:__imp_GetProcAddress
0x1800c9216  mov     [rdi+80h], rax
0x1800c921d  jmp     short loc_1800C9246
0x1800c921f  call    cs:__imp_GetLastError
0x1800c9225  mov     [rsp+58h+var_38], eax
0x1800c9229  lea     r9, aLoadlibraryexw_1; "LoadLibraryExW failed [%d]"
0x1800c9230  mov     r8d, 67h ; 'g'
0x1800c9236  lea     rdx, aWindowsCompatI_36; "Windows::Compat::Inventory::ApiSampling"...
0x1800c923d  lea     ecx, [r8-66h]
0x1800c9241  call    AslLogCallPrintf
0x1800c9246  mov     rsi, [rdi+58h]
0x1800c924a  test    rsi, rsi
0x1800c924d  jz      short loc_1800C929A
0x1800c924f  mov     rax, [rdi+60h]
0x1800c9253  test    rax, rax
0x1800c9256  jz      short loc_1800C9280
0x1800c9258  cmp     qword ptr [rdi+68h], 0
0x1800c925d  jz      short loc_1800C9280
0x1800c925f  cmp     qword ptr [rdi+70h], 0
0x1800c9264  jz      short loc_1800C9280
0x1800c9266  cmp     qword ptr [rdi+78h], 0
0x1800c926b  jz      short loc_1800C9280
0x1800c926d  cmp     qword ptr [rdi+80h], 0
0x1800c9275  jz      short loc_1800C9280
0x1800c9277  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800c927c  mov     ebp, eax
0x1800c927e  jmp     short loc_1800C92A2
0x1800c9280  call    cs:__imp_GetLastError
0x1800c9286  mov     ebx, eax
0x1800c9288  mov     rcx, rsi; hLibModule
0x1800c928b  call    cs:__imp_FreeLibrary
0x1800c9291  mov     ecx, ebx; dwErrCode
0x1800c9293  call    cs:__imp_SetLastError
0x1800c9299  nop
0x1800c929a  mov     qword ptr [rdi+58h], 0
0x1800c92a2  mov     eax, ebp
0x1800c92a4  add     rsp, 30h
0x1800c92a8  pop     r14
0x1800c92aa  pop     rdi
0x1800c92ab  pop     rsi
0x1800c92ac  pop     rbp
0x1800c92ad  pop     rbx
0x1800c92ae  retn
```
