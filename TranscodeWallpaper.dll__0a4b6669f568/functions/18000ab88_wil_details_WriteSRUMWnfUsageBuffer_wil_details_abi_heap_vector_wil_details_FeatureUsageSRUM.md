# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000ab88`
- end: `0x18000adc0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180007100`

## callees

- `0x180002170`
- `0x180002cb4`
- `0x18000ab88`
- `0x18000adc8`
- `0x18000dd00`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ac28`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ac28`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ac11`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ac11`

## string_xrefs

- `0x18000ac0a`: `ntdll.dll`

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
0x18000ab88  push    rbp
0x18000ab8a  push    rbx
0x18000ab8b  push    rsi
0x18000ab8c  push    rdi
0x18000ab8d  push    r14
0x18000ab8f  push    r15
0x18000ab91  lea     rbp, [rsp-0F68h]
0x18000ab99  mov     eax, 1068h
0x18000ab9e  call    _alloca_probe
0x18000aba3  sub     rsp, rax
0x18000aba6  mov     rax, cs:__security_cookie
0x18000abad  xor     rax, rsp
0x18000abb0  mov     [rbp+0F90h+var_40], rax
0x18000abb7  mov     rax, [rcx+8]
0x18000abbb  xor     ebx, ebx
0x18000abbd  sub     rax, [rcx]
0x18000abc0  xor     esi, esi
0x18000abc2  mov     r14, rcx
0x18000abc5  cmp     rax, 0Ch
0x18000abc9  jb      loc_18000AD8C
0x18000abcf  xor     r15d, r15d
0x18000abd2  xor     edx, edx; Val
0x18000abd4  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000abd9  mov     r8d, 1000h; Size
0x18000abdf  call    memset_0
0x18000abe4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000abec  mov     [rsp+1090h+var_1050], 1000h
0x18000abf4  mov     [rsp+1090h+var_104C], 0
0x18000abfc  jnz     short loc_18000AC46
0x18000abfe  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ac05  test    rax, rax
0x18000ac08  jnz     short loc_18000AC1E
0x18000ac0a  lea     rcx, ModuleName; "ntdll.dll"
0x18000ac11  call    cs:__imp_GetModuleHandleW
0x18000ac17  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ac1e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000ac25  mov     rcx, rax; hModule
0x18000ac28  call    cs:__imp_GetProcAddress
0x18000ac2e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000ac35  test    rax, rax
0x18000ac38  jnz     short loc_18000AC46
0x18000ac3a  mov     edi, 0C0000139h
0x18000ac3f  mov     ebx, edi
0x18000ac41  jmp     loc_18000AD73
0x18000ac46  lea     rax, [rsp+1090h+var_1050]
0x18000ac4b  xor     r8d, r8d
0x18000ac4e  mov     [rsp+1090h+var_1068], rax
0x18000ac53  lea     r9, [rsp+1090h+var_104C]
0x18000ac58  lea     rax, [rsp+1090h+var_1040]
0x18000ac5d  xor     edx, edx
0x18000ac5f  mov     [rsp+1090h+var_1070], rax
0x18000ac64  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ac6b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000ac72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ac77  mov     ebx, eax
0x18000ac79  mov     edi, eax
0x18000ac7b  test    eax, eax
0x18000ac7d  jnz     loc_18000AD73
0x18000ac83  mov     r9d, [rsp+1090h+var_1050]
0x18000ac88  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000ac92  mov     rax, r11
0x18000ac95  mul     r9
0x18000ac98  shr     rdx, 3
0x18000ac9c  lea     rcx, [rdx+rdx*2]
0x18000aca0  shl     rcx, 2
0x18000aca4  cmp     r9, rcx
0x18000aca7  jz      short loc_18000ACB1
0x18000aca9  xor     r9d, r9d
0x18000acac  mov     [rsp+1090h+var_1050], r9d
0x18000acb1  mov     r8, [r14]
0x18000acb4  mov     rax, r11
0x18000acb7  mov     ecx, r9d
0x18000acba  mul     rcx
0x18000acbd  mov     rcx, [r14+8]
0x18000acc1  mov     rax, r11
0x18000acc4  mov     r10, rdx
0x18000acc7  sub     rcx, r8
0x18000acca  mul     rcx
0x18000accd  shr     r10, 3
0x18000acd1  shr     rdx, 3
0x18000acd5  lea     rax, [rdx+rdx*2]
0x18000acd9  lea     rsi, [r8+rax*4]
0x18000acdd  jmp     short loc_18000AD48
0x18000acdf  mov     eax, r10d
0x18000ace2  lea     rcx, [rax+rax*2]
0x18000ace6  lea     rdx, [rdx+rcx*4]
0x18000acea  lea     rax, [rsp+1090h+var_1040]
0x18000acef  cmp     rax, rdx
0x18000acf2  jz      short loc_18000AD19
0x18000acf4  mov     r11d, [r8]
0x18000acf7  lea     rcx, [rsp+1090h+var_1040]
0x18000acfc  cmp     [rcx], r11d
0x18000acff  jnz     short loc_18000AD10
0x18000ad01  movzx   eax, word ptr [r8+4]
0x18000ad06  cmp     [rcx+4], ax
0x18000ad0a  jz      loc_18000ADB2
0x18000ad10  add     rcx, 0Ch
0x18000ad14  cmp     rcx, rdx
0x18000ad17  jnz     short loc_18000ACFC
0x18000ad19  mov     eax, r9d
0x18000ad1c  add     rax, 0Ch
0x18000ad20  cmp     rax, 1000h
0x18000ad26  ja      short loc_18000AD44
0x18000ad28  movsd   xmm0, qword ptr [r8]
0x18000ad2d  add     r9d, 0Ch
0x18000ad31  movsd   qword ptr [rdx], xmm0
0x18000ad35  inc     r10d
0x18000ad38  mov     eax, [r8+8]
0x18000ad3c  mov     [rdx+8], eax
0x18000ad3f  mov     [rsp+1090h+var_1050], r9d
0x18000ad44  add     r8, 0Ch
0x18000ad48  lea     rdx, [rsp+1090h+var_1040]
0x18000ad4d  cmp     r8, rsi
0x18000ad50  jnz     short loc_18000ACDF
0x18000ad52  mov     eax, [rsp+1090h+var_104C]
0x18000ad56  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ad5d  mov     [rsp+1090h+var_1060], 1
0x18000ad65  mov     r8d, r9d
0x18000ad68  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000ad6c  call    wil_details_NtUpdateWnfStateData
0x18000ad71  mov     esi, eax
0x18000ad73  cmp     esi, 0C0000001h
0x18000ad79  jnz     short loc_18000AD8C
0x18000ad7b  inc     r15d
0x18000ad7e  cmp     r15d, 64h ; 'd'
0x18000ad82  jge     short loc_18000AD8C
0x18000ad84  test    edi, edi
0x18000ad86  jz      loc_18000ABD2
0x18000ad8c  test    ebx, ebx
0x18000ad8e  cmovz   ebx, esi
0x18000ad91  mov     eax, ebx
0x18000ad93  mov     rcx, [rbp+0F90h+var_40]
0x18000ad9a  xor     rcx, rsp; StackCookie
0x18000ad9d  call    __security_check_cookie
0x18000ada2  add     rsp, 1068h
0x18000ada9  pop     r15
0x18000adab  pop     r14
0x18000adad  pop     rdi
0x18000adae  pop     rsi
0x18000adaf  pop     rbx
0x18000adb0  pop     rbp
0x18000adb1  retn
0x18000adb2  mov     eax, [r8+8]
0x18000adb6  add     [rcx+8], eax
0x18000adb9  mov     r9d, [rsp+1090h+var_1050]
0x18000adbe  jmp     short loc_18000AD44
```
