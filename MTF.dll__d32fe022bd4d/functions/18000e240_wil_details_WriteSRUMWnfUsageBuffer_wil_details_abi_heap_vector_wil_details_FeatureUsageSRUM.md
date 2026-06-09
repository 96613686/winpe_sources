# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000e240`
- end: `0x18000e478`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180008360`

## callees

- `0x18000e240`
- `0x18000e480`
- `0x18002bc62`
- `0x18002bca0`
- `0x18002bd60`
- `0x18002f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e2e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000e2e0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e2c9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000e2c9`

## string_xrefs

- `0x18000e2c2`: `ntdll.dll`

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
0x18000e240  push    rbp
0x18000e242  push    rbx
0x18000e243  push    rsi
0x18000e244  push    rdi
0x18000e245  push    r14
0x18000e247  push    r15
0x18000e249  lea     rbp, [rsp-0F68h]
0x18000e251  mov     eax, 1068h
0x18000e256  call    _alloca_probe
0x18000e25b  sub     rsp, rax
0x18000e25e  mov     rax, cs:__security_cookie
0x18000e265  xor     rax, rsp
0x18000e268  mov     [rbp+0F90h+var_40], rax
0x18000e26f  mov     rax, [rcx+8]
0x18000e273  xor     ebx, ebx
0x18000e275  sub     rax, [rcx]
0x18000e278  xor     esi, esi
0x18000e27a  mov     r14, rcx
0x18000e27d  cmp     rax, 0Ch
0x18000e281  jb      loc_18000E444
0x18000e287  xor     r15d, r15d
0x18000e28a  xor     edx, edx; Val
0x18000e28c  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000e291  mov     r8d, 1000h; Size
0x18000e297  call    memset_0
0x18000e29c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000e2a4  mov     [rsp+1090h+var_1050], 1000h
0x18000e2ac  mov     [rsp+1090h+var_104C], 0
0x18000e2b4  jnz     short loc_18000E2FE
0x18000e2b6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e2bd  test    rax, rax
0x18000e2c0  jnz     short loc_18000E2D6
0x18000e2c2  lea     rcx, ModuleName; "ntdll.dll"
0x18000e2c9  call    cs:__imp_GetModuleHandleW
0x18000e2cf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000e2d6  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000e2dd  mov     rcx, rax; hModule
0x18000e2e0  call    cs:__imp_GetProcAddress
0x18000e2e6  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000e2ed  test    rax, rax
0x18000e2f0  jnz     short loc_18000E2FE
0x18000e2f2  mov     edi, 0C0000139h
0x18000e2f7  mov     ebx, edi
0x18000e2f9  jmp     loc_18000E42B
0x18000e2fe  lea     rax, [rsp+1090h+var_1050]
0x18000e303  xor     r8d, r8d
0x18000e306  mov     [rsp+1090h+var_1068], rax
0x18000e30b  lea     r9, [rsp+1090h+var_104C]
0x18000e310  lea     rax, [rsp+1090h+var_1040]
0x18000e315  xor     edx, edx
0x18000e317  mov     [rsp+1090h+var_1070], rax
0x18000e31c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000e323  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000e32a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000e32f  mov     ebx, eax
0x18000e331  mov     edi, eax
0x18000e333  test    eax, eax
0x18000e335  jnz     loc_18000E42B
0x18000e33b  mov     r9d, [rsp+1090h+var_1050]
0x18000e340  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000e34a  mov     rax, r11
0x18000e34d  mul     r9
0x18000e350  shr     rdx, 3
0x18000e354  lea     rcx, [rdx+rdx*2]
0x18000e358  shl     rcx, 2
0x18000e35c  cmp     r9, rcx
0x18000e35f  jz      short loc_18000E369
0x18000e361  xor     r9d, r9d
0x18000e364  mov     [rsp+1090h+var_1050], r9d
0x18000e369  mov     r8, [r14]
0x18000e36c  mov     rax, r11
0x18000e36f  mov     ecx, r9d
0x18000e372  mul     rcx
0x18000e375  mov     rcx, [r14+8]
0x18000e379  mov     rax, r11
0x18000e37c  mov     r10, rdx
0x18000e37f  sub     rcx, r8
0x18000e382  mul     rcx
0x18000e385  shr     r10, 3
0x18000e389  shr     rdx, 3
0x18000e38d  lea     rax, [rdx+rdx*2]
0x18000e391  lea     rsi, [r8+rax*4]
0x18000e395  jmp     short loc_18000E400
0x18000e397  mov     eax, r10d
0x18000e39a  lea     rcx, [rax+rax*2]
0x18000e39e  lea     rdx, [rdx+rcx*4]
0x18000e3a2  lea     rax, [rsp+1090h+var_1040]
0x18000e3a7  cmp     rax, rdx
0x18000e3aa  jz      short loc_18000E3D1
0x18000e3ac  mov     r11d, [r8]
0x18000e3af  lea     rcx, [rsp+1090h+var_1040]
0x18000e3b4  cmp     [rcx], r11d
0x18000e3b7  jnz     short loc_18000E3C8
0x18000e3b9  movzx   eax, word ptr [r8+4]
0x18000e3be  cmp     [rcx+4], ax
0x18000e3c2  jz      loc_18000E46A
0x18000e3c8  add     rcx, 0Ch
0x18000e3cc  cmp     rcx, rdx
0x18000e3cf  jnz     short loc_18000E3B4
0x18000e3d1  mov     eax, r9d
0x18000e3d4  add     rax, 0Ch
0x18000e3d8  cmp     rax, 1000h
0x18000e3de  ja      short loc_18000E3FC
0x18000e3e0  movsd   xmm0, qword ptr [r8]
0x18000e3e5  add     r9d, 0Ch
0x18000e3e9  movsd   qword ptr [rdx], xmm0
0x18000e3ed  inc     r10d
0x18000e3f0  mov     eax, [r8+8]
0x18000e3f4  mov     [rdx+8], eax
0x18000e3f7  mov     [rsp+1090h+var_1050], r9d
0x18000e3fc  add     r8, 0Ch
0x18000e400  lea     rdx, [rsp+1090h+var_1040]
0x18000e405  cmp     r8, rsi
0x18000e408  jnz     short loc_18000E397
0x18000e40a  mov     eax, [rsp+1090h+var_104C]
0x18000e40e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000e415  mov     [rsp+1090h+var_1060], 1
0x18000e41d  mov     r8d, r9d
0x18000e420  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000e424  call    wil_details_NtUpdateWnfStateData
0x18000e429  mov     esi, eax
0x18000e42b  cmp     esi, 0C0000001h
0x18000e431  jnz     short loc_18000E444
0x18000e433  inc     r15d
0x18000e436  cmp     r15d, 64h ; 'd'
0x18000e43a  jge     short loc_18000E444
0x18000e43c  test    edi, edi
0x18000e43e  jz      loc_18000E28A
0x18000e444  test    ebx, ebx
0x18000e446  cmovz   ebx, esi
0x18000e449  mov     eax, ebx
0x18000e44b  mov     rcx, [rbp+0F90h+var_40]
0x18000e452  xor     rcx, rsp; StackCookie
0x18000e455  call    __security_check_cookie
0x18000e45a  add     rsp, 1068h
0x18000e461  pop     r15
0x18000e463  pop     r14
0x18000e465  pop     rdi
0x18000e466  pop     rsi
0x18000e467  pop     rbx
0x18000e468  pop     rbp
0x18000e469  retn
0x18000e46a  mov     eax, [r8+8]
0x18000e46e  add     [rcx+8], eax
0x18000e471  mov     r9d, [rsp+1090h+var_1050]
0x18000e476  jmp     short loc_18000E3FC
```
