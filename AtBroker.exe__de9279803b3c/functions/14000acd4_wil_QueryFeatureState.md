# wil_QueryFeatureState

- ea: `0x14000acd4`
- end: `0x14000ae3a`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x1400068c8`

## callees

- `0x14000acd4`
- `0x140015b00`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000ad70`
- `KERNEL32!GetProcAddress` at `0x14000ad70`
- `KERNEL32!GetModuleHandleW` at `0x14000ad59`
- `KERNEL32!GetModuleHandleW` at `0x14000ad59`

## string_xrefs

- `0x14000ad52`: `ntdll.dll`
- `0x14000ad66`: `RtlQueryFeatureConfiguration`

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
0x14000acd4  mov     [rsp+arg_10], rbx
0x14000acd9  mov     [rsp+arg_18], rbp
0x14000acde  push    rsi
0x14000acdf  push    rdi
0x14000ace0  push    r14
0x14000ace2  sub     rsp, 50h
0x14000ace6  mov     rax, cs:__security_cookie
0x14000aced  xor     rax, rsp
0x14000acf0  mov     [rsp+68h+var_20], rax
0x14000acf5  mov     rdi, [rsp+68h+arg_20]
0x14000acfd  mov     r14d, edx
0x14000ad00  mov     rax, [rsp+68h+arg_28]
0x14000ad08  mov     rsi, rcx
0x14000ad0b  test    rdi, rdi
0x14000ad0e  jz      short loc_14000AD16
0x14000ad10  mov     dword ptr [rdi], 0
0x14000ad16  xor     ebp, ebp
0x14000ad18  mov     [rsp+68h+var_38], 0
0x14000ad21  test    r8d, r8d
0x14000ad24  mov     ebx, 1
0x14000ad29  mov     [rax], ebx
0x14000ad2b  setz    bpl
0x14000ad2f  xor     eax, eax
0x14000ad31  mov     [rsp+68h+var_30], rax
0x14000ad36  mov     [rsp+68h+var_28], eax
0x14000ad3a  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000ad41  test    rax, rax
0x14000ad44  jnz     short loc_14000ADC1
0x14000ad46  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ad4d  test    rax, rax
0x14000ad50  jnz     short loc_14000AD66
0x14000ad52  lea     rcx, ModuleName; "ntdll.dll"
0x14000ad59  call    cs:__imp_GetModuleHandleW
0x14000ad5f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ad66  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000ad6d  mov     rcx, rax; hModule
0x14000ad70  call    cs:__imp_GetProcAddress
0x14000ad76  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000ad7d  test    rax, rax
0x14000ad80  jnz     short loc_14000ADC1
0x14000ad82  mov     r8d, 0C0000139h
0x14000ad88  xor     ebx, ebx
0x14000ad8a  test    rdi, rdi
0x14000ad8d  jz      short loc_14000AD9D
0x14000ad8f  xor     ecx, ecx
0x14000ad91  cmp     r8d, 80000022h
0x14000ad98  setnz   cl
0x14000ad9b  mov     [rdi], ecx
0x14000ad9d  mov     eax, ebx
0x14000ad9f  mov     rcx, [rsp+68h+var_20]
0x14000ada4  xor     rcx, rsp; StackCookie
0x14000ada7  call    __security_check_cookie
0x14000adac  lea     r11, [rsp+68h+var_18]
0x14000adb1  mov     rbx, [r11+30h]
0x14000adb5  mov     rbp, [r11+38h]
0x14000adb9  mov     rsp, r11
0x14000adbc  pop     r14
0x14000adbe  pop     rdi
0x14000adbf  pop     rsi
0x14000adc0  retn
0x14000adc1  lea     r9, [rsp+68h+var_30]
0x14000adc6  mov     edx, ebp
0x14000adc8  lea     r8, [rsp+68h+var_38]
0x14000adcd  mov     ecx, r14d
0x14000add0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000add5  mov     r8d, eax
0x14000add8  test    eax, eax
0x14000adda  jnz     short loc_14000AE1E
0x14000addc  mov     edx, dword ptr [rsp+68h+var_30+4]
0x14000ade0  mov     ecx, edx
0x14000ade2  mov     eax, [rsp+68h+var_28]
0x14000ade6  mov     [rsi+0Ch], eax
0x14000ade9  mov     eax, edx
0x14000adeb  shr     eax, 0Eh
0x14000adee  shr     ecx, 4
0x14000adf1  and     eax, 3
0x14000adf4  and     ecx, 3
0x14000adf7  mov     [rsi+8], eax
0x14000adfa  mov     [rsi], ecx
0x14000adfc  mov     eax, edx
0x14000adfe  mov     ecx, edx
0x14000ae00  shr     eax, 6
0x14000ae03  shr     ecx, 8
0x14000ae06  and     eax, ebx
0x14000ae08  and     cl, 3Fh
0x14000ae0b  shr     edx, 7
0x14000ae0e  and     edx, ebx
0x14000ae10  mov     [rsi+4], cl
0x14000ae13  mov     [rsi+10h], edx
0x14000ae16  mov     [rsi+14h], eax
0x14000ae19  jmp     loc_14000AD8A
0x14000ae1e  cmp     eax, 117h
0x14000ae23  jnz     loc_14000AD88
0x14000ae29  mov     eax, dword ptr [rsp+68h+var_30+4]
0x14000ae2d  shr     eax, 7
0x14000ae30  and     eax, ebx
0x14000ae32  mov     [rsi+10h], eax
0x14000ae35  jmp     loc_14000AD8A
```
