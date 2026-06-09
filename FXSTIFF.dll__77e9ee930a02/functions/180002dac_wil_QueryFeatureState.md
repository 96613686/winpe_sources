# wil_QueryFeatureState

- ea: `0x180002dac`
- end: `0x180002f23`
- name: `wil_QueryFeatureState`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000340c`

## callees

- `0x180002dac`
- `0x1800189d0`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180002e35`
- `KERNEL32!GetModuleHandleW` at `0x180002e35`
- `KERNEL32!GetProcAddress` at `0x180002e52`
- `KERNEL32!GetProcAddress` at `0x180002e52`

## string_xrefs

- `0x180002e2e`: `ntdll.dll`
- `0x180002e48`: `RtlQueryFeatureConfiguration`

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
0x180002dac  mov     [rsp+arg_10], rbx
0x180002db1  mov     [rsp+arg_18], rbp
0x180002db6  push    rsi
0x180002db7  push    rdi
0x180002db8  push    r14
0x180002dba  sub     rsp, 50h
0x180002dbe  mov     rax, cs:__security_cookie
0x180002dc5  xor     rax, rsp
0x180002dc8  mov     [rsp+68h+var_20], rax
0x180002dcd  mov     rdi, [rsp+68h+arg_20]
0x180002dd5  mov     r14d, edx
0x180002dd8  mov     rax, [rsp+68h+arg_28]
0x180002de0  mov     rsi, rcx
0x180002de3  test    rdi, rdi
0x180002de6  jz      short loc_180002DEE
0x180002de8  mov     dword ptr [rdi], 0
0x180002dee  xor     ebp, ebp
0x180002df0  mov     [rsp+68h+var_38], 0
0x180002df9  test    r8d, r8d
0x180002dfc  mov     ebx, 1
0x180002e01  mov     [rax], ebx
0x180002e03  setz    bpl
0x180002e07  xor     eax, eax
0x180002e09  mov     [rsp+68h+var_30], rax
0x180002e0e  mov     [rsp+68h+var_28], eax
0x180002e12  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180002e19  test    rax, rax
0x180002e1c  jnz     loc_180002EAA
0x180002e22  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180002e29  test    rax, rax
0x180002e2c  jnz     short loc_180002E48
0x180002e2e  lea     rcx, ModuleName; "ntdll.dll"
0x180002e35  call    cs:__imp_GetModuleHandleW
0x180002e3c  nop     dword ptr [rax+rax+00h]
0x180002e41  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x180002e48  lea     rdx, ProcName; "RtlQueryFeatureConfiguration"
0x180002e4f  mov     rcx, rax; hModule
0x180002e52  call    cs:__imp_GetProcAddress
0x180002e59  nop     dword ptr [rax+rax+00h]
0x180002e5e  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180002e65  test    rax, rax
0x180002e68  jnz     short loc_180002EAA
0x180002e6a  mov     r8d, 0C0000139h
0x180002e70  xor     ebx, ebx
0x180002e72  test    rdi, rdi
0x180002e75  jz      short loc_180002E85
0x180002e77  xor     ecx, ecx
0x180002e79  cmp     r8d, 80000022h
0x180002e80  setnz   cl
0x180002e83  mov     [rdi], ecx
0x180002e85  mov     eax, ebx
0x180002e87  mov     rcx, [rsp+68h+var_20]
0x180002e8c  xor     rcx, rsp; StackCookie
0x180002e8f  call    __security_check_cookie
0x180002e94  lea     r11, [rsp+68h+var_18]
0x180002e99  mov     rbx, [r11+30h]
0x180002e9d  mov     rbp, [r11+38h]
0x180002ea1  mov     rsp, r11
0x180002ea4  pop     r14
0x180002ea6  pop     rdi
0x180002ea7  pop     rsi
0x180002ea8  retn
0x180002eaa  lea     r9, [rsp+68h+var_30]
0x180002eaf  mov     edx, ebp
0x180002eb1  lea     r8, [rsp+68h+var_38]
0x180002eb6  mov     ecx, r14d
0x180002eb9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ebe  mov     r8d, eax
0x180002ec1  test    eax, eax
0x180002ec3  jnz     short loc_180002F07
0x180002ec5  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180002ec9  mov     ecx, edx
0x180002ecb  mov     eax, [rsp+68h+var_28]
0x180002ecf  mov     [rsi+0Ch], eax
0x180002ed2  mov     eax, edx
0x180002ed4  shr     eax, 0Eh
0x180002ed7  shr     ecx, 4
0x180002eda  and     eax, 3
0x180002edd  and     ecx, 3
0x180002ee0  mov     [rsi+8], eax
0x180002ee3  mov     [rsi], ecx
0x180002ee5  mov     eax, edx
0x180002ee7  mov     ecx, edx
0x180002ee9  shr     eax, 6
0x180002eec  shr     ecx, 8
0x180002eef  and     eax, ebx
0x180002ef1  and     cl, 3Fh
0x180002ef4  shr     edx, 7
0x180002ef7  and     edx, ebx
0x180002ef9  mov     [rsi+4], cl
0x180002efc  mov     [rsi+10h], edx
0x180002eff  mov     [rsi+14h], eax
0x180002f02  jmp     loc_180002E72
0x180002f07  cmp     eax, 117h
0x180002f0c  jnz     loc_180002E70
0x180002f12  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180002f16  shr     eax, 7
0x180002f19  and     eax, ebx
0x180002f1b  mov     [rsi+10h], eax
0x180002f1e  jmp     loc_180002E72
```
