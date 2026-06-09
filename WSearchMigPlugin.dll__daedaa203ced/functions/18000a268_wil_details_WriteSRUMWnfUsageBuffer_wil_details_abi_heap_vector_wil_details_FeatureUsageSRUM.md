# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000a268`
- end: `0x18000a4a0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180003710`

## callees

- `0x1800026f0`
- `0x18000329c`
- `0x18000a268`
- `0x18000a730`
- `0x180016d70`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a2f1`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000a2f1`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a308`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000a308`

## string_xrefs

- `0x18000a2ea`: `ntdll.dll`

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
0x18000a268  push    rbp
0x18000a26a  push    rbx
0x18000a26b  push    rsi
0x18000a26c  push    rdi
0x18000a26d  push    r14
0x18000a26f  push    r15
0x18000a271  lea     rbp, [rsp-0F68h]
0x18000a279  mov     eax, 1068h
0x18000a27e  call    _alloca_probe
0x18000a283  sub     rsp, rax
0x18000a286  mov     rax, cs:__security_cookie
0x18000a28d  xor     rax, rsp
0x18000a290  mov     [rbp+0F90h+var_40], rax
0x18000a297  mov     rax, [rcx+8]
0x18000a29b  xor     ebx, ebx
0x18000a29d  sub     rax, [rcx]
0x18000a2a0  xor     esi, esi
0x18000a2a2  mov     r14, rcx
0x18000a2a5  cmp     rax, 0Ch
0x18000a2a9  jb      loc_18000A46C
0x18000a2af  xor     r15d, r15d
0x18000a2b2  xor     edx, edx; Val
0x18000a2b4  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000a2b9  mov     r8d, 1000h; Size
0x18000a2bf  call    memset_0
0x18000a2c4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000a2cc  mov     [rsp+1090h+var_1050], 1000h
0x18000a2d4  mov     [rsp+1090h+var_104C], 0
0x18000a2dc  jnz     short loc_18000A326
0x18000a2de  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a2e5  test    rax, rax
0x18000a2e8  jnz     short loc_18000A2FE
0x18000a2ea  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000a2f1  call    cs:__imp_GetModuleHandleW
0x18000a2f7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a2fe  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000a305  mov     rcx, rax; hModule
0x18000a308  call    cs:__imp_GetProcAddress
0x18000a30e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000a315  test    rax, rax
0x18000a318  jnz     short loc_18000A326
0x18000a31a  mov     edi, 0C0000139h
0x18000a31f  mov     ebx, edi
0x18000a321  jmp     loc_18000A453
0x18000a326  lea     rax, [rsp+1090h+var_1050]
0x18000a32b  xor     r8d, r8d
0x18000a32e  mov     [rsp+1090h+var_1068], rax
0x18000a333  lea     r9, [rsp+1090h+var_104C]
0x18000a338  lea     rax, [rsp+1090h+var_1040]
0x18000a33d  xor     edx, edx
0x18000a33f  mov     [rsp+1090h+var_1070], rax
0x18000a344  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a34b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000a352  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a357  mov     ebx, eax
0x18000a359  mov     edi, eax
0x18000a35b  test    eax, eax
0x18000a35d  jnz     loc_18000A453
0x18000a363  mov     r9d, [rsp+1090h+var_1050]
0x18000a368  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000a372  mov     rax, r11
0x18000a375  mul     r9
0x18000a378  shr     rdx, 3
0x18000a37c  lea     rcx, [rdx+rdx*2]
0x18000a380  shl     rcx, 2
0x18000a384  cmp     r9, rcx
0x18000a387  jz      short loc_18000A391
0x18000a389  xor     r9d, r9d
0x18000a38c  mov     [rsp+1090h+var_1050], r9d
0x18000a391  mov     r8, [r14]
0x18000a394  mov     rax, r11
0x18000a397  mov     ecx, r9d
0x18000a39a  mul     rcx
0x18000a39d  mov     rcx, [r14+8]
0x18000a3a1  mov     rax, r11
0x18000a3a4  mov     r10, rdx
0x18000a3a7  sub     rcx, r8
0x18000a3aa  mul     rcx
0x18000a3ad  shr     r10, 3
0x18000a3b1  shr     rdx, 3
0x18000a3b5  lea     rax, [rdx+rdx*2]
0x18000a3b9  lea     rsi, [r8+rax*4]
0x18000a3bd  jmp     short loc_18000A428
0x18000a3bf  mov     eax, r10d
0x18000a3c2  lea     rcx, [rax+rax*2]
0x18000a3c6  lea     rdx, [rdx+rcx*4]
0x18000a3ca  lea     rax, [rsp+1090h+var_1040]
0x18000a3cf  cmp     rax, rdx
0x18000a3d2  jz      short loc_18000A3F9
0x18000a3d4  mov     r11d, [r8]
0x18000a3d7  lea     rcx, [rsp+1090h+var_1040]
0x18000a3dc  cmp     [rcx], r11d
0x18000a3df  jnz     short loc_18000A3F0
0x18000a3e1  movzx   eax, word ptr [r8+4]
0x18000a3e6  cmp     [rcx+4], ax
0x18000a3ea  jz      loc_18000A492
0x18000a3f0  add     rcx, 0Ch
0x18000a3f4  cmp     rcx, rdx
0x18000a3f7  jnz     short loc_18000A3DC
0x18000a3f9  mov     eax, r9d
0x18000a3fc  add     rax, 0Ch
0x18000a400  cmp     rax, 1000h
0x18000a406  ja      short loc_18000A424
0x18000a408  movsd   xmm0, qword ptr [r8]
0x18000a40d  add     r9d, 0Ch
0x18000a411  movsd   qword ptr [rdx], xmm0
0x18000a415  inc     r10d
0x18000a418  mov     eax, [r8+8]
0x18000a41c  mov     [rdx+8], eax
0x18000a41f  mov     [rsp+1090h+var_1050], r9d
0x18000a424  add     r8, 0Ch
0x18000a428  lea     rdx, [rsp+1090h+var_1040]
0x18000a42d  cmp     r8, rsi
0x18000a430  jnz     short loc_18000A3BF
0x18000a432  mov     eax, [rsp+1090h+var_104C]
0x18000a436  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a43d  mov     [rsp+1090h+var_1060], 1
0x18000a445  mov     r8d, r9d
0x18000a448  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a44c  call    wil_details_NtUpdateWnfStateData
0x18000a451  mov     esi, eax
0x18000a453  cmp     esi, 0C0000001h
0x18000a459  jnz     short loc_18000A46C
0x18000a45b  inc     r15d
0x18000a45e  cmp     r15d, 64h ; 'd'
0x18000a462  jge     short loc_18000A46C
0x18000a464  test    edi, edi
0x18000a466  jz      loc_18000A2B2
0x18000a46c  test    ebx, ebx
0x18000a46e  cmovz   ebx, esi
0x18000a471  mov     eax, ebx
0x18000a473  mov     rcx, [rbp+0F90h+var_40]
0x18000a47a  xor     rcx, rsp; StackCookie
0x18000a47d  call    __security_check_cookie
0x18000a482  add     rsp, 1068h
0x18000a489  pop     r15
0x18000a48b  pop     r14
0x18000a48d  pop     rdi
0x18000a48e  pop     rsi
0x18000a48f  pop     rbx
0x18000a490  pop     rbp
0x18000a491  retn
0x18000a492  mov     eax, [r8+8]
0x18000a496  add     [rcx+8], eax
0x18000a499  mov     r9d, [rsp+1090h+var_1050]
0x18000a49e  jmp     short loc_18000A424
```
