# wil_QueryFeatureState

- ea: `0x18001353c`
- end: `0x1800136a2`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000de7c`

## callees

- `0x1800045b0`
- `0x18001353c`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800135c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800135c1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800135d8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800135d8`

## string_xrefs

- `0x1800135ba`: `ntdll.dll`
- `0x1800135ce`: `RtlQueryFeatureConfiguration`

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
0x18001353c  mov     [rsp+arg_10], rbx
0x180013541  mov     [rsp+arg_18], rbp
0x180013546  push    rsi
0x180013547  push    rdi
0x180013548  push    r14
0x18001354a  sub     rsp, 50h
0x18001354e  mov     rax, cs:__security_cookie
0x180013555  xor     rax, rsp
0x180013558  mov     [rsp+68h+var_20], rax
0x18001355d  mov     rdi, [rsp+68h+arg_20]
0x180013565  mov     r14d, edx
0x180013568  mov     rax, [rsp+68h+arg_28]
0x180013570  mov     rsi, rcx
0x180013573  test    rdi, rdi
0x180013576  jz      short loc_18001357E
0x180013578  mov     dword ptr [rdi], 0
0x18001357e  xor     ebp, ebp
0x180013580  mov     [rsp+68h+var_38], 0
0x180013589  test    r8d, r8d
0x18001358c  mov     ebx, 1
0x180013591  mov     [rax], ebx
0x180013593  setz    bpl
0x180013597  xor     eax, eax
0x180013599  mov     [rsp+68h+var_30], rax
0x18001359e  mov     [rsp+68h+var_28], eax
0x1800135a2  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800135a9  test    rax, rax
0x1800135ac  jnz     short loc_180013629
0x1800135ae  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800135b5  test    rax, rax
0x1800135b8  jnz     short loc_1800135CE
0x1800135ba  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800135c1  call    cs:__imp_GetModuleHandleW
0x1800135c7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800135ce  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800135d5  mov     rcx, rax; hModule
0x1800135d8  call    cs:__imp_GetProcAddress
0x1800135de  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800135e5  test    rax, rax
0x1800135e8  jnz     short loc_180013629
0x1800135ea  mov     r8d, 0C0000139h
0x1800135f0  xor     ebx, ebx
0x1800135f2  test    rdi, rdi
0x1800135f5  jz      short loc_180013605
0x1800135f7  xor     ecx, ecx
0x1800135f9  cmp     r8d, 80000022h
0x180013600  setnz   cl
0x180013603  mov     [rdi], ecx
0x180013605  mov     eax, ebx
0x180013607  mov     rcx, [rsp+68h+var_20]
0x18001360c  xor     rcx, rsp; StackCookie
0x18001360f  call    __security_check_cookie
0x180013614  lea     r11, [rsp+68h+var_18]
0x180013619  mov     rbx, [r11+30h]
0x18001361d  mov     rbp, [r11+38h]
0x180013621  mov     rsp, r11
0x180013624  pop     r14
0x180013626  pop     rdi
0x180013627  pop     rsi
0x180013628  retn
0x180013629  lea     r9, [rsp+68h+var_30]
0x18001362e  mov     edx, ebp
0x180013630  lea     r8, [rsp+68h+var_38]
0x180013635  mov     ecx, r14d
0x180013638  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001363d  mov     r8d, eax
0x180013640  test    eax, eax
0x180013642  jnz     short loc_180013686
0x180013644  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180013648  mov     ecx, edx
0x18001364a  mov     eax, [rsp+68h+var_28]
0x18001364e  mov     [rsi+0Ch], eax
0x180013651  mov     eax, edx
0x180013653  shr     eax, 0Eh
0x180013656  shr     ecx, 4
0x180013659  and     eax, 3
0x18001365c  and     ecx, 3
0x18001365f  mov     [rsi+8], eax
0x180013662  mov     [rsi], ecx
0x180013664  mov     eax, edx
0x180013666  mov     ecx, edx
0x180013668  shr     eax, 6
0x18001366b  shr     ecx, 8
0x18001366e  and     eax, ebx
0x180013670  and     cl, 3Fh
0x180013673  shr     edx, 7
0x180013676  and     edx, ebx
0x180013678  mov     [rsi+4], cl
0x18001367b  mov     [rsi+10h], edx
0x18001367e  mov     [rsi+14h], eax
0x180013681  jmp     loc_1800135F2
0x180013686  cmp     eax, 117h
0x18001368b  jnz     loc_1800135F0
0x180013691  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180013695  shr     eax, 7
0x180013698  and     eax, ebx
0x18001369a  mov     [rsi+10h], eax
0x18001369d  jmp     loc_1800135F2
```
