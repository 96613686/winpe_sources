# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000a958`
- end: `0x14000ab90`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x140002b90`

## callees

- `0x14000a958`
- `0x14000b1a0`
- `0x140015ac2`
- `0x140015b00`
- `0x140015b90`
- `0x140017010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000a9f8`
- `KERNEL32!GetProcAddress` at `0x14000a9f8`
- `KERNEL32!GetModuleHandleW` at `0x14000a9e1`
- `KERNEL32!GetModuleHandleW` at `0x14000a9e1`

## string_xrefs

- `0x14000a9da`: `ntdll.dll`

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
0x14000a958  push    rbp
0x14000a95a  push    rbx
0x14000a95b  push    rsi
0x14000a95c  push    rdi
0x14000a95d  push    r14
0x14000a95f  push    r15
0x14000a961  lea     rbp, [rsp-0F68h]
0x14000a969  mov     eax, 1068h
0x14000a96e  call    _alloca_probe
0x14000a973  sub     rsp, rax
0x14000a976  mov     rax, cs:__security_cookie
0x14000a97d  xor     rax, rsp
0x14000a980  mov     [rbp+0F90h+var_40], rax
0x14000a987  mov     rax, [rcx+8]
0x14000a98b  xor     ebx, ebx
0x14000a98d  sub     rax, [rcx]
0x14000a990  xor     esi, esi
0x14000a992  mov     r14, rcx
0x14000a995  cmp     rax, 0Ch
0x14000a999  jb      loc_14000AB5C
0x14000a99f  xor     r15d, r15d
0x14000a9a2  xor     edx, edx; Val
0x14000a9a4  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000a9a9  mov     r8d, 1000h; Size
0x14000a9af  call    memset_0
0x14000a9b4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000a9bc  mov     [rsp+1090h+var_1050], 1000h
0x14000a9c4  mov     [rsp+1090h+var_104C], 0
0x14000a9cc  jnz     short loc_14000AA16
0x14000a9ce  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a9d5  test    rax, rax
0x14000a9d8  jnz     short loc_14000A9EE
0x14000a9da  lea     rcx, ModuleName; "ntdll.dll"
0x14000a9e1  call    cs:__imp_GetModuleHandleW
0x14000a9e7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000a9ee  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000a9f5  mov     rcx, rax; hModule
0x14000a9f8  call    cs:__imp_GetProcAddress
0x14000a9fe  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000aa05  test    rax, rax
0x14000aa08  jnz     short loc_14000AA16
0x14000aa0a  mov     edi, 0C0000139h
0x14000aa0f  mov     ebx, edi
0x14000aa11  jmp     loc_14000AB43
0x14000aa16  lea     rax, [rsp+1090h+var_1050]
0x14000aa1b  xor     r8d, r8d
0x14000aa1e  mov     [rsp+1090h+var_1068], rax
0x14000aa23  lea     r9, [rsp+1090h+var_104C]
0x14000aa28  lea     rax, [rsp+1090h+var_1040]
0x14000aa2d  xor     edx, edx
0x14000aa2f  mov     [rsp+1090h+var_1070], rax
0x14000aa34  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000aa3b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000aa42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000aa47  mov     ebx, eax
0x14000aa49  mov     edi, eax
0x14000aa4b  test    eax, eax
0x14000aa4d  jnz     loc_14000AB43
0x14000aa53  mov     r9d, [rsp+1090h+var_1050]
0x14000aa58  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000aa62  mov     rax, r11
0x14000aa65  mul     r9
0x14000aa68  shr     rdx, 3
0x14000aa6c  lea     rcx, [rdx+rdx*2]
0x14000aa70  shl     rcx, 2
0x14000aa74  cmp     r9, rcx
0x14000aa77  jz      short loc_14000AA81
0x14000aa79  xor     r9d, r9d
0x14000aa7c  mov     [rsp+1090h+var_1050], r9d
0x14000aa81  mov     r8, [r14]
0x14000aa84  mov     rax, r11
0x14000aa87  mov     ecx, r9d
0x14000aa8a  mul     rcx
0x14000aa8d  mov     rcx, [r14+8]
0x14000aa91  mov     rax, r11
0x14000aa94  mov     r10, rdx
0x14000aa97  sub     rcx, r8
0x14000aa9a  mul     rcx
0x14000aa9d  shr     r10, 3
0x14000aaa1  shr     rdx, 3
0x14000aaa5  lea     rax, [rdx+rdx*2]
0x14000aaa9  lea     rsi, [r8+rax*4]
0x14000aaad  jmp     short loc_14000AB18
0x14000aaaf  mov     eax, r10d
0x14000aab2  lea     rcx, [rax+rax*2]
0x14000aab6  lea     rdx, [rdx+rcx*4]
0x14000aaba  lea     rax, [rsp+1090h+var_1040]
0x14000aabf  cmp     rax, rdx
0x14000aac2  jz      short loc_14000AAE9
0x14000aac4  mov     r11d, [r8]
0x14000aac7  lea     rcx, [rsp+1090h+var_1040]
0x14000aacc  cmp     [rcx], r11d
0x14000aacf  jnz     short loc_14000AAE0
0x14000aad1  movzx   eax, word ptr [r8+4]
0x14000aad6  cmp     [rcx+4], ax
0x14000aada  jz      loc_14000AB82
0x14000aae0  add     rcx, 0Ch
0x14000aae4  cmp     rcx, rdx
0x14000aae7  jnz     short loc_14000AACC
0x14000aae9  mov     eax, r9d
0x14000aaec  add     rax, 0Ch
0x14000aaf0  cmp     rax, 1000h
0x14000aaf6  ja      short loc_14000AB14
0x14000aaf8  movsd   xmm0, qword ptr [r8]
0x14000aafd  add     r9d, 0Ch
0x14000ab01  movsd   qword ptr [rdx], xmm0
0x14000ab05  inc     r10d
0x14000ab08  mov     eax, [r8+8]
0x14000ab0c  mov     [rdx+8], eax
0x14000ab0f  mov     [rsp+1090h+var_1050], r9d
0x14000ab14  add     r8, 0Ch
0x14000ab18  lea     rdx, [rsp+1090h+var_1040]
0x14000ab1d  cmp     r8, rsi
0x14000ab20  jnz     short loc_14000AAAF
0x14000ab22  mov     eax, [rsp+1090h+var_104C]
0x14000ab26  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000ab2d  mov     [rsp+1090h+var_1060], 1
0x14000ab35  mov     r8d, r9d
0x14000ab38  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000ab3c  call    wil_details_NtUpdateWnfStateData
0x14000ab41  mov     esi, eax
0x14000ab43  cmp     esi, 0C0000001h
0x14000ab49  jnz     short loc_14000AB5C
0x14000ab4b  inc     r15d
0x14000ab4e  cmp     r15d, 64h ; 'd'
0x14000ab52  jge     short loc_14000AB5C
0x14000ab54  test    edi, edi
0x14000ab56  jz      loc_14000A9A2
0x14000ab5c  test    ebx, ebx
0x14000ab5e  cmovz   ebx, esi
0x14000ab61  mov     eax, ebx
0x14000ab63  mov     rcx, [rbp+0F90h+var_40]
0x14000ab6a  xor     rcx, rsp; StackCookie
0x14000ab6d  call    __security_check_cookie
0x14000ab72  add     rsp, 1068h
0x14000ab79  pop     r15
0x14000ab7b  pop     r14
0x14000ab7d  pop     rdi
0x14000ab7e  pop     rsi
0x14000ab7f  pop     rbx
0x14000ab80  pop     rbp
0x14000ab81  retn
0x14000ab82  mov     eax, [r8+8]
0x14000ab86  add     [rcx+8], eax
0x14000ab89  mov     r9d, [rsp+1090h+var_1050]
0x14000ab8e  jmp     short loc_14000AB14
```
