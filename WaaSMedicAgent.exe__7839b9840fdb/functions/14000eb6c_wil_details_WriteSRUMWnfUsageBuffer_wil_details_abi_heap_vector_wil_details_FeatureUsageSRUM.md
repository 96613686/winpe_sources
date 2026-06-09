# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000eb6c`
- end: `0x14000eda4`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x14000b870`

## callees

- `0x140002a30`
- `0x14000369c`
- `0x14000eb6c`
- `0x14000ee14`
- `0x140011fc0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ec0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ec0c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ebf5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ebf5`

## string_xrefs

- `0x14000ebee`: `ntdll.dll`

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
0x14000eb6c  push    rbp
0x14000eb6e  push    rbx
0x14000eb6f  push    rsi
0x14000eb70  push    rdi
0x14000eb71  push    r14
0x14000eb73  push    r15
0x14000eb75  lea     rbp, [rsp-0F68h]
0x14000eb7d  mov     eax, 1068h
0x14000eb82  call    _alloca_probe
0x14000eb87  sub     rsp, rax
0x14000eb8a  mov     rax, cs:__security_cookie
0x14000eb91  xor     rax, rsp
0x14000eb94  mov     [rbp+0F90h+var_40], rax
0x14000eb9b  mov     rax, [rcx+8]
0x14000eb9f  xor     ebx, ebx
0x14000eba1  sub     rax, [rcx]
0x14000eba4  xor     esi, esi
0x14000eba6  mov     r14, rcx
0x14000eba9  cmp     rax, 0Ch
0x14000ebad  jb      loc_14000ED70
0x14000ebb3  xor     r15d, r15d
0x14000ebb6  xor     edx, edx; Val
0x14000ebb8  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000ebbd  mov     r8d, 1000h; Size
0x14000ebc3  call    memset_0
0x14000ebc8  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000ebd0  mov     [rsp+1090h+var_1050], 1000h
0x14000ebd8  mov     [rsp+1090h+var_104C], 0
0x14000ebe0  jnz     short loc_14000EC2A
0x14000ebe2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ebe9  test    rax, rax
0x14000ebec  jnz     short loc_14000EC02
0x14000ebee  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000ebf5  call    cs:__imp_GetModuleHandleW
0x14000ebfb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ec02  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000ec09  mov     rcx, rax; hModule
0x14000ec0c  call    cs:__imp_GetProcAddress
0x14000ec12  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000ec19  test    rax, rax
0x14000ec1c  jnz     short loc_14000EC2A
0x14000ec1e  mov     edi, 0C0000139h
0x14000ec23  mov     ebx, edi
0x14000ec25  jmp     loc_14000ED57
0x14000ec2a  lea     rax, [rsp+1090h+var_1050]
0x14000ec2f  xor     r8d, r8d
0x14000ec32  mov     [rsp+1090h+var_1068], rax
0x14000ec37  lea     r9, [rsp+1090h+var_104C]
0x14000ec3c  lea     rax, [rsp+1090h+var_1040]
0x14000ec41  xor     edx, edx
0x14000ec43  mov     [rsp+1090h+var_1070], rax
0x14000ec48  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000ec4f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000ec56  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ec5b  mov     ebx, eax
0x14000ec5d  mov     edi, eax
0x14000ec5f  test    eax, eax
0x14000ec61  jnz     loc_14000ED57
0x14000ec67  mov     r9d, [rsp+1090h+var_1050]
0x14000ec6c  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000ec76  mov     rax, r11
0x14000ec79  mul     r9
0x14000ec7c  shr     rdx, 3
0x14000ec80  lea     rcx, [rdx+rdx*2]
0x14000ec84  shl     rcx, 2
0x14000ec88  cmp     r9, rcx
0x14000ec8b  jz      short loc_14000EC95
0x14000ec8d  xor     r9d, r9d
0x14000ec90  mov     [rsp+1090h+var_1050], r9d
0x14000ec95  mov     r8, [r14]
0x14000ec98  mov     rax, r11
0x14000ec9b  mov     ecx, r9d
0x14000ec9e  mul     rcx
0x14000eca1  mov     rcx, [r14+8]
0x14000eca5  mov     rax, r11
0x14000eca8  mov     r10, rdx
0x14000ecab  sub     rcx, r8
0x14000ecae  mul     rcx
0x14000ecb1  shr     r10, 3
0x14000ecb5  shr     rdx, 3
0x14000ecb9  lea     rax, [rdx+rdx*2]
0x14000ecbd  lea     rsi, [r8+rax*4]
0x14000ecc1  jmp     short loc_14000ED2C
0x14000ecc3  mov     eax, r10d
0x14000ecc6  lea     rcx, [rax+rax*2]
0x14000ecca  lea     rdx, [rdx+rcx*4]
0x14000ecce  lea     rax, [rsp+1090h+var_1040]
0x14000ecd3  cmp     rax, rdx
0x14000ecd6  jz      short loc_14000ECFD
0x14000ecd8  mov     r11d, [r8]
0x14000ecdb  lea     rcx, [rsp+1090h+var_1040]
0x14000ece0  cmp     [rcx], r11d
0x14000ece3  jnz     short loc_14000ECF4
0x14000ece5  movzx   eax, word ptr [r8+4]
0x14000ecea  cmp     [rcx+4], ax
0x14000ecee  jz      loc_14000ED96
0x14000ecf4  add     rcx, 0Ch
0x14000ecf8  cmp     rcx, rdx
0x14000ecfb  jnz     short loc_14000ECE0
0x14000ecfd  mov     eax, r9d
0x14000ed00  add     rax, 0Ch
0x14000ed04  cmp     rax, 1000h
0x14000ed0a  ja      short loc_14000ED28
0x14000ed0c  movsd   xmm0, qword ptr [r8]
0x14000ed11  add     r9d, 0Ch
0x14000ed15  movsd   qword ptr [rdx], xmm0
0x14000ed19  inc     r10d
0x14000ed1c  mov     eax, [r8+8]
0x14000ed20  mov     [rdx+8], eax
0x14000ed23  mov     [rsp+1090h+var_1050], r9d
0x14000ed28  add     r8, 0Ch
0x14000ed2c  lea     rdx, [rsp+1090h+var_1040]
0x14000ed31  cmp     r8, rsi
0x14000ed34  jnz     short loc_14000ECC3
0x14000ed36  mov     eax, [rsp+1090h+var_104C]
0x14000ed3a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000ed41  mov     [rsp+1090h+var_1060], 1
0x14000ed49  mov     r8d, r9d
0x14000ed4c  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000ed50  call    wil_details_NtUpdateWnfStateData
0x14000ed55  mov     esi, eax
0x14000ed57  cmp     esi, 0C0000001h
0x14000ed5d  jnz     short loc_14000ED70
0x14000ed5f  inc     r15d
0x14000ed62  cmp     r15d, 64h ; 'd'
0x14000ed66  jge     short loc_14000ED70
0x14000ed68  test    edi, edi
0x14000ed6a  jz      loc_14000EBB6
0x14000ed70  test    ebx, ebx
0x14000ed72  cmovz   ebx, esi
0x14000ed75  mov     eax, ebx
0x14000ed77  mov     rcx, [rbp+0F90h+var_40]
0x14000ed7e  xor     rcx, rsp; StackCookie
0x14000ed81  call    __security_check_cookie
0x14000ed86  add     rsp, 1068h
0x14000ed8d  pop     r15
0x14000ed8f  pop     r14
0x14000ed91  pop     rdi
0x14000ed92  pop     rsi
0x14000ed93  pop     rbx
0x14000ed94  pop     rbp
0x14000ed95  retn
0x14000ed96  mov     eax, [r8+8]
0x14000ed9a  add     [rcx+8], eax
0x14000ed9d  mov     r9d, [rsp+1090h+var_1050]
0x14000eda2  jmp     short loc_14000ED28
```
