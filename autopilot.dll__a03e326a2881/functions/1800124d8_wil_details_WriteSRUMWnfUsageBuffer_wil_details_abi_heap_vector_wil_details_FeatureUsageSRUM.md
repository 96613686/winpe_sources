# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800124d8`
- end: `0x180012710`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180009ab0`

## callees

- `0x1800045b0`
- `0x180005374`
- `0x1800124d8`
- `0x180013730`
- `0x1800281e0`
- `0x18002e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012561`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180012561`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012578`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180012578`

## string_xrefs

- `0x18001255a`: `ntdll.dll`

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
0x1800124d8  push    rbp
0x1800124da  push    rbx
0x1800124db  push    rsi
0x1800124dc  push    rdi
0x1800124dd  push    r14
0x1800124df  push    r15
0x1800124e1  lea     rbp, [rsp-0F68h]
0x1800124e9  mov     eax, 1068h
0x1800124ee  call    _alloca_probe
0x1800124f3  sub     rsp, rax
0x1800124f6  mov     rax, cs:__security_cookie
0x1800124fd  xor     rax, rsp
0x180012500  mov     [rbp+0F90h+var_40], rax
0x180012507  mov     rax, [rcx+8]
0x18001250b  xor     ebx, ebx
0x18001250d  sub     rax, [rcx]
0x180012510  xor     esi, esi
0x180012512  mov     r14, rcx
0x180012515  cmp     rax, 0Ch
0x180012519  jb      loc_1800126DC
0x18001251f  xor     r15d, r15d
0x180012522  xor     edx, edx; Val
0x180012524  lea     rcx, [rsp+1090h+var_1040]; void *
0x180012529  mov     r8d, 1000h; Size
0x18001252f  call    memset_0
0x180012534  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18001253c  mov     [rsp+1090h+var_1050], 1000h
0x180012544  mov     [rsp+1090h+var_104C], 0
0x18001254c  jnz     short loc_180012596
0x18001254e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180012555  test    rax, rax
0x180012558  jnz     short loc_18001256E
0x18001255a  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180012561  call    cs:__imp_GetModuleHandleW
0x180012567  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001256e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180012575  mov     rcx, rax; hModule
0x180012578  call    cs:__imp_GetProcAddress
0x18001257e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180012585  test    rax, rax
0x180012588  jnz     short loc_180012596
0x18001258a  mov     edi, 0C0000139h
0x18001258f  mov     ebx, edi
0x180012591  jmp     loc_1800126C3
0x180012596  lea     rax, [rsp+1090h+var_1050]
0x18001259b  xor     r8d, r8d
0x18001259e  mov     [rsp+1090h+var_1068], rax
0x1800125a3  lea     r9, [rsp+1090h+var_104C]
0x1800125a8  lea     rax, [rsp+1090h+var_1040]
0x1800125ad  xor     edx, edx
0x1800125af  mov     [rsp+1090h+var_1070], rax
0x1800125b4  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800125bb  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800125c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800125c7  mov     ebx, eax
0x1800125c9  mov     edi, eax
0x1800125cb  test    eax, eax
0x1800125cd  jnz     loc_1800126C3
0x1800125d3  mov     r9d, [rsp+1090h+var_1050]
0x1800125d8  mov     r11, 0AAAAAAAAAAAAAAABh
0x1800125e2  mov     rax, r11
0x1800125e5  mul     r9
0x1800125e8  shr     rdx, 3
0x1800125ec  lea     rcx, [rdx+rdx*2]
0x1800125f0  shl     rcx, 2
0x1800125f4  cmp     r9, rcx
0x1800125f7  jz      short loc_180012601
0x1800125f9  xor     r9d, r9d
0x1800125fc  mov     [rsp+1090h+var_1050], r9d
0x180012601  mov     r8, [r14]
0x180012604  mov     rax, r11
0x180012607  mov     ecx, r9d
0x18001260a  mul     rcx
0x18001260d  mov     rcx, [r14+8]
0x180012611  mov     rax, r11
0x180012614  mov     r10, rdx
0x180012617  sub     rcx, r8
0x18001261a  mul     rcx
0x18001261d  shr     r10, 3
0x180012621  shr     rdx, 3
0x180012625  lea     rax, [rdx+rdx*2]
0x180012629  lea     rsi, [r8+rax*4]
0x18001262d  jmp     short loc_180012698
0x18001262f  mov     eax, r10d
0x180012632  lea     rcx, [rax+rax*2]
0x180012636  lea     rdx, [rdx+rcx*4]
0x18001263a  lea     rax, [rsp+1090h+var_1040]
0x18001263f  cmp     rax, rdx
0x180012642  jz      short loc_180012669
0x180012644  mov     r11d, [r8]
0x180012647  lea     rcx, [rsp+1090h+var_1040]
0x18001264c  cmp     [rcx], r11d
0x18001264f  jnz     short loc_180012660
0x180012651  movzx   eax, word ptr [r8+4]
0x180012656  cmp     [rcx+4], ax
0x18001265a  jz      loc_180012702
0x180012660  add     rcx, 0Ch
0x180012664  cmp     rcx, rdx
0x180012667  jnz     short loc_18001264C
0x180012669  mov     eax, r9d
0x18001266c  add     rax, 0Ch
0x180012670  cmp     rax, 1000h
0x180012676  ja      short loc_180012694
0x180012678  movsd   xmm0, qword ptr [r8]
0x18001267d  add     r9d, 0Ch
0x180012681  movsd   qword ptr [rdx], xmm0
0x180012685  inc     r10d
0x180012688  mov     eax, [r8+8]
0x18001268c  mov     [rdx+8], eax
0x18001268f  mov     [rsp+1090h+var_1050], r9d
0x180012694  add     r8, 0Ch
0x180012698  lea     rdx, [rsp+1090h+var_1040]
0x18001269d  cmp     r8, rsi
0x1800126a0  jnz     short loc_18001262F
0x1800126a2  mov     eax, [rsp+1090h+var_104C]
0x1800126a6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800126ad  mov     [rsp+1090h+var_1060], 1
0x1800126b5  mov     r8d, r9d
0x1800126b8  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800126bc  call    wil_details_NtUpdateWnfStateData
0x1800126c1  mov     esi, eax
0x1800126c3  cmp     esi, 0C0000001h
0x1800126c9  jnz     short loc_1800126DC
0x1800126cb  inc     r15d
0x1800126ce  cmp     r15d, 64h ; 'd'
0x1800126d2  jge     short loc_1800126DC
0x1800126d4  test    edi, edi
0x1800126d6  jz      loc_180012522
0x1800126dc  test    ebx, ebx
0x1800126de  cmovz   ebx, esi
0x1800126e1  mov     eax, ebx
0x1800126e3  mov     rcx, [rbp+0F90h+var_40]
0x1800126ea  xor     rcx, rsp; StackCookie
0x1800126ed  call    __security_check_cookie
0x1800126f2  add     rsp, 1068h
0x1800126f9  pop     r15
0x1800126fb  pop     r14
0x1800126fd  pop     rdi
0x1800126fe  pop     rsi
0x1800126ff  pop     rbx
0x180012700  pop     rbp
0x180012701  retn
0x180012702  mov     eax, [r8+8]
0x180012706  add     [rcx+8], eax
0x180012709  mov     r9d, [rsp+1090h+var_1050]
0x18001270e  jmp     short loc_180012694
```
