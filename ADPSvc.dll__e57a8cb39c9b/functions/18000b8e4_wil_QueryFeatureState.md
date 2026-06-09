# wil_QueryFeatureState

- ea: `0x18000b8e4`
- end: `0x18000ba4a`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800094c0`

## callees

- `0x180002250`
- `0x18000b8e4`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b969`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b969`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b980`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b980`

## string_xrefs

- `0x18000b962`: `ntdll.dll`
- `0x18000b976`: `RtlQueryFeatureConfiguration`

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
  __int64 v18; // [rsp+38h] [rbp-30h] BYREF
  int v19; // [rsp+40h] [rbp-28h]

  if ( a5 )
    *a5 = 0;
  v17 = 0;
  v8 = 1;
  *a6 = 1;
  v9 = a3 == 0;
  v18 = 0;
  v19 = 0;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(a2, v9, &v17, &v18);
  v12 = v14;
  if ( v14 )
  {
    if ( v14 != 279 )
      goto LABEL_8;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v18) >> 7) & 1;
  }
  else
  {
    v15 = HIDWORD(v18);
    v16 = HIDWORD(v18);
    *(_DWORD *)(a1 + 12) = v19;
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
0x18000b8e4  mov     [rsp+arg_10], rbx
0x18000b8e9  mov     [rsp+arg_18], rbp
0x18000b8ee  push    rsi
0x18000b8ef  push    rdi
0x18000b8f0  push    r14
0x18000b8f2  sub     rsp, 50h
0x18000b8f6  mov     rax, cs:__security_cookie
0x18000b8fd  xor     rax, rsp
0x18000b900  mov     [rsp+68h+var_20], rax
0x18000b905  mov     rdi, [rsp+68h+arg_20]
0x18000b90d  mov     r14d, edx
0x18000b910  mov     rax, [rsp+68h+arg_28]
0x18000b918  mov     rsi, rcx
0x18000b91b  test    rdi, rdi
0x18000b91e  jz      short loc_18000B926
0x18000b920  mov     dword ptr [rdi], 0
0x18000b926  xor     ebp, ebp
0x18000b928  mov     [rsp+68h+var_38], 0
0x18000b931  test    r8d, r8d
0x18000b934  mov     ebx, 1
0x18000b939  mov     [rax], ebx
0x18000b93b  setz    bpl
0x18000b93f  xor     eax, eax
0x18000b941  mov     [rsp+68h+var_30], rax
0x18000b946  mov     [rsp+68h+var_28], eax
0x18000b94a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000b951  test    rax, rax
0x18000b954  jnz     short loc_18000B9D1
0x18000b956  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b95d  test    rax, rax
0x18000b960  jnz     short loc_18000B976
0x18000b962  lea     rcx, ModuleName; "ntdll.dll"
0x18000b969  call    cs:__imp_GetModuleHandleW
0x18000b96f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b976  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000b97d  mov     rcx, rax; hModule
0x18000b980  call    cs:__imp_GetProcAddress
0x18000b986  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000b98d  test    rax, rax
0x18000b990  jnz     short loc_18000B9D1
0x18000b992  mov     r8d, 0C0000139h
0x18000b998  xor     ebx, ebx
0x18000b99a  test    rdi, rdi
0x18000b99d  jz      short loc_18000B9AD
0x18000b99f  xor     ecx, ecx
0x18000b9a1  cmp     r8d, 80000022h
0x18000b9a8  setnz   cl
0x18000b9ab  mov     [rdi], ecx
0x18000b9ad  mov     eax, ebx
0x18000b9af  mov     rcx, [rsp+68h+var_20]
0x18000b9b4  xor     rcx, rsp; StackCookie
0x18000b9b7  call    __security_check_cookie
0x18000b9bc  lea     r11, [rsp+68h+var_18]
0x18000b9c1  mov     rbx, [r11+30h]
0x18000b9c5  mov     rbp, [r11+38h]
0x18000b9c9  mov     rsp, r11
0x18000b9cc  pop     r14
0x18000b9ce  pop     rdi
0x18000b9cf  pop     rsi
0x18000b9d0  retn
0x18000b9d1  lea     r9, [rsp+68h+var_30]
0x18000b9d6  mov     edx, ebp
0x18000b9d8  lea     r8, [rsp+68h+var_38]
0x18000b9dd  mov     ecx, r14d
0x18000b9e0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b9e5  mov     r8d, eax
0x18000b9e8  test    eax, eax
0x18000b9ea  jnz     short loc_18000BA2E
0x18000b9ec  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000b9f0  mov     ecx, edx
0x18000b9f2  mov     eax, [rsp+68h+var_28]
0x18000b9f6  mov     [rsi+0Ch], eax
0x18000b9f9  mov     eax, edx
0x18000b9fb  shr     eax, 0Eh
0x18000b9fe  shr     ecx, 4
0x18000ba01  and     eax, 3
0x18000ba04  and     ecx, 3
0x18000ba07  mov     [rsi+8], eax
0x18000ba0a  mov     [rsi], ecx
0x18000ba0c  mov     eax, edx
0x18000ba0e  mov     ecx, edx
0x18000ba10  shr     eax, 6
0x18000ba13  shr     ecx, 8
0x18000ba16  and     eax, ebx
0x18000ba18  and     cl, 3Fh
0x18000ba1b  shr     edx, 7
0x18000ba1e  and     edx, ebx
0x18000ba20  mov     [rsi+4], cl
0x18000ba23  mov     [rsi+10h], edx
0x18000ba26  mov     [rsi+14h], eax
0x18000ba29  jmp     loc_18000B99A
0x18000ba2e  cmp     eax, 117h
0x18000ba33  jnz     loc_18000B998
0x18000ba39  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000ba3d  shr     eax, 7
0x18000ba40  and     eax, ebx
0x18000ba42  mov     [rsi+10h], eax
0x18000ba45  jmp     loc_18000B99A
```
