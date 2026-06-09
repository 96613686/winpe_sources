# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180007db8`
- end: `0x180007ff0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180001f40`

## callees

- `0x180007db8`
- `0x180009aa0`
- `0x18000c4a4`
- `0x18000c560`
- `0x18000c5f0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e58`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007e58`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e41`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007e41`

## string_xrefs

- `0x180007e3a`: `ntdll.dll`

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
0x180007db8  push    rbp
0x180007dba  push    rbx
0x180007dbb  push    rsi
0x180007dbc  push    rdi
0x180007dbd  push    r14
0x180007dbf  push    r15
0x180007dc1  lea     rbp, [rsp-0F68h]
0x180007dc9  mov     eax, 1068h
0x180007dce  call    _alloca_probe
0x180007dd3  sub     rsp, rax
0x180007dd6  mov     rax, cs:__security_cookie
0x180007ddd  xor     rax, rsp
0x180007de0  mov     [rbp+0F90h+var_40], rax
0x180007de7  mov     rax, [rcx+8]
0x180007deb  xor     ebx, ebx
0x180007ded  sub     rax, [rcx]
0x180007df0  xor     esi, esi
0x180007df2  mov     r14, rcx
0x180007df5  cmp     rax, 0Ch
0x180007df9  jb      loc_180007FBC
0x180007dff  xor     r15d, r15d
0x180007e02  xor     edx, edx; Val
0x180007e04  lea     rcx, [rsp+1090h+var_1040]; void *
0x180007e09  mov     r8d, 1000h; Size
0x180007e0f  call    memset_0
0x180007e14  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180007e1c  mov     [rsp+1090h+var_1050], 1000h
0x180007e24  mov     [rsp+1090h+var_104C], 0
0x180007e2c  jnz     short loc_180007E76
0x180007e2e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007e35  test    rax, rax
0x180007e38  jnz     short loc_180007E4E
0x180007e3a  lea     rcx, ModuleName; "ntdll.dll"
0x180007e41  call    cs:__imp_GetModuleHandleW
0x180007e47  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007e4e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180007e55  mov     rcx, rax; hModule
0x180007e58  call    cs:__imp_GetProcAddress
0x180007e5e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180007e65  test    rax, rax
0x180007e68  jnz     short loc_180007E76
0x180007e6a  mov     edi, 0C0000139h
0x180007e6f  mov     ebx, edi
0x180007e71  jmp     loc_180007FA3
0x180007e76  lea     rax, [rsp+1090h+var_1050]
0x180007e7b  xor     r8d, r8d
0x180007e7e  mov     [rsp+1090h+var_1068], rax
0x180007e83  lea     r9, [rsp+1090h+var_104C]
0x180007e88  lea     rax, [rsp+1090h+var_1040]
0x180007e8d  xor     edx, edx
0x180007e8f  mov     [rsp+1090h+var_1070], rax
0x180007e94  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180007e9b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180007ea2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007ea7  mov     ebx, eax
0x180007ea9  mov     edi, eax
0x180007eab  test    eax, eax
0x180007ead  jnz     loc_180007FA3
0x180007eb3  mov     r9d, [rsp+1090h+var_1050]
0x180007eb8  mov     r11, 0AAAAAAAAAAAAAAABh
0x180007ec2  mov     rax, r11
0x180007ec5  mul     r9
0x180007ec8  shr     rdx, 3
0x180007ecc  lea     rcx, [rdx+rdx*2]
0x180007ed0  shl     rcx, 2
0x180007ed4  cmp     r9, rcx
0x180007ed7  jz      short loc_180007EE1
0x180007ed9  xor     r9d, r9d
0x180007edc  mov     [rsp+1090h+var_1050], r9d
0x180007ee1  mov     r8, [r14]
0x180007ee4  mov     rax, r11
0x180007ee7  mov     ecx, r9d
0x180007eea  mul     rcx
0x180007eed  mov     rcx, [r14+8]
0x180007ef1  mov     rax, r11
0x180007ef4  mov     r10, rdx
0x180007ef7  sub     rcx, r8
0x180007efa  mul     rcx
0x180007efd  shr     r10, 3
0x180007f01  shr     rdx, 3
0x180007f05  lea     rax, [rdx+rdx*2]
0x180007f09  lea     rsi, [r8+rax*4]
0x180007f0d  jmp     short loc_180007F78
0x180007f0f  mov     eax, r10d
0x180007f12  lea     rcx, [rax+rax*2]
0x180007f16  lea     rdx, [rdx+rcx*4]
0x180007f1a  lea     rax, [rsp+1090h+var_1040]
0x180007f1f  cmp     rax, rdx
0x180007f22  jz      short loc_180007F49
0x180007f24  mov     r11d, [r8]
0x180007f27  lea     rcx, [rsp+1090h+var_1040]
0x180007f2c  cmp     [rcx], r11d
0x180007f2f  jnz     short loc_180007F40
0x180007f31  movzx   eax, word ptr [r8+4]
0x180007f36  cmp     [rcx+4], ax
0x180007f3a  jz      loc_180007FE2
0x180007f40  add     rcx, 0Ch
0x180007f44  cmp     rcx, rdx
0x180007f47  jnz     short loc_180007F2C
0x180007f49  mov     eax, r9d
0x180007f4c  add     rax, 0Ch
0x180007f50  cmp     rax, 1000h
0x180007f56  ja      short loc_180007F74
0x180007f58  movsd   xmm0, qword ptr [r8]
0x180007f5d  add     r9d, 0Ch
0x180007f61  movsd   qword ptr [rdx], xmm0
0x180007f65  inc     r10d
0x180007f68  mov     eax, [r8+8]
0x180007f6c  mov     [rdx+8], eax
0x180007f6f  mov     [rsp+1090h+var_1050], r9d
0x180007f74  add     r8, 0Ch
0x180007f78  lea     rdx, [rsp+1090h+var_1040]
0x180007f7d  cmp     r8, rsi
0x180007f80  jnz     short loc_180007F0F
0x180007f82  mov     eax, [rsp+1090h+var_104C]
0x180007f86  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180007f8d  mov     [rsp+1090h+var_1060], 1
0x180007f95  mov     r8d, r9d
0x180007f98  mov     dword ptr [rsp+1090h+var_1068], eax
0x180007f9c  call    wil_details_NtUpdateWnfStateData
0x180007fa1  mov     esi, eax
0x180007fa3  cmp     esi, 0C0000001h
0x180007fa9  jnz     short loc_180007FBC
0x180007fab  inc     r15d
0x180007fae  cmp     r15d, 64h ; 'd'
0x180007fb2  jge     short loc_180007FBC
0x180007fb4  test    edi, edi
0x180007fb6  jz      loc_180007E02
0x180007fbc  test    ebx, ebx
0x180007fbe  cmovz   ebx, esi
0x180007fc1  mov     eax, ebx
0x180007fc3  mov     rcx, [rbp+0F90h+var_40]
0x180007fca  xor     rcx, rsp; StackCookie
0x180007fcd  call    __security_check_cookie
0x180007fd2  add     rsp, 1068h
0x180007fd9  pop     r15
0x180007fdb  pop     r14
0x180007fdd  pop     rdi
0x180007fde  pop     rsi
0x180007fdf  pop     rbx
0x180007fe0  pop     rbp
0x180007fe1  retn
0x180007fe2  mov     eax, [r8+8]
0x180007fe6  add     [rcx+8], eax
0x180007fe9  mov     r9d, [rsp+1090h+var_1050]
0x180007fee  jmp     short loc_180007F74
```
