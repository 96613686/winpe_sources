# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1400120a8`
- end: `0x1400122e0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140005790`

## callees

- `0x1400120a8`
- `0x1400127c0`
- `0x14001346e`
- `0x1400134a0`
- `0x140013530`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012148`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140012148`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012131`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140012131`

## string_xrefs

- `0x14001212a`: `ntdll.dll`

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
0x1400120a8  push    rbp
0x1400120aa  push    rbx
0x1400120ab  push    rsi
0x1400120ac  push    rdi
0x1400120ad  push    r14
0x1400120af  push    r15
0x1400120b1  lea     rbp, [rsp-0F68h]
0x1400120b9  mov     eax, 1068h
0x1400120be  call    _alloca_probe
0x1400120c3  sub     rsp, rax
0x1400120c6  mov     rax, cs:__security_cookie
0x1400120cd  xor     rax, rsp
0x1400120d0  mov     [rbp+0F90h+var_40], rax
0x1400120d7  mov     rax, [rcx+8]
0x1400120db  xor     ebx, ebx
0x1400120dd  sub     rax, [rcx]
0x1400120e0  xor     esi, esi
0x1400120e2  mov     r14, rcx
0x1400120e5  cmp     rax, 0Ch
0x1400120e9  jb      loc_1400122AC
0x1400120ef  xor     r15d, r15d
0x1400120f2  xor     edx, edx; Val
0x1400120f4  lea     rcx, [rsp+1090h+var_1040]; void *
0x1400120f9  mov     r8d, 1000h; Size
0x1400120ff  call    memset_0
0x140012104  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14001210c  mov     [rsp+1090h+var_1050], 1000h
0x140012114  mov     [rsp+1090h+var_104C], 0
0x14001211c  jnz     short loc_140012166
0x14001211e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140012125  test    rax, rax
0x140012128  jnz     short loc_14001213E
0x14001212a  lea     rcx, ModuleName; "ntdll.dll"
0x140012131  call    cs:__imp_GetModuleHandleW
0x140012137  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001213e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140012145  mov     rcx, rax; hModule
0x140012148  call    cs:__imp_GetProcAddress
0x14001214e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140012155  test    rax, rax
0x140012158  jnz     short loc_140012166
0x14001215a  mov     edi, 0C0000139h
0x14001215f  mov     ebx, edi
0x140012161  jmp     loc_140012293
0x140012166  lea     rax, [rsp+1090h+var_1050]
0x14001216b  xor     r8d, r8d
0x14001216e  mov     [rsp+1090h+var_1068], rax
0x140012173  lea     r9, [rsp+1090h+var_104C]
0x140012178  lea     rax, [rsp+1090h+var_1040]
0x14001217d  xor     edx, edx
0x14001217f  mov     [rsp+1090h+var_1070], rax
0x140012184  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14001218b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140012192  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140012197  mov     ebx, eax
0x140012199  mov     edi, eax
0x14001219b  test    eax, eax
0x14001219d  jnz     loc_140012293
0x1400121a3  mov     r9d, [rsp+1090h+var_1050]
0x1400121a8  mov     r11, 0AAAAAAAAAAAAAAABh
0x1400121b2  mov     rax, r11
0x1400121b5  mul     r9
0x1400121b8  shr     rdx, 3
0x1400121bc  lea     rcx, [rdx+rdx*2]
0x1400121c0  shl     rcx, 2
0x1400121c4  cmp     r9, rcx
0x1400121c7  jz      short loc_1400121D1
0x1400121c9  xor     r9d, r9d
0x1400121cc  mov     [rsp+1090h+var_1050], r9d
0x1400121d1  mov     r8, [r14]
0x1400121d4  mov     rax, r11
0x1400121d7  mov     ecx, r9d
0x1400121da  mul     rcx
0x1400121dd  mov     rcx, [r14+8]
0x1400121e1  mov     rax, r11
0x1400121e4  mov     r10, rdx
0x1400121e7  sub     rcx, r8
0x1400121ea  mul     rcx
0x1400121ed  shr     r10, 3
0x1400121f1  shr     rdx, 3
0x1400121f5  lea     rax, [rdx+rdx*2]
0x1400121f9  lea     rsi, [r8+rax*4]
0x1400121fd  jmp     short loc_140012268
0x1400121ff  mov     eax, r10d
0x140012202  lea     rcx, [rax+rax*2]
0x140012206  lea     rdx, [rdx+rcx*4]
0x14001220a  lea     rax, [rsp+1090h+var_1040]
0x14001220f  cmp     rax, rdx
0x140012212  jz      short loc_140012239
0x140012214  mov     r11d, [r8]
0x140012217  lea     rcx, [rsp+1090h+var_1040]
0x14001221c  cmp     [rcx], r11d
0x14001221f  jnz     short loc_140012230
0x140012221  movzx   eax, word ptr [r8+4]
0x140012226  cmp     [rcx+4], ax
0x14001222a  jz      loc_1400122D2
0x140012230  add     rcx, 0Ch
0x140012234  cmp     rcx, rdx
0x140012237  jnz     short loc_14001221C
0x140012239  mov     eax, r9d
0x14001223c  add     rax, 0Ch
0x140012240  cmp     rax, 1000h
0x140012246  ja      short loc_140012264
0x140012248  movsd   xmm0, qword ptr [r8]
0x14001224d  add     r9d, 0Ch
0x140012251  movsd   qword ptr [rdx], xmm0
0x140012255  inc     r10d
0x140012258  mov     eax, [r8+8]
0x14001225c  mov     [rdx+8], eax
0x14001225f  mov     [rsp+1090h+var_1050], r9d
0x140012264  add     r8, 0Ch
0x140012268  lea     rdx, [rsp+1090h+var_1040]
0x14001226d  cmp     r8, rsi
0x140012270  jnz     short loc_1400121FF
0x140012272  mov     eax, [rsp+1090h+var_104C]
0x140012276  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14001227d  mov     [rsp+1090h+var_1060], 1
0x140012285  mov     r8d, r9d
0x140012288  mov     dword ptr [rsp+1090h+var_1068], eax
0x14001228c  call    wil_details_NtUpdateWnfStateData
0x140012291  mov     esi, eax
0x140012293  cmp     esi, 0C0000001h
0x140012299  jnz     short loc_1400122AC
0x14001229b  inc     r15d
0x14001229e  cmp     r15d, 64h ; 'd'
0x1400122a2  jge     short loc_1400122AC
0x1400122a4  test    edi, edi
0x1400122a6  jz      loc_1400120F2
0x1400122ac  test    ebx, ebx
0x1400122ae  cmovz   ebx, esi
0x1400122b1  mov     eax, ebx
0x1400122b3  mov     rcx, [rbp+0F90h+var_40]
0x1400122ba  xor     rcx, rsp; StackCookie
0x1400122bd  call    __security_check_cookie
0x1400122c2  add     rsp, 1068h
0x1400122c9  pop     r15
0x1400122cb  pop     r14
0x1400122cd  pop     rdi
0x1400122ce  pop     rsi
0x1400122cf  pop     rbx
0x1400122d0  pop     rbp
0x1400122d1  retn
0x1400122d2  mov     eax, [r8+8]
0x1400122d6  add     [rcx+8], eax
0x1400122d9  mov     r9d, [rsp+1090h+var_1050]
0x1400122de  jmp     short loc_140012264
```
