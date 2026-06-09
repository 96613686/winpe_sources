# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140012d0c`
- end: `0x140012f44`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14000f570`

## callees

- `0x140002310`
- `0x140002ecc`
- `0x140012d0c`
- `0x140012f4c`
- `0x140021f90`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012dac`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012dac`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012d95`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012d95`

## string_xrefs

- `0x140012d8e`: `ntdll.dll`

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
0x140012d0c  push    rbp
0x140012d0e  push    rbx
0x140012d0f  push    rsi
0x140012d10  push    rdi
0x140012d11  push    r14
0x140012d13  push    r15
0x140012d15  lea     rbp, [rsp-0F68h]
0x140012d1d  mov     eax, 1068h
0x140012d22  call    _alloca_probe
0x140012d27  sub     rsp, rax
0x140012d2a  mov     rax, cs:__security_cookie
0x140012d31  xor     rax, rsp
0x140012d34  mov     [rbp+0F90h+var_40], rax
0x140012d3b  mov     rax, [rcx+8]
0x140012d3f  xor     ebx, ebx
0x140012d41  sub     rax, [rcx]
0x140012d44  xor     esi, esi
0x140012d46  mov     r14, rcx
0x140012d49  cmp     rax, 0Ch
0x140012d4d  jb      loc_140012F10
0x140012d53  xor     r15d, r15d
0x140012d56  xor     edx, edx; Val
0x140012d58  lea     rcx, [rsp+1090h+var_1040]; void *
0x140012d5d  mov     r8d, 1000h; Size
0x140012d63  call    memset_0
0x140012d68  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x140012d70  mov     [rsp+1090h+var_1050], 1000h
0x140012d78  mov     [rsp+1090h+var_104C], 0
0x140012d80  jnz     short loc_140012DCA
0x140012d82  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012d89  test    rax, rax
0x140012d8c  jnz     short loc_140012DA2
0x140012d8e  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140012d95  call    cs:__imp_GetModuleHandleW
0x140012d9b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012da2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140012da9  mov     rcx, rax; hModule
0x140012dac  call    cs:__imp_GetProcAddress
0x140012db2  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140012db9  test    rax, rax
0x140012dbc  jnz     short loc_140012DCA
0x140012dbe  mov     edi, 0C0000139h
0x140012dc3  mov     ebx, edi
0x140012dc5  jmp     loc_140012EF7
0x140012dca  lea     rax, [rsp+1090h+var_1050]
0x140012dcf  xor     r8d, r8d
0x140012dd2  mov     [rsp+1090h+var_1068], rax
0x140012dd7  lea     r9, [rsp+1090h+var_104C]
0x140012ddc  lea     rax, [rsp+1090h+var_1040]
0x140012de1  xor     edx, edx
0x140012de3  mov     [rsp+1090h+var_1070], rax
0x140012de8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140012def  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140012df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012dfb  mov     ebx, eax
0x140012dfd  mov     edi, eax
0x140012dff  test    eax, eax
0x140012e01  jnz     loc_140012EF7
0x140012e07  mov     r9d, [rsp+1090h+var_1050]
0x140012e0c  mov     r11, 0AAAAAAAAAAAAAAABh
0x140012e16  mov     rax, r11
0x140012e19  mul     r9
0x140012e1c  shr     rdx, 3
0x140012e20  lea     rcx, [rdx+rdx*2]
0x140012e24  shl     rcx, 2
0x140012e28  cmp     r9, rcx
0x140012e2b  jz      short loc_140012E35
0x140012e2d  xor     r9d, r9d
0x140012e30  mov     [rsp+1090h+var_1050], r9d
0x140012e35  mov     r8, [r14]
0x140012e38  mov     rax, r11
0x140012e3b  mov     ecx, r9d
0x140012e3e  mul     rcx
0x140012e41  mov     rcx, [r14+8]
0x140012e45  mov     rax, r11
0x140012e48  mov     r10, rdx
0x140012e4b  sub     rcx, r8
0x140012e4e  mul     rcx
0x140012e51  shr     r10, 3
0x140012e55  shr     rdx, 3
0x140012e59  lea     rax, [rdx+rdx*2]
0x140012e5d  lea     rsi, [r8+rax*4]
0x140012e61  jmp     short loc_140012ECC
0x140012e63  mov     eax, r10d
0x140012e66  lea     rcx, [rax+rax*2]
0x140012e6a  lea     rdx, [rdx+rcx*4]
0x140012e6e  lea     rax, [rsp+1090h+var_1040]
0x140012e73  cmp     rax, rdx
0x140012e76  jz      short loc_140012E9D
0x140012e78  mov     r11d, [r8]
0x140012e7b  lea     rcx, [rsp+1090h+var_1040]
0x140012e80  cmp     [rcx], r11d
0x140012e83  jnz     short loc_140012E94
0x140012e85  movzx   eax, word ptr [r8+4]
0x140012e8a  cmp     [rcx+4], ax
0x140012e8e  jz      loc_140012F36
0x140012e94  add     rcx, 0Ch
0x140012e98  cmp     rcx, rdx
0x140012e9b  jnz     short loc_140012E80
0x140012e9d  mov     eax, r9d
0x140012ea0  add     rax, 0Ch
0x140012ea4  cmp     rax, 1000h
0x140012eaa  ja      short loc_140012EC8
0x140012eac  movsd   xmm0, qword ptr [r8]
0x140012eb1  add     r9d, 0Ch
0x140012eb5  movsd   qword ptr [rdx], xmm0
0x140012eb9  inc     r10d
0x140012ebc  mov     eax, [r8+8]
0x140012ec0  mov     [rdx+8], eax
0x140012ec3  mov     [rsp+1090h+var_1050], r9d
0x140012ec8  add     r8, 0Ch
0x140012ecc  lea     rdx, [rsp+1090h+var_1040]
0x140012ed1  cmp     r8, rsi
0x140012ed4  jnz     short loc_140012E63
0x140012ed6  mov     eax, [rsp+1090h+var_104C]
0x140012eda  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140012ee1  mov     [rsp+1090h+var_1060], 1
0x140012ee9  mov     r8d, r9d
0x140012eec  mov     dword ptr [rsp+1090h+var_1068], eax
0x140012ef0  call    wil_details_NtUpdateWnfStateData
0x140012ef5  mov     esi, eax
0x140012ef7  cmp     esi, 0C0000001h
0x140012efd  jnz     short loc_140012F10
0x140012eff  inc     r15d
0x140012f02  cmp     r15d, 64h ; 'd'
0x140012f06  jge     short loc_140012F10
0x140012f08  test    edi, edi
0x140012f0a  jz      loc_140012D56
0x140012f10  test    ebx, ebx
0x140012f12  cmovz   ebx, esi
0x140012f15  mov     eax, ebx
0x140012f17  mov     rcx, [rbp+0F90h+var_40]
0x140012f1e  xor     rcx, rsp; StackCookie
0x140012f21  call    __security_check_cookie
0x140012f26  add     rsp, 1068h
0x140012f2d  pop     r15
0x140012f2f  pop     r14
0x140012f31  pop     rdi
0x140012f32  pop     rsi
0x140012f33  pop     rbx
0x140012f34  pop     rbp
0x140012f35  retn
0x140012f36  mov     eax, [r8+8]
0x140012f3a  add     [rcx+8], eax
0x140012f3d  mov     r9d, [rsp+1090h+var_1050]
0x140012f42  jmp     short loc_140012EC8
```
