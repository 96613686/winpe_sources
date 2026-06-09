# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000c8e8`
- end: `0x18000cb20`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180003cc0`

## callees

- `0x180002590`
- `0x180002f98`
- `0x18000c8e8`
- `0x18000d348`
- `0x1800300f0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c971`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c971`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c988`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c988`

## string_xrefs

- `0x18000c96a`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int v1; // ebx
  unsigned int updated; // esi
  int v4; // r15d
  HMODULE ModuleHandleW; // rax
  int v6; // edi
  __int64 v7; // r9
  __int64 v8; // r8
  int v9; // r10d
  unsigned __int64 v10; // rsi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h]
  int v15[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v16[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v1 = 0;
  updated = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v16, 0, sizeof(v16));
      v15[0] = 0;
      if ( g_wil_details_pfnNtQueryWnfStateData )
        goto LABEL_8;
      ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
      if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
      {
        ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
        `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
      }
      g_wil_details_pfnNtQueryWnfStateData = (__int64)GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
      if ( g_wil_details_pfnNtQueryWnfStateData )
      {
LABEL_8:
        v1 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, int *))g_wil_details_pfnNtQueryWnfStateData)(
               &__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
               0,
               0,
               v15);
        v6 = v1;
        if ( !v1 )
        {
          v7 = 0;
          v14 = 0;
          v8 = *a1;
          v9 = 0;
          v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
          while ( v8 != v10 )
          {
            v11 = &v16[3 * v9];
            if ( v16 == v11 )
            {
LABEL_15:
              if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
              {
                v7 = (unsigned int)(v7 + 12);
                *(_QWORD *)v11 = *(_QWORD *)v8;
                ++v9;
                v11[2] = *(_DWORD *)(v8 + 8);
                v14 = v7;
              }
            }
            else
            {
              v12 = v16;
              while ( *v12 != *(_DWORD *)v8 || *((_WORD *)v12 + 2) != *(_WORD *)(v8 + 4) )
              {
                v12 += 3;
                if ( v12 == v11 )
                  goto LABEL_15;
              }
              v12[2] += *(_DWORD *)(v8 + 8);
              v7 = v14;
            }
            v8 += 12;
          }
          updated = wil_details_NtUpdateWnfStateData(
                      (__int64)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                      (__int64)v16,
                      v7,
                      v7,
                      (int)v16,
                      v15[0],
                      1);
        }
      }
      else
      {
        v6 = -1073741511;
        v1 = -1073741511;
      }
      if ( updated != -1073741823 )
        break;
      if ( ++v4 >= 100 )
        break;
    }
    while ( !v6 );
  }
  if ( !v1 )
    return updated;
  return v1;
}

```

## disassembly

```asm
0x18000c8e8  push    rbp
0x18000c8ea  push    rbx
0x18000c8eb  push    rsi
0x18000c8ec  push    rdi
0x18000c8ed  push    r14
0x18000c8ef  push    r15
0x18000c8f1  lea     rbp, [rsp-0F68h]
0x18000c8f9  mov     eax, 1068h
0x18000c8fe  call    _alloca_probe
0x18000c903  sub     rsp, rax
0x18000c906  mov     rax, cs:__security_cookie
0x18000c90d  xor     rax, rsp
0x18000c910  mov     [rbp+0F90h+var_40], rax
0x18000c917  mov     rax, [rcx+8]
0x18000c91b  xor     ebx, ebx
0x18000c91d  sub     rax, [rcx]
0x18000c920  xor     esi, esi
0x18000c922  mov     r14, rcx
0x18000c925  cmp     rax, 0Ch
0x18000c929  jb      loc_18000CAEC
0x18000c92f  xor     r15d, r15d
0x18000c932  xor     edx, edx; Val
0x18000c934  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000c939  mov     r8d, 1000h; Size
0x18000c93f  call    memset_0
0x18000c944  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000c94c  mov     [rsp+1090h+var_1050], 1000h
0x18000c954  mov     [rsp+1090h+var_104C], 0
0x18000c95c  jnz     short loc_18000C9A6
0x18000c95e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c965  test    rax, rax
0x18000c968  jnz     short loc_18000C97E
0x18000c96a  lea     rcx, ModuleName; "ntdll.dll"
0x18000c971  call    cs:__imp_GetModuleHandleW
0x18000c977  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c97e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000c985  mov     rcx, rax; hModule
0x18000c988  call    cs:__imp_GetProcAddress
0x18000c98e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000c995  test    rax, rax
0x18000c998  jnz     short loc_18000C9A6
0x18000c99a  mov     edi, 0C0000139h
0x18000c99f  mov     ebx, edi
0x18000c9a1  jmp     loc_18000CAD3
0x18000c9a6  lea     rax, [rsp+1090h+var_1050]
0x18000c9ab  xor     r8d, r8d
0x18000c9ae  mov     [rsp+1090h+var_1068], rax
0x18000c9b3  lea     r9, [rsp+1090h+var_104C]
0x18000c9b8  lea     rax, [rsp+1090h+var_1040]
0x18000c9bd  xor     edx, edx
0x18000c9bf  mov     [rsp+1090h+var_1070], rax
0x18000c9c4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000c9cb  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000c9d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c9d7  mov     ebx, eax
0x18000c9d9  mov     edi, eax
0x18000c9db  test    eax, eax
0x18000c9dd  jnz     loc_18000CAD3
0x18000c9e3  mov     r9d, [rsp+1090h+var_1050]
0x18000c9e8  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000c9f2  mov     rax, r11
0x18000c9f5  mul     r9
0x18000c9f8  shr     rdx, 3
0x18000c9fc  lea     rcx, [rdx+rdx*2]
0x18000ca00  shl     rcx, 2
0x18000ca04  cmp     r9, rcx
0x18000ca07  jz      short loc_18000CA11
0x18000ca09  xor     r9d, r9d
0x18000ca0c  mov     [rsp+1090h+var_1050], r9d
0x18000ca11  mov     r8, [r14]
0x18000ca14  mov     rax, r11
0x18000ca17  mov     ecx, r9d
0x18000ca1a  mul     rcx
0x18000ca1d  mov     rcx, [r14+8]
0x18000ca21  mov     rax, r11
0x18000ca24  mov     r10, rdx
0x18000ca27  sub     rcx, r8
0x18000ca2a  mul     rcx
0x18000ca2d  shr     r10, 3
0x18000ca31  shr     rdx, 3
0x18000ca35  lea     rax, [rdx+rdx*2]
0x18000ca39  lea     rsi, [r8+rax*4]
0x18000ca3d  jmp     short loc_18000CAA8
0x18000ca3f  mov     eax, r10d
0x18000ca42  lea     rcx, [rax+rax*2]
0x18000ca46  lea     rdx, [rdx+rcx*4]
0x18000ca4a  lea     rax, [rsp+1090h+var_1040]
0x18000ca4f  cmp     rax, rdx
0x18000ca52  jz      short loc_18000CA79
0x18000ca54  mov     r11d, [r8]
0x18000ca57  lea     rcx, [rsp+1090h+var_1040]
0x18000ca5c  cmp     [rcx], r11d
0x18000ca5f  jnz     short loc_18000CA70
0x18000ca61  movzx   eax, word ptr [r8+4]
0x18000ca66  cmp     [rcx+4], ax
0x18000ca6a  jz      loc_18000CB12
0x18000ca70  add     rcx, 0Ch
0x18000ca74  cmp     rcx, rdx
0x18000ca77  jnz     short loc_18000CA5C
0x18000ca79  mov     eax, r9d
0x18000ca7c  add     rax, 0Ch
0x18000ca80  cmp     rax, 1000h
0x18000ca86  ja      short loc_18000CAA4
0x18000ca88  movsd   xmm0, qword ptr [r8]
0x18000ca8d  add     r9d, 0Ch
0x18000ca91  movsd   qword ptr [rdx], xmm0
0x18000ca95  inc     r10d
0x18000ca98  mov     eax, [r8+8]
0x18000ca9c  mov     [rdx+8], eax
0x18000ca9f  mov     [rsp+1090h+var_1050], r9d
0x18000caa4  add     r8, 0Ch
0x18000caa8  lea     rdx, [rsp+1090h+var_1040]
0x18000caad  cmp     r8, rsi
0x18000cab0  jnz     short loc_18000CA3F
0x18000cab2  mov     eax, [rsp+1090h+var_104C]
0x18000cab6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cabd  mov     [rsp+1090h+var_1060], 1
0x18000cac5  mov     r8d, r9d
0x18000cac8  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000cacc  call    wil_details_NtUpdateWnfStateData
0x18000cad1  mov     esi, eax
0x18000cad3  cmp     esi, 0C0000001h
0x18000cad9  jnz     short loc_18000CAEC
0x18000cadb  inc     r15d
0x18000cade  cmp     r15d, 64h ; 'd'
0x18000cae2  jge     short loc_18000CAEC
0x18000cae4  test    edi, edi
0x18000cae6  jz      loc_18000C932
0x18000caec  test    ebx, ebx
0x18000caee  cmovz   ebx, esi
0x18000caf1  mov     eax, ebx
0x18000caf3  mov     rcx, [rbp+0F90h+var_40]
0x18000cafa  xor     rcx, rsp; StackCookie
0x18000cafd  call    __security_check_cookie
0x18000cb02  add     rsp, 1068h
0x18000cb09  pop     r15
0x18000cb0b  pop     r14
0x18000cb0d  pop     rdi
0x18000cb0e  pop     rsi
0x18000cb0f  pop     rbx
0x18000cb10  pop     rbp
0x18000cb11  retn
0x18000cb12  mov     eax, [r8+8]
0x18000cb16  add     [rcx+8], eax
0x18000cb19  mov     r9d, [rsp+1090h+var_1050]
0x18000cb1e  jmp     short loc_18000CAA4
```
