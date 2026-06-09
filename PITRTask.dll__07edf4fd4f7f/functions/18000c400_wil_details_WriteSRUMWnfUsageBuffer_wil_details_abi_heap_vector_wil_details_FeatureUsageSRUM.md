# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000c400`
- end: `0x18000c638`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002410`

## callees

- `0x18000c400`
- `0x18000cdd0`
- `0x180010792`
- `0x1800107c0`
- `0x180010880`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c4a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000c4a0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c489`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000c489`

## string_xrefs

- `0x18000c482`: `ntdll.dll`

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
0x18000c400  push    rbp
0x18000c402  push    rbx
0x18000c403  push    rsi
0x18000c404  push    rdi
0x18000c405  push    r14
0x18000c407  push    r15
0x18000c409  lea     rbp, [rsp-0F68h]
0x18000c411  mov     eax, 1068h
0x18000c416  call    _alloca_probe
0x18000c41b  sub     rsp, rax
0x18000c41e  mov     rax, cs:__security_cookie
0x18000c425  xor     rax, rsp
0x18000c428  mov     [rbp+0F90h+var_40], rax
0x18000c42f  mov     rax, [rcx+8]
0x18000c433  xor     ebx, ebx
0x18000c435  sub     rax, [rcx]
0x18000c438  xor     esi, esi
0x18000c43a  mov     r14, rcx
0x18000c43d  cmp     rax, 0Ch
0x18000c441  jb      loc_18000C604
0x18000c447  xor     r15d, r15d
0x18000c44a  xor     edx, edx; Val
0x18000c44c  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000c451  mov     r8d, 1000h; Size
0x18000c457  call    memset_0
0x18000c45c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000c464  mov     [rsp+1090h+var_1050], 1000h
0x18000c46c  mov     [rsp+1090h+var_104C], 0
0x18000c474  jnz     short loc_18000C4BE
0x18000c476  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c47d  test    rax, rax
0x18000c480  jnz     short loc_18000C496
0x18000c482  lea     rcx, ModuleName; "ntdll.dll"
0x18000c489  call    cs:__imp_GetModuleHandleW
0x18000c48f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c496  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000c49d  mov     rcx, rax; hModule
0x18000c4a0  call    cs:__imp_GetProcAddress
0x18000c4a6  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000c4ad  test    rax, rax
0x18000c4b0  jnz     short loc_18000C4BE
0x18000c4b2  mov     edi, 0C0000139h
0x18000c4b7  mov     ebx, edi
0x18000c4b9  jmp     loc_18000C5EB
0x18000c4be  lea     rax, [rsp+1090h+var_1050]
0x18000c4c3  xor     r8d, r8d
0x18000c4c6  mov     [rsp+1090h+var_1068], rax
0x18000c4cb  lea     r9, [rsp+1090h+var_104C]
0x18000c4d0  lea     rax, [rsp+1090h+var_1040]
0x18000c4d5  xor     edx, edx
0x18000c4d7  mov     [rsp+1090h+var_1070], rax
0x18000c4dc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000c4e3  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000c4ea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c4ef  mov     ebx, eax
0x18000c4f1  mov     edi, eax
0x18000c4f3  test    eax, eax
0x18000c4f5  jnz     loc_18000C5EB
0x18000c4fb  mov     r9d, [rsp+1090h+var_1050]
0x18000c500  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000c50a  mov     rax, r11
0x18000c50d  mul     r9
0x18000c510  shr     rdx, 3
0x18000c514  lea     rcx, [rdx+rdx*2]
0x18000c518  shl     rcx, 2
0x18000c51c  cmp     r9, rcx
0x18000c51f  jz      short loc_18000C529
0x18000c521  xor     r9d, r9d
0x18000c524  mov     [rsp+1090h+var_1050], r9d
0x18000c529  mov     r8, [r14]
0x18000c52c  mov     rax, r11
0x18000c52f  mov     ecx, r9d
0x18000c532  mul     rcx
0x18000c535  mov     rcx, [r14+8]
0x18000c539  mov     rax, r11
0x18000c53c  mov     r10, rdx
0x18000c53f  sub     rcx, r8
0x18000c542  mul     rcx
0x18000c545  shr     r10, 3
0x18000c549  shr     rdx, 3
0x18000c54d  lea     rax, [rdx+rdx*2]
0x18000c551  lea     rsi, [r8+rax*4]
0x18000c555  jmp     short loc_18000C5C0
0x18000c557  mov     eax, r10d
0x18000c55a  lea     rcx, [rax+rax*2]
0x18000c55e  lea     rdx, [rdx+rcx*4]
0x18000c562  lea     rax, [rsp+1090h+var_1040]
0x18000c567  cmp     rax, rdx
0x18000c56a  jz      short loc_18000C591
0x18000c56c  mov     r11d, [r8]
0x18000c56f  lea     rcx, [rsp+1090h+var_1040]
0x18000c574  cmp     [rcx], r11d
0x18000c577  jnz     short loc_18000C588
0x18000c579  movzx   eax, word ptr [r8+4]
0x18000c57e  cmp     [rcx+4], ax
0x18000c582  jz      loc_18000C62A
0x18000c588  add     rcx, 0Ch
0x18000c58c  cmp     rcx, rdx
0x18000c58f  jnz     short loc_18000C574
0x18000c591  mov     eax, r9d
0x18000c594  add     rax, 0Ch
0x18000c598  cmp     rax, 1000h
0x18000c59e  ja      short loc_18000C5BC
0x18000c5a0  movsd   xmm0, qword ptr [r8]
0x18000c5a5  add     r9d, 0Ch
0x18000c5a9  movsd   qword ptr [rdx], xmm0
0x18000c5ad  inc     r10d
0x18000c5b0  mov     eax, [r8+8]
0x18000c5b4  mov     [rdx+8], eax
0x18000c5b7  mov     [rsp+1090h+var_1050], r9d
0x18000c5bc  add     r8, 0Ch
0x18000c5c0  lea     rdx, [rsp+1090h+var_1040]
0x18000c5c5  cmp     r8, rsi
0x18000c5c8  jnz     short loc_18000C557
0x18000c5ca  mov     eax, [rsp+1090h+var_104C]
0x18000c5ce  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000c5d5  mov     [rsp+1090h+var_1060], 1
0x18000c5dd  mov     r8d, r9d
0x18000c5e0  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000c5e4  call    wil_details_NtUpdateWnfStateData
0x18000c5e9  mov     esi, eax
0x18000c5eb  cmp     esi, 0C0000001h
0x18000c5f1  jnz     short loc_18000C604
0x18000c5f3  inc     r15d
0x18000c5f6  cmp     r15d, 64h ; 'd'
0x18000c5fa  jge     short loc_18000C604
0x18000c5fc  test    edi, edi
0x18000c5fe  jz      loc_18000C44A
0x18000c604  test    ebx, ebx
0x18000c606  cmovz   ebx, esi
0x18000c609  mov     eax, ebx
0x18000c60b  mov     rcx, [rbp+0F90h+var_40]
0x18000c612  xor     rcx, rsp; StackCookie
0x18000c615  call    __security_check_cookie
0x18000c61a  add     rsp, 1068h
0x18000c621  pop     r15
0x18000c623  pop     r14
0x18000c625  pop     rdi
0x18000c626  pop     rsi
0x18000c627  pop     rbx
0x18000c628  pop     rbp
0x18000c629  retn
0x18000c62a  mov     eax, [r8+8]
0x18000c62e  add     [rcx+8], eax
0x18000c631  mov     r9d, [rsp+1090h+var_1050]
0x18000c636  jmp     short loc_18000C5BC
```
