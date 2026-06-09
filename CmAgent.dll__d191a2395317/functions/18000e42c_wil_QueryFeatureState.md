# wil_QueryFeatureState

- ea: `0x18000e42c`
- end: `0x18000e5a3`
- name: `wil_QueryFeatureState`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000e96c`

## callees

- `0x180002140`
- `0x18000e42c`
- `0x18003c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e4b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e4b5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e4d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e4d2`

## string_xrefs

- `0x18000e4ae`: `ntdll.dll`
- `0x18000e4c8`: `RtlQueryFeatureConfiguration`

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
0x18000e42c  mov     [rsp+arg_10], rbx
0x18000e431  mov     [rsp+arg_18], rbp
0x18000e436  push    rsi
0x18000e437  push    rdi
0x18000e438  push    r14
0x18000e43a  sub     rsp, 50h
0x18000e43e  mov     rax, cs:__security_cookie
0x18000e445  xor     rax, rsp
0x18000e448  mov     [rsp+68h+var_20], rax
0x18000e44d  mov     rdi, [rsp+68h+arg_20]
0x18000e455  mov     r14d, edx
0x18000e458  mov     rax, [rsp+68h+arg_28]
0x18000e460  mov     rsi, rcx
0x18000e463  test    rdi, rdi
0x18000e466  jz      short loc_18000E46E
0x18000e468  mov     dword ptr [rdi], 0
0x18000e46e  xor     ebp, ebp
0x18000e470  mov     [rsp+68h+var_38], 0
0x18000e479  test    r8d, r8d
0x18000e47c  mov     ebx, 1
0x18000e481  mov     [rax], ebx
0x18000e483  setz    bpl
0x18000e487  xor     eax, eax
0x18000e489  mov     [rsp+68h+var_30], rax
0x18000e48e  mov     [rsp+68h+var_28], eax
0x18000e492  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000e499  test    rax, rax
0x18000e49c  jnz     loc_18000E52A
0x18000e4a2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000e4a9  test    rax, rax
0x18000e4ac  jnz     short loc_18000E4C8
0x18000e4ae  lea     rcx, ModuleName; "ntdll.dll"
0x18000e4b5  call    cs:__imp_GetModuleHandleW
0x18000e4bc  nop     dword ptr [rax+rax+00h]
0x18000e4c1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000e4c8  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000e4cf  mov     rcx, rax; hModule
0x18000e4d2  call    cs:__imp_GetProcAddress
0x18000e4d9  nop     dword ptr [rax+rax+00h]
0x18000e4de  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000e4e5  test    rax, rax
0x18000e4e8  jnz     short loc_18000E52A
0x18000e4ea  mov     r8d, 0C0000139h
0x18000e4f0  xor     ebx, ebx
0x18000e4f2  test    rdi, rdi
0x18000e4f5  jz      short loc_18000E505
0x18000e4f7  xor     ecx, ecx
0x18000e4f9  cmp     r8d, 80000022h
0x18000e500  setnz   cl
0x18000e503  mov     [rdi], ecx
0x18000e505  mov     eax, ebx
0x18000e507  mov     rcx, [rsp+68h+var_20]
0x18000e50c  xor     rcx, rsp; StackCookie
0x18000e50f  call    __security_check_cookie
0x18000e514  lea     r11, [rsp+68h+var_18]
0x18000e519  mov     rbx, [r11+30h]
0x18000e51d  mov     rbp, [r11+38h]
0x18000e521  mov     rsp, r11
0x18000e524  pop     r14
0x18000e526  pop     rdi
0x18000e527  pop     rsi
0x18000e528  retn
0x18000e52a  lea     r9, [rsp+68h+var_30]
0x18000e52f  mov     edx, ebp
0x18000e531  lea     r8, [rsp+68h+var_38]
0x18000e536  mov     ecx, r14d
0x18000e539  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e53e  mov     r8d, eax
0x18000e541  test    eax, eax
0x18000e543  jnz     short loc_18000E587
0x18000e545  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000e549  mov     ecx, edx
0x18000e54b  mov     eax, [rsp+68h+var_28]
0x18000e54f  mov     [rsi+0Ch], eax
0x18000e552  mov     eax, edx
0x18000e554  shr     eax, 0Eh
0x18000e557  shr     ecx, 4
0x18000e55a  and     eax, 3
0x18000e55d  and     ecx, 3
0x18000e560  mov     [rsi+8], eax
0x18000e563  mov     [rsi], ecx
0x18000e565  mov     eax, edx
0x18000e567  mov     ecx, edx
0x18000e569  shr     eax, 6
0x18000e56c  shr     ecx, 8
0x18000e56f  and     eax, ebx
0x18000e571  and     cl, 3Fh
0x18000e574  shr     edx, 7
0x18000e577  and     edx, ebx
0x18000e579  mov     [rsi+4], cl
0x18000e57c  mov     [rsi+10h], edx
0x18000e57f  mov     [rsi+14h], eax
0x18000e582  jmp     loc_18000E4F2
0x18000e587  cmp     eax, 117h
0x18000e58c  jnz     loc_18000E4F0
0x18000e592  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000e596  shr     eax, 7
0x18000e599  and     eax, ebx
0x18000e59b  mov     [rsi+10h], eax
0x18000e59e  jmp     loc_18000E4F2
```
