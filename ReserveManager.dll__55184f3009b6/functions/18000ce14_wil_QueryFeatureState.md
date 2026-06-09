# wil_QueryFeatureState

- ea: `0x18000ce14`
- end: `0x18000cf7a`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180008154`

## callees

- `0x180003870`
- `0x18000ce14`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000ce99`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000ce99`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000ceb0`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000ceb0`

## string_xrefs

- `0x18000ce92`: `ntdll.dll`
- `0x18000cea6`: `RtlQueryFeatureConfiguration`

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
0x18000ce14  mov     [rsp+arg_10], rbx
0x18000ce19  mov     [rsp+arg_18], rbp
0x18000ce1e  push    rsi
0x18000ce1f  push    rdi
0x18000ce20  push    r14
0x18000ce22  sub     rsp, 50h
0x18000ce26  mov     rax, cs:__security_cookie
0x18000ce2d  xor     rax, rsp
0x18000ce30  mov     [rsp+68h+var_20], rax
0x18000ce35  mov     rdi, [rsp+68h+arg_20]
0x18000ce3d  mov     r14d, edx
0x18000ce40  mov     rax, [rsp+68h+arg_28]
0x18000ce48  mov     rsi, rcx
0x18000ce4b  test    rdi, rdi
0x18000ce4e  jz      short loc_18000CE56
0x18000ce50  mov     dword ptr [rdi], 0
0x18000ce56  xor     ebp, ebp
0x18000ce58  mov     [rsp+68h+var_28], 0
0x18000ce61  test    r8d, r8d
0x18000ce64  mov     ebx, 1
0x18000ce69  mov     [rax], ebx
0x18000ce6b  setz    bpl
0x18000ce6f  xor     eax, eax
0x18000ce71  mov     [rsp+68h+var_38], rax
0x18000ce76  mov     [rsp+68h+var_30], eax
0x18000ce7a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000ce81  test    rax, rax
0x18000ce84  jnz     short loc_18000CF01
0x18000ce86  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ce8d  test    rax, rax
0x18000ce90  jnz     short loc_18000CEA6
0x18000ce92  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ce99  call    cs:__imp_GetModuleHandleW
0x18000ce9f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cea6  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000cead  mov     rcx, rax; hModule
0x18000ceb0  call    cs:__imp_GetProcAddress
0x18000ceb6  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000cebd  test    rax, rax
0x18000cec0  jnz     short loc_18000CF01
0x18000cec2  mov     r8d, 0C0000139h
0x18000cec8  xor     ebx, ebx
0x18000ceca  test    rdi, rdi
0x18000cecd  jz      short loc_18000CEDD
0x18000cecf  xor     ecx, ecx
0x18000ced1  cmp     r8d, 80000022h
0x18000ced8  setnz   cl
0x18000cedb  mov     [rdi], ecx
0x18000cedd  mov     eax, ebx
0x18000cedf  mov     rcx, [rsp+68h+var_20]
0x18000cee4  xor     rcx, rsp; StackCookie
0x18000cee7  call    __security_check_cookie
0x18000ceec  lea     r11, [rsp+68h+var_18]
0x18000cef1  mov     rbx, [r11+30h]
0x18000cef5  mov     rbp, [r11+38h]
0x18000cef9  mov     rsp, r11
0x18000cefc  pop     r14
0x18000cefe  pop     rdi
0x18000ceff  pop     rsi
0x18000cf00  retn
0x18000cf01  lea     r9, [rsp+68h+var_38]
0x18000cf06  mov     edx, ebp
0x18000cf08  lea     r8, [rsp+68h+var_28]
0x18000cf0d  mov     ecx, r14d
0x18000cf10  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf15  mov     r8d, eax
0x18000cf18  test    eax, eax
0x18000cf1a  jnz     short loc_18000CF5E
0x18000cf1c  mov     edx, dword ptr [rsp+68h+var_38+4]
0x18000cf20  mov     ecx, edx
0x18000cf22  mov     eax, [rsp+68h+var_30]
0x18000cf26  mov     [rsi+0Ch], eax
0x18000cf29  mov     eax, edx
0x18000cf2b  shr     eax, 0Eh
0x18000cf2e  shr     ecx, 4
0x18000cf31  and     eax, 3
0x18000cf34  and     ecx, 3
0x18000cf37  mov     [rsi+8], eax
0x18000cf3a  mov     [rsi], ecx
0x18000cf3c  mov     eax, edx
0x18000cf3e  mov     ecx, edx
0x18000cf40  shr     eax, 6
0x18000cf43  shr     ecx, 8
0x18000cf46  and     eax, ebx
0x18000cf48  and     cl, 3Fh
0x18000cf4b  shr     edx, 7
0x18000cf4e  and     edx, ebx
0x18000cf50  mov     [rsi+4], cl
0x18000cf53  mov     [rsi+10h], edx
0x18000cf56  mov     [rsi+14h], eax
0x18000cf59  jmp     loc_18000CECA
0x18000cf5e  cmp     eax, 117h
0x18000cf63  jnz     loc_18000CEC8
0x18000cf69  mov     eax, dword ptr [rsp+68h+var_38+4]
0x18000cf6d  shr     eax, 7
0x18000cf70  and     eax, ebx
0x18000cf72  mov     [rsi+10h], eax
0x18000cf75  jmp     loc_18000CECA
```
