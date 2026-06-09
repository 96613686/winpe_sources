# wil_QueryFeatureState

- ea: `0x18000a1f8`
- end: `0x18000a35e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180006594`

## callees

- `0x180001d40`
- `0x18000a1f8`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a294`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a294`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a27d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a27d`

## string_xrefs

- `0x18000a276`: `ntdll.dll`
- `0x18000a28a`: `RtlQueryFeatureConfiguration`

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
0x18000a1f8  mov     [rsp+arg_10], rbx
0x18000a1fd  mov     [rsp+arg_18], rbp
0x18000a202  push    rsi
0x18000a203  push    rdi
0x18000a204  push    r14
0x18000a206  sub     rsp, 50h
0x18000a20a  mov     rax, cs:__security_cookie
0x18000a211  xor     rax, rsp
0x18000a214  mov     [rsp+68h+var_20], rax
0x18000a219  mov     rdi, [rsp+68h+arg_20]
0x18000a221  mov     r14d, edx
0x18000a224  mov     rax, [rsp+68h+arg_28]
0x18000a22c  mov     rsi, rcx
0x18000a22f  test    rdi, rdi
0x18000a232  jz      short loc_18000A23A
0x18000a234  mov     dword ptr [rdi], 0
0x18000a23a  xor     ebp, ebp
0x18000a23c  mov     [rsp+68h+var_38], 0
0x18000a245  test    r8d, r8d
0x18000a248  mov     ebx, 1
0x18000a24d  mov     [rax], ebx
0x18000a24f  setz    bpl
0x18000a253  xor     eax, eax
0x18000a255  mov     [rsp+68h+var_30], rax
0x18000a25a  mov     [rsp+68h+var_28], eax
0x18000a25e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000a265  test    rax, rax
0x18000a268  jnz     short loc_18000A2E5
0x18000a26a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a271  test    rax, rax
0x18000a274  jnz     short loc_18000A28A
0x18000a276  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a27d  call    cs:__imp_GetModuleHandleW
0x18000a283  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a28a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000a291  mov     rcx, rax; hModule
0x18000a294  call    cs:__imp_GetProcAddress
0x18000a29a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000a2a1  test    rax, rax
0x18000a2a4  jnz     short loc_18000A2E5
0x18000a2a6  mov     r8d, 0C0000139h
0x18000a2ac  xor     ebx, ebx
0x18000a2ae  test    rdi, rdi
0x18000a2b1  jz      short loc_18000A2C1
0x18000a2b3  xor     ecx, ecx
0x18000a2b5  cmp     r8d, 80000022h
0x18000a2bc  setnz   cl
0x18000a2bf  mov     [rdi], ecx
0x18000a2c1  mov     eax, ebx
0x18000a2c3  mov     rcx, [rsp+68h+var_20]
0x18000a2c8  xor     rcx, rsp; StackCookie
0x18000a2cb  call    __security_check_cookie
0x18000a2d0  lea     r11, [rsp+68h+var_18]
0x18000a2d5  mov     rbx, [r11+30h]
0x18000a2d9  mov     rbp, [r11+38h]
0x18000a2dd  mov     rsp, r11
0x18000a2e0  pop     r14
0x18000a2e2  pop     rdi
0x18000a2e3  pop     rsi
0x18000a2e4  retn
0x18000a2e5  lea     r9, [rsp+68h+var_30]
0x18000a2ea  mov     edx, ebp
0x18000a2ec  lea     r8, [rsp+68h+var_38]
0x18000a2f1  mov     ecx, r14d
0x18000a2f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2f9  mov     r8d, eax
0x18000a2fc  test    eax, eax
0x18000a2fe  jnz     short loc_18000A342
0x18000a300  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000a304  mov     ecx, edx
0x18000a306  mov     eax, [rsp+68h+var_28]
0x18000a30a  mov     [rsi+0Ch], eax
0x18000a30d  mov     eax, edx
0x18000a30f  shr     eax, 0Eh
0x18000a312  shr     ecx, 4
0x18000a315  and     eax, 3
0x18000a318  and     ecx, 3
0x18000a31b  mov     [rsi+8], eax
0x18000a31e  mov     [rsi], ecx
0x18000a320  mov     eax, edx
0x18000a322  mov     ecx, edx
0x18000a324  shr     eax, 6
0x18000a327  shr     ecx, 8
0x18000a32a  and     eax, ebx
0x18000a32c  and     cl, 3Fh
0x18000a32f  shr     edx, 7
0x18000a332  and     edx, ebx
0x18000a334  mov     [rsi+4], cl
0x18000a337  mov     [rsi+10h], edx
0x18000a33a  mov     [rsi+14h], eax
0x18000a33d  jmp     loc_18000A2AE
0x18000a342  cmp     eax, 117h
0x18000a347  jnz     loc_18000A2AC
0x18000a34d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000a351  shr     eax, 7
0x18000a354  and     eax, ebx
0x18000a356  mov     [rsi+10h], eax
0x18000a359  jmp     loc_18000A2AE
```
