# wil_QueryFeatureState

- ea: `0x140014e18`
- end: `0x140014f7e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140011ec0`

## callees

- `0x140003200`
- `0x140014e18`
- `0x14001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014eb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140014eb4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014e9d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140014e9d`

## string_xrefs

- `0x140014e96`: `ntdll.dll`
- `0x140014eaa`: `RtlQueryFeatureConfiguration`

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
0x140014e18  mov     [rsp+arg_10], rbx
0x140014e1d  mov     [rsp+arg_18], rbp
0x140014e22  push    rsi
0x140014e23  push    rdi
0x140014e24  push    r14
0x140014e26  sub     rsp, 50h
0x140014e2a  mov     rax, cs:__security_cookie
0x140014e31  xor     rax, rsp
0x140014e34  mov     [rsp+68h+var_20], rax
0x140014e39  mov     rdi, [rsp+68h+arg_20]
0x140014e41  mov     r14d, edx
0x140014e44  mov     rax, [rsp+68h+arg_28]
0x140014e4c  mov     rsi, rcx
0x140014e4f  test    rdi, rdi
0x140014e52  jz      short loc_140014E5A
0x140014e54  mov     dword ptr [rdi], 0
0x140014e5a  xor     ebp, ebp
0x140014e5c  mov     [rsp+68h+var_38], 0
0x140014e65  test    r8d, r8d
0x140014e68  mov     ebx, 1
0x140014e6d  mov     [rax], ebx
0x140014e6f  setz    bpl
0x140014e73  xor     eax, eax
0x140014e75  mov     [rsp+68h+var_30], rax
0x140014e7a  mov     [rsp+68h+var_28], eax
0x140014e7e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x140014e85  test    rax, rax
0x140014e88  jnz     short loc_140014F05
0x140014e8a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140014e91  test    rax, rax
0x140014e94  jnz     short loc_140014EAA
0x140014e96  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x140014e9d  call    cs:__imp_GetModuleHandleW
0x140014ea3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140014eaa  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x140014eb1  mov     rcx, rax; hModule
0x140014eb4  call    cs:__imp_GetProcAddress
0x140014eba  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x140014ec1  test    rax, rax
0x140014ec4  jnz     short loc_140014F05
0x140014ec6  mov     r8d, 0C0000139h
0x140014ecc  xor     ebx, ebx
0x140014ece  test    rdi, rdi
0x140014ed1  jz      short loc_140014EE1
0x140014ed3  xor     ecx, ecx
0x140014ed5  cmp     r8d, 80000022h
0x140014edc  setnz   cl
0x140014edf  mov     [rdi], ecx
0x140014ee1  mov     eax, ebx
0x140014ee3  mov     rcx, [rsp+68h+var_20]
0x140014ee8  xor     rcx, rsp; StackCookie
0x140014eeb  call    __security_check_cookie
0x140014ef0  lea     r11, [rsp+68h+var_18]
0x140014ef5  mov     rbx, [r11+30h]
0x140014ef9  mov     rbp, [r11+38h]
0x140014efd  mov     rsp, r11
0x140014f00  pop     r14
0x140014f02  pop     rdi
0x140014f03  pop     rsi
0x140014f04  retn
0x140014f05  lea     r9, [rsp+68h+var_30]
0x140014f0a  mov     edx, ebp
0x140014f0c  lea     r8, [rsp+68h+var_38]
0x140014f11  mov     ecx, r14d
0x140014f14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140014f19  mov     r8d, eax
0x140014f1c  test    eax, eax
0x140014f1e  jnz     short loc_140014F62
0x140014f20  mov     edx, dword ptr [rsp+68h+var_30+4]
0x140014f24  mov     ecx, edx
0x140014f26  mov     eax, [rsp+68h+var_28]
0x140014f2a  mov     [rsi+0Ch], eax
0x140014f2d  mov     eax, edx
0x140014f2f  shr     eax, 0Eh
0x140014f32  shr     ecx, 4
0x140014f35  and     eax, 3
0x140014f38  and     ecx, 3
0x140014f3b  mov     [rsi+8], eax
0x140014f3e  mov     [rsi], ecx
0x140014f40  mov     eax, edx
0x140014f42  mov     ecx, edx
0x140014f44  shr     eax, 6
0x140014f47  shr     ecx, 8
0x140014f4a  and     eax, ebx
0x140014f4c  and     cl, 3Fh
0x140014f4f  shr     edx, 7
0x140014f52  and     edx, ebx
0x140014f54  mov     [rsi+4], cl
0x140014f57  mov     [rsi+10h], edx
0x140014f5a  mov     [rsi+14h], eax
0x140014f5d  jmp     loc_140014ECE
0x140014f62  cmp     eax, 117h
0x140014f67  jnz     loc_140014ECC
0x140014f6d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x140014f71  shr     eax, 7
0x140014f74  and     eax, ebx
0x140014f76  mov     [rsi+10h], eax
0x140014f79  jmp     loc_140014ECE
```
