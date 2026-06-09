# wil_QueryFeatureState

- ea: `0x18000ccd4`
- end: `0x18000ce3a`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1800089b4`

## callees

- `0x1800033d0`
- `0x18000ccd4`
- `0x180108010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cd59`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000cd59`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cd70`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000cd70`

## string_xrefs

- `0x18000cd52`: `ntdll.dll`
- `0x18000cd66`: `RtlQueryFeatureConfiguration`

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
0x18000ccd4  mov     [rsp+arg_10], rbx
0x18000ccd9  mov     [rsp+arg_18], rbp
0x18000ccde  push    rsi
0x18000ccdf  push    rdi
0x18000cce0  push    r14
0x18000cce2  sub     rsp, 50h
0x18000cce6  mov     rax, cs:__security_cookie
0x18000cced  xor     rax, rsp
0x18000ccf0  mov     [rsp+68h+var_20], rax
0x18000ccf5  mov     rdi, [rsp+68h+arg_20]
0x18000ccfd  mov     r14d, edx
0x18000cd00  mov     rax, [rsp+68h+arg_28]
0x18000cd08  mov     rsi, rcx
0x18000cd0b  test    rdi, rdi
0x18000cd0e  jz      short loc_18000CD16
0x18000cd10  mov     dword ptr [rdi], 0
0x18000cd16  xor     ebp, ebp
0x18000cd18  mov     [rsp+68h+var_38], 0
0x18000cd21  test    r8d, r8d
0x18000cd24  mov     ebx, 1
0x18000cd29  mov     [rax], ebx
0x18000cd2b  setz    bpl
0x18000cd2f  xor     eax, eax
0x18000cd31  mov     [rsp+68h+var_30], rax
0x18000cd36  mov     [rsp+68h+var_28], eax
0x18000cd3a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000cd41  test    rax, rax
0x18000cd44  jnz     short loc_18000CDC1
0x18000cd46  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cd4d  test    rax, rax
0x18000cd50  jnz     short loc_18000CD66
0x18000cd52  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000cd59  call    cs:__imp_GetModuleHandleW
0x18000cd5f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000cd66  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000cd6d  mov     rcx, rax; hModule
0x18000cd70  call    cs:__imp_GetProcAddress
0x18000cd76  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000cd7d  test    rax, rax
0x18000cd80  jnz     short loc_18000CDC1
0x18000cd82  mov     r8d, 0C0000139h
0x18000cd88  xor     ebx, ebx
0x18000cd8a  test    rdi, rdi
0x18000cd8d  jz      short loc_18000CD9D
0x18000cd8f  xor     ecx, ecx
0x18000cd91  cmp     r8d, 80000022h
0x18000cd98  setnz   cl
0x18000cd9b  mov     [rdi], ecx
0x18000cd9d  mov     eax, ebx
0x18000cd9f  mov     rcx, [rsp+68h+var_20]
0x18000cda4  xor     rcx, rsp; StackCookie
0x18000cda7  call    __security_check_cookie
0x18000cdac  lea     r11, [rsp+68h+var_18]
0x18000cdb1  mov     rbx, [r11+30h]
0x18000cdb5  mov     rbp, [r11+38h]
0x18000cdb9  mov     rsp, r11
0x18000cdbc  pop     r14
0x18000cdbe  pop     rdi
0x18000cdbf  pop     rsi
0x18000cdc0  retn
0x18000cdc1  lea     r9, [rsp+68h+var_30]
0x18000cdc6  mov     edx, ebp
0x18000cdc8  lea     r8, [rsp+68h+var_38]
0x18000cdcd  mov     ecx, r14d
0x18000cdd0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000cdd5  mov     r8d, eax
0x18000cdd8  test    eax, eax
0x18000cdda  jnz     short loc_18000CE1E
0x18000cddc  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000cde0  mov     ecx, edx
0x18000cde2  mov     eax, [rsp+68h+var_28]
0x18000cde6  mov     [rsi+0Ch], eax
0x18000cde9  mov     eax, edx
0x18000cdeb  shr     eax, 0Eh
0x18000cdee  shr     ecx, 4
0x18000cdf1  and     eax, 3
0x18000cdf4  and     ecx, 3
0x18000cdf7  mov     [rsi+8], eax
0x18000cdfa  mov     [rsi], ecx
0x18000cdfc  mov     eax, edx
0x18000cdfe  mov     ecx, edx
0x18000ce00  shr     eax, 6
0x18000ce03  shr     ecx, 8
0x18000ce06  and     eax, ebx
0x18000ce08  and     cl, 3Fh
0x18000ce0b  shr     edx, 7
0x18000ce0e  and     edx, ebx
0x18000ce10  mov     [rsi+4], cl
0x18000ce13  mov     [rsi+10h], edx
0x18000ce16  mov     [rsi+14h], eax
0x18000ce19  jmp     loc_18000CD8A
0x18000ce1e  cmp     eax, 117h
0x18000ce23  jnz     loc_18000CD88
0x18000ce29  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000ce2d  shr     eax, 7
0x18000ce30  and     eax, ebx
0x18000ce32  mov     [rsi+10h], eax
0x18000ce35  jmp     loc_18000CD8A
```
