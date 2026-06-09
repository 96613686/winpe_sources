# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18001836c`
- end: `0x1800185a4`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000fb40`

## callees

- `0x180001d40`
- `0x180002928`
- `0x18001836c`
- `0x180018b10`
- `0x18001d300`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001840c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001840c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800183f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800183f5`

## string_xrefs

- `0x1800183ee`: `ntdll.dll`

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
0x18001836c  push    rbp
0x18001836e  push    rbx
0x18001836f  push    rsi
0x180018370  push    rdi
0x180018371  push    r14
0x180018373  push    r15
0x180018375  lea     rbp, [rsp-0F68h]
0x18001837d  mov     eax, 1068h
0x180018382  call    _alloca_probe
0x180018387  sub     rsp, rax
0x18001838a  mov     rax, cs:__security_cookie
0x180018391  xor     rax, rsp
0x180018394  mov     [rbp+0F90h+var_40], rax
0x18001839b  mov     rax, [rcx+8]
0x18001839f  xor     ebx, ebx
0x1800183a1  sub     rax, [rcx]
0x1800183a4  xor     esi, esi
0x1800183a6  mov     r14, rcx
0x1800183a9  cmp     rax, 0Ch
0x1800183ad  jb      loc_180018570
0x1800183b3  xor     r15d, r15d
0x1800183b6  xor     edx, edx; Val
0x1800183b8  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800183bd  mov     r8d, 1000h; Size
0x1800183c3  call    memset_0
0x1800183c8  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x1800183d0  mov     [rsp+1090h+var_1050], 1000h
0x1800183d8  mov     [rsp+1090h+var_104C], 0
0x1800183e0  jnz     short loc_18001842A
0x1800183e2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800183e9  test    rax, rax
0x1800183ec  jnz     short loc_180018402
0x1800183ee  lea     rcx, ModuleName; "ntdll.dll"
0x1800183f5  call    cs:__imp_GetModuleHandleW
0x1800183fb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180018402  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180018409  mov     rcx, rax; hModule
0x18001840c  call    cs:__imp_GetProcAddress
0x180018412  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180018419  test    rax, rax
0x18001841c  jnz     short loc_18001842A
0x18001841e  mov     edi, 0C0000139h
0x180018423  mov     ebx, edi
0x180018425  jmp     loc_180018557
0x18001842a  lea     rax, [rsp+1090h+var_1050]
0x18001842f  xor     r8d, r8d
0x180018432  mov     [rsp+1090h+var_1068], rax
0x180018437  lea     r9, [rsp+1090h+var_104C]
0x18001843c  lea     rax, [rsp+1090h+var_1040]
0x180018441  xor     edx, edx
0x180018443  mov     [rsp+1090h+var_1070], rax
0x180018448  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18001844f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180018456  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001845b  mov     ebx, eax
0x18001845d  mov     edi, eax
0x18001845f  test    eax, eax
0x180018461  jnz     loc_180018557
0x180018467  mov     r9d, [rsp+1090h+var_1050]
0x18001846c  mov     r11, 0AAAAAAAAAAAAAAABh
0x180018476  mov     rax, r11
0x180018479  mul     r9
0x18001847c  shr     rdx, 3
0x180018480  lea     rcx, [rdx+rdx*2]
0x180018484  shl     rcx, 2
0x180018488  cmp     r9, rcx
0x18001848b  jz      short loc_180018495
0x18001848d  xor     r9d, r9d
0x180018490  mov     [rsp+1090h+var_1050], r9d
0x180018495  mov     r8, [r14]
0x180018498  mov     rax, r11
0x18001849b  mov     ecx, r9d
0x18001849e  mul     rcx
0x1800184a1  mov     rcx, [r14+8]
0x1800184a5  mov     rax, r11
0x1800184a8  mov     r10, rdx
0x1800184ab  sub     rcx, r8
0x1800184ae  mul     rcx
0x1800184b1  shr     r10, 3
0x1800184b5  shr     rdx, 3
0x1800184b9  lea     rax, [rdx+rdx*2]
0x1800184bd  lea     rsi, [r8+rax*4]
0x1800184c1  jmp     short loc_18001852C
0x1800184c3  mov     eax, r10d
0x1800184c6  lea     rcx, [rax+rax*2]
0x1800184ca  lea     rdx, [rdx+rcx*4]
0x1800184ce  lea     rax, [rsp+1090h+var_1040]
0x1800184d3  cmp     rax, rdx
0x1800184d6  jz      short loc_1800184FD
0x1800184d8  mov     r11d, [r8]
0x1800184db  lea     rcx, [rsp+1090h+var_1040]
0x1800184e0  cmp     [rcx], r11d
0x1800184e3  jnz     short loc_1800184F4
0x1800184e5  movzx   eax, word ptr [r8+4]
0x1800184ea  cmp     [rcx+4], ax
0x1800184ee  jz      loc_180018596
0x1800184f4  add     rcx, 0Ch
0x1800184f8  cmp     rcx, rdx
0x1800184fb  jnz     short loc_1800184E0
0x1800184fd  mov     eax, r9d
0x180018500  add     rax, 0Ch
0x180018504  cmp     rax, 1000h
0x18001850a  ja      short loc_180018528
0x18001850c  movsd   xmm0, qword ptr [r8]
0x180018511  add     r9d, 0Ch
0x180018515  movsd   qword ptr [rdx], xmm0
0x180018519  inc     r10d
0x18001851c  mov     eax, [r8+8]
0x180018520  mov     [rdx+8], eax
0x180018523  mov     [rsp+1090h+var_1050], r9d
0x180018528  add     r8, 0Ch
0x18001852c  lea     rdx, [rsp+1090h+var_1040]
0x180018531  cmp     r8, rsi
0x180018534  jnz     short loc_1800184C3
0x180018536  mov     eax, [rsp+1090h+var_104C]
0x18001853a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180018541  mov     [rsp+1090h+var_1060], 1
0x180018549  mov     r8d, r9d
0x18001854c  mov     dword ptr [rsp+1090h+var_1068], eax
0x180018550  call    wil_details_NtUpdateWnfStateData
0x180018555  mov     esi, eax
0x180018557  cmp     esi, 0C0000001h
0x18001855d  jnz     short loc_180018570
0x18001855f  inc     r15d
0x180018562  cmp     r15d, 64h ; 'd'
0x180018566  jge     short loc_180018570
0x180018568  test    edi, edi
0x18001856a  jz      loc_1800183B6
0x180018570  test    ebx, ebx
0x180018572  cmovz   ebx, esi
0x180018575  mov     eax, ebx
0x180018577  mov     rcx, [rbp+0F90h+var_40]
0x18001857e  xor     rcx, rsp; StackCookie
0x180018581  call    __security_check_cookie
0x180018586  add     rsp, 1068h
0x18001858d  pop     r15
0x18001858f  pop     r14
0x180018591  pop     rdi
0x180018592  pop     rsi
0x180018593  pop     rbx
0x180018594  pop     rbp
0x180018595  retn
0x180018596  mov     eax, [r8+8]
0x18001859a  add     [rcx+8], eax
0x18001859d  mov     r9d, [rsp+1090h+var_1050]
0x1800185a2  jmp     short loc_180018528
```
