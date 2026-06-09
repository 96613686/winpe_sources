# wil_QueryFeatureState

- ea: `0x18000b928`
- end: `0x18000ba8e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800068e4`

## callees

- `0x18000b928`
- `0x18000c610`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b9c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b9c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b9ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b9ad`

## string_xrefs

- `0x18000b9a6`: `ntdll.dll`
- `0x18000b9ba`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_QueryFeatureState(__int64 a1, unsigned int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  unsigned int v8; // ebx
  BOOL v9; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v12; // r8d
  int v14; // eax
  unsigned int v15; // edx
  unsigned int v16; // ecx
  __int64 v17; // [rsp+30h] [rbp-38h] BYREF
  int v18; // [rsp+38h] [rbp-30h]
  __int64 v19; // [rsp+40h] [rbp-28h] BYREF

  if ( a5 )
    *a5 = 0;
  v19 = 0;
  v8 = 1;
  *a6 = 1;
  v9 = a3 == 0;
  v17 = 0;
  v18 = 0;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      v12 = -1073741511;
LABEL_8:
      v8 = 0;
      goto LABEL_9;
    }
  }
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(a2, v9, &v19, &v17);
  v12 = v14;
  if ( v14 )
  {
    if ( v14 != 279 )
      goto LABEL_8;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v17) >> 7) & 1;
  }
  else
  {
    v15 = HIDWORD(v17);
    v16 = HIDWORD(v17);
    *(_DWORD *)(a1 + 12) = v18;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v16 >> 14;
    *(_DWORD *)a1 = (v16 >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v15) & 0x3F;
    *(_DWORD *)(a1 + 16) = (v15 >> 7) & 1;
    *(_DWORD *)(a1 + 20) = (v15 >> 6) & 1;
  }
LABEL_9:
  if ( a5 )
    *a5 = v12 != -2147483614;
  return v8;
}

```

## disassembly

```asm
0x18000b928  mov     [rsp+arg_10], rbx
0x18000b92d  mov     [rsp+arg_18], rbp
0x18000b932  push    rsi
0x18000b933  push    rdi
0x18000b934  push    r14
0x18000b936  sub     rsp, 50h
0x18000b93a  mov     rax, cs:__security_cookie
0x18000b941  xor     rax, rsp
0x18000b944  mov     [rsp+68h+var_20], rax
0x18000b949  mov     rdi, [rsp+68h+arg_20]
0x18000b951  mov     r14d, edx
0x18000b954  mov     rax, [rsp+68h+arg_28]
0x18000b95c  mov     rsi, rcx
0x18000b95f  test    rdi, rdi
0x18000b962  jz      short loc_18000B96A
0x18000b964  mov     dword ptr [rdi], 0
0x18000b96a  xor     ebp, ebp
0x18000b96c  mov     [rsp+68h+var_28], 0
0x18000b975  test    r8d, r8d
0x18000b978  mov     ebx, 1
0x18000b97d  mov     [rax], ebx
0x18000b97f  setz    bpl
0x18000b983  xor     eax, eax
0x18000b985  mov     [rsp+68h+var_38], rax
0x18000b98a  mov     [rsp+68h+var_30], eax
0x18000b98e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000b995  test    rax, rax
0x18000b998  jnz     short loc_18000BA15
0x18000b99a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b9a1  test    rax, rax
0x18000b9a4  jnz     short loc_18000B9BA
0x18000b9a6  lea     rcx, ModuleName; "ntdll.dll"
0x18000b9ad  call    cs:__imp_GetModuleHandleW
0x18000b9b3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b9ba  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000b9c1  mov     rcx, rax; hModule
0x18000b9c4  call    cs:__imp_GetProcAddress
0x18000b9ca  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000b9d1  test    rax, rax
0x18000b9d4  jnz     short loc_18000BA15
0x18000b9d6  mov     r8d, 0C0000139h
0x18000b9dc  xor     ebx, ebx
0x18000b9de  test    rdi, rdi
0x18000b9e1  jz      short loc_18000B9F1
0x18000b9e3  xor     ecx, ecx
0x18000b9e5  cmp     r8d, 80000022h
0x18000b9ec  setnz   cl
0x18000b9ef  mov     [rdi], ecx
0x18000b9f1  mov     eax, ebx
0x18000b9f3  mov     rcx, [rsp+68h+var_20]
0x18000b9f8  xor     rcx, rsp; StackCookie
0x18000b9fb  call    __security_check_cookie
0x18000ba00  lea     r11, [rsp+68h+var_18]
0x18000ba05  mov     rbx, [r11+30h]
0x18000ba09  mov     rbp, [r11+38h]
0x18000ba0d  mov     rsp, r11
0x18000ba10  pop     r14
0x18000ba12  pop     rdi
0x18000ba13  pop     rsi
0x18000ba14  retn
0x18000ba15  lea     r9, [rsp+68h+var_38]
0x18000ba1a  mov     edx, ebp
0x18000ba1c  lea     r8, [rsp+68h+var_28]
0x18000ba21  mov     ecx, r14d
0x18000ba24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ba29  mov     r8d, eax
0x18000ba2c  test    eax, eax
0x18000ba2e  jnz     short loc_18000BA72
0x18000ba30  mov     edx, dword ptr [rsp+68h+var_38+4]
0x18000ba34  mov     ecx, edx
0x18000ba36  mov     eax, [rsp+68h+var_30]
0x18000ba3a  mov     [rsi+0Ch], eax
0x18000ba3d  mov     eax, edx
0x18000ba3f  shr     eax, 0Eh
0x18000ba42  shr     ecx, 4
0x18000ba45  and     eax, 3
0x18000ba48  and     ecx, 3
0x18000ba4b  mov     [rsi+8], eax
0x18000ba4e  mov     [rsi], ecx
0x18000ba50  mov     eax, edx
0x18000ba52  mov     ecx, edx
0x18000ba54  shr     eax, 6
0x18000ba57  shr     ecx, 8
0x18000ba5a  and     eax, ebx
0x18000ba5c  and     cl, 3Fh
0x18000ba5f  shr     edx, 7
0x18000ba62  and     edx, ebx
0x18000ba64  mov     [rsi+4], cl
0x18000ba67  mov     [rsi+10h], edx
0x18000ba6a  mov     [rsi+14h], eax
0x18000ba6d  jmp     loc_18000B9DE
0x18000ba72  cmp     eax, 117h
0x18000ba77  jnz     loc_18000B9DC
0x18000ba7d  mov     eax, dword ptr [rsp+68h+var_38+4]
0x18000ba81  shr     eax, 7
0x18000ba84  and     eax, ebx
0x18000ba86  mov     [rsi+10h], eax
0x18000ba89  jmp     loc_18000B9DE
```
