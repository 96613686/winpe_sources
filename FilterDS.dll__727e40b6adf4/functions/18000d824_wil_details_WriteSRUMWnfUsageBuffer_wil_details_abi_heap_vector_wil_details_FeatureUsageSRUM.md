# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000d824`
- end: `0x18000da5c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180007570`

## callees

- `0x18000d824`
- `0x18000da64`
- `0x180021822`
- `0x180021850`
- `0x180021910`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d8c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d8c4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d8ad`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d8ad`

## string_xrefs

- `0x18000d8a6`: `ntdll.dll`

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
      ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
0x18000d824  push    rbp
0x18000d826  push    rbx
0x18000d827  push    rsi
0x18000d828  push    rdi
0x18000d829  push    r14
0x18000d82b  push    r15
0x18000d82d  lea     rbp, [rsp-0F68h]
0x18000d835  mov     eax, 1068h
0x18000d83a  call    _alloca_probe
0x18000d83f  sub     rsp, rax
0x18000d842  mov     rax, cs:__security_cookie
0x18000d849  xor     rax, rsp
0x18000d84c  mov     [rbp+0F90h+var_40], rax
0x18000d853  mov     rax, [rcx+8]
0x18000d857  xor     ebx, ebx
0x18000d859  sub     rax, [rcx]
0x18000d85c  xor     esi, esi
0x18000d85e  mov     r14, rcx
0x18000d861  cmp     rax, 0Ch
0x18000d865  jb      loc_18000DA28
0x18000d86b  xor     r15d, r15d
0x18000d86e  xor     edx, edx; Val
0x18000d870  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000d875  mov     r8d, 1000h; Size
0x18000d87b  call    memset_0
0x18000d880  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000d888  mov     [rsp+1090h+var_1050], 1000h
0x18000d890  mov     [rsp+1090h+var_104C], 0
0x18000d898  jnz     short loc_18000D8E2
0x18000d89a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d8a1  test    rax, rax
0x18000d8a4  jnz     short loc_18000D8BA
0x18000d8a6  lea     rcx, ModuleName; "ntdll.dll"
0x18000d8ad  call    cs:__imp_GetModuleHandleW
0x18000d8b3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d8ba  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000d8c1  mov     rcx, rax; hModule
0x18000d8c4  call    cs:__imp_GetProcAddress
0x18000d8ca  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000d8d1  test    rax, rax
0x18000d8d4  jnz     short loc_18000D8E2
0x18000d8d6  mov     edi, 0C0000139h
0x18000d8db  mov     ebx, edi
0x18000d8dd  jmp     loc_18000DA0F
0x18000d8e2  lea     rax, [rsp+1090h+var_1050]
0x18000d8e7  xor     r8d, r8d
0x18000d8ea  mov     [rsp+1090h+var_1068], rax
0x18000d8ef  lea     r9, [rsp+1090h+var_104C]
0x18000d8f4  lea     rax, [rsp+1090h+var_1040]
0x18000d8f9  xor     edx, edx
0x18000d8fb  mov     [rsp+1090h+var_1070], rax
0x18000d900  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d907  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000d90e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d913  mov     ebx, eax
0x18000d915  mov     edi, eax
0x18000d917  test    eax, eax
0x18000d919  jnz     loc_18000DA0F
0x18000d91f  mov     r9d, [rsp+1090h+var_1050]
0x18000d924  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000d92e  mov     rax, r11
0x18000d931  mul     r9
0x18000d934  shr     rdx, 3
0x18000d938  lea     rcx, [rdx+rdx*2]
0x18000d93c  shl     rcx, 2
0x18000d940  cmp     r9, rcx
0x18000d943  jz      short loc_18000D94D
0x18000d945  xor     r9d, r9d
0x18000d948  mov     [rsp+1090h+var_1050], r9d
0x18000d94d  mov     r8, [r14]
0x18000d950  mov     rax, r11
0x18000d953  mov     ecx, r9d
0x18000d956  mul     rcx
0x18000d959  mov     rcx, [r14+8]
0x18000d95d  mov     rax, r11
0x18000d960  mov     r10, rdx
0x18000d963  sub     rcx, r8
0x18000d966  mul     rcx
0x18000d969  shr     r10, 3
0x18000d96d  shr     rdx, 3
0x18000d971  lea     rax, [rdx+rdx*2]
0x18000d975  lea     rsi, [r8+rax*4]
0x18000d979  jmp     short loc_18000D9E4
0x18000d97b  mov     eax, r10d
0x18000d97e  lea     rcx, [rax+rax*2]
0x18000d982  lea     rdx, [rdx+rcx*4]
0x18000d986  lea     rax, [rsp+1090h+var_1040]
0x18000d98b  cmp     rax, rdx
0x18000d98e  jz      short loc_18000D9B5
0x18000d990  mov     r11d, [r8]
0x18000d993  lea     rcx, [rsp+1090h+var_1040]
0x18000d998  cmp     [rcx], r11d
0x18000d99b  jnz     short loc_18000D9AC
0x18000d99d  movzx   eax, word ptr [r8+4]
0x18000d9a2  cmp     [rcx+4], ax
0x18000d9a6  jz      loc_18000DA4E
0x18000d9ac  add     rcx, 0Ch
0x18000d9b0  cmp     rcx, rdx
0x18000d9b3  jnz     short loc_18000D998
0x18000d9b5  mov     eax, r9d
0x18000d9b8  add     rax, 0Ch
0x18000d9bc  cmp     rax, 1000h
0x18000d9c2  ja      short loc_18000D9E0
0x18000d9c4  movsd   xmm0, qword ptr [r8]
0x18000d9c9  add     r9d, 0Ch
0x18000d9cd  movsd   qword ptr [rdx], xmm0
0x18000d9d1  inc     r10d
0x18000d9d4  mov     eax, [r8+8]
0x18000d9d8  mov     [rdx+8], eax
0x18000d9db  mov     [rsp+1090h+var_1050], r9d
0x18000d9e0  add     r8, 0Ch
0x18000d9e4  lea     rdx, [rsp+1090h+var_1040]
0x18000d9e9  cmp     r8, rsi
0x18000d9ec  jnz     short loc_18000D97B
0x18000d9ee  mov     eax, [rsp+1090h+var_104C]
0x18000d9f2  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d9f9  mov     [rsp+1090h+var_1060], 1
0x18000da01  mov     r8d, r9d
0x18000da04  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000da08  call    wil_details_NtUpdateWnfStateData
0x18000da0d  mov     esi, eax
0x18000da0f  cmp     esi, 0C0000001h
0x18000da15  jnz     short loc_18000DA28
0x18000da17  inc     r15d
0x18000da1a  cmp     r15d, 64h ; 'd'
0x18000da1e  jge     short loc_18000DA28
0x18000da20  test    edi, edi
0x18000da22  jz      loc_18000D86E
0x18000da28  test    ebx, ebx
0x18000da2a  cmovz   ebx, esi
0x18000da2d  mov     eax, ebx
0x18000da2f  mov     rcx, [rbp+0F90h+var_40]
0x18000da36  xor     rcx, rsp; StackCookie
0x18000da39  call    __security_check_cookie
0x18000da3e  add     rsp, 1068h
0x18000da45  pop     r15
0x18000da47  pop     r14
0x18000da49  pop     rdi
0x18000da4a  pop     rsi
0x18000da4b  pop     rbx
0x18000da4c  pop     rbp
0x18000da4d  retn
0x18000da4e  mov     eax, [r8+8]
0x18000da52  add     [rcx+8], eax
0x18000da55  mov     r9d, [rsp+1090h+var_1050]
0x18000da5a  jmp     short loc_18000D9E0
```
