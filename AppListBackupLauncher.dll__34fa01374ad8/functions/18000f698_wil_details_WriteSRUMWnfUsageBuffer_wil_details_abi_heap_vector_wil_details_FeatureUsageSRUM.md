# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000f698`
- end: `0x18000f8d0`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800030c0`

## callees

- `0x180002300`
- `0x180002de0`
- `0x18000f698`
- `0x180010160`
- `0x180010290`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f738`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000f738`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f721`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000f721`

## string_xrefs

- `0x18000f71a`: `ntdll.dll`

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
0x18000f698  push    rbp
0x18000f69a  push    rbx
0x18000f69b  push    rsi
0x18000f69c  push    rdi
0x18000f69d  push    r14
0x18000f69f  push    r15
0x18000f6a1  lea     rbp, [rsp-0F68h]
0x18000f6a9  mov     eax, 1068h
0x18000f6ae  call    _alloca_probe
0x18000f6b3  sub     rsp, rax
0x18000f6b6  mov     rax, cs:__security_cookie
0x18000f6bd  xor     rax, rsp
0x18000f6c0  mov     [rbp+0F90h+var_40], rax
0x18000f6c7  mov     rax, [rcx+8]
0x18000f6cb  xor     ebx, ebx
0x18000f6cd  sub     rax, [rcx]
0x18000f6d0  xor     esi, esi
0x18000f6d2  mov     r14, rcx
0x18000f6d5  cmp     rax, 0Ch
0x18000f6d9  jb      loc_18000F89C
0x18000f6df  xor     r15d, r15d
0x18000f6e2  xor     edx, edx; Val
0x18000f6e4  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000f6e9  mov     r8d, 1000h; Size
0x18000f6ef  call    memset_0
0x18000f6f4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000f6fc  mov     [rsp+1090h+var_1050], 1000h
0x18000f704  mov     [rsp+1090h+var_104C], 0
0x18000f70c  jnz     short loc_18000F756
0x18000f70e  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f715  test    rax, rax
0x18000f718  jnz     short loc_18000F72E
0x18000f71a  lea     rcx, ModuleName; "ntdll.dll"
0x18000f721  call    cs:__imp_GetModuleHandleW
0x18000f727  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000f72e  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000f735  mov     rcx, rax; hModule
0x18000f738  call    cs:__imp_GetProcAddress
0x18000f73e  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000f745  test    rax, rax
0x18000f748  jnz     short loc_18000F756
0x18000f74a  mov     edi, 0C0000139h
0x18000f74f  mov     ebx, edi
0x18000f751  jmp     loc_18000F883
0x18000f756  lea     rax, [rsp+1090h+var_1050]
0x18000f75b  xor     r8d, r8d
0x18000f75e  mov     [rsp+1090h+var_1068], rax
0x18000f763  lea     r9, [rsp+1090h+var_104C]
0x18000f768  lea     rax, [rsp+1090h+var_1040]
0x18000f76d  xor     edx, edx
0x18000f76f  mov     [rsp+1090h+var_1070], rax
0x18000f774  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000f77b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000f782  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f787  mov     ebx, eax
0x18000f789  mov     edi, eax
0x18000f78b  test    eax, eax
0x18000f78d  jnz     loc_18000F883
0x18000f793  mov     r9d, [rsp+1090h+var_1050]
0x18000f798  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000f7a2  mov     rax, r11
0x18000f7a5  mul     r9
0x18000f7a8  shr     rdx, 3
0x18000f7ac  lea     rcx, [rdx+rdx*2]
0x18000f7b0  shl     rcx, 2
0x18000f7b4  cmp     r9, rcx
0x18000f7b7  jz      short loc_18000F7C1
0x18000f7b9  xor     r9d, r9d
0x18000f7bc  mov     [rsp+1090h+var_1050], r9d
0x18000f7c1  mov     r8, [r14]
0x18000f7c4  mov     rax, r11
0x18000f7c7  mov     ecx, r9d
0x18000f7ca  mul     rcx
0x18000f7cd  mov     rcx, [r14+8]
0x18000f7d1  mov     rax, r11
0x18000f7d4  mov     r10, rdx
0x18000f7d7  sub     rcx, r8
0x18000f7da  mul     rcx
0x18000f7dd  shr     r10, 3
0x18000f7e1  shr     rdx, 3
0x18000f7e5  lea     rax, [rdx+rdx*2]
0x18000f7e9  lea     rsi, [r8+rax*4]
0x18000f7ed  jmp     short loc_18000F858
0x18000f7ef  mov     eax, r10d
0x18000f7f2  lea     rcx, [rax+rax*2]
0x18000f7f6  lea     rdx, [rdx+rcx*4]
0x18000f7fa  lea     rax, [rsp+1090h+var_1040]
0x18000f7ff  cmp     rax, rdx
0x18000f802  jz      short loc_18000F829
0x18000f804  mov     r11d, [r8]
0x18000f807  lea     rcx, [rsp+1090h+var_1040]
0x18000f80c  cmp     [rcx], r11d
0x18000f80f  jnz     short loc_18000F820
0x18000f811  movzx   eax, word ptr [r8+4]
0x18000f816  cmp     [rcx+4], ax
0x18000f81a  jz      loc_18000F8C2
0x18000f820  add     rcx, 0Ch
0x18000f824  cmp     rcx, rdx
0x18000f827  jnz     short loc_18000F80C
0x18000f829  mov     eax, r9d
0x18000f82c  add     rax, 0Ch
0x18000f830  cmp     rax, 1000h
0x18000f836  ja      short loc_18000F854
0x18000f838  movsd   xmm0, qword ptr [r8]
0x18000f83d  add     r9d, 0Ch
0x18000f841  movsd   qword ptr [rdx], xmm0
0x18000f845  inc     r10d
0x18000f848  mov     eax, [r8+8]
0x18000f84c  mov     [rdx+8], eax
0x18000f84f  mov     [rsp+1090h+var_1050], r9d
0x18000f854  add     r8, 0Ch
0x18000f858  lea     rdx, [rsp+1090h+var_1040]
0x18000f85d  cmp     r8, rsi
0x18000f860  jnz     short loc_18000F7EF
0x18000f862  mov     eax, [rsp+1090h+var_104C]
0x18000f866  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000f86d  mov     [rsp+1090h+var_1060], 1
0x18000f875  mov     r8d, r9d
0x18000f878  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000f87c  call    wil_details_NtUpdateWnfStateData
0x18000f881  mov     esi, eax
0x18000f883  cmp     esi, 0C0000001h
0x18000f889  jnz     short loc_18000F89C
0x18000f88b  inc     r15d
0x18000f88e  cmp     r15d, 64h ; 'd'
0x18000f892  jge     short loc_18000F89C
0x18000f894  test    edi, edi
0x18000f896  jz      loc_18000F6E2
0x18000f89c  test    ebx, ebx
0x18000f89e  cmovz   ebx, esi
0x18000f8a1  mov     eax, ebx
0x18000f8a3  mov     rcx, [rbp+0F90h+var_40]
0x18000f8aa  xor     rcx, rsp; StackCookie
0x18000f8ad  call    __security_check_cookie
0x18000f8b2  add     rsp, 1068h
0x18000f8b9  pop     r15
0x18000f8bb  pop     r14
0x18000f8bd  pop     rdi
0x18000f8be  pop     rsi
0x18000f8bf  pop     rbx
0x18000f8c0  pop     rbp
0x18000f8c1  retn
0x18000f8c2  mov     eax, [r8+8]
0x18000f8c6  add     [rcx+8], eax
0x18000f8c9  mov     r9d, [rsp+1090h+var_1050]
0x18000f8ce  jmp     short loc_18000F854
```
