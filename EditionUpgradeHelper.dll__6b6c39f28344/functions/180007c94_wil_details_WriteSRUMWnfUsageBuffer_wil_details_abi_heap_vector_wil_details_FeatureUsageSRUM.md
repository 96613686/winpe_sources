# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180007c94`
- end: `0x180007ecc`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800025b0`

## callees

- `0x1800018e0`
- `0x1800024d4`
- `0x180007c94`
- `0x180007f64`
- `0x1800265e0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007d1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007d1d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007d34`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007d34`

## string_xrefs

- `0x180007d16`: `ntdll.dll`

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
0x180007c94  push    rbp
0x180007c96  push    rbx
0x180007c97  push    rsi
0x180007c98  push    rdi
0x180007c99  push    r14
0x180007c9b  push    r15
0x180007c9d  lea     rbp, [rsp-0F68h]
0x180007ca5  mov     eax, 1068h
0x180007caa  call    _alloca_probe
0x180007caf  sub     rsp, rax
0x180007cb2  mov     rax, cs:__security_cookie
0x180007cb9  xor     rax, rsp
0x180007cbc  mov     [rbp+0F90h+var_40], rax
0x180007cc3  mov     rax, [rcx+8]
0x180007cc7  xor     ebx, ebx
0x180007cc9  sub     rax, [rcx]
0x180007ccc  xor     esi, esi
0x180007cce  mov     r14, rcx
0x180007cd1  cmp     rax, 0Ch
0x180007cd5  jb      loc_180007E98
0x180007cdb  xor     r15d, r15d
0x180007cde  xor     edx, edx; Val
0x180007ce0  lea     rcx, [rsp+1090h+var_1040]; void *
0x180007ce5  mov     r8d, 1000h; Size
0x180007ceb  call    memset_0
0x180007cf0  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180007cf8  mov     [rsp+1090h+var_1050], 1000h
0x180007d00  mov     [rsp+1090h+var_104C], 0
0x180007d08  jnz     short loc_180007D52
0x180007d0a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007d11  test    rax, rax
0x180007d14  jnz     short loc_180007D2A
0x180007d16  lea     rcx, ModuleName; "ntdll.dll"
0x180007d1d  call    cs:__imp_GetModuleHandleW
0x180007d23  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007d2a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180007d31  mov     rcx, rax; hModule
0x180007d34  call    cs:__imp_GetProcAddress
0x180007d3a  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180007d41  test    rax, rax
0x180007d44  jnz     short loc_180007D52
0x180007d46  mov     edi, 0C0000139h
0x180007d4b  mov     ebx, edi
0x180007d4d  jmp     loc_180007E7F
0x180007d52  lea     rax, [rsp+1090h+var_1050]
0x180007d57  xor     r8d, r8d
0x180007d5a  mov     [rsp+1090h+var_1068], rax
0x180007d5f  lea     r9, [rsp+1090h+var_104C]
0x180007d64  lea     rax, [rsp+1090h+var_1040]
0x180007d69  xor     edx, edx
0x180007d6b  mov     [rsp+1090h+var_1070], rax
0x180007d70  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180007d77  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180007d7e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007d83  mov     ebx, eax
0x180007d85  mov     edi, eax
0x180007d87  test    eax, eax
0x180007d89  jnz     loc_180007E7F
0x180007d8f  mov     r9d, [rsp+1090h+var_1050]
0x180007d94  mov     r11, 0AAAAAAAAAAAAAAABh
0x180007d9e  mov     rax, r11
0x180007da1  mul     r9
0x180007da4  shr     rdx, 3
0x180007da8  lea     rcx, [rdx+rdx*2]
0x180007dac  shl     rcx, 2
0x180007db0  cmp     r9, rcx
0x180007db3  jz      short loc_180007DBD
0x180007db5  xor     r9d, r9d
0x180007db8  mov     [rsp+1090h+var_1050], r9d
0x180007dbd  mov     r8, [r14]
0x180007dc0  mov     rax, r11
0x180007dc3  mov     ecx, r9d
0x180007dc6  mul     rcx
0x180007dc9  mov     rcx, [r14+8]
0x180007dcd  mov     rax, r11
0x180007dd0  mov     r10, rdx
0x180007dd3  sub     rcx, r8
0x180007dd6  mul     rcx
0x180007dd9  shr     r10, 3
0x180007ddd  shr     rdx, 3
0x180007de1  lea     rax, [rdx+rdx*2]
0x180007de5  lea     rsi, [r8+rax*4]
0x180007de9  jmp     short loc_180007E54
0x180007deb  mov     eax, r10d
0x180007dee  lea     rcx, [rax+rax*2]
0x180007df2  lea     rdx, [rdx+rcx*4]
0x180007df6  lea     rax, [rsp+1090h+var_1040]
0x180007dfb  cmp     rax, rdx
0x180007dfe  jz      short loc_180007E25
0x180007e00  mov     r11d, [r8]
0x180007e03  lea     rcx, [rsp+1090h+var_1040]
0x180007e08  cmp     [rcx], r11d
0x180007e0b  jnz     short loc_180007E1C
0x180007e0d  movzx   eax, word ptr [r8+4]
0x180007e12  cmp     [rcx+4], ax
0x180007e16  jz      loc_180007EBE
0x180007e1c  add     rcx, 0Ch
0x180007e20  cmp     rcx, rdx
0x180007e23  jnz     short loc_180007E08
0x180007e25  mov     eax, r9d
0x180007e28  add     rax, 0Ch
0x180007e2c  cmp     rax, 1000h
0x180007e32  ja      short loc_180007E50
0x180007e34  movsd   xmm0, qword ptr [r8]
0x180007e39  add     r9d, 0Ch
0x180007e3d  movsd   qword ptr [rdx], xmm0
0x180007e41  inc     r10d
0x180007e44  mov     eax, [r8+8]
0x180007e48  mov     [rdx+8], eax
0x180007e4b  mov     [rsp+1090h+var_1050], r9d
0x180007e50  add     r8, 0Ch
0x180007e54  lea     rdx, [rsp+1090h+var_1040]
0x180007e59  cmp     r8, rsi
0x180007e5c  jnz     short loc_180007DEB
0x180007e5e  mov     eax, [rsp+1090h+var_104C]
0x180007e62  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180007e69  mov     [rsp+1090h+var_1060], 1
0x180007e71  mov     r8d, r9d
0x180007e74  mov     dword ptr [rsp+1090h+var_1068], eax
0x180007e78  call    wil_details_NtUpdateWnfStateData
0x180007e7d  mov     esi, eax
0x180007e7f  cmp     esi, 0C0000001h
0x180007e85  jnz     short loc_180007E98
0x180007e87  inc     r15d
0x180007e8a  cmp     r15d, 64h ; 'd'
0x180007e8e  jge     short loc_180007E98
0x180007e90  test    edi, edi
0x180007e92  jz      loc_180007CDE
0x180007e98  test    ebx, ebx
0x180007e9a  cmovz   ebx, esi
0x180007e9d  mov     eax, ebx
0x180007e9f  mov     rcx, [rbp+0F90h+var_40]
0x180007ea6  xor     rcx, rsp; StackCookie
0x180007ea9  call    __security_check_cookie
0x180007eae  add     rsp, 1068h
0x180007eb5  pop     r15
0x180007eb7  pop     r14
0x180007eb9  pop     rdi
0x180007eba  pop     rsi
0x180007ebb  pop     rbx
0x180007ebc  pop     rbp
0x180007ebd  retn
0x180007ebe  mov     eax, [r8+8]
0x180007ec2  add     [rcx+8], eax
0x180007ec5  mov     r9d, [rsp+1090h+var_1050]
0x180007eca  jmp     short loc_180007E50
```
