# wil_QueryFeatureState

- ea: `0x180008b24`
- end: `0x180008c8a`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180005834`

## callees

- `0x180001ac0`
- `0x180008b24`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008bc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008bc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ba9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008ba9`

## string_xrefs

- `0x180008ba2`: `ntdll.dll`
- `0x180008bb6`: `RtlQueryFeatureConfiguration`

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
0x180008b24  mov     [rsp+arg_10], rbx
0x180008b29  mov     [rsp+arg_18], rbp
0x180008b2e  push    rsi
0x180008b2f  push    rdi
0x180008b30  push    r14
0x180008b32  sub     rsp, 50h
0x180008b36  mov     rax, cs:__security_cookie
0x180008b3d  xor     rax, rsp
0x180008b40  mov     [rsp+68h+var_20], rax
0x180008b45  mov     rdi, [rsp+68h+arg_20]
0x180008b4d  mov     r14d, edx
0x180008b50  mov     rax, [rsp+68h+arg_28]
0x180008b58  mov     rsi, rcx
0x180008b5b  test    rdi, rdi
0x180008b5e  jz      short loc_180008B66
0x180008b60  mov     dword ptr [rdi], 0
0x180008b66  xor     ebp, ebp
0x180008b68  mov     [rsp+68h+var_38], 0
0x180008b71  test    r8d, r8d
0x180008b74  mov     ebx, 1
0x180008b79  mov     [rax], ebx
0x180008b7b  setz    bpl
0x180008b7f  xor     eax, eax
0x180008b81  mov     [rsp+68h+var_30], rax
0x180008b86  mov     [rsp+68h+var_28], eax
0x180008b8a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180008b91  test    rax, rax
0x180008b94  jnz     short loc_180008C11
0x180008b96  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008b9d  test    rax, rax
0x180008ba0  jnz     short loc_180008BB6
0x180008ba2  lea     rcx, ModuleName; "ntdll.dll"
0x180008ba9  call    cs:__imp_GetModuleHandleW
0x180008baf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008bb6  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180008bbd  mov     rcx, rax; hModule
0x180008bc0  call    cs:__imp_GetProcAddress
0x180008bc6  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180008bcd  test    rax, rax
0x180008bd0  jnz     short loc_180008C11
0x180008bd2  mov     r8d, 0C0000139h
0x180008bd8  xor     ebx, ebx
0x180008bda  test    rdi, rdi
0x180008bdd  jz      short loc_180008BED
0x180008bdf  xor     ecx, ecx
0x180008be1  cmp     r8d, 80000022h
0x180008be8  setnz   cl
0x180008beb  mov     [rdi], ecx
0x180008bed  mov     eax, ebx
0x180008bef  mov     rcx, [rsp+68h+var_20]
0x180008bf4  xor     rcx, rsp; StackCookie
0x180008bf7  call    __security_check_cookie
0x180008bfc  lea     r11, [rsp+68h+var_18]
0x180008c01  mov     rbx, [r11+30h]
0x180008c05  mov     rbp, [r11+38h]
0x180008c09  mov     rsp, r11
0x180008c0c  pop     r14
0x180008c0e  pop     rdi
0x180008c0f  pop     rsi
0x180008c10  retn
0x180008c11  lea     r9, [rsp+68h+var_30]
0x180008c16  mov     edx, ebp
0x180008c18  lea     r8, [rsp+68h+var_38]
0x180008c1d  mov     ecx, r14d
0x180008c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c25  mov     r8d, eax
0x180008c28  test    eax, eax
0x180008c2a  jnz     short loc_180008C6E
0x180008c2c  mov     edx, dword ptr [rsp+68h+var_30+4]
0x180008c30  mov     ecx, edx
0x180008c32  mov     eax, [rsp+68h+var_28]
0x180008c36  mov     [rsi+0Ch], eax
0x180008c39  mov     eax, edx
0x180008c3b  shr     eax, 0Eh
0x180008c3e  shr     ecx, 4
0x180008c41  and     eax, 3
0x180008c44  and     ecx, 3
0x180008c47  mov     [rsi+8], eax
0x180008c4a  mov     [rsi], ecx
0x180008c4c  mov     eax, edx
0x180008c4e  mov     ecx, edx
0x180008c50  shr     eax, 6
0x180008c53  shr     ecx, 8
0x180008c56  and     eax, ebx
0x180008c58  and     cl, 3Fh
0x180008c5b  shr     edx, 7
0x180008c5e  and     edx, ebx
0x180008c60  mov     [rsi+4], cl
0x180008c63  mov     [rsi+10h], edx
0x180008c66  mov     [rsi+14h], eax
0x180008c69  jmp     loc_180008BDA
0x180008c6e  cmp     eax, 117h
0x180008c73  jnz     loc_180008BD8
0x180008c79  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180008c7d  shr     eax, 7
0x180008c80  and     eax, ebx
0x180008c82  mov     [rsi+10h], eax
0x180008c85  jmp     loc_180008BDA
```
