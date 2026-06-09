# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800163a0`
- end: `0x1800165d8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800107c0`

## callees

- `0x1800163a0`
- `0x180016ab0`
- `0x18001972e`
- `0x180019760`
- `0x180019820`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016440`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180016440`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016429`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180016429`

## string_xrefs

- `0x180016422`: `ntdll.dll`

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
0x1800163a0  push    rbp
0x1800163a2  push    rbx
0x1800163a3  push    rsi
0x1800163a4  push    rdi
0x1800163a5  push    r14
0x1800163a7  push    r15
0x1800163a9  lea     rbp, [rsp-0F68h]
0x1800163b1  mov     eax, 1068h
0x1800163b6  call    _alloca_probe
0x1800163bb  sub     rsp, rax
0x1800163be  mov     rax, cs:__security_cookie
0x1800163c5  xor     rax, rsp
0x1800163c8  mov     [rbp+0F90h+var_40], rax
0x1800163cf  mov     rax, [rcx+8]
0x1800163d3  xor     ebx, ebx
0x1800163d5  sub     rax, [rcx]
0x1800163d8  xor     esi, esi
0x1800163da  mov     r14, rcx
0x1800163dd  cmp     rax, 0Ch
0x1800163e1  jb      loc_1800165A4
0x1800163e7  xor     r15d, r15d
0x1800163ea  xor     edx, edx; Val
0x1800163ec  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800163f1  mov     r8d, 1000h; Size
0x1800163f7  call    memset_0
0x1800163fc  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180016404  mov     [rsp+1090h+var_1050], 1000h
0x18001640c  mov     [rsp+1090h+var_104C], 0
0x180016414  jnz     short loc_18001645E
0x180016416  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001641d  test    rax, rax
0x180016420  jnz     short loc_180016436
0x180016422  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180016429  call    cs:__imp_GetModuleHandleW
0x18001642f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180016436  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18001643d  mov     rcx, rax; hModule
0x180016440  call    cs:__imp_GetProcAddress
0x180016446  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18001644d  test    rax, rax
0x180016450  jnz     short loc_18001645E
0x180016452  mov     edi, 0C0000139h
0x180016457  mov     ebx, edi
0x180016459  jmp     loc_18001658B
0x18001645e  lea     rax, [rsp+1090h+var_1050]
0x180016463  xor     r8d, r8d
0x180016466  mov     [rsp+1090h+var_1068], rax
0x18001646b  lea     r9, [rsp+1090h+var_104C]
0x180016470  lea     rax, [rsp+1090h+var_1040]
0x180016475  xor     edx, edx
0x180016477  mov     [rsp+1090h+var_1070], rax
0x18001647c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180016483  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18001648a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001648f  mov     ebx, eax
0x180016491  mov     edi, eax
0x180016493  test    eax, eax
0x180016495  jnz     loc_18001658B
0x18001649b  mov     r9d, [rsp+1090h+var_1050]
0x1800164a0  mov     r11, 0AAAAAAAAAAAAAAABh
0x1800164aa  mov     rax, r11
0x1800164ad  mul     r9
0x1800164b0  shr     rdx, 3
0x1800164b4  lea     rcx, [rdx+rdx*2]
0x1800164b8  shl     rcx, 2
0x1800164bc  cmp     r9, rcx
0x1800164bf  jz      short loc_1800164C9
0x1800164c1  xor     r9d, r9d
0x1800164c4  mov     [rsp+1090h+var_1050], r9d
0x1800164c9  mov     r8, [r14]
0x1800164cc  mov     rax, r11
0x1800164cf  mov     ecx, r9d
0x1800164d2  mul     rcx
0x1800164d5  mov     rcx, [r14+8]
0x1800164d9  mov     rax, r11
0x1800164dc  mov     r10, rdx
0x1800164df  sub     rcx, r8
0x1800164e2  mul     rcx
0x1800164e5  shr     r10, 3
0x1800164e9  shr     rdx, 3
0x1800164ed  lea     rax, [rdx+rdx*2]
0x1800164f1  lea     rsi, [r8+rax*4]
0x1800164f5  jmp     short loc_180016560
0x1800164f7  mov     eax, r10d
0x1800164fa  lea     rcx, [rax+rax*2]
0x1800164fe  lea     rdx, [rdx+rcx*4]
0x180016502  lea     rax, [rsp+1090h+var_1040]
0x180016507  cmp     rax, rdx
0x18001650a  jz      short loc_180016531
0x18001650c  mov     r11d, [r8]
0x18001650f  lea     rcx, [rsp+1090h+var_1040]
0x180016514  cmp     [rcx], r11d
0x180016517  jnz     short loc_180016528
0x180016519  movzx   eax, word ptr [r8+4]
0x18001651e  cmp     [rcx+4], ax
0x180016522  jz      loc_1800165CA
0x180016528  add     rcx, 0Ch
0x18001652c  cmp     rcx, rdx
0x18001652f  jnz     short loc_180016514
0x180016531  mov     eax, r9d
0x180016534  add     rax, 0Ch
0x180016538  cmp     rax, 1000h
0x18001653e  ja      short loc_18001655C
0x180016540  movsd   xmm0, qword ptr [r8]
0x180016545  add     r9d, 0Ch
0x180016549  movsd   qword ptr [rdx], xmm0
0x18001654d  inc     r10d
0x180016550  mov     eax, [r8+8]
0x180016554  mov     [rdx+8], eax
0x180016557  mov     [rsp+1090h+var_1050], r9d
0x18001655c  add     r8, 0Ch
0x180016560  lea     rdx, [rsp+1090h+var_1040]
0x180016565  cmp     r8, rsi
0x180016568  jnz     short loc_1800164F7
0x18001656a  mov     eax, [rsp+1090h+var_104C]
0x18001656e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180016575  mov     [rsp+1090h+var_1060], 1
0x18001657d  mov     r8d, r9d
0x180016580  mov     dword ptr [rsp+1090h+var_1068], eax
0x180016584  call    wil_details_NtUpdateWnfStateData
0x180016589  mov     esi, eax
0x18001658b  cmp     esi, 0C0000001h
0x180016591  jnz     short loc_1800165A4
0x180016593  inc     r15d
0x180016596  cmp     r15d, 64h ; 'd'
0x18001659a  jge     short loc_1800165A4
0x18001659c  test    edi, edi
0x18001659e  jz      loc_1800163EA
0x1800165a4  test    ebx, ebx
0x1800165a6  cmovz   ebx, esi
0x1800165a9  mov     eax, ebx
0x1800165ab  mov     rcx, [rbp+0F90h+var_40]
0x1800165b2  xor     rcx, rsp; StackCookie
0x1800165b5  call    __security_check_cookie
0x1800165ba  add     rsp, 1068h
0x1800165c1  pop     r15
0x1800165c3  pop     r14
0x1800165c5  pop     rdi
0x1800165c6  pop     rsi
0x1800165c7  pop     rbx
0x1800165c8  pop     rbp
0x1800165c9  retn
0x1800165ca  mov     eax, [r8+8]
0x1800165ce  add     [rcx+8], eax
0x1800165d1  mov     r9d, [rsp+1090h+var_1050]
0x1800165d6  jmp     short loc_18001655C
```
