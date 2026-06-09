# wil_QueryFeatureState

- ea: `0x18000e368`
- end: `0x18000e4cf`
- name: `wil_QueryFeatureState`
- size: `359`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800074dc`

## callees

- `0x18000e368`
- `0x18000f5f0`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000e3ed`
- `KERNEL32!GetModuleHandleW` at `0x18000e3ed`
- `KERNEL32!GetProcAddress` at `0x18000e404`
- `KERNEL32!GetProcAddress` at `0x18000e404`

## string_xrefs

- `0x18000e3e6`: `ntdll.dll`
- `0x18000e3fa`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil_QueryFeatureState(__int64 a1, unsigned int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  unsigned int v8; // ebx
  BOOL v9; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v12; // r8d
  int v14; // eax
  unsigned int v15; // edx
  __int64 v16; // [rsp+30h] [rbp-38h] BYREF
  __int64 v17; // [rsp+38h] [rbp-30h] BYREF
  int v18; // [rsp+40h] [rbp-28h]

  if ( a5 )
    *a5 = 0;
  v8 = 1;
  *a6 = 1;
  v16 = 0;
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
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(a2, v9, &v16, &v17);
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
    *(_DWORD *)a1 = (HIDWORD(v17) >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v15) & 0x3F;
    *(_DWORD *)(a1 + 12) = v18;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v15 >> 14;
    *(_DWORD *)(a1 + 20) = (v15 >> 6) & 1;
    *(_DWORD *)(a1 + 16) = (v15 >> 7) & 1;
  }
LABEL_9:
  if ( a5 )
    *a5 = v12 != -2147483614;
  return v8;
}

```

## disassembly

```asm
0x18000e368  mov     [rsp+arg_10], rbx
0x18000e36d  mov     [rsp+arg_18], rbp
0x18000e372  push    rsi
0x18000e373  push    rdi
0x18000e374  push    r14
0x18000e376  sub     rsp, 50h
0x18000e37a  mov     rax, cs:__security_cookie
0x18000e381  xor     rax, rsp
0x18000e384  mov     [rsp+68h+var_20], rax
0x18000e389  mov     r14d, edx
0x18000e38c  mov     rsi, rcx
0x18000e38f  mov     rdi, [rsp+68h+arg_20]
0x18000e397  mov     rax, [rsp+68h+arg_28]
0x18000e39f  test    rdi, rdi
0x18000e3a2  jz      short loc_18000E3AA
0x18000e3a4  mov     dword ptr [rdi], 0
0x18000e3aa  mov     ebx, 1
0x18000e3af  mov     [rax], ebx
0x18000e3b1  mov     [rsp+68h+var_38], 0
0x18000e3ba  xor     ebp, ebp
0x18000e3bc  test    r8d, r8d
0x18000e3bf  setz    bpl
0x18000e3c3  xor     eax, eax
0x18000e3c5  mov     [rsp+68h+var_30], rax
0x18000e3ca  mov     [rsp+68h+var_28], eax
0x18000e3ce  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000e3d5  test    rax, rax
0x18000e3d8  jnz     short loc_18000E456
0x18000e3da  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e3e1  test    rax, rax
0x18000e3e4  jnz     short loc_18000E3FA
0x18000e3e6  lea     rcx, ModuleName; "ntdll.dll"
0x18000e3ed  call    cs:__imp_GetModuleHandleW
0x18000e3f3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e3fa  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000e401  mov     rcx, rax; hModule
0x18000e404  call    cs:__imp_GetProcAddress
0x18000e40a  nop
0x18000e40b  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000e412  test    rax, rax
0x18000e415  jnz     short loc_18000E456
0x18000e417  mov     r8d, 0C0000139h
0x18000e41d  xor     ebx, ebx
0x18000e41f  test    rdi, rdi
0x18000e422  jz      short loc_18000E432
0x18000e424  xor     ecx, ecx
0x18000e426  cmp     r8d, 80000022h
0x18000e42d  setnz   cl
0x18000e430  mov     [rdi], ecx
0x18000e432  mov     eax, ebx
0x18000e434  mov     rcx, [rsp+68h+var_20]
0x18000e439  xor     rcx, rsp; StackCookie
0x18000e43c  call    __security_check_cookie
0x18000e441  lea     r11, [rsp+68h+var_18]
0x18000e446  mov     rbx, [r11+30h]
0x18000e44a  mov     rbp, [r11+38h]
0x18000e44e  mov     rsp, r11
0x18000e451  pop     r14
0x18000e453  pop     rdi
0x18000e454  pop     rsi
0x18000e455  retn
0x18000e456  lea     r9, [rsp+68h+var_30]
0x18000e45b  lea     r8, [rsp+68h+var_38]
0x18000e460  mov     edx, ebp
0x18000e462  mov     ecx, r14d
0x18000e465  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e46a  mov     r8d, eax
0x18000e46d  test    eax, eax
0x18000e46f  jnz     short loc_18000E4B3
0x18000e471  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000e475  mov     ecx, edx
0x18000e477  shr     ecx, 4
0x18000e47a  and     ecx, 3
0x18000e47d  mov     [rsi], ecx
0x18000e47f  mov     ecx, edx
0x18000e481  shr     ecx, 8
0x18000e484  and     cl, 3Fh
0x18000e487  mov     [rsi+4], cl
0x18000e48a  mov     eax, [rsp+68h+var_28]
0x18000e48e  mov     [rsi+0Ch], eax
0x18000e491  mov     eax, edx
0x18000e493  shr     eax, 0Eh
0x18000e496  and     eax, 3
0x18000e499  mov     [rsi+8], eax
0x18000e49c  mov     eax, edx
0x18000e49e  shr     eax, 6
0x18000e4a1  and     eax, ebx
0x18000e4a3  mov     [rsi+14h], eax
0x18000e4a6  shr     edx, 7
0x18000e4a9  and     edx, ebx
0x18000e4ab  mov     [rsi+10h], edx
0x18000e4ae  jmp     loc_18000E41F
0x18000e4b3  cmp     eax, 117h
0x18000e4b8  jnz     loc_18000E41D
0x18000e4be  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000e4c2  shr     eax, 7
0x18000e4c5  and     eax, ebx
0x18000e4c7  mov     [rsi+10h], eax
0x18000e4ca  jmp     loc_18000E41F
```
