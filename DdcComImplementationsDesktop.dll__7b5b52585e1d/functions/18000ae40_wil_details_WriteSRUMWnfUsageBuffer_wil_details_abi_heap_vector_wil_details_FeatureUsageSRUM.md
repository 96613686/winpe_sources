# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x18000ae40`
- end: `0x18000b078`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180004c70`

## callees

- `0x1800016b0`
- `0x180002134`
- `0x18000ae40`
- `0x18000b110`
- `0x18000bba0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aee0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000aee0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aec9`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000aec9`

## string_xrefs

- `0x18000aec2`: `ntdll.dll`

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
0x18000ae40  push    rbp
0x18000ae42  push    rbx
0x18000ae43  push    rsi
0x18000ae44  push    rdi
0x18000ae45  push    r14
0x18000ae47  push    r15
0x18000ae49  lea     rbp, [rsp-0F68h]
0x18000ae51  mov     eax, 1068h
0x18000ae56  call    _alloca_probe
0x18000ae5b  sub     rsp, rax
0x18000ae5e  mov     rax, cs:__security_cookie
0x18000ae65  xor     rax, rsp
0x18000ae68  mov     [rbp+0F90h+var_40], rax
0x18000ae6f  mov     rax, [rcx+8]
0x18000ae73  xor     ebx, ebx
0x18000ae75  sub     rax, [rcx]
0x18000ae78  xor     esi, esi
0x18000ae7a  mov     r14, rcx
0x18000ae7d  cmp     rax, 0Ch
0x18000ae81  jb      loc_18000B044
0x18000ae87  xor     r15d, r15d
0x18000ae8a  xor     edx, edx; Val
0x18000ae8c  lea     rcx, [rsp+1090h+var_1040]; void *
0x18000ae91  mov     r8d, 1000h; Size
0x18000ae97  call    memset_0
0x18000ae9c  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000aea4  mov     [rsp+1090h+var_1050], 1000h
0x18000aeac  mov     [rsp+1090h+var_104C], 0
0x18000aeb4  jnz     short loc_18000AEFE
0x18000aeb6  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aebd  test    rax, rax
0x18000aec0  jnz     short loc_18000AED6
0x18000aec2  lea     rcx, ModuleName; "ntdll.dll"
0x18000aec9  call    cs:__imp_GetModuleHandleW
0x18000aecf  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000aed6  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000aedd  mov     rcx, rax; hModule
0x18000aee0  call    cs:__imp_GetProcAddress
0x18000aee6  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000aeed  test    rax, rax
0x18000aef0  jnz     short loc_18000AEFE
0x18000aef2  mov     edi, 0C0000139h
0x18000aef7  mov     ebx, edi
0x18000aef9  jmp     loc_18000B02B
0x18000aefe  lea     rax, [rsp+1090h+var_1050]
0x18000af03  xor     r8d, r8d
0x18000af06  mov     [rsp+1090h+var_1068], rax
0x18000af0b  lea     r9, [rsp+1090h+var_104C]
0x18000af10  lea     rax, [rsp+1090h+var_1040]
0x18000af15  xor     edx, edx
0x18000af17  mov     [rsp+1090h+var_1070], rax
0x18000af1c  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000af23  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000af2a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af2f  mov     ebx, eax
0x18000af31  mov     edi, eax
0x18000af33  test    eax, eax
0x18000af35  jnz     loc_18000B02B
0x18000af3b  mov     r9d, [rsp+1090h+var_1050]
0x18000af40  mov     r11, 0AAAAAAAAAAAAAAABh
0x18000af4a  mov     rax, r11
0x18000af4d  mul     r9
0x18000af50  shr     rdx, 3
0x18000af54  lea     rcx, [rdx+rdx*2]
0x18000af58  shl     rcx, 2
0x18000af5c  cmp     r9, rcx
0x18000af5f  jz      short loc_18000AF69
0x18000af61  xor     r9d, r9d
0x18000af64  mov     [rsp+1090h+var_1050], r9d
0x18000af69  mov     r8, [r14]
0x18000af6c  mov     rax, r11
0x18000af6f  mov     ecx, r9d
0x18000af72  mul     rcx
0x18000af75  mov     rcx, [r14+8]
0x18000af79  mov     rax, r11
0x18000af7c  mov     r10, rdx
0x18000af7f  sub     rcx, r8
0x18000af82  mul     rcx
0x18000af85  shr     r10, 3
0x18000af89  shr     rdx, 3
0x18000af8d  lea     rax, [rdx+rdx*2]
0x18000af91  lea     rsi, [r8+rax*4]
0x18000af95  jmp     short loc_18000B000
0x18000af97  mov     eax, r10d
0x18000af9a  lea     rcx, [rax+rax*2]
0x18000af9e  lea     rdx, [rdx+rcx*4]
0x18000afa2  lea     rax, [rsp+1090h+var_1040]
0x18000afa7  cmp     rax, rdx
0x18000afaa  jz      short loc_18000AFD1
0x18000afac  mov     r11d, [r8]
0x18000afaf  lea     rcx, [rsp+1090h+var_1040]
0x18000afb4  cmp     [rcx], r11d
0x18000afb7  jnz     short loc_18000AFC8
0x18000afb9  movzx   eax, word ptr [r8+4]
0x18000afbe  cmp     [rcx+4], ax
0x18000afc2  jz      loc_18000B06A
0x18000afc8  add     rcx, 0Ch
0x18000afcc  cmp     rcx, rdx
0x18000afcf  jnz     short loc_18000AFB4
0x18000afd1  mov     eax, r9d
0x18000afd4  add     rax, 0Ch
0x18000afd8  cmp     rax, 1000h
0x18000afde  ja      short loc_18000AFFC
0x18000afe0  movsd   xmm0, qword ptr [r8]
0x18000afe5  add     r9d, 0Ch
0x18000afe9  movsd   qword ptr [rdx], xmm0
0x18000afed  inc     r10d
0x18000aff0  mov     eax, [r8+8]
0x18000aff4  mov     [rdx+8], eax
0x18000aff7  mov     [rsp+1090h+var_1050], r9d
0x18000affc  add     r8, 0Ch
0x18000b000  lea     rdx, [rsp+1090h+var_1040]
0x18000b005  cmp     r8, rsi
0x18000b008  jnz     short loc_18000AF97
0x18000b00a  mov     eax, [rsp+1090h+var_104C]
0x18000b00e  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000b015  mov     [rsp+1090h+var_1060], 1
0x18000b01d  mov     r8d, r9d
0x18000b020  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000b024  call    wil_details_NtUpdateWnfStateData
0x18000b029  mov     esi, eax
0x18000b02b  cmp     esi, 0C0000001h
0x18000b031  jnz     short loc_18000B044
0x18000b033  inc     r15d
0x18000b036  cmp     r15d, 64h ; 'd'
0x18000b03a  jge     short loc_18000B044
0x18000b03c  test    edi, edi
0x18000b03e  jz      loc_18000AE8A
0x18000b044  test    ebx, ebx
0x18000b046  cmovz   ebx, esi
0x18000b049  mov     eax, ebx
0x18000b04b  mov     rcx, [rbp+0F90h+var_40]
0x18000b052  xor     rcx, rsp; StackCookie
0x18000b055  call    __security_check_cookie
0x18000b05a  add     rsp, 1068h
0x18000b061  pop     r15
0x18000b063  pop     r14
0x18000b065  pop     rdi
0x18000b066  pop     rsi
0x18000b067  pop     rbx
0x18000b068  pop     rbp
0x18000b069  retn
0x18000b06a  mov     eax, [r8+8]
0x18000b06e  add     [rcx+8], eax
0x18000b071  mov     r9d, [rsp+1090h+var_1050]
0x18000b076  jmp     short loc_18000AFFC
```
