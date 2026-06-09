# wil_QueryFeatureState

- ea: `0x18000954c`
- end: `0x1800096b2`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180005890`

## callees

- `0x180001630`
- `0x18000954c`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800095e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800095e8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800095d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800095d1`

## string_xrefs

- `0x1800095ca`: `ntdll.dll`
- `0x1800095de`: `RtlQueryFeatureConfiguration`

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
0x18000954c  mov     [rsp+arg_10], rbx
0x180009551  mov     [rsp+arg_18], rbp
0x180009556  push    rsi
0x180009557  push    rdi
0x180009558  push    r14
0x18000955a  sub     rsp, 50h
0x18000955e  mov     rax, cs:__security_cookie
0x180009565  xor     rax, rsp
0x180009568  mov     [rsp+68h+var_20], rax
0x18000956d  mov     rdi, [rsp+68h+arg_20]
0x180009575  mov     r14d, edx
0x180009578  mov     rax, [rsp+68h+arg_28]
0x180009580  mov     rsi, rcx
0x180009583  test    rdi, rdi
0x180009586  jz      short loc_18000958E
0x180009588  mov     dword ptr [rdi], 0
0x18000958e  xor     ebp, ebp
0x180009590  mov     [rsp+68h+var_38], 0
0x180009599  test    r8d, r8d
0x18000959c  mov     ebx, 1
0x1800095a1  mov     [rax], ebx
0x1800095a3  setz    bpl
0x1800095a7  xor     eax, eax
0x1800095a9  mov     [rsp+68h+var_30], rax
0x1800095ae  mov     [rsp+68h+var_28], eax
0x1800095b2  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800095b9  test    rax, rax
0x1800095bc  jnz     short loc_180009639
0x1800095be  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800095c5  test    rax, rax
0x1800095c8  jnz     short loc_1800095DE
0x1800095ca  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800095d1  call    cs:__imp_GetModuleHandleW
0x1800095d7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800095de  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800095e5  mov     rcx, rax; hModule
0x1800095e8  call    cs:__imp_GetProcAddress
0x1800095ee  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800095f5  test    rax, rax
0x1800095f8  jnz     short loc_180009639
0x1800095fa  mov     r8d, 0C0000139h
0x180009600  xor     ebx, ebx
0x180009602  test    rdi, rdi
0x180009605  jz      short loc_180009615
0x180009607  xor     ecx, ecx
0x180009609  cmp     r8d, 80000022h
0x180009610  setnz   cl
0x180009613  mov     [rdi], ecx
0x180009615  mov     eax, ebx
0x180009617  mov     rcx, [rsp+68h+var_20]
0x18000961c  xor     rcx, rsp; StackCookie
0x18000961f  call    __security_check_cookie
0x180009624  lea     r11, [rsp+68h+var_18]
0x180009629  mov     rbx, [r11+30h]
0x18000962d  mov     rbp, [r11+38h]
0x180009631  mov     rsp, r11
0x180009634  pop     r14
0x180009636  pop     rdi
0x180009637  pop     rsi
0x180009638  retn
0x180009639  lea     r9, [rsp+68h+var_30]
0x18000963e  mov     edx, ebp
0x180009640  lea     r8, [rsp+68h+var_38]
0x180009645  mov     ecx, r14d
0x180009648  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000964d  mov     r8d, eax
0x180009650  test    eax, eax
0x180009652  jnz     short loc_180009696
0x180009654  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180009658  mov     ecx, edx
0x18000965a  mov     eax, [rsp+68h+var_28]
0x18000965e  mov     [rsi+0Ch], eax
0x180009661  mov     eax, edx
0x180009663  shr     eax, 0Eh
0x180009666  shr     ecx, 4
0x180009669  and     eax, 3
0x18000966c  and     ecx, 3
0x18000966f  mov     [rsi+8], eax
0x180009672  mov     [rsi], ecx
0x180009674  mov     eax, edx
0x180009676  mov     ecx, edx
0x180009678  shr     eax, 6
0x18000967b  shr     ecx, 8
0x18000967e  and     eax, ebx
0x180009680  and     cl, 3Fh
0x180009683  shr     edx, 7
0x180009686  and     edx, ebx
0x180009688  mov     [rsi+4], cl
0x18000968b  mov     [rsi+10h], edx
0x18000968e  mov     [rsi+14h], eax
0x180009691  jmp     loc_180009602
0x180009696  cmp     eax, 117h
0x18000969b  jnz     loc_180009600
0x1800096a1  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800096a5  shr     eax, 7
0x1800096a8  and     eax, ebx
0x1800096aa  mov     [rsi+10h], eax
0x1800096ad  jmp     loc_180009602
```
