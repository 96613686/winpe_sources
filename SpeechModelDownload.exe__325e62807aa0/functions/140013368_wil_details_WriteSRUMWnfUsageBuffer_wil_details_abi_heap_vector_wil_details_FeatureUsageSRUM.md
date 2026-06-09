# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140013368`
- end: `0x1400135a0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14000a0d0`

## callees

- `0x140002600`
- `0x1400030dc`
- `0x140013368`
- `0x1400137a0`
- `0x14001bb30`
- `0x14001d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400133f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1400133f1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140013408`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140013408`

## string_xrefs

- `0x1400133ea`: `ntdll.dll`

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
0x140013368  push    rbp
0x14001336a  push    rbx
0x14001336b  push    rsi
0x14001336c  push    rdi
0x14001336d  push    r14
0x14001336f  push    r15
0x140013371  lea     rbp, [rsp-0F68h]
0x140013379  mov     eax, 1068h
0x14001337e  call    _alloca_probe
0x140013383  sub     rsp, rax
0x140013386  mov     rax, cs:__security_cookie
0x14001338d  xor     rax, rsp
0x140013390  mov     [rbp+0F90h+var_40], rax
0x140013397  mov     rax, [rcx+8]
0x14001339b  xor     ebx, ebx
0x14001339d  sub     rax, [rcx]
0x1400133a0  xor     esi, esi
0x1400133a2  mov     r14, rcx
0x1400133a5  cmp     rax, 0Ch
0x1400133a9  jb      loc_14001356C
0x1400133af  xor     r15d, r15d
0x1400133b2  xor     edx, edx; Val
0x1400133b4  lea     rcx, [rsp+1090h+var_1040]; void *
0x1400133b9  mov     r8d, 1000h; Size
0x1400133bf  call    memset_0
0x1400133c4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1400133cc  mov     [rsp+1090h+var_1050], 1000h
0x1400133d4  mov     [rsp+1090h+var_104C], 0
0x1400133dc  jnz     short loc_140013426
0x1400133de  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400133e5  test    rax, rax
0x1400133e8  jnz     short loc_1400133FE
0x1400133ea  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x1400133f1  call    cs:__imp_GetModuleHandleW
0x1400133f7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1400133fe  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140013405  mov     rcx, rax; hModule
0x140013408  call    cs:__imp_GetProcAddress
0x14001340e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140013415  test    rax, rax
0x140013418  jnz     short loc_140013426
0x14001341a  mov     edi, 0C0000139h
0x14001341f  mov     ebx, edi
0x140013421  jmp     loc_140013553
0x140013426  lea     rax, [rsp+1090h+var_1050]
0x14001342b  xor     r8d, r8d
0x14001342e  mov     [rsp+1090h+var_1068], rax
0x140013433  lea     r9, [rsp+1090h+var_104C]
0x140013438  lea     rax, [rsp+1090h+var_1040]
0x14001343d  xor     edx, edx
0x14001343f  mov     [rsp+1090h+var_1070], rax
0x140013444  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14001344b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140013452  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140013457  mov     ebx, eax
0x140013459  mov     edi, eax
0x14001345b  test    eax, eax
0x14001345d  jnz     loc_140013553
0x140013463  mov     r9d, [rsp+1090h+var_1050]
0x140013468  mov     r11, 0AAAAAAAAAAAAAAABh
0x140013472  mov     rax, r11
0x140013475  mul     r9
0x140013478  shr     rdx, 3
0x14001347c  lea     rcx, [rdx+rdx*2]
0x140013480  shl     rcx, 2
0x140013484  cmp     r9, rcx
0x140013487  jz      short loc_140013491
0x140013489  xor     r9d, r9d
0x14001348c  mov     [rsp+1090h+var_1050], r9d
0x140013491  mov     r8, [r14]
0x140013494  mov     rax, r11
0x140013497  mov     ecx, r9d
0x14001349a  mul     rcx
0x14001349d  mov     rcx, [r14+8]
0x1400134a1  mov     rax, r11
0x1400134a4  mov     r10, rdx
0x1400134a7  sub     rcx, r8
0x1400134aa  mul     rcx
0x1400134ad  shr     r10, 3
0x1400134b1  shr     rdx, 3
0x1400134b5  lea     rax, [rdx+rdx*2]
0x1400134b9  lea     rsi, [r8+rax*4]
0x1400134bd  jmp     short loc_140013528
0x1400134bf  mov     eax, r10d
0x1400134c2  lea     rcx, [rax+rax*2]
0x1400134c6  lea     rdx, [rdx+rcx*4]
0x1400134ca  lea     rax, [rsp+1090h+var_1040]
0x1400134cf  cmp     rax, rdx
0x1400134d2  jz      short loc_1400134F9
0x1400134d4  mov     r11d, [r8]
0x1400134d7  lea     rcx, [rsp+1090h+var_1040]
0x1400134dc  cmp     [rcx], r11d
0x1400134df  jnz     short loc_1400134F0
0x1400134e1  movzx   eax, word ptr [r8+4]
0x1400134e6  cmp     [rcx+4], ax
0x1400134ea  jz      loc_140013592
0x1400134f0  add     rcx, 0Ch
0x1400134f4  cmp     rcx, rdx
0x1400134f7  jnz     short loc_1400134DC
0x1400134f9  mov     eax, r9d
0x1400134fc  add     rax, 0Ch
0x140013500  cmp     rax, 1000h
0x140013506  ja      short loc_140013524
0x140013508  movsd   xmm0, qword ptr [r8]
0x14001350d  add     r9d, 0Ch
0x140013511  movsd   qword ptr [rdx], xmm0
0x140013515  inc     r10d
0x140013518  mov     eax, [r8+8]
0x14001351c  mov     [rdx+8], eax
0x14001351f  mov     [rsp+1090h+var_1050], r9d
0x140013524  add     r8, 0Ch
0x140013528  lea     rdx, [rsp+1090h+var_1040]
0x14001352d  cmp     r8, rsi
0x140013530  jnz     short loc_1400134BF
0x140013532  mov     eax, [rsp+1090h+var_104C]
0x140013536  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14001353d  mov     [rsp+1090h+var_1060], 1
0x140013545  mov     r8d, r9d
0x140013548  mov     dword ptr [rsp+1090h+var_1068], eax
0x14001354c  call    wil_details_NtUpdateWnfStateData
0x140013551  mov     esi, eax
0x140013553  cmp     esi, 0C0000001h
0x140013559  jnz     short loc_14001356C
0x14001355b  inc     r15d
0x14001355e  cmp     r15d, 64h ; 'd'
0x140013562  jge     short loc_14001356C
0x140013564  test    edi, edi
0x140013566  jz      loc_1400133B2
0x14001356c  test    ebx, ebx
0x14001356e  cmovz   ebx, esi
0x140013571  mov     eax, ebx
0x140013573  mov     rcx, [rbp+0F90h+var_40]
0x14001357a  xor     rcx, rsp; StackCookie
0x14001357d  call    __security_check_cookie
0x140013582  add     rsp, 1068h
0x140013589  pop     r15
0x14001358b  pop     r14
0x14001358d  pop     rdi
0x14001358e  pop     rsi
0x14001358f  pop     rbx
0x140013590  pop     rbp
0x140013591  retn
0x140013592  mov     eax, [r8+8]
0x140013596  add     [rcx+8], eax
0x140013599  mov     r9d, [rsp+1090h+var_1050]
0x14001359e  jmp     short loc_140013524
```
