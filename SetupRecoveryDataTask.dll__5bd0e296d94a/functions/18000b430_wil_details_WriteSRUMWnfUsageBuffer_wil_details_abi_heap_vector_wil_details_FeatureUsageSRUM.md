# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000b430`
- end: `0x18000b668`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002200`

## callees

- `0x18000b430`
- `0x18000be00`
- `0x18000c5e2`
- `0x18000c610`
- `0x18000c6d0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b4d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b4d0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b4b9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b4b9`

## string_xrefs

- `0x18000b4b2`: `ntdll.dll`

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
0x18000b430  push    rbp
0x18000b432  push    rbx
0x18000b433  push    rsi
0x18000b434  push    rdi
0x18000b435  push    r14
0x18000b437  push    r15
0x18000b439  lea     rbp, [rsp-0F68h]
0x18000b441  mov     eax, 1068h
0x18000b446  call    _alloca_probe
0x18000b44b  sub     rsp, rax
0x18000b44e  mov     rax, cs:__security_cookie
0x18000b455  xor     rax, rsp
0x18000b458  mov     [rbp+0F90h+var_40], rax
0x18000b45f  mov     rax, [rcx+8]
0x18000b463  xor     ebx, ebx
0x18000b465  sub     rax, [rcx]
0x18000b468  xor     esi, esi
0x18000b46a  mov     r14, rcx
0x18000b46d  cmp     rax, 0Ch
0x18000b471  jb      loc_18000B634
0x18000b477  xor     r15d, r15d
0x18000b47a  xor     edx, edx; Val
0x18000b47c  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000b481  mov     r8d, 1000h; Size
0x18000b487  call    memset_0
0x18000b48c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000b494  mov     [rsp+1090h+var_1050], 1000h
0x18000b49c  mov     [rsp+1090h+var_104C], 0
0x18000b4a4  jnz     short loc_18000B4EE
0x18000b4a6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b4ad  test    rax, rax
0x18000b4b0  jnz     short loc_18000B4C6
0x18000b4b2  lea     rcx, ModuleName; "ntdll.dll"
0x18000b4b9  call    cs:__imp_GetModuleHandleW
0x18000b4bf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b4c6  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b4cd  mov     rcx, rax; hModule
0x18000b4d0  call    cs:__imp_GetProcAddress
0x18000b4d6  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b4dd  test    rax, rax
0x18000b4e0  jnz     short loc_18000B4EE
0x18000b4e2  mov     edi, 0C0000139h
0x18000b4e7  mov     ebx, edi
0x18000b4e9  jmp     loc_18000B61B
0x18000b4ee  lea     rax, [rsp+1090h+var_1050]
0x18000b4f3  xor     r8d, r8d
0x18000b4f6  mov     [rsp+1090h+var_1068], rax
0x18000b4fb  lea     r9, [rsp+1090h+var_104C]
0x18000b500  lea     rax, [rsp+1090h+var_1040]
0x18000b505  xor     edx, edx
0x18000b507  mov     [rsp+1090h+var_1070], rax
0x18000b50c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b513  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b51a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b51f  mov     ebx, eax
0x18000b521  mov     edi, eax
0x18000b523  test    eax, eax
0x18000b525  jnz     loc_18000B61B
0x18000b52b  mov     r9d, [rsp+1090h+var_1050]
0x18000b530  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000b53a  mov     rax, r11
0x18000b53d  mul     r9
0x18000b540  shr     rdx, 3
0x18000b544  lea     rcx, [rdx+rdx*2]
0x18000b548  shl     rcx, 2
0x18000b54c  cmp     r9, rcx
0x18000b54f  jz      short loc_18000B559
0x18000b551  xor     r9d, r9d
0x18000b554  mov     [rsp+1090h+var_1050], r9d
0x18000b559  mov     r8, [r14]
0x18000b55c  mov     rax, r11
0x18000b55f  mov     ecx, r9d
0x18000b562  mul     rcx
0x18000b565  mov     rcx, [r14+8]
0x18000b569  mov     rax, r11
0x18000b56c  mov     r10, rdx
0x18000b56f  sub     rcx, r8
0x18000b572  mul     rcx
0x18000b575  shr     r10, 3
0x18000b579  shr     rdx, 3
0x18000b57d  lea     rax, [rdx+rdx*2]
0x18000b581  lea     rsi, [r8+rax*4]
0x18000b585  jmp     short loc_18000B5F0
0x18000b587  mov     eax, r10d
0x18000b58a  lea     rcx, [rax+rax*2]
0x18000b58e  lea     rdx, [rdx+rcx*4]
0x18000b592  lea     rax, [rsp+1090h+var_1040]
0x18000b597  cmp     rax, rdx
0x18000b59a  jz      short loc_18000B5C1
0x18000b59c  mov     r11d, [r8]
0x18000b59f  lea     rcx, [rsp+1090h+var_1040]
0x18000b5a4  cmp     [rcx], r11d
0x18000b5a7  jnz     short loc_18000B5B8
0x18000b5a9  movzx   eax, word ptr [r8+4]
0x18000b5ae  cmp     [rcx+4], ax
0x18000b5b2  jz      loc_18000B65A
0x18000b5b8  add     rcx, 0Ch
0x18000b5bc  cmp     rcx, rdx
0x18000b5bf  jnz     short loc_18000B5A4
0x18000b5c1  mov     eax, r9d
0x18000b5c4  add     rax, 0Ch
0x18000b5c8  cmp     rax, 1000h
0x18000b5ce  ja      short loc_18000B5EC
0x18000b5d0  movsd   xmm0, qword ptr [r8]
0x18000b5d5  add     r9d, 0Ch
0x18000b5d9  movsd   qword ptr [rdx], xmm0
0x18000b5dd  inc     r10d
0x18000b5e0  mov     eax, [r8+8]
0x18000b5e4  mov     [rdx+8], eax
0x18000b5e7  mov     [rsp+1090h+var_1050], r9d
0x18000b5ec  add     r8, 0Ch
0x18000b5f0  lea     rdx, [rsp+1090h+var_1040]
0x18000b5f5  cmp     r8, rsi
0x18000b5f8  jnz     short loc_18000B587
0x18000b5fa  mov     eax, [rsp+1090h+var_104C]
0x18000b5fe  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b605  mov     [rsp+1090h+var_1060], 1
0x18000b60d  mov     r8d, r9d
0x18000b610  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000b614  call    wil_details_NtUpdateWnfStateData
0x18000b619  mov     esi, eax
0x18000b61b  cmp     esi, 0C0000001h
0x18000b621  jnz     short loc_18000B634
0x18000b623  inc     r15d
0x18000b626  cmp     r15d, 64h ; 'd'
0x18000b62a  jge     short loc_18000B634
0x18000b62c  test    edi, edi
0x18000b62e  jz      loc_18000B47A
0x18000b634  test    ebx, ebx
0x18000b636  cmovz   ebx, esi
0x18000b639  mov     eax, ebx
0x18000b63b  mov     rcx, [rbp+0F90h+var_40]
0x18000b642  xor     rcx, rsp; StackCookie
0x18000b645  call    __security_check_cookie
0x18000b64a  add     rsp, 1068h
0x18000b651  pop     r15
0x18000b653  pop     r14
0x18000b655  pop     rdi
0x18000b656  pop     rsi
0x18000b657  pop     rbx
0x18000b658  pop     rbp
0x18000b659  retn
0x18000b65a  mov     eax, [r8+8]
0x18000b65e  add     [rcx+8], eax
0x18000b661  mov     r9d, [rsp+1090h+var_1050]
0x18000b666  jmp     short loc_18000B5EC
```
