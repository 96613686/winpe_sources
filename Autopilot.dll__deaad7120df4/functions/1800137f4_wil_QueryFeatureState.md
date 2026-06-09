# wil_QueryFeatureState

- ea: `0x1800137f4`
- end: `0x18001396b`
- name: `wil_QueryFeatureState`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000def4`

## callees

- `0x1800045d0`
- `0x1800137f4`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001387d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001387d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001389a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001389a`

## string_xrefs

- `0x180013876`: `ntdll.dll`
- `0x180013890`: `RtlQueryFeatureConfiguration`

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
0x1800137f4  mov     [rsp+arg_10], rbx
0x1800137f9  mov     [rsp+arg_18], rbp
0x1800137fe  push    rsi
0x1800137ff  push    rdi
0x180013800  push    r14
0x180013802  sub     rsp, 50h
0x180013806  mov     rax, cs:__security_cookie
0x18001380d  xor     rax, rsp
0x180013810  mov     [rsp+68h+var_20], rax
0x180013815  mov     rdi, [rsp+68h+arg_20]
0x18001381d  mov     r14d, edx
0x180013820  mov     rax, [rsp+68h+arg_28]
0x180013828  mov     rsi, rcx
0x18001382b  test    rdi, rdi
0x18001382e  jz      short loc_180013836
0x180013830  mov     dword ptr [rdi], 0
0x180013836  xor     ebp, ebp
0x180013838  mov     [rsp+68h+var_38], 0
0x180013841  test    r8d, r8d
0x180013844  mov     ebx, 1
0x180013849  mov     [rax], ebx
0x18001384b  setz    bpl
0x18001384f  xor     eax, eax
0x180013851  mov     [rsp+68h+var_30], rax
0x180013856  mov     [rsp+68h+var_28], eax
0x18001385a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180013861  test    rax, rax
0x180013864  jnz     loc_1800138F2
0x18001386a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013871  test    rax, rax
0x180013874  jnz     short loc_180013890
0x180013876  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18001387d  call    cs:__imp_GetModuleHandleW
0x180013884  nop     dword ptr [rax+rax+00h]
0x180013889  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180013890  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180013897  mov     rcx, rax; hModule
0x18001389a  call    cs:__imp_GetProcAddress
0x1800138a1  nop     dword ptr [rax+rax+00h]
0x1800138a6  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800138ad  test    rax, rax
0x1800138b0  jnz     short loc_1800138F2
0x1800138b2  mov     r8d, 0C0000139h
0x1800138b8  xor     ebx, ebx
0x1800138ba  test    rdi, rdi
0x1800138bd  jz      short loc_1800138CD
0x1800138bf  xor     ecx, ecx
0x1800138c1  cmp     r8d, 80000022h
0x1800138c8  setnz   cl
0x1800138cb  mov     [rdi], ecx
0x1800138cd  mov     eax, ebx
0x1800138cf  mov     rcx, [rsp+68h+var_20]
0x1800138d4  xor     rcx, rsp; StackCookie
0x1800138d7  call    __security_check_cookie
0x1800138dc  lea     r11, [rsp+68h+var_18]
0x1800138e1  mov     rbx, [r11+30h]
0x1800138e5  mov     rbp, [r11+38h]
0x1800138e9  mov     rsp, r11
0x1800138ec  pop     r14
0x1800138ee  pop     rdi
0x1800138ef  pop     rsi
0x1800138f0  retn
0x1800138f2  lea     r9, [rsp+68h+var_30]
0x1800138f7  mov     edx, ebp
0x1800138f9  lea     r8, [rsp+68h+var_38]
0x1800138fe  mov     ecx, r14d
0x180013901  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013906  mov     r8d, eax
0x180013909  test    eax, eax
0x18001390b  jnz     short loc_18001394F
0x18001390d  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180013911  mov     ecx, edx
0x180013913  mov     eax, [rsp+68h+var_28]
0x180013917  mov     [rsi+0Ch], eax
0x18001391a  mov     eax, edx
0x18001391c  shr     eax, 0Eh
0x18001391f  shr     ecx, 4
0x180013922  and     eax, 3
0x180013925  and     ecx, 3
0x180013928  mov     [rsi+8], eax
0x18001392b  mov     [rsi], ecx
0x18001392d  mov     eax, edx
0x18001392f  mov     ecx, edx
0x180013931  shr     eax, 6
0x180013934  shr     ecx, 8
0x180013937  and     eax, ebx
0x180013939  and     cl, 3Fh
0x18001393c  shr     edx, 7
0x18001393f  and     edx, ebx
0x180013941  mov     [rsi+4], cl
0x180013944  mov     [rsi+10h], edx
0x180013947  mov     [rsi+14h], eax
0x18001394a  jmp     loc_1800138BA
0x18001394f  cmp     eax, 117h
0x180013954  jnz     loc_1800138B8
0x18001395a  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18001395e  shr     eax, 7
0x180013961  and     eax, ebx
0x180013963  mov     [rsi+10h], eax
0x180013966  jmp     loc_1800138BA
```
