# wil_QueryFeatureState

- ea: `0x1800221d0`
- end: `0x180022336`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180011448`

## callees

- `0x1800221d0`
- `0x180050300`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022255`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022255`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002226c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002226c`

## string_xrefs

- `0x18002224e`: `ntdll.dll`
- `0x180022262`: `RtlQueryFeatureConfiguration`

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
0x1800221d0  mov     [rsp+arg_10], rbx
0x1800221d5  mov     [rsp+arg_18], rbp
0x1800221da  push    rsi
0x1800221db  push    rdi
0x1800221dc  push    r14
0x1800221de  sub     rsp, 50h
0x1800221e2  mov     rax, cs:__security_cookie
0x1800221e9  xor     rax, rsp
0x1800221ec  mov     [rsp+68h+var_20], rax
0x1800221f1  mov     rdi, [rsp+68h+arg_20]
0x1800221f9  mov     r14d, edx
0x1800221fc  mov     rax, [rsp+68h+arg_28]
0x180022204  mov     rsi, rcx
0x180022207  test    rdi, rdi
0x18002220a  jz      short loc_180022212
0x18002220c  mov     dword ptr [rdi], 0
0x180022212  xor     ebp, ebp
0x180022214  mov     [rsp+68h+var_28], 0
0x18002221d  test    r8d, r8d
0x180022220  mov     ebx, 1
0x180022225  mov     [rax], ebx
0x180022227  setz    bpl
0x18002222b  xor     eax, eax
0x18002222d  mov     [rsp+68h+var_38], rax
0x180022232  mov     [rsp+68h+var_30], eax
0x180022236  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18002223d  test    rax, rax
0x180022240  jnz     short loc_1800222BD
0x180022242  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022249  test    rax, rax
0x18002224c  jnz     short loc_180022262
0x18002224e  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x180022255  call    cs:__imp_GetModuleHandleW
0x18002225b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022262  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180022269  mov     rcx, rax; hModule
0x18002226c  call    cs:__imp_GetProcAddress
0x180022272  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180022279  test    rax, rax
0x18002227c  jnz     short loc_1800222BD
0x18002227e  mov     r8d, 0C0000139h
0x180022284  xor     ebx, ebx
0x180022286  test    rdi, rdi
0x180022289  jz      short loc_180022299
0x18002228b  xor     ecx, ecx
0x18002228d  cmp     r8d, 80000022h
0x180022294  setnz   cl
0x180022297  mov     [rdi], ecx
0x180022299  mov     eax, ebx
0x18002229b  mov     rcx, [rsp+68h+var_20]
0x1800222a0  xor     rcx, rsp; StackCookie
0x1800222a3  call    __security_check_cookie
0x1800222a8  lea     r11, [rsp+68h+var_18]
0x1800222ad  mov     rbx, [r11+30h]
0x1800222b1  mov     rbp, [r11+38h]
0x1800222b5  mov     rsp, r11
0x1800222b8  pop     r14
0x1800222ba  pop     rdi
0x1800222bb  pop     rsi
0x1800222bc  retn
0x1800222bd  lea     r9, [rsp+68h+var_38]
0x1800222c2  mov     edx, ebp
0x1800222c4  lea     r8, [rsp+68h+var_28]
0x1800222c9  mov     ecx, r14d
0x1800222cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800222d1  mov     r8d, eax
0x1800222d4  test    eax, eax
0x1800222d6  jnz     short loc_18002231A
0x1800222d8  mov     edx, dword ptr [rsp+68h+var_38+4]
0x1800222dc  mov     ecx, edx
0x1800222de  mov     eax, [rsp+68h+var_30]
0x1800222e2  mov     [rsi+0Ch], eax
0x1800222e5  mov     eax, edx
0x1800222e7  shr     eax, 0Eh
0x1800222ea  shr     ecx, 4
0x1800222ed  and     eax, 3
0x1800222f0  and     ecx, 3
0x1800222f3  mov     [rsi+8], eax
0x1800222f6  mov     [rsi], ecx
0x1800222f8  mov     eax, edx
0x1800222fa  mov     ecx, edx
0x1800222fc  shr     eax, 6
0x1800222ff  shr     ecx, 8
0x180022302  and     eax, ebx
0x180022304  and     cl, 3Fh
0x180022307  shr     edx, 7
0x18002230a  and     edx, ebx
0x18002230c  mov     [rsi+4], cl
0x18002230f  mov     [rsi+10h], edx
0x180022312  mov     [rsi+14h], eax
0x180022315  jmp     loc_180022286
0x18002231a  cmp     eax, 117h
0x18002231f  jnz     loc_180022284
0x180022325  mov     eax, dword ptr [rsp+68h+var_38+4]
0x180022329  shr     eax, 7
0x18002232c  and     eax, ebx
0x18002232e  mov     [rsi+10h], eax
0x180022331  jmp     loc_180022286
```
