# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180030780`
- end: `0x1800309b8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180026e50`

## callees

- `0x1800268ef`
- `0x180030780`
- `0x180031150`
- `0x1800350e0`
- `0x1800351a0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030820`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180030820`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030809`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180030809`

## string_xrefs

- `0x180030802`: `ntdll.dll`

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
0x180030780  push    rbp
0x180030782  push    rbx
0x180030783  push    rsi
0x180030784  push    rdi
0x180030785  push    r14
0x180030787  push    r15
0x180030789  lea     rbp, [rsp-0F68h]
0x180030791  mov     eax, 1068h
0x180030796  call    _alloca_probe
0x18003079b  sub     rsp, rax
0x18003079e  mov     rax, cs:__security_cookie
0x1800307a5  xor     rax, rsp
0x1800307a8  mov     [rbp+0F90h+var_40], rax
0x1800307af  mov     rax, [rcx+8]
0x1800307b3  xor     ebx, ebx
0x1800307b5  sub     rax, [rcx]
0x1800307b8  xor     esi, esi
0x1800307ba  mov     r14, rcx
0x1800307bd  cmp     rax, 0Ch
0x1800307c1  jb      loc_180030984
0x1800307c7  xor     r15d, r15d
0x1800307ca  xor     edx, edx; Val
0x1800307cc  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800307d1  mov     r8d, 1000h; Size
0x1800307d7  call    memset_0
0x1800307dc  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800307e4  mov     [rsp+1090h+var_1050], 1000h
0x1800307ec  mov     [rsp+1090h+var_104C], 0
0x1800307f4  jnz     short loc_18003083E
0x1800307f6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800307fd  test    rax, rax
0x180030800  jnz     short loc_180030816
0x180030802  lea     rcx, ModuleName; "ntdll.dll"
0x180030809  call    cs:__imp_GetModuleHandleW
0x18003080f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180030816  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18003081d  mov     rcx, rax; hModule
0x180030820  call    cs:__imp_GetProcAddress
0x180030826  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18003082d  test    rax, rax
0x180030830  jnz     short loc_18003083E
0x180030832  mov     edi, 0C0000139h
0x180030837  mov     ebx, edi
0x180030839  jmp     loc_18003096B
0x18003083e  lea     rax, [rsp+1090h+var_1050]
0x180030843  xor     r8d, r8d
0x180030846  mov     [rsp+1090h+var_1068], rax
0x18003084b  lea     r9, [rsp+1090h+var_104C]
0x180030850  lea     rax, [rsp+1090h+var_1040]
0x180030855  xor     edx, edx
0x180030857  mov     [rsp+1090h+var_1070], rax
0x18003085c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180030863  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18003086a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003086f  mov     ebx, eax
0x180030871  mov     edi, eax
0x180030873  test    eax, eax
0x180030875  jnz     loc_18003096B
0x18003087b  mov     r9d, [rsp+1090h+var_1050]
0x180030880  mov     r11, 0AAAAAAAAAAAAAAABh
0x18003088a  mov     rax, r11
0x18003088d  mul     r9
0x180030890  shr     rdx, 3
0x180030894  lea     rcx, [rdx+rdx*2]
0x180030898  shl     rcx, 2
0x18003089c  cmp     r9, rcx
0x18003089f  jz      short loc_1800308A9
0x1800308a1  xor     r9d, r9d
0x1800308a4  mov     [rsp+1090h+var_1050], r9d
0x1800308a9  mov     r8, [r14]
0x1800308ac  mov     rax, r11
0x1800308af  mov     ecx, r9d
0x1800308b2  mul     rcx
0x1800308b5  mov     rcx, [r14+8]
0x1800308b9  mov     rax, r11
0x1800308bc  mov     r10, rdx
0x1800308bf  sub     rcx, r8
0x1800308c2  mul     rcx
0x1800308c5  shr     r10, 3
0x1800308c9  shr     rdx, 3
0x1800308cd  lea     rax, [rdx+rdx*2]
0x1800308d1  lea     rsi, [r8+rax*4]
0x1800308d5  jmp     short loc_180030940
0x1800308d7  mov     eax, r10d
0x1800308da  lea     rcx, [rax+rax*2]
0x1800308de  lea     rdx, [rdx+rcx*4]
0x1800308e2  lea     rax, [rsp+1090h+var_1040]
0x1800308e7  cmp     rax, rdx
0x1800308ea  jz      short loc_180030911
0x1800308ec  mov     r11d, [r8]
0x1800308ef  lea     rcx, [rsp+1090h+var_1040]
0x1800308f4  cmp     [rcx], r11d
0x1800308f7  jnz     short loc_180030908
0x1800308f9  movzx   eax, word ptr [r8+4]
0x1800308fe  cmp     [rcx+4], ax
0x180030902  jz      loc_1800309AA
0x180030908  add     rcx, 0Ch
0x18003090c  cmp     rcx, rdx
0x18003090f  jnz     short loc_1800308F4
0x180030911  mov     eax, r9d
0x180030914  add     rax, 0Ch
0x180030918  cmp     rax, 1000h
0x18003091e  ja      short loc_18003093C
0x180030920  movsd   xmm0, qword ptr [r8]
0x180030925  add     r9d, 0Ch
0x180030929  movsd   qword ptr [rdx], xmm0
0x18003092d  inc     r10d
0x180030930  mov     eax, [r8+8]
0x180030934  mov     [rdx+8], eax
0x180030937  mov     [rsp+1090h+var_1050], r9d
0x18003093c  add     r8, 0Ch
0x180030940  lea     rdx, [rsp+1090h+var_1040]
0x180030945  cmp     r8, rsi
0x180030948  jnz     short loc_1800308D7
0x18003094a  mov     eax, [rsp+1090h+var_104C]
0x18003094e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180030955  mov     [rsp+1090h+var_1060], 1
0x18003095d  mov     r8d, r9d
0x180030960  mov     dword ptr [rsp+1090h+var_1068], eax
0x180030964  call    wil_details_NtUpdateWnfStateData
0x180030969  mov     esi, eax
0x18003096b  cmp     esi, 0C0000001h
0x180030971  jnz     short loc_180030984
0x180030973  inc     r15d
0x180030976  cmp     r15d, 64h ; 'd'
0x18003097a  jge     short loc_180030984
0x18003097c  test    edi, edi
0x18003097e  jz      loc_1800307CA
0x180030984  test    ebx, ebx
0x180030986  cmovz   ebx, esi
0x180030989  mov     eax, ebx
0x18003098b  mov     rcx, [rbp+0F90h+var_40]
0x180030992  xor     rcx, rsp; StackCookie
0x180030995  call    __security_check_cookie
0x18003099a  add     rsp, 1068h
0x1800309a1  pop     r15
0x1800309a3  pop     r14
0x1800309a5  pop     rdi
0x1800309a6  pop     rsi
0x1800309a7  pop     rbx
0x1800309a8  pop     rbp
0x1800309a9  retn
0x1800309aa  mov     eax, [r8+8]
0x1800309ae  add     [rcx+8], eax
0x1800309b1  mov     r9d, [rsp+1090h+var_1050]
0x1800309b6  jmp     short loc_18003093C
```
