# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000fec8`
- end: `0x180010100`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180008980`

## callees

- `0x1800028f0`
- `0x1800033e8`
- `0x18000fec8`
- `0x180010390`
- `0x180027600`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ff51`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ff51`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ff68`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ff68`

## string_xrefs

- `0x18000ff4a`: `ntdll.dll`

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
0x18000fec8  push    rbp
0x18000feca  push    rbx
0x18000fecb  push    rsi
0x18000fecc  push    rdi
0x18000fecd  push    r14
0x18000fecf  push    r15
0x18000fed1  lea     rbp, [rsp-0F68h]
0x18000fed9  mov     eax, 1068h
0x18000fede  call    _alloca_probe
0x18000fee3  sub     rsp, rax
0x18000fee6  mov     rax, cs:__security_cookie
0x18000feed  xor     rax, rsp
0x18000fef0  mov     [rbp+0F90h+var_40], rax
0x18000fef7  mov     rax, [rcx+8]
0x18000fefb  xor     ebx, ebx
0x18000fefd  sub     rax, [rcx]
0x18000ff00  xor     esi, esi
0x18000ff02  mov     r14, rcx
0x18000ff05  cmp     rax, 0Ch
0x18000ff09  jb      loc_1800100CC
0x18000ff0f  xor     r15d, r15d
0x18000ff12  xor     edx, edx; Val
0x18000ff14  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ff19  mov     r8d, 1000h; Size
0x18000ff1f  call    memset_0
0x18000ff24  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000ff2c  mov     [rsp+1090h+var_1050], 1000h
0x18000ff34  mov     [rsp+1090h+var_104C], 0
0x18000ff3c  jnz     short loc_18000FF86
0x18000ff3e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ff45  test    rax, rax
0x18000ff48  jnz     short loc_18000FF5E
0x18000ff4a  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000ff51  call    cs:__imp_GetModuleHandleW
0x18000ff57  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ff5e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000ff65  mov     rcx, rax; hModule
0x18000ff68  call    cs:__imp_GetProcAddress
0x18000ff6e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000ff75  test    rax, rax
0x18000ff78  jnz     short loc_18000FF86
0x18000ff7a  mov     edi, 0C0000139h
0x18000ff7f  mov     ebx, edi
0x18000ff81  jmp     loc_1800100B3
0x18000ff86  lea     rax, [rsp+1090h+var_1050]
0x18000ff8b  xor     r8d, r8d
0x18000ff8e  mov     [rsp+1090h+var_1068], rax
0x18000ff93  lea     r9, [rsp+1090h+var_104C]
0x18000ff98  lea     rax, [rsp+1090h+var_1040]
0x18000ff9d  xor     edx, edx
0x18000ff9f  mov     [rsp+1090h+var_1070], rax
0x18000ffa4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000ffab  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000ffb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffb7  mov     ebx, eax
0x18000ffb9  mov     edi, eax
0x18000ffbb  test    eax, eax
0x18000ffbd  jnz     loc_1800100B3
0x18000ffc3  mov     r9d, [rsp+1090h+var_1050]
0x18000ffc8  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000ffd2  mov     rax, r11
0x18000ffd5  mul     r9
0x18000ffd8  shr     rdx, 3
0x18000ffdc  lea     rcx, [rdx+rdx*2]
0x18000ffe0  shl     rcx, 2
0x18000ffe4  cmp     r9, rcx
0x18000ffe7  jz      short loc_18000FFF1
0x18000ffe9  xor     r9d, r9d
0x18000ffec  mov     [rsp+1090h+var_1050], r9d
0x18000fff1  mov     r8, [r14]
0x18000fff4  mov     rax, r11
0x18000fff7  mov     ecx, r9d
0x18000fffa  mul     rcx
0x18000fffd  mov     rcx, [r14+8]
0x180010001  mov     rax, r11
0x180010004  mov     r10, rdx
0x180010007  sub     rcx, r8
0x18001000a  mul     rcx
0x18001000d  shr     r10, 3
0x180010011  shr     rdx, 3
0x180010015  lea     rax, [rdx+rdx*2]
0x180010019  lea     rsi, [r8+rax*4]
0x18001001d  jmp     short loc_180010088
0x18001001f  mov     eax, r10d
0x180010022  lea     rcx, [rax+rax*2]
0x180010026  lea     rdx, [rdx+rcx*4]
0x18001002a  lea     rax, [rsp+1090h+var_1040]
0x18001002f  cmp     rax, rdx
0x180010032  jz      short loc_180010059
0x180010034  mov     r11d, [r8]
0x180010037  lea     rcx, [rsp+1090h+var_1040]
0x18001003c  cmp     [rcx], r11d
0x18001003f  jnz     short loc_180010050
0x180010041  movzx   eax, word ptr [r8+4]
0x180010046  cmp     [rcx+4], ax
0x18001004a  jz      loc_1800100F2
0x180010050  add     rcx, 0Ch
0x180010054  cmp     rcx, rdx
0x180010057  jnz     short loc_18001003C
0x180010059  mov     eax, r9d
0x18001005c  add     rax, 0Ch
0x180010060  cmp     rax, 1000h
0x180010066  ja      short loc_180010084
0x180010068  movsd   xmm0, qword ptr [r8]
0x18001006d  add     r9d, 0Ch
0x180010071  movsd   qword ptr [rdx], xmm0
0x180010075  inc     r10d
0x180010078  mov     eax, [r8+8]
0x18001007c  mov     [rdx+8], eax
0x18001007f  mov     [rsp+1090h+var_1050], r9d
0x180010084  add     r8, 0Ch
0x180010088  lea     rdx, [rsp+1090h+var_1040]
0x18001008d  cmp     r8, rsi
0x180010090  jnz     short loc_18001001F
0x180010092  mov     eax, [rsp+1090h+var_104C]
0x180010096  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001009d  mov     [rsp+1090h+var_1060], 1
0x1800100a5  mov     r8d, r9d
0x1800100a8  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800100ac  call    wil_details_NtUpdateWnfStateData
0x1800100b1  mov     esi, eax
0x1800100b3  cmp     esi, 0C0000001h
0x1800100b9  jnz     short loc_1800100CC
0x1800100bb  inc     r15d
0x1800100be  cmp     r15d, 64h ; 'd'
0x1800100c2  jge     short loc_1800100CC
0x1800100c4  test    edi, edi
0x1800100c6  jz      loc_18000FF12
0x1800100cc  test    ebx, ebx
0x1800100ce  cmovz   ebx, esi
0x1800100d1  mov     eax, ebx
0x1800100d3  mov     rcx, [rbp+0F90h+var_40]
0x1800100da  xor     rcx, rsp; StackCookie
0x1800100dd  call    __security_check_cookie
0x1800100e2  add     rsp, 1068h
0x1800100e9  pop     r15
0x1800100eb  pop     r14
0x1800100ed  pop     rdi
0x1800100ee  pop     rsi
0x1800100ef  pop     rbx
0x1800100f0  pop     rbp
0x1800100f1  retn
0x1800100f2  mov     eax, [r8+8]
0x1800100f6  add     [rcx+8], eax
0x1800100f9  mov     r9d, [rsp+1090h+var_1050]
0x1800100fe  jmp     short loc_180010084
```
