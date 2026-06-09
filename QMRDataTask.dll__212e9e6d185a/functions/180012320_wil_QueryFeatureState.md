# wil_QueryFeatureState

- ea: `0x180012320`
- end: `0x180012486`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000ba78`

## callees

- `0x180012320`
- `0x180014310`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x1800123bc`
- `KERNEL32!GetProcAddress` at `0x1800123bc`
- `KERNEL32!GetModuleHandleW` at `0x1800123a5`
- `KERNEL32!GetModuleHandleW` at `0x1800123a5`

## string_xrefs

- `0x18001239e`: `ntdll.dll`
- `0x1800123b2`: `RtlQueryFeatureConfiguration`

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
0x180012320  mov     [rsp+arg_10], rbx
0x180012325  mov     [rsp+arg_18], rbp
0x18001232a  push    rsi
0x18001232b  push    rdi
0x18001232c  push    r14
0x18001232e  sub     rsp, 50h
0x180012332  mov     rax, cs:__security_cookie
0x180012339  xor     rax, rsp
0x18001233c  mov     [rsp+68h+var_20], rax
0x180012341  mov     rdi, [rsp+68h+arg_20]
0x180012349  mov     r14d, edx
0x18001234c  mov     rax, [rsp+68h+arg_28]
0x180012354  mov     rsi, rcx
0x180012357  test    rdi, rdi
0x18001235a  jz      short loc_180012362
0x18001235c  mov     dword ptr [rdi], 0
0x180012362  xor     ebp, ebp
0x180012364  mov     [rsp+68h+var_38], 0
0x18001236d  test    r8d, r8d
0x180012370  mov     ebx, 1
0x180012375  mov     [rax], ebx
0x180012377  setz    bpl
0x18001237b  xor     eax, eax
0x18001237d  mov     [rsp+68h+var_30], rax
0x180012382  mov     [rsp+68h+var_28], eax
0x180012386  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18001238d  test    rax, rax
0x180012390  jnz     short loc_18001240D
0x180012392  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012399  test    rax, rax
0x18001239c  jnz     short loc_1800123B2
0x18001239e  lea     rcx, ModuleName; "ntdll.dll"
0x1800123a5  call    cs:__imp_GetModuleHandleW
0x1800123ab  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800123b2  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1800123b9  mov     rcx, rax; hModule
0x1800123bc  call    cs:__imp_GetProcAddress
0x1800123c2  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800123c9  test    rax, rax
0x1800123cc  jnz     short loc_18001240D
0x1800123ce  mov     r8d, 0C0000139h
0x1800123d4  xor     ebx, ebx
0x1800123d6  test    rdi, rdi
0x1800123d9  jz      short loc_1800123E9
0x1800123db  xor     ecx, ecx
0x1800123dd  cmp     r8d, 80000022h
0x1800123e4  setnz   cl
0x1800123e7  mov     [rdi], ecx
0x1800123e9  mov     eax, ebx
0x1800123eb  mov     rcx, [rsp+68h+var_20]
0x1800123f0  xor     rcx, rsp; StackCookie
0x1800123f3  call    __security_check_cookie
0x1800123f8  lea     r11, [rsp+68h+var_18]
0x1800123fd  mov     rbx, [r11+30h]
0x180012401  mov     rbp, [r11+38h]
0x180012405  mov     rsp, r11
0x180012408  pop     r14
0x18001240a  pop     rdi
0x18001240b  pop     rsi
0x18001240c  retn
0x18001240d  lea     r9, [rsp+68h+var_30]
0x180012412  mov     edx, ebp
0x180012414  lea     r8, [rsp+68h+var_38]
0x180012419  mov     ecx, r14d
0x18001241c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012421  mov     r8d, eax
0x180012424  test    eax, eax
0x180012426  jnz     short loc_18001246A
0x180012428  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18001242c  mov     ecx, edx
0x18001242e  mov     eax, [rsp+68h+var_28]
0x180012432  mov     [rsi+0Ch], eax
0x180012435  mov     eax, edx
0x180012437  shr     eax, 0Eh
0x18001243a  shr     ecx, 4
0x18001243d  and     eax, 3
0x180012440  and     ecx, 3
0x180012443  mov     [rsi+8], eax
0x180012446  mov     [rsi], ecx
0x180012448  mov     eax, edx
0x18001244a  mov     ecx, edx
0x18001244c  shr     eax, 6
0x18001244f  shr     ecx, 8
0x180012452  and     eax, ebx
0x180012454  and     cl, 3Fh
0x180012457  shr     edx, 7
0x18001245a  and     edx, ebx
0x18001245c  mov     [rsi+4], cl
0x18001245f  mov     [rsi+10h], edx
0x180012462  mov     [rsi+14h], eax
0x180012465  jmp     loc_1800123D6
0x18001246a  cmp     eax, 117h
0x18001246f  jnz     loc_1800123D4
0x180012475  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180012479  shr     eax, 7
0x18001247c  and     eax, ebx
0x18001247e  mov     [rsi+10h], eax
0x180012481  jmp     loc_1800123D6
```
