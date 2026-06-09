# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1400083b4`
- end: `0x1400085ec`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140005900`

## callees

- `0x140001530`
- `0x140001f50`
- `0x1400083b4`
- `0x1400087dc`
- `0x140008990`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000843d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000843d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008454`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008454`

## string_xrefs

- `0x140008436`: `ntdll.dll`

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
0x1400083b4  push    rbp
0x1400083b6  push    rbx
0x1400083b7  push    rsi
0x1400083b8  push    rdi
0x1400083b9  push    r14
0x1400083bb  push    r15
0x1400083bd  lea     rbp, [rsp-0F68h]
0x1400083c5  mov     eax, 1068h
0x1400083ca  call    _alloca_probe
0x1400083cf  sub     rsp, rax
0x1400083d2  mov     rax, cs:__security_cookie
0x1400083d9  xor     rax, rsp
0x1400083dc  mov     [rbp+0F90h+var_40], rax
0x1400083e3  mov     rax, [rcx+8]
0x1400083e7  xor     ebx, ebx
0x1400083e9  sub     rax, [rcx]
0x1400083ec  xor     esi, esi
0x1400083ee  mov     r14, rcx
0x1400083f1  cmp     rax, 0Ch
0x1400083f5  jb      loc_1400085B8
0x1400083fb  xor     r15d, r15d
0x1400083fe  xor     edx, edx; Val
0x140008400  lea     rcx, [rsp+1090h+var_1040]; void *
0x140008405  mov     r8d, 1000h; Size
0x14000840b  call    memset_0
0x140008410  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x140008418  mov     [rsp+1090h+var_1050], 1000h
0x140008420  mov     [rsp+1090h+var_104C], 0
0x140008428  jnz     short loc_140008472
0x14000842a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008431  test    rax, rax
0x140008434  jnz     short loc_14000844A
0x140008436  lea     rcx, ModuleName; "ntdll.dll"
0x14000843d  call    cs:__imp_GetModuleHandleW
0x140008443  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000844a  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140008451  mov     rcx, rax; hModule
0x140008454  call    cs:__imp_GetProcAddress
0x14000845a  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140008461  test    rax, rax
0x140008464  jnz     short loc_140008472
0x140008466  mov     edi, 0C0000139h
0x14000846b  mov     ebx, edi
0x14000846d  jmp     loc_14000859F
0x140008472  lea     rax, [rsp+1090h+var_1050]
0x140008477  xor     r8d, r8d
0x14000847a  mov     [rsp+1090h+var_1068], rax
0x14000847f  lea     r9, [rsp+1090h+var_104C]
0x140008484  lea     rax, [rsp+1090h+var_1040]
0x140008489  xor     edx, edx
0x14000848b  mov     [rsp+1090h+var_1070], rax
0x140008490  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140008497  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000849e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400084a3  mov     ebx, eax
0x1400084a5  mov     edi, eax
0x1400084a7  test    eax, eax
0x1400084a9  jnz     loc_14000859F
0x1400084af  mov     r9d, [rsp+1090h+var_1050]
0x1400084b4  mov     r11, 0AAAAAAAAAAAAAAABh
0x1400084be  mov     rax, r11
0x1400084c1  mul     r9
0x1400084c4  shr     rdx, 3
0x1400084c8  lea     rcx, [rdx+rdx*2]
0x1400084cc  shl     rcx, 2
0x1400084d0  cmp     r9, rcx
0x1400084d3  jz      short loc_1400084DD
0x1400084d5  xor     r9d, r9d
0x1400084d8  mov     [rsp+1090h+var_1050], r9d
0x1400084dd  mov     r8, [r14]
0x1400084e0  mov     rax, r11
0x1400084e3  mov     ecx, r9d
0x1400084e6  mul     rcx
0x1400084e9  mov     rcx, [r14+8]
0x1400084ed  mov     rax, r11
0x1400084f0  mov     r10, rdx
0x1400084f3  sub     rcx, r8
0x1400084f6  mul     rcx
0x1400084f9  shr     r10, 3
0x1400084fd  shr     rdx, 3
0x140008501  lea     rax, [rdx+rdx*2]
0x140008505  lea     rsi, [r8+rax*4]
0x140008509  jmp     short loc_140008574
0x14000850b  mov     eax, r10d
0x14000850e  lea     rcx, [rax+rax*2]
0x140008512  lea     rdx, [rdx+rcx*4]
0x140008516  lea     rax, [rsp+1090h+var_1040]
0x14000851b  cmp     rax, rdx
0x14000851e  jz      short loc_140008545
0x140008520  mov     r11d, [r8]
0x140008523  lea     rcx, [rsp+1090h+var_1040]
0x140008528  cmp     [rcx], r11d
0x14000852b  jnz     short loc_14000853C
0x14000852d  movzx   eax, word ptr [r8+4]
0x140008532  cmp     [rcx+4], ax
0x140008536  jz      loc_1400085DE
0x14000853c  add     rcx, 0Ch
0x140008540  cmp     rcx, rdx
0x140008543  jnz     short loc_140008528
0x140008545  mov     eax, r9d
0x140008548  add     rax, 0Ch
0x14000854c  cmp     rax, 1000h
0x140008552  ja      short loc_140008570
0x140008554  movsd   xmm0, qword ptr [r8]
0x140008559  add     r9d, 0Ch
0x14000855d  movsd   qword ptr [rdx], xmm0
0x140008561  inc     r10d
0x140008564  mov     eax, [r8+8]
0x140008568  mov     [rdx+8], eax
0x14000856b  mov     [rsp+1090h+var_1050], r9d
0x140008570  add     r8, 0Ch
0x140008574  lea     rdx, [rsp+1090h+var_1040]
0x140008579  cmp     r8, rsi
0x14000857c  jnz     short loc_14000850B
0x14000857e  mov     eax, [rsp+1090h+var_104C]
0x140008582  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140008589  mov     [rsp+1090h+var_1060], 1
0x140008591  mov     r8d, r9d
0x140008594  mov     dword ptr [rsp+1090h+var_1068], eax
0x140008598  call    wil_details_NtUpdateWnfStateData
0x14000859d  mov     esi, eax
0x14000859f  cmp     esi, 0C0000001h
0x1400085a5  jnz     short loc_1400085B8
0x1400085a7  inc     r15d
0x1400085aa  cmp     r15d, 64h ; 'd'
0x1400085ae  jge     short loc_1400085B8
0x1400085b0  test    edi, edi
0x1400085b2  jz      loc_1400083FE
0x1400085b8  test    ebx, ebx
0x1400085ba  cmovz   ebx, esi
0x1400085bd  mov     eax, ebx
0x1400085bf  mov     rcx, [rbp+0F90h+var_40]
0x1400085c6  xor     rcx, rsp; StackCookie
0x1400085c9  call    __security_check_cookie
0x1400085ce  add     rsp, 1068h
0x1400085d5  pop     r15
0x1400085d7  pop     r14
0x1400085d9  pop     rdi
0x1400085da  pop     rsi
0x1400085db  pop     rbx
0x1400085dc  pop     rbp
0x1400085dd  retn
0x1400085de  mov     eax, [r8+8]
0x1400085e2  add     [rcx+8], eax
0x1400085e5  mov     r9d, [rsp+1090h+var_1050]
0x1400085ea  jmp     short loc_140008570
```
