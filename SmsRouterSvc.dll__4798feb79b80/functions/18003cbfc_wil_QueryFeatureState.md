# wil_QueryFeatureState

- ea: `0x18003cbfc`
- end: `0x18003cd62`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180039b70`

## callees

- `0x180003a60`
- `0x18003cbfc`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cc81`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003cc81`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cc98`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003cc98`

## string_xrefs

- `0x18003cc7a`: `ntdll.dll`
- `0x18003cc8e`: `RtlQueryFeatureConfiguration`

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
0x18003cbfc  mov     [rsp+arg_10], rbx
0x18003cc01  mov     [rsp+arg_18], rbp
0x18003cc06  push    rsi
0x18003cc07  push    rdi
0x18003cc08  push    r14
0x18003cc0a  sub     rsp, 50h
0x18003cc0e  mov     rax, cs:__security_cookie
0x18003cc15  xor     rax, rsp
0x18003cc18  mov     [rsp+68h+var_20], rax
0x18003cc1d  mov     rdi, [rsp+68h+arg_20]
0x18003cc25  mov     r14d, edx
0x18003cc28  mov     rax, [rsp+68h+arg_28]
0x18003cc30  mov     rsi, rcx
0x18003cc33  test    rdi, rdi
0x18003cc36  jz      short loc_18003CC3E
0x18003cc38  mov     dword ptr [rdi], 0
0x18003cc3e  xor     ebp, ebp
0x18003cc40  mov     [rsp+68h+var_38], 0
0x18003cc49  test    r8d, r8d
0x18003cc4c  mov     ebx, 1
0x18003cc51  mov     [rax], ebx
0x18003cc53  setz    bpl
0x18003cc57  xor     eax, eax
0x18003cc59  mov     [rsp+68h+var_30], rax
0x18003cc5e  mov     [rsp+68h+var_28], eax
0x18003cc62  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18003cc69  test    rax, rax
0x18003cc6c  jnz     short loc_18003CCE9
0x18003cc6e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003cc75  test    rax, rax
0x18003cc78  jnz     short loc_18003CC8E
0x18003cc7a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18003cc81  call    cs:__imp_GetModuleHandleW
0x18003cc87  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003cc8e  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18003cc95  mov     rcx, rax; hModule
0x18003cc98  call    cs:__imp_GetProcAddress
0x18003cc9e  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18003cca5  test    rax, rax
0x18003cca8  jnz     short loc_18003CCE9
0x18003ccaa  mov     r8d, 0C0000139h
0x18003ccb0  xor     ebx, ebx
0x18003ccb2  test    rdi, rdi
0x18003ccb5  jz      short loc_18003CCC5
0x18003ccb7  xor     ecx, ecx
0x18003ccb9  cmp     r8d, 80000022h
0x18003ccc0  setnz   cl
0x18003ccc3  mov     [rdi], ecx
0x18003ccc5  mov     eax, ebx
0x18003ccc7  mov     rcx, [rsp+68h+var_20]
0x18003cccc  xor     rcx, rsp; StackCookie
0x18003cccf  call    __security_check_cookie
0x18003ccd4  lea     r11, [rsp+68h+var_18]
0x18003ccd9  mov     rbx, [r11+30h]
0x18003ccdd  mov     rbp, [r11+38h]
0x18003cce1  mov     rsp, r11
0x18003cce4  pop     r14
0x18003cce6  pop     rdi
0x18003cce7  pop     rsi
0x18003cce8  retn
0x18003cce9  lea     r9, [rsp+68h+var_30]
0x18003ccee  mov     edx, ebp
0x18003ccf0  lea     r8, [rsp+68h+var_38]
0x18003ccf5  mov     ecx, r14d
0x18003ccf8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003ccfd  mov     r8d, eax
0x18003cd00  test    eax, eax
0x18003cd02  jnz     short loc_18003CD46
0x18003cd04  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18003cd08  mov     ecx, edx
0x18003cd0a  mov     eax, [rsp+68h+var_28]
0x18003cd0e  mov     [rsi+0Ch], eax
0x18003cd11  mov     eax, edx
0x18003cd13  shr     eax, 0Eh
0x18003cd16  shr     ecx, 4
0x18003cd19  and     eax, 3
0x18003cd1c  and     ecx, 3
0x18003cd1f  mov     [rsi+8], eax
0x18003cd22  mov     [rsi], ecx
0x18003cd24  mov     eax, edx
0x18003cd26  mov     ecx, edx
0x18003cd28  shr     eax, 6
0x18003cd2b  shr     ecx, 8
0x18003cd2e  and     eax, ebx
0x18003cd30  and     cl, 3Fh
0x18003cd33  shr     edx, 7
0x18003cd36  and     edx, ebx
0x18003cd38  mov     [rsi+4], cl
0x18003cd3b  mov     [rsi+10h], edx
0x18003cd3e  mov     [rsi+14h], eax
0x18003cd41  jmp     loc_18003CCB2
0x18003cd46  cmp     eax, 117h
0x18003cd4b  jnz     loc_18003CCB0
0x18003cd51  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18003cd55  shr     eax, 7
0x18003cd58  and     eax, ebx
0x18003cd5a  mov     [rsi+10h], eax
0x18003cd5d  jmp     loc_18003CCB2
```
