# wil_QueryFeatureState

- ea: `0x14000a888`
- end: `0x14000a9ee`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400067e4`

## callees

- `0x140001ba0`
- `0x14000a888`
- `0x1400a8010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a90d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000a90d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a924`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000a924`

## string_xrefs

- `0x14000a906`: `ntdll.dll`
- `0x14000a91a`: `RtlQueryFeatureConfiguration`

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
0x14000a888  mov     [rsp+arg_10], rbx
0x14000a88d  mov     [rsp+arg_18], rbp
0x14000a892  push    rsi
0x14000a893  push    rdi
0x14000a894  push    r14
0x14000a896  sub     rsp, 50h
0x14000a89a  mov     rax, cs:__security_cookie
0x14000a8a1  xor     rax, rsp
0x14000a8a4  mov     [rsp+68h+var_20], rax
0x14000a8a9  mov     rdi, [rsp+68h+arg_20]
0x14000a8b1  mov     r14d, edx
0x14000a8b4  mov     rax, [rsp+68h+arg_28]
0x14000a8bc  mov     rsi, rcx
0x14000a8bf  test    rdi, rdi
0x14000a8c2  jz      short loc_14000A8CA
0x14000a8c4  mov     dword ptr [rdi], 0
0x14000a8ca  xor     ebp, ebp
0x14000a8cc  mov     [rsp+68h+var_38], 0
0x14000a8d5  test    r8d, r8d
0x14000a8d8  mov     ebx, 1
0x14000a8dd  mov     [rax], ebx
0x14000a8df  setz    bpl
0x14000a8e3  xor     eax, eax
0x14000a8e5  mov     [rsp+68h+var_30], rax
0x14000a8ea  mov     [rsp+68h+var_28], eax
0x14000a8ee  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000a8f5  test    rax, rax
0x14000a8f8  jnz     short loc_14000A975
0x14000a8fa  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a901  test    rax, rax
0x14000a904  jnz     short loc_14000A91A
0x14000a906  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000a90d  call    cs:__imp_GetModuleHandleW
0x14000a913  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a91a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000a921  mov     rcx, rax; hModule
0x14000a924  call    cs:__imp_GetProcAddress
0x14000a92a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000a931  test    rax, rax
0x14000a934  jnz     short loc_14000A975
0x14000a936  mov     r8d, 0C0000139h
0x14000a93c  xor     ebx, ebx
0x14000a93e  test    rdi, rdi
0x14000a941  jz      short loc_14000A951
0x14000a943  xor     ecx, ecx
0x14000a945  cmp     r8d, 80000022h
0x14000a94c  setnz   cl
0x14000a94f  mov     [rdi], ecx
0x14000a951  mov     eax, ebx
0x14000a953  mov     rcx, [rsp+68h+var_20]
0x14000a958  xor     rcx, rsp; StackCookie
0x14000a95b  call    __security_check_cookie
0x14000a960  lea     r11, [rsp+68h+var_18]
0x14000a965  mov     rbx, [r11+30h]
0x14000a969  mov     rbp, [r11+38h]
0x14000a96d  mov     rsp, r11
0x14000a970  pop     r14
0x14000a972  pop     rdi
0x14000a973  pop     rsi
0x14000a974  retn
0x14000a975  lea     r9, [rsp+68h+var_30]
0x14000a97a  mov     edx, ebp
0x14000a97c  lea     r8, [rsp+68h+var_38]
0x14000a981  mov     ecx, r14d
0x14000a984  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000a989  mov     r8d, eax
0x14000a98c  test    eax, eax
0x14000a98e  jnz     short loc_14000A9D2
0x14000a990  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000a994  mov     ecx, edx
0x14000a996  mov     eax, [rsp+68h+var_28]
0x14000a99a  mov     [rsi+0Ch], eax
0x14000a99d  mov     eax, edx
0x14000a99f  shr     eax, 0Eh
0x14000a9a2  shr     ecx, 4
0x14000a9a5  and     eax, 3
0x14000a9a8  and     ecx, 3
0x14000a9ab  mov     [rsi+8], eax
0x14000a9ae  mov     [rsi], ecx
0x14000a9b0  mov     eax, edx
0x14000a9b2  mov     ecx, edx
0x14000a9b4  shr     eax, 6
0x14000a9b7  shr     ecx, 8
0x14000a9ba  and     eax, ebx
0x14000a9bc  and     cl, 3Fh
0x14000a9bf  shr     edx, 7
0x14000a9c2  and     edx, ebx
0x14000a9c4  mov     [rsi+4], cl
0x14000a9c7  mov     [rsi+10h], edx
0x14000a9ca  mov     [rsi+14h], eax
0x14000a9cd  jmp     loc_14000A93E
0x14000a9d2  cmp     eax, 117h
0x14000a9d7  jnz     loc_14000A93C
0x14000a9dd  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000a9e1  shr     eax, 7
0x14000a9e4  and     eax, ebx
0x14000a9e6  mov     [rsi+10h], eax
0x14000a9e9  jmp     loc_14000A93E
```
