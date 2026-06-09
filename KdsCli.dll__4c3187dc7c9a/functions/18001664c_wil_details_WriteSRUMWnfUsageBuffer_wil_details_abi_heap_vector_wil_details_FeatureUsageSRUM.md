# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001664c`
- end: `0x180016884`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180011140`

## callees

- `0x180001630`
- `0x180001f7c`
- `0x18001664c`
- `0x180016a80`
- `0x18001a640`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800166d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800166d5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800166ec`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800166ec`

## string_xrefs

- `0x1800166ce`: `ntdll.dll`

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
0x18001664c  push    rbp
0x18001664e  push    rbx
0x18001664f  push    rsi
0x180016650  push    rdi
0x180016651  push    r14
0x180016653  push    r15
0x180016655  lea     rbp, [rsp-0F68h]
0x18001665d  mov     eax, 1068h
0x180016662  call    _alloca_probe
0x180016667  sub     rsp, rax
0x18001666a  mov     rax, cs:__security_cookie
0x180016671  xor     rax, rsp
0x180016674  mov     [rbp+0F90h+var_40], rax
0x18001667b  mov     rax, [rcx+8]
0x18001667f  xor     ebx, ebx
0x180016681  sub     rax, [rcx]
0x180016684  xor     esi, esi
0x180016686  mov     r14, rcx
0x180016689  cmp     rax, 0Ch
0x18001668d  jb      loc_180016850
0x180016693  xor     r15d, r15d
0x180016696  xor     edx, edx; Val
0x180016698  lea     rcx, [rsp+1090h+var_1040]; void *
0x18001669d  mov     r8d, 1000h; Size
0x1800166a3  call    memset_0
0x1800166a8  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800166b0  mov     [rsp+1090h+var_1050], 1000h
0x1800166b8  mov     [rsp+1090h+var_104C], 0
0x1800166c0  jnz     short loc_18001670A
0x1800166c2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800166c9  test    rax, rax
0x1800166cc  jnz     short loc_1800166E2
0x1800166ce  lea     rcx, ModuleName; "ntdll.dll"
0x1800166d5  call    cs:__imp_GetModuleHandleW
0x1800166db  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800166e2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800166e9  mov     rcx, rax; hModule
0x1800166ec  call    cs:__imp_GetProcAddress
0x1800166f2  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800166f9  test    rax, rax
0x1800166fc  jnz     short loc_18001670A
0x1800166fe  mov     edi, 0C0000139h
0x180016703  mov     ebx, edi
0x180016705  jmp     loc_180016837
0x18001670a  lea     rax, [rsp+1090h+var_1050]
0x18001670f  xor     r8d, r8d
0x180016712  mov     [rsp+1090h+var_1068], rax
0x180016717  lea     r9, [rsp+1090h+var_104C]
0x18001671c  lea     rax, [rsp+1090h+var_1040]
0x180016721  xor     edx, edx
0x180016723  mov     [rsp+1090h+var_1070], rax
0x180016728  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001672f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180016736  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001673b  mov     ebx, eax
0x18001673d  mov     edi, eax
0x18001673f  test    eax, eax
0x180016741  jnz     loc_180016837
0x180016747  mov     r9d, [rsp+1090h+var_1050]
0x18001674c  mov     r11, 0AAAAAAAAAAAAAAABh
0x180016756  mov     rax, r11
0x180016759  mul     r9
0x18001675c  shr     rdx, 3
0x180016760  lea     rcx, [rdx+rdx*2]
0x180016764  shl     rcx, 2
0x180016768  cmp     r9, rcx
0x18001676b  jz      short loc_180016775
0x18001676d  xor     r9d, r9d
0x180016770  mov     [rsp+1090h+var_1050], r9d
0x180016775  mov     r8, [r14]
0x180016778  mov     rax, r11
0x18001677b  mov     ecx, r9d
0x18001677e  mul     rcx
0x180016781  mov     rcx, [r14+8]
0x180016785  mov     rax, r11
0x180016788  mov     r10, rdx
0x18001678b  sub     rcx, r8
0x18001678e  mul     rcx
0x180016791  shr     r10, 3
0x180016795  shr     rdx, 3
0x180016799  lea     rax, [rdx+rdx*2]
0x18001679d  lea     rsi, [r8+rax*4]
0x1800167a1  jmp     short loc_18001680C
0x1800167a3  mov     eax, r10d
0x1800167a6  lea     rcx, [rax+rax*2]
0x1800167aa  lea     rdx, [rdx+rcx*4]
0x1800167ae  lea     rax, [rsp+1090h+var_1040]
0x1800167b3  cmp     rax, rdx
0x1800167b6  jz      short loc_1800167DD
0x1800167b8  mov     r11d, [r8]
0x1800167bb  lea     rcx, [rsp+1090h+var_1040]
0x1800167c0  cmp     [rcx], r11d
0x1800167c3  jnz     short loc_1800167D4
0x1800167c5  movzx   eax, word ptr [r8+4]
0x1800167ca  cmp     [rcx+4], ax
0x1800167ce  jz      loc_180016876
0x1800167d4  add     rcx, 0Ch
0x1800167d8  cmp     rcx, rdx
0x1800167db  jnz     short loc_1800167C0
0x1800167dd  mov     eax, r9d
0x1800167e0  add     rax, 0Ch
0x1800167e4  cmp     rax, 1000h
0x1800167ea  ja      short loc_180016808
0x1800167ec  movsd   xmm0, qword ptr [r8]
0x1800167f1  add     r9d, 0Ch
0x1800167f5  movsd   qword ptr [rdx], xmm0
0x1800167f9  inc     r10d
0x1800167fc  mov     eax, [r8+8]
0x180016800  mov     [rdx+8], eax
0x180016803  mov     [rsp+1090h+var_1050], r9d
0x180016808  add     r8, 0Ch
0x18001680c  lea     rdx, [rsp+1090h+var_1040]
0x180016811  cmp     r8, rsi
0x180016814  jnz     short loc_1800167A3
0x180016816  mov     eax, [rsp+1090h+var_104C]
0x18001681a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180016821  mov     [rsp+1090h+var_1060], 1
0x180016829  mov     r8d, r9d
0x18001682c  mov     dword ptr [rsp+1090h+var_1068], eax
0x180016830  call    wil_details_NtUpdateWnfStateData
0x180016835  mov     esi, eax
0x180016837  cmp     esi, 0C0000001h
0x18001683d  jnz     short loc_180016850
0x18001683f  inc     r15d
0x180016842  cmp     r15d, 64h ; 'd'
0x180016846  jge     short loc_180016850
0x180016848  test    edi, edi
0x18001684a  jz      loc_180016696
0x180016850  test    ebx, ebx
0x180016852  cmovz   ebx, esi
0x180016855  mov     eax, ebx
0x180016857  mov     rcx, [rbp+0F90h+var_40]
0x18001685e  xor     rcx, rsp; StackCookie
0x180016861  call    __security_check_cookie
0x180016866  add     rsp, 1068h
0x18001686d  pop     r15
0x18001686f  pop     r14
0x180016871  pop     rdi
0x180016872  pop     rsi
0x180016873  pop     rbx
0x180016874  pop     rbp
0x180016875  retn
0x180016876  mov     eax, [r8+8]
0x18001687a  add     [rcx+8], eax
0x18001687d  mov     r9d, [rsp+1090h+var_1050]
0x180016882  jmp     short loc_180016808
```
