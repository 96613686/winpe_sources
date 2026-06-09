# wil_QueryFeatureState

- ea: `0x1800089c8`
- end: `0x180008b2e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180005698`

## callees

- `0x1800089c8`
- `0x180016280`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180008a4d`
- `KERNEL32!GetModuleHandleW` at `0x180008a4d`
- `KERNEL32!GetProcAddress` at `0x180008a64`
- `KERNEL32!GetProcAddress` at `0x180008a64`

## string_xrefs

- `0x180008a46`: `ntdll.dll`
- `0x180008a5a`: `RtlQueryFeatureConfiguration`

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
0x1800089c8  mov     [rsp+arg_10], rbx
0x1800089cd  mov     [rsp+arg_18], rbp
0x1800089d2  push    rsi
0x1800089d3  push    rdi
0x1800089d4  push    r14
0x1800089d6  sub     rsp, 50h
0x1800089da  mov     rax, cs:__security_cookie
0x1800089e1  xor     rax, rsp
0x1800089e4  mov     [rsp+68h+var_20], rax
0x1800089e9  mov     rdi, [rsp+68h+arg_20]
0x1800089f1  mov     r14d, edx
0x1800089f4  mov     rax, [rsp+68h+arg_28]
0x1800089fc  mov     rsi, rcx
0x1800089ff  test    rdi, rdi
0x180008a02  jz      short loc_180008A0A
0x180008a04  mov     dword ptr [rdi], 0
0x180008a0a  xor     ebp, ebp
0x180008a0c  mov     [rsp+68h+var_38], 0
0x180008a15  test    r8d, r8d
0x180008a18  mov     ebx, 1
0x180008a1d  mov     [rax], ebx
0x180008a1f  setz    bpl
0x180008a23  xor     eax, eax
0x180008a25  mov     [rsp+68h+var_30], rax
0x180008a2a  mov     [rsp+68h+var_28], eax
0x180008a2e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180008a35  test    rax, rax
0x180008a38  jnz     short loc_180008AB5
0x180008a3a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a41  test    rax, rax
0x180008a44  jnz     short loc_180008A5A
0x180008a46  lea     rcx, ModuleName; "ntdll.dll"
0x180008a4d  call    cs:__imp_GetModuleHandleW
0x180008a53  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a5a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180008a61  mov     rcx, rax; hModule
0x180008a64  call    cs:__imp_GetProcAddress
0x180008a6a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180008a71  test    rax, rax
0x180008a74  jnz     short loc_180008AB5
0x180008a76  mov     r8d, 0C0000139h
0x180008a7c  xor     ebx, ebx
0x180008a7e  test    rdi, rdi
0x180008a81  jz      short loc_180008A91
0x180008a83  xor     ecx, ecx
0x180008a85  cmp     r8d, 80000022h
0x180008a8c  setnz   cl
0x180008a8f  mov     [rdi], ecx
0x180008a91  mov     eax, ebx
0x180008a93  mov     rcx, [rsp+68h+var_20]
0x180008a98  xor     rcx, rsp; StackCookie
0x180008a9b  call    __security_check_cookie
0x180008aa0  lea     r11, [rsp+68h+var_18]
0x180008aa5  mov     rbx, [r11+30h]
0x180008aa9  mov     rbp, [r11+38h]
0x180008aad  mov     rsp, r11
0x180008ab0  pop     r14
0x180008ab2  pop     rdi
0x180008ab3  pop     rsi
0x180008ab4  retn
0x180008ab5  lea     r9, [rsp+68h+var_30]
0x180008aba  mov     edx, ebp
0x180008abc  lea     r8, [rsp+68h+var_38]
0x180008ac1  mov     ecx, r14d
0x180008ac4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ac9  mov     r8d, eax
0x180008acc  test    eax, eax
0x180008ace  jnz     short loc_180008B12
0x180008ad0  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180008ad4  mov     ecx, edx
0x180008ad6  mov     eax, [rsp+68h+var_28]
0x180008ada  mov     [rsi+0Ch], eax
0x180008add  mov     eax, edx
0x180008adf  shr     eax, 0Eh
0x180008ae2  shr     ecx, 4
0x180008ae5  and     eax, 3
0x180008ae8  and     ecx, 3
0x180008aeb  mov     [rsi+8], eax
0x180008aee  mov     [rsi], ecx
0x180008af0  mov     eax, edx
0x180008af2  mov     ecx, edx
0x180008af4  shr     eax, 6
0x180008af7  shr     ecx, 8
0x180008afa  and     eax, ebx
0x180008afc  and     cl, 3Fh
0x180008aff  shr     edx, 7
0x180008b02  and     edx, ebx
0x180008b04  mov     [rsi+4], cl
0x180008b07  mov     [rsi+10h], edx
0x180008b0a  mov     [rsi+14h], eax
0x180008b0d  jmp     loc_180008A7E
0x180008b12  cmp     eax, 117h
0x180008b17  jnz     loc_180008A7C
0x180008b1d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180008b21  shr     eax, 7
0x180008b24  and     eax, ebx
0x180008b26  mov     [rsi+10h], eax
0x180008b29  jmp     loc_180008A7E
```
