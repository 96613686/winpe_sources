# wil_QueryFeatureState

- ea: `0x1800eccbc`
- end: `0x1800ece22`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800e8ad8`

## callees

- `0x180003060`
- `0x1800eccbc`
- `0x18010d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ecd58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800ecd58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ecd41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800ecd41`

## string_xrefs

- `0x1800ecd3a`: `ntdll.dll`
- `0x1800ecd4e`: `RtlQueryFeatureConfiguration`

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
0x1800eccbc  mov     [rsp+arg_10], rbx
0x1800eccc1  mov     [rsp+arg_18], rbp
0x1800eccc6  push    rsi
0x1800eccc7  push    rdi
0x1800eccc8  push    r14
0x1800eccca  sub     rsp, 50h
0x1800eccce  mov     rax, cs:__security_cookie
0x1800eccd5  xor     rax, rsp
0x1800eccd8  mov     [rsp+68h+var_20], rax
0x1800eccdd  mov     rdi, [rsp+68h+arg_20]
0x1800ecce5  mov     r14d, edx
0x1800ecce8  mov     rax, [rsp+68h+arg_28]
0x1800eccf0  mov     rsi, rcx
0x1800eccf3  test    rdi, rdi
0x1800eccf6  jz      short loc_1800ECCFE
0x1800eccf8  mov     dword ptr [rdi], 0
0x1800eccfe  xor     ebp, ebp
0x1800ecd00  mov     [rsp+68h+var_38], 0
0x1800ecd09  test    r8d, r8d
0x1800ecd0c  mov     ebx, 1
0x1800ecd11  mov     [rax], ebx
0x1800ecd13  setz    bpl
0x1800ecd17  xor     eax, eax
0x1800ecd19  mov     [rsp+68h+var_30], rax
0x1800ecd1e  mov     [rsp+68h+var_28], eax
0x1800ecd22  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800ecd29  test    rax, rax
0x1800ecd2c  jnz     short loc_1800ECDA9
0x1800ecd2e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800ecd35  test    rax, rax
0x1800ecd38  jnz     short loc_1800ECD4E
0x1800ecd3a  lea     rcx, ModuleName; "ntdll.dll"
0x1800ecd41  call    cs:__imp_GetModuleHandleW
0x1800ecd47  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800ecd4e  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800ecd55  mov     rcx, rax; hModule
0x1800ecd58  call    cs:__imp_GetProcAddress
0x1800ecd5e  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800ecd65  test    rax, rax
0x1800ecd68  jnz     short loc_1800ECDA9
0x1800ecd6a  mov     r8d, 0C0000139h
0x1800ecd70  xor     ebx, ebx
0x1800ecd72  test    rdi, rdi
0x1800ecd75  jz      short loc_1800ECD85
0x1800ecd77  xor     ecx, ecx
0x1800ecd79  cmp     r8d, 80000022h
0x1800ecd80  setnz   cl
0x1800ecd83  mov     [rdi], ecx
0x1800ecd85  mov     eax, ebx
0x1800ecd87  mov     rcx, [rsp+68h+var_20]
0x1800ecd8c  xor     rcx, rsp; StackCookie
0x1800ecd8f  call    __security_check_cookie
0x1800ecd94  lea     r11, [rsp+68h+var_18]
0x1800ecd99  mov     rbx, [r11+30h]
0x1800ecd9d  mov     rbp, [r11+38h]
0x1800ecda1  mov     rsp, r11
0x1800ecda4  pop     r14
0x1800ecda6  pop     rdi
0x1800ecda7  pop     rsi
0x1800ecda8  retn
0x1800ecda9  lea     r9, [rsp+68h+var_30]
0x1800ecdae  mov     edx, ebp
0x1800ecdb0  lea     r8, [rsp+68h+var_38]
0x1800ecdb5  mov     ecx, r14d
0x1800ecdb8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800ecdbd  mov     r8d, eax
0x1800ecdc0  test    eax, eax
0x1800ecdc2  jnz     short loc_1800ECE06
0x1800ecdc4  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800ecdc8  mov     ecx, edx
0x1800ecdca  mov     eax, [rsp+68h+var_28]
0x1800ecdce  mov     [rsi+0Ch], eax
0x1800ecdd1  mov     eax, edx
0x1800ecdd3  shr     eax, 0Eh
0x1800ecdd6  shr     ecx, 4
0x1800ecdd9  and     eax, 3
0x1800ecddc  and     ecx, 3
0x1800ecddf  mov     [rsi+8], eax
0x1800ecde2  mov     [rsi], ecx
0x1800ecde4  mov     eax, edx
0x1800ecde6  mov     ecx, edx
0x1800ecde8  shr     eax, 6
0x1800ecdeb  shr     ecx, 8
0x1800ecdee  and     eax, ebx
0x1800ecdf0  and     cl, 3Fh
0x1800ecdf3  shr     edx, 7
0x1800ecdf6  and     edx, ebx
0x1800ecdf8  mov     [rsi+4], cl
0x1800ecdfb  mov     [rsi+10h], edx
0x1800ecdfe  mov     [rsi+14h], eax
0x1800ece01  jmp     loc_1800ECD72
0x1800ece06  cmp     eax, 117h
0x1800ece0b  jnz     loc_1800ECD70
0x1800ece11  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800ece15  shr     eax, 7
0x1800ece18  and     eax, ebx
0x1800ece1a  mov     [rsi+10h], eax
0x1800ece1d  jmp     loc_1800ECD72
```
