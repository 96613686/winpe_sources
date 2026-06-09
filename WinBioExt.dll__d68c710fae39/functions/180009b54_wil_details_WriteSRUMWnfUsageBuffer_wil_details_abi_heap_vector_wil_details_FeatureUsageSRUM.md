# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180009b54`
- end: `0x180009d8c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800070c0`

## callees

- `0x180001610`
- `0x180002084`
- `0x180009b54`
- `0x180009d94`
- `0x180009f50`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009bdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009bdd`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009bf4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009bf4`

## string_xrefs

- `0x180009bd6`: `ntdll.dll`

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
0x180009b54  push    rbp
0x180009b56  push    rbx
0x180009b57  push    rsi
0x180009b58  push    rdi
0x180009b59  push    r14
0x180009b5b  push    r15
0x180009b5d  lea     rbp, [rsp-0F68h]
0x180009b65  mov     eax, 1068h
0x180009b6a  call    _alloca_probe
0x180009b6f  sub     rsp, rax
0x180009b72  mov     rax, cs:__security_cookie
0x180009b79  xor     rax, rsp
0x180009b7c  mov     [rbp+0F90h+var_40], rax
0x180009b83  mov     rax, [rcx+8]
0x180009b87  xor     ebx, ebx
0x180009b89  sub     rax, [rcx]
0x180009b8c  xor     esi, esi
0x180009b8e  mov     r14, rcx
0x180009b91  cmp     rax, 0Ch
0x180009b95  jb      loc_180009D58
0x180009b9b  xor     r15d, r15d
0x180009b9e  xor     edx, edx; Val
0x180009ba0  lea     rcx, [rsp+1090h+var_1040]; void *
0x180009ba5  mov     r8d, 1000h; Size
0x180009bab  call    memset_0
0x180009bb0  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180009bb8  mov     [rsp+1090h+var_1050], 1000h
0x180009bc0  mov     [rsp+1090h+var_104C], 0
0x180009bc8  jnz     short loc_180009C12
0x180009bca  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009bd1  test    rax, rax
0x180009bd4  jnz     short loc_180009BEA
0x180009bd6  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180009bdd  call    cs:__imp_GetModuleHandleW
0x180009be3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009bea  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009bf1  mov     rcx, rax; hModule
0x180009bf4  call    cs:__imp_GetProcAddress
0x180009bfa  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009c01  test    rax, rax
0x180009c04  jnz     short loc_180009C12
0x180009c06  mov     edi, 0C0000139h
0x180009c0b  mov     ebx, edi
0x180009c0d  jmp     loc_180009D3F
0x180009c12  lea     rax, [rsp+1090h+var_1050]
0x180009c17  xor     r8d, r8d
0x180009c1a  mov     [rsp+1090h+var_1068], rax
0x180009c1f  lea     r9, [rsp+1090h+var_104C]
0x180009c24  lea     rax, [rsp+1090h+var_1040]
0x180009c29  xor     edx, edx
0x180009c2b  mov     [rsp+1090h+var_1070], rax
0x180009c30  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009c37  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180009c3e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c43  mov     ebx, eax
0x180009c45  mov     edi, eax
0x180009c47  test    eax, eax
0x180009c49  jnz     loc_180009D3F
0x180009c4f  mov     r9d, [rsp+1090h+var_1050]
0x180009c54  mov     r11, 0AAAAAAAAAAAAAAABh
0x180009c5e  mov     rax, r11
0x180009c61  mul     r9
0x180009c64  shr     rdx, 3
0x180009c68  lea     rcx, [rdx+rdx*2]
0x180009c6c  shl     rcx, 2
0x180009c70  cmp     r9, rcx
0x180009c73  jz      short loc_180009C7D
0x180009c75  xor     r9d, r9d
0x180009c78  mov     [rsp+1090h+var_1050], r9d
0x180009c7d  mov     r8, [r14]
0x180009c80  mov     rax, r11
0x180009c83  mov     ecx, r9d
0x180009c86  mul     rcx
0x180009c89  mov     rcx, [r14+8]
0x180009c8d  mov     rax, r11
0x180009c90  mov     r10, rdx
0x180009c93  sub     rcx, r8
0x180009c96  mul     rcx
0x180009c99  shr     r10, 3
0x180009c9d  shr     rdx, 3
0x180009ca1  lea     rax, [rdx+rdx*2]
0x180009ca5  lea     rsi, [r8+rax*4]
0x180009ca9  jmp     short loc_180009D14
0x180009cab  mov     eax, r10d
0x180009cae  lea     rcx, [rax+rax*2]
0x180009cb2  lea     rdx, [rdx+rcx*4]
0x180009cb6  lea     rax, [rsp+1090h+var_1040]
0x180009cbb  cmp     rax, rdx
0x180009cbe  jz      short loc_180009CE5
0x180009cc0  mov     r11d, [r8]
0x180009cc3  lea     rcx, [rsp+1090h+var_1040]
0x180009cc8  cmp     [rcx], r11d
0x180009ccb  jnz     short loc_180009CDC
0x180009ccd  movzx   eax, word ptr [r8+4]
0x180009cd2  cmp     [rcx+4], ax
0x180009cd6  jz      loc_180009D7E
0x180009cdc  add     rcx, 0Ch
0x180009ce0  cmp     rcx, rdx
0x180009ce3  jnz     short loc_180009CC8
0x180009ce5  mov     eax, r9d
0x180009ce8  add     rax, 0Ch
0x180009cec  cmp     rax, 1000h
0x180009cf2  ja      short loc_180009D10
0x180009cf4  movsd   xmm0, qword ptr [r8]
0x180009cf9  add     r9d, 0Ch
0x180009cfd  movsd   qword ptr [rdx], xmm0
0x180009d01  inc     r10d
0x180009d04  mov     eax, [r8+8]
0x180009d08  mov     [rdx+8], eax
0x180009d0b  mov     [rsp+1090h+var_1050], r9d
0x180009d10  add     r8, 0Ch
0x180009d14  lea     rdx, [rsp+1090h+var_1040]
0x180009d19  cmp     r8, rsi
0x180009d1c  jnz     short loc_180009CAB
0x180009d1e  mov     eax, [rsp+1090h+var_104C]
0x180009d22  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180009d29  mov     [rsp+1090h+var_1060], 1
0x180009d31  mov     r8d, r9d
0x180009d34  mov     dword ptr [rsp+1090h+var_1068], eax
0x180009d38  call    wil_details_NtUpdateWnfStateData
0x180009d3d  mov     esi, eax
0x180009d3f  cmp     esi, 0C0000001h
0x180009d45  jnz     short loc_180009D58
0x180009d47  inc     r15d
0x180009d4a  cmp     r15d, 64h ; 'd'
0x180009d4e  jge     short loc_180009D58
0x180009d50  test    edi, edi
0x180009d52  jz      loc_180009B9E
0x180009d58  test    ebx, ebx
0x180009d5a  cmovz   ebx, esi
0x180009d5d  mov     eax, ebx
0x180009d5f  mov     rcx, [rbp+0F90h+var_40]
0x180009d66  xor     rcx, rsp; StackCookie
0x180009d69  call    __security_check_cookie
0x180009d6e  add     rsp, 1068h
0x180009d75  pop     r15
0x180009d77  pop     r14
0x180009d79  pop     rdi
0x180009d7a  pop     rsi
0x180009d7b  pop     rbx
0x180009d7c  pop     rbp
0x180009d7d  retn
0x180009d7e  mov     eax, [r8+8]
0x180009d82  add     [rcx+8], eax
0x180009d85  mov     r9d, [rsp+1090h+var_1050]
0x180009d8a  jmp     short loc_180009D10
```
