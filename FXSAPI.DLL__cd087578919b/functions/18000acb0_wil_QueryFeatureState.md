# wil_QueryFeatureState

- ea: `0x18000acb0`
- end: `0x18000ae27`
- name: `wil_QueryFeatureState`
- size: `375`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x18003bdb8`

## callees

- `0x18000acb0`
- `0x18003d510`
- `0x18003e010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000ad56`
- `KERNEL32!GetProcAddress` at `0x18000ad56`
- `KERNEL32!GetModuleHandleW` at `0x18000ad39`
- `KERNEL32!GetModuleHandleW` at `0x18000ad39`

## string_xrefs

- `0x18000ad32`: `ntdll.dll`
- `0x18000ad4c`: `RtlQueryFeatureConfiguration`

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
0x18000acb0  mov     [rsp+arg_10], rbx
0x18000acb5  mov     [rsp+arg_18], rbp
0x18000acba  push    rsi
0x18000acbb  push    rdi
0x18000acbc  push    r14
0x18000acbe  sub     rsp, 50h
0x18000acc2  mov     rax, cs:__security_cookie
0x18000acc9  xor     rax, rsp
0x18000accc  mov     [rsp+68h+var_20], rax
0x18000acd1  mov     rdi, [rsp+68h+arg_20]
0x18000acd9  mov     r14d, edx
0x18000acdc  mov     rax, [rsp+68h+arg_28]
0x18000ace4  mov     rsi, rcx
0x18000ace7  test    rdi, rdi
0x18000acea  jz      short loc_18000ACF2
0x18000acec  mov     dword ptr [rdi], 0
0x18000acf2  xor     ebp, ebp
0x18000acf4  mov     [rsp+68h+var_38], 0
0x18000acfd  test    r8d, r8d
0x18000ad00  mov     ebx, 1
0x18000ad05  mov     [rax], ebx
0x18000ad07  setz    bpl
0x18000ad0b  xor     eax, eax
0x18000ad0d  mov     [rsp+68h+var_30], rax
0x18000ad12  mov     [rsp+68h+var_28], eax
0x18000ad16  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000ad1d  test    rax, rax
0x18000ad20  jnz     loc_18000ADAE
0x18000ad26  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ad2d  test    rax, rax
0x18000ad30  jnz     short loc_18000AD4C
0x18000ad32  lea     rcx, ModuleName; "ntdll.dll"
0x18000ad39  call    cs:__imp_GetModuleHandleW
0x18000ad40  nop     dword ptr [rax+rax+00h]
0x18000ad45  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ad4c  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000ad53  mov     rcx, rax; hModule
0x18000ad56  call    cs:__imp_GetProcAddress
0x18000ad5d  nop     dword ptr [rax+rax+00h]
0x18000ad62  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000ad69  test    rax, rax
0x18000ad6c  jnz     short loc_18000ADAE
0x18000ad6e  mov     r8d, 0C0000139h
0x18000ad74  xor     ebx, ebx
0x18000ad76  test    rdi, rdi
0x18000ad79  jz      short loc_18000AD89
0x18000ad7b  xor     ecx, ecx
0x18000ad7d  cmp     r8d, 80000022h
0x18000ad84  setnz   cl
0x18000ad87  mov     [rdi], ecx
0x18000ad89  mov     eax, ebx
0x18000ad8b  mov     rcx, [rsp+68h+var_20]
0x18000ad90  xor     rcx, rsp; StackCookie
0x18000ad93  call    __security_check_cookie
0x18000ad98  lea     r11, [rsp+68h+var_18]
0x18000ad9d  mov     rbx, [r11+30h]
0x18000ada1  mov     rbp, [r11+38h]
0x18000ada5  mov     rsp, r11
0x18000ada8  pop     r14
0x18000adaa  pop     rdi
0x18000adab  pop     rsi
0x18000adac  retn
0x18000adae  lea     r9, [rsp+68h+var_30]
0x18000adb3  mov     edx, ebp
0x18000adb5  lea     r8, [rsp+68h+var_38]
0x18000adba  mov     ecx, r14d
0x18000adbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000adc2  mov     r8d, eax
0x18000adc5  test    eax, eax
0x18000adc7  jnz     short loc_18000AE0B
0x18000adc9  mov     edx, dword ptr [rsp+68h+var_30+4]
0x18000adcd  mov     ecx, edx
0x18000adcf  mov     eax, [rsp+68h+var_28]
0x18000add3  mov     [rsi+0Ch], eax
0x18000add6  mov     eax, edx
0x18000add8  shr     eax, 0Eh
0x18000addb  shr     ecx, 4
0x18000adde  and     eax, 3
0x18000ade1  and     ecx, 3
0x18000ade4  mov     [rsi+8], eax
0x18000ade7  mov     [rsi], ecx
0x18000ade9  mov     eax, edx
0x18000adeb  mov     ecx, edx
0x18000aded  shr     eax, 6
0x18000adf0  shr     ecx, 8
0x18000adf3  and     eax, ebx
0x18000adf5  and     cl, 3Fh
0x18000adf8  shr     edx, 7
0x18000adfb  and     edx, ebx
0x18000adfd  mov     [rsi+4], cl
0x18000ae00  mov     [rsi+10h], edx
0x18000ae03  mov     [rsi+14h], eax
0x18000ae06  jmp     loc_18000AD76
0x18000ae0b  cmp     eax, 117h
0x18000ae10  jnz     loc_18000AD74
0x18000ae16  mov     eax, dword ptr [rsp+68h+var_30+4]
0x18000ae1a  shr     eax, 7
0x18000ae1d  and     eax, ebx
0x18000ae1f  mov     [rsi+10h], eax
0x18000ae22  jmp     loc_18000AD76
```
