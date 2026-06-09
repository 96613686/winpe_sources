# wil_QueryFeatureState

- ea: `0x180012cf8`
- end: `0x180012e5e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000dc08`

## callees

- `0x180002240`
- `0x180012cf8`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012d94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012d94`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012d7d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012d7d`

## string_xrefs

- `0x180012d76`: `ntdll.dll`
- `0x180012d8a`: `RtlQueryFeatureConfiguration`

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
0x180012cf8  mov     [rsp+arg_10], rbx
0x180012cfd  mov     [rsp+arg_18], rbp
0x180012d02  push    rsi
0x180012d03  push    rdi
0x180012d04  push    r14
0x180012d06  sub     rsp, 50h
0x180012d0a  mov     rax, cs:__security_cookie
0x180012d11  xor     rax, rsp
0x180012d14  mov     [rsp+68h+var_20], rax
0x180012d19  mov     rdi, [rsp+68h+arg_20]
0x180012d21  mov     r14d, edx
0x180012d24  mov     rax, [rsp+68h+arg_28]
0x180012d2c  mov     rsi, rcx
0x180012d2f  test    rdi, rdi
0x180012d32  jz      short loc_180012D3A
0x180012d34  mov     dword ptr [rdi], 0
0x180012d3a  xor     ebp, ebp
0x180012d3c  mov     [rsp+68h+var_38], 0
0x180012d45  test    r8d, r8d
0x180012d48  mov     ebx, 1
0x180012d4d  mov     [rax], ebx
0x180012d4f  setz    bpl
0x180012d53  xor     eax, eax
0x180012d55  mov     [rsp+68h+var_30], rax
0x180012d5a  mov     [rsp+68h+var_28], eax
0x180012d5e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180012d65  test    rax, rax
0x180012d68  jnz     short loc_180012DE5
0x180012d6a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012d71  test    rax, rax
0x180012d74  jnz     short loc_180012D8A
0x180012d76  lea     rcx, ModuleName; "ntdll.dll"
0x180012d7d  call    cs:__imp_GetModuleHandleW
0x180012d83  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012d8a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180012d91  mov     rcx, rax; hModule
0x180012d94  call    cs:__imp_GetProcAddress
0x180012d9a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180012da1  test    rax, rax
0x180012da4  jnz     short loc_180012DE5
0x180012da6  mov     r8d, 0C0000139h
0x180012dac  xor     ebx, ebx
0x180012dae  test    rdi, rdi
0x180012db1  jz      short loc_180012DC1
0x180012db3  xor     ecx, ecx
0x180012db5  cmp     r8d, 80000022h
0x180012dbc  setnz   cl
0x180012dbf  mov     [rdi], ecx
0x180012dc1  mov     eax, ebx
0x180012dc3  mov     rcx, [rsp+68h+var_20]
0x180012dc8  xor     rcx, rsp; StackCookie
0x180012dcb  call    __security_check_cookie
0x180012dd0  lea     r11, [rsp+68h+var_18]
0x180012dd5  mov     rbx, [r11+30h]
0x180012dd9  mov     rbp, [r11+38h]
0x180012ddd  mov     rsp, r11
0x180012de0  pop     r14
0x180012de2  pop     rdi
0x180012de3  pop     rsi
0x180012de4  retn
0x180012de5  lea     r9, [rsp+68h+var_30]
0x180012dea  mov     edx, ebp
0x180012dec  lea     r8, [rsp+68h+var_38]
0x180012df1  mov     ecx, r14d
0x180012df4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012df9  mov     r8d, eax
0x180012dfc  test    eax, eax
0x180012dfe  jnz     short loc_180012E42
0x180012e00  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180012e04  mov     ecx, edx
0x180012e06  mov     eax, [rsp+68h+var_28]
0x180012e0a  mov     [rsi+0Ch], eax
0x180012e0d  mov     eax, edx
0x180012e0f  shr     eax, 0Eh
0x180012e12  shr     ecx, 4
0x180012e15  and     eax, 3
0x180012e18  and     ecx, 3
0x180012e1b  mov     [rsi+8], eax
0x180012e1e  mov     [rsi], ecx
0x180012e20  mov     eax, edx
0x180012e22  mov     ecx, edx
0x180012e24  shr     eax, 6
0x180012e27  shr     ecx, 8
0x180012e2a  and     eax, ebx
0x180012e2c  and     cl, 3Fh
0x180012e2f  shr     edx, 7
0x180012e32  and     edx, ebx
0x180012e34  mov     [rsi+4], cl
0x180012e37  mov     [rsi+10h], edx
0x180012e3a  mov     [rsi+14h], eax
0x180012e3d  jmp     loc_180012DAE
0x180012e42  cmp     eax, 117h
0x180012e47  jnz     loc_180012DAC
0x180012e4d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180012e51  shr     eax, 7
0x180012e54  and     eax, ebx
0x180012e56  mov     [rsi+10h], eax
0x180012e59  jmp     loc_180012DAE
```
