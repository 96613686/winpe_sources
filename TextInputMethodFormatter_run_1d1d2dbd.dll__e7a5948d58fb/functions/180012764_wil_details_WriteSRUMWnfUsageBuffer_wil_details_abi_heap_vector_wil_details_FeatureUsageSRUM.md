# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180012764`
- end: `0x18001299c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180007e30`

## callees

- `0x180002240`
- `0x180002db8`
- `0x180012764`
- `0x1800131d0`
- `0x180056f80`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012804`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012804`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800127ed`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800127ed`

## string_xrefs

- `0x1800127e6`: `ntdll.dll`

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
0x180012764  push    rbp
0x180012766  push    rbx
0x180012767  push    rsi
0x180012768  push    rdi
0x180012769  push    r14
0x18001276b  push    r15
0x18001276d  lea     rbp, [rsp-0F68h]
0x180012775  mov     eax, 1068h
0x18001277a  call    _alloca_probe
0x18001277f  sub     rsp, rax
0x180012782  mov     rax, cs:__security_cookie
0x180012789  xor     rax, rsp
0x18001278c  mov     [rbp+0F90h+var_40], rax
0x180012793  mov     rax, [rcx+8]
0x180012797  xor     ebx, ebx
0x180012799  sub     rax, [rcx]
0x18001279c  xor     esi, esi
0x18001279e  mov     r14, rcx
0x1800127a1  cmp     rax, 0Ch
0x1800127a5  jb      loc_180012968
0x1800127ab  xor     r15d, r15d
0x1800127ae  xor     edx, edx; Val
0x1800127b0  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800127b5  mov     r8d, 1000h; Size
0x1800127bb  call    memset_0
0x1800127c0  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800127c8  mov     [rsp+1090h+var_1050], 1000h
0x1800127d0  mov     [rsp+1090h+var_104C], 0
0x1800127d8  jnz     short loc_180012822
0x1800127da  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800127e1  test    rax, rax
0x1800127e4  jnz     short loc_1800127FA
0x1800127e6  lea     rcx, ModuleName; "ntdll.dll"
0x1800127ed  call    cs:__imp_GetModuleHandleW
0x1800127f3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800127fa  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180012801  mov     rcx, rax; hModule
0x180012804  call    cs:__imp_GetProcAddress
0x18001280a  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180012811  test    rax, rax
0x180012814  jnz     short loc_180012822
0x180012816  mov     edi, 0C0000139h
0x18001281b  mov     ebx, edi
0x18001281d  jmp     loc_18001294F
0x180012822  lea     rax, [rsp+1090h+var_1050]
0x180012827  xor     r8d, r8d
0x18001282a  mov     [rsp+1090h+var_1068], rax
0x18001282f  lea     r9, [rsp+1090h+var_104C]
0x180012834  lea     rax, [rsp+1090h+var_1040]
0x180012839  xor     edx, edx
0x18001283b  mov     [rsp+1090h+var_1070], rax
0x180012840  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012847  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18001284e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180012853  mov     ebx, eax
0x180012855  mov     edi, eax
0x180012857  test    eax, eax
0x180012859  jnz     loc_18001294F
0x18001285f  mov     r9d, [rsp+1090h+var_1050]
0x180012864  mov     r11, 0AAAAAAAAAAAAAAABh
0x18001286e  mov     rax, r11
0x180012871  mul     r9
0x180012874  shr     rdx, 3
0x180012878  lea     rcx, [rdx+rdx*2]
0x18001287c  shl     rcx, 2
0x180012880  cmp     r9, rcx
0x180012883  jz      short loc_18001288D
0x180012885  xor     r9d, r9d
0x180012888  mov     [rsp+1090h+var_1050], r9d
0x18001288d  mov     r8, [r14]
0x180012890  mov     rax, r11
0x180012893  mov     ecx, r9d
0x180012896  mul     rcx
0x180012899  mov     rcx, [r14+8]
0x18001289d  mov     rax, r11
0x1800128a0  mov     r10, rdx
0x1800128a3  sub     rcx, r8
0x1800128a6  mul     rcx
0x1800128a9  shr     r10, 3
0x1800128ad  shr     rdx, 3
0x1800128b1  lea     rax, [rdx+rdx*2]
0x1800128b5  lea     rsi, [r8+rax*4]
0x1800128b9  jmp     short loc_180012924
0x1800128bb  mov     eax, r10d
0x1800128be  lea     rcx, [rax+rax*2]
0x1800128c2  lea     rdx, [rdx+rcx*4]
0x1800128c6  lea     rax, [rsp+1090h+var_1040]
0x1800128cb  cmp     rax, rdx
0x1800128ce  jz      short loc_1800128F5
0x1800128d0  mov     r11d, [r8]
0x1800128d3  lea     rcx, [rsp+1090h+var_1040]
0x1800128d8  cmp     [rcx], r11d
0x1800128db  jnz     short loc_1800128EC
0x1800128dd  movzx   eax, word ptr [r8+4]
0x1800128e2  cmp     [rcx+4], ax
0x1800128e6  jz      loc_18001298E
0x1800128ec  add     rcx, 0Ch
0x1800128f0  cmp     rcx, rdx
0x1800128f3  jnz     short loc_1800128D8
0x1800128f5  mov     eax, r9d
0x1800128f8  add     rax, 0Ch
0x1800128fc  cmp     rax, 1000h
0x180012902  ja      short loc_180012920
0x180012904  movsd   xmm0, qword ptr [r8]
0x180012909  add     r9d, 0Ch
0x18001290d  movsd   qword ptr [rdx], xmm0
0x180012911  inc     r10d
0x180012914  mov     eax, [r8+8]
0x180012918  mov     [rdx+8], eax
0x18001291b  mov     [rsp+1090h+var_1050], r9d
0x180012920  add     r8, 0Ch
0x180012924  lea     rdx, [rsp+1090h+var_1040]
0x180012929  cmp     r8, rsi
0x18001292c  jnz     short loc_1800128BB
0x18001292e  mov     eax, [rsp+1090h+var_104C]
0x180012932  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180012939  mov     [rsp+1090h+var_1060], 1
0x180012941  mov     r8d, r9d
0x180012944  mov     dword ptr [rsp+1090h+var_1068], eax
0x180012948  call    wil_details_NtUpdateWnfStateData
0x18001294d  mov     esi, eax
0x18001294f  cmp     esi, 0C0000001h
0x180012955  jnz     short loc_180012968
0x180012957  inc     r15d
0x18001295a  cmp     r15d, 64h ; 'd'
0x18001295e  jge     short loc_180012968
0x180012960  test    edi, edi
0x180012962  jz      loc_1800127AE
0x180012968  test    ebx, ebx
0x18001296a  cmovz   ebx, esi
0x18001296d  mov     eax, ebx
0x18001296f  mov     rcx, [rbp+0F90h+var_40]
0x180012976  xor     rcx, rsp; StackCookie
0x180012979  call    __security_check_cookie
0x18001297e  add     rsp, 1068h
0x180012985  pop     r15
0x180012987  pop     r14
0x180012989  pop     rdi
0x18001298a  pop     rsi
0x18001298b  pop     rbx
0x18001298c  pop     rbp
0x18001298d  retn
0x18001298e  mov     eax, [r8+8]
0x180012992  add     [rcx+8], eax
0x180012995  mov     r9d, [rsp+1090h+var_1050]
0x18001299a  jmp     short loc_180012920
```
