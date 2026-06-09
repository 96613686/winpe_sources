# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180019a00`
- end: `0x180019c38`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180013930`

## callees

- `0x1800016d0`
- `0x180002024`
- `0x180019a00`
- `0x180019cd0`
- `0x18002ad30`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019aa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180019aa0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019a89`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180019a89`

## string_xrefs

- `0x180019a82`: `ntdll.dll`

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
0x180019a00  push    rbp
0x180019a02  push    rbx
0x180019a03  push    rsi
0x180019a04  push    rdi
0x180019a05  push    r14
0x180019a07  push    r15
0x180019a09  lea     rbp, [rsp-0F68h]
0x180019a11  mov     eax, 1068h
0x180019a16  call    _alloca_probe
0x180019a1b  sub     rsp, rax
0x180019a1e  mov     rax, cs:__security_cookie
0x180019a25  xor     rax, rsp
0x180019a28  mov     [rbp+0F90h+var_40], rax
0x180019a2f  mov     rax, [rcx+8]
0x180019a33  xor     ebx, ebx
0x180019a35  sub     rax, [rcx]
0x180019a38  xor     esi, esi
0x180019a3a  mov     r14, rcx
0x180019a3d  cmp     rax, 0Ch
0x180019a41  jb      loc_180019C04
0x180019a47  xor     r15d, r15d
0x180019a4a  xor     edx, edx; Val
0x180019a4c  lea     rcx, [rsp+1090h+var_1040]; void *
0x180019a51  mov     r8d, 1000h; Size
0x180019a57  call    memset_0
0x180019a5c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180019a64  mov     [rsp+1090h+var_1050], 1000h
0x180019a6c  mov     [rsp+1090h+var_104C], 0
0x180019a74  jnz     short loc_180019ABE
0x180019a76  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019a7d  test    rax, rax
0x180019a80  jnz     short loc_180019A96
0x180019a82  lea     rcx, ModuleName; "ntdll.dll"
0x180019a89  call    cs:__imp_GetModuleHandleW
0x180019a8f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180019a96  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180019a9d  mov     rcx, rax; hModule
0x180019aa0  call    cs:__imp_GetProcAddress
0x180019aa6  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180019aad  test    rax, rax
0x180019ab0  jnz     short loc_180019ABE
0x180019ab2  mov     edi, 0C0000139h
0x180019ab7  mov     ebx, edi
0x180019ab9  jmp     loc_180019BEB
0x180019abe  lea     rax, [rsp+1090h+var_1050]
0x180019ac3  xor     r8d, r8d
0x180019ac6  mov     [rsp+1090h+var_1068], rax
0x180019acb  lea     r9, [rsp+1090h+var_104C]
0x180019ad0  lea     rax, [rsp+1090h+var_1040]
0x180019ad5  xor     edx, edx
0x180019ad7  mov     [rsp+1090h+var_1070], rax
0x180019adc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180019ae3  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180019aea  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180019aef  mov     ebx, eax
0x180019af1  mov     edi, eax
0x180019af3  test    eax, eax
0x180019af5  jnz     loc_180019BEB
0x180019afb  mov     r9d, [rsp+1090h+var_1050]
0x180019b00  mov     r11, 0AAAAAAAAAAAAAAABh
0x180019b0a  mov     rax, r11
0x180019b0d  mul     r9
0x180019b10  shr     rdx, 3
0x180019b14  lea     rcx, [rdx+rdx*2]
0x180019b18  shl     rcx, 2
0x180019b1c  cmp     r9, rcx
0x180019b1f  jz      short loc_180019B29
0x180019b21  xor     r9d, r9d
0x180019b24  mov     [rsp+1090h+var_1050], r9d
0x180019b29  mov     r8, [r14]
0x180019b2c  mov     rax, r11
0x180019b2f  mov     ecx, r9d
0x180019b32  mul     rcx
0x180019b35  mov     rcx, [r14+8]
0x180019b39  mov     rax, r11
0x180019b3c  mov     r10, rdx
0x180019b3f  sub     rcx, r8
0x180019b42  mul     rcx
0x180019b45  shr     r10, 3
0x180019b49  shr     rdx, 3
0x180019b4d  lea     rax, [rdx+rdx*2]
0x180019b51  lea     rsi, [r8+rax*4]
0x180019b55  jmp     short loc_180019BC0
0x180019b57  mov     eax, r10d
0x180019b5a  lea     rcx, [rax+rax*2]
0x180019b5e  lea     rdx, [rdx+rcx*4]
0x180019b62  lea     rax, [rsp+1090h+var_1040]
0x180019b67  cmp     rax, rdx
0x180019b6a  jz      short loc_180019B91
0x180019b6c  mov     r11d, [r8]
0x180019b6f  lea     rcx, [rsp+1090h+var_1040]
0x180019b74  cmp     [rcx], r11d
0x180019b77  jnz     short loc_180019B88
0x180019b79  movzx   eax, word ptr [r8+4]
0x180019b7e  cmp     [rcx+4], ax
0x180019b82  jz      loc_180019C2A
0x180019b88  add     rcx, 0Ch
0x180019b8c  cmp     rcx, rdx
0x180019b8f  jnz     short loc_180019B74
0x180019b91  mov     eax, r9d
0x180019b94  add     rax, 0Ch
0x180019b98  cmp     rax, 1000h
0x180019b9e  ja      short loc_180019BBC
0x180019ba0  movsd   xmm0, qword ptr [r8]
0x180019ba5  add     r9d, 0Ch
0x180019ba9  movsd   qword ptr [rdx], xmm0
0x180019bad  inc     r10d
0x180019bb0  mov     eax, [r8+8]
0x180019bb4  mov     [rdx+8], eax
0x180019bb7  mov     [rsp+1090h+var_1050], r9d
0x180019bbc  add     r8, 0Ch
0x180019bc0  lea     rdx, [rsp+1090h+var_1040]
0x180019bc5  cmp     r8, rsi
0x180019bc8  jnz     short loc_180019B57
0x180019bca  mov     eax, [rsp+1090h+var_104C]
0x180019bce  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180019bd5  mov     [rsp+1090h+var_1060], 1
0x180019bdd  mov     r8d, r9d
0x180019be0  mov     dword ptr [rsp+1090h+var_1068], eax
0x180019be4  call    wil_details_NtUpdateWnfStateData
0x180019be9  mov     esi, eax
0x180019beb  cmp     esi, 0C0000001h
0x180019bf1  jnz     short loc_180019C04
0x180019bf3  inc     r15d
0x180019bf6  cmp     r15d, 64h ; 'd'
0x180019bfa  jge     short loc_180019C04
0x180019bfc  test    edi, edi
0x180019bfe  jz      loc_180019A4A
0x180019c04  test    ebx, ebx
0x180019c06  cmovz   ebx, esi
0x180019c09  mov     eax, ebx
0x180019c0b  mov     rcx, [rbp+0F90h+var_40]
0x180019c12  xor     rcx, rsp; StackCookie
0x180019c15  call    __security_check_cookie
0x180019c1a  add     rsp, 1068h
0x180019c21  pop     r15
0x180019c23  pop     r14
0x180019c25  pop     rdi
0x180019c26  pop     rsi
0x180019c27  pop     rbx
0x180019c28  pop     rbp
0x180019c29  retn
0x180019c2a  mov     eax, [r8+8]
0x180019c2e  add     [rcx+8], eax
0x180019c31  mov     r9d, [rsp+1090h+var_1050]
0x180019c36  jmp     short loc_180019BBC
```
