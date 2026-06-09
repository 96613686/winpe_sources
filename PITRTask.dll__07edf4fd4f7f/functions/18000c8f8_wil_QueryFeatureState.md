# wil_QueryFeatureState

- ea: `0x18000c8f8`
- end: `0x18000ca5e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800069d0`

## callees

- `0x18000c8f8`
- `0x1800107c0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c994`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c994`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c97d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c97d`

## string_xrefs

- `0x18000c976`: `ntdll.dll`
- `0x18000c98a`: `RtlQueryFeatureConfiguration`

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
0x18000c8f8  mov     [rsp+arg_10], rbx
0x18000c8fd  mov     [rsp+arg_18], rbp
0x18000c902  push    rsi
0x18000c903  push    rdi
0x18000c904  push    r14
0x18000c906  sub     rsp, 50h
0x18000c90a  mov     rax, cs:__security_cookie
0x18000c911  xor     rax, rsp
0x18000c914  mov     [rsp+68h+var_20], rax
0x18000c919  mov     rdi, [rsp+68h+arg_20]
0x18000c921  mov     r14d, edx
0x18000c924  mov     rax, [rsp+68h+arg_28]
0x18000c92c  mov     rsi, rcx
0x18000c92f  test    rdi, rdi
0x18000c932  jz      short loc_18000C93A
0x18000c934  mov     dword ptr [rdi], 0
0x18000c93a  xor     ebp, ebp
0x18000c93c  mov     [rsp+68h+var_28], 0
0x18000c945  test    r8d, r8d
0x18000c948  mov     ebx, 1
0x18000c94d  mov     [rax], ebx
0x18000c94f  setz    bpl
0x18000c953  xor     eax, eax
0x18000c955  mov     [rsp+68h+var_38], rax
0x18000c95a  mov     [rsp+68h+var_30], eax
0x18000c95e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000c965  test    rax, rax
0x18000c968  jnz     short loc_18000C9E5
0x18000c96a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c971  test    rax, rax
0x18000c974  jnz     short loc_18000C98A
0x18000c976  lea     rcx, ModuleName; "ntdll.dll"
0x18000c97d  call    cs:__imp_GetModuleHandleW
0x18000c983  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c98a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000c991  mov     rcx, rax; hModule
0x18000c994  call    cs:__imp_GetProcAddress
0x18000c99a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000c9a1  test    rax, rax
0x18000c9a4  jnz     short loc_18000C9E5
0x18000c9a6  mov     r8d, 0C0000139h
0x18000c9ac  xor     ebx, ebx
0x18000c9ae  test    rdi, rdi
0x18000c9b1  jz      short loc_18000C9C1
0x18000c9b3  xor     ecx, ecx
0x18000c9b5  cmp     r8d, 80000022h
0x18000c9bc  setnz   cl
0x18000c9bf  mov     [rdi], ecx
0x18000c9c1  mov     eax, ebx
0x18000c9c3  mov     rcx, [rsp+68h+var_20]
0x18000c9c8  xor     rcx, rsp; StackCookie
0x18000c9cb  call    __security_check_cookie
0x18000c9d0  lea     r11, [rsp+68h+var_18]
0x18000c9d5  mov     rbx, [r11+30h]
0x18000c9d9  mov     rbp, [r11+38h]
0x18000c9dd  mov     rsp, r11
0x18000c9e0  pop     r14
0x18000c9e2  pop     rdi
0x18000c9e3  pop     rsi
0x18000c9e4  retn
0x18000c9e5  lea     r9, [rsp+68h+var_38]
0x18000c9ea  mov     edx, ebp
0x18000c9ec  lea     r8, [rsp+68h+var_28]
0x18000c9f1  mov     ecx, r14d
0x18000c9f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9f9  mov     r8d, eax
0x18000c9fc  test    eax, eax
0x18000c9fe  jnz     short loc_18000CA42
0x18000ca00  mov     edx, dword ptr [rsp+68h+var_38+4]
0x18000ca04  mov     ecx, edx
0x18000ca06  mov     eax, [rsp+68h+var_30]
0x18000ca0a  mov     [rsi+0Ch], eax
0x18000ca0d  mov     eax, edx
0x18000ca0f  shr     eax, 0Eh
0x18000ca12  shr     ecx, 4
0x18000ca15  and     eax, 3
0x18000ca18  and     ecx, 3
0x18000ca1b  mov     [rsi+8], eax
0x18000ca1e  mov     [rsi], ecx
0x18000ca20  mov     eax, edx
0x18000ca22  mov     ecx, edx
0x18000ca24  shr     eax, 6
0x18000ca27  shr     ecx, 8
0x18000ca2a  and     eax, ebx
0x18000ca2c  and     cl, 3Fh
0x18000ca2f  shr     edx, 7
0x18000ca32  and     edx, ebx
0x18000ca34  mov     [rsi+4], cl
0x18000ca37  mov     [rsi+10h], edx
0x18000ca3a  mov     [rsi+14h], eax
0x18000ca3d  jmp     loc_18000C9AE
0x18000ca42  cmp     eax, 117h
0x18000ca47  jnz     loc_18000C9AC
0x18000ca4d  mov     eax, dword ptr [rsp+68h+var_38+4]
0x18000ca51  shr     eax, 7
0x18000ca54  and     eax, ebx
0x18000ca56  mov     [rsi+10h], eax
0x18000ca59  jmp     loc_18000C9AE
```
