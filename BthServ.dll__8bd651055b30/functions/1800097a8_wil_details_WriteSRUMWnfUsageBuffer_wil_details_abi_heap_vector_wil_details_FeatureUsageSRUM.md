# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800097a8`
- end: `0x1800099e0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800029c0`

## callees

- `0x180001790`
- `0x1800024ac`
- `0x1800097a8`
- `0x180009c70`
- `0x180032bf0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009831`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009831`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009848`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009848`

## string_xrefs

- `0x18000982a`: `ntdll.dll`

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
0x1800097a8  push    rbp
0x1800097aa  push    rbx
0x1800097ab  push    rsi
0x1800097ac  push    rdi
0x1800097ad  push    r14
0x1800097af  push    r15
0x1800097b1  lea     rbp, [rsp-0F68h]
0x1800097b9  mov     eax, 1068h
0x1800097be  call    _alloca_probe
0x1800097c3  sub     rsp, rax
0x1800097c6  mov     rax, cs:__security_cookie
0x1800097cd  xor     rax, rsp
0x1800097d0  mov     [rbp+0F90h+var_40], rax
0x1800097d7  mov     rax, [rcx+8]
0x1800097db  xor     ebx, ebx
0x1800097dd  sub     rax, [rcx]
0x1800097e0  xor     esi, esi
0x1800097e2  mov     r14, rcx
0x1800097e5  cmp     rax, 0Ch
0x1800097e9  jb      loc_1800099AC
0x1800097ef  xor     r15d, r15d
0x1800097f2  xor     edx, edx; Val
0x1800097f4  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800097f9  mov     r8d, 1000h; Size
0x1800097ff  call    memset_0
0x180009804  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000980c  mov     [rsp+1090h+var_1050], 1000h
0x180009814  mov     [rsp+1090h+var_104C], 0
0x18000981c  jnz     short loc_180009866
0x18000981e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009825  test    rax, rax
0x180009828  jnz     short loc_18000983E
0x18000982a  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180009831  call    cs:__imp_GetModuleHandleW
0x180009837  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000983e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009845  mov     rcx, rax; hModule
0x180009848  call    cs:__imp_GetProcAddress
0x18000984e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009855  test    rax, rax
0x180009858  jnz     short loc_180009866
0x18000985a  mov     edi, 0C0000139h
0x18000985f  mov     ebx, edi
0x180009861  jmp     loc_180009993
0x180009866  lea     rax, [rsp+1090h+var_1050]
0x18000986b  xor     r8d, r8d
0x18000986e  mov     [rsp+1090h+var_1068], rax
0x180009873  lea     r9, [rsp+1090h+var_104C]
0x180009878  lea     rax, [rsp+1090h+var_1040]
0x18000987d  xor     edx, edx
0x18000987f  mov     [rsp+1090h+var_1070], rax
0x180009884  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000988b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180009892  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009897  mov     ebx, eax
0x180009899  mov     edi, eax
0x18000989b  test    eax, eax
0x18000989d  jnz     loc_180009993
0x1800098a3  mov     r9d, [rsp+1090h+var_1050]
0x1800098a8  mov     r11, 0AAAAAAAAAAAAAAABh
0x1800098b2  mov     rax, r11
0x1800098b5  mul     r9
0x1800098b8  shr     rdx, 3
0x1800098bc  lea     rcx, [rdx+rdx*2]
0x1800098c0  shl     rcx, 2
0x1800098c4  cmp     r9, rcx
0x1800098c7  jz      short loc_1800098D1
0x1800098c9  xor     r9d, r9d
0x1800098cc  mov     [rsp+1090h+var_1050], r9d
0x1800098d1  mov     r8, [r14]
0x1800098d4  mov     rax, r11
0x1800098d7  mov     ecx, r9d
0x1800098da  mul     rcx
0x1800098dd  mov     rcx, [r14+8]
0x1800098e1  mov     rax, r11
0x1800098e4  mov     r10, rdx
0x1800098e7  sub     rcx, r8
0x1800098ea  mul     rcx
0x1800098ed  shr     r10, 3
0x1800098f1  shr     rdx, 3
0x1800098f5  lea     rax, [rdx+rdx*2]
0x1800098f9  lea     rsi, [r8+rax*4]
0x1800098fd  jmp     short loc_180009968
0x1800098ff  mov     eax, r10d
0x180009902  lea     rcx, [rax+rax*2]
0x180009906  lea     rdx, [rdx+rcx*4]
0x18000990a  lea     rax, [rsp+1090h+var_1040]
0x18000990f  cmp     rax, rdx
0x180009912  jz      short loc_180009939
0x180009914  mov     r11d, [r8]
0x180009917  lea     rcx, [rsp+1090h+var_1040]
0x18000991c  cmp     [rcx], r11d
0x18000991f  jnz     short loc_180009930
0x180009921  movzx   eax, word ptr [r8+4]
0x180009926  cmp     [rcx+4], ax
0x18000992a  jz      loc_1800099D2
0x180009930  add     rcx, 0Ch
0x180009934  cmp     rcx, rdx
0x180009937  jnz     short loc_18000991C
0x180009939  mov     eax, r9d
0x18000993c  add     rax, 0Ch
0x180009940  cmp     rax, 1000h
0x180009946  ja      short loc_180009964
0x180009948  movsd   xmm0, qword ptr [r8]
0x18000994d  add     r9d, 0Ch
0x180009951  movsd   qword ptr [rdx], xmm0
0x180009955  inc     r10d
0x180009958  mov     eax, [r8+8]
0x18000995c  mov     [rdx+8], eax
0x18000995f  mov     [rsp+1090h+var_1050], r9d
0x180009964  add     r8, 0Ch
0x180009968  lea     rdx, [rsp+1090h+var_1040]
0x18000996d  cmp     r8, rsi
0x180009970  jnz     short loc_1800098FF
0x180009972  mov     eax, [rsp+1090h+var_104C]
0x180009976  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000997d  mov     [rsp+1090h+var_1060], 1
0x180009985  mov     r8d, r9d
0x180009988  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000998c  call    wil_details_NtUpdateWnfStateData
0x180009991  mov     esi, eax
0x180009993  cmp     esi, 0C0000001h
0x180009999  jnz     short loc_1800099AC
0x18000999b  inc     r15d
0x18000999e  cmp     r15d, 64h ; 'd'
0x1800099a2  jge     short loc_1800099AC
0x1800099a4  test    edi, edi
0x1800099a6  jz      loc_1800097F2
0x1800099ac  test    ebx, ebx
0x1800099ae  cmovz   ebx, esi
0x1800099b1  mov     eax, ebx
0x1800099b3  mov     rcx, [rbp+0F90h+var_40]
0x1800099ba  xor     rcx, rsp; StackCookie
0x1800099bd  call    __security_check_cookie
0x1800099c2  add     rsp, 1068h
0x1800099c9  pop     r15
0x1800099cb  pop     r14
0x1800099cd  pop     rdi
0x1800099ce  pop     rsi
0x1800099cf  pop     rbx
0x1800099d0  pop     rbp
0x1800099d1  retn
0x1800099d2  mov     eax, [r8+8]
0x1800099d6  add     [rcx+8], eax
0x1800099d9  mov     r9d, [rsp+1090h+var_1050]
0x1800099de  jmp     short loc_180009964
```
