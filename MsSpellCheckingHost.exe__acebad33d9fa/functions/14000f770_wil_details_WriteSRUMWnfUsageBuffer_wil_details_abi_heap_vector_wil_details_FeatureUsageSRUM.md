# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000f770`
- end: `0x14000f9a8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140006c50`

## callees

- `0x1400023f3`
- `0x14000f770`
- `0x14000fc00`
- `0x140011e10`
- `0x140011ed0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f7f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000f7f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f810`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000f810`

## string_xrefs

- `0x14000f7f2`: `ntdll.dll`

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
0x14000f770  push    rbp
0x14000f772  push    rbx
0x14000f773  push    rsi
0x14000f774  push    rdi
0x14000f775  push    r14
0x14000f777  push    r15
0x14000f779  lea     rbp, [rsp-0F68h]
0x14000f781  mov     eax, 1068h
0x14000f786  call    _alloca_probe
0x14000f78b  sub     rsp, rax
0x14000f78e  mov     rax, cs:__security_cookie
0x14000f795  xor     rax, rsp
0x14000f798  mov     [rbp+0F90h+var_40], rax
0x14000f79f  mov     rax, [rcx+8]
0x14000f7a3  xor     ebx, ebx
0x14000f7a5  sub     rax, [rcx]
0x14000f7a8  xor     esi, esi
0x14000f7aa  mov     r14, rcx
0x14000f7ad  cmp     rax, 0Ch
0x14000f7b1  jb      loc_14000F974
0x14000f7b7  xor     r15d, r15d
0x14000f7ba  xor     edx, edx; Val
0x14000f7bc  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000f7c1  mov     r8d, 1000h; Size
0x14000f7c7  call    memset_0
0x14000f7cc  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000f7d4  mov     [rsp+1090h+var_1050], 1000h
0x14000f7dc  mov     [rsp+1090h+var_104C], 0
0x14000f7e4  jnz     short loc_14000F82E
0x14000f7e6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000f7ed  test    rax, rax
0x14000f7f0  jnz     short loc_14000F806
0x14000f7f2  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000f7f9  call    cs:__imp_GetModuleHandleW
0x14000f7ff  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000f806  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000f80d  mov     rcx, rax; hModule
0x14000f810  call    cs:__imp_GetProcAddress
0x14000f816  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000f81d  test    rax, rax
0x14000f820  jnz     short loc_14000F82E
0x14000f822  mov     edi, 0C0000139h
0x14000f827  mov     ebx, edi
0x14000f829  jmp     loc_14000F95B
0x14000f82e  lea     rax, [rsp+1090h+var_1050]
0x14000f833  xor     r8d, r8d
0x14000f836  mov     [rsp+1090h+var_1068], rax
0x14000f83b  lea     r9, [rsp+1090h+var_104C]
0x14000f840  lea     rax, [rsp+1090h+var_1040]
0x14000f845  xor     edx, edx
0x14000f847  mov     [rsp+1090h+var_1070], rax
0x14000f84c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000f853  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000f85a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000f85f  mov     ebx, eax
0x14000f861  mov     edi, eax
0x14000f863  test    eax, eax
0x14000f865  jnz     loc_14000F95B
0x14000f86b  mov     r9d, [rsp+1090h+var_1050]
0x14000f870  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000f87a  mov     rax, r11
0x14000f87d  mul     r9
0x14000f880  shr     rdx, 3
0x14000f884  lea     rcx, [rdx+rdx*2]
0x14000f888  shl     rcx, 2
0x14000f88c  cmp     r9, rcx
0x14000f88f  jz      short loc_14000F899
0x14000f891  xor     r9d, r9d
0x14000f894  mov     [rsp+1090h+var_1050], r9d
0x14000f899  mov     r8, [r14]
0x14000f89c  mov     rax, r11
0x14000f89f  mov     ecx, r9d
0x14000f8a2  mul     rcx
0x14000f8a5  mov     rcx, [r14+8]
0x14000f8a9  mov     rax, r11
0x14000f8ac  mov     r10, rdx
0x14000f8af  sub     rcx, r8
0x14000f8b2  mul     rcx
0x14000f8b5  shr     r10, 3
0x14000f8b9  shr     rdx, 3
0x14000f8bd  lea     rax, [rdx+rdx*2]
0x14000f8c1  lea     rsi, [r8+rax*4]
0x14000f8c5  jmp     short loc_14000F930
0x14000f8c7  mov     eax, r10d
0x14000f8ca  lea     rcx, [rax+rax*2]
0x14000f8ce  lea     rdx, [rdx+rcx*4]
0x14000f8d2  lea     rax, [rsp+1090h+var_1040]
0x14000f8d7  cmp     rax, rdx
0x14000f8da  jz      short loc_14000F901
0x14000f8dc  mov     r11d, [r8]
0x14000f8df  lea     rcx, [rsp+1090h+var_1040]
0x14000f8e4  cmp     [rcx], r11d
0x14000f8e7  jnz     short loc_14000F8F8
0x14000f8e9  movzx   eax, word ptr [r8+4]
0x14000f8ee  cmp     [rcx+4], ax
0x14000f8f2  jz      loc_14000F99A
0x14000f8f8  add     rcx, 0Ch
0x14000f8fc  cmp     rcx, rdx
0x14000f8ff  jnz     short loc_14000F8E4
0x14000f901  mov     eax, r9d
0x14000f904  add     rax, 0Ch
0x14000f908  cmp     rax, 1000h
0x14000f90e  ja      short loc_14000F92C
0x14000f910  movsd   xmm0, qword ptr [r8]
0x14000f915  add     r9d, 0Ch
0x14000f919  movsd   qword ptr [rdx], xmm0
0x14000f91d  inc     r10d
0x14000f920  mov     eax, [r8+8]
0x14000f924  mov     [rdx+8], eax
0x14000f927  mov     [rsp+1090h+var_1050], r9d
0x14000f92c  add     r8, 0Ch
0x14000f930  lea     rdx, [rsp+1090h+var_1040]
0x14000f935  cmp     r8, rsi
0x14000f938  jnz     short loc_14000F8C7
0x14000f93a  mov     eax, [rsp+1090h+var_104C]
0x14000f93e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000f945  mov     [rsp+1090h+var_1060], 1
0x14000f94d  mov     r8d, r9d
0x14000f950  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000f954  call    wil_details_NtUpdateWnfStateData
0x14000f959  mov     esi, eax
0x14000f95b  cmp     esi, 0C0000001h
0x14000f961  jnz     short loc_14000F974
0x14000f963  inc     r15d
0x14000f966  cmp     r15d, 64h ; 'd'
0x14000f96a  jge     short loc_14000F974
0x14000f96c  test    edi, edi
0x14000f96e  jz      loc_14000F7BA
0x14000f974  test    ebx, ebx
0x14000f976  cmovz   ebx, esi
0x14000f979  mov     eax, ebx
0x14000f97b  mov     rcx, [rbp+0F90h+var_40]
0x14000f982  xor     rcx, rsp; StackCookie
0x14000f985  call    __security_check_cookie
0x14000f98a  add     rsp, 1068h
0x14000f991  pop     r15
0x14000f993  pop     r14
0x14000f995  pop     rdi
0x14000f996  pop     rsi
0x14000f997  pop     rbx
0x14000f998  pop     rbp
0x14000f999  retn
0x14000f99a  mov     eax, [r8+8]
0x14000f99e  add     [rcx+8], eax
0x14000f9a1  mov     r9d, [rsp+1090h+var_1050]
0x14000f9a6  jmp     short loc_14000F92C
```
