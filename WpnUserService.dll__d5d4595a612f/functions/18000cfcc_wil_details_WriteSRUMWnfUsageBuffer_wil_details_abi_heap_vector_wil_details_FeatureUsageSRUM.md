# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000cfcc`
- end: `0x18000d204`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180007560`

## callees

- `0x180002bc0`
- `0x18000354c`
- `0x18000cfcc`
- `0x18000d3e0`
- `0x180010ba0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d055`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d055`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d06c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d06c`

## string_xrefs

- `0x18000d04e`: `ntdll.dll`

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
0x18000cfcc  push    rbp
0x18000cfce  push    rbx
0x18000cfcf  push    rsi
0x18000cfd0  push    rdi
0x18000cfd1  push    r14
0x18000cfd3  push    r15
0x18000cfd5  lea     rbp, [rsp-0F68h]
0x18000cfdd  mov     eax, 1068h
0x18000cfe2  call    _alloca_probe
0x18000cfe7  sub     rsp, rax
0x18000cfea  mov     rax, cs:__security_cookie
0x18000cff1  xor     rax, rsp
0x18000cff4  mov     [rbp+0F90h+var_40], rax
0x18000cffb  mov     rax, [rcx+8]
0x18000cfff  xor     ebx, ebx
0x18000d001  sub     rax, [rcx]
0x18000d004  xor     esi, esi
0x18000d006  mov     r14, rcx
0x18000d009  cmp     rax, 0Ch
0x18000d00d  jb      loc_18000D1D0
0x18000d013  xor     r15d, r15d
0x18000d016  xor     edx, edx; Val
0x18000d018  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000d01d  mov     r8d, 1000h; Size
0x18000d023  call    memset_0
0x18000d028  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000d030  mov     [rsp+1090h+var_1050], 1000h
0x18000d038  mov     [rsp+1090h+var_104C], 0
0x18000d040  jnz     short loc_18000D08A
0x18000d042  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d049  test    rax, rax
0x18000d04c  jnz     short loc_18000D062
0x18000d04e  lea     rcx, ModuleName; "ntdll.dll"
0x18000d055  call    cs:__imp_GetModuleHandleW
0x18000d05b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d062  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000d069  mov     rcx, rax; hModule
0x18000d06c  call    cs:__imp_GetProcAddress
0x18000d072  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000d079  test    rax, rax
0x18000d07c  jnz     short loc_18000D08A
0x18000d07e  mov     edi, 0C0000139h
0x18000d083  mov     ebx, edi
0x18000d085  jmp     loc_18000D1B7
0x18000d08a  lea     rax, [rsp+1090h+var_1050]
0x18000d08f  xor     r8d, r8d
0x18000d092  mov     [rsp+1090h+var_1068], rax
0x18000d097  lea     r9, [rsp+1090h+var_104C]
0x18000d09c  lea     rax, [rsp+1090h+var_1040]
0x18000d0a1  xor     edx, edx
0x18000d0a3  mov     [rsp+1090h+var_1070], rax
0x18000d0a8  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d0af  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000d0b6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d0bb  mov     ebx, eax
0x18000d0bd  mov     edi, eax
0x18000d0bf  test    eax, eax
0x18000d0c1  jnz     loc_18000D1B7
0x18000d0c7  mov     r9d, [rsp+1090h+var_1050]
0x18000d0cc  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000d0d6  mov     rax, r11
0x18000d0d9  mul     r9
0x18000d0dc  shr     rdx, 3
0x18000d0e0  lea     rcx, [rdx+rdx*2]
0x18000d0e4  shl     rcx, 2
0x18000d0e8  cmp     r9, rcx
0x18000d0eb  jz      short loc_18000D0F5
0x18000d0ed  xor     r9d, r9d
0x18000d0f0  mov     [rsp+1090h+var_1050], r9d
0x18000d0f5  mov     r8, [r14]
0x18000d0f8  mov     rax, r11
0x18000d0fb  mov     ecx, r9d
0x18000d0fe  mul     rcx
0x18000d101  mov     rcx, [r14+8]
0x18000d105  mov     rax, r11
0x18000d108  mov     r10, rdx
0x18000d10b  sub     rcx, r8
0x18000d10e  mul     rcx
0x18000d111  shr     r10, 3
0x18000d115  shr     rdx, 3
0x18000d119  lea     rax, [rdx+rdx*2]
0x18000d11d  lea     rsi, [r8+rax*4]
0x18000d121  jmp     short loc_18000D18C
0x18000d123  mov     eax, r10d
0x18000d126  lea     rcx, [rax+rax*2]
0x18000d12a  lea     rdx, [rdx+rcx*4]
0x18000d12e  lea     rax, [rsp+1090h+var_1040]
0x18000d133  cmp     rax, rdx
0x18000d136  jz      short loc_18000D15D
0x18000d138  mov     r11d, [r8]
0x18000d13b  lea     rcx, [rsp+1090h+var_1040]
0x18000d140  cmp     [rcx], r11d
0x18000d143  jnz     short loc_18000D154
0x18000d145  movzx   eax, word ptr [r8+4]
0x18000d14a  cmp     [rcx+4], ax
0x18000d14e  jz      loc_18000D1F6
0x18000d154  add     rcx, 0Ch
0x18000d158  cmp     rcx, rdx
0x18000d15b  jnz     short loc_18000D140
0x18000d15d  mov     eax, r9d
0x18000d160  add     rax, 0Ch
0x18000d164  cmp     rax, 1000h
0x18000d16a  ja      short loc_18000D188
0x18000d16c  movsd   xmm0, qword ptr [r8]
0x18000d171  add     r9d, 0Ch
0x18000d175  movsd   qword ptr [rdx], xmm0
0x18000d179  inc     r10d
0x18000d17c  mov     eax, [r8+8]
0x18000d180  mov     [rdx+8], eax
0x18000d183  mov     [rsp+1090h+var_1050], r9d
0x18000d188  add     r8, 0Ch
0x18000d18c  lea     rdx, [rsp+1090h+var_1040]
0x18000d191  cmp     r8, rsi
0x18000d194  jnz     short loc_18000D123
0x18000d196  mov     eax, [rsp+1090h+var_104C]
0x18000d19a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000d1a1  mov     [rsp+1090h+var_1060], 1
0x18000d1a9  mov     r8d, r9d
0x18000d1ac  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000d1b0  call    wil_details_NtUpdateWnfStateData
0x18000d1b5  mov     esi, eax
0x18000d1b7  cmp     esi, 0C0000001h
0x18000d1bd  jnz     short loc_18000D1D0
0x18000d1bf  inc     r15d
0x18000d1c2  cmp     r15d, 64h ; 'd'
0x18000d1c6  jge     short loc_18000D1D0
0x18000d1c8  test    edi, edi
0x18000d1ca  jz      loc_18000D016
0x18000d1d0  test    ebx, ebx
0x18000d1d2  cmovz   ebx, esi
0x18000d1d5  mov     eax, ebx
0x18000d1d7  mov     rcx, [rbp+0F90h+var_40]
0x18000d1de  xor     rcx, rsp; StackCookie
0x18000d1e1  call    __security_check_cookie
0x18000d1e6  add     rsp, 1068h
0x18000d1ed  pop     r15
0x18000d1ef  pop     r14
0x18000d1f1  pop     rdi
0x18000d1f2  pop     rsi
0x18000d1f3  pop     rbx
0x18000d1f4  pop     rbp
0x18000d1f5  retn
0x18000d1f6  mov     eax, [r8+8]
0x18000d1fa  add     [rcx+8], eax
0x18000d1fd  mov     r9d, [rsp+1090h+var_1050]
0x18000d202  jmp     short loc_18000D188
```
