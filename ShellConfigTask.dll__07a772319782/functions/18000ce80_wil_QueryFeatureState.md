# wil_QueryFeatureState

- ea: `0x18000ce80`
- end: `0x18000cfe6`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800083e4`

## callees

- `0x180002590`
- `0x18000ce80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cf05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cf05`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cf1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cf1c`

## string_xrefs

- `0x18000cefe`: `ntdll.dll`
- `0x18000cf12`: `RtlQueryFeatureConfiguration`

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
0x18000ce80  mov     [rsp+arg_10], rbx
0x18000ce85  mov     [rsp+arg_18], rbp
0x18000ce8a  push    rsi
0x18000ce8b  push    rdi
0x18000ce8c  push    r14
0x18000ce8e  sub     rsp, 50h
0x18000ce92  mov     rax, cs:__security_cookie
0x18000ce99  xor     rax, rsp
0x18000ce9c  mov     [rsp+68h+var_20], rax
0x18000cea1  mov     rdi, [rsp+68h+arg_20]
0x18000cea9  mov     r14d, edx
0x18000ceac  mov     rax, [rsp+68h+arg_28]
0x18000ceb4  mov     rsi, rcx
0x18000ceb7  test    rdi, rdi
0x18000ceba  jz      short loc_18000CEC2
0x18000cebc  mov     dword ptr [rdi], 0
0x18000cec2  xor     ebp, ebp
0x18000cec4  mov     [rsp+68h+var_38], 0
0x18000cecd  test    r8d, r8d
0x18000ced0  mov     ebx, 1
0x18000ced5  mov     [rax], ebx
0x18000ced7  setz    bpl
0x18000cedb  xor     eax, eax
0x18000cedd  mov     [rsp+68h+var_30], rax
0x18000cee2  mov     [rsp+68h+var_28], eax
0x18000cee6  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000ceed  test    rax, rax
0x18000cef0  jnz     short loc_18000CF6D
0x18000cef2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cef9  test    rax, rax
0x18000cefc  jnz     short loc_18000CF12
0x18000cefe  lea     rcx, ModuleName; "ntdll.dll"
0x18000cf05  call    cs:__imp_GetModuleHandleW
0x18000cf0b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cf12  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000cf19  mov     rcx, rax; hModule
0x18000cf1c  call    cs:__imp_GetProcAddress
0x18000cf22  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000cf29  test    rax, rax
0x18000cf2c  jnz     short loc_18000CF6D
0x18000cf2e  mov     r8d, 0C0000139h
0x18000cf34  xor     ebx, ebx
0x18000cf36  test    rdi, rdi
0x18000cf39  jz      short loc_18000CF49
0x18000cf3b  xor     ecx, ecx
0x18000cf3d  cmp     r8d, 80000022h
0x18000cf44  setnz   cl
0x18000cf47  mov     [rdi], ecx
0x18000cf49  mov     eax, ebx
0x18000cf4b  mov     rcx, [rsp+68h+var_20]
0x18000cf50  xor     rcx, rsp; StackCookie
0x18000cf53  call    __security_check_cookie
0x18000cf58  lea     r11, [rsp+68h+var_18]
0x18000cf5d  mov     rbx, [r11+30h]
0x18000cf61  mov     rbp, [r11+38h]
0x18000cf65  mov     rsp, r11
0x18000cf68  pop     r14
0x18000cf6a  pop     rdi
0x18000cf6b  pop     rsi
0x18000cf6c  retn
0x18000cf6d  lea     r9, [rsp+68h+var_30]
0x18000cf72  mov     edx, ebp
0x18000cf74  lea     r8, [rsp+68h+var_38]
0x18000cf79  mov     ecx, r14d
0x18000cf7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cf81  mov     r8d, eax
0x18000cf84  test    eax, eax
0x18000cf86  jnz     short loc_18000CFCA
0x18000cf88  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000cf8c  mov     ecx, edx
0x18000cf8e  mov     eax, [rsp+68h+var_28]
0x18000cf92  mov     [rsi+0Ch], eax
0x18000cf95  mov     eax, edx
0x18000cf97  shr     eax, 0Eh
0x18000cf9a  shr     ecx, 4
0x18000cf9d  and     eax, 3
0x18000cfa0  and     ecx, 3
0x18000cfa3  mov     [rsi+8], eax
0x18000cfa6  mov     [rsi], ecx
0x18000cfa8  mov     eax, edx
0x18000cfaa  mov     ecx, edx
0x18000cfac  shr     eax, 6
0x18000cfaf  shr     ecx, 8
0x18000cfb2  and     eax, ebx
0x18000cfb4  and     cl, 3Fh
0x18000cfb7  shr     edx, 7
0x18000cfba  and     edx, ebx
0x18000cfbc  mov     [rsi+4], cl
0x18000cfbf  mov     [rsi+10h], edx
0x18000cfc2  mov     [rsi+14h], eax
0x18000cfc5  jmp     loc_18000CF36
0x18000cfca  cmp     eax, 117h
0x18000cfcf  jnz     loc_18000CF34
0x18000cfd5  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000cfd9  shr     eax, 7
0x18000cfdc  and     eax, ebx
0x18000cfde  mov     [rsi+10h], eax
0x18000cfe1  jmp     loc_18000CF36
```
