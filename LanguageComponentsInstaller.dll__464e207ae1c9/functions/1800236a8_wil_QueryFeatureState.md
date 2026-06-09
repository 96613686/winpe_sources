# wil_QueryFeatureState

- ea: `0x1800236a8`
- end: `0x18002380e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800187bc`
- `0x180027804`

## callees

- `0x180003520`
- `0x1800236a8`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023744`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180023744`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002372d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002372d`

## string_xrefs

- `0x180023726`: `ntdll.dll`
- `0x18002373a`: `RtlQueryFeatureConfiguration`

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
0x1800236a8  mov     [rsp+arg_10], rbx
0x1800236ad  mov     [rsp+arg_18], rbp
0x1800236b2  push    rsi
0x1800236b3  push    rdi
0x1800236b4  push    r14
0x1800236b6  sub     rsp, 50h
0x1800236ba  mov     rax, cs:__security_cookie
0x1800236c1  xor     rax, rsp
0x1800236c4  mov     [rsp+68h+var_20], rax
0x1800236c9  mov     rdi, [rsp+68h+arg_20]
0x1800236d1  mov     r14d, edx
0x1800236d4  mov     rax, [rsp+68h+arg_28]
0x1800236dc  mov     rsi, rcx
0x1800236df  test    rdi, rdi
0x1800236e2  jz      short loc_1800236EA
0x1800236e4  mov     dword ptr [rdi], 0
0x1800236ea  xor     ebp, ebp
0x1800236ec  mov     [rsp+68h+var_28], 0
0x1800236f5  test    r8d, r8d
0x1800236f8  mov     ebx, 1
0x1800236fd  mov     [rax], ebx
0x1800236ff  setz    bpl
0x180023703  xor     eax, eax
0x180023705  mov     [rsp+68h+var_38], rax
0x18002370a  mov     [rsp+68h+var_30], eax
0x18002370e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180023715  test    rax, rax
0x180023718  jnz     short loc_180023795
0x18002371a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180023721  test    rax, rax
0x180023724  jnz     short loc_18002373A
0x180023726  lea     rcx, ModuleName; "ntdll.dll"
0x18002372d  call    cs:__imp_GetModuleHandleW
0x180023733  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002373a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180023741  mov     rcx, rax; hModule
0x180023744  call    cs:__imp_GetProcAddress
0x18002374a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180023751  test    rax, rax
0x180023754  jnz     short loc_180023795
0x180023756  mov     r8d, 0C0000139h
0x18002375c  xor     ebx, ebx
0x18002375e  test    rdi, rdi
0x180023761  jz      short loc_180023771
0x180023763  xor     ecx, ecx
0x180023765  cmp     r8d, 80000022h
0x18002376c  setnz   cl
0x18002376f  mov     [rdi], ecx
0x180023771  mov     eax, ebx
0x180023773  mov     rcx, [rsp+68h+var_20]
0x180023778  xor     rcx, rsp; StackCookie
0x18002377b  call    __security_check_cookie
0x180023780  lea     r11, [rsp+68h+var_18]
0x180023785  mov     rbx, [r11+30h]
0x180023789  mov     rbp, [r11+38h]
0x18002378d  mov     rsp, r11
0x180023790  pop     r14
0x180023792  pop     rdi
0x180023793  pop     rsi
0x180023794  retn
0x180023795  lea     r9, [rsp+68h+var_38]
0x18002379a  mov     edx, ebp
0x18002379c  lea     r8, [rsp+68h+var_28]
0x1800237a1  mov     ecx, r14d
0x1800237a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800237a9  mov     r8d, eax
0x1800237ac  test    eax, eax
0x1800237ae  jnz     short loc_1800237F2
0x1800237b0  mov     edx, dword ptr [rsp+68h+var_38+4]
0x1800237b4  mov     ecx, edx
0x1800237b6  mov     eax, [rsp+68h+var_30]
0x1800237ba  mov     [rsi+0Ch], eax
0x1800237bd  mov     eax, edx
0x1800237bf  shr     eax, 0Eh
0x1800237c2  shr     ecx, 4
0x1800237c5  and     eax, 3
0x1800237c8  and     ecx, 3
0x1800237cb  mov     [rsi+8], eax
0x1800237ce  mov     [rsi], ecx
0x1800237d0  mov     eax, edx
0x1800237d2  mov     ecx, edx
0x1800237d4  shr     eax, 6
0x1800237d7  shr     ecx, 8
0x1800237da  and     eax, ebx
0x1800237dc  and     cl, 3Fh
0x1800237df  shr     edx, 7
0x1800237e2  and     edx, ebx
0x1800237e4  mov     [rsi+4], cl
0x1800237e7  mov     [rsi+10h], edx
0x1800237ea  mov     [rsi+14h], eax
0x1800237ed  jmp     loc_18002375E
0x1800237f2  cmp     eax, 117h
0x1800237f7  jnz     loc_18002375C
0x1800237fd  mov     eax, dword ptr [rsp+68h+var_38+4]
0x180023801  shr     eax, 7
0x180023804  and     eax, ebx
0x180023806  mov     [rsi+10h], eax
0x180023809  jmp     loc_18002375E
```
