# wil_QueryFeatureState

- ea: `0x180015df8`
- end: `0x180015f5e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800134dc`

## callees

- `0x1800026b0`
- `0x180015df8`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015e7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015e7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e94`

## string_xrefs

- `0x180015e76`: `ntdll.dll`
- `0x180015e8a`: `RtlQueryFeatureConfiguration`

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
0x180015df8  mov     [rsp+arg_10], rbx
0x180015dfd  mov     [rsp+arg_18], rbp
0x180015e02  push    rsi
0x180015e03  push    rdi
0x180015e04  push    r14
0x180015e06  sub     rsp, 50h
0x180015e0a  mov     rax, cs:__security_cookie
0x180015e11  xor     rax, rsp
0x180015e14  mov     [rsp+68h+var_20], rax
0x180015e19  mov     rdi, [rsp+68h+arg_20]
0x180015e21  mov     r14d, edx
0x180015e24  mov     rax, [rsp+68h+arg_28]
0x180015e2c  mov     rsi, rcx
0x180015e2f  test    rdi, rdi
0x180015e32  jz      short loc_180015E3A
0x180015e34  mov     dword ptr [rdi], 0
0x180015e3a  xor     ebp, ebp
0x180015e3c  mov     [rsp+68h+var_38], 0
0x180015e45  test    r8d, r8d
0x180015e48  mov     ebx, 1
0x180015e4d  mov     [rax], ebx
0x180015e4f  setz    bpl
0x180015e53  xor     eax, eax
0x180015e55  mov     [rsp+68h+var_30], rax
0x180015e5a  mov     [rsp+68h+var_28], eax
0x180015e5e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180015e65  test    rax, rax
0x180015e68  jnz     short loc_180015EE5
0x180015e6a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015e71  test    rax, rax
0x180015e74  jnz     short loc_180015E8A
0x180015e76  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180015e7d  call    cs:__imp_GetModuleHandleW
0x180015e83  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015e8a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180015e91  mov     rcx, rax; hModule
0x180015e94  call    cs:__imp_GetProcAddress
0x180015e9a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180015ea1  test    rax, rax
0x180015ea4  jnz     short loc_180015EE5
0x180015ea6  mov     r8d, 0C0000139h
0x180015eac  xor     ebx, ebx
0x180015eae  test    rdi, rdi
0x180015eb1  jz      short loc_180015EC1
0x180015eb3  xor     ecx, ecx
0x180015eb5  cmp     r8d, 80000022h
0x180015ebc  setnz   cl
0x180015ebf  mov     [rdi], ecx
0x180015ec1  mov     eax, ebx
0x180015ec3  mov     rcx, [rsp+68h+var_20]
0x180015ec8  xor     rcx, rsp; StackCookie
0x180015ecb  call    __security_check_cookie
0x180015ed0  lea     r11, [rsp+68h+var_18]
0x180015ed5  mov     rbx, [r11+30h]
0x180015ed9  mov     rbp, [r11+38h]
0x180015edd  mov     rsp, r11
0x180015ee0  pop     r14
0x180015ee2  pop     rdi
0x180015ee3  pop     rsi
0x180015ee4  retn
0x180015ee5  lea     r9, [rsp+68h+var_30]
0x180015eea  mov     edx, ebp
0x180015eec  lea     r8, [rsp+68h+var_38]
0x180015ef1  mov     ecx, r14d
0x180015ef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ef9  mov     r8d, eax
0x180015efc  test    eax, eax
0x180015efe  jnz     short loc_180015F42
0x180015f00  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180015f04  mov     ecx, edx
0x180015f06  mov     eax, [rsp+68h+var_28]
0x180015f0a  mov     [rsi+0Ch], eax
0x180015f0d  mov     eax, edx
0x180015f0f  shr     eax, 0Eh
0x180015f12  shr     ecx, 4
0x180015f15  and     eax, 3
0x180015f18  and     ecx, 3
0x180015f1b  mov     [rsi+8], eax
0x180015f1e  mov     [rsi], ecx
0x180015f20  mov     eax, edx
0x180015f22  mov     ecx, edx
0x180015f24  shr     eax, 6
0x180015f27  shr     ecx, 8
0x180015f2a  and     eax, ebx
0x180015f2c  and     cl, 3Fh
0x180015f2f  shr     edx, 7
0x180015f32  and     edx, ebx
0x180015f34  mov     [rsi+4], cl
0x180015f37  mov     [rsi+10h], edx
0x180015f3a  mov     [rsi+14h], eax
0x180015f3d  jmp     loc_180015EAE
0x180015f42  cmp     eax, 117h
0x180015f47  jnz     loc_180015EAC
0x180015f4d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180015f51  shr     eax, 7
0x180015f54  and     eax, ebx
0x180015f56  mov     [rsi+10h], eax
0x180015f59  jmp     loc_180015EAE
```
