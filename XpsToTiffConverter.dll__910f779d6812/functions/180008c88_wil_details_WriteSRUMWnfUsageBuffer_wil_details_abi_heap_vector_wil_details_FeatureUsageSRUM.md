# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008c88`
- end: `0x180008ec0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002240`

## callees

- `0x1800016a0`
- `0x1800020e4`
- `0x180008c88`
- `0x180008f98`
- `0x18000caf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d28`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008d28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d11`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008d11`

## string_xrefs

- `0x180008d0a`: `ntdll.dll`

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
0x180008c88  push    rbp
0x180008c8a  push    rbx
0x180008c8b  push    rsi
0x180008c8c  push    rdi
0x180008c8d  push    r14
0x180008c8f  push    r15
0x180008c91  lea     rbp, [rsp-0F68h]
0x180008c99  mov     eax, 1068h
0x180008c9e  call    _alloca_probe
0x180008ca3  sub     rsp, rax
0x180008ca6  mov     rax, cs:__security_cookie
0x180008cad  xor     rax, rsp
0x180008cb0  mov     [rbp+0F90h+var_40], rax
0x180008cb7  mov     rax, [rcx+8]
0x180008cbb  xor     ebx, ebx
0x180008cbd  sub     rax, [rcx]
0x180008cc0  xor     esi, esi
0x180008cc2  mov     r14, rcx
0x180008cc5  cmp     rax, 0Ch
0x180008cc9  jb      loc_180008E8C
0x180008ccf  xor     r15d, r15d
0x180008cd2  xor     edx, edx; Val
0x180008cd4  lea     rcx, [rsp+1090h+var_1040]; void *
0x180008cd9  mov     r8d, 1000h; Size
0x180008cdf  call    memset_0
0x180008ce4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180008cec  mov     [rsp+1090h+var_1050], 1000h
0x180008cf4  mov     [rsp+1090h+var_104C], 0
0x180008cfc  jnz     short loc_180008D46
0x180008cfe  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d05  test    rax, rax
0x180008d08  jnz     short loc_180008D1E
0x180008d0a  lea     rcx, ModuleName; "ntdll.dll"
0x180008d11  call    cs:__imp_GetModuleHandleW
0x180008d17  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008d1e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008d25  mov     rcx, rax; hModule
0x180008d28  call    cs:__imp_GetProcAddress
0x180008d2e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008d35  test    rax, rax
0x180008d38  jnz     short loc_180008D46
0x180008d3a  mov     edi, 0C0000139h
0x180008d3f  mov     ebx, edi
0x180008d41  jmp     loc_180008E73
0x180008d46  lea     rax, [rsp+1090h+var_1050]
0x180008d4b  xor     r8d, r8d
0x180008d4e  mov     [rsp+1090h+var_1068], rax
0x180008d53  lea     r9, [rsp+1090h+var_104C]
0x180008d58  lea     rax, [rsp+1090h+var_1040]
0x180008d5d  xor     edx, edx
0x180008d5f  mov     [rsp+1090h+var_1070], rax
0x180008d64  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008d6b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008d72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008d77  mov     ebx, eax
0x180008d79  mov     edi, eax
0x180008d7b  test    eax, eax
0x180008d7d  jnz     loc_180008E73
0x180008d83  mov     r9d, [rsp+1090h+var_1050]
0x180008d88  mov     r11, 0AAAAAAAAAAAAAAABh
0x180008d92  mov     rax, r11
0x180008d95  mul     r9
0x180008d98  shr     rdx, 3
0x180008d9c  lea     rcx, [rdx+rdx*2]
0x180008da0  shl     rcx, 2
0x180008da4  cmp     r9, rcx
0x180008da7  jz      short loc_180008DB1
0x180008da9  xor     r9d, r9d
0x180008dac  mov     [rsp+1090h+var_1050], r9d
0x180008db1  mov     r8, [r14]
0x180008db4  mov     rax, r11
0x180008db7  mov     ecx, r9d
0x180008dba  mul     rcx
0x180008dbd  mov     rcx, [r14+8]
0x180008dc1  mov     rax, r11
0x180008dc4  mov     r10, rdx
0x180008dc7  sub     rcx, r8
0x180008dca  mul     rcx
0x180008dcd  shr     r10, 3
0x180008dd1  shr     rdx, 3
0x180008dd5  lea     rax, [rdx+rdx*2]
0x180008dd9  lea     rsi, [r8+rax*4]
0x180008ddd  jmp     short loc_180008E48
0x180008ddf  mov     eax, r10d
0x180008de2  lea     rcx, [rax+rax*2]
0x180008de6  lea     rdx, [rdx+rcx*4]
0x180008dea  lea     rax, [rsp+1090h+var_1040]
0x180008def  cmp     rax, rdx
0x180008df2  jz      short loc_180008E19
0x180008df4  mov     r11d, [r8]
0x180008df7  lea     rcx, [rsp+1090h+var_1040]
0x180008dfc  cmp     [rcx], r11d
0x180008dff  jnz     short loc_180008E10
0x180008e01  movzx   eax, word ptr [r8+4]
0x180008e06  cmp     [rcx+4], ax
0x180008e0a  jz      loc_180008EB2
0x180008e10  add     rcx, 0Ch
0x180008e14  cmp     rcx, rdx
0x180008e17  jnz     short loc_180008DFC
0x180008e19  mov     eax, r9d
0x180008e1c  add     rax, 0Ch
0x180008e20  cmp     rax, 1000h
0x180008e26  ja      short loc_180008E44
0x180008e28  movsd   xmm0, qword ptr [r8]
0x180008e2d  add     r9d, 0Ch
0x180008e31  movsd   qword ptr [rdx], xmm0
0x180008e35  inc     r10d
0x180008e38  mov     eax, [r8+8]
0x180008e3c  mov     [rdx+8], eax
0x180008e3f  mov     [rsp+1090h+var_1050], r9d
0x180008e44  add     r8, 0Ch
0x180008e48  lea     rdx, [rsp+1090h+var_1040]
0x180008e4d  cmp     r8, rsi
0x180008e50  jnz     short loc_180008DDF
0x180008e52  mov     eax, [rsp+1090h+var_104C]
0x180008e56  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008e5d  mov     [rsp+1090h+var_1060], 1
0x180008e65  mov     r8d, r9d
0x180008e68  mov     dword ptr [rsp+1090h+var_1068], eax
0x180008e6c  call    wil_details_NtUpdateWnfStateData
0x180008e71  mov     esi, eax
0x180008e73  cmp     esi, 0C0000001h
0x180008e79  jnz     short loc_180008E8C
0x180008e7b  inc     r15d
0x180008e7e  cmp     r15d, 64h ; 'd'
0x180008e82  jge     short loc_180008E8C
0x180008e84  test    edi, edi
0x180008e86  jz      loc_180008CD2
0x180008e8c  test    ebx, ebx
0x180008e8e  cmovz   ebx, esi
0x180008e91  mov     eax, ebx
0x180008e93  mov     rcx, [rbp+0F90h+var_40]
0x180008e9a  xor     rcx, rsp; StackCookie
0x180008e9d  call    __security_check_cookie
0x180008ea2  add     rsp, 1068h
0x180008ea9  pop     r15
0x180008eab  pop     r14
0x180008ead  pop     rdi
0x180008eae  pop     rsi
0x180008eaf  pop     rbx
0x180008eb0  pop     rbp
0x180008eb1  retn
0x180008eb2  mov     eax, [r8+8]
0x180008eb6  add     [rcx+8], eax
0x180008eb9  mov     r9d, [rsp+1090h+var_1050]
0x180008ebe  jmp     short loc_180008E44
```
