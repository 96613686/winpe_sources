# wil_QueryFeatureState

- ea: `0x18000aab8`
- end: `0x18000ac1e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180006c68`
- `0x180028cc4`

## callees

- `0x180002350`
- `0x18000aab8`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ab54`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ab54`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ab3d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ab3d`

## string_xrefs

- `0x18000ab36`: `ntdll.dll`
- `0x18000ab4a`: `RtlQueryFeatureConfiguration`

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
0x18000aab8  mov     [rsp+arg_10], rbx
0x18000aabd  mov     [rsp+arg_18], rbp
0x18000aac2  push    rsi
0x18000aac3  push    rdi
0x18000aac4  push    r14
0x18000aac6  sub     rsp, 50h
0x18000aaca  mov     rax, cs:__security_cookie
0x18000aad1  xor     rax, rsp
0x18000aad4  mov     [rsp+68h+var_20], rax
0x18000aad9  mov     rdi, [rsp+68h+arg_20]
0x18000aae1  mov     r14d, edx
0x18000aae4  mov     rax, [rsp+68h+arg_28]
0x18000aaec  mov     rsi, rcx
0x18000aaef  test    rdi, rdi
0x18000aaf2  jz      short loc_18000AAFA
0x18000aaf4  mov     dword ptr [rdi], 0
0x18000aafa  xor     ebp, ebp
0x18000aafc  mov     [rsp+68h+var_38], 0
0x18000ab05  test    r8d, r8d
0x18000ab08  mov     ebx, 1
0x18000ab0d  mov     [rax], ebx
0x18000ab0f  setz    bpl
0x18000ab13  xor     eax, eax
0x18000ab15  mov     [rsp+68h+var_30], rax
0x18000ab1a  mov     [rsp+68h+var_28], eax
0x18000ab1e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000ab25  test    rax, rax
0x18000ab28  jnz     short loc_18000ABA5
0x18000ab2a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ab31  test    rax, rax
0x18000ab34  jnz     short loc_18000AB4A
0x18000ab36  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000ab3d  call    cs:__imp_GetModuleHandleW
0x18000ab43  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ab4a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000ab51  mov     rcx, rax; hModule
0x18000ab54  call    cs:__imp_GetProcAddress
0x18000ab5a  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000ab61  test    rax, rax
0x18000ab64  jnz     short loc_18000ABA5
0x18000ab66  mov     r8d, 0C0000139h
0x18000ab6c  xor     ebx, ebx
0x18000ab6e  test    rdi, rdi
0x18000ab71  jz      short loc_18000AB81
0x18000ab73  xor     ecx, ecx
0x18000ab75  cmp     r8d, 80000022h
0x18000ab7c  setnz   cl
0x18000ab7f  mov     [rdi], ecx
0x18000ab81  mov     eax, ebx
0x18000ab83  mov     rcx, [rsp+68h+var_20]
0x18000ab88  xor     rcx, rsp; StackCookie
0x18000ab8b  call    __security_check_cookie
0x18000ab90  lea     r11, [rsp+68h+var_18]
0x18000ab95  mov     rbx, [r11+30h]
0x18000ab99  mov     rbp, [r11+38h]
0x18000ab9d  mov     rsp, r11
0x18000aba0  pop     r14
0x18000aba2  pop     rdi
0x18000aba3  pop     rsi
0x18000aba4  retn
0x18000aba5  lea     r9, [rsp+68h+var_30]
0x18000abaa  mov     edx, ebp
0x18000abac  lea     r8, [rsp+68h+var_38]
0x18000abb1  mov     ecx, r14d
0x18000abb4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000abb9  mov     r8d, eax
0x18000abbc  test    eax, eax
0x18000abbe  jnz     short loc_18000AC02
0x18000abc0  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000abc4  mov     ecx, edx
0x18000abc6  mov     eax, [rsp+68h+var_28]
0x18000abca  mov     [rsi+0Ch], eax
0x18000abcd  mov     eax, edx
0x18000abcf  shr     eax, 0Eh
0x18000abd2  shr     ecx, 4
0x18000abd5  and     eax, 3
0x18000abd8  and     ecx, 3
0x18000abdb  mov     [rsi+8], eax
0x18000abde  mov     [rsi], ecx
0x18000abe0  mov     eax, edx
0x18000abe2  mov     ecx, edx
0x18000abe4  shr     eax, 6
0x18000abe7  shr     ecx, 8
0x18000abea  and     eax, ebx
0x18000abec  and     cl, 3Fh
0x18000abef  shr     edx, 7
0x18000abf2  and     edx, ebx
0x18000abf4  mov     [rsi+4], cl
0x18000abf7  mov     [rsi+10h], edx
0x18000abfa  mov     [rsi+14h], eax
0x18000abfd  jmp     loc_18000AB6E
0x18000ac02  cmp     eax, 117h
0x18000ac07  jnz     loc_18000AB6C
0x18000ac0d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000ac11  shr     eax, 7
0x18000ac14  and     eax, ebx
0x18000ac16  mov     [rsi+10h], eax
0x18000ac19  jmp     loc_18000AB6E
```
