# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000b0a0`
- end: `0x18000b2d8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180007660`

## callees

- `0x18000b0a0`
- `0x18000b45c`
- `0x18000b612`
- `0x18000b640`
- `0x18000b700`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b140`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b140`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b129`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b129`

## string_xrefs

- `0x18000b122`: `ntdll.dll`

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
0x18000b0a0  push    rbp
0x18000b0a2  push    rbx
0x18000b0a3  push    rsi
0x18000b0a4  push    rdi
0x18000b0a5  push    r14
0x18000b0a7  push    r15
0x18000b0a9  lea     rbp, [rsp-0F68h]
0x18000b0b1  mov     eax, 1068h
0x18000b0b6  call    _alloca_probe
0x18000b0bb  sub     rsp, rax
0x18000b0be  mov     rax, cs:__security_cookie
0x18000b0c5  xor     rax, rsp
0x18000b0c8  mov     [rbp+0F90h+var_40], rax
0x18000b0cf  mov     rax, [rcx+8]
0x18000b0d3  xor     ebx, ebx
0x18000b0d5  sub     rax, [rcx]
0x18000b0d8  xor     esi, esi
0x18000b0da  mov     r14, rcx
0x18000b0dd  cmp     rax, 0Ch
0x18000b0e1  jb      loc_18000B2A4
0x18000b0e7  xor     r15d, r15d
0x18000b0ea  xor     edx, edx; Val
0x18000b0ec  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000b0f1  mov     r8d, 1000h; Size
0x18000b0f7  call    memset_0
0x18000b0fc  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000b104  mov     [rsp+1090h+var_1050], 1000h
0x18000b10c  mov     [rsp+1090h+var_104C], 0
0x18000b114  jnz     short loc_18000B15E
0x18000b116  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b11d  test    rax, rax
0x18000b120  jnz     short loc_18000B136
0x18000b122  lea     rcx, ModuleName; "ntdll.dll"
0x18000b129  call    cs:__imp_GetModuleHandleW
0x18000b12f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b136  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b13d  mov     rcx, rax; hModule
0x18000b140  call    cs:__imp_GetProcAddress
0x18000b146  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b14d  test    rax, rax
0x18000b150  jnz     short loc_18000B15E
0x18000b152  mov     edi, 0C0000139h
0x18000b157  mov     ebx, edi
0x18000b159  jmp     loc_18000B28B
0x18000b15e  lea     rax, [rsp+1090h+var_1050]
0x18000b163  xor     r8d, r8d
0x18000b166  mov     [rsp+1090h+var_1068], rax
0x18000b16b  lea     r9, [rsp+1090h+var_104C]
0x18000b170  lea     rax, [rsp+1090h+var_1040]
0x18000b175  xor     edx, edx
0x18000b177  mov     [rsp+1090h+var_1070], rax
0x18000b17c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b183  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b18a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b18f  mov     ebx, eax
0x18000b191  mov     edi, eax
0x18000b193  test    eax, eax
0x18000b195  jnz     loc_18000B28B
0x18000b19b  mov     r9d, [rsp+1090h+var_1050]
0x18000b1a0  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000b1aa  mov     rax, r11
0x18000b1ad  mul     r9
0x18000b1b0  shr     rdx, 3
0x18000b1b4  lea     rcx, [rdx+rdx*2]
0x18000b1b8  shl     rcx, 2
0x18000b1bc  cmp     r9, rcx
0x18000b1bf  jz      short loc_18000B1C9
0x18000b1c1  xor     r9d, r9d
0x18000b1c4  mov     [rsp+1090h+var_1050], r9d
0x18000b1c9  mov     r8, [r14]
0x18000b1cc  mov     rax, r11
0x18000b1cf  mov     ecx, r9d
0x18000b1d2  mul     rcx
0x18000b1d5  mov     rcx, [r14+8]
0x18000b1d9  mov     rax, r11
0x18000b1dc  mov     r10, rdx
0x18000b1df  sub     rcx, r8
0x18000b1e2  mul     rcx
0x18000b1e5  shr     r10, 3
0x18000b1e9  shr     rdx, 3
0x18000b1ed  lea     rax, [rdx+rdx*2]
0x18000b1f1  lea     rsi, [r8+rax*4]
0x18000b1f5  jmp     short loc_18000B260
0x18000b1f7  mov     eax, r10d
0x18000b1fa  lea     rcx, [rax+rax*2]
0x18000b1fe  lea     rdx, [rdx+rcx*4]
0x18000b202  lea     rax, [rsp+1090h+var_1040]
0x18000b207  cmp     rax, rdx
0x18000b20a  jz      short loc_18000B231
0x18000b20c  mov     r11d, [r8]
0x18000b20f  lea     rcx, [rsp+1090h+var_1040]
0x18000b214  cmp     [rcx], r11d
0x18000b217  jnz     short loc_18000B228
0x18000b219  movzx   eax, word ptr [r8+4]
0x18000b21e  cmp     [rcx+4], ax
0x18000b222  jz      loc_18000B2CA
0x18000b228  add     rcx, 0Ch
0x18000b22c  cmp     rcx, rdx
0x18000b22f  jnz     short loc_18000B214
0x18000b231  mov     eax, r9d
0x18000b234  add     rax, 0Ch
0x18000b238  cmp     rax, 1000h
0x18000b23e  ja      short loc_18000B25C
0x18000b240  movsd   xmm0, qword ptr [r8]
0x18000b245  add     r9d, 0Ch
0x18000b249  movsd   qword ptr [rdx], xmm0
0x18000b24d  inc     r10d
0x18000b250  mov     eax, [r8+8]
0x18000b254  mov     [rdx+8], eax
0x18000b257  mov     [rsp+1090h+var_1050], r9d
0x18000b25c  add     r8, 0Ch
0x18000b260  lea     rdx, [rsp+1090h+var_1040]
0x18000b265  cmp     r8, rsi
0x18000b268  jnz     short loc_18000B1F7
0x18000b26a  mov     eax, [rsp+1090h+var_104C]
0x18000b26e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b275  mov     [rsp+1090h+var_1060], 1
0x18000b27d  mov     r8d, r9d
0x18000b280  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000b284  call    wil_details_NtUpdateWnfStateData
0x18000b289  mov     esi, eax
0x18000b28b  cmp     esi, 0C0000001h
0x18000b291  jnz     short loc_18000B2A4
0x18000b293  inc     r15d
0x18000b296  cmp     r15d, 64h ; 'd'
0x18000b29a  jge     short loc_18000B2A4
0x18000b29c  test    edi, edi
0x18000b29e  jz      loc_18000B0EA
0x18000b2a4  test    ebx, ebx
0x18000b2a6  cmovz   ebx, esi
0x18000b2a9  mov     eax, ebx
0x18000b2ab  mov     rcx, [rbp+0F90h+var_40]
0x18000b2b2  xor     rcx, rsp; StackCookie
0x18000b2b5  call    __security_check_cookie
0x18000b2ba  add     rsp, 1068h
0x18000b2c1  pop     r15
0x18000b2c3  pop     r14
0x18000b2c5  pop     rdi
0x18000b2c6  pop     rsi
0x18000b2c7  pop     rbx
0x18000b2c8  pop     rbp
0x18000b2c9  retn
0x18000b2ca  mov     eax, [r8+8]
0x18000b2ce  add     [rcx+8], eax
0x18000b2d1  mov     r9d, [rsp+1090h+var_1050]
0x18000b2d6  jmp     short loc_18000B25C
```
