# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000d8b0`
- end: `0x14000dae8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140006b00`

## callees

- `0x14000295f`
- `0x14000d8b0`
- `0x14000dfe0`
- `0x14000e1c0`
- `0x14000e280`
- `0x14000f010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000d950`
- `KERNEL32!GetProcAddress` at `0x14000d950`
- `KERNEL32!GetModuleHandleW` at `0x14000d939`
- `KERNEL32!GetModuleHandleW` at `0x14000d939`

## string_xrefs

- `0x14000d932`: `ntdll.dll`

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
0x14000d8b0  push    rbp
0x14000d8b2  push    rbx
0x14000d8b3  push    rsi
0x14000d8b4  push    rdi
0x14000d8b5  push    r14
0x14000d8b7  push    r15
0x14000d8b9  lea     rbp, [rsp-0F68h]
0x14000d8c1  mov     eax, 1068h
0x14000d8c6  call    _alloca_probe
0x14000d8cb  sub     rsp, rax
0x14000d8ce  mov     rax, cs:__security_cookie
0x14000d8d5  xor     rax, rsp
0x14000d8d8  mov     [rbp+0F90h+var_40], rax
0x14000d8df  mov     rax, [rcx+8]
0x14000d8e3  xor     ebx, ebx
0x14000d8e5  sub     rax, [rcx]
0x14000d8e8  xor     esi, esi
0x14000d8ea  mov     r14, rcx
0x14000d8ed  cmp     rax, 0Ch
0x14000d8f1  jb      loc_14000DAB4
0x14000d8f7  xor     r15d, r15d
0x14000d8fa  xor     edx, edx; Val
0x14000d8fc  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000d901  mov     r8d, 1000h; Size
0x14000d907  call    memset_0
0x14000d90c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000d914  mov     [rsp+1090h+var_1050], 1000h
0x14000d91c  mov     [rsp+1090h+var_104C], 0
0x14000d924  jnz     short loc_14000D96E
0x14000d926  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d92d  test    rax, rax
0x14000d930  jnz     short loc_14000D946
0x14000d932  lea     rcx, ModuleName; "ntdll.dll"
0x14000d939  call    cs:__imp_GetModuleHandleW
0x14000d93f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000d946  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000d94d  mov     rcx, rax; hModule
0x14000d950  call    cs:__imp_GetProcAddress
0x14000d956  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000d95d  test    rax, rax
0x14000d960  jnz     short loc_14000D96E
0x14000d962  mov     edi, 0C0000139h
0x14000d967  mov     ebx, edi
0x14000d969  jmp     loc_14000DA9B
0x14000d96e  lea     rax, [rsp+1090h+var_1050]
0x14000d973  xor     r8d, r8d
0x14000d976  mov     [rsp+1090h+var_1068], rax
0x14000d97b  lea     r9, [rsp+1090h+var_104C]
0x14000d980  lea     rax, [rsp+1090h+var_1040]
0x14000d985  xor     edx, edx
0x14000d987  mov     [rsp+1090h+var_1070], rax
0x14000d98c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000d993  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000d99a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d99f  mov     ebx, eax
0x14000d9a1  mov     edi, eax
0x14000d9a3  test    eax, eax
0x14000d9a5  jnz     loc_14000DA9B
0x14000d9ab  mov     r9d, [rsp+1090h+var_1050]
0x14000d9b0  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000d9ba  mov     rax, r11
0x14000d9bd  mul     r9
0x14000d9c0  shr     rdx, 3
0x14000d9c4  lea     rcx, [rdx+rdx*2]
0x14000d9c8  shl     rcx, 2
0x14000d9cc  cmp     r9, rcx
0x14000d9cf  jz      short loc_14000D9D9
0x14000d9d1  xor     r9d, r9d
0x14000d9d4  mov     [rsp+1090h+var_1050], r9d
0x14000d9d9  mov     r8, [r14]
0x14000d9dc  mov     rax, r11
0x14000d9df  mov     ecx, r9d
0x14000d9e2  mul     rcx
0x14000d9e5  mov     rcx, [r14+8]
0x14000d9e9  mov     rax, r11
0x14000d9ec  mov     r10, rdx
0x14000d9ef  sub     rcx, r8
0x14000d9f2  mul     rcx
0x14000d9f5  shr     r10, 3
0x14000d9f9  shr     rdx, 3
0x14000d9fd  lea     rax, [rdx+rdx*2]
0x14000da01  lea     rsi, [r8+rax*4]
0x14000da05  jmp     short loc_14000DA70
0x14000da07  mov     eax, r10d
0x14000da0a  lea     rcx, [rax+rax*2]
0x14000da0e  lea     rdx, [rdx+rcx*4]
0x14000da12  lea     rax, [rsp+1090h+var_1040]
0x14000da17  cmp     rax, rdx
0x14000da1a  jz      short loc_14000DA41
0x14000da1c  mov     r11d, [r8]
0x14000da1f  lea     rcx, [rsp+1090h+var_1040]
0x14000da24  cmp     [rcx], r11d
0x14000da27  jnz     short loc_14000DA38
0x14000da29  movzx   eax, word ptr [r8+4]
0x14000da2e  cmp     [rcx+4], ax
0x14000da32  jz      loc_14000DADA
0x14000da38  add     rcx, 0Ch
0x14000da3c  cmp     rcx, rdx
0x14000da3f  jnz     short loc_14000DA24
0x14000da41  mov     eax, r9d
0x14000da44  add     rax, 0Ch
0x14000da48  cmp     rax, 1000h
0x14000da4e  ja      short loc_14000DA6C
0x14000da50  movsd   xmm0, qword ptr [r8]
0x14000da55  add     r9d, 0Ch
0x14000da59  movsd   qword ptr [rdx], xmm0
0x14000da5d  inc     r10d
0x14000da60  mov     eax, [r8+8]
0x14000da64  mov     [rdx+8], eax
0x14000da67  mov     [rsp+1090h+var_1050], r9d
0x14000da6c  add     r8, 0Ch
0x14000da70  lea     rdx, [rsp+1090h+var_1040]
0x14000da75  cmp     r8, rsi
0x14000da78  jnz     short loc_14000DA07
0x14000da7a  mov     eax, [rsp+1090h+var_104C]
0x14000da7e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000da85  mov     [rsp+1090h+var_1060], 1
0x14000da8d  mov     r8d, r9d
0x14000da90  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000da94  call    wil_details_NtUpdateWnfStateData
0x14000da99  mov     esi, eax
0x14000da9b  cmp     esi, 0C0000001h
0x14000daa1  jnz     short loc_14000DAB4
0x14000daa3  inc     r15d
0x14000daa6  cmp     r15d, 64h ; 'd'
0x14000daaa  jge     short loc_14000DAB4
0x14000daac  test    edi, edi
0x14000daae  jz      loc_14000D8FA
0x14000dab4  test    ebx, ebx
0x14000dab6  cmovz   ebx, esi
0x14000dab9  mov     eax, ebx
0x14000dabb  mov     rcx, [rbp+0F90h+var_40]
0x14000dac2  xor     rcx, rsp; StackCookie
0x14000dac5  call    __security_check_cookie
0x14000daca  add     rsp, 1068h
0x14000dad1  pop     r15
0x14000dad3  pop     r14
0x14000dad5  pop     rdi
0x14000dad6  pop     rsi
0x14000dad7  pop     rbx
0x14000dad8  pop     rbp
0x14000dad9  retn
0x14000dada  mov     eax, [r8+8]
0x14000dade  add     [rcx+8], eax
0x14000dae1  mov     r9d, [rsp+1090h+var_1050]
0x14000dae6  jmp     short loc_14000DA6C
```
