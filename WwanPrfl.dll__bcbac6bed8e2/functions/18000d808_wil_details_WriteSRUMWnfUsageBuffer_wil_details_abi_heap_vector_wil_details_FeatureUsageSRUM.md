# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000d808`
- end: `0x18000da40`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800024b0`

## callees

- `0x180001670`
- `0x180002034`
- `0x18000d808`
- `0x18000ebd0`
- `0x1800136a0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d8a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d8a8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d891`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d891`

## string_xrefs

- `0x18000d88a`: `ntdll.dll`

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
0x18000d808  push    rbp
0x18000d80a  push    rbx
0x18000d80b  push    rsi
0x18000d80c  push    rdi
0x18000d80d  push    r14
0x18000d80f  push    r15
0x18000d811  lea     rbp, [rsp-0F68h]
0x18000d819  mov     eax, 1068h
0x18000d81e  call    _alloca_probe
0x18000d823  sub     rsp, rax
0x18000d826  mov     rax, cs:__security_cookie
0x18000d82d  xor     rax, rsp
0x18000d830  mov     [rbp+0F90h+var_40], rax
0x18000d837  mov     rax, [rcx+8]
0x18000d83b  xor     ebx, ebx
0x18000d83d  sub     rax, [rcx]
0x18000d840  xor     esi, esi
0x18000d842  mov     r14, rcx
0x18000d845  cmp     rax, 0Ch
0x18000d849  jb      loc_18000DA0C
0x18000d84f  xor     r15d, r15d
0x18000d852  xor     edx, edx; Val
0x18000d854  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000d859  mov     r8d, 1000h; Size
0x18000d85f  call    memset_0
0x18000d864  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000d86c  mov     [rsp+1090h+var_1050], 1000h
0x18000d874  mov     [rsp+1090h+var_104C], 0
0x18000d87c  jnz     short loc_18000D8C6
0x18000d87e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d885  test    rax, rax
0x18000d888  jnz     short loc_18000D89E
0x18000d88a  lea     rcx, ModuleName; "ntdll.dll"
0x18000d891  call    cs:__imp_GetModuleHandleW
0x18000d897  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d89e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000d8a5  mov     rcx, rax; hModule
0x18000d8a8  call    cs:__imp_GetProcAddress
0x18000d8ae  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000d8b5  test    rax, rax
0x18000d8b8  jnz     short loc_18000D8C6
0x18000d8ba  mov     edi, 0C0000139h
0x18000d8bf  mov     ebx, edi
0x18000d8c1  jmp     loc_18000D9F3
0x18000d8c6  lea     rax, [rsp+1090h+var_1050]
0x18000d8cb  xor     r8d, r8d
0x18000d8ce  mov     [rsp+1090h+var_1068], rax
0x18000d8d3  lea     r9, [rsp+1090h+var_104C]
0x18000d8d8  lea     rax, [rsp+1090h+var_1040]
0x18000d8dd  xor     edx, edx
0x18000d8df  mov     [rsp+1090h+var_1070], rax
0x18000d8e4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d8eb  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000d8f2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8f7  mov     ebx, eax
0x18000d8f9  mov     edi, eax
0x18000d8fb  test    eax, eax
0x18000d8fd  jnz     loc_18000D9F3
0x18000d903  mov     r9d, [rsp+1090h+var_1050]
0x18000d908  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000d912  mov     rax, r11
0x18000d915  mul     r9
0x18000d918  shr     rdx, 3
0x18000d91c  lea     rcx, [rdx+rdx*2]
0x18000d920  shl     rcx, 2
0x18000d924  cmp     r9, rcx
0x18000d927  jz      short loc_18000D931
0x18000d929  xor     r9d, r9d
0x18000d92c  mov     [rsp+1090h+var_1050], r9d
0x18000d931  mov     r8, [r14]
0x18000d934  mov     rax, r11
0x18000d937  mov     ecx, r9d
0x18000d93a  mul     rcx
0x18000d93d  mov     rcx, [r14+8]
0x18000d941  mov     rax, r11
0x18000d944  mov     r10, rdx
0x18000d947  sub     rcx, r8
0x18000d94a  mul     rcx
0x18000d94d  shr     r10, 3
0x18000d951  shr     rdx, 3
0x18000d955  lea     rax, [rdx+rdx*2]
0x18000d959  lea     rsi, [r8+rax*4]
0x18000d95d  jmp     short loc_18000D9C8
0x18000d95f  mov     eax, r10d
0x18000d962  lea     rcx, [rax+rax*2]
0x18000d966  lea     rdx, [rdx+rcx*4]
0x18000d96a  lea     rax, [rsp+1090h+var_1040]
0x18000d96f  cmp     rax, rdx
0x18000d972  jz      short loc_18000D999
0x18000d974  mov     r11d, [r8]
0x18000d977  lea     rcx, [rsp+1090h+var_1040]
0x18000d97c  cmp     [rcx], r11d
0x18000d97f  jnz     short loc_18000D990
0x18000d981  movzx   eax, word ptr [r8+4]
0x18000d986  cmp     [rcx+4], ax
0x18000d98a  jz      loc_18000DA32
0x18000d990  add     rcx, 0Ch
0x18000d994  cmp     rcx, rdx
0x18000d997  jnz     short loc_18000D97C
0x18000d999  mov     eax, r9d
0x18000d99c  add     rax, 0Ch
0x18000d9a0  cmp     rax, 1000h
0x18000d9a6  ja      short loc_18000D9C4
0x18000d9a8  movsd   xmm0, qword ptr [r8]
0x18000d9ad  add     r9d, 0Ch
0x18000d9b1  movsd   qword ptr [rdx], xmm0
0x18000d9b5  inc     r10d
0x18000d9b8  mov     eax, [r8+8]
0x18000d9bc  mov     [rdx+8], eax
0x18000d9bf  mov     [rsp+1090h+var_1050], r9d
0x18000d9c4  add     r8, 0Ch
0x18000d9c8  lea     rdx, [rsp+1090h+var_1040]
0x18000d9cd  cmp     r8, rsi
0x18000d9d0  jnz     short loc_18000D95F
0x18000d9d2  mov     eax, [rsp+1090h+var_104C]
0x18000d9d6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d9dd  mov     [rsp+1090h+var_1060], 1
0x18000d9e5  mov     r8d, r9d
0x18000d9e8  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000d9ec  call    wil_details_NtUpdateWnfStateData
0x18000d9f1  mov     esi, eax
0x18000d9f3  cmp     esi, 0C0000001h
0x18000d9f9  jnz     short loc_18000DA0C
0x18000d9fb  inc     r15d
0x18000d9fe  cmp     r15d, 64h ; 'd'
0x18000da02  jge     short loc_18000DA0C
0x18000da04  test    edi, edi
0x18000da06  jz      loc_18000D852
0x18000da0c  test    ebx, ebx
0x18000da0e  cmovz   ebx, esi
0x18000da11  mov     eax, ebx
0x18000da13  mov     rcx, [rbp+0F90h+var_40]
0x18000da1a  xor     rcx, rsp; StackCookie
0x18000da1d  call    __security_check_cookie
0x18000da22  add     rsp, 1068h
0x18000da29  pop     r15
0x18000da2b  pop     r14
0x18000da2d  pop     rdi
0x18000da2e  pop     rsi
0x18000da2f  pop     rbx
0x18000da30  pop     rbp
0x18000da31  retn
0x18000da32  mov     eax, [r8+8]
0x18000da36  add     [rcx+8], eax
0x18000da39  mov     r9d, [rsp+1090h+var_1050]
0x18000da3e  jmp     short loc_18000D9C4
```
