# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000a270`
- end: `0x18000a4a8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002660`

## callees

- `0x18000a270`
- `0x18000a7b8`
- `0x18001380e`
- `0x180013840`
- `0x1800138d0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a2f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a2f9`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a310`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a310`

## string_xrefs

- `0x18000a2f2`: `ntdll.dll`

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
0x18000a270  push    rbp
0x18000a272  push    rbx
0x18000a273  push    rsi
0x18000a274  push    rdi
0x18000a275  push    r14
0x18000a277  push    r15
0x18000a279  lea     rbp, [rsp-0F68h]
0x18000a281  mov     eax, 1068h
0x18000a286  call    _alloca_probe
0x18000a28b  sub     rsp, rax
0x18000a28e  mov     rax, cs:__security_cookie
0x18000a295  xor     rax, rsp
0x18000a298  mov     [rbp+0F90h+var_40], rax
0x18000a29f  mov     rax, [rcx+8]
0x18000a2a3  xor     ebx, ebx
0x18000a2a5  sub     rax, [rcx]
0x18000a2a8  xor     esi, esi
0x18000a2aa  mov     r14, rcx
0x18000a2ad  cmp     rax, 0Ch
0x18000a2b1  jb      loc_18000A474
0x18000a2b7  xor     r15d, r15d
0x18000a2ba  xor     edx, edx; Val
0x18000a2bc  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000a2c1  mov     r8d, 1000h; Size
0x18000a2c7  call    memset_0
0x18000a2cc  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000a2d4  mov     [rsp+1090h+var_1050], 1000h
0x18000a2dc  mov     [rsp+1090h+var_104C], 0
0x18000a2e4  jnz     short loc_18000A32E
0x18000a2e6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a2ed  test    rax, rax
0x18000a2f0  jnz     short loc_18000A306
0x18000a2f2  lea     rcx, ModuleName; "ntdll.dll"
0x18000a2f9  call    cs:__imp_GetModuleHandleW
0x18000a2ff  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a306  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000a30d  mov     rcx, rax; hModule
0x18000a310  call    cs:__imp_GetProcAddress
0x18000a316  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000a31d  test    rax, rax
0x18000a320  jnz     short loc_18000A32E
0x18000a322  mov     edi, 0C0000139h
0x18000a327  mov     ebx, edi
0x18000a329  jmp     loc_18000A45B
0x18000a32e  lea     rax, [rsp+1090h+var_1050]
0x18000a333  xor     r8d, r8d
0x18000a336  mov     [rsp+1090h+var_1068], rax
0x18000a33b  lea     r9, [rsp+1090h+var_104C]
0x18000a340  lea     rax, [rsp+1090h+var_1040]
0x18000a345  xor     edx, edx
0x18000a347  mov     [rsp+1090h+var_1070], rax
0x18000a34c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a353  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000a35a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a35f  mov     ebx, eax
0x18000a361  mov     edi, eax
0x18000a363  test    eax, eax
0x18000a365  jnz     loc_18000A45B
0x18000a36b  mov     r9d, [rsp+1090h+var_1050]
0x18000a370  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000a37a  mov     rax, r11
0x18000a37d  mul     r9
0x18000a380  shr     rdx, 3
0x18000a384  lea     rcx, [rdx+rdx*2]
0x18000a388  shl     rcx, 2
0x18000a38c  cmp     r9, rcx
0x18000a38f  jz      short loc_18000A399
0x18000a391  xor     r9d, r9d
0x18000a394  mov     [rsp+1090h+var_1050], r9d
0x18000a399  mov     r8, [r14]
0x18000a39c  mov     rax, r11
0x18000a39f  mov     ecx, r9d
0x18000a3a2  mul     rcx
0x18000a3a5  mov     rcx, [r14+8]
0x18000a3a9  mov     rax, r11
0x18000a3ac  mov     r10, rdx
0x18000a3af  sub     rcx, r8
0x18000a3b2  mul     rcx
0x18000a3b5  shr     r10, 3
0x18000a3b9  shr     rdx, 3
0x18000a3bd  lea     rax, [rdx+rdx*2]
0x18000a3c1  lea     rsi, [r8+rax*4]
0x18000a3c5  jmp     short loc_18000A430
0x18000a3c7  mov     eax, r10d
0x18000a3ca  lea     rcx, [rax+rax*2]
0x18000a3ce  lea     rdx, [rdx+rcx*4]
0x18000a3d2  lea     rax, [rsp+1090h+var_1040]
0x18000a3d7  cmp     rax, rdx
0x18000a3da  jz      short loc_18000A401
0x18000a3dc  mov     r11d, [r8]
0x18000a3df  lea     rcx, [rsp+1090h+var_1040]
0x18000a3e4  cmp     [rcx], r11d
0x18000a3e7  jnz     short loc_18000A3F8
0x18000a3e9  movzx   eax, word ptr [r8+4]
0x18000a3ee  cmp     [rcx+4], ax
0x18000a3f2  jz      loc_18000A49A
0x18000a3f8  add     rcx, 0Ch
0x18000a3fc  cmp     rcx, rdx
0x18000a3ff  jnz     short loc_18000A3E4
0x18000a401  mov     eax, r9d
0x18000a404  add     rax, 0Ch
0x18000a408  cmp     rax, 1000h
0x18000a40e  ja      short loc_18000A42C
0x18000a410  movsd   xmm0, qword ptr [r8]
0x18000a415  add     r9d, 0Ch
0x18000a419  movsd   qword ptr [rdx], xmm0
0x18000a41d  inc     r10d
0x18000a420  mov     eax, [r8+8]
0x18000a424  mov     [rdx+8], eax
0x18000a427  mov     [rsp+1090h+var_1050], r9d
0x18000a42c  add     r8, 0Ch
0x18000a430  lea     rdx, [rsp+1090h+var_1040]
0x18000a435  cmp     r8, rsi
0x18000a438  jnz     short loc_18000A3C7
0x18000a43a  mov     eax, [rsp+1090h+var_104C]
0x18000a43e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a445  mov     [rsp+1090h+var_1060], 1
0x18000a44d  mov     r8d, r9d
0x18000a450  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a454  call    wil_details_NtUpdateWnfStateData
0x18000a459  mov     esi, eax
0x18000a45b  cmp     esi, 0C0000001h
0x18000a461  jnz     short loc_18000A474
0x18000a463  inc     r15d
0x18000a466  cmp     r15d, 64h ; 'd'
0x18000a46a  jge     short loc_18000A474
0x18000a46c  test    edi, edi
0x18000a46e  jz      loc_18000A2BA
0x18000a474  test    ebx, ebx
0x18000a476  cmovz   ebx, esi
0x18000a479  mov     eax, ebx
0x18000a47b  mov     rcx, [rbp+0F90h+var_40]
0x18000a482  xor     rcx, rsp; StackCookie
0x18000a485  call    __security_check_cookie
0x18000a48a  add     rsp, 1068h
0x18000a491  pop     r15
0x18000a493  pop     r14
0x18000a495  pop     rdi
0x18000a496  pop     rsi
0x18000a497  pop     rbx
0x18000a498  pop     rbp
0x18000a499  retn
0x18000a49a  mov     eax, [r8+8]
0x18000a49e  add     [rcx+8], eax
0x18000a4a1  mov     r9d, [rsp+1090h+var_1050]
0x18000a4a6  jmp     short loc_18000A42C
```
