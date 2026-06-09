# wil_QueryFeatureState

- ea: `0x18001688c`
- end: `0x1800169f2`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180013d70`

## callees

- `0x180001630`
- `0x18001688c`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016911`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016911`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016928`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016928`

## string_xrefs

- `0x18001690a`: `ntdll.dll`
- `0x18001691e`: `RtlQueryFeatureConfiguration`

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
0x18001688c  mov     [rsp+arg_10], rbx
0x180016891  mov     [rsp+arg_18], rbp
0x180016896  push    rsi
0x180016897  push    rdi
0x180016898  push    r14
0x18001689a  sub     rsp, 50h
0x18001689e  mov     rax, cs:__security_cookie
0x1800168a5  xor     rax, rsp
0x1800168a8  mov     [rsp+68h+var_20], rax
0x1800168ad  mov     rdi, [rsp+68h+arg_20]
0x1800168b5  mov     r14d, edx
0x1800168b8  mov     rax, [rsp+68h+arg_28]
0x1800168c0  mov     rsi, rcx
0x1800168c3  test    rdi, rdi
0x1800168c6  jz      short loc_1800168CE
0x1800168c8  mov     dword ptr [rdi], 0
0x1800168ce  xor     ebp, ebp
0x1800168d0  mov     [rsp+68h+var_38], 0
0x1800168d9  test    r8d, r8d
0x1800168dc  mov     ebx, 1
0x1800168e1  mov     [rax], ebx
0x1800168e3  setz    bpl
0x1800168e7  xor     eax, eax
0x1800168e9  mov     [rsp+68h+var_30], rax
0x1800168ee  mov     [rsp+68h+var_28], eax
0x1800168f2  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800168f9  test    rax, rax
0x1800168fc  jnz     short loc_180016979
0x1800168fe  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016905  test    rax, rax
0x180016908  jnz     short loc_18001691E
0x18001690a  lea     rcx, ModuleName; "ntdll.dll"
0x180016911  call    cs:__imp_GetModuleHandleW
0x180016917  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001691e  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180016925  mov     rcx, rax; hModule
0x180016928  call    cs:__imp_GetProcAddress
0x18001692e  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180016935  test    rax, rax
0x180016938  jnz     short loc_180016979
0x18001693a  mov     r8d, 0C0000139h
0x180016940  xor     ebx, ebx
0x180016942  test    rdi, rdi
0x180016945  jz      short loc_180016955
0x180016947  xor     ecx, ecx
0x180016949  cmp     r8d, 80000022h
0x180016950  setnz   cl
0x180016953  mov     [rdi], ecx
0x180016955  mov     eax, ebx
0x180016957  mov     rcx, [rsp+68h+var_20]
0x18001695c  xor     rcx, rsp; StackCookie
0x18001695f  call    __security_check_cookie
0x180016964  lea     r11, [rsp+68h+var_18]
0x180016969  mov     rbx, [r11+30h]
0x18001696d  mov     rbp, [r11+38h]
0x180016971  mov     rsp, r11
0x180016974  pop     r14
0x180016976  pop     rdi
0x180016977  pop     rsi
0x180016978  retn
0x180016979  lea     r9, [rsp+68h+var_30]
0x18001697e  mov     edx, ebp
0x180016980  lea     r8, [rsp+68h+var_38]
0x180016985  mov     ecx, r14d
0x180016988  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001698d  mov     r8d, eax
0x180016990  test    eax, eax
0x180016992  jnz     short loc_1800169D6
0x180016994  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180016998  mov     ecx, edx
0x18001699a  mov     eax, [rsp+68h+var_28]
0x18001699e  mov     [rsi+0Ch], eax
0x1800169a1  mov     eax, edx
0x1800169a3  shr     eax, 0Eh
0x1800169a6  shr     ecx, 4
0x1800169a9  and     eax, 3
0x1800169ac  and     ecx, 3
0x1800169af  mov     [rsi+8], eax
0x1800169b2  mov     [rsi], ecx
0x1800169b4  mov     eax, edx
0x1800169b6  mov     ecx, edx
0x1800169b8  shr     eax, 6
0x1800169bb  shr     ecx, 8
0x1800169be  and     eax, ebx
0x1800169c0  and     cl, 3Fh
0x1800169c3  shr     edx, 7
0x1800169c6  and     edx, ebx
0x1800169c8  mov     [rsi+4], cl
0x1800169cb  mov     [rsi+10h], edx
0x1800169ce  mov     [rsi+14h], eax
0x1800169d1  jmp     loc_180016942
0x1800169d6  cmp     eax, 117h
0x1800169db  jnz     loc_180016940
0x1800169e1  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800169e5  shr     eax, 7
0x1800169e8  and     eax, ebx
0x1800169ea  mov     [rsi+10h], eax
0x1800169ed  jmp     loc_180016942
```
