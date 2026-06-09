# wil_QueryFeatureState

- ea: `0x1800098ac`
- end: `0x180009a12`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x180004e10`

## callees

- `0x1800098ac`
- `0x18000c560`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009948`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009948`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009931`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009931`

## string_xrefs

- `0x18000992a`: `ntdll.dll`
- `0x18000993e`: `RtlQueryFeatureConfiguration`

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
0x1800098ac  mov     [rsp+arg_10], rbx
0x1800098b1  mov     [rsp+arg_18], rbp
0x1800098b6  push    rsi
0x1800098b7  push    rdi
0x1800098b8  push    r14
0x1800098ba  sub     rsp, 50h
0x1800098be  mov     rax, cs:__security_cookie
0x1800098c5  xor     rax, rsp
0x1800098c8  mov     [rsp+68h+var_20], rax
0x1800098cd  mov     rdi, [rsp+68h+arg_20]
0x1800098d5  mov     r14d, edx
0x1800098d8  mov     rax, [rsp+68h+arg_28]
0x1800098e0  mov     rsi, rcx
0x1800098e3  test    rdi, rdi
0x1800098e6  jz      short loc_1800098EE
0x1800098e8  mov     dword ptr [rdi], 0
0x1800098ee  xor     ebp, ebp
0x1800098f0  mov     [rsp+68h+var_38], 0
0x1800098f9  test    r8d, r8d
0x1800098fc  mov     ebx, 1
0x180009901  mov     [rax], ebx
0x180009903  setz    bpl
0x180009907  xor     eax, eax
0x180009909  mov     [rsp+68h+var_30], rax
0x18000990e  mov     [rsp+68h+var_28], eax
0x180009912  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x180009919  test    rax, rax
0x18000991c  jnz     short loc_180009999
0x18000991e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009925  test    rax, rax
0x180009928  jnz     short loc_18000993E
0x18000992a  lea     rcx, ModuleName; "ntdll.dll"
0x180009931  call    cs:__imp_GetModuleHandleW
0x180009937  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000993e  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x180009945  mov     rcx, rax; hModule
0x180009948  call    cs:__imp_GetProcAddress
0x18000994e  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x180009955  test    rax, rax
0x180009958  jnz     short loc_180009999
0x18000995a  mov     r8d, 0C0000139h
0x180009960  xor     ebx, ebx
0x180009962  test    rdi, rdi
0x180009965  jz      short loc_180009975
0x180009967  xor     ecx, ecx
0x180009969  cmp     r8d, 80000022h
0x180009970  setnz   cl
0x180009973  mov     [rdi], ecx
0x180009975  mov     eax, ebx
0x180009977  mov     rcx, [rsp+68h+var_20]
0x18000997c  xor     rcx, rsp; StackCookie
0x18000997f  call    __security_check_cookie
0x180009984  lea     r11, [rsp+68h+var_18]
0x180009989  mov     rbx, [r11+30h]
0x18000998d  mov     rbp, [r11+38h]
0x180009991  mov     rsp, r11
0x180009994  pop     r14
0x180009996  pop     rdi
0x180009997  pop     rsi
0x180009998  retn
0x180009999  lea     r9, [rsp+68h+var_30]
0x18000999e  mov     edx, ebp
0x1800099a0  lea     r8, [rsp+68h+var_38]
0x1800099a5  mov     ecx, r14d
0x1800099a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800099ad  mov     r8d, eax
0x1800099b0  test    eax, eax
0x1800099b2  jnz     short loc_1800099F6
0x1800099b4  mov     edx, dword ptr [rsp+68h+var_30+4]
0x1800099b8  mov     ecx, edx
0x1800099ba  mov     eax, [rsp+68h+var_28]
0x1800099be  mov     [rsi+0Ch], eax
0x1800099c1  mov     eax, edx
0x1800099c3  shr     eax, 0Eh
0x1800099c6  shr     ecx, 4
0x1800099c9  and     eax, 3
0x1800099cc  and     ecx, 3
0x1800099cf  mov     [rsi+8], eax
0x1800099d2  mov     [rsi], ecx
0x1800099d4  mov     eax, edx
0x1800099d6  mov     ecx, edx
0x1800099d8  shr     eax, 6
0x1800099db  shr     ecx, 8
0x1800099de  and     eax, ebx
0x1800099e0  and     cl, 3Fh
0x1800099e3  shr     edx, 7
0x1800099e6  and     edx, ebx
0x1800099e8  mov     [rsi+4], cl
0x1800099eb  mov     [rsi+10h], edx
0x1800099ee  mov     [rsi+14h], eax
0x1800099f1  jmp     loc_180009962
0x1800099f6  cmp     eax, 117h
0x1800099fb  jnz     loc_180009960
0x180009a01  mov     eax, dword ptr [rsp+68h+var_30+4]
0x180009a05  shr     eax, 7
0x180009a08  and     eax, ebx
0x180009a0a  mov     [rsi+10h], eax
0x180009a0d  jmp     loc_180009962
```
