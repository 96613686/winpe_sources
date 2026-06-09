# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000eb7c`
- end: `0x18000edb4`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800093f0`

## callees

- `0x18000eb7c`
- `0x18000edbc`
- `0x18001143a`
- `0x180011460`
- `0x180011520`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ec1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ec1c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ec05`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ec05`

## string_xrefs

- `0x18000ebfe`: `ntdll.dll`

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
0x18000eb7c  push    rbp
0x18000eb7e  push    rbx
0x18000eb7f  push    rsi
0x18000eb80  push    rdi
0x18000eb81  push    r14
0x18000eb83  push    r15
0x18000eb85  lea     rbp, [rsp-0F68h]
0x18000eb8d  mov     eax, 1068h
0x18000eb92  call    _alloca_probe
0x18000eb97  sub     rsp, rax
0x18000eb9a  mov     rax, cs:__security_cookie
0x18000eba1  xor     rax, rsp
0x18000eba4  mov     [rbp+0F90h+var_40], rax
0x18000ebab  mov     rax, [rcx+8]
0x18000ebaf  xor     ebx, ebx
0x18000ebb1  sub     rax, [rcx]
0x18000ebb4  xor     esi, esi
0x18000ebb6  mov     r14, rcx
0x18000ebb9  cmp     rax, 0Ch
0x18000ebbd  jb      loc_18000ED80
0x18000ebc3  xor     r15d, r15d
0x18000ebc6  xor     edx, edx; Val
0x18000ebc8  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ebcd  mov     r8d, 1000h; Size
0x18000ebd3  call    memset_0
0x18000ebd8  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000ebe0  mov     [rsp+1090h+var_1050], 1000h
0x18000ebe8  mov     [rsp+1090h+var_104C], 0
0x18000ebf0  jnz     short loc_18000EC3A
0x18000ebf2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ebf9  test    rax, rax
0x18000ebfc  jnz     short loc_18000EC12
0x18000ebfe  lea     rcx, ModuleName; "ntdll.dll"
0x18000ec05  call    cs:__imp_GetModuleHandleW
0x18000ec0b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ec12  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000ec19  mov     rcx, rax; hModule
0x18000ec1c  call    cs:__imp_GetProcAddress
0x18000ec22  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000ec29  test    rax, rax
0x18000ec2c  jnz     short loc_18000EC3A
0x18000ec2e  mov     edi, 0C0000139h
0x18000ec33  mov     ebx, edi
0x18000ec35  jmp     loc_18000ED67
0x18000ec3a  lea     rax, [rsp+1090h+var_1050]
0x18000ec3f  xor     r8d, r8d
0x18000ec42  mov     [rsp+1090h+var_1068], rax
0x18000ec47  lea     r9, [rsp+1090h+var_104C]
0x18000ec4c  lea     rax, [rsp+1090h+var_1040]
0x18000ec51  xor     edx, edx
0x18000ec53  mov     [rsp+1090h+var_1070], rax
0x18000ec58  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ec5f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000ec66  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ec6b  mov     ebx, eax
0x18000ec6d  mov     edi, eax
0x18000ec6f  test    eax, eax
0x18000ec71  jnz     loc_18000ED67
0x18000ec77  mov     r9d, [rsp+1090h+var_1050]
0x18000ec7c  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000ec86  mov     rax, r11
0x18000ec89  mul     r9
0x18000ec8c  shr     rdx, 3
0x18000ec90  lea     rcx, [rdx+rdx*2]
0x18000ec94  shl     rcx, 2
0x18000ec98  cmp     r9, rcx
0x18000ec9b  jz      short loc_18000ECA5
0x18000ec9d  xor     r9d, r9d
0x18000eca0  mov     [rsp+1090h+var_1050], r9d
0x18000eca5  mov     r8, [r14]
0x18000eca8  mov     rax, r11
0x18000ecab  mov     ecx, r9d
0x18000ecae  mul     rcx
0x18000ecb1  mov     rcx, [r14+8]
0x18000ecb5  mov     rax, r11
0x18000ecb8  mov     r10, rdx
0x18000ecbb  sub     rcx, r8
0x18000ecbe  mul     rcx
0x18000ecc1  shr     r10, 3
0x18000ecc5  shr     rdx, 3
0x18000ecc9  lea     rax, [rdx+rdx*2]
0x18000eccd  lea     rsi, [r8+rax*4]
0x18000ecd1  jmp     short loc_18000ED3C
0x18000ecd3  mov     eax, r10d
0x18000ecd6  lea     rcx, [rax+rax*2]
0x18000ecda  lea     rdx, [rdx+rcx*4]
0x18000ecde  lea     rax, [rsp+1090h+var_1040]
0x18000ece3  cmp     rax, rdx
0x18000ece6  jz      short loc_18000ED0D
0x18000ece8  mov     r11d, [r8]
0x18000eceb  lea     rcx, [rsp+1090h+var_1040]
0x18000ecf0  cmp     [rcx], r11d
0x18000ecf3  jnz     short loc_18000ED04
0x18000ecf5  movzx   eax, word ptr [r8+4]
0x18000ecfa  cmp     [rcx+4], ax
0x18000ecfe  jz      loc_18000EDA6
0x18000ed04  add     rcx, 0Ch
0x18000ed08  cmp     rcx, rdx
0x18000ed0b  jnz     short loc_18000ECF0
0x18000ed0d  mov     eax, r9d
0x18000ed10  add     rax, 0Ch
0x18000ed14  cmp     rax, 1000h
0x18000ed1a  ja      short loc_18000ED38
0x18000ed1c  movsd   xmm0, qword ptr [r8]
0x18000ed21  add     r9d, 0Ch
0x18000ed25  movsd   qword ptr [rdx], xmm0
0x18000ed29  inc     r10d
0x18000ed2c  mov     eax, [r8+8]
0x18000ed30  mov     [rdx+8], eax
0x18000ed33  mov     [rsp+1090h+var_1050], r9d
0x18000ed38  add     r8, 0Ch
0x18000ed3c  lea     rdx, [rsp+1090h+var_1040]
0x18000ed41  cmp     r8, rsi
0x18000ed44  jnz     short loc_18000ECD3
0x18000ed46  mov     eax, [rsp+1090h+var_104C]
0x18000ed4a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ed51  mov     [rsp+1090h+var_1060], 1
0x18000ed59  mov     r8d, r9d
0x18000ed5c  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000ed60  call    wil_details_NtUpdateWnfStateData
0x18000ed65  mov     esi, eax
0x18000ed67  cmp     esi, 0C0000001h
0x18000ed6d  jnz     short loc_18000ED80
0x18000ed6f  inc     r15d
0x18000ed72  cmp     r15d, 64h ; 'd'
0x18000ed76  jge     short loc_18000ED80
0x18000ed78  test    edi, edi
0x18000ed7a  jz      loc_18000EBC6
0x18000ed80  test    ebx, ebx
0x18000ed82  cmovz   ebx, esi
0x18000ed85  mov     eax, ebx
0x18000ed87  mov     rcx, [rbp+0F90h+var_40]
0x18000ed8e  xor     rcx, rsp; StackCookie
0x18000ed91  call    __security_check_cookie
0x18000ed96  add     rsp, 1068h
0x18000ed9d  pop     r15
0x18000ed9f  pop     r14
0x18000eda1  pop     rdi
0x18000eda2  pop     rsi
0x18000eda3  pop     rbx
0x18000eda4  pop     rbp
0x18000eda5  retn
0x18000eda6  mov     eax, [r8+8]
0x18000edaa  add     [rcx+8], eax
0x18000edad  mov     r9d, [rsp+1090h+var_1050]
0x18000edb2  jmp     short loc_18000ED38
```
