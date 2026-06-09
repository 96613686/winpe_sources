# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180009f28`
- end: `0x18000a160`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800032d0`

## callees

- `0x180001d40`
- `0x180002a28`
- `0x180009f28`
- `0x18000a3f0`
- `0x180017e10`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009fc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009fc8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009fb1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009fb1`

## string_xrefs

- `0x180009faa`: `ntdll.dll`

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
0x180009f28  push    rbp
0x180009f2a  push    rbx
0x180009f2b  push    rsi
0x180009f2c  push    rdi
0x180009f2d  push    r14
0x180009f2f  push    r15
0x180009f31  lea     rbp, [rsp-0F68h]
0x180009f39  mov     eax, 1068h
0x180009f3e  call    _alloca_probe
0x180009f43  sub     rsp, rax
0x180009f46  mov     rax, cs:__security_cookie
0x180009f4d  xor     rax, rsp
0x180009f50  mov     [rbp+0F90h+var_40], rax
0x180009f57  mov     rax, [rcx+8]
0x180009f5b  xor     ebx, ebx
0x180009f5d  sub     rax, [rcx]
0x180009f60  xor     esi, esi
0x180009f62  mov     r14, rcx
0x180009f65  cmp     rax, 0Ch
0x180009f69  jb      loc_18000A12C
0x180009f6f  xor     r15d, r15d
0x180009f72  xor     edx, edx; Val
0x180009f74  lea     rcx, [rsp+1090h+var_1040]; void *
0x180009f79  mov     r8d, 1000h; Size
0x180009f7f  call    memset_0
0x180009f84  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180009f8c  mov     [rsp+1090h+var_1050], 1000h
0x180009f94  mov     [rsp+1090h+var_104C], 0
0x180009f9c  jnz     short loc_180009FE6
0x180009f9e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009fa5  test    rax, rax
0x180009fa8  jnz     short loc_180009FBE
0x180009faa  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009fb1  call    cs:__imp_GetModuleHandleW
0x180009fb7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009fbe  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009fc5  mov     rcx, rax; hModule
0x180009fc8  call    cs:__imp_GetProcAddress
0x180009fce  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009fd5  test    rax, rax
0x180009fd8  jnz     short loc_180009FE6
0x180009fda  mov     edi, 0C0000139h
0x180009fdf  mov     ebx, edi
0x180009fe1  jmp     loc_18000A113
0x180009fe6  lea     rax, [rsp+1090h+var_1050]
0x180009feb  xor     r8d, r8d
0x180009fee  mov     [rsp+1090h+var_1068], rax
0x180009ff3  lea     r9, [rsp+1090h+var_104C]
0x180009ff8  lea     rax, [rsp+1090h+var_1040]
0x180009ffd  xor     edx, edx
0x180009fff  mov     [rsp+1090h+var_1070], rax
0x18000a004  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a00b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000a012  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a017  mov     ebx, eax
0x18000a019  mov     edi, eax
0x18000a01b  test    eax, eax
0x18000a01d  jnz     loc_18000A113
0x18000a023  mov     r9d, [rsp+1090h+var_1050]
0x18000a028  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000a032  mov     rax, r11
0x18000a035  mul     r9
0x18000a038  shr     rdx, 3
0x18000a03c  lea     rcx, [rdx+rdx*2]
0x18000a040  shl     rcx, 2
0x18000a044  cmp     r9, rcx
0x18000a047  jz      short loc_18000A051
0x18000a049  xor     r9d, r9d
0x18000a04c  mov     [rsp+1090h+var_1050], r9d
0x18000a051  mov     r8, [r14]
0x18000a054  mov     rax, r11
0x18000a057  mov     ecx, r9d
0x18000a05a  mul     rcx
0x18000a05d  mov     rcx, [r14+8]
0x18000a061  mov     rax, r11
0x18000a064  mov     r10, rdx
0x18000a067  sub     rcx, r8
0x18000a06a  mul     rcx
0x18000a06d  shr     r10, 3
0x18000a071  shr     rdx, 3
0x18000a075  lea     rax, [rdx+rdx*2]
0x18000a079  lea     rsi, [r8+rax*4]
0x18000a07d  jmp     short loc_18000A0E8
0x18000a07f  mov     eax, r10d
0x18000a082  lea     rcx, [rax+rax*2]
0x18000a086  lea     rdx, [rdx+rcx*4]
0x18000a08a  lea     rax, [rsp+1090h+var_1040]
0x18000a08f  cmp     rax, rdx
0x18000a092  jz      short loc_18000A0B9
0x18000a094  mov     r11d, [r8]
0x18000a097  lea     rcx, [rsp+1090h+var_1040]
0x18000a09c  cmp     [rcx], r11d
0x18000a09f  jnz     short loc_18000A0B0
0x18000a0a1  movzx   eax, word ptr [r8+4]
0x18000a0a6  cmp     [rcx+4], ax
0x18000a0aa  jz      loc_18000A152
0x18000a0b0  add     rcx, 0Ch
0x18000a0b4  cmp     rcx, rdx
0x18000a0b7  jnz     short loc_18000A09C
0x18000a0b9  mov     eax, r9d
0x18000a0bc  add     rax, 0Ch
0x18000a0c0  cmp     rax, 1000h
0x18000a0c6  ja      short loc_18000A0E4
0x18000a0c8  movsd   xmm0, qword ptr [r8]
0x18000a0cd  add     r9d, 0Ch
0x18000a0d1  movsd   qword ptr [rdx], xmm0
0x18000a0d5  inc     r10d
0x18000a0d8  mov     eax, [r8+8]
0x18000a0dc  mov     [rdx+8], eax
0x18000a0df  mov     [rsp+1090h+var_1050], r9d
0x18000a0e4  add     r8, 0Ch
0x18000a0e8  lea     rdx, [rsp+1090h+var_1040]
0x18000a0ed  cmp     r8, rsi
0x18000a0f0  jnz     short loc_18000A07F
0x18000a0f2  mov     eax, [rsp+1090h+var_104C]
0x18000a0f6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000a0fd  mov     [rsp+1090h+var_1060], 1
0x18000a105  mov     r8d, r9d
0x18000a108  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000a10c  call    wil_details_NtUpdateWnfStateData
0x18000a111  mov     esi, eax
0x18000a113  cmp     esi, 0C0000001h
0x18000a119  jnz     short loc_18000A12C
0x18000a11b  inc     r15d
0x18000a11e  cmp     r15d, 64h ; 'd'
0x18000a122  jge     short loc_18000A12C
0x18000a124  test    edi, edi
0x18000a126  jz      loc_180009F72
0x18000a12c  test    ebx, ebx
0x18000a12e  cmovz   ebx, esi
0x18000a131  mov     eax, ebx
0x18000a133  mov     rcx, [rbp+0F90h+var_40]
0x18000a13a  xor     rcx, rsp; StackCookie
0x18000a13d  call    __security_check_cookie
0x18000a142  add     rsp, 1068h
0x18000a149  pop     r15
0x18000a14b  pop     r14
0x18000a14d  pop     rdi
0x18000a14e  pop     rsi
0x18000a14f  pop     rbx
0x18000a150  pop     rbp
0x18000a151  retn
0x18000a152  mov     eax, [r8+8]
0x18000a156  add     [rcx+8], eax
0x18000a159  mov     r9d, [rsp+1090h+var_1050]
0x18000a15e  jmp     short loc_18000A0E4
```
