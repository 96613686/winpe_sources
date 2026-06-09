# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180014934`
- end: `0x180014b6c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000dea0`

## callees

- `0x1800032a0`
- `0x180003d14`
- `0x180014934`
- `0x180014b74`
- `0x180028fe0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800149bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800149bd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800149d4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800149d4`

## string_xrefs

- `0x1800149b6`: `ntdll.dll`

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
0x180014934  push    rbp
0x180014936  push    rbx
0x180014937  push    rsi
0x180014938  push    rdi
0x180014939  push    r14
0x18001493b  push    r15
0x18001493d  lea     rbp, [rsp-0F68h]
0x180014945  mov     eax, 1068h
0x18001494a  call    _alloca_probe
0x18001494f  sub     rsp, rax
0x180014952  mov     rax, cs:__security_cookie
0x180014959  xor     rax, rsp
0x18001495c  mov     [rbp+0F90h+var_40], rax
0x180014963  mov     rax, [rcx+8]
0x180014967  xor     ebx, ebx
0x180014969  sub     rax, [rcx]
0x18001496c  xor     esi, esi
0x18001496e  mov     r14, rcx
0x180014971  cmp     rax, 0Ch
0x180014975  jb      loc_180014B38
0x18001497b  xor     r15d, r15d
0x18001497e  xor     edx, edx; Val
0x180014980  lea     rcx, [rsp+1090h+var_1040]; void *
0x180014985  mov     r8d, 1000h; Size
0x18001498b  call    memset_0
0x180014990  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180014998  mov     [rsp+1090h+var_1050], 1000h
0x1800149a0  mov     [rsp+1090h+var_104C], 0
0x1800149a8  jnz     short loc_1800149F2
0x1800149aa  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800149b1  test    rax, rax
0x1800149b4  jnz     short loc_1800149CA
0x1800149b6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800149bd  call    cs:__imp_GetModuleHandleW
0x1800149c3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800149ca  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800149d1  mov     rcx, rax; hModule
0x1800149d4  call    cs:__imp_GetProcAddress
0x1800149da  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800149e1  test    rax, rax
0x1800149e4  jnz     short loc_1800149F2
0x1800149e6  mov     edi, 0C0000139h
0x1800149eb  mov     ebx, edi
0x1800149ed  jmp     loc_180014B1F
0x1800149f2  lea     rax, [rsp+1090h+var_1050]
0x1800149f7  xor     r8d, r8d
0x1800149fa  mov     [rsp+1090h+var_1068], rax
0x1800149ff  lea     r9, [rsp+1090h+var_104C]
0x180014a04  lea     rax, [rsp+1090h+var_1040]
0x180014a09  xor     edx, edx
0x180014a0b  mov     [rsp+1090h+var_1070], rax
0x180014a10  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180014a17  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180014a1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014a23  mov     ebx, eax
0x180014a25  mov     edi, eax
0x180014a27  test    eax, eax
0x180014a29  jnz     loc_180014B1F
0x180014a2f  mov     r9d, [rsp+1090h+var_1050]
0x180014a34  mov     r11, 0AAAAAAAAAAAAAAABh
0x180014a3e  mov     rax, r11
0x180014a41  mul     r9
0x180014a44  shr     rdx, 3
0x180014a48  lea     rcx, [rdx+rdx*2]
0x180014a4c  shl     rcx, 2
0x180014a50  cmp     r9, rcx
0x180014a53  jz      short loc_180014A5D
0x180014a55  xor     r9d, r9d
0x180014a58  mov     [rsp+1090h+var_1050], r9d
0x180014a5d  mov     r8, [r14]
0x180014a60  mov     rax, r11
0x180014a63  mov     ecx, r9d
0x180014a66  mul     rcx
0x180014a69  mov     rcx, [r14+8]
0x180014a6d  mov     rax, r11
0x180014a70  mov     r10, rdx
0x180014a73  sub     rcx, r8
0x180014a76  mul     rcx
0x180014a79  shr     r10, 3
0x180014a7d  shr     rdx, 3
0x180014a81  lea     rax, [rdx+rdx*2]
0x180014a85  lea     rsi, [r8+rax*4]
0x180014a89  jmp     short loc_180014AF4
0x180014a8b  mov     eax, r10d
0x180014a8e  lea     rcx, [rax+rax*2]
0x180014a92  lea     rdx, [rdx+rcx*4]
0x180014a96  lea     rax, [rsp+1090h+var_1040]
0x180014a9b  cmp     rax, rdx
0x180014a9e  jz      short loc_180014AC5
0x180014aa0  mov     r11d, [r8]
0x180014aa3  lea     rcx, [rsp+1090h+var_1040]
0x180014aa8  cmp     [rcx], r11d
0x180014aab  jnz     short loc_180014ABC
0x180014aad  movzx   eax, word ptr [r8+4]
0x180014ab2  cmp     [rcx+4], ax
0x180014ab6  jz      loc_180014B5E
0x180014abc  add     rcx, 0Ch
0x180014ac0  cmp     rcx, rdx
0x180014ac3  jnz     short loc_180014AA8
0x180014ac5  mov     eax, r9d
0x180014ac8  add     rax, 0Ch
0x180014acc  cmp     rax, 1000h
0x180014ad2  ja      short loc_180014AF0
0x180014ad4  movsd   xmm0, qword ptr [r8]
0x180014ad9  add     r9d, 0Ch
0x180014add  movsd   qword ptr [rdx], xmm0
0x180014ae1  inc     r10d
0x180014ae4  mov     eax, [r8+8]
0x180014ae8  mov     [rdx+8], eax
0x180014aeb  mov     [rsp+1090h+var_1050], r9d
0x180014af0  add     r8, 0Ch
0x180014af4  lea     rdx, [rsp+1090h+var_1040]
0x180014af9  cmp     r8, rsi
0x180014afc  jnz     short loc_180014A8B
0x180014afe  mov     eax, [rsp+1090h+var_104C]
0x180014b02  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180014b09  mov     [rsp+1090h+var_1060], 1
0x180014b11  mov     r8d, r9d
0x180014b14  mov     dword ptr [rsp+1090h+var_1068], eax
0x180014b18  call    wil_details_NtUpdateWnfStateData
0x180014b1d  mov     esi, eax
0x180014b1f  cmp     esi, 0C0000001h
0x180014b25  jnz     short loc_180014B38
0x180014b27  inc     r15d
0x180014b2a  cmp     r15d, 64h ; 'd'
0x180014b2e  jge     short loc_180014B38
0x180014b30  test    edi, edi
0x180014b32  jz      loc_18001497E
0x180014b38  test    ebx, ebx
0x180014b3a  cmovz   ebx, esi
0x180014b3d  mov     eax, ebx
0x180014b3f  mov     rcx, [rbp+0F90h+var_40]
0x180014b46  xor     rcx, rsp; StackCookie
0x180014b49  call    __security_check_cookie
0x180014b4e  add     rsp, 1068h
0x180014b55  pop     r15
0x180014b57  pop     r14
0x180014b59  pop     rdi
0x180014b5a  pop     rsi
0x180014b5b  pop     rbx
0x180014b5c  pop     rbp
0x180014b5d  retn
0x180014b5e  mov     eax, [r8+8]
0x180014b62  add     [rcx+8], eax
0x180014b65  mov     r9d, [rsp+1090h+var_1050]
0x180014b6a  jmp     short loc_180014AF0
```
