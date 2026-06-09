# wil_QueryFeatureState

- ea: `0x180010198`
- end: `0x1800102fe`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c3a0`

## callees

- `0x1800028f0`
- `0x180010198`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001021d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001021d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010234`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010234`

## string_xrefs

- `0x180010216`: `ntdll.dll`
- `0x18001022a`: `RtlQueryFeatureConfiguration`

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
0x180010198  mov     [rsp+arg_10], rbx
0x18001019d  mov     [rsp+arg_18], rbp
0x1800101a2  push    rsi
0x1800101a3  push    rdi
0x1800101a4  push    r14
0x1800101a6  sub     rsp, 50h
0x1800101aa  mov     rax, cs:__security_cookie
0x1800101b1  xor     rax, rsp
0x1800101b4  mov     [rsp+68h+var_20], rax
0x1800101b9  mov     rdi, [rsp+68h+arg_20]
0x1800101c1  mov     r14d, edx
0x1800101c4  mov     rax, [rsp+68h+arg_28]
0x1800101cc  mov     rsi, rcx
0x1800101cf  test    rdi, rdi
0x1800101d2  jz      short loc_1800101DA
0x1800101d4  mov     dword ptr [rdi], 0
0x1800101da  xor     ebp, ebp
0x1800101dc  mov     [rsp+68h+var_38], 0
0x1800101e5  test    r8d, r8d
0x1800101e8  mov     ebx, 1
0x1800101ed  mov     [rax], ebx
0x1800101ef  setz    bpl
0x1800101f3  xor     eax, eax
0x1800101f5  mov     [rsp+68h+var_30], rax
0x1800101fa  mov     [rsp+68h+var_28], eax
0x1800101fe  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180010205  test    rax, rax
0x180010208  jnz     short loc_180010285
0x18001020a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010211  test    rax, rax
0x180010214  jnz     short loc_18001022A
0x180010216  lea     rcx, aNtdllDll; "ntdll.dll"
0x18001021d  call    cs:__imp_GetModuleHandleW
0x180010223  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001022a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180010231  mov     rcx, rax; hModule
0x180010234  call    cs:__imp_GetProcAddress
0x18001023a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180010241  test    rax, rax
0x180010244  jnz     short loc_180010285
0x180010246  mov     r8d, 0C0000139h
0x18001024c  xor     ebx, ebx
0x18001024e  test    rdi, rdi
0x180010251  jz      short loc_180010261
0x180010253  xor     ecx, ecx
0x180010255  cmp     r8d, 80000022h
0x18001025c  setnz   cl
0x18001025f  mov     [rdi], ecx
0x180010261  mov     eax, ebx
0x180010263  mov     rcx, [rsp+68h+var_20]
0x180010268  xor     rcx, rsp; StackCookie
0x18001026b  call    __security_check_cookie
0x180010270  lea     r11, [rsp+68h+var_18]
0x180010275  mov     rbx, [r11+30h]
0x180010279  mov     rbp, [r11+38h]
0x18001027d  mov     rsp, r11
0x180010280  pop     r14
0x180010282  pop     rdi
0x180010283  pop     rsi
0x180010284  retn
0x180010285  lea     r9, [rsp+68h+var_30]
0x18001028a  mov     edx, ebp
0x18001028c  lea     r8, [rsp+68h+var_38]
0x180010291  mov     ecx, r14d
0x180010294  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010299  mov     r8d, eax
0x18001029c  test    eax, eax
0x18001029e  jnz     short loc_1800102E2
0x1800102a0  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800102a4  mov     ecx, edx
0x1800102a6  mov     eax, [rsp+68h+var_28]
0x1800102aa  mov     [rsi+0Ch], eax
0x1800102ad  mov     eax, edx
0x1800102af  shr     eax, 0Eh
0x1800102b2  shr     ecx, 4
0x1800102b5  and     eax, 3
0x1800102b8  and     ecx, 3
0x1800102bb  mov     [rsi+8], eax
0x1800102be  mov     [rsi], ecx
0x1800102c0  mov     eax, edx
0x1800102c2  mov     ecx, edx
0x1800102c4  shr     eax, 6
0x1800102c7  shr     ecx, 8
0x1800102ca  and     eax, ebx
0x1800102cc  and     cl, 3Fh
0x1800102cf  shr     edx, 7
0x1800102d2  and     edx, ebx
0x1800102d4  mov     [rsi+4], cl
0x1800102d7  mov     [rsi+10h], edx
0x1800102da  mov     [rsi+14h], eax
0x1800102dd  jmp     loc_18001024E
0x1800102e2  cmp     eax, 117h
0x1800102e7  jnz     loc_18001024C
0x1800102ed  mov     eax, dword ptr [rsp+68h+var_30+4]
0x1800102f1  shr     eax, 7
0x1800102f4  and     eax, ebx
0x1800102f6  mov     [rsi+10h], eax
0x1800102f9  jmp     loc_18001024E
```
