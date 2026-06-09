# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000cde8`
- end: `0x18000d021`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180002190`

## callees

- `0x18000cde8`
- `0x18000e560`
- `0x18000f5c2`
- `0x18000f5f0`
- `0x18000f680`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x18000ce71`
- `KERNEL32!GetModuleHandleW` at `0x18000ce71`
- `KERNEL32!GetProcAddress` at `0x18000ce88`
- `KERNEL32!GetProcAddress` at `0x18000ce88`

## string_xrefs

- `0x18000ce6a`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
__int64 __fastcall wil_details_WriteSRUMWnfUsageBuffer(__int64 *a1)
{
  unsigned int v2; // ebx
  unsigned int updated; // esi
  int v4; // r15d
  HMODULE ModuleHandleW; // rax
  int v6; // edi
  __int64 v7; // r9
  int v8; // r10d
  __int64 v9; // r8
  unsigned __int64 v10; // rsi
  _DWORD *v11; // rdx
  _DWORD *v12; // rcx
  unsigned int v14; // [rsp+40h] [rbp-C0h]
  int v15[3]; // [rsp+44h] [rbp-BCh] BYREF
  _DWORD v16[1024]; // [rsp+50h] [rbp-B0h] BYREF

  v2 = 0;
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
        v2 = ((__int64 (__fastcall *)(void *, _QWORD, _QWORD, int *))g_wil_details_pfnNtQueryWnfStateData)(
               &__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM,
               0,
               0,
               v15);
        v6 = v2;
        if ( !v2 )
        {
          v7 = 0;
          v14 = 0;
          v8 = 0;
          v9 = *a1;
          v10 = *a1 + 12 * ((a1[1] - *a1) / 0xCuLL);
          while ( v9 != v10 )
          {
            v11 = &v16[3 * v8];
            if ( v16 == v11 )
            {
LABEL_15:
              if ( (unsigned __int64)(unsigned int)v7 + 12 <= 0x1000 )
              {
                *(_QWORD *)v11 = *(_QWORD *)v9;
                v11[2] = *(_DWORD *)(v9 + 8);
                v7 = (unsigned int)(v7 + 12);
                v14 = v7;
                ++v8;
              }
            }
            else
            {
              v12 = v16;
              while ( *v12 != *(_DWORD *)v9 || *((_WORD *)v12 + 2) != *(_WORD *)(v9 + 4) )
              {
                v12 += 3;
                if ( v12 == v11 )
                  goto LABEL_15;
              }
              v12[2] += *(_DWORD *)(v9 + 8);
              v7 = v14;
            }
            v9 += 12;
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
        v2 = -1073741511;
      }
      if ( updated != -1073741823 )
        break;
      if ( ++v4 >= 100 )
        break;
    }
    while ( !v6 );
  }
  if ( !v2 )
    return updated;
  return v2;
}

