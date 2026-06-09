# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008758`
- end: `0x180008990`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800022e0`

## callees

- `0x180001760`
- `0x180002194`
- `0x180008758`
- `0x180008a28`
- `0x18000f4f0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800087f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800087f8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800087e1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800087e1`

## string_xrefs

- `0x1800087da`: `ntdll.dll`

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
0x180008758  push    rbp
0x18000875a  push    rbx
0x18000875b  push    rsi
0x18000875c  push    rdi
0x18000875d  push    r14
0x18000875f  push    r15
0x180008761  lea     rbp, [rsp-0F68h]
0x180008769  mov     eax, 1068h
0x18000876e  call    _alloca_probe
0x180008773  sub     rsp, rax
0x180008776  mov     rax, cs:__security_cookie
0x18000877d  xor     rax, rsp
0x180008780  mov     [rbp+0F90h+var_40], rax
0x180008787  mov     rax, [rcx+8]
0x18000878b  xor     ebx, ebx
0x18000878d  sub     rax, [rcx]
0x180008790  xor     esi, esi
0x180008792  mov     r14, rcx
0x180008795  cmp     rax, 0Ch
0x180008799  jb      loc_18000895C
0x18000879f  xor     r15d, r15d
0x1800087a2  xor     edx, edx; Val
0x1800087a4  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800087a9  mov     r8d, 1000h; Size
0x1800087af  call    memset_0
0x1800087b4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800087bc  mov     [rsp+1090h+var_1050], 1000h
0x1800087c4  mov     [rsp+1090h+var_104C], 0
0x1800087cc  jnz     short loc_180008816
0x1800087ce  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800087d5  test    rax, rax
0x1800087d8  jnz     short loc_1800087EE
0x1800087da  lea     rcx, ModuleName; "ntdll.dll"
0x1800087e1  call    cs:__imp_GetModuleHandleW
0x1800087e7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800087ee  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800087f5  mov     rcx, rax; hModule
0x1800087f8  call    cs:__imp_GetProcAddress
0x1800087fe  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008805  test    rax, rax
0x180008808  jnz     short loc_180008816
0x18000880a  mov     edi, 0C0000139h
0x18000880f  mov     ebx, edi
0x180008811  jmp     loc_180008943
0x180008816  lea     rax, [rsp+1090h+var_1050]
0x18000881b  xor     r8d, r8d
0x18000881e  mov     [rsp+1090h+var_1068], rax
0x180008823  lea     r9, [rsp+1090h+var_104C]
0x180008828  lea     rax, [rsp+1090h+var_1040]
0x18000882d  xor     edx, edx
0x18000882f  mov     [rsp+1090h+var_1070], rax
0x180008834  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000883b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008847  mov     ebx, eax
0x180008849  mov     edi, eax
0x18000884b  test    eax, eax
0x18000884d  jnz     loc_180008943
0x180008853  mov     r9d, [rsp+1090h+var_1050]
0x180008858  mov     r11, 0AAAAAAAAAAAAAAABh
0x180008862  mov     rax, r11
0x180008865  mul     r9
0x180008868  shr     rdx, 3
0x18000886c  lea     rcx, [rdx+rdx*2]
0x180008870  shl     rcx, 2
0x180008874  cmp     r9, rcx
0x180008877  jz      short loc_180008881
0x180008879  xor     r9d, r9d
0x18000887c  mov     [rsp+1090h+var_1050], r9d
0x180008881  mov     r8, [r14]
0x180008884  mov     rax, r11
0x180008887  mov     ecx, r9d
0x18000888a  mul     rcx
0x18000888d  mov     rcx, [r14+8]
0x180008891  mov     rax, r11
0x180008894  mov     r10, rdx
0x180008897  sub     rcx, r8
0x18000889a  mul     rcx
0x18000889d  shr     r10, 3
0x1800088a1  shr     rdx, 3
0x1800088a5  lea     rax, [rdx+rdx*2]
0x1800088a9  lea     rsi, [r8+rax*4]
0x1800088ad  jmp     short loc_180008918
0x1800088af  mov     eax, r10d
0x1800088b2  lea     rcx, [rax+rax*2]
0x1800088b6  lea     rdx, [rdx+rcx*4]
0x1800088ba  lea     rax, [rsp+1090h+var_1040]
0x1800088bf  cmp     rax, rdx
0x1800088c2  jz      short loc_1800088E9
0x1800088c4  mov     r11d, [r8]
0x1800088c7  lea     rcx, [rsp+1090h+var_1040]
0x1800088cc  cmp     [rcx], r11d
0x1800088cf  jnz     short loc_1800088E0
0x1800088d1  movzx   eax, word ptr [r8+4]
0x1800088d6  cmp     [rcx+4], ax
0x1800088da  jz      loc_180008982
0x1800088e0  add     rcx, 0Ch
0x1800088e4  cmp     rcx, rdx
0x1800088e7  jnz     short loc_1800088CC
0x1800088e9  mov     eax, r9d
0x1800088ec  add     rax, 0Ch
0x1800088f0  cmp     rax, 1000h
0x1800088f6  ja      short loc_180008914
0x1800088f8  movsd   xmm0, qword ptr [r8]
0x1800088fd  add     r9d, 0Ch
0x180008901  movsd   qword ptr [rdx], xmm0
0x180008905  inc     r10d
0x180008908  mov     eax, [r8+8]
0x18000890c  mov     [rdx+8], eax
0x18000890f  mov     [rsp+1090h+var_1050], r9d
0x180008914  add     r8, 0Ch
0x180008918  lea     rdx, [rsp+1090h+var_1040]
0x18000891d  cmp     r8, rsi
0x180008920  jnz     short loc_1800088AF
0x180008922  mov     eax, [rsp+1090h+var_104C]
0x180008926  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000892d  mov     [rsp+1090h+var_1060], 1
0x180008935  mov     r8d, r9d
0x180008938  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000893c  call    wil_details_NtUpdateWnfStateData
0x180008941  mov     esi, eax
0x180008943  cmp     esi, 0C0000001h
0x180008949  jnz     short loc_18000895C
0x18000894b  inc     r15d
0x18000894e  cmp     r15d, 64h ; 'd'
0x180008952  jge     short loc_18000895C
0x180008954  test    edi, edi
0x180008956  jz      loc_1800087A2
0x18000895c  test    ebx, ebx
0x18000895e  cmovz   ebx, esi
0x180008961  mov     eax, ebx
0x180008963  mov     rcx, [rbp+0F90h+var_40]
0x18000896a  xor     rcx, rsp; StackCookie
0x18000896d  call    __security_check_cookie
0x180008972  add     rsp, 1068h
0x180008979  pop     r15
0x18000897b  pop     r14
0x18000897d  pop     rdi
0x18000897e  pop     rsi
0x18000897f  pop     rbx
0x180008980  pop     rbp
0x180008981  retn
0x180008982  mov     eax, [r8+8]
0x180008986  add     [rcx+8], eax
0x180008989  mov     r9d, [rsp+1090h+var_1050]
0x18000898e  jmp     short loc_180008914
```
