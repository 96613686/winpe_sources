# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000b684`
- end: `0x18000b8bc`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800083a0`

## callees

- `0x180002250`
- `0x180002cf8`
- `0x18000b684`
- `0x18000bad0`
- `0x1800c6e30`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b70d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b70d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b724`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b724`

## string_xrefs

- `0x18000b706`: `ntdll.dll`

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
0x18000b684  push    rbp
0x18000b686  push    rbx
0x18000b687  push    rsi
0x18000b688  push    rdi
0x18000b689  push    r14
0x18000b68b  push    r15
0x18000b68d  lea     rbp, [rsp-0F68h]
0x18000b695  mov     eax, 1068h
0x18000b69a  call    _alloca_probe
0x18000b69f  sub     rsp, rax
0x18000b6a2  mov     rax, cs:__security_cookie
0x18000b6a9  xor     rax, rsp
0x18000b6ac  mov     [rbp+0F90h+var_40], rax
0x18000b6b3  mov     rax, [rcx+8]
0x18000b6b7  xor     ebx, ebx
0x18000b6b9  sub     rax, [rcx]
0x18000b6bc  xor     esi, esi
0x18000b6be  mov     r14, rcx
0x18000b6c1  cmp     rax, 0Ch
0x18000b6c5  jb      loc_18000B888
0x18000b6cb  xor     r15d, r15d
0x18000b6ce  xor     edx, edx; Val
0x18000b6d0  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000b6d5  mov     r8d, 1000h; Size
0x18000b6db  call    memset_0
0x18000b6e0  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000b6e8  mov     [rsp+1090h+var_1050], 1000h
0x18000b6f0  mov     [rsp+1090h+var_104C], 0
0x18000b6f8  jnz     short loc_18000B742
0x18000b6fa  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b701  test    rax, rax
0x18000b704  jnz     short loc_18000B71A
0x18000b706  lea     rcx, ModuleName; "ntdll.dll"
0x18000b70d  call    cs:__imp_GetModuleHandleW
0x18000b713  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b71a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b721  mov     rcx, rax; hModule
0x18000b724  call    cs:__imp_GetProcAddress
0x18000b72a  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b731  test    rax, rax
0x18000b734  jnz     short loc_18000B742
0x18000b736  mov     edi, 0C0000139h
0x18000b73b  mov     ebx, edi
0x18000b73d  jmp     loc_18000B86F
0x18000b742  lea     rax, [rsp+1090h+var_1050]
0x18000b747  xor     r8d, r8d
0x18000b74a  mov     [rsp+1090h+var_1068], rax
0x18000b74f  lea     r9, [rsp+1090h+var_104C]
0x18000b754  lea     rax, [rsp+1090h+var_1040]
0x18000b759  xor     edx, edx
0x18000b75b  mov     [rsp+1090h+var_1070], rax
0x18000b760  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b767  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b76e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b773  mov     ebx, eax
0x18000b775  mov     edi, eax
0x18000b777  test    eax, eax
0x18000b779  jnz     loc_18000B86F
0x18000b77f  mov     r9d, [rsp+1090h+var_1050]
0x18000b784  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000b78e  mov     rax, r11
0x18000b791  mul     r9
0x18000b794  shr     rdx, 3
0x18000b798  lea     rcx, [rdx+rdx*2]
0x18000b79c  shl     rcx, 2
0x18000b7a0  cmp     r9, rcx
0x18000b7a3  jz      short loc_18000B7AD
0x18000b7a5  xor     r9d, r9d
0x18000b7a8  mov     [rsp+1090h+var_1050], r9d
0x18000b7ad  mov     r8, [r14]
0x18000b7b0  mov     rax, r11
0x18000b7b3  mov     ecx, r9d
0x18000b7b6  mul     rcx
0x18000b7b9  mov     rcx, [r14+8]
0x18000b7bd  mov     rax, r11
0x18000b7c0  mov     r10, rdx
0x18000b7c3  sub     rcx, r8
0x18000b7c6  mul     rcx
0x18000b7c9  shr     r10, 3
0x18000b7cd  shr     rdx, 3
0x18000b7d1  lea     rax, [rdx+rdx*2]
0x18000b7d5  lea     rsi, [r8+rax*4]
0x18000b7d9  jmp     short loc_18000B844
0x18000b7db  mov     eax, r10d
0x18000b7de  lea     rcx, [rax+rax*2]
0x18000b7e2  lea     rdx, [rdx+rcx*4]
0x18000b7e6  lea     rax, [rsp+1090h+var_1040]
0x18000b7eb  cmp     rax, rdx
0x18000b7ee  jz      short loc_18000B815
0x18000b7f0  mov     r11d, [r8]
0x18000b7f3  lea     rcx, [rsp+1090h+var_1040]
0x18000b7f8  cmp     [rcx], r11d
0x18000b7fb  jnz     short loc_18000B80C
0x18000b7fd  movzx   eax, word ptr [r8+4]
0x18000b802  cmp     [rcx+4], ax
0x18000b806  jz      loc_18000B8AE
0x18000b80c  add     rcx, 0Ch
0x18000b810  cmp     rcx, rdx
0x18000b813  jnz     short loc_18000B7F8
0x18000b815  mov     eax, r9d
0x18000b818  add     rax, 0Ch
0x18000b81c  cmp     rax, 1000h
0x18000b822  ja      short loc_18000B840
0x18000b824  movsd   xmm0, qword ptr [r8]
0x18000b829  add     r9d, 0Ch
0x18000b82d  movsd   qword ptr [rdx], xmm0
0x18000b831  inc     r10d
0x18000b834  mov     eax, [r8+8]
0x18000b838  mov     [rdx+8], eax
0x18000b83b  mov     [rsp+1090h+var_1050], r9d
0x18000b840  add     r8, 0Ch
0x18000b844  lea     rdx, [rsp+1090h+var_1040]
0x18000b849  cmp     r8, rsi
0x18000b84c  jnz     short loc_18000B7DB
0x18000b84e  mov     eax, [rsp+1090h+var_104C]
0x18000b852  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b859  mov     [rsp+1090h+var_1060], 1
0x18000b861  mov     r8d, r9d
0x18000b864  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000b868  call    wil_details_NtUpdateWnfStateData
0x18000b86d  mov     esi, eax
0x18000b86f  cmp     esi, 0C0000001h
0x18000b875  jnz     short loc_18000B888
0x18000b877  inc     r15d
0x18000b87a  cmp     r15d, 64h ; 'd'
0x18000b87e  jge     short loc_18000B888
0x18000b880  test    edi, edi
0x18000b882  jz      loc_18000B6CE
0x18000b888  test    ebx, ebx
0x18000b88a  cmovz   ebx, esi
0x18000b88d  mov     eax, ebx
0x18000b88f  mov     rcx, [rbp+0F90h+var_40]
0x18000b896  xor     rcx, rsp; StackCookie
0x18000b899  call    __security_check_cookie
0x18000b89e  add     rsp, 1068h
0x18000b8a5  pop     r15
0x18000b8a7  pop     r14
0x18000b8a9  pop     rdi
0x18000b8aa  pop     rsi
0x18000b8ab  pop     rbx
0x18000b8ac  pop     rbp
0x18000b8ad  retn
0x18000b8ae  mov     eax, [r8+8]
0x18000b8b2  add     [rcx+8], eax
0x18000b8b5  mov     r9d, [rsp+1090h+var_1050]
0x18000b8ba  jmp     short loc_18000B840
```
