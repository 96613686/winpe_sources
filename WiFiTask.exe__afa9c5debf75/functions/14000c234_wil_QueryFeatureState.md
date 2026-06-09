# wil_QueryFeatureState

- ea: `0x14000c234`
- end: `0x14000c39a`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400075d0`

## callees

- `0x1400016a0`
- `0x14000c234`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c2b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000c2b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c2d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c2d0`

## string_xrefs

- `0x14000c2b2`: `ntdll.dll`
- `0x14000c2c6`: `RtlQueryFeatureConfiguration`

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
0x14000c234  mov     [rsp+arg_10], rbx
0x14000c239  mov     [rsp+arg_18], rbp
0x14000c23e  push    rsi
0x14000c23f  push    rdi
0x14000c240  push    r14
0x14000c242  sub     rsp, 50h
0x14000c246  mov     rax, cs:__security_cookie
0x14000c24d  xor     rax, rsp
0x14000c250  mov     [rsp+68h+var_20], rax
0x14000c255  mov     rdi, [rsp+68h+arg_20]
0x14000c25d  mov     r14d, edx
0x14000c260  mov     rax, [rsp+68h+arg_28]
0x14000c268  mov     rsi, rcx
0x14000c26b  test    rdi, rdi
0x14000c26e  jz      short loc_14000C276
0x14000c270  mov     dword ptr [rdi], 0
0x14000c276  xor     ebp, ebp
0x14000c278  mov     [rsp+68h+var_38], 0
0x14000c281  test    r8d, r8d
0x14000c284  mov     ebx, 1
0x14000c289  mov     [rax], ebx
0x14000c28b  setz    bpl
0x14000c28f  xor     eax, eax
0x14000c291  mov     [rsp+68h+var_30], rax
0x14000c296  mov     [rsp+68h+var_28], eax
0x14000c29a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000c2a1  test    rax, rax
0x14000c2a4  jnz     short loc_14000C321
0x14000c2a6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c2ad  test    rax, rax
0x14000c2b0  jnz     short loc_14000C2C6
0x14000c2b2  lea     rcx, ModuleName; "ntdll.dll"
0x14000c2b9  call    cs:__imp_GetModuleHandleW
0x14000c2bf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c2c6  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000c2cd  mov     rcx, rax; hModule
0x14000c2d0  call    cs:__imp_GetProcAddress
0x14000c2d6  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000c2dd  test    rax, rax
0x14000c2e0  jnz     short loc_14000C321
0x14000c2e2  mov     r8d, 0C0000139h
0x14000c2e8  xor     ebx, ebx
0x14000c2ea  test    rdi, rdi
0x14000c2ed  jz      short loc_14000C2FD
0x14000c2ef  xor     ecx, ecx
0x14000c2f1  cmp     r8d, 80000022h
0x14000c2f8  setnz   cl
0x14000c2fb  mov     [rdi], ecx
0x14000c2fd  mov     eax, ebx
0x14000c2ff  mov     rcx, [rsp+68h+var_20]
0x14000c304  xor     rcx, rsp; StackCookie
0x14000c307  call    __security_check_cookie
0x14000c30c  lea     r11, [rsp+68h+var_18]
0x14000c311  mov     rbx, [r11+30h]
0x14000c315  mov     rbp, [r11+38h]
0x14000c319  mov     rsp, r11
0x14000c31c  pop     r14
0x14000c31e  pop     rdi
0x14000c31f  pop     rsi
0x14000c320  retn
0x14000c321  lea     r9, [rsp+68h+var_30]
0x14000c326  mov     edx, ebp
0x14000c328  lea     r8, [rsp+68h+var_38]
0x14000c32d  mov     ecx, r14d
0x14000c330  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c335  mov     r8d, eax
0x14000c338  test    eax, eax
0x14000c33a  jnz     short loc_14000C37E
0x14000c33c  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000c340  mov     ecx, edx
0x14000c342  mov     eax, [rsp+68h+var_28]
0x14000c346  mov     [rsi+0Ch], eax
0x14000c349  mov     eax, edx
0x14000c34b  shr     eax, 0Eh
0x14000c34e  shr     ecx, 4
0x14000c351  and     eax, 3
0x14000c354  and     ecx, 3
0x14000c357  mov     [rsi+8], eax
0x14000c35a  mov     [rsi], ecx
0x14000c35c  mov     eax, edx
0x14000c35e  mov     ecx, edx
0x14000c360  shr     eax, 6
0x14000c363  shr     ecx, 8
0x14000c366  and     eax, ebx
0x14000c368  and     cl, 3Fh
0x14000c36b  shr     edx, 7
0x14000c36e  and     edx, ebx
0x14000c370  mov     [rsi+4], cl
0x14000c373  mov     [rsi+10h], edx
0x14000c376  mov     [rsi+14h], eax
0x14000c379  jmp     loc_14000C2EA
0x14000c37e  cmp     eax, 117h
0x14000c383  jnz     loc_14000C2E8
0x14000c389  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000c38d  shr     eax, 7
0x14000c390  and     eax, ebx
0x14000c392  mov     [rsi+10h], eax
0x14000c395  jmp     loc_14000C2EA
```
