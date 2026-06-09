# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x140008e48`
- end: `0x140009080`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1400024e0`

## callees

- `0x1400016f0`
- `0x14000221c`
- `0x140008e48`
- `0x140009310`
- `0x14000b840`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008ed1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008ed1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008ee8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008ee8`

## string_xrefs

- `0x140008eca`: `ntdll.dll`

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
0x140008e48  push    rbp
0x140008e4a  push    rbx
0x140008e4b  push    rsi
0x140008e4c  push    rdi
0x140008e4d  push    r14
0x140008e4f  push    r15
0x140008e51  lea     rbp, [rsp-0F68h]
0x140008e59  mov     eax, 1068h
0x140008e5e  call    _alloca_probe
0x140008e63  sub     rsp, rax
0x140008e66  mov     rax, cs:__security_cookie
0x140008e6d  xor     rax, rsp
0x140008e70  mov     [rbp+0F90h+var_40], rax
0x140008e77  mov     rax, [rcx+8]
0x140008e7b  xor     ebx, ebx
0x140008e7d  sub     rax, [rcx]
0x140008e80  xor     esi, esi
0x140008e82  mov     r14, rcx
0x140008e85  cmp     rax, 0Ch
0x140008e89  jb      loc_14000904C
0x140008e8f  xor     r15d, r15d
0x140008e92  xor     edx, edx; Val
0x140008e94  lea     rcx, [rsp+1090h+var_1040]; void *
0x140008e99  mov     r8d, 1000h; Size
0x140008e9f  call    memset_0
0x140008ea4  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x140008eac  mov     [rsp+1090h+var_1050], 1000h
0x140008eb4  mov     [rsp+1090h+var_104C], 0
0x140008ebc  jnz     short loc_140008F06
0x140008ebe  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008ec5  test    rax, rax
0x140008ec8  jnz     short loc_140008EDE
0x140008eca  lea     rcx, ModuleName; "ntdll.dll"
0x140008ed1  call    cs:__imp_GetModuleHandleW
0x140008ed7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008ede  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140008ee5  mov     rcx, rax; hModule
0x140008ee8  call    cs:__imp_GetProcAddress
0x140008eee  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140008ef5  test    rax, rax
0x140008ef8  jnz     short loc_140008F06
0x140008efa  mov     edi, 0C0000139h
0x140008eff  mov     ebx, edi
0x140008f01  jmp     loc_140009033
0x140008f06  lea     rax, [rsp+1090h+var_1050]
0x140008f0b  xor     r8d, r8d
0x140008f0e  mov     [rsp+1090h+var_1068], rax
0x140008f13  lea     r9, [rsp+1090h+var_104C]
0x140008f18  lea     rax, [rsp+1090h+var_1040]
0x140008f1d  xor     edx, edx
0x140008f1f  mov     [rsp+1090h+var_1070], rax
0x140008f24  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x140008f2b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140008f32  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f37  mov     ebx, eax
0x140008f39  mov     edi, eax
0x140008f3b  test    eax, eax
0x140008f3d  jnz     loc_140009033
0x140008f43  mov     r9d, [rsp+1090h+var_1050]
0x140008f48  mov     r11, 0AAAAAAAAAAAAAAABh
0x140008f52  mov     rax, r11
0x140008f55  mul     r9
0x140008f58  shr     rdx, 3
0x140008f5c  lea     rcx, [rdx+rdx*2]
0x140008f60  shl     rcx, 2
0x140008f64  cmp     r9, rcx
0x140008f67  jz      short loc_140008F71
0x140008f69  xor     r9d, r9d
0x140008f6c  mov     [rsp+1090h+var_1050], r9d
0x140008f71  mov     r8, [r14]
0x140008f74  mov     rax, r11
0x140008f77  mov     ecx, r9d
0x140008f7a  mul     rcx
0x140008f7d  mov     rcx, [r14+8]
0x140008f81  mov     rax, r11
0x140008f84  mov     r10, rdx
0x140008f87  sub     rcx, r8
0x140008f8a  mul     rcx
0x140008f8d  shr     r10, 3
0x140008f91  shr     rdx, 3
0x140008f95  lea     rax, [rdx+rdx*2]
0x140008f99  lea     rsi, [r8+rax*4]
0x140008f9d  jmp     short loc_140009008
0x140008f9f  mov     eax, r10d
0x140008fa2  lea     rcx, [rax+rax*2]
0x140008fa6  lea     rdx, [rdx+rcx*4]
0x140008faa  lea     rax, [rsp+1090h+var_1040]
0x140008faf  cmp     rax, rdx
0x140008fb2  jz      short loc_140008FD9
0x140008fb4  mov     r11d, [r8]
0x140008fb7  lea     rcx, [rsp+1090h+var_1040]
0x140008fbc  cmp     [rcx], r11d
0x140008fbf  jnz     short loc_140008FD0
0x140008fc1  movzx   eax, word ptr [r8+4]
0x140008fc6  cmp     [rcx+4], ax
0x140008fca  jz      loc_140009072
0x140008fd0  add     rcx, 0Ch
0x140008fd4  cmp     rcx, rdx
0x140008fd7  jnz     short loc_140008FBC
0x140008fd9  mov     eax, r9d
0x140008fdc  add     rax, 0Ch
0x140008fe0  cmp     rax, 1000h
0x140008fe6  ja      short loc_140009004
0x140008fe8  movsd   xmm0, qword ptr [r8]
0x140008fed  add     r9d, 0Ch
0x140008ff1  movsd   qword ptr [rdx], xmm0
0x140008ff5  inc     r10d
0x140008ff8  mov     eax, [r8+8]
0x140008ffc  mov     [rdx+8], eax
0x140008fff  mov     [rsp+1090h+var_1050], r9d
0x140009004  add     r8, 0Ch
0x140009008  lea     rdx, [rsp+1090h+var_1040]
0x14000900d  cmp     r8, rsi
0x140009010  jnz     short loc_140008F9F
0x140009012  mov     eax, [rsp+1090h+var_104C]
0x140009016  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000901d  mov     [rsp+1090h+var_1060], 1
0x140009025  mov     r8d, r9d
0x140009028  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000902c  call    wil_details_NtUpdateWnfStateData
0x140009031  mov     esi, eax
0x140009033  cmp     esi, 0C0000001h
0x140009039  jnz     short loc_14000904C
0x14000903b  inc     r15d
0x14000903e  cmp     r15d, 64h ; 'd'
0x140009042  jge     short loc_14000904C
0x140009044  test    edi, edi
0x140009046  jz      loc_140008E92
0x14000904c  test    ebx, ebx
0x14000904e  cmovz   ebx, esi
0x140009051  mov     eax, ebx
0x140009053  mov     rcx, [rbp+0F90h+var_40]
0x14000905a  xor     rcx, rsp; StackCookie
0x14000905d  call    __security_check_cookie
0x140009062  add     rsp, 1068h
0x140009069  pop     r15
0x14000906b  pop     r14
0x14000906d  pop     rdi
0x14000906e  pop     rsi
0x14000906f  pop     rbx
0x140009070  pop     rbp
0x140009071  retn
0x140009072  mov     eax, [r8+8]
0x140009076  add     [rcx+8], eax
0x140009079  mov     r9d, [rsp+1090h+var_1050]
0x14000907e  jmp     short loc_140009004
```
