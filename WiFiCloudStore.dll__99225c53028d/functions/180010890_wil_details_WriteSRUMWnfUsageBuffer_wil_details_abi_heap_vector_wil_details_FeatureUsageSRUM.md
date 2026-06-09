# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180010890`
- end: `0x180010b4f`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `703`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180010be0`

## callees

- `0x180010890`
- `0x180010ba4`
- `0x18002a030`
- `0x18002aad0`
- `0x18003d850`
- `0x180041010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010ac3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010af5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010ac3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180010af5`

## string_xrefs

- `0x180010aee`: `NtUpdateWnfStateData`

## pseudocode

```c
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int v2; // esi
  unsigned int v3; // ebx
  int v4; // ebp
  int v5; // r14d
  unsigned int v6; // edi
  __int64 v7; // rcx
  unsigned int v8; // r11d
  unsigned __int64 v9; // r10
  _DWORD *v10; // r8
  _DWORD *v11; // r9
  FARPROC ProcAddress; // rax
  int v13; // ebx
  HMODULE v15; // rax
  HMODULE NtDllModuleHandle; // rax
  __int64 v17; // [rsp+28h] [rbp-1060h]
  unsigned int v18; // [rsp+40h] [rbp-1048h] BYREF
  _DWORD v19[3]; // [rsp+44h] [rbp-1044h] BYREF
  _DWORD v20[1024]; // [rsp+50h] [rbp-1038h] BYREF

  v2 = 0;
  v3 = 0;
  if ( (unsigned __int64)(a1[1] - *a1) >= 0xC )
  {
    v4 = 0;
    do
    {
      memset_0(v20, 0, sizeof(v20));
      v18 = 4096;
      v19[0] = 0;
      if ( g_wil_details_pfnNtQueryWnfStateData
        || (v15 = wil_details_GetNtDllModuleHandle(),
            (g_wil_details_pfnNtQueryWnfStateData = (__int64)GetProcAddress(v15, "NtQueryWnfStateData")) != 0) )
      {
        v2 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, _DWORD *, _DWORD *, unsigned int *))g_wil_details_pfnNtQueryWnfStateData)(
               &__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
               0,
               0,
               v19,
               v20,
               &v18);
        v5 = v2;
        if ( !v2 )
        {
          v6 = v18;
          if ( v18 != 12 * (v18 / 0xCuLL) )
          {
            v6 = 0;
            v18 = 0;
          }
          v7 = *a1;
          v8 = v6 / 0xC;
          v9 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
          if ( *a1 != v9 )
          {
            do
            {
              v10 = v20;
              v11 = &v20[3 * v8];
              while ( v10 != v11 )
              {
                if ( *v10 == *(_DWORD *)v7 && *((_WORD *)v10 + 2) == *(_WORD *)(v7 + 4) )
                {
                  v10[2] += *(_DWORD *)(v7 + 8);
                  v6 = v18;
                  goto LABEL_13;
                }
                v10 += 3;
              }
              if ( (unsigned __int64)v6 + 12 <= 0x1000 )
              {
                v6 += 12;
                *(_QWORD *)v11 = *(_QWORD *)v7;
                ++v8;
                v11[2] = *(_DWORD *)(v7 + 8);
                v18 = v6;
              }
LABEL_13:
              v7 += 12;
            }
            while ( v7 != v9 );
          }
          ProcAddress = (FARPROC)g_wil_details_pfnNtUpdateWnfStateData;
          v13 = v19[0];
          if ( g_wil_details_pfnNtUpdateWnfStateData
            || (NtDllModuleHandle = wil_details_GetNtDllModuleHandle(),
                ProcAddress = GetProcAddress(NtDllModuleHandle, "NtUpdateWnfStateData"),
                (g_wil_details_pfnNtUpdateWnfStateData = (__int64)ProcAddress) != 0) )
          {
            LODWORD(v17) = v13;
            v3 = ((__int64 (__fastcall *)(void *, _DWORD *, _QWORD, _QWORD, _QWORD, __int64, int))ProcAddress)(
                   &__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
                   v20,
                   v6,
                   0,
                   0,
                   v17,
                   1);
          }
          else
          {
            v3 = -1073741511;
          }
        }
      }
      else
      {
        v2 = -1073741511;
        v5 = -1073741511;
      }
      if ( v3 != -1073741823 )
        break;
      if ( ++v4 >= 100 )
        break;
    }
    while ( !v5 );
  }
  if ( !v2 )
    return v3;
  return v2;
}