```

## disassembly

```asm
0x18000cde8  push    rbp
0x18000cdea  push    rbx
0x18000cdeb  push    rsi
0x18000cdec  push    rdi
0x18000cded  push    r14
0x18000cdef  push    r15
0x18000cdf1  lea     rbp, [rsp-0F68h]
0x18000cdf9  mov     eax, 1068h
0x18000cdfe  call    _alloca_probe
0x18000ce03  sub     rsp, rax
0x18000ce06  mov     rax, cs:__security_cookie
0x18000ce0d  xor     rax, rsp
0x18000ce10  mov     [rbp+0F90h+var_40], rax
0x18000ce17  mov     r14, rcx
0x18000ce1a  xor     ebx, ebx
0x18000ce1c  xor     esi, esi
0x18000ce1e  mov     rax, [rcx+8]
0x18000ce22  sub     rax, [rcx]
0x18000ce25  cmp     rax, 0Ch
0x18000ce29  jb      loc_18000CFED
0x18000ce2f  xor     r15d, r15d
0x18000ce32  xor     edx, edx; Val
0x18000ce34  mov     r8d, 1000h; Size
0x18000ce3a  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ce3f  call    memset_0
0x18000ce44  mov     [rsp+1090h+var_1050], 1000h
0x18000ce4c  mov     [rsp+1090h+var_104C], 0
0x18000ce54  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000ce5c  jnz     short loc_18000CEA7
0x18000ce5e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ce65  test    rax, rax
0x18000ce68  jnz     short loc_18000CE7E
0x18000ce6a  lea     rcx, ModuleName; "ntdll.dll"
0x18000ce71  call    cs:__imp_GetModuleHandleW
0x18000ce77  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000ce7e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000ce85  mov     rcx, rax; hModule
0x18000ce88  call    cs:__imp_GetProcAddress
0x18000ce8e  nop
0x18000ce8f  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000ce96  test    rax, rax
0x18000ce99  jnz     short loc_18000CEA7
0x18000ce9b  mov     edi, 0C0000139h
0x18000cea0  mov     ebx, edi
0x18000cea2  jmp     loc_18000CFD4
0x18000cea7  lea     rax, [rsp+1090h+var_1050]
0x18000ceac  mov     [rsp+1090h+var_1068], rax
0x18000ceb1  lea     rax, [rsp+1090h+var_1040]
0x18000ceb6  mov     [rsp+1090h+var_1070], rax
0x18000cebb  lea     r9, [rsp+1090h+var_104C]
0x18000cec0  xor     r8d, r8d
0x18000cec3  xor     edx, edx
0x18000cec5  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cecc  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000ced3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ced8  mov     ebx, eax
0x18000ceda  mov     edi, eax
0x18000cedc  test    eax, eax
0x18000cede  jnz     loc_18000CFD4
0x18000cee4  mov     r9d, [rsp+1090h+var_1050]
0x18000cee9  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000cef3  mov     rax, r11
0x18000cef6  mul     r9
0x18000cef9  shr     rdx, 3
0x18000cefd  lea     rcx, [rdx+rdx*2]
0x18000cf01  shl     rcx, 2
0x18000cf05  cmp     r9, rcx
0x18000cf08  jz      short loc_18000CF12
0x18000cf0a  xor     r9d, r9d
0x18000cf0d  mov     [rsp+1090h+var_1050], r9d
0x18000cf12  mov     ecx, r9d
0x18000cf15  mov     rax, r11
0x18000cf18  mul     rcx
0x18000cf1b  mov     r10, rdx
0x18000cf1e  shr     r10, 3
0x18000cf22  mov     r8, [r14]
0x18000cf25  mov     rcx, [r14+8]
0x18000cf29  sub     rcx, r8
0x18000cf2c  mov     rax, r11
0x18000cf2f  mul     rcx
0x18000cf32  shr     rdx, 3
0x18000cf36  lea     rax, [rdx+rdx*2]
0x18000cf3a  lea     rsi, [r8+rax*4]
0x18000cf3e  jmp     short loc_18000CFA9
0x18000cf40  mov     eax, r10d
0x18000cf43  lea     rcx, [rax+rax*2]
0x18000cf47  lea     rdx, [rdx+rcx*4]
0x18000cf4b  lea     rax, [rsp+1090h+var_1040]
0x18000cf50  cmp     rax, rdx
0x18000cf53  jz      short loc_18000CF7A
0x18000cf55  lea     rcx, [rsp+1090h+var_1040]
0x18000cf5a  mov     r11d, [r8]
0x18000cf5d  cmp     [rcx], r11d
0x18000cf60  jnz     short loc_18000CF71
0x18000cf62  movzx   eax, word ptr [r8+4]
0x18000cf67  cmp     [rcx+4], ax
0x18000cf6b  jz      loc_18000D013
0x18000cf71  add     rcx, 0Ch
0x18000cf75  cmp     rcx, rdx
0x18000cf78  jnz     short loc_18000CF5D
0x18000cf7a  mov     eax, r9d
0x18000cf7d  add     rax, 0Ch
0x18000cf81  cmp     rax, 1000h
0x18000cf87  ja      short loc_18000CFA5
0x18000cf89  movsd   xmm0, qword ptr [r8]
0x18000cf8e  movsd   qword ptr [rdx], xmm0
0x18000cf92  mov     eax, [r8+8]
0x18000cf96  mov     [rdx+8], eax
0x18000cf99  add     r9d, 0Ch
0x18000cf9d  mov     [rsp+1090h+var_1050], r9d
0x18000cfa2  inc     r10d
0x18000cfa5  add     r8, 0Ch
0x18000cfa9  lea     rdx, [rsp+1090h+var_1040]
0x18000cfae  cmp     r8, rsi
0x18000cfb1  jnz     short loc_18000CF40
0x18000cfb3  mov     [rsp+1090h+var_1060], 1
0x18000cfbb  mov     eax, [rsp+1090h+var_104C]
0x18000cfbf  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000cfc3  mov     r8d, r9d
0x18000cfc6  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000cfcd  call    wil_details_NtUpdateWnfStateData
0x18000cfd2  mov     esi, eax
0x18000cfd4  cmp     esi, 0C0000001h
0x18000cfda  jnz     short loc_18000CFED
0x18000cfdc  inc     r15d
0x18000cfdf  cmp     r15d, 64h ; 'd'
0x18000cfe3  jge     short loc_18000CFED
0x18000cfe5  test    edi, edi
0x18000cfe7  jz      loc_18000CE32
0x18000cfed  test    ebx, ebx
0x18000cfef  cmovz   ebx, esi
0x18000cff2  mov     eax, ebx
0x18000cff4  mov     rcx, [rbp+0F90h+var_40]
0x18000cffb  xor     rcx, rsp; StackCookie
0x18000cffe  call    __security_check_cookie
0x18000d003  add     rsp, 1068h
0x18000d00a  pop     r15
0x18000d00c  pop     r14
0x18000d00e  pop     rdi
0x18000d00f  pop     rsi
0x18000d010  pop     rbx
0x18000d011  pop     rbp
0x18000d012  retn
0x18000d013  mov     eax, [r8+8]
0x18000d017  add     [rcx+8], eax
0x18000d01a  mov     r9d, [rsp+1090h+var_1050]
0x18000d01f  jmp     short loc_18000CFA5
```
