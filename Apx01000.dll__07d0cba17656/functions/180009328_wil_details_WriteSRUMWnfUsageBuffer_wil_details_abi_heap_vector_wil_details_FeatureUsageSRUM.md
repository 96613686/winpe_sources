# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180009328`
- end: `0x180009560`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800028a0`

## callees

- `0x180001d30`
- `0x1800027c8`
- `0x180009328`
- `0x1800097f0`
- `0x180029820`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800093b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800093b1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800093c8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800093c8`

## string_xrefs

- `0x1800093aa`: `ntdll.dll`

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
0x180009328  push    rbp
0x18000932a  push    rbx
0x18000932b  push    rsi
0x18000932c  push    rdi
0x18000932d  push    r14
0x18000932f  push    r15
0x180009331  lea     rbp, [rsp-0F68h]
0x180009339  mov     eax, 1068h
0x18000933e  call    _alloca_probe
0x180009343  sub     rsp, rax
0x180009346  mov     rax, cs:__security_cookie
0x18000934d  xor     rax, rsp
0x180009350  mov     [rbp+0F90h+var_40], rax
0x180009357  mov     rax, [rcx+8]
0x18000935b  xor     ebx, ebx
0x18000935d  sub     rax, [rcx]
0x180009360  xor     esi, esi
0x180009362  mov     r14, rcx
0x180009365  cmp     rax, 0Ch
0x180009369  jb      loc_18000952C
0x18000936f  xor     r15d, r15d
0x180009372  xor     edx, edx; Val
0x180009374  lea     rcx, [rsp+1090h+var_1040]; void *
0x180009379  mov     r8d, 1000h; Size
0x18000937f  call    memset_0
0x180009384  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000938c  mov     [rsp+1090h+var_1050], 1000h
0x180009394  mov     [rsp+1090h+var_104C], 0
0x18000939c  jnz     short loc_1800093E6
0x18000939e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800093a5  test    rax, rax
0x1800093a8  jnz     short loc_1800093BE
0x1800093aa  lea     rcx, ModuleName; "ntdll.dll"
0x1800093b1  call    cs:__imp_GetModuleHandleW
0x1800093b7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800093be  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800093c5  mov     rcx, rax; hModule
0x1800093c8  call    cs:__imp_GetProcAddress
0x1800093ce  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800093d5  test    rax, rax
0x1800093d8  jnz     short loc_1800093E6
0x1800093da  mov     edi, 0C0000139h
0x1800093df  mov     ebx, edi
0x1800093e1  jmp     loc_180009513
0x1800093e6  lea     rax, [rsp+1090h+var_1050]
0x1800093eb  xor     r8d, r8d
0x1800093ee  mov     [rsp+1090h+var_1068], rax
0x1800093f3  lea     r9, [rsp+1090h+var_104C]
0x1800093f8  lea     rax, [rsp+1090h+var_1040]
0x1800093fd  xor     edx, edx
0x1800093ff  mov     [rsp+1090h+var_1070], rax
0x180009404  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000940b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180009412  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009417  mov     ebx, eax
0x180009419  mov     edi, eax
0x18000941b  test    eax, eax
0x18000941d  jnz     loc_180009513
0x180009423  mov     r9d, [rsp+1090h+var_1050]
0x180009428  mov     r11, 0AAAAAAAAAAAAAAABh
0x180009432  mov     rax, r11
0x180009435  mul     r9
0x180009438  shr     rdx, 3
0x18000943c  lea     rcx, [rdx+rdx*2]
0x180009440  shl     rcx, 2
0x180009444  cmp     r9, rcx
0x180009447  jz      short loc_180009451
0x180009449  xor     r9d, r9d
0x18000944c  mov     [rsp+1090h+var_1050], r9d
0x180009451  mov     r8, [r14]
0x180009454  mov     rax, r11
0x180009457  mov     ecx, r9d
0x18000945a  mul     rcx
0x18000945d  mov     rcx, [r14+8]
0x180009461  mov     rax, r11
0x180009464  mov     r10, rdx
0x180009467  sub     rcx, r8
0x18000946a  mul     rcx
0x18000946d  shr     r10, 3
0x180009471  shr     rdx, 3
0x180009475  lea     rax, [rdx+rdx*2]
0x180009479  lea     rsi, [r8+rax*4]
0x18000947d  jmp     short loc_1800094E8
0x18000947f  mov     eax, r10d
0x180009482  lea     rcx, [rax+rax*2]
0x180009486  lea     rdx, [rdx+rcx*4]
0x18000948a  lea     rax, [rsp+1090h+var_1040]
0x18000948f  cmp     rax, rdx
0x180009492  jz      short loc_1800094B9
0x180009494  mov     r11d, [r8]
0x180009497  lea     rcx, [rsp+1090h+var_1040]
0x18000949c  cmp     [rcx], r11d
0x18000949f  jnz     short loc_1800094B0
0x1800094a1  movzx   eax, word ptr [r8+4]
0x1800094a6  cmp     [rcx+4], ax
0x1800094aa  jz      loc_180009552
0x1800094b0  add     rcx, 0Ch
0x1800094b4  cmp     rcx, rdx
0x1800094b7  jnz     short loc_18000949C
0x1800094b9  mov     eax, r9d
0x1800094bc  add     rax, 0Ch
0x1800094c0  cmp     rax, 1000h
0x1800094c6  ja      short loc_1800094E4
0x1800094c8  movsd   xmm0, qword ptr [r8]
0x1800094cd  add     r9d, 0Ch
0x1800094d1  movsd   qword ptr [rdx], xmm0
0x1800094d5  inc     r10d
0x1800094d8  mov     eax, [r8+8]
0x1800094dc  mov     [rdx+8], eax
0x1800094df  mov     [rsp+1090h+var_1050], r9d
0x1800094e4  add     r8, 0Ch
0x1800094e8  lea     rdx, [rsp+1090h+var_1040]
0x1800094ed  cmp     r8, rsi
0x1800094f0  jnz     short loc_18000947F
0x1800094f2  mov     eax, [rsp+1090h+var_104C]
0x1800094f6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800094fd  mov     [rsp+1090h+var_1060], 1
0x180009505  mov     r8d, r9d
0x180009508  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000950c  call    wil_details_NtUpdateWnfStateData
0x180009511  mov     esi, eax
0x180009513  cmp     esi, 0C0000001h
0x180009519  jnz     short loc_18000952C
0x18000951b  inc     r15d
0x18000951e  cmp     r15d, 64h ; 'd'
0x180009522  jge     short loc_18000952C
0x180009524  test    edi, edi
0x180009526  jz      loc_180009372
0x18000952c  test    ebx, ebx
0x18000952e  cmovz   ebx, esi
0x180009531  mov     eax, ebx
0x180009533  mov     rcx, [rbp+0F90h+var_40]
0x18000953a  xor     rcx, rsp; StackCookie
0x18000953d  call    __security_check_cookie
0x180009542  add     rsp, 1068h
0x180009549  pop     r15
0x18000954b  pop     r14
0x18000954d  pop     rdi
0x18000954e  pop     rsi
0x18000954f  pop     rbx
0x180009550  pop     rbp
0x180009551  retn
0x180009552  mov     eax, [r8+8]
0x180009556  add     [rcx+8], eax
0x180009559  mov     r9d, [rsp+1090h+var_1050]
0x18000955e  jmp     short loc_1800094E4
```
