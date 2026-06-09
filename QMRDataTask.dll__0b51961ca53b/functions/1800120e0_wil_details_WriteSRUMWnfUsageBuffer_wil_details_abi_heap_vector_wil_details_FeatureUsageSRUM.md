# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800120e0`
- end: `0x180012318`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180004640`

## callees

- `0x1800120e0`
- `0x1800127f0`
- `0x1800142d2`
- `0x180014310`
- `0x1800143d0`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x180012180`
- `KERNEL32!GetProcAddress` at `0x180012180`
- `KERNEL32!GetModuleHandleW` at `0x180012169`
- `KERNEL32!GetModuleHandleW` at `0x180012169`

## string_xrefs

- `0x180012162`: `ntdll.dll`

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
0x1800120e0  push    rbp
0x1800120e2  push    rbx
0x1800120e3  push    rsi
0x1800120e4  push    rdi
0x1800120e5  push    r14
0x1800120e7  push    r15
0x1800120e9  lea     rbp, [rsp-0F68h]
0x1800120f1  mov     eax, 1068h
0x1800120f6  call    _alloca_probe
0x1800120fb  sub     rsp, rax
0x1800120fe  mov     rax, cs:__security_cookie
0x180012105  xor     rax, rsp
0x180012108  mov     [rbp+0F90h+var_40], rax
0x18001210f  mov     rax, [rcx+8]
0x180012113  xor     ebx, ebx
0x180012115  sub     rax, [rcx]
0x180012118  xor     esi, esi
0x18001211a  mov     r14, rcx
0x18001211d  cmp     rax, 0Ch
0x180012121  jb      loc_1800122E4
0x180012127  xor     r15d, r15d
0x18001212a  xor     edx, edx; Val
0x18001212c  lea     rcx, [rsp+1090h+var_1040]; void *
0x180012131  mov     r8d, 1000h; Size
0x180012137  call    memset_0
0x18001213c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180012144  mov     [rsp+1090h+var_1050], 1000h
0x18001214c  mov     [rsp+1090h+var_104C], 0
0x180012154  jnz     short loc_18001219E
0x180012156  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001215d  test    rax, rax
0x180012160  jnz     short loc_180012176
0x180012162  lea     rcx, ModuleName; "ntdll.dll"
0x180012169  call    cs:__imp_GetModuleHandleW
0x18001216f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012176  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18001217d  mov     rcx, rax; hModule
0x180012180  call    cs:__imp_GetProcAddress
0x180012186  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18001218d  test    rax, rax
0x180012190  jnz     short loc_18001219E
0x180012192  mov     edi, 0C0000139h
0x180012197  mov     ebx, edi
0x180012199  jmp     loc_1800122CB
0x18001219e  lea     rax, [rsp+1090h+var_1050]
0x1800121a3  xor     r8d, r8d
0x1800121a6  mov     [rsp+1090h+var_1068], rax
0x1800121ab  lea     r9, [rsp+1090h+var_104C]
0x1800121b0  lea     rax, [rsp+1090h+var_1040]
0x1800121b5  xor     edx, edx
0x1800121b7  mov     [rsp+1090h+var_1070], rax
0x1800121bc  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800121c3  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800121ca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800121cf  mov     ebx, eax
0x1800121d1  mov     edi, eax
0x1800121d3  test    eax, eax
0x1800121d5  jnz     loc_1800122CB
0x1800121db  mov     r9d, [rsp+1090h+var_1050]
0x1800121e0  mov     r11, 0AAAAAAAAAAAAAAABh
0x1800121ea  mov     rax, r11
0x1800121ed  mul     r9
0x1800121f0  shr     rdx, 3
0x1800121f4  lea     rcx, [rdx+rdx*2]
0x1800121f8  shl     rcx, 2
0x1800121fc  cmp     r9, rcx
0x1800121ff  jz      short loc_180012209
0x180012201  xor     r9d, r9d
0x180012204  mov     [rsp+1090h+var_1050], r9d
0x180012209  mov     r8, [r14]
0x18001220c  mov     rax, r11
0x18001220f  mov     ecx, r9d
0x180012212  mul     rcx
0x180012215  mov     rcx, [r14+8]
0x180012219  mov     rax, r11
0x18001221c  mov     r10, rdx
0x18001221f  sub     rcx, r8
0x180012222  mul     rcx
0x180012225  shr     r10, 3
0x180012229  shr     rdx, 3
0x18001222d  lea     rax, [rdx+rdx*2]
0x180012231  lea     rsi, [r8+rax*4]
0x180012235  jmp     short loc_1800122A0
0x180012237  mov     eax, r10d
0x18001223a  lea     rcx, [rax+rax*2]
0x18001223e  lea     rdx, [rdx+rcx*4]
0x180012242  lea     rax, [rsp+1090h+var_1040]
0x180012247  cmp     rax, rdx
0x18001224a  jz      short loc_180012271
0x18001224c  mov     r11d, [r8]
0x18001224f  lea     rcx, [rsp+1090h+var_1040]
0x180012254  cmp     [rcx], r11d
0x180012257  jnz     short loc_180012268
0x180012259  movzx   eax, word ptr [r8+4]
0x18001225e  cmp     [rcx+4], ax
0x180012262  jz      loc_18001230A
0x180012268  add     rcx, 0Ch
0x18001226c  cmp     rcx, rdx
0x18001226f  jnz     short loc_180012254
0x180012271  mov     eax, r9d
0x180012274  add     rax, 0Ch
0x180012278  cmp     rax, 1000h
0x18001227e  ja      short loc_18001229C
0x180012280  movsd   xmm0, qword ptr [r8]
0x180012285  add     r9d, 0Ch
0x180012289  movsd   qword ptr [rdx], xmm0
0x18001228d  inc     r10d
0x180012290  mov     eax, [r8+8]
0x180012294  mov     [rdx+8], eax
0x180012297  mov     [rsp+1090h+var_1050], r9d
0x18001229c  add     r8, 0Ch
0x1800122a0  lea     rdx, [rsp+1090h+var_1040]
0x1800122a5  cmp     r8, rsi
0x1800122a8  jnz     short loc_180012237
0x1800122aa  mov     eax, [rsp+1090h+var_104C]
0x1800122ae  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800122b5  mov     [rsp+1090h+var_1060], 1
0x1800122bd  mov     r8d, r9d
0x1800122c0  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800122c4  call    wil_details_NtUpdateWnfStateData
0x1800122c9  mov     esi, eax
0x1800122cb  cmp     esi, 0C0000001h
0x1800122d1  jnz     short loc_1800122E4
0x1800122d3  inc     r15d
0x1800122d6  cmp     r15d, 64h ; 'd'
0x1800122da  jge     short loc_1800122E4
0x1800122dc  test    edi, edi
0x1800122de  jz      loc_18001212A
0x1800122e4  test    ebx, ebx
0x1800122e6  cmovz   ebx, esi
0x1800122e9  mov     eax, ebx
0x1800122eb  mov     rcx, [rbp+0F90h+var_40]
0x1800122f2  xor     rcx, rsp; StackCookie
0x1800122f5  call    __security_check_cookie
0x1800122fa  add     rsp, 1068h
0x180012301  pop     r15
0x180012303  pop     r14
0x180012305  pop     rdi
0x180012306  pop     rsi
0x180012307  pop     rbx
0x180012308  pop     rbp
0x180012309  retn
0x18001230a  mov     eax, [r8+8]
0x18001230e  add     [rcx+8], eax
0x180012311  mov     r9d, [rsp+1090h+var_1050]
0x180012316  jmp     short loc_18001229C
```
