# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000c898`
- end: `0x14000cad0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1400077c0`

## callees

- `0x1400015d0`
- `0x14000202c`
- `0x14000c898`
- `0x14000cb68`
- `0x140012180`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000c921`
- `KERNEL32!GetModuleHandleW` at `0x14000c921`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c938`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000c938`

## string_xrefs

- `0x14000c91a`: `ntdll.dll`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int v1; // ebx
  unsigned int updated; // esi
  int v4; // r15d
  HMODULE ModuleHandleW; // rax
  int v6; // edi
  unsigned int v7; // r9d
  __int64 v8; // r8
  int v9; // r10d
  unsigned __int64 v10; // rsi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h]
  _DWORD v15[3]; // [rsp+44h] [rbp-BCh] BYREF
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
        v1 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, _DWORD *))g_wil_details_pfnNtQueryWnfStateData)(
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
              if ( (unsigned __int64)v7 + 12 <= 0x1000 )
              {
                v7 += 12;
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
                      (unsigned int)&__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                      (unsigned int)v16,
                      v7,
                      v7,
                      (unsigned int)v16,
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
0x14000c898  push    rbp
0x14000c89a  push    rbx
0x14000c89b  push    rsi
0x14000c89c  push    rdi
0x14000c89d  push    r14
0x14000c89f  push    r15
0x14000c8a1  lea     rbp, [rsp-0F68h]
0x14000c8a9  mov     eax, 1068h
0x14000c8ae  call    _alloca_probe
0x14000c8b3  sub     rsp, rax
0x14000c8b6  mov     rax, cs:__security_cookie
0x14000c8bd  xor     rax, rsp
0x14000c8c0  mov     [rbp+0F90h+var_40], rax
0x14000c8c7  mov     rax, [rcx+8]
0x14000c8cb  xor     ebx, ebx
0x14000c8cd  sub     rax, [rcx]
0x14000c8d0  xor     esi, esi
0x14000c8d2  mov     r14, rcx
0x14000c8d5  cmp     rax, 0Ch
0x14000c8d9  jb      loc_14000CA9C
0x14000c8df  xor     r15d, r15d
0x14000c8e2  xor     edx, edx; Val
0x14000c8e4  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000c8e9  mov     r8d, 1000h; Size
0x14000c8ef  call    memset_0
0x14000c8f4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000c8fc  mov     [rsp+1090h+var_1050], 1000h
0x14000c904  mov     [rsp+1090h+var_104C], 0
0x14000c90c  jnz     short loc_14000C956
0x14000c90e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c915  test    rax, rax
0x14000c918  jnz     short loc_14000C92E
0x14000c91a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000c921  call    cs:__imp_GetModuleHandleW
0x14000c927  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000c92e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000c935  mov     rcx, rax; hModule
0x14000c938  call    cs:__imp_GetProcAddress
0x14000c93e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000c945  test    rax, rax
0x14000c948  jnz     short loc_14000C956
0x14000c94a  mov     edi, 0C0000139h
0x14000c94f  mov     ebx, edi
0x14000c951  jmp     loc_14000CA83
0x14000c956  lea     rax, [rsp+1090h+var_1050]
0x14000c95b  xor     r8d, r8d
0x14000c95e  mov     [rsp+1090h+var_1068], rax
0x14000c963  lea     r9, [rsp+1090h+var_104C]
0x14000c968  lea     rax, [rsp+1090h+var_1040]
0x14000c96d  xor     edx, edx
0x14000c96f  mov     [rsp+1090h+var_1070], rax
0x14000c974  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000c97b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000c982  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000c987  mov     ebx, eax
0x14000c989  mov     edi, eax
0x14000c98b  test    eax, eax
0x14000c98d  jnz     loc_14000CA83
0x14000c993  mov     r9d, [rsp+1090h+var_1050]
0x14000c998  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000c9a2  mov     rax, r11
0x14000c9a5  mul     r9
0x14000c9a8  shr     rdx, 3
0x14000c9ac  lea     rcx, [rdx+rdx*2]
0x14000c9b0  shl     rcx, 2
0x14000c9b4  cmp     r9, rcx
0x14000c9b7  jz      short loc_14000C9C1
0x14000c9b9  xor     r9d, r9d
0x14000c9bc  mov     [rsp+1090h+var_1050], r9d
0x14000c9c1  mov     r8, [r14]
0x14000c9c4  mov     rax, r11
0x14000c9c7  mov     ecx, r9d
0x14000c9ca  mul     rcx
0x14000c9cd  mov     rcx, [r14+8]
0x14000c9d1  mov     rax, r11
0x14000c9d4  mov     r10, rdx
0x14000c9d7  sub     rcx, r8
0x14000c9da  mul     rcx
0x14000c9dd  shr     r10, 3
0x14000c9e1  shr     rdx, 3
0x14000c9e5  lea     rax, [rdx+rdx*2]
0x14000c9e9  lea     rsi, [r8+rax*4]
0x14000c9ed  jmp     short loc_14000CA58
0x14000c9ef  mov     eax, r10d
0x14000c9f2  lea     rcx, [rax+rax*2]
0x14000c9f6  lea     rdx, [rdx+rcx*4]
0x14000c9fa  lea     rax, [rsp+1090h+var_1040]
0x14000c9ff  cmp     rax, rdx
0x14000ca02  jz      short loc_14000CA29
0x14000ca04  mov     r11d, [r8]
0x14000ca07  lea     rcx, [rsp+1090h+var_1040]
0x14000ca0c  cmp     [rcx], r11d
0x14000ca0f  jnz     short loc_14000CA20
0x14000ca11  movzx   eax, word ptr [r8+4]
0x14000ca16  cmp     [rcx+4], ax
0x14000ca1a  jz      loc_14000CAC2
0x14000ca20  add     rcx, 0Ch
0x14000ca24  cmp     rcx, rdx
0x14000ca27  jnz     short loc_14000CA0C
0x14000ca29  mov     eax, r9d
0x14000ca2c  add     rax, 0Ch
0x14000ca30  cmp     rax, 1000h
0x14000ca36  ja      short loc_14000CA54
0x14000ca38  movsd   xmm0, qword ptr [r8]
0x14000ca3d  add     r9d, 0Ch
0x14000ca41  movsd   qword ptr [rdx], xmm0
0x14000ca45  inc     r10d
0x14000ca48  mov     eax, [r8+8]
0x14000ca4c  mov     [rdx+8], eax
0x14000ca4f  mov     [rsp+1090h+var_1050], r9d
0x14000ca54  add     r8, 0Ch
0x14000ca58  lea     rdx, [rsp+1090h+var_1040]
0x14000ca5d  cmp     r8, rsi
0x14000ca60  jnz     short loc_14000C9EF
0x14000ca62  mov     eax, [rsp+1090h+var_104C]
0x14000ca66  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000ca6d  mov     [rsp+1090h+var_1060], 1
0x14000ca75  mov     r8d, r9d
0x14000ca78  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000ca7c  call    wil_details_NtUpdateWnfStateData
0x14000ca81  mov     esi, eax
0x14000ca83  cmp     esi, 0C0000001h
0x14000ca89  jnz     short loc_14000CA9C
0x14000ca8b  inc     r15d
0x14000ca8e  cmp     r15d, 64h ; 'd'
0x14000ca92  jge     short loc_14000CA9C
0x14000ca94  test    edi, edi
0x14000ca96  jz      loc_14000C8E2
0x14000ca9c  test    ebx, ebx
0x14000ca9e  cmovz   ebx, esi
0x14000caa1  mov     eax, ebx
0x14000caa3  mov     rcx, [rbp+0F90h+var_40]
0x14000caaa  xor     rcx, rsp; StackCookie
0x14000caad  call    __security_check_cookie
0x14000cab2  add     rsp, 1068h
0x14000cab9  pop     r15
0x14000cabb  pop     r14
0x14000cabd  pop     rdi
0x14000cabe  pop     rsi
0x14000cabf  pop     rbx
0x14000cac0  pop     rbp
0x14000cac1  retn
0x14000cac2  mov     eax, [r8+8]
0x14000cac6  add     [rcx+8], eax
0x14000cac9  mov     r9d, [rsp+1090h+var_1050]
0x14000cace  jmp     short loc_14000CA54
```
