# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14001638c`
- end: `0x1400165c4`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1400123a0`

## callees

- `0x140008660`
- `0x1400090ec`
- `0x14001638c`
- `0x1400165cc`
- `0x1400167a0`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140016415`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140016415`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001642c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14001642c`

## string_xrefs

- `0x14001640e`: `ntdll.dll`

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
0x14001638c  push    rbp
0x14001638e  push    rbx
0x14001638f  push    rsi
0x140016390  push    rdi
0x140016391  push    r14
0x140016393  push    r15
0x140016395  lea     rbp, [rsp-0F68h]
0x14001639d  mov     eax, 1068h
0x1400163a2  call    _alloca_probe
0x1400163a7  sub     rsp, rax
0x1400163aa  mov     rax, cs:__security_cookie
0x1400163b1  xor     rax, rsp
0x1400163b4  mov     [rbp+0F90h+var_40], rax
0x1400163bb  mov     rax, [rcx+8]
0x1400163bf  xor     ebx, ebx
0x1400163c1  sub     rax, [rcx]
0x1400163c4  xor     esi, esi
0x1400163c6  mov     r14, rcx
0x1400163c9  cmp     rax, 0Ch
0x1400163cd  jb      loc_140016590
0x1400163d3  xor     r15d, r15d
0x1400163d6  xor     edx, edx; Val
0x1400163d8  lea     rcx, [rsp+1090h+var_1040]; void *
0x1400163dd  mov     r8d, 1000h; Size
0x1400163e3  call    memset_0
0x1400163e8  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1400163f0  mov     [rsp+1090h+var_1050], 1000h
0x1400163f8  mov     [rsp+1090h+var_104C], 0
0x140016400  jnz     short loc_14001644A
0x140016402  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016409  test    rax, rax
0x14001640c  jnz     short loc_140016422
0x14001640e  lea     rcx, ModuleName; "ntdll.dll"
0x140016415  call    cs:__imp_GetModuleHandleW
0x14001641b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140016422  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140016429  mov     rcx, rax; hModule
0x14001642c  call    cs:__imp_GetProcAddress
0x140016432  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140016439  test    rax, rax
0x14001643c  jnz     short loc_14001644A
0x14001643e  mov     edi, 0C0000139h
0x140016443  mov     ebx, edi
0x140016445  jmp     loc_140016577
0x14001644a  lea     rax, [rsp+1090h+var_1050]
0x14001644f  xor     r8d, r8d
0x140016452  mov     [rsp+1090h+var_1068], rax
0x140016457  lea     r9, [rsp+1090h+var_104C]
0x14001645c  lea     rax, [rsp+1090h+var_1040]
0x140016461  xor     edx, edx
0x140016463  mov     [rsp+1090h+var_1070], rax
0x140016468  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14001646f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140016476  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001647b  mov     ebx, eax
0x14001647d  mov     edi, eax
0x14001647f  test    eax, eax
0x140016481  jnz     loc_140016577
0x140016487  mov     r9d, [rsp+1090h+var_1050]
0x14001648c  mov     r11, 0AAAAAAAAAAAAAAABh
0x140016496  mov     rax, r11
0x140016499  mul     r9
0x14001649c  shr     rdx, 3
0x1400164a0  lea     rcx, [rdx+rdx*2]
0x1400164a4  shl     rcx, 2
0x1400164a8  cmp     r9, rcx
0x1400164ab  jz      short loc_1400164B5
0x1400164ad  xor     r9d, r9d
0x1400164b0  mov     [rsp+1090h+var_1050], r9d
0x1400164b5  mov     r8, [r14]
0x1400164b8  mov     rax, r11
0x1400164bb  mov     ecx, r9d
0x1400164be  mul     rcx
0x1400164c1  mov     rcx, [r14+8]
0x1400164c5  mov     rax, r11
0x1400164c8  mov     r10, rdx
0x1400164cb  sub     rcx, r8
0x1400164ce  mul     rcx
0x1400164d1  shr     r10, 3
0x1400164d5  shr     rdx, 3
0x1400164d9  lea     rax, [rdx+rdx*2]
0x1400164dd  lea     rsi, [r8+rax*4]
0x1400164e1  jmp     short loc_14001654C
0x1400164e3  mov     eax, r10d
0x1400164e6  lea     rcx, [rax+rax*2]
0x1400164ea  lea     rdx, [rdx+rcx*4]
0x1400164ee  lea     rax, [rsp+1090h+var_1040]
0x1400164f3  cmp     rax, rdx
0x1400164f6  jz      short loc_14001651D
0x1400164f8  mov     r11d, [r8]
0x1400164fb  lea     rcx, [rsp+1090h+var_1040]
0x140016500  cmp     [rcx], r11d
0x140016503  jnz     short loc_140016514
0x140016505  movzx   eax, word ptr [r8+4]
0x14001650a  cmp     [rcx+4], ax
0x14001650e  jz      loc_1400165B6
0x140016514  add     rcx, 0Ch
0x140016518  cmp     rcx, rdx
0x14001651b  jnz     short loc_140016500
0x14001651d  mov     eax, r9d
0x140016520  add     rax, 0Ch
0x140016524  cmp     rax, 1000h
0x14001652a  ja      short loc_140016548
0x14001652c  movsd   xmm0, qword ptr [r8]
0x140016531  add     r9d, 0Ch
0x140016535  movsd   qword ptr [rdx], xmm0
0x140016539  inc     r10d
0x14001653c  mov     eax, [r8+8]
0x140016540  mov     [rdx+8], eax
0x140016543  mov     [rsp+1090h+var_1050], r9d
0x140016548  add     r8, 0Ch
0x14001654c  lea     rdx, [rsp+1090h+var_1040]
0x140016551  cmp     r8, rsi
0x140016554  jnz     short loc_1400164E3
0x140016556  mov     eax, [rsp+1090h+var_104C]
0x14001655a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140016561  mov     [rsp+1090h+var_1060], 1
0x140016569  mov     r8d, r9d
0x14001656c  mov     dword ptr [rsp+1090h+var_1068], eax
0x140016570  call    wil_details_NtUpdateWnfStateData
0x140016575  mov     esi, eax
0x140016577  cmp     esi, 0C0000001h
0x14001657d  jnz     short loc_140016590
0x14001657f  inc     r15d
0x140016582  cmp     r15d, 64h ; 'd'
0x140016586  jge     short loc_140016590
0x140016588  test    edi, edi
0x14001658a  jz      loc_1400163D6
0x140016590  test    ebx, ebx
0x140016592  cmovz   ebx, esi
0x140016595  mov     eax, ebx
0x140016597  mov     rcx, [rbp+0F90h+var_40]
0x14001659e  xor     rcx, rsp; StackCookie
0x1400165a1  call    __security_check_cookie
0x1400165a6  add     rsp, 1068h
0x1400165ad  pop     r15
0x1400165af  pop     r14
0x1400165b1  pop     rdi
0x1400165b2  pop     rsi
0x1400165b3  pop     rbx
0x1400165b4  pop     rbp
0x1400165b5  retn
0x1400165b6  mov     eax, [r8+8]
0x1400165ba  add     [rcx+8], eax
0x1400165bd  mov     r9d, [rsp+1090h+var_1050]
0x1400165c2  jmp     short loc_140016548
```
