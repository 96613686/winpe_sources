# wil_QueryFeatureState

- ea: `0x140009118`
- end: `0x14000927e`
- name: `wil_QueryFeatureState`
- size: `358`
- prototype: `__int64 __fastcall(__int64, unsigned int, int, __int64, _DWORD *, _DWORD *)`
- caller_count: `1`
- callee_count: `3`
- tags: `registry_config, loader_planting`

## callers

- `0x140005674`

## callees

- `0x1400016f0`
- `0x140009118`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000919d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000919d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400091b4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1400091b4`

## string_xrefs

- `0x140009196`: `ntdll.dll`
- `0x1400091aa`: `RtlQueryFeatureConfiguration`

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
0x140009118  mov     [rsp+arg_10], rbx
0x14000911d  mov     [rsp+arg_18], rbp
0x140009122  push    rsi
0x140009123  push    rdi
0x140009124  push    r14
0x140009126  sub     rsp, 50h
0x14000912a  mov     rax, cs:__security_cookie
0x140009131  xor     rax, rsp
0x140009134  mov     [rsp+68h+var_20], rax
0x140009139  mov     rdi, [rsp+68h+arg_20]
0x140009141  mov     r14d, edx
0x140009144  mov     rax, [rsp+68h+arg_28]
0x14000914c  mov     rsi, rcx
0x14000914f  test    rdi, rdi
0x140009152  jz      short loc_14000915A
0x140009154  mov     dword ptr [rdi], 0
0x14000915a  xor     ebp, ebp
0x14000915c  mov     [rsp+68h+var_38], 0
0x140009165  test    r8d, r8d
0x140009168  mov     ebx, 1
0x14000916d  mov     [rax], ebx
0x14000916f  setz    bpl
0x140009173  xor     eax, eax
0x140009175  mov     [rsp+68h+var_30], rax
0x14000917a  mov     [rsp+68h+var_28], eax
0x14000917e  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x140009185  test    rax, rax
0x140009188  jnz     short loc_140009205
0x14000918a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140009191  test    rax, rax
0x140009194  jnz     short loc_1400091AA
0x140009196  lea     rcx, ModuleName; "ntdll.dll"
0x14000919d  call    cs:__imp_GetModuleHandleW
0x1400091a3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400091aa  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x1400091b1  mov     rcx, rax; hModule
0x1400091b4  call    cs:__imp_GetProcAddress
0x1400091ba  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x1400091c1  test    rax, rax
0x1400091c4  jnz     short loc_140009205
0x1400091c6  mov     r8d, 0C0000139h
0x1400091cc  xor     ebx, ebx
0x1400091ce  test    rdi, rdi
0x1400091d1  jz      short loc_1400091E1
0x1400091d3  xor     ecx, ecx
0x1400091d5  cmp     r8d, 80000022h
0x1400091dc  setnz   cl
0x1400091df  mov     [rdi], ecx
0x1400091e1  mov     eax, ebx
0x1400091e3  mov     rcx, [rsp+68h+var_20]
0x1400091e8  xor     rcx, rsp; StackCookie
0x1400091eb  call    __security_check_cookie
0x1400091f0  lea     r11, [rsp+68h+var_18]
0x1400091f5  mov     rbx, [r11+30h]
0x1400091f9  mov     rbp, [r11+38h]
0x1400091fd  mov     rsp, r11
0x140009200  pop     r14
0x140009202  pop     rdi
0x140009203  pop     rsi
0x140009204  retn
0x140009205  lea     r9, [rsp+68h+var_30]
0x14000920a  mov     edx, ebp
0x14000920c  lea     r8, [rsp+68h+var_38]
0x140009211  mov     ecx, r14d
0x140009214  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009219  mov     r8d, eax
0x14000921c  test    eax, eax
0x14000921e  jnz     short loc_140009262
0x140009220  mov     edx, dword ptr [rsp+68h+var_30+4]
0x140009224  mov     ecx, edx
0x140009226  mov     eax, [rsp+68h+var_28]
0x14000922a  mov     [rsi+0Ch], eax
0x14000922d  mov     eax, edx
0x14000922f  shr     eax, 0Eh
0x140009232  shr     ecx, 4
0x140009235  and     eax, 3
0x140009238  and     ecx, 3
0x14000923b  mov     [rsi+8], eax
0x14000923e  mov     [rsi], ecx
0x140009240  mov     eax, edx
0x140009242  mov     ecx, edx
0x140009244  shr     eax, 6
0x140009247  shr     ecx, 8
0x14000924a  and     eax, ebx
0x14000924c  and     cl, 3Fh
0x14000924f  shr     edx, 7
0x140009252  and     edx, ebx
0x140009254  mov     [rsi+4], cl
0x140009257  mov     [rsi+10h], edx
0x14000925a  mov     [rsi+14h], eax
0x14000925d  jmp     loc_1400091CE
0x140009262  cmp     eax, 117h
0x140009267  jnz     loc_1400091CC
0x14000926d  mov     eax, dword ptr [rsp+68h+var_30+4]
0x140009271  shr     eax, 7
0x140009274  and     eax, ebx
0x140009276  mov     [rsi+10h], eax
0x140009279  jmp     loc_1400091CE
```
