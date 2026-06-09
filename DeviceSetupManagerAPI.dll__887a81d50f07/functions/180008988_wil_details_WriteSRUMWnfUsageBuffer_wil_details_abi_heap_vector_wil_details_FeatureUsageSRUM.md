# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008988`
- end: `0x180008bc0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002710`

## callees

- `0x1800017c0`
- `0x180002570`
- `0x180008988`
- `0x180008c58`
- `0x18000e3e0`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a28`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008a28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a11`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008a11`

## string_xrefs

- `0x180008a0a`: `ntdll.dll`

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
0x180008988  push    rbp
0x18000898a  push    rbx
0x18000898b  push    rsi
0x18000898c  push    rdi
0x18000898d  push    r14
0x18000898f  push    r15
0x180008991  lea     rbp, [rsp-0F68h]
0x180008999  mov     eax, 1068h
0x18000899e  call    _alloca_probe
0x1800089a3  sub     rsp, rax
0x1800089a6  mov     rax, cs:__security_cookie
0x1800089ad  xor     rax, rsp
0x1800089b0  mov     [rbp+0F90h+var_40], rax
0x1800089b7  mov     rax, [rcx+8]
0x1800089bb  xor     ebx, ebx
0x1800089bd  sub     rax, [rcx]
0x1800089c0  xor     esi, esi
0x1800089c2  mov     r14, rcx
0x1800089c5  cmp     rax, 0Ch
0x1800089c9  jb      loc_180008B8C
0x1800089cf  xor     r15d, r15d
0x1800089d2  xor     edx, edx; Val
0x1800089d4  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800089d9  mov     r8d, 1000h; Size
0x1800089df  call    memset_0
0x1800089e4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800089ec  mov     [rsp+1090h+var_1050], 1000h
0x1800089f4  mov     [rsp+1090h+var_104C], 0
0x1800089fc  jnz     short loc_180008A46
0x1800089fe  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a05  test    rax, rax
0x180008a08  jnz     short loc_180008A1E
0x180008a0a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008a11  call    cs:__imp_GetModuleHandleW
0x180008a17  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008a1e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008a25  mov     rcx, rax; hModule
0x180008a28  call    cs:__imp_GetProcAddress
0x180008a2e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008a35  test    rax, rax
0x180008a38  jnz     short loc_180008A46
0x180008a3a  mov     edi, 0C0000139h
0x180008a3f  mov     ebx, edi
0x180008a41  jmp     loc_180008B73
0x180008a46  lea     rax, [rsp+1090h+var_1050]
0x180008a4b  xor     r8d, r8d
0x180008a4e  mov     [rsp+1090h+var_1068], rax
0x180008a53  lea     r9, [rsp+1090h+var_104C]
0x180008a58  lea     rax, [rsp+1090h+var_1040]
0x180008a5d  xor     edx, edx
0x180008a5f  mov     [rsp+1090h+var_1070], rax
0x180008a64  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008a6b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008a72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a77  mov     ebx, eax
0x180008a79  mov     edi, eax
0x180008a7b  test    eax, eax
0x180008a7d  jnz     loc_180008B73
0x180008a83  mov     r9d, [rsp+1090h+var_1050]
0x180008a88  mov     r11, 0AAAAAAAAAAAAAAABh
0x180008a92  mov     rax, r11
0x180008a95  mul     r9
0x180008a98  shr     rdx, 3
0x180008a9c  lea     rcx, [rdx+rdx*2]
0x180008aa0  shl     rcx, 2
0x180008aa4  cmp     r9, rcx
0x180008aa7  jz      short loc_180008AB1
0x180008aa9  xor     r9d, r9d
0x180008aac  mov     [rsp+1090h+var_1050], r9d
0x180008ab1  mov     r8, [r14]
0x180008ab4  mov     rax, r11
0x180008ab7  mov     ecx, r9d
0x180008aba  mul     rcx
0x180008abd  mov     rcx, [r14+8]
0x180008ac1  mov     rax, r11
0x180008ac4  mov     r10, rdx
0x180008ac7  sub     rcx, r8
0x180008aca  mul     rcx
0x180008acd  shr     r10, 3
0x180008ad1  shr     rdx, 3
0x180008ad5  lea     rax, [rdx+rdx*2]
0x180008ad9  lea     rsi, [r8+rax*4]
0x180008add  jmp     short loc_180008B48
0x180008adf  mov     eax, r10d
0x180008ae2  lea     rcx, [rax+rax*2]
0x180008ae6  lea     rdx, [rdx+rcx*4]
0x180008aea  lea     rax, [rsp+1090h+var_1040]
0x180008aef  cmp     rax, rdx
0x180008af2  jz      short loc_180008B19
0x180008af4  mov     r11d, [r8]
0x180008af7  lea     rcx, [rsp+1090h+var_1040]
0x180008afc  cmp     [rcx], r11d
0x180008aff  jnz     short loc_180008B10
0x180008b01  movzx   eax, word ptr [r8+4]
0x180008b06  cmp     [rcx+4], ax
0x180008b0a  jz      loc_180008BB2
0x180008b10  add     rcx, 0Ch
0x180008b14  cmp     rcx, rdx
0x180008b17  jnz     short loc_180008AFC
0x180008b19  mov     eax, r9d
0x180008b1c  add     rax, 0Ch
0x180008b20  cmp     rax, 1000h
0x180008b26  ja      short loc_180008B44
0x180008b28  movsd   xmm0, qword ptr [r8]
0x180008b2d  add     r9d, 0Ch
0x180008b31  movsd   qword ptr [rdx], xmm0
0x180008b35  inc     r10d
0x180008b38  mov     eax, [r8+8]
0x180008b3c  mov     [rdx+8], eax
0x180008b3f  mov     [rsp+1090h+var_1050], r9d
0x180008b44  add     r8, 0Ch
0x180008b48  lea     rdx, [rsp+1090h+var_1040]
0x180008b4d  cmp     r8, rsi
0x180008b50  jnz     short loc_180008ADF
0x180008b52  mov     eax, [rsp+1090h+var_104C]
0x180008b56  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008b5d  mov     [rsp+1090h+var_1060], 1
0x180008b65  mov     r8d, r9d
0x180008b68  mov     dword ptr [rsp+1090h+var_1068], eax
0x180008b6c  call    wil_details_NtUpdateWnfStateData
0x180008b71  mov     esi, eax
0x180008b73  cmp     esi, 0C0000001h
0x180008b79  jnz     short loc_180008B8C
0x180008b7b  inc     r15d
0x180008b7e  cmp     r15d, 64h ; 'd'
0x180008b82  jge     short loc_180008B8C
0x180008b84  test    edi, edi
0x180008b86  jz      loc_1800089D2
0x180008b8c  test    ebx, ebx
0x180008b8e  cmovz   ebx, esi
0x180008b91  mov     eax, ebx
0x180008b93  mov     rcx, [rbp+0F90h+var_40]
0x180008b9a  xor     rcx, rsp; StackCookie
0x180008b9d  call    __security_check_cookie
0x180008ba2  add     rsp, 1068h
0x180008ba9  pop     r15
0x180008bab  pop     r14
0x180008bad  pop     rdi
0x180008bae  pop     rsi
0x180008baf  pop     rbx
0x180008bb0  pop     rbp
0x180008bb1  retn
0x180008bb2  mov     eax, [r8+8]
0x180008bb6  add     [rcx+8], eax
0x180008bb9  mov     r9d, [rsp+1090h+var_1050]
0x180008bbe  jmp     short loc_180008B44
```
