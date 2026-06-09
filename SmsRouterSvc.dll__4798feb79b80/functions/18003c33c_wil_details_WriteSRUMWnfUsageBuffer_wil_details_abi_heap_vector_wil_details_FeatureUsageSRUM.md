# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18003c33c`
- end: `0x18003c574`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800387e0`

## callees

- `0x180003a60`
- `0x180004998`
- `0x18003c33c`
- `0x18003cdf0`
- `0x18006b600`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003c3c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003c3c5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c3dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003c3dc`

## string_xrefs

- `0x18003c3be`: `ntdll.dll`

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
0x18003c33c  push    rbp
0x18003c33e  push    rbx
0x18003c33f  push    rsi
0x18003c340  push    rdi
0x18003c341  push    r14
0x18003c343  push    r15
0x18003c345  lea     rbp, [rsp-0F68h]
0x18003c34d  mov     eax, 1068h
0x18003c352  call    _alloca_probe
0x18003c357  sub     rsp, rax
0x18003c35a  mov     rax, cs:__security_cookie
0x18003c361  xor     rax, rsp
0x18003c364  mov     [rbp+0F90h+var_40], rax
0x18003c36b  mov     rax, [rcx+8]
0x18003c36f  xor     ebx, ebx
0x18003c371  sub     rax, [rcx]
0x18003c374  xor     esi, esi
0x18003c376  mov     r14, rcx
0x18003c379  cmp     rax, 0Ch
0x18003c37d  jb      loc_18003C540
0x18003c383  xor     r15d, r15d
0x18003c386  xor     edx, edx; Val
0x18003c388  lea     rcx, [rsp+1090h+var_1040]; void *
0x18003c38d  mov     r8d, 1000h; Size
0x18003c393  call    memset_0
0x18003c398  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18003c3a0  mov     [rsp+1090h+var_1050], 1000h
0x18003c3a8  mov     [rsp+1090h+var_104C], 0
0x18003c3b0  jnz     short loc_18003C3FA
0x18003c3b2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003c3b9  test    rax, rax
0x18003c3bc  jnz     short loc_18003C3D2
0x18003c3be  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18003c3c5  call    cs:__imp_GetModuleHandleW
0x18003c3cb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003c3d2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18003c3d9  mov     rcx, rax; hModule
0x18003c3dc  call    cs:__imp_GetProcAddress
0x18003c3e2  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18003c3e9  test    rax, rax
0x18003c3ec  jnz     short loc_18003C3FA
0x18003c3ee  mov     edi, 0C0000139h
0x18003c3f3  mov     ebx, edi
0x18003c3f5  jmp     loc_18003C527
0x18003c3fa  lea     rax, [rsp+1090h+var_1050]
0x18003c3ff  xor     r8d, r8d
0x18003c402  mov     [rsp+1090h+var_1068], rax
0x18003c407  lea     r9, [rsp+1090h+var_104C]
0x18003c40c  lea     rax, [rsp+1090h+var_1040]
0x18003c411  xor     edx, edx
0x18003c413  mov     [rsp+1090h+var_1070], rax
0x18003c418  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18003c41f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18003c426  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003c42b  mov     ebx, eax
0x18003c42d  mov     edi, eax
0x18003c42f  test    eax, eax
0x18003c431  jnz     loc_18003C527
0x18003c437  mov     r9d, [rsp+1090h+var_1050]
0x18003c43c  mov     r11, 0AAAAAAAAAAAAAAABh
0x18003c446  mov     rax, r11
0x18003c449  mul     r9
0x18003c44c  shr     rdx, 3
0x18003c450  lea     rcx, [rdx+rdx*2]
0x18003c454  shl     rcx, 2
0x18003c458  cmp     r9, rcx
0x18003c45b  jz      short loc_18003C465
0x18003c45d  xor     r9d, r9d
0x18003c460  mov     [rsp+1090h+var_1050], r9d
0x18003c465  mov     r8, [r14]
0x18003c468  mov     rax, r11
0x18003c46b  mov     ecx, r9d
0x18003c46e  mul     rcx
0x18003c471  mov     rcx, [r14+8]
0x18003c475  mov     rax, r11
0x18003c478  mov     r10, rdx
0x18003c47b  sub     rcx, r8
0x18003c47e  mul     rcx
0x18003c481  shr     r10, 3
0x18003c485  shr     rdx, 3
0x18003c489  lea     rax, [rdx+rdx*2]
0x18003c48d  lea     rsi, [r8+rax*4]
0x18003c491  jmp     short loc_18003C4FC
0x18003c493  mov     eax, r10d
0x18003c496  lea     rcx, [rax+rax*2]
0x18003c49a  lea     rdx, [rdx+rcx*4]
0x18003c49e  lea     rax, [rsp+1090h+var_1040]
0x18003c4a3  cmp     rax, rdx
0x18003c4a6  jz      short loc_18003C4CD
0x18003c4a8  mov     r11d, [r8]
0x18003c4ab  lea     rcx, [rsp+1090h+var_1040]
0x18003c4b0  cmp     [rcx], r11d
0x18003c4b3  jnz     short loc_18003C4C4
0x18003c4b5  movzx   eax, word ptr [r8+4]
0x18003c4ba  cmp     [rcx+4], ax
0x18003c4be  jz      loc_18003C566
0x18003c4c4  add     rcx, 0Ch
0x18003c4c8  cmp     rcx, rdx
0x18003c4cb  jnz     short loc_18003C4B0
0x18003c4cd  mov     eax, r9d
0x18003c4d0  add     rax, 0Ch
0x18003c4d4  cmp     rax, 1000h
0x18003c4da  ja      short loc_18003C4F8
0x18003c4dc  movsd   xmm0, qword ptr [r8]
0x18003c4e1  add     r9d, 0Ch
0x18003c4e5  movsd   qword ptr [rdx], xmm0
0x18003c4e9  inc     r10d
0x18003c4ec  mov     eax, [r8+8]
0x18003c4f0  mov     [rdx+8], eax
0x18003c4f3  mov     [rsp+1090h+var_1050], r9d
0x18003c4f8  add     r8, 0Ch
0x18003c4fc  lea     rdx, [rsp+1090h+var_1040]
0x18003c501  cmp     r8, rsi
0x18003c504  jnz     short loc_18003C493
0x18003c506  mov     eax, [rsp+1090h+var_104C]
0x18003c50a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18003c511  mov     [rsp+1090h+var_1060], 1
0x18003c519  mov     r8d, r9d
0x18003c51c  mov     dword ptr [rsp+1090h+var_1068], eax
0x18003c520  call    wil_details_NtUpdateWnfStateData
0x18003c525  mov     esi, eax
0x18003c527  cmp     esi, 0C0000001h
0x18003c52d  jnz     short loc_18003C540
0x18003c52f  inc     r15d
0x18003c532  cmp     r15d, 64h ; 'd'
0x18003c536  jge     short loc_18003C540
0x18003c538  test    edi, edi
0x18003c53a  jz      loc_18003C386
0x18003c540  test    ebx, ebx
0x18003c542  cmovz   ebx, esi
0x18003c545  mov     eax, ebx
0x18003c547  mov     rcx, [rbp+0F90h+var_40]
0x18003c54e  xor     rcx, rsp; StackCookie
0x18003c551  call    __security_check_cookie
0x18003c556  add     rsp, 1068h
0x18003c55d  pop     r15
0x18003c55f  pop     r14
0x18003c561  pop     rdi
0x18003c562  pop     rsi
0x18003c563  pop     rbx
0x18003c564  pop     rbp
0x18003c565  retn
0x18003c566  mov     eax, [r8+8]
0x18003c56a  add     [rcx+8], eax
0x18003c56d  mov     r9d, [rsp+1090h+var_1050]
0x18003c572  jmp     short loc_18003C4F8
```
