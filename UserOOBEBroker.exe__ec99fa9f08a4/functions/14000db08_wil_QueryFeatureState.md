# wil_QueryFeatureState

- ea: `0x14000db08`
- end: `0x14000dc6e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x14000a660`

## callees

- `0x14000db08`
- `0x14000e1c0`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000dba4`
- `KERNEL32!GetProcAddress` at `0x14000dba4`
- `KERNEL32!GetModuleHandleW` at `0x14000db8d`
- `KERNEL32!GetModuleHandleW` at `0x14000db8d`

## string_xrefs

- `0x14000db86`: `ntdll.dll`
- `0x14000db9a`: `RtlQueryFeatureConfiguration`

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
0x14000db08  mov     [rsp+arg_10], rbx
0x14000db0d  mov     [rsp+arg_18], rbp
0x14000db12  push    rsi
0x14000db13  push    rdi
0x14000db14  push    r14
0x14000db16  sub     rsp, 50h
0x14000db1a  mov     rax, cs:__security_cookie
0x14000db21  xor     rax, rsp
0x14000db24  mov     [rsp+68h+var_20], rax
0x14000db29  mov     rdi, [rsp+68h+arg_20]
0x14000db31  mov     r14d, edx
0x14000db34  mov     rax, [rsp+68h+arg_28]
0x14000db3c  mov     rsi, rcx
0x14000db3f  test    rdi, rdi
0x14000db42  jz      short loc_14000DB4A
0x14000db44  mov     dword ptr [rdi], 0
0x14000db4a  xor     ebp, ebp
0x14000db4c  mov     [rsp+68h+var_38], 0
0x14000db55  test    r8d, r8d
0x14000db58  mov     ebx, 1
0x14000db5d  mov     [rax], ebx
0x14000db5f  setz    bpl
0x14000db63  xor     eax, eax
0x14000db65  mov     [rsp+68h+var_30], rax
0x14000db6a  mov     [rsp+68h+var_28], eax
0x14000db6e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000db75  test    rax, rax
0x14000db78  jnz     short loc_14000DBF5
0x14000db7a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000db81  test    rax, rax
0x14000db84  jnz     short loc_14000DB9A
0x14000db86  lea     rcx, ModuleName; "ntdll.dll"
0x14000db8d  call    cs:__imp_GetModuleHandleW
0x14000db93  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000db9a  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000dba1  mov     rcx, rax; hModule
0x14000dba4  call    cs:__imp_GetProcAddress
0x14000dbaa  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000dbb1  test    rax, rax
0x14000dbb4  jnz     short loc_14000DBF5
0x14000dbb6  mov     r8d, 0C0000139h
0x14000dbbc  xor     ebx, ebx
0x14000dbbe  test    rdi, rdi
0x14000dbc1  jz      short loc_14000DBD1
0x14000dbc3  xor     ecx, ecx
0x14000dbc5  cmp     r8d, 80000022h
0x14000dbcc  setnz   cl
0x14000dbcf  mov     [rdi], ecx
0x14000dbd1  mov     eax, ebx
0x14000dbd3  mov     rcx, [rsp+68h+var_20]
0x14000dbd8  xor     rcx, rsp; StackCookie
0x14000dbdb  call    __security_check_cookie
0x14000dbe0  lea     r11, [rsp+68h+var_18]
0x14000dbe5  mov     rbx, [r11+30h]
0x14000dbe9  mov     rbp, [r11+38h]
0x14000dbed  mov     rsp, r11
0x14000dbf0  pop     r14
0x14000dbf2  pop     rdi
0x14000dbf3  pop     rsi
0x14000dbf4  retn
0x14000dbf5  lea     r9, [rsp+68h+var_30]
0x14000dbfa  mov     edx, ebp
0x14000dbfc  lea     r8, [rsp+68h+var_38]
0x14000dc01  mov     ecx, r14d
0x14000dc04  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dc09  mov     r8d, eax
0x14000dc0c  test    eax, eax
0x14000dc0e  jnz     short loc_14000DC52
0x14000dc10  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000dc14  mov     ecx, edx
0x14000dc16  mov     eax, [rsp+68h+var_28]
0x14000dc1a  mov     [rsi+0Ch], eax
0x14000dc1d  mov     eax, edx
0x14000dc1f  shr     eax, 0Eh
0x14000dc22  shr     ecx, 4
0x14000dc25  and     eax, 3
0x14000dc28  and     ecx, 3
0x14000dc2b  mov     [rsi+8], eax
0x14000dc2e  mov     [rsi], ecx
0x14000dc30  mov     eax, edx
0x14000dc32  mov     ecx, edx
0x14000dc34  shr     eax, 6
0x14000dc37  shr     ecx, 8
0x14000dc3a  and     eax, ebx
0x14000dc3c  and     cl, 3Fh
0x14000dc3f  shr     edx, 7
0x14000dc42  and     edx, ebx
0x14000dc44  mov     [rsi+4], cl
0x14000dc47  mov     [rsi+10h], edx
0x14000dc4a  mov     [rsi+14h], eax
0x14000dc4d  jmp     loc_14000DBBE
0x14000dc52  cmp     eax, 117h
0x14000dc57  jnz     loc_14000DBBC
0x14000dc5d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000dc61  shr     eax, 7
0x14000dc64  and     eax, ebx
0x14000dc66  mov     [rsi+10h], eax
0x14000dc69  jmp     loc_14000DBBE
```