```

## disassembly

```asm
0x180010890  push    rbx
0x180010892  push    rsi
0x180010893  push    r12
0x180010895  push    r15
0x180010897  mov     eax, 1068h
0x18001089c  call    _alloca_probe
0x1800108a1  sub     rsp, rax
0x1800108a4  mov     rax, cs:__security_cookie
0x1800108ab  xor     rax, rsp
0x1800108ae  mov     [rsp+1088h+var_38], rax
0x1800108b6  mov     rax, [rcx+8]
0x1800108ba  xor     r12d, r12d
0x1800108bd  sub     rax, [rcx]
0x1800108c0  mov     r15, rcx
0x1800108c3  mov     esi, r12d
0x1800108c6  mov     ebx, r12d
0x1800108c9  cmp     rax, 0Ch
0x1800108cd  jb      loc_180010A82
0x1800108d3  mov     [rsp+1088h+arg_0], rbp
0x1800108db  mov     ebp, r12d
0x1800108de  mov     [rsp+1088h+arg_8], rdi
0x1800108e6  mov     [rsp+1088h+arg_10], r13
0x1800108ee  mov     r13, 0AAAAAAAAAAAAAAABh
0x1800108f8  mov     [rsp+1088h+var_28], r14
0x180010900  xor     edx, edx; Val
0x180010902  lea     rcx, [rsp+1088h+var_1038]; void *
0x180010907  mov     r8d, 1000h; Size
0x18001090d  call    memset_0
0x180010912  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, r12
0x180010919  mov     [rsp+1088h+var_1048], 1000h
0x180010921  mov     [rsp+1088h+var_1044], r12d
0x180010926  jz      loc_180010AB4
0x18001092c  lea     rax, [rsp+1088h+var_1048]
0x180010931  xor     r8d, r8d
0x180010934  mov     [rsp+1088h+var_1060], rax
0x180010939  lea     r9, [rsp+1088h+var_1044]
0x18001093e  lea     rax, [rsp+1088h+var_1038]
0x180010943  xor     edx, edx
0x180010945  mov     [rsp+1088h+var_1068], rax
0x18001094a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180010951  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180010958  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001095d  mov     esi, eax
0x18001095f  mov     r14d, eax
0x180010962  test    eax, eax
0x180010964  jnz     loc_180010A4A
0x18001096a  mov     edi, [rsp+1088h+var_1048]
0x18001096e  mov     rax, r13
0x180010971  mul     rdi
0x180010974  shr     rdx, 3
0x180010978  lea     rcx, [rdx+rdx*2]
0x18001097c  shl     rcx, 2
0x180010980  cmp     rdi, rcx
0x180010983  jnz     loc_180010AA7
0x180010989  mov     r8, [r15+8]
0x18001098d  mov     rax, r13
0x180010990  mov     ecx, edi
0x180010992  mul     rcx
0x180010995  mov     rcx, [r15]
0x180010998  mov     rax, r13
0x18001099b  mov     r11, rdx
0x18001099e  sub     r8, rcx
0x1800109a1  mul     r8
0x1800109a4  shr     r11, 3
0x1800109a8  shr     rdx, 3
0x1800109ac  lea     rax, [rdx+rdx*2]
0x1800109b0  lea     r10, [rcx+rax*4]
0x1800109b4  cmp     rcx, r10
0x1800109b7  jz      short loc_180010A0C
0x1800109b9  nop     dword ptr [rax+00000000h]
0x1800109c0  mov     eax, r11d
0x1800109c3  lea     r9, [rsp+1088h+var_1038]
0x1800109c8  lea     r8, [rsp+1088h+var_1038]
0x1800109cd  lea     rdx, [rax+rax*2]
0x1800109d1  lea     r9, [r9+rdx*4]
0x1800109d5  cmp     r8, r9
0x1800109d8  jz      loc_180010B1E
0x1800109de  mov     eax, [rcx]
0x1800109e0  cmp     [r8], eax
0x1800109e3  jnz     loc_180010B15
0x1800109e9  movzx   eax, word ptr [rcx+4]
0x1800109ed  cmp     [r8+4], ax
0x1800109f2  jnz     loc_180010B15
0x1800109f8  mov     eax, [rcx+8]
0x1800109fb  add     [r8+8], eax
0x1800109ff  mov     edi, [rsp+1088h+var_1048]
0x180010a03  add     rcx, 0Ch
0x180010a07  cmp     rcx, r10
0x180010a0a  jnz     short loc_1800109C0
0x180010a0c  mov     rax, cs:g_wil_details_pfnNtUpdateWnfStateData
0x180010a13  mov     ebx, [rsp+1088h+var_1044]
0x180010a17  test    rax, rax
0x180010a1a  jz      loc_180010AE6
0x180010a20  mov     [rsp+1088h+var_1058], 1
0x180010a28  lea     rdx, [rsp+1088h+var_1038]
0x180010a2d  mov     dword ptr [rsp+1088h+var_1060], ebx
0x180010a31  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180010a38  xor     r9d, r9d
0x180010a3b  mov     [rsp+1088h+var_1068], r12
0x180010a40  mov     r8d, edi
0x180010a43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180010a48  mov     ebx, eax
0x180010a4a  cmp     ebx, 0C0000001h
0x180010a50  jnz     short loc_180010A62
0x180010a52  inc     ebp
0x180010a54  cmp     ebp, 64h ; 'd'
0x180010a57  jge     short loc_180010A62
0x180010a59  test    r14d, r14d
0x180010a5c  jz      loc_180010900
0x180010a62  mov     r14, [rsp+1088h+var_28]
0x180010a6a  mov     r13, [rsp+1088h+arg_10]
0x180010a72  mov     rdi, [rsp+1088h+arg_8]
0x180010a7a  mov     rbp, [rsp+1088h+arg_0]
0x180010a82  test    esi, esi
0x180010a84  cmovz   esi, ebx
0x180010a87  mov     eax, esi
0x180010a89  mov     rcx, [rsp+1088h+var_38]
0x180010a91  xor     rcx, rsp; StackCookie
0x180010a94  call    __security_check_cookie
0x180010a99  add     rsp, 1068h
0x180010aa0  pop     r15
0x180010aa2  pop     r12
0x180010aa4  pop     rsi
0x180010aa5  pop     rbx
0x180010aa6  retn
0x180010aa7  mov     edi, r12d
0x180010aaa  mov     [rsp+1088h+var_1048], r12d
0x180010aaf  jmp     loc_180010989
0x180010ab4  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180010ab9  mov     rcx, rax; hModule
0x180010abc  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180010ac3  call    cs:__imp_GetProcAddress
0x180010ac9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180010ad0  test    rax, rax
0x180010ad3  jnz     loc_18001092C
0x180010ad9  mov     esi, 0C0000139h
0x180010ade  mov     r14d, esi
0x180010ae1  jmp     loc_180010A4A
0x180010ae6  call    ?wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ; wil_details_GetNtDllModuleHandle(void)
0x180010aeb  mov     rcx, rax; hModule
0x180010aee  lea     rdx, aNtupdatewnfsta; "NtUpdateWnfStateData"
0x180010af5  call    cs:__imp_GetProcAddress
0x180010afb  mov     cs:g_wil_details_pfnNtUpdateWnfStateData, rax
0x180010b02  test    rax, rax
0x180010b05  jnz     loc_180010A20
0x180010b0b  mov     ebx, 0C0000139h
0x180010b10  jmp     loc_180010A4A
0x180010b15  add     r8, 0Ch
0x180010b19  jmp     loc_1800109D5
0x180010b1e  mov     eax, edi
0x180010b20  add     rax, 0Ch
0x180010b24  cmp     rax, 1000h
0x180010b2a  ja      loc_180010A03
0x180010b30  movsd   xmm0, qword ptr [rcx]
0x180010b34  add     edi, 0Ch
0x180010b37  movsd   qword ptr [r9], xmm0
0x180010b3c  inc     r11d
0x180010b3f  mov     eax, [rcx+8]
0x180010b42  mov     [r9+8], eax
0x180010b46  mov     [rsp+1088h+var_1048], edi
0x180010b4a  jmp     loc_180010A03
```
