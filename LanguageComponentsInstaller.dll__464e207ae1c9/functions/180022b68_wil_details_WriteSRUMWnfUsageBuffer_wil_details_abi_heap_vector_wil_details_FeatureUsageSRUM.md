# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180022b68`
- end: `0x180022da0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000adc0`

## callees

- `0x180003520`
- `0x180004118`
- `0x180022b68`
- `0x180023c18`
- `0x180027cb0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022c08`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180022c08`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022bf1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180022bf1`

## string_xrefs

- `0x180022bea`: `ntdll.dll`

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
0x180022b68  push    rbp
0x180022b6a  push    rbx
0x180022b6b  push    rsi
0x180022b6c  push    rdi
0x180022b6d  push    r14
0x180022b6f  push    r15
0x180022b71  lea     rbp, [rsp-0F68h]
0x180022b79  mov     eax, 1068h
0x180022b7e  call    _alloca_probe
0x180022b83  sub     rsp, rax
0x180022b86  mov     rax, cs:__security_cookie
0x180022b8d  xor     rax, rsp
0x180022b90  mov     [rbp+0F90h+var_40], rax
0x180022b97  mov     rax, [rcx+8]
0x180022b9b  xor     ebx, ebx
0x180022b9d  sub     rax, [rcx]
0x180022ba0  xor     esi, esi
0x180022ba2  mov     r14, rcx
0x180022ba5  cmp     rax, 0Ch
0x180022ba9  jb      loc_180022D6C
0x180022baf  xor     r15d, r15d
0x180022bb2  xor     edx, edx; Val
0x180022bb4  lea     rcx, [rsp+1090h+var_1040]; void *
0x180022bb9  mov     r8d, 1000h; Size
0x180022bbf  call    memset_0
0x180022bc4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180022bcc  mov     [rsp+1090h+var_1050], 1000h
0x180022bd4  mov     [rsp+1090h+var_104C], 0
0x180022bdc  jnz     short loc_180022C26
0x180022bde  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022be5  test    rax, rax
0x180022be8  jnz     short loc_180022BFE
0x180022bea  lea     rcx, ModuleName; "ntdll.dll"
0x180022bf1  call    cs:__imp_GetModuleHandleW
0x180022bf7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180022bfe  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180022c05  mov     rcx, rax; hModule
0x180022c08  call    cs:__imp_GetProcAddress
0x180022c0e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180022c15  test    rax, rax
0x180022c18  jnz     short loc_180022C26
0x180022c1a  mov     edi, 0C0000139h
0x180022c1f  mov     ebx, edi
0x180022c21  jmp     loc_180022D53
0x180022c26  lea     rax, [rsp+1090h+var_1050]
0x180022c2b  xor     r8d, r8d
0x180022c2e  mov     [rsp+1090h+var_1068], rax
0x180022c33  lea     r9, [rsp+1090h+var_104C]
0x180022c38  lea     rax, [rsp+1090h+var_1040]
0x180022c3d  xor     edx, edx
0x180022c3f  mov     [rsp+1090h+var_1070], rax
0x180022c44  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180022c4b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180022c52  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180022c57  mov     ebx, eax
0x180022c59  mov     edi, eax
0x180022c5b  test    eax, eax
0x180022c5d  jnz     loc_180022D53
0x180022c63  mov     r9d, [rsp+1090h+var_1050]
0x180022c68  mov     r11, 0AAAAAAAAAAAAAAABh
0x180022c72  mov     rax, r11
0x180022c75  mul     r9
0x180022c78  shr     rdx, 3
0x180022c7c  lea     rcx, [rdx+rdx*2]
0x180022c80  shl     rcx, 2
0x180022c84  cmp     r9, rcx
0x180022c87  jz      short loc_180022C91
0x180022c89  xor     r9d, r9d
0x180022c8c  mov     [rsp+1090h+var_1050], r9d
0x180022c91  mov     r8, [r14]
0x180022c94  mov     rax, r11
0x180022c97  mov     ecx, r9d
0x180022c9a  mul     rcx
0x180022c9d  mov     rcx, [r14+8]
0x180022ca1  mov     rax, r11
0x180022ca4  mov     r10, rdx
0x180022ca7  sub     rcx, r8
0x180022caa  mul     rcx
0x180022cad  shr     r10, 3
0x180022cb1  shr     rdx, 3
0x180022cb5  lea     rax, [rdx+rdx*2]
0x180022cb9  lea     rsi, [r8+rax*4]
0x180022cbd  jmp     short loc_180022D28
0x180022cbf  mov     eax, r10d
0x180022cc2  lea     rcx, [rax+rax*2]
0x180022cc6  lea     rdx, [rdx+rcx*4]
0x180022cca  lea     rax, [rsp+1090h+var_1040]
0x180022ccf  cmp     rax, rdx
0x180022cd2  jz      short loc_180022CF9
0x180022cd4  mov     r11d, [r8]
0x180022cd7  lea     rcx, [rsp+1090h+var_1040]
0x180022cdc  cmp     [rcx], r11d
0x180022cdf  jnz     short loc_180022CF0
0x180022ce1  movzx   eax, word ptr [r8+4]
0x180022ce6  cmp     [rcx+4], ax
0x180022cea  jz      loc_180022D92
0x180022cf0  add     rcx, 0Ch
0x180022cf4  cmp     rcx, rdx
0x180022cf7  jnz     short loc_180022CDC
0x180022cf9  mov     eax, r9d
0x180022cfc  add     rax, 0Ch
0x180022d00  cmp     rax, 1000h
0x180022d06  ja      short loc_180022D24
0x180022d08  movsd   xmm0, qword ptr [r8]
0x180022d0d  add     r9d, 0Ch
0x180022d11  movsd   qword ptr [rdx], xmm0
0x180022d15  inc     r10d
0x180022d18  mov     eax, [r8+8]
0x180022d1c  mov     [rdx+8], eax
0x180022d1f  mov     [rsp+1090h+var_1050], r9d
0x180022d24  add     r8, 0Ch
0x180022d28  lea     rdx, [rsp+1090h+var_1040]
0x180022d2d  cmp     r8, rsi
0x180022d30  jnz     short loc_180022CBF
0x180022d32  mov     eax, [rsp+1090h+var_104C]
0x180022d36  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180022d3d  mov     [rsp+1090h+var_1060], 1
0x180022d45  mov     r8d, r9d
0x180022d48  mov     dword ptr [rsp+1090h+var_1068], eax
0x180022d4c  call    wil_details_NtUpdateWnfStateData
0x180022d51  mov     esi, eax
0x180022d53  cmp     esi, 0C0000001h
0x180022d59  jnz     short loc_180022D6C
0x180022d5b  inc     r15d
0x180022d5e  cmp     r15d, 64h ; 'd'
0x180022d62  jge     short loc_180022D6C
0x180022d64  test    edi, edi
0x180022d66  jz      loc_180022BB2
0x180022d6c  test    ebx, ebx
0x180022d6e  cmovz   ebx, esi
0x180022d71  mov     eax, ebx
0x180022d73  mov     rcx, [rbp+0F90h+var_40]
0x180022d7a  xor     rcx, rsp; StackCookie
0x180022d7d  call    __security_check_cookie
0x180022d82  add     rsp, 1068h
0x180022d89  pop     r15
0x180022d8b  pop     r14
0x180022d8d  pop     rdi
0x180022d8e  pop     rsi
0x180022d8f  pop     rbx
0x180022d90  pop     rbp
0x180022d91  retn
0x180022d92  mov     eax, [r8+8]
0x180022d96  add     [rcx+8], eax
0x180022d99  mov     r9d, [rsp+1090h+var_1050]
0x180022d9e  jmp     short loc_180022D24
```
