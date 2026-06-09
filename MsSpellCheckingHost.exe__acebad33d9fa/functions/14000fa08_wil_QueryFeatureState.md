# wil_QueryFeatureState

- ea: `0x14000fa08`
- end: `0x14000fb6e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000b4cc`

## callees

- `0x14000fa08`
- `0x140011e10`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fa8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000fa8d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000faa4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000faa4`

## string_xrefs

- `0x14000fa86`: `ntdll.dll`
- `0x14000fa9a`: `RtlQueryFeatureConfiguration`

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
0x14000fa08  mov     [rsp+arg_10], rbx
0x14000fa0d  mov     [rsp+arg_18], rbp
0x14000fa12  push    rsi
0x14000fa13  push    rdi
0x14000fa14  push    r14
0x14000fa16  sub     rsp, 50h
0x14000fa1a  mov     rax, cs:__security_cookie
0x14000fa21  xor     rax, rsp
0x14000fa24  mov     [rsp+68h+var_20], rax
0x14000fa29  mov     rdi, [rsp+68h+arg_20]
0x14000fa31  mov     r14d, edx
0x14000fa34  mov     rax, [rsp+68h+arg_28]
0x14000fa3c  mov     rsi, rcx
0x14000fa3f  test    rdi, rdi
0x14000fa42  jz      short loc_14000FA4A
0x14000fa44  mov     dword ptr [rdi], 0
0x14000fa4a  xor     ebp, ebp
0x14000fa4c  mov     [rsp+68h+var_38], 0
0x14000fa55  test    r8d, r8d
0x14000fa58  mov     ebx, 1
0x14000fa5d  mov     [rax], ebx
0x14000fa5f  setz    bpl
0x14000fa63  xor     eax, eax
0x14000fa65  mov     [rsp+68h+var_30], rax
0x14000fa6a  mov     [rsp+68h+var_28], eax
0x14000fa6e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000fa75  test    rax, rax
0x14000fa78  jnz     short loc_14000FAF5
0x14000fa7a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000fa81  test    rax, rax
0x14000fa84  jnz     short loc_14000FA9A
0x14000fa86  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000fa8d  call    cs:__imp_GetModuleHandleW
0x14000fa93  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000fa9a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000faa1  mov     rcx, rax; hModule
0x14000faa4  call    cs:__imp_GetProcAddress
0x14000faaa  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000fab1  test    rax, rax
0x14000fab4  jnz     short loc_14000FAF5
0x14000fab6  mov     r8d, 0C0000139h
0x14000fabc  xor     ebx, ebx
0x14000fabe  test    rdi, rdi
0x14000fac1  jz      short loc_14000FAD1
0x14000fac3  xor     ecx, ecx
0x14000fac5  cmp     r8d, 80000022h
0x14000facc  setnz   cl
0x14000facf  mov     [rdi], ecx
0x14000fad1  mov     eax, ebx
0x14000fad3  mov     rcx, [rsp+68h+var_20]
0x14000fad8  xor     rcx, rsp; StackCookie
0x14000fadb  call    __security_check_cookie
0x14000fae0  lea     r11, [rsp+68h+var_18]
0x14000fae5  mov     rbx, [r11+30h]
0x14000fae9  mov     rbp, [r11+38h]
0x14000faed  mov     rsp, r11
0x14000faf0  pop     r14
0x14000faf2  pop     rdi
0x14000faf3  pop     rsi
0x14000faf4  retn
0x14000faf5  lea     r9, [rsp+68h+var_30]
0x14000fafa  mov     edx, ebp
0x14000fafc  lea     r8, [rsp+68h+var_38]
0x14000fb01  mov     ecx, r14d
0x14000fb04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000fb09  mov     r8d, eax
0x14000fb0c  test    eax, eax
0x14000fb0e  jnz     short loc_14000FB52
0x14000fb10  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000fb14  mov     ecx, edx
0x14000fb16  mov     eax, [rsp+68h+var_28]
0x14000fb1a  mov     [rsi+0Ch], eax
0x14000fb1d  mov     eax, edx
0x14000fb1f  shr     eax, 0Eh
0x14000fb22  shr     ecx, 4
0x14000fb25  and     eax, 3
0x14000fb28  and     ecx, 3
0x14000fb2b  mov     [rsi+8], eax
0x14000fb2e  mov     [rsi], ecx
0x14000fb30  mov     eax, edx
0x14000fb32  mov     ecx, edx
0x14000fb34  shr     eax, 6
0x14000fb37  shr     ecx, 8
0x14000fb3a  and     eax, ebx
0x14000fb3c  and     cl, 3Fh
0x14000fb3f  shr     edx, 7
0x14000fb42  and     edx, ebx
0x14000fb44  mov     [rsi+4], cl
0x14000fb47  mov     [rsi+10h], edx
0x14000fb4a  mov     [rsi+14h], eax
0x14000fb4d  jmp     loc_14000FABE
0x14000fb52  cmp     eax, 117h
0x14000fb57  jnz     loc_14000FABC
0x14000fb5d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000fb61  shr     eax, 7
0x14000fb64  and     eax, ebx
0x14000fb66  mov     [rsi+10h], eax
0x14000fb69  jmp     loc_14000FABE
```
