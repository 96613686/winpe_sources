# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180015aa4`
- end: `0x180015cdc`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180011ef0`

## callees

- `0x1800026b0`
- `0x18000316c`
- `0x180015aa4`
- `0x1800162d0`
- `0x18004bab0`
- `0x18004f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015b2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015b2d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015b44`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015b44`

## string_xrefs

- `0x180015b26`: `ntdll.dll`

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
0x180015aa4  push    rbp
0x180015aa6  push    rbx
0x180015aa7  push    rsi
0x180015aa8  push    rdi
0x180015aa9  push    r14
0x180015aab  push    r15
0x180015aad  lea     rbp, [rsp-0F68h]
0x180015ab5  mov     eax, 1068h
0x180015aba  call    _alloca_probe
0x180015abf  sub     rsp, rax
0x180015ac2  mov     rax, cs:__security_cookie
0x180015ac9  xor     rax, rsp
0x180015acc  mov     [rbp+0F90h+var_40], rax
0x180015ad3  mov     rax, [rcx+8]
0x180015ad7  xor     ebx, ebx
0x180015ad9  sub     rax, [rcx]
0x180015adc  xor     esi, esi
0x180015ade  mov     r14, rcx
0x180015ae1  cmp     rax, 0Ch
0x180015ae5  jb      loc_180015CA8
0x180015aeb  xor     r15d, r15d
0x180015aee  xor     edx, edx; Val
0x180015af0  lea     rcx, [rsp+1090h+var_1040]; void *
0x180015af5  mov     r8d, 1000h; Size
0x180015afb  call    memset_0
0x180015b00  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180015b08  mov     [rsp+1090h+var_1050], 1000h
0x180015b10  mov     [rsp+1090h+var_104C], 0
0x180015b18  jnz     short loc_180015B62
0x180015b1a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015b21  test    rax, rax
0x180015b24  jnz     short loc_180015B3A
0x180015b26  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180015b2d  call    cs:__imp_GetModuleHandleW
0x180015b33  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015b3a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180015b41  mov     rcx, rax; hModule
0x180015b44  call    cs:__imp_GetProcAddress
0x180015b4a  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180015b51  test    rax, rax
0x180015b54  jnz     short loc_180015B62
0x180015b56  mov     edi, 0C0000139h
0x180015b5b  mov     ebx, edi
0x180015b5d  jmp     loc_180015C8F
0x180015b62  lea     rax, [rsp+1090h+var_1050]
0x180015b67  xor     r8d, r8d
0x180015b6a  mov     [rsp+1090h+var_1068], rax
0x180015b6f  lea     r9, [rsp+1090h+var_104C]
0x180015b74  lea     rax, [rsp+1090h+var_1040]
0x180015b79  xor     edx, edx
0x180015b7b  mov     [rsp+1090h+var_1070], rax
0x180015b80  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180015b87  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180015b8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015b93  mov     ebx, eax
0x180015b95  mov     edi, eax
0x180015b97  test    eax, eax
0x180015b99  jnz     loc_180015C8F
0x180015b9f  mov     r9d, [rsp+1090h+var_1050]
0x180015ba4  mov     r11, 0AAAAAAAAAAAAAAABh
0x180015bae  mov     rax, r11
0x180015bb1  mul     r9
0x180015bb4  shr     rdx, 3
0x180015bb8  lea     rcx, [rdx+rdx*2]
0x180015bbc  shl     rcx, 2
0x180015bc0  cmp     r9, rcx
0x180015bc3  jz      short loc_180015BCD
0x180015bc5  xor     r9d, r9d
0x180015bc8  mov     [rsp+1090h+var_1050], r9d
0x180015bcd  mov     r8, [r14]
0x180015bd0  mov     rax, r11
0x180015bd3  mov     ecx, r9d
0x180015bd6  mul     rcx
0x180015bd9  mov     rcx, [r14+8]
0x180015bdd  mov     rax, r11
0x180015be0  mov     r10, rdx
0x180015be3  sub     rcx, r8
0x180015be6  mul     rcx
0x180015be9  shr     r10, 3
0x180015bed  shr     rdx, 3
0x180015bf1  lea     rax, [rdx+rdx*2]
0x180015bf5  lea     rsi, [r8+rax*4]
0x180015bf9  jmp     short loc_180015C64
0x180015bfb  mov     eax, r10d
0x180015bfe  lea     rcx, [rax+rax*2]
0x180015c02  lea     rdx, [rdx+rcx*4]
0x180015c06  lea     rax, [rsp+1090h+var_1040]
0x180015c0b  cmp     rax, rdx
0x180015c0e  jz      short loc_180015C35
0x180015c10  mov     r11d, [r8]
0x180015c13  lea     rcx, [rsp+1090h+var_1040]
0x180015c18  cmp     [rcx], r11d
0x180015c1b  jnz     short loc_180015C2C
0x180015c1d  movzx   eax, word ptr [r8+4]
0x180015c22  cmp     [rcx+4], ax
0x180015c26  jz      loc_180015CCE
0x180015c2c  add     rcx, 0Ch
0x180015c30  cmp     rcx, rdx
0x180015c33  jnz     short loc_180015C18
0x180015c35  mov     eax, r9d
0x180015c38  add     rax, 0Ch
0x180015c3c  cmp     rax, 1000h
0x180015c42  ja      short loc_180015C60
0x180015c44  movsd   xmm0, qword ptr [r8]
0x180015c49  add     r9d, 0Ch
0x180015c4d  movsd   qword ptr [rdx], xmm0
0x180015c51  inc     r10d
0x180015c54  mov     eax, [r8+8]
0x180015c58  mov     [rdx+8], eax
0x180015c5b  mov     [rsp+1090h+var_1050], r9d
0x180015c60  add     r8, 0Ch
0x180015c64  lea     rdx, [rsp+1090h+var_1040]
0x180015c69  cmp     r8, rsi
0x180015c6c  jnz     short loc_180015BFB
0x180015c6e  mov     eax, [rsp+1090h+var_104C]
0x180015c72  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180015c79  mov     [rsp+1090h+var_1060], 1
0x180015c81  mov     r8d, r9d
0x180015c84  mov     dword ptr [rsp+1090h+var_1068], eax
0x180015c88  call    wil_details_NtUpdateWnfStateData
0x180015c8d  mov     esi, eax
0x180015c8f  cmp     esi, 0C0000001h
0x180015c95  jnz     short loc_180015CA8
0x180015c97  inc     r15d
0x180015c9a  cmp     r15d, 64h ; 'd'
0x180015c9e  jge     short loc_180015CA8
0x180015ca0  test    edi, edi
0x180015ca2  jz      loc_180015AEE
0x180015ca8  test    ebx, ebx
0x180015caa  cmovz   ebx, esi
0x180015cad  mov     eax, ebx
0x180015caf  mov     rcx, [rbp+0F90h+var_40]
0x180015cb6  xor     rcx, rsp; StackCookie
0x180015cb9  call    __security_check_cookie
0x180015cbe  add     rsp, 1068h
0x180015cc5  pop     r15
0x180015cc7  pop     r14
0x180015cc9  pop     rdi
0x180015cca  pop     rsi
0x180015ccb  pop     rbx
0x180015ccc  pop     rbp
0x180015ccd  retn
0x180015cce  mov     eax, [r8+8]
0x180015cd2  add     [rcx+8], eax
0x180015cd5  mov     r9d, [rsp+1090h+var_1050]
0x180015cda  jmp     short loc_180015C60
```
