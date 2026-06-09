# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180024e34`
- end: `0x18002506c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180018280`

## callees

- `0x180024e34`
- `0x180025074`
- `0x1800322d2`
- `0x180032310`
- `0x1800323d0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024ebd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180024ebd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024ed4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180024ed4`

## string_xrefs

- `0x180024eb6`: `ntdll.dll`

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
0x180024e34  push    rbp
0x180024e36  push    rbx
0x180024e37  push    rsi
0x180024e38  push    rdi
0x180024e39  push    r14
0x180024e3b  push    r15
0x180024e3d  lea     rbp, [rsp-0F68h]
0x180024e45  mov     eax, 1068h
0x180024e4a  call    _alloca_probe
0x180024e4f  sub     rsp, rax
0x180024e52  mov     rax, cs:__security_cookie
0x180024e59  xor     rax, rsp
0x180024e5c  mov     [rbp+0F90h+var_40], rax
0x180024e63  mov     rax, [rcx+8]
0x180024e67  xor     ebx, ebx
0x180024e69  sub     rax, [rcx]
0x180024e6c  xor     esi, esi
0x180024e6e  mov     r14, rcx
0x180024e71  cmp     rax, 0Ch
0x180024e75  jb      loc_180025038
0x180024e7b  xor     r15d, r15d
0x180024e7e  xor     edx, edx; Val
0x180024e80  lea     rcx, [rsp+1090h+var_1040]; void *
0x180024e85  mov     r8d, 1000h; Size
0x180024e8b  call    memset_0
0x180024e90  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180024e98  mov     [rsp+1090h+var_1050], 1000h
0x180024ea0  mov     [rsp+1090h+var_104C], 0
0x180024ea8  jnz     short loc_180024EF2
0x180024eaa  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180024eb1  test    rax, rax
0x180024eb4  jnz     short loc_180024ECA
0x180024eb6  lea     rcx, LibFileName; "ntdll.dll"
0x180024ebd  call    cs:__imp_GetModuleHandleW
0x180024ec3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180024eca  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180024ed1  mov     rcx, rax; hModule
0x180024ed4  call    cs:__imp_GetProcAddress
0x180024eda  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180024ee1  test    rax, rax
0x180024ee4  jnz     short loc_180024EF2
0x180024ee6  mov     edi, 0C0000139h
0x180024eeb  mov     ebx, edi
0x180024eed  jmp     loc_18002501F
0x180024ef2  lea     rax, [rsp+1090h+var_1050]
0x180024ef7  xor     r8d, r8d
0x180024efa  mov     [rsp+1090h+var_1068], rax
0x180024eff  lea     r9, [rsp+1090h+var_104C]
0x180024f04  lea     rax, [rsp+1090h+var_1040]
0x180024f09  xor     edx, edx
0x180024f0b  mov     [rsp+1090h+var_1070], rax
0x180024f10  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180024f17  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180024f1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180024f23  mov     ebx, eax
0x180024f25  mov     edi, eax
0x180024f27  test    eax, eax
0x180024f29  jnz     loc_18002501F
0x180024f2f  mov     r9d, [rsp+1090h+var_1050]
0x180024f34  mov     r11, 0AAAAAAAAAAAAAAABh
0x180024f3e  mov     rax, r11
0x180024f41  mul     r9
0x180024f44  shr     rdx, 3
0x180024f48  lea     rcx, [rdx+rdx*2]
0x180024f4c  shl     rcx, 2
0x180024f50  cmp     r9, rcx
0x180024f53  jz      short loc_180024F5D
0x180024f55  xor     r9d, r9d
0x180024f58  mov     [rsp+1090h+var_1050], r9d
0x180024f5d  mov     r8, [r14]
0x180024f60  mov     rax, r11
0x180024f63  mov     ecx, r9d
0x180024f66  mul     rcx
0x180024f69  mov     rcx, [r14+8]
0x180024f6d  mov     rax, r11
0x180024f70  mov     r10, rdx
0x180024f73  sub     rcx, r8
0x180024f76  mul     rcx
0x180024f79  shr     r10, 3
0x180024f7d  shr     rdx, 3
0x180024f81  lea     rax, [rdx+rdx*2]
0x180024f85  lea     rsi, [r8+rax*4]
0x180024f89  jmp     short loc_180024FF4
0x180024f8b  mov     eax, r10d
0x180024f8e  lea     rcx, [rax+rax*2]
0x180024f92  lea     rdx, [rdx+rcx*4]
0x180024f96  lea     rax, [rsp+1090h+var_1040]
0x180024f9b  cmp     rax, rdx
0x180024f9e  jz      short loc_180024FC5
0x180024fa0  mov     r11d, [r8]
0x180024fa3  lea     rcx, [rsp+1090h+var_1040]
0x180024fa8  cmp     [rcx], r11d
0x180024fab  jnz     short loc_180024FBC
0x180024fad  movzx   eax, word ptr [r8+4]
0x180024fb2  cmp     [rcx+4], ax
0x180024fb6  jz      loc_18002505E
0x180024fbc  add     rcx, 0Ch
0x180024fc0  cmp     rcx, rdx
0x180024fc3  jnz     short loc_180024FA8
0x180024fc5  mov     eax, r9d
0x180024fc8  add     rax, 0Ch
0x180024fcc  cmp     rax, 1000h
0x180024fd2  ja      short loc_180024FF0
0x180024fd4  movsd   xmm0, qword ptr [r8]
0x180024fd9  add     r9d, 0Ch
0x180024fdd  movsd   qword ptr [rdx], xmm0
0x180024fe1  inc     r10d
0x180024fe4  mov     eax, [r8+8]
0x180024fe8  mov     [rdx+8], eax
0x180024feb  mov     [rsp+1090h+var_1050], r9d
0x180024ff0  add     r8, 0Ch
0x180024ff4  lea     rdx, [rsp+1090h+var_1040]
0x180024ff9  cmp     r8, rsi
0x180024ffc  jnz     short loc_180024F8B
0x180024ffe  mov     eax, [rsp+1090h+var_104C]
0x180025002  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180025009  mov     [rsp+1090h+var_1060], 1
0x180025011  mov     r8d, r9d
0x180025014  mov     dword ptr [rsp+1090h+var_1068], eax
0x180025018  call    wil_details_NtUpdateWnfStateData
0x18002501d  mov     esi, eax
0x18002501f  cmp     esi, 0C0000001h
0x180025025  jnz     short loc_180025038
0x180025027  inc     r15d
0x18002502a  cmp     r15d, 64h ; 'd'
0x18002502e  jge     short loc_180025038
0x180025030  test    edi, edi
0x180025032  jz      loc_180024E7E
0x180025038  test    ebx, ebx
0x18002503a  cmovz   ebx, esi
0x18002503d  mov     eax, ebx
0x18002503f  mov     rcx, [rbp+0F90h+var_40]
0x180025046  xor     rcx, rsp; StackCookie
0x180025049  call    __security_check_cookie
0x18002504e  add     rsp, 1068h
0x180025055  pop     r15
0x180025057  pop     r14
0x180025059  pop     rdi
0x18002505a  pop     rsi
0x18002505b  pop     rbx
0x18002505c  pop     rbp
0x18002505d  retn
0x18002505e  mov     eax, [r8+8]
0x180025062  add     [rcx+8], eax
0x180025065  mov     r9d, [rsp+1090h+var_1050]
0x18002506a  jmp     short loc_180024FF0
```
