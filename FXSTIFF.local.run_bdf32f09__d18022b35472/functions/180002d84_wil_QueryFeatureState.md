# wil_QueryFeatureState

- ea: `0x180002d84`
- end: `0x180002eea`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800033b4`

## callees

- `0x180002d84`
- `0x180017c00`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180002e09`
- `KERNEL32!GetModuleHandleW` at `0x180002e09`
- `KERNEL32!GetProcAddress` at `0x180002e20`
- `KERNEL32!GetProcAddress` at `0x180002e20`

## string_xrefs

- `0x180002e02`: `ntdll.dll`
- `0x180002e16`: `RtlQueryFeatureConfiguration`

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
0x180002d84  mov     [rsp+arg_10], rbx
0x180002d89  mov     [rsp+arg_18], rbp
0x180002d8e  push    rsi
0x180002d8f  push    rdi
0x180002d90  push    r14
0x180002d92  sub     rsp, 50h
0x180002d96  mov     rax, cs:__security_cookie
0x180002d9d  xor     rax, rsp
0x180002da0  mov     [rsp+68h+var_20], rax
0x180002da5  mov     rdi, [rsp+68h+arg_20]
0x180002dad  mov     r14d, edx
0x180002db0  mov     rax, [rsp+68h+arg_28]
0x180002db8  mov     rsi, rcx
0x180002dbb  test    rdi, rdi
0x180002dbe  jz      short loc_180002DC6
0x180002dc0  mov     dword ptr [rdi], 0
0x180002dc6  xor     ebp, ebp
0x180002dc8  mov     [rsp+68h+var_38], 0
0x180002dd1  test    r8d, r8d
0x180002dd4  mov     ebx, 1
0x180002dd9  mov     [rax], ebx
0x180002ddb  setz    bpl
0x180002ddf  xor     eax, eax
0x180002de1  mov     [rsp+68h+var_30], rax
0x180002de6  mov     [rsp+68h+var_28], eax
0x180002dea  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180002df1  test    rax, rax
0x180002df4  jnz     short loc_180002E71
0x180002df6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180002dfd  test    rax, rax
0x180002e00  jnz     short loc_180002E16
0x180002e02  lea     rcx, ModuleName; "ntdll.dll"
0x180002e09  call    cs:__imp_GetModuleHandleW
0x180002e0f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180002e16  lea     rdx, ProcName; "RtlQueryFeatureConfiguration"
0x180002e1d  mov     rcx, rax; hModule
0x180002e20  call    cs:__imp_GetProcAddress
0x180002e26  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180002e2d  test    rax, rax
0x180002e30  jnz     short loc_180002E71
0x180002e32  mov     r8d, 0C0000139h
0x180002e38  xor     ebx, ebx
0x180002e3a  test    rdi, rdi
0x180002e3d  jz      short loc_180002E4D
0x180002e3f  xor     ecx, ecx
0x180002e41  cmp     r8d, 80000022h
0x180002e48  setnz   cl
0x180002e4b  mov     [rdi], ecx
0x180002e4d  mov     eax, ebx
0x180002e4f  mov     rcx, [rsp+68h+var_20]
0x180002e54  xor     rcx, rsp; StackCookie
0x180002e57  call    __security_check_cookie
0x180002e5c  lea     r11, [rsp+68h+var_18]
0x180002e61  mov     rbx, [r11+30h]
0x180002e65  mov     rbp, [r11+38h]
0x180002e69  mov     rsp, r11
0x180002e6c  pop     r14
0x180002e6e  pop     rdi
0x180002e6f  pop     rsi
0x180002e70  retn
0x180002e71  lea     r9, [rsp+68h+var_30]
0x180002e76  mov     edx, ebp
0x180002e78  lea     r8, [rsp+68h+var_38]
0x180002e7d  mov     ecx, r14d
0x180002e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002e85  mov     r8d, eax
0x180002e88  test    eax, eax
0x180002e8a  jnz     short loc_180002ECE
0x180002e8c  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180002e90  mov     ecx, edx
0x180002e92  mov     eax, [rsp+68h+var_28]
0x180002e96  mov     [rsi+0Ch], eax
0x180002e99  mov     eax, edx
0x180002e9b  shr     eax, 0Eh
0x180002e9e  shr     ecx, 4
0x180002ea1  and     eax, 3
0x180002ea4  and     ecx, 3
0x180002ea7  mov     [rsi+8], eax
0x180002eaa  mov     [rsi], ecx
0x180002eac  mov     eax, edx
0x180002eae  mov     ecx, edx
0x180002eb0  shr     eax, 6
0x180002eb3  shr     ecx, 8
0x180002eb6  and     eax, ebx
0x180002eb8  and     cl, 3Fh
0x180002ebb  shr     edx, 7
0x180002ebe  and     edx, ebx
0x180002ec0  mov     [rsi+4], cl
0x180002ec3  mov     [rsi+10h], edx
0x180002ec6  mov     [rsi+14h], eax
0x180002ec9  jmp     loc_180002E3A
0x180002ece  cmp     eax, 117h
0x180002ed3  jnz     loc_180002E38
0x180002ed9  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180002edd  shr     eax, 7
0x180002ee0  and     eax, ebx
0x180002ee2  mov     [rsi+10h], eax
0x180002ee5  jmp     loc_180002E3A
```
