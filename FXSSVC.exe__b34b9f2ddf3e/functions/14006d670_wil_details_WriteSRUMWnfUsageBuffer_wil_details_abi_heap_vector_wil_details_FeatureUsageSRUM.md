# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14006d670`
- end: `0x14006d8a8`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140067350`

## callees

- `0x140002c43`
- `0x14006d670`
- `0x14006eed8`
- `0x1400818b0`
- `0x140081970`
- `0x140085010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14006d710`
- `KERNEL32!GetProcAddress` at `0x14006d710`
- `KERNEL32!GetModuleHandleW` at `0x14006d6f9`
- `KERNEL32!GetModuleHandleW` at `0x14006d6f9`

## string_xrefs

- `0x14006d6f2`: `ntdll.dll`

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
0x14006d670  push    rbp
0x14006d672  push    rbx
0x14006d673  push    rsi
0x14006d674  push    rdi
0x14006d675  push    r14
0x14006d677  push    r15
0x14006d679  lea     rbp, [rsp-0F68h]
0x14006d681  mov     eax, 1068h
0x14006d686  call    _alloca_probe
0x14006d68b  sub     rsp, rax
0x14006d68e  mov     rax, cs:__security_cookie
0x14006d695  xor     rax, rsp
0x14006d698  mov     [rbp+0F90h+var_40], rax
0x14006d69f  mov     rax, [rcx+8]
0x14006d6a3  xor     ebx, ebx
0x14006d6a5  sub     rax, [rcx]
0x14006d6a8  xor     esi, esi
0x14006d6aa  mov     r14, rcx
0x14006d6ad  cmp     rax, 0Ch
0x14006d6b1  jb      loc_14006D874
0x14006d6b7  xor     r15d, r15d
0x14006d6ba  xor     edx, edx; Val
0x14006d6bc  lea     rcx, [rsp+1090h+var_1040]; void *
0x14006d6c1  mov     r8d, 1000h; Size
0x14006d6c7  call    memset_0
0x14006d6cc  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14006d6d4  mov     [rsp+1090h+var_1050], 1000h
0x14006d6dc  mov     [rsp+1090h+var_104C], 0
0x14006d6e4  jnz     short loc_14006D72E
0x14006d6e6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14006d6ed  test    rax, rax
0x14006d6f0  jnz     short loc_14006D706
0x14006d6f2  lea     rcx, ModuleName; "ntdll.dll"
0x14006d6f9  call    cs:__imp_GetModuleHandleW
0x14006d6ff  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14006d706  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14006d70d  mov     rcx, rax; hModule
0x14006d710  call    cs:__imp_GetProcAddress
0x14006d716  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14006d71d  test    rax, rax
0x14006d720  jnz     short loc_14006D72E
0x14006d722  mov     edi, 0C0000139h
0x14006d727  mov     ebx, edi
0x14006d729  jmp     loc_14006D85B
0x14006d72e  lea     rax, [rsp+1090h+var_1050]
0x14006d733  xor     r8d, r8d
0x14006d736  mov     [rsp+1090h+var_1068], rax
0x14006d73b  lea     r9, [rsp+1090h+var_104C]
0x14006d740  lea     rax, [rsp+1090h+var_1040]
0x14006d745  xor     edx, edx
0x14006d747  mov     [rsp+1090h+var_1070], rax
0x14006d74c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14006d753  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14006d75a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14006d75f  mov     ebx, eax
0x14006d761  mov     edi, eax
0x14006d763  test    eax, eax
0x14006d765  jnz     loc_14006D85B
0x14006d76b  mov     r9d, [rsp+1090h+var_1050]
0x14006d770  mov     r11, 0AAAAAAAAAAAAAAABh
0x14006d77a  mov     rax, r11
0x14006d77d  mul     r9
0x14006d780  shr     rdx, 3
0x14006d784  lea     rcx, [rdx+rdx*2]
0x14006d788  shl     rcx, 2
0x14006d78c  cmp     r9, rcx
0x14006d78f  jz      short loc_14006D799
0x14006d791  xor     r9d, r9d
0x14006d794  mov     [rsp+1090h+var_1050], r9d
0x14006d799  mov     r8, [r14]
0x14006d79c  mov     rax, r11
0x14006d79f  mov     ecx, r9d
0x14006d7a2  mul     rcx
0x14006d7a5  mov     rcx, [r14+8]
0x14006d7a9  mov     rax, r11
0x14006d7ac  mov     r10, rdx
0x14006d7af  sub     rcx, r8
0x14006d7b2  mul     rcx
0x14006d7b5  shr     r10, 3
0x14006d7b9  shr     rdx, 3
0x14006d7bd  lea     rax, [rdx+rdx*2]
0x14006d7c1  lea     rsi, [r8+rax*4]
0x14006d7c5  jmp     short loc_14006D830
0x14006d7c7  mov     eax, r10d
0x14006d7ca  lea     rcx, [rax+rax*2]
0x14006d7ce  lea     rdx, [rdx+rcx*4]
0x14006d7d2  lea     rax, [rsp+1090h+var_1040]
0x14006d7d7  cmp     rax, rdx
0x14006d7da  jz      short loc_14006D801
0x14006d7dc  mov     r11d, [r8]
0x14006d7df  lea     rcx, [rsp+1090h+var_1040]
0x14006d7e4  cmp     [rcx], r11d
0x14006d7e7  jnz     short loc_14006D7F8
0x14006d7e9  movzx   eax, word ptr [r8+4]
0x14006d7ee  cmp     [rcx+4], ax
0x14006d7f2  jz      loc_14006D89A
0x14006d7f8  add     rcx, 0Ch
0x14006d7fc  cmp     rcx, rdx
0x14006d7ff  jnz     short loc_14006D7E4
0x14006d801  mov     eax, r9d
0x14006d804  add     rax, 0Ch
0x14006d808  cmp     rax, 1000h
0x14006d80e  ja      short loc_14006D82C
0x14006d810  movsd   xmm0, qword ptr [r8]
0x14006d815  add     r9d, 0Ch
0x14006d819  movsd   qword ptr [rdx], xmm0
0x14006d81d  inc     r10d
0x14006d820  mov     eax, [r8+8]
0x14006d824  mov     [rdx+8], eax
0x14006d827  mov     [rsp+1090h+var_1050], r9d
0x14006d82c  add     r8, 0Ch
0x14006d830  lea     rdx, [rsp+1090h+var_1040]
0x14006d835  cmp     r8, rsi
0x14006d838  jnz     short loc_14006D7C7
0x14006d83a  mov     eax, [rsp+1090h+var_104C]
0x14006d83e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14006d845  mov     [rsp+1090h+var_1060], 1
0x14006d84d  mov     r8d, r9d
0x14006d850  mov     dword ptr [rsp+1090h+var_1068], eax
0x14006d854  call    wil_details_NtUpdateWnfStateData
0x14006d859  mov     esi, eax
0x14006d85b  cmp     esi, 0C0000001h
0x14006d861  jnz     short loc_14006D874
0x14006d863  inc     r15d
0x14006d866  cmp     r15d, 64h ; 'd'
0x14006d86a  jge     short loc_14006D874
0x14006d86c  test    edi, edi
0x14006d86e  jz      loc_14006D6BA
0x14006d874  test    ebx, ebx
0x14006d876  cmovz   ebx, esi
0x14006d879  mov     eax, ebx
0x14006d87b  mov     rcx, [rbp+0F90h+var_40]
0x14006d882  xor     rcx, rsp; StackCookie
0x14006d885  call    __security_check_cookie
0x14006d88a  add     rsp, 1068h
0x14006d891  pop     r15
0x14006d893  pop     r14
0x14006d895  pop     rdi
0x14006d896  pop     rsi
0x14006d897  pop     rbx
0x14006d898  pop     rbp
0x14006d899  retn
0x14006d89a  mov     eax, [r8+8]
0x14006d89e  add     [rcx+8], eax
0x14006d8a1  mov     r9d, [rsp+1090h+var_1050]
0x14006d8a6  jmp     short loc_14006D82C
```
