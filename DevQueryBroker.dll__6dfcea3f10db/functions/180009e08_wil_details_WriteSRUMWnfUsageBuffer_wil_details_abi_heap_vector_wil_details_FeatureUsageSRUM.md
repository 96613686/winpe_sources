# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180009e08`
- end: `0x18000a040`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180004870`

## callees

- `0x180009e08`
- `0x18000a048`
- `0x18000a19e`
- `0x18000a1d0`
- `0x18000a260`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ea8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009ea8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e91`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009e91`

## string_xrefs

- `0x180009e8a`: `ntdll.dll`

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
0x180009e08  push    rbp
0x180009e0a  push    rbx
0x180009e0b  push    rsi
0x180009e0c  push    rdi
0x180009e0d  push    r14
0x180009e0f  push    r15
0x180009e11  lea     rbp, [rsp-0F68h]
0x180009e19  mov     eax, 1068h
0x180009e1e  call    _alloca_probe
0x180009e23  sub     rsp, rax
0x180009e26  mov     rax, cs:__security_cookie
0x180009e2d  xor     rax, rsp
0x180009e30  mov     [rbp+0F90h+var_40], rax
0x180009e37  mov     rax, [rcx+8]
0x180009e3b  xor     ebx, ebx
0x180009e3d  sub     rax, [rcx]
0x180009e40  xor     esi, esi
0x180009e42  mov     r14, rcx
0x180009e45  cmp     rax, 0Ch
0x180009e49  jb      loc_18000A00C
0x180009e4f  xor     r15d, r15d
0x180009e52  xor     edx, edx; Val
0x180009e54  lea     rcx, [rsp+1090h+var_1040]; void *
0x180009e59  mov     r8d, 1000h; Size
0x180009e5f  call    memset_0
0x180009e64  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180009e6c  mov     [rsp+1090h+var_1050], 1000h
0x180009e74  mov     [rsp+1090h+var_104C], 0
0x180009e7c  jnz     short loc_180009EC6
0x180009e7e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009e85  test    rax, rax
0x180009e88  jnz     short loc_180009E9E
0x180009e8a  lea     rcx, ModuleName; "ntdll.dll"
0x180009e91  call    cs:__imp_GetModuleHandleW
0x180009e97  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009e9e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009ea5  mov     rcx, rax; hModule
0x180009ea8  call    cs:__imp_GetProcAddress
0x180009eae  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009eb5  test    rax, rax
0x180009eb8  jnz     short loc_180009EC6
0x180009eba  mov     edi, 0C0000139h
0x180009ebf  mov     ebx, edi
0x180009ec1  jmp     loc_180009FF3
0x180009ec6  lea     rax, [rsp+1090h+var_1050]
0x180009ecb  xor     r8d, r8d
0x180009ece  mov     [rsp+1090h+var_1068], rax
0x180009ed3  lea     r9, [rsp+1090h+var_104C]
0x180009ed8  lea     rax, [rsp+1090h+var_1040]
0x180009edd  xor     edx, edx
0x180009edf  mov     [rsp+1090h+var_1070], rax
0x180009ee4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009eeb  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180009ef2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ef7  mov     ebx, eax
0x180009ef9  mov     edi, eax
0x180009efb  test    eax, eax
0x180009efd  jnz     loc_180009FF3
0x180009f03  mov     r9d, [rsp+1090h+var_1050]
0x180009f08  mov     r11, 0AAAAAAAAAAAAAAABh
0x180009f12  mov     rax, r11
0x180009f15  mul     r9
0x180009f18  shr     rdx, 3
0x180009f1c  lea     rcx, [rdx+rdx*2]
0x180009f20  shl     rcx, 2
0x180009f24  cmp     r9, rcx
0x180009f27  jz      short loc_180009F31
0x180009f29  xor     r9d, r9d
0x180009f2c  mov     [rsp+1090h+var_1050], r9d
0x180009f31  mov     r8, [r14]
0x180009f34  mov     rax, r11
0x180009f37  mov     ecx, r9d
0x180009f3a  mul     rcx
0x180009f3d  mov     rcx, [r14+8]
0x180009f41  mov     rax, r11
0x180009f44  mov     r10, rdx
0x180009f47  sub     rcx, r8
0x180009f4a  mul     rcx
0x180009f4d  shr     r10, 3
0x180009f51  shr     rdx, 3
0x180009f55  lea     rax, [rdx+rdx*2]
0x180009f59  lea     rsi, [r8+rax*4]
0x180009f5d  jmp     short loc_180009FC8
0x180009f5f  mov     eax, r10d
0x180009f62  lea     rcx, [rax+rax*2]
0x180009f66  lea     rdx, [rdx+rcx*4]
0x180009f6a  lea     rax, [rsp+1090h+var_1040]
0x180009f6f  cmp     rax, rdx
0x180009f72  jz      short loc_180009F99
0x180009f74  mov     r11d, [r8]
0x180009f77  lea     rcx, [rsp+1090h+var_1040]
0x180009f7c  cmp     [rcx], r11d
0x180009f7f  jnz     short loc_180009F90
0x180009f81  movzx   eax, word ptr [r8+4]
0x180009f86  cmp     [rcx+4], ax
0x180009f8a  jz      loc_18000A032
0x180009f90  add     rcx, 0Ch
0x180009f94  cmp     rcx, rdx
0x180009f97  jnz     short loc_180009F7C
0x180009f99  mov     eax, r9d
0x180009f9c  add     rax, 0Ch
0x180009fa0  cmp     rax, 1000h
0x180009fa6  ja      short loc_180009FC4
0x180009fa8  movsd   xmm0, qword ptr [r8]
0x180009fad  add     r9d, 0Ch
0x180009fb1  movsd   qword ptr [rdx], xmm0
0x180009fb5  inc     r10d
0x180009fb8  mov     eax, [r8+8]
0x180009fbc  mov     [rdx+8], eax
0x180009fbf  mov     [rsp+1090h+var_1050], r9d
0x180009fc4  add     r8, 0Ch
0x180009fc8  lea     rdx, [rsp+1090h+var_1040]
0x180009fcd  cmp     r8, rsi
0x180009fd0  jnz     short loc_180009F5F
0x180009fd2  mov     eax, [rsp+1090h+var_104C]
0x180009fd6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009fdd  mov     [rsp+1090h+var_1060], 1
0x180009fe5  mov     r8d, r9d
0x180009fe8  mov     dword ptr [rsp+1090h+var_1068], eax
0x180009fec  call    wil_details_NtUpdateWnfStateData
0x180009ff1  mov     esi, eax
0x180009ff3  cmp     esi, 0C0000001h
0x180009ff9  jnz     short loc_18000A00C
0x180009ffb  inc     r15d
0x180009ffe  cmp     r15d, 64h ; 'd'
0x18000a002  jge     short loc_18000A00C
0x18000a004  test    edi, edi
0x18000a006  jz      loc_180009E52
0x18000a00c  test    ebx, ebx
0x18000a00e  cmovz   ebx, esi
0x18000a011  mov     eax, ebx
0x18000a013  mov     rcx, [rbp+0F90h+var_40]
0x18000a01a  xor     rcx, rsp; StackCookie
0x18000a01d  call    __security_check_cookie
0x18000a022  add     rsp, 1068h
0x18000a029  pop     r15
0x18000a02b  pop     r14
0x18000a02d  pop     rdi
0x18000a02e  pop     rsi
0x18000a02f  pop     rbx
0x18000a030  pop     rbp
0x18000a031  retn
0x18000a032  mov     eax, [r8+8]
0x18000a036  add     [rcx+8], eax
0x18000a039  mov     r9d, [rsp+1090h+var_1050]
0x18000a03e  jmp     short loc_180009FC4
```
