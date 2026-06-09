# wil_RtlStagingConfig_QueryFeatureState

- ea: `0x180008060`
- end: `0x1800081a5`
- name: `wil_RtlStagingConfig_QueryFeatureState`
- size: `325`
- prototype: `__int64 __fastcall(_QWORD, _QWORD, _QWORD, _QWORD)`
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180007de0`
- `0x180007f50`

## callees

- `0x180008060`
- `0x18001aec0`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800080bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800080bf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080d6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800080d6`

## string_xrefs

- `0x1800080b8`: `ntdll.dll`
- `0x1800080cc`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_RtlStagingConfig_QueryFeatureState(__int64 a1, unsigned int a2, int a3, _DWORD *a4)
{
  BOOL v7; // esi
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v10; // r8d
  __int64 result; // rax
  int v12; // eax
  unsigned int v13; // edx
  unsigned int v14; // ecx
  __int64 v15; // [rsp+30h] [rbp-38h] BYREF
  __int64 v16; // [rsp+38h] [rbp-30h] BYREF
  int v17; // [rsp+40h] [rbp-28h]

  v15 = 0;
  v7 = a3 == 0;
  v16 = 0;
  v17 = 0;
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
      v10 = -1073741511;
LABEL_6:
      result = 0;
      goto LABEL_7;
    }
  }
  v12 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(a2, v7, &v15, &v16);
  v10 = v12;
  if ( v12 )
  {
    if ( v12 != 279 )
      goto LABEL_6;
    *(_DWORD *)(a1 + 16) = (HIDWORD(v16) >> 7) & 1;
    result = 1;
  }
  else
  {
    v13 = HIDWORD(v16);
    v14 = HIDWORD(v16);
    *(_DWORD *)(a1 + 12) = v17;
    *(_DWORD *)(a1 + 8) = (unsigned __int16)v14 >> 14;
    *(_DWORD *)a1 = (v14 >> 4) & 3;
    *(_DWORD *)(a1 + 20) = (v13 >> 6) & 1;
    *(_DWORD *)(a1 + 16) = (v13 >> 7) & 1;
    result = 1;
    *(_BYTE *)(a1 + 4) = BYTE1(v13) & 0x3F;
  }
LABEL_7:
  if ( a4 )
    *a4 = v10 != -2147483614;
  return result;
}

```

## disassembly

```asm
0x180008060  mov     [rsp+arg_10], rbx
0x180008065  push    rbp
0x180008066  push    rsi
0x180008067  push    rdi
0x180008068  sub     rsp, 50h
0x18000806c  mov     rax, cs:__security_cookie
0x180008073  xor     rax, rsp
0x180008076  mov     [rsp+68h+var_20], rax
0x18000807b  xor     esi, esi
0x18000807d  mov     [rsp+68h+var_38], 0
0x180008086  test    r8d, r8d
0x180008089  mov     rdi, r9
0x18000808c  mov     ebp, edx
0x18000808e  mov     rbx, rcx
0x180008091  setz    sil
0x180008095  xor     eax, eax
0x180008097  mov     [rsp+68h+var_30], rax
0x18000809c  mov     [rsp+68h+var_28], eax
0x1800080a0  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x1800080a7  test    rax, rax
0x1800080aa  jnz     short loc_180008120
0x1800080ac  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800080b3  test    rax, rax
0x1800080b6  jnz     short loc_1800080CC
0x1800080b8  lea     rcx, ModuleName; "ntdll.dll"
0x1800080bf  call    cs:__imp_GetModuleHandleW
0x1800080c5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800080cc  lea     rdx, ProcName; "RtlQueryFeatureConfiguration"
0x1800080d3  mov     rcx, rax; hModule
0x1800080d6  call    cs:__imp_GetProcAddress
0x1800080dc  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1800080e3  test    rax, rax
0x1800080e6  jnz     short loc_180008120
0x1800080e8  mov     r8d, 0C0000139h
0x1800080ee  xor     eax, eax
0x1800080f0  test    rdi, rdi
0x1800080f3  jz      short loc_180008103
0x1800080f5  xor     ecx, ecx
0x1800080f7  cmp     r8d, 80000022h
0x1800080fe  setnz   cl
0x180008101  mov     [rdi], ecx
0x180008103  mov     rcx, [rsp+68h+var_20]
0x180008108  xor     rcx, rsp; StackCookie
0x18000810b  call    __security_check_cookie
0x180008110  mov     rbx, [rsp+68h+arg_10]
0x180008118  add     rsp, 50h
0x18000811c  pop     rdi
0x18000811d  pop     rsi
0x18000811e  pop     rbp
0x18000811f  retn
0x180008120  lea     r9, [rsp+68h+var_30]
0x180008125  mov     edx, esi
0x180008127  lea     r8, [rsp+68h+var_38]
0x18000812c  mov     ecx, ebp
0x18000812e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008133  mov     r8d, eax
0x180008136  test    eax, eax
0x180008138  jnz     short loc_180008183
0x18000813a  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000813e  mov     ecx, edx
0x180008140  mov     eax, [rsp+68h+var_28]
0x180008144  mov     [rbx+0Ch], eax
0x180008147  mov     eax, edx
0x180008149  shr     eax, 0Eh
0x18000814c  and     eax, 3
0x18000814f  shr     ecx, 4
0x180008152  and     ecx, 3
0x180008155  mov     [rbx+8], eax
0x180008158  mov     [rbx], ecx
0x18000815a  mov     eax, edx
0x18000815c  mov     ecx, edx
0x18000815e  shr     eax, 6
0x180008161  and     eax, 1
0x180008164  shr     ecx, 8
0x180008167  and     cl, 3Fh
0x18000816a  shr     edx, 7
0x18000816d  and     edx, 1
0x180008170  mov     [rbx+14h], eax
0x180008173  mov     [rbx+10h], edx
0x180008176  mov     eax, 1
0x18000817b  mov     [rbx+4], cl
0x18000817e  jmp     loc_1800080F0
0x180008183  cmp     eax, 117h
0x180008188  jnz     loc_1800080EE
0x18000818e  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180008192  shr     eax, 7
0x180008195  and     eax, 1
0x180008198  mov     [rbx+10h], eax
0x18000819b  mov     eax, 1
0x1800081a0  jmp     loc_1800080F0
```
