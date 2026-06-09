# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000bd90`
- end: `0x14000bfc8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140006970`

## callees

- `0x1400015f0`
- `0x1400022ec`
- `0x14000bd90`
- `0x14000c060`
- `0x14000fa20`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000be19`
- `KERNEL32!GetModuleHandleW` at `0x14000be19`
- `KERNEL32!GetProcAddress` at `0x14000be30`
- `KERNEL32!GetProcAddress` at `0x14000be30`

## string_xrefs

- `0x14000be12`: `ntdll.dll`

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
0x14000bd90  push    rbp
0x14000bd92  push    rbx
0x14000bd93  push    rsi
0x14000bd94  push    rdi
0x14000bd95  push    r14
0x14000bd97  push    r15
0x14000bd99  lea     rbp, [rsp-0F68h]
0x14000bda1  mov     eax, 1068h
0x14000bda6  call    _alloca_probe
0x14000bdab  sub     rsp, rax
0x14000bdae  mov     rax, cs:__security_cookie
0x14000bdb5  xor     rax, rsp
0x14000bdb8  mov     [rbp+0F90h+var_40], rax
0x14000bdbf  mov     rax, [rcx+8]
0x14000bdc3  xor     ebx, ebx
0x14000bdc5  sub     rax, [rcx]
0x14000bdc8  xor     esi, esi
0x14000bdca  mov     r14, rcx
0x14000bdcd  cmp     rax, 0Ch
0x14000bdd1  jb      loc_14000BF94
0x14000bdd7  xor     r15d, r15d
0x14000bdda  xor     edx, edx; Val
0x14000bddc  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000bde1  mov     r8d, 1000h; Size
0x14000bde7  call    memset_0
0x14000bdec  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000bdf4  mov     [rsp+1090h+var_1050], 1000h
0x14000bdfc  mov     [rsp+1090h+var_104C], 0
0x14000be04  jnz     short loc_14000BE4E
0x14000be06  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000be0d  test    rax, rax
0x14000be10  jnz     short loc_14000BE26
0x14000be12  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000be19  call    cs:__imp_GetModuleHandleW
0x14000be1f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000be26  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000be2d  mov     rcx, rax; hModule
0x14000be30  call    cs:__imp_GetProcAddress
0x14000be36  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000be3d  test    rax, rax
0x14000be40  jnz     short loc_14000BE4E
0x14000be42  mov     edi, 0C0000139h
0x14000be47  mov     ebx, edi
0x14000be49  jmp     loc_14000BF7B
0x14000be4e  lea     rax, [rsp+1090h+var_1050]
0x14000be53  xor     r8d, r8d
0x14000be56  mov     [rsp+1090h+var_1068], rax
0x14000be5b  lea     r9, [rsp+1090h+var_104C]
0x14000be60  lea     rax, [rsp+1090h+var_1040]
0x14000be65  xor     edx, edx
0x14000be67  mov     [rsp+1090h+var_1070], rax
0x14000be6c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000be73  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000be7a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000be7f  mov     ebx, eax
0x14000be81  mov     edi, eax
0x14000be83  test    eax, eax
0x14000be85  jnz     loc_14000BF7B
0x14000be8b  mov     r9d, [rsp+1090h+var_1050]
0x14000be90  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000be9a  mov     rax, r11
0x14000be9d  mul     r9
0x14000bea0  shr     rdx, 3
0x14000bea4  lea     rcx, [rdx+rdx*2]
0x14000bea8  shl     rcx, 2
0x14000beac  cmp     r9, rcx
0x14000beaf  jz      short loc_14000BEB9
0x14000beb1  xor     r9d, r9d
0x14000beb4  mov     [rsp+1090h+var_1050], r9d
0x14000beb9  mov     r8, [r14]
0x14000bebc  mov     rax, r11
0x14000bebf  mov     ecx, r9d
0x14000bec2  mul     rcx
0x14000bec5  mov     rcx, [r14+8]
0x14000bec9  mov     rax, r11
0x14000becc  mov     r10, rdx
0x14000becf  sub     rcx, r8
0x14000bed2  mul     rcx
0x14000bed5  shr     r10, 3
0x14000bed9  shr     rdx, 3
0x14000bedd  lea     rax, [rdx+rdx*2]
0x14000bee1  lea     rsi, [r8+rax*4]
0x14000bee5  jmp     short loc_14000BF50
0x14000bee7  mov     eax, r10d
0x14000beea  lea     rcx, [rax+rax*2]
0x14000beee  lea     rdx, [rdx+rcx*4]
0x14000bef2  lea     rax, [rsp+1090h+var_1040]
0x14000bef7  cmp     rax, rdx
0x14000befa  jz      short loc_14000BF21
0x14000befc  mov     r11d, [r8]
0x14000beff  lea     rcx, [rsp+1090h+var_1040]
0x14000bf04  cmp     [rcx], r11d
0x14000bf07  jnz     short loc_14000BF18
0x14000bf09  movzx   eax, word ptr [r8+4]
0x14000bf0e  cmp     [rcx+4], ax
0x14000bf12  jz      loc_14000BFBA
0x14000bf18  add     rcx, 0Ch
0x14000bf1c  cmp     rcx, rdx
0x14000bf1f  jnz     short loc_14000BF04
0x14000bf21  mov     eax, r9d
0x14000bf24  add     rax, 0Ch
0x14000bf28  cmp     rax, 1000h
0x14000bf2e  ja      short loc_14000BF4C
0x14000bf30  movsd   xmm0, qword ptr [r8]
0x14000bf35  add     r9d, 0Ch
0x14000bf39  movsd   qword ptr [rdx], xmm0
0x14000bf3d  inc     r10d
0x14000bf40  mov     eax, [r8+8]
0x14000bf44  mov     [rdx+8], eax
0x14000bf47  mov     [rsp+1090h+var_1050], r9d
0x14000bf4c  add     r8, 0Ch
0x14000bf50  lea     rdx, [rsp+1090h+var_1040]
0x14000bf55  cmp     r8, rsi
0x14000bf58  jnz     short loc_14000BEE7
0x14000bf5a  mov     eax, [rsp+1090h+var_104C]
0x14000bf5e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000bf65  mov     [rsp+1090h+var_1060], 1
0x14000bf6d  mov     r8d, r9d
0x14000bf70  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000bf74  call    wil_details_NtUpdateWnfStateData
0x14000bf79  mov     esi, eax
0x14000bf7b  cmp     esi, 0C0000001h
0x14000bf81  jnz     short loc_14000BF94
0x14000bf83  inc     r15d
0x14000bf86  cmp     r15d, 64h ; 'd'
0x14000bf8a  jge     short loc_14000BF94
0x14000bf8c  test    edi, edi
0x14000bf8e  jz      loc_14000BDDA
0x14000bf94  test    ebx, ebx
0x14000bf96  cmovz   ebx, esi
0x14000bf99  mov     eax, ebx
0x14000bf9b  mov     rcx, [rbp+0F90h+var_40]
0x14000bfa2  xor     rcx, rsp; StackCookie
0x14000bfa5  call    __security_check_cookie
0x14000bfaa  add     rsp, 1068h
0x14000bfb1  pop     r15
0x14000bfb3  pop     r14
0x14000bfb5  pop     rdi
0x14000bfb6  pop     rsi
0x14000bfb7  pop     rbx
0x14000bfb8  pop     rbp
0x14000bfb9  retn
0x14000bfba  mov     eax, [r8+8]
0x14000bfbe  add     [rcx+8], eax
0x14000bfc1  mov     r9d, [rsp+1090h+var_1050]
0x14000bfc6  jmp     short loc_14000BF4C
```
