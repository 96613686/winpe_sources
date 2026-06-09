# wil_QueryFeatureState

- ea: `0x180010c4c`
- end: `0x180010db2`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18000c928`

## callees

- `0x180002880`
- `0x180010c4c`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010ce8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010ce8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010ccb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180010ccb`

## string_xrefs

- `0x180010cc4`: `ntdll.dll`
- `0x180010cde`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_QueryFeatureState(__int64 a1, unsigned int a2, int a3, __int64 a4, _DWORD *a5, _DWORD *a6)
{
  int v6; // ebx
  BOOL v9; // r14d
  unsigned int v10; // ebp
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // ecx
  __int64 v16; // [rsp+30h] [rbp-48h] BYREF
  __int64 v17; // [rsp+38h] [rbp-40h] BYREF
  int v18; // [rsp+40h] [rbp-38h]

  v6 = 0;
  if ( a5 )
    *a5 = 0;
  *a6 = 1;
  v16 = 0;
  v9 = a3 == 0;
  v10 = 0;
  v17 = 0;
  v18 = 0;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      v13 = -1073741511;
      goto LABEL_13;
    }
  }
  v13 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(a2, v9, &v16, &v17);
  if ( v13 )
  {
    if ( v13 != 279 )
      goto LABEL_13;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v17) >> 7) & 1;
  }
  else
  {
    v14 = HIDWORD(v17);
    *(_DWORD *)a1 = (HIDWORD(v17) >> 4) & 3;
    *(_BYTE *)(a1 + 4) = BYTE1(v14) & 0x3F;
    *(_DWORD *)(a1 + 12) = v18;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v14 >> 14;
    *(_DWORD *)(a1 + 20) = (v14 >> 6) & 1;
    *(_DWORD *)(a1 + 16) = (v14 >> 7) & 1;
  }
  v10 = 1;
LABEL_13:
  if ( a5 )
  {
    LOBYTE(v6) = v13 != -2147483614;
    *a5 = v6;
  }
  return v10;
}

```

## disassembly

```asm
0x180010c4c  mov     [rsp+arg_10], rbx
0x180010c51  push    rbp
0x180010c52  push    rsi
0x180010c53  push    rdi
0x180010c54  push    r14
0x180010c56  push    r15
0x180010c58  sub     rsp, 50h
0x180010c5c  mov     rax, cs:__security_cookie
0x180010c63  xor     rax, rsp
0x180010c66  mov     [rsp+78h+var_30], rax
0x180010c6b  mov     rdi, [rsp+78h+arg_20]
0x180010c73  xor     ebx, ebx
0x180010c75  mov     rax, [rsp+78h+arg_28]
0x180010c7d  mov     r15d, edx
0x180010c80  mov     rsi, rcx
0x180010c83  test    rdi, rdi
0x180010c86  jz      short loc_180010C8A
0x180010c88  mov     [rdi], ebx
0x180010c8a  test    r8d, r8d
0x180010c8d  mov     dword ptr [rax], 1
0x180010c93  mov     r14d, ebx
0x180010c96  mov     [rsp+78h+var_48], rbx
0x180010c9b  setz    r14b
0x180010c9f  mov     ebp, ebx
0x180010ca1  xor     eax, eax
0x180010ca3  mov     [rsp+78h+var_40], rax
0x180010ca8  mov     [rsp+78h+var_38], eax
0x180010cac  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180010cb3  test    rax, rax
0x180010cb6  jnz     short loc_180010D07
0x180010cb8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010cbf  test    rax, rax
0x180010cc2  jnz     short loc_180010CDE
0x180010cc4  lea     rcx, aNtdllDll; "ntdll.dll"
0x180010ccb  call    cs:__imp_GetModuleHandleW
0x180010cd2  nop     dword ptr [rax+rax+00h]
0x180010cd7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180010cde  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180010ce5  mov     rcx, rax; hModule
0x180010ce8  call    cs:__imp_GetProcAddress
0x180010cef  nop     dword ptr [rax+rax+00h]
0x180010cf4  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180010cfb  test    rax, rax
0x180010cfe  jnz     short loc_180010D07
0x180010d00  mov     edx, 0C0000139h
0x180010d05  jmp     short loc_180010D7E
0x180010d07  lea     r9, [rsp+78h+var_40]
0x180010d0c  mov     edx, r14d
0x180010d0f  lea     r8, [rsp+78h+var_48]
0x180010d14  mov     ecx, r15d
0x180010d17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010d1c  mov     edx, eax
0x180010d1e  mov     ecx, eax
0x180010d20  test    eax, eax
0x180010d22  jnz     short loc_180010D64
0x180010d24  mov     ecx, dword ptr [rsp+78h+var_40+4]
0x180010d28  mov     eax, ecx
0x180010d2a  shr     eax, 4
0x180010d2d  and     eax, 3
0x180010d30  mov     [rsi], eax
0x180010d32  mov     eax, ecx
0x180010d34  shr     eax, 8
0x180010d37  and     al, 3Fh
0x180010d39  mov     [rsi+4], al
0x180010d3c  mov     eax, [rsp+78h+var_38]
0x180010d40  mov     [rsi+0Ch], eax
0x180010d43  mov     eax, ecx
0x180010d45  shr     eax, 0Eh
0x180010d48  and     eax, 3
0x180010d4b  mov     [rsi+8], eax
0x180010d4e  mov     eax, ecx
0x180010d50  shr     eax, 6
0x180010d53  and     eax, 1
0x180010d56  shr     ecx, 7
0x180010d59  and     ecx, 1
0x180010d5c  mov     [rsi+14h], eax
0x180010d5f  mov     [rsi+10h], ecx
0x180010d62  jmp     short loc_180010D79
0x180010d64  cmp     ecx, 117h
0x180010d6a  jnz     short loc_180010D7E
0x180010d6c  mov     eax, dword ptr [rsp+78h+var_40+4]
0x180010d70  shr     eax, 7
0x180010d73  and     eax, 1
0x180010d76  mov     [rsi+10h], eax
0x180010d79  mov     ebp, 1
0x180010d7e  test    rdi, rdi
0x180010d81  jz      short loc_180010D8E
0x180010d83  cmp     edx, 80000022h
0x180010d89  setnz   bl
0x180010d8c  mov     [rdi], ebx
0x180010d8e  mov     eax, ebp
0x180010d90  mov     rcx, [rsp+78h+var_30]
0x180010d95  xor     rcx, rsp; StackCookie
0x180010d98  call    __security_check_cookie
0x180010d9d  mov     rbx, [rsp+78h+arg_10]
0x180010da5  add     rsp, 50h
0x180010da9  pop     r15
0x180010dab  pop     r14
0x180010dad  pop     rdi
0x180010dae  pop     rsi
0x180010daf  pop     rbp
0x180010db0  retn
```
