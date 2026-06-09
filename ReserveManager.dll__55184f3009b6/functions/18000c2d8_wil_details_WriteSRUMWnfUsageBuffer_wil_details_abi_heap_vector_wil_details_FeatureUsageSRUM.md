# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000c2d8`
- end: `0x18000c510`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180004650`

## callees

- `0x180003870`
- `0x1800042f4`
- `0x18000c2d8`
- `0x18000d0b0`
- `0x180031b80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000c361`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x18000c361`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000c378`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000c378`

## string_xrefs

- `0x18000c35a`: `ntdll.dll`

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
0x18000c2d8  push    rbp
0x18000c2da  push    rbx
0x18000c2db  push    rsi
0x18000c2dc  push    rdi
0x18000c2dd  push    r14
0x18000c2df  push    r15
0x18000c2e1  lea     rbp, [rsp-0F68h]
0x18000c2e9  mov     eax, 1068h
0x18000c2ee  call    _alloca_probe
0x18000c2f3  sub     rsp, rax
0x18000c2f6  mov     rax, cs:__security_cookie
0x18000c2fd  xor     rax, rsp
0x18000c300  mov     [rbp+0F90h+var_40], rax
0x18000c307  mov     rax, [rcx+8]
0x18000c30b  xor     ebx, ebx
0x18000c30d  sub     rax, [rcx]
0x18000c310  xor     esi, esi
0x18000c312  mov     r14, rcx
0x18000c315  cmp     rax, 0Ch
0x18000c319  jb      loc_18000C4DC
0x18000c31f  xor     r15d, r15d
0x18000c322  xor     edx, edx; Val
0x18000c324  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000c329  mov     r8d, 1000h; Size
0x18000c32f  call    memset_0
0x18000c334  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000c33c  mov     [rsp+1090h+var_1050], 1000h
0x18000c344  mov     [rsp+1090h+var_104C], 0
0x18000c34c  jnz     short loc_18000C396
0x18000c34e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c355  test    rax, rax
0x18000c358  jnz     short loc_18000C36E
0x18000c35a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x18000c361  call    cs:__imp_GetModuleHandleW
0x18000c367  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000c36e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000c375  mov     rcx, rax; hModule
0x18000c378  call    cs:__imp_GetProcAddress
0x18000c37e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000c385  test    rax, rax
0x18000c388  jnz     short loc_18000C396
0x18000c38a  mov     edi, 0C0000139h
0x18000c38f  mov     ebx, edi
0x18000c391  jmp     loc_18000C4C3
0x18000c396  lea     rax, [rsp+1090h+var_1050]
0x18000c39b  xor     r8d, r8d
0x18000c39e  mov     [rsp+1090h+var_1068], rax
0x18000c3a3  lea     r9, [rsp+1090h+var_104C]
0x18000c3a8  lea     rax, [rsp+1090h+var_1040]
0x18000c3ad  xor     edx, edx
0x18000c3af  mov     [rsp+1090h+var_1070], rax
0x18000c3b4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000c3bb  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000c3c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000c3c7  mov     ebx, eax
0x18000c3c9  mov     edi, eax
0x18000c3cb  test    eax, eax
0x18000c3cd  jnz     loc_18000C4C3
0x18000c3d3  mov     r9d, [rsp+1090h+var_1050]
0x18000c3d8  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000c3e2  mov     rax, r11
0x18000c3e5  mul     r9
0x18000c3e8  shr     rdx, 3
0x18000c3ec  lea     rcx, [rdx+rdx*2]
0x18000c3f0  shl     rcx, 2
0x18000c3f4  cmp     r9, rcx
0x18000c3f7  jz      short loc_18000C401
0x18000c3f9  xor     r9d, r9d
0x18000c3fc  mov     [rsp+1090h+var_1050], r9d
0x18000c401  mov     r8, [r14]
0x18000c404  mov     rax, r11
0x18000c407  mov     ecx, r9d
0x18000c40a  mul     rcx
0x18000c40d  mov     rcx, [r14+8]
0x18000c411  mov     rax, r11
0x18000c414  mov     r10, rdx
0x18000c417  sub     rcx, r8
0x18000c41a  mul     rcx
0x18000c41d  shr     r10, 3
0x18000c421  shr     rdx, 3
0x18000c425  lea     rax, [rdx+rdx*2]
0x18000c429  lea     rsi, [r8+rax*4]
0x18000c42d  jmp     short loc_18000C498
0x18000c42f  mov     eax, r10d
0x18000c432  lea     rcx, [rax+rax*2]
0x18000c436  lea     rdx, [rdx+rcx*4]
0x18000c43a  lea     rax, [rsp+1090h+var_1040]
0x18000c43f  cmp     rax, rdx
0x18000c442  jz      short loc_18000C469
0x18000c444  mov     r11d, [r8]
0x18000c447  lea     rcx, [rsp+1090h+var_1040]
0x18000c44c  cmp     [rcx], r11d
0x18000c44f  jnz     short loc_18000C460
0x18000c451  movzx   eax, word ptr [r8+4]
0x18000c456  cmp     [rcx+4], ax
0x18000c45a  jz      loc_18000C502
0x18000c460  add     rcx, 0Ch
0x18000c464  cmp     rcx, rdx
0x18000c467  jnz     short loc_18000C44C
0x18000c469  mov     eax, r9d
0x18000c46c  add     rax, 0Ch
0x18000c470  cmp     rax, 1000h
0x18000c476  ja      short loc_18000C494
0x18000c478  movsd   xmm0, qword ptr [r8]
0x18000c47d  add     r9d, 0Ch
0x18000c481  movsd   qword ptr [rdx], xmm0
0x18000c485  inc     r10d
0x18000c488  mov     eax, [r8+8]
0x18000c48c  mov     [rdx+8], eax
0x18000c48f  mov     [rsp+1090h+var_1050], r9d
0x18000c494  add     r8, 0Ch
0x18000c498  lea     rdx, [rsp+1090h+var_1040]
0x18000c49d  cmp     r8, rsi
0x18000c4a0  jnz     short loc_18000C42F
0x18000c4a2  mov     eax, [rsp+1090h+var_104C]
0x18000c4a6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000c4ad  mov     [rsp+1090h+var_1060], 1
0x18000c4b5  mov     r8d, r9d
0x18000c4b8  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000c4bc  call    wil_details_NtUpdateWnfStateData
0x18000c4c1  mov     esi, eax
0x18000c4c3  cmp     esi, 0C0000001h
0x18000c4c9  jnz     short loc_18000C4DC
0x18000c4cb  inc     r15d
0x18000c4ce  cmp     r15d, 64h ; 'd'
0x18000c4d2  jge     short loc_18000C4DC
0x18000c4d4  test    edi, edi
0x18000c4d6  jz      loc_18000C322
0x18000c4dc  test    ebx, ebx
0x18000c4de  cmovz   ebx, esi
0x18000c4e1  mov     eax, ebx
0x18000c4e3  mov     rcx, [rbp+0F90h+var_40]
0x18000c4ea  xor     rcx, rsp; StackCookie
0x18000c4ed  call    __security_check_cookie
0x18000c4f2  add     rsp, 1068h
0x18000c4f9  pop     r15
0x18000c4fb  pop     r14
0x18000c4fd  pop     rdi
0x18000c4fe  pop     rsi
0x18000c4ff  pop     rbx
0x18000c500  pop     rbp
0x18000c501  retn
0x18000c502  mov     eax, [r8+8]
0x18000c506  add     [rcx+8], eax
0x18000c509  mov     r9d, [rsp+1090h+var_1050]
0x18000c50e  jmp     short loc_18000C494
```
