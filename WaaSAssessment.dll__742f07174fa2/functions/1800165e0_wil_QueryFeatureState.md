# wil_QueryFeatureState

- ea: `0x1800165e0`
- end: `0x180016746`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18001364c`

## callees

- `0x1800165e0`
- `0x180019760`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001667c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001667c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016665`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016665`

## string_xrefs

- `0x18001665e`: `ntdll.dll`
- `0x180016672`: `RtlQueryFeatureConfiguration`

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
0x1800165e0  mov     [rsp+arg_10], rbx
0x1800165e5  mov     [rsp+arg_18], rbp
0x1800165ea  push    rsi
0x1800165eb  push    rdi
0x1800165ec  push    r14
0x1800165ee  sub     rsp, 50h
0x1800165f2  mov     rax, cs:__security_cookie
0x1800165f9  xor     rax, rsp
0x1800165fc  mov     [rsp+68h+var_20], rax
0x180016601  mov     rdi, [rsp+68h+arg_20]
0x180016609  mov     r14d, edx
0x18001660c  mov     rax, [rsp+68h+arg_28]
0x180016614  mov     rsi, rcx
0x180016617  test    rdi, rdi
0x18001661a  jz      short loc_180016622
0x18001661c  mov     dword ptr [rdi], 0
0x180016622  xor     ebp, ebp
0x180016624  mov     [rsp+68h+var_38], 0
0x18001662d  test    r8d, r8d
0x180016630  mov     ebx, 1
0x180016635  mov     [rax], ebx
0x180016637  setz    bpl
0x18001663b  xor     eax, eax
0x18001663d  mov     [rsp+68h+var_30], rax
0x180016642  mov     [rsp+68h+var_28], eax
0x180016646  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001664d  test    rax, rax
0x180016650  jnz     short loc_1800166CD
0x180016652  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016659  test    rax, rax
0x18001665c  jnz     short loc_180016672
0x18001665e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180016665  call    cs:__imp_GetModuleHandleW
0x18001666b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016672  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180016679  mov     rcx, rax; hModule
0x18001667c  call    cs:__imp_GetProcAddress
0x180016682  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180016689  test    rax, rax
0x18001668c  jnz     short loc_1800166CD
0x18001668e  mov     r8d, 0C0000139h
0x180016694  xor     ebx, ebx
0x180016696  test    rdi, rdi
0x180016699  jz      short loc_1800166A9
0x18001669b  xor     ecx, ecx
0x18001669d  cmp     r8d, 80000022h
0x1800166a4  setnz   cl
0x1800166a7  mov     [rdi], ecx
0x1800166a9  mov     eax, ebx
0x1800166ab  mov     rcx, [rsp+68h+var_20]
0x1800166b0  xor     rcx, rsp; StackCookie
0x1800166b3  call    __security_check_cookie
0x1800166b8  lea     r11, [rsp+68h+var_18]
0x1800166bd  mov     rbx, [r11+30h]
0x1800166c1  mov     rbp, [r11+38h]
0x1800166c5  mov     rsp, r11
0x1800166c8  pop     r14
0x1800166ca  pop     rdi
0x1800166cb  pop     rsi
0x1800166cc  retn
0x1800166cd  lea     r9, [rsp+68h+var_30]
0x1800166d2  mov     edx, ebp
0x1800166d4  lea     r8, [rsp+68h+var_38]
0x1800166d9  mov     ecx, r14d
0x1800166dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800166e1  mov     r8d, eax
0x1800166e4  test    eax, eax
0x1800166e6  jnz     short loc_18001672A
0x1800166e8  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800166ec  mov     ecx, edx
0x1800166ee  mov     eax, [rsp+68h+var_28]
0x1800166f2  mov     [rsi+0Ch], eax
0x1800166f5  mov     eax, edx
0x1800166f7  shr     eax, 0Eh
0x1800166fa  shr     ecx, 4
0x1800166fd  and     eax, 3
0x180016700  and     ecx, 3
0x180016703  mov     [rsi+8], eax
0x180016706  mov     [rsi], ecx
0x180016708  mov     eax, edx
0x18001670a  mov     ecx, edx
0x18001670c  shr     eax, 6
0x18001670f  shr     ecx, 8
0x180016712  and     eax, ebx
0x180016714  and     cl, 3Fh
0x180016717  shr     edx, 7
0x18001671a  and     edx, ebx
0x18001671c  mov     [rsi+4], cl
0x18001671f  mov     [rsi+10h], edx
0x180016722  mov     [rsi+14h], eax
0x180016725  jmp     loc_180016696
0x18001672a  cmp     eax, 117h
0x18001672f  jnz     loc_180016694
0x180016735  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180016739  shr     eax, 7
0x18001673c  and     eax, ebx
0x18001673e  mov     [rsi+10h], eax
0x180016741  jmp     loc_180016696
```
