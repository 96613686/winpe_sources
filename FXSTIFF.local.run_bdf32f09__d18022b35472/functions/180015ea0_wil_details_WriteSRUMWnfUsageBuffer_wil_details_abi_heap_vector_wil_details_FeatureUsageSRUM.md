# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180015ea0`
- end: `0x1800160d9`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `569`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f810`

## callees

- `0x180015ea0`
- `0x180016254`
- `0x180017bce`
- `0x180017c00`
- `0x180017c90`
- `0x180019010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180015f29`
- `KERNEL32!GetModuleHandleW` at `0x180015f29`
- `KERNEL32!GetProcAddress` at `0x180015f40`
- `KERNEL32!GetProcAddress` at `0x180015f40`

## string_xrefs

- `0x180015f22`: `ntdll.dll`

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
0x180015ea0  push    rbp
0x180015ea2  push    rbx
0x180015ea3  push    rsi
0x180015ea4  push    rdi
0x180015ea5  push    r14
0x180015ea7  push    r15
0x180015ea9  lea     rbp, [rsp-0F68h]
0x180015eb1  mov     eax, 1068h
0x180015eb6  call    _alloca_probe
0x180015ebb  sub     rsp, rax
0x180015ebe  mov     rax, cs:__security_cookie
0x180015ec5  xor     rax, rsp
0x180015ec8  mov     [rbp+0F90h+var_40], rax
0x180015ecf  mov     r14, rcx
0x180015ed2  xor     ebx, ebx
0x180015ed4  xor     esi, esi
0x180015ed6  mov     rax, [rcx+8]
0x180015eda  sub     rax, [rcx]
0x180015edd  cmp     rax, 0Ch
0x180015ee1  jb      loc_1800160A5
0x180015ee7  xor     r15d, r15d
0x180015eea  xor     edx, edx; Val
0x180015eec  mov     r8d, 1000h; Size
0x180015ef2  lea     rcx, [rsp+1090h+var_1040]; void *
0x180015ef7  call    memset_0
0x180015efc  mov     [rsp+1090h+var_1050], 1000h
0x180015f04  mov     [rsp+1090h+var_104C], 0
0x180015f0c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180015f14  jnz     short loc_180015F5F
0x180015f16  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015f1d  test    rax, rax
0x180015f20  jnz     short loc_180015F36
0x180015f22  lea     rcx, ModuleName; "ntdll.dll"
0x180015f29  call    cs:__imp_GetModuleHandleW
0x180015f2f  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015f36  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180015f3d  mov     rcx, rax; hModule
0x180015f40  call    cs:__imp_GetProcAddress
0x180015f46  nop
0x180015f47  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180015f4e  test    rax, rax
0x180015f51  jnz     short loc_180015F5F
0x180015f53  mov     edi, 0C0000139h
0x180015f58  mov     ebx, edi
0x180015f5a  jmp     loc_18001608C
0x180015f5f  lea     rax, [rsp+1090h+var_1050]
0x180015f64  mov     [rsp+1090h+var_1068], rax
0x180015f69  lea     rax, [rsp+1090h+var_1040]
0x180015f6e  mov     [rsp+1090h+var_1070], rax
0x180015f73  lea     r9, [rsp+1090h+var_104C]
0x180015f78  xor     r8d, r8d
0x180015f7b  xor     edx, edx
0x180015f7d  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180015f84  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180015f8b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015f90  mov     ebx, eax
0x180015f92  mov     edi, eax
0x180015f94  test    eax, eax
0x180015f96  jnz     loc_18001608C
0x180015f9c  mov     r9d, [rsp+1090h+var_1050]
0x180015fa1  mov     r11, 0AAAAAAAAAAAAAAABh
0x180015fab  mov     rax, r11
0x180015fae  mul     r9
0x180015fb1  shr     rdx, 3
0x180015fb5  lea     rcx, [rdx+rdx*2]
0x180015fb9  shl     rcx, 2
0x180015fbd  cmp     r9, rcx
0x180015fc0  jz      short loc_180015FCA
0x180015fc2  xor     r9d, r9d
0x180015fc5  mov     [rsp+1090h+var_1050], r9d
0x180015fca  mov     ecx, r9d
0x180015fcd  mov     rax, r11
0x180015fd0  mul     rcx
0x180015fd3  mov     r10, rdx
0x180015fd6  shr     r10, 3
0x180015fda  mov     r8, [r14]
0x180015fdd  mov     rcx, [r14+8]
0x180015fe1  sub     rcx, r8
0x180015fe4  mov     rax, r11
0x180015fe7  mul     rcx
0x180015fea  shr     rdx, 3
0x180015fee  lea     rax, [rdx+rdx*2]
0x180015ff2  lea     rsi, [r8+rax*4]
0x180015ff6  jmp     short loc_180016061
0x180015ff8  mov     eax, r10d
0x180015ffb  lea     rcx, [rax+rax*2]
0x180015fff  lea     rdx, [rdx+rcx*4]
0x180016003  lea     rax, [rsp+1090h+var_1040]
0x180016008  cmp     rax, rdx
0x18001600b  jz      short loc_180016032
0x18001600d  lea     rcx, [rsp+1090h+var_1040]
0x180016012  mov     r11d, [r8]
0x180016015  cmp     [rcx], r11d
0x180016018  jnz     short loc_180016029
0x18001601a  movzx   eax, word ptr [r8+4]
0x18001601f  cmp     [rcx+4], ax
0x180016023  jz      loc_1800160CB
0x180016029  add     rcx, 0Ch
0x18001602d  cmp     rcx, rdx
0x180016030  jnz     short loc_180016015
0x180016032  mov     eax, r9d
0x180016035  add     rax, 0Ch
0x180016039  cmp     rax, 1000h
0x18001603f  ja      short loc_18001605D
0x180016041  movsd   xmm0, qword ptr [r8]
0x180016046  movsd   qword ptr [rdx], xmm0
0x18001604a  mov     eax, [r8+8]
0x18001604e  mov     [rdx+8], eax
0x180016051  add     r9d, 0Ch
0x180016055  mov     [rsp+1090h+var_1050], r9d
0x18001605a  inc     r10d
0x18001605d  add     r8, 0Ch
0x180016061  lea     rdx, [rsp+1090h+var_1040]
0x180016066  cmp     r8, rsi
0x180016069  jnz     short loc_180015FF8
0x18001606b  mov     [rsp+1090h+var_1060], 1
0x180016073  mov     eax, [rsp+1090h+var_104C]
0x180016077  mov     dword ptr [rsp+1090h+var_1068], eax
0x18001607b  mov     r8d, r9d
0x18001607e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180016085  call    wil_details_NtUpdateWnfStateData
0x18001608a  mov     esi, eax
0x18001608c  cmp     esi, 0C0000001h
0x180016092  jnz     short loc_1800160A5
0x180016094  inc     r15d
0x180016097  cmp     r15d, 64h ; 'd'
0x18001609b  jge     short loc_1800160A5
0x18001609d  test    edi, edi
0x18001609f  jz      loc_180015EEA
0x1800160a5  test    ebx, ebx
0x1800160a7  cmovz   ebx, esi
0x1800160aa  mov     eax, ebx
0x1800160ac  mov     rcx, [rbp+0F90h+var_40]
0x1800160b3  xor     rcx, rsp; StackCookie
0x1800160b6  call    __security_check_cookie
0x1800160bb  add     rsp, 1068h
0x1800160c2  pop     r15
0x1800160c4  pop     r14
0x1800160c6  pop     rdi
0x1800160c7  pop     rsi
0x1800160c8  pop     rbx
0x1800160c9  pop     rbp
0x1800160ca  retn
0x1800160cb  mov     eax, [r8+8]
0x1800160cf  add     [rcx+8], eax
0x1800160d2  mov     r9d, [rsp+1090h+var_1050]
0x1800160d7  jmp     short loc_18001605D
```
