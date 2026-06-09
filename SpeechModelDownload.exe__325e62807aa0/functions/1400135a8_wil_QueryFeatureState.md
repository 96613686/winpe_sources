# wil_QueryFeatureState

- ea: `0x1400135a8`
- end: `0x14001370e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140010084`

## callees

- `0x140002600`
- `0x1400135a8`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001362d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14001362d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140013644`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140013644`

## string_xrefs

- `0x140013626`: `ntdll.dll`
- `0x14001363a`: `RtlQueryFeatureConfiguration`

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
0x1400135a8  mov     [rsp+arg_10], rbx
0x1400135ad  mov     [rsp+arg_18], rbp
0x1400135b2  push    rsi
0x1400135b3  push    rdi
0x1400135b4  push    r14
0x1400135b6  sub     rsp, 50h
0x1400135ba  mov     rax, cs:__security_cookie
0x1400135c1  xor     rax, rsp
0x1400135c4  mov     [rsp+68h+var_20], rax
0x1400135c9  mov     rdi, [rsp+68h+arg_20]
0x1400135d1  mov     r14d, edx
0x1400135d4  mov     rax, [rsp+68h+arg_28]
0x1400135dc  mov     rsi, rcx
0x1400135df  test    rdi, rdi
0x1400135e2  jz      short loc_1400135EA
0x1400135e4  mov     dword ptr [rdi], 0
0x1400135ea  xor     ebp, ebp
0x1400135ec  mov     [rsp+68h+var_38], 0
0x1400135f5  test    r8d, r8d
0x1400135f8  mov     ebx, 1
0x1400135fd  mov     [rax], ebx
0x1400135ff  setz    bpl
0x140013603  xor     eax, eax
0x140013605  mov     [rsp+68h+var_30], rax
0x14001360a  mov     [rsp+68h+var_28], eax
0x14001360e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x140013615  test    rax, rax
0x140013618  jnz     short loc_140013695
0x14001361a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140013621  test    rax, rax
0x140013624  jnz     short loc_14001363A
0x140013626  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14001362d  call    cs:__imp_GetModuleHandleW
0x140013633  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001363a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x140013641  mov     rcx, rax; hModule
0x140013644  call    cs:__imp_GetProcAddress
0x14001364a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x140013651  test    rax, rax
0x140013654  jnz     short loc_140013695
0x140013656  mov     r8d, 0C0000139h
0x14001365c  xor     ebx, ebx
0x14001365e  test    rdi, rdi
0x140013661  jz      short loc_140013671
0x140013663  xor     ecx, ecx
0x140013665  cmp     r8d, 80000022h
0x14001366c  setnz   cl
0x14001366f  mov     [rdi], ecx
0x140013671  mov     eax, ebx
0x140013673  mov     rcx, [rsp+68h+var_20]
0x140013678  xor     rcx, rsp; StackCookie
0x14001367b  call    __security_check_cookie
0x140013680  lea     r11, [rsp+68h+var_18]
0x140013685  mov     rbx, [r11+30h]
0x140013689  mov     rbp, [r11+38h]
0x14001368d  mov     rsp, r11
0x140013690  pop     r14
0x140013692  pop     rdi
0x140013693  pop     rsi
0x140013694  retn
0x140013695  lea     r9, [rsp+68h+var_30]
0x14001369a  mov     edx, ebp
0x14001369c  lea     r8, [rsp+68h+var_38]
0x1400136a1  mov     ecx, r14d
0x1400136a4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400136a9  mov     r8d, eax
0x1400136ac  test    eax, eax
0x1400136ae  jnz     short loc_1400136F2
0x1400136b0  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1400136b4  mov     ecx, edx
0x1400136b6  mov     eax, [rsp+68h+var_28]
0x1400136ba  mov     [rsi+0Ch], eax
0x1400136bd  mov     eax, edx
0x1400136bf  shr     eax, 0Eh
0x1400136c2  shr     ecx, 4
0x1400136c5  and     eax, 3
0x1400136c8  and     ecx, 3
0x1400136cb  mov     [rsi+8], eax
0x1400136ce  mov     [rsi], ecx
0x1400136d0  mov     eax, edx
0x1400136d2  mov     ecx, edx
0x1400136d4  shr     eax, 6
0x1400136d7  shr     ecx, 8
0x1400136da  and     eax, ebx
0x1400136dc  and     cl, 3Fh
0x1400136df  shr     edx, 7
0x1400136e2  and     edx, ebx
0x1400136e4  mov     [rsi+4], cl
0x1400136e7  mov     [rsi+10h], edx
0x1400136ea  mov     [rsi+14h], eax
0x1400136ed  jmp     loc_14001365E
0x1400136f2  cmp     eax, 117h
0x1400136f7  jnz     loc_14001365C
0x1400136fd  mov     eax, dword ptr [rsp+68h+var_30+4]
0x140013701  shr     eax, 7
0x140013704  and     eax, ebx
0x140013706  mov     [rsi+10h], eax
0x140013709  jmp     loc_14001365E
```
