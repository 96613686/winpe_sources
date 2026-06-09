# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008854`
- end: `0x180008a8c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800028a0`

## callees

- `0x180001ac0`
- `0x1800026b4`
- `0x180008854`
- `0x180008d10`
- `0x1800228f0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800088f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800088f4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088dd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800088dd`

## string_xrefs

- `0x1800088d6`: `ntdll.dll`

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
0x180008854  push    rbp
0x180008856  push    rbx
0x180008857  push    rsi
0x180008858  push    rdi
0x180008859  push    r14
0x18000885b  push    r15
0x18000885d  lea     rbp, [rsp-0F68h]
0x180008865  mov     eax, 1068h
0x18000886a  call    _alloca_probe
0x18000886f  sub     rsp, rax
0x180008872  mov     rax, cs:__security_cookie
0x180008879  xor     rax, rsp
0x18000887c  mov     [rbp+0F90h+var_40], rax
0x180008883  mov     rax, [rcx+8]
0x180008887  xor     ebx, ebx
0x180008889  sub     rax, [rcx]
0x18000888c  xor     esi, esi
0x18000888e  mov     r14, rcx
0x180008891  cmp     rax, 0Ch
0x180008895  jb      loc_180008A58
0x18000889b  xor     r15d, r15d
0x18000889e  xor     edx, edx; Val
0x1800088a0  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800088a5  mov     r8d, 1000h; Size
0x1800088ab  call    memset_0
0x1800088b0  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800088b8  mov     [rsp+1090h+var_1050], 1000h
0x1800088c0  mov     [rsp+1090h+var_104C], 0
0x1800088c8  jnz     short loc_180008912
0x1800088ca  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800088d1  test    rax, rax
0x1800088d4  jnz     short loc_1800088EA
0x1800088d6  lea     rcx, ModuleName; "ntdll.dll"
0x1800088dd  call    cs:__imp_GetModuleHandleW
0x1800088e3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800088ea  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800088f1  mov     rcx, rax; hModule
0x1800088f4  call    cs:__imp_GetProcAddress
0x1800088fa  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008901  test    rax, rax
0x180008904  jnz     short loc_180008912
0x180008906  mov     edi, 0C0000139h
0x18000890b  mov     ebx, edi
0x18000890d  jmp     loc_180008A3F
0x180008912  lea     rax, [rsp+1090h+var_1050]
0x180008917  xor     r8d, r8d
0x18000891a  mov     [rsp+1090h+var_1068], rax
0x18000891f  lea     r9, [rsp+1090h+var_104C]
0x180008924  lea     rax, [rsp+1090h+var_1040]
0x180008929  xor     edx, edx
0x18000892b  mov     [rsp+1090h+var_1070], rax
0x180008930  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008937  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000893e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008943  mov     ebx, eax
0x180008945  mov     edi, eax
0x180008947  test    eax, eax
0x180008949  jnz     loc_180008A3F
0x18000894f  mov     r9d, [rsp+1090h+var_1050]
0x180008954  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000895e  mov     rax, r11
0x180008961  mul     r9
0x180008964  shr     rdx, 3
0x180008968  lea     rcx, [rdx+rdx*2]
0x18000896c  shl     rcx, 2
0x180008970  cmp     r9, rcx
0x180008973  jz      short loc_18000897D
0x180008975  xor     r9d, r9d
0x180008978  mov     [rsp+1090h+var_1050], r9d
0x18000897d  mov     r8, [r14]
0x180008980  mov     rax, r11
0x180008983  mov     ecx, r9d
0x180008986  mul     rcx
0x180008989  mov     rcx, [r14+8]
0x18000898d  mov     rax, r11
0x180008990  mov     r10, rdx
0x180008993  sub     rcx, r8
0x180008996  mul     rcx
0x180008999  shr     r10, 3
0x18000899d  shr     rdx, 3
0x1800089a1  lea     rax, [rdx+rdx*2]
0x1800089a5  lea     rsi, [r8+rax*4]
0x1800089a9  jmp     short loc_180008A14
0x1800089ab  mov     eax, r10d
0x1800089ae  lea     rcx, [rax+rax*2]
0x1800089b2  lea     rdx, [rdx+rcx*4]
0x1800089b6  lea     rax, [rsp+1090h+var_1040]
0x1800089bb  cmp     rax, rdx
0x1800089be  jz      short loc_1800089E5
0x1800089c0  mov     r11d, [r8]
0x1800089c3  lea     rcx, [rsp+1090h+var_1040]
0x1800089c8  cmp     [rcx], r11d
0x1800089cb  jnz     short loc_1800089DC
0x1800089cd  movzx   eax, word ptr [r8+4]
0x1800089d2  cmp     [rcx+4], ax
0x1800089d6  jz      loc_180008A7E
0x1800089dc  add     rcx, 0Ch
0x1800089e0  cmp     rcx, rdx
0x1800089e3  jnz     short loc_1800089C8
0x1800089e5  mov     eax, r9d
0x1800089e8  add     rax, 0Ch
0x1800089ec  cmp     rax, 1000h
0x1800089f2  ja      short loc_180008A10
0x1800089f4  movsd   xmm0, qword ptr [r8]
0x1800089f9  add     r9d, 0Ch
0x1800089fd  movsd   qword ptr [rdx], xmm0
0x180008a01  inc     r10d
0x180008a04  mov     eax, [r8+8]
0x180008a08  mov     [rdx+8], eax
0x180008a0b  mov     [rsp+1090h+var_1050], r9d
0x180008a10  add     r8, 0Ch
0x180008a14  lea     rdx, [rsp+1090h+var_1040]
0x180008a19  cmp     r8, rsi
0x180008a1c  jnz     short loc_1800089AB
0x180008a1e  mov     eax, [rsp+1090h+var_104C]
0x180008a22  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180008a29  mov     [rsp+1090h+var_1060], 1
0x180008a31  mov     r8d, r9d
0x180008a34  mov     dword ptr [rsp+1090h+var_1068], eax
0x180008a38  call    wil_details_NtUpdateWnfStateData
0x180008a3d  mov     esi, eax
0x180008a3f  cmp     esi, 0C0000001h
0x180008a45  jnz     short loc_180008A58
0x180008a47  inc     r15d
0x180008a4a  cmp     r15d, 64h ; 'd'
0x180008a4e  jge     short loc_180008A58
0x180008a50  test    edi, edi
0x180008a52  jz      loc_18000889E
0x180008a58  test    ebx, ebx
0x180008a5a  cmovz   ebx, esi
0x180008a5d  mov     eax, ebx
0x180008a5f  mov     rcx, [rbp+0F90h+var_40]
0x180008a66  xor     rcx, rsp; StackCookie
0x180008a69  call    __security_check_cookie
0x180008a6e  add     rsp, 1068h
0x180008a75  pop     r15
0x180008a77  pop     r14
0x180008a79  pop     rdi
0x180008a7a  pop     rsi
0x180008a7b  pop     rbx
0x180008a7c  pop     rbp
0x180008a7d  retn
0x180008a7e  mov     eax, [r8+8]
0x180008a82  add     [rcx+8], eax
0x180008a85  mov     r9d, [rsp+1090h+var_1050]
0x180008a8a  jmp     short loc_180008A10
```
