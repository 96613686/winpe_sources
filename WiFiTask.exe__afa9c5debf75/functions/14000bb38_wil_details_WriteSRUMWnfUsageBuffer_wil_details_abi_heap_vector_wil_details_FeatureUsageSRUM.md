# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x14000bb38`
- end: `0x14000bd70`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(__int64 *)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1400022a0`

## callees

- `0x1400016a0`
- `0x140002168`
- `0x14000bb38`
- `0x14000c700`
- `0x140010d80`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bbc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000bbc1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bbd8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000bbd8`

## string_xrefs

- `0x14000bbba`: `ntdll.dll`

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
0x14000bb38  push    rbp
0x14000bb3a  push    rbx
0x14000bb3b  push    rsi
0x14000bb3c  push    rdi
0x14000bb3d  push    r14
0x14000bb3f  push    r15
0x14000bb41  lea     rbp, [rsp-0F68h]
0x14000bb49  mov     eax, 1068h
0x14000bb4e  call    _alloca_probe
0x14000bb53  sub     rsp, rax
0x14000bb56  mov     rax, cs:__security_cookie
0x14000bb5d  xor     rax, rsp
0x14000bb60  mov     [rbp+0F90h+var_40], rax
0x14000bb67  mov     rax, [rcx+8]
0x14000bb6b  xor     ebx, ebx
0x14000bb6d  sub     rax, [rcx]
0x14000bb70  xor     esi, esi
0x14000bb72  mov     r14, rcx
0x14000bb75  cmp     rax, 0Ch
0x14000bb79  jb      loc_14000BD3C
0x14000bb7f  xor     r15d, r15d
0x14000bb82  xor     edx, edx; Val
0x14000bb84  lea     rcx, [rsp+1090h+var_1040]; void *
0x14000bb89  mov     r8d, 1000h; Size
0x14000bb8f  call    memset_0
0x14000bb94  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x14000bb9c  mov     [rsp+1090h+var_1050], 1000h
0x14000bba4  mov     [rsp+1090h+var_104C], 0
0x14000bbac  jnz     short loc_14000BBF6
0x14000bbae  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bbb5  test    rax, rax
0x14000bbb8  jnz     short loc_14000BBCE
0x14000bbba  lea     rcx, ModuleName; "ntdll.dll"
0x14000bbc1  call    cs:__imp_GetModuleHandleW
0x14000bbc7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bbce  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000bbd5  mov     rcx, rax; hModule
0x14000bbd8  call    cs:__imp_GetProcAddress
0x14000bbde  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000bbe5  test    rax, rax
0x14000bbe8  jnz     short loc_14000BBF6
0x14000bbea  mov     edi, 0C0000139h
0x14000bbef  mov     ebx, edi
0x14000bbf1  jmp     loc_14000BD23
0x14000bbf6  lea     rax, [rsp+1090h+var_1050]
0x14000bbfb  xor     r8d, r8d
0x14000bbfe  mov     [rsp+1090h+var_1068], rax
0x14000bc03  lea     r9, [rsp+1090h+var_104C]
0x14000bc08  lea     rax, [rsp+1090h+var_1040]
0x14000bc0d  xor     edx, edx
0x14000bc0f  mov     [rsp+1090h+var_1070], rax
0x14000bc14  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000bc1b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000bc22  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc27  mov     ebx, eax
0x14000bc29  mov     edi, eax
0x14000bc2b  test    eax, eax
0x14000bc2d  jnz     loc_14000BD23
0x14000bc33  mov     r9d, [rsp+1090h+var_1050]
0x14000bc38  mov     r11, 0AAAAAAAAAAAAAAABh
0x14000bc42  mov     rax, r11
0x14000bc45  mul     r9
0x14000bc48  shr     rdx, 3
0x14000bc4c  lea     rcx, [rdx+rdx*2]
0x14000bc50  shl     rcx, 2
0x14000bc54  cmp     r9, rcx
0x14000bc57  jz      short loc_14000BC61
0x14000bc59  xor     r9d, r9d
0x14000bc5c  mov     [rsp+1090h+var_1050], r9d
0x14000bc61  mov     r8, [r14]
0x14000bc64  mov     rax, r11
0x14000bc67  mov     ecx, r9d
0x14000bc6a  mul     rcx
0x14000bc6d  mov     rcx, [r14+8]
0x14000bc71  mov     rax, r11
0x14000bc74  mov     r10, rdx
0x14000bc77  sub     rcx, r8
0x14000bc7a  mul     rcx
0x14000bc7d  shr     r10, 3
0x14000bc81  shr     rdx, 3
0x14000bc85  lea     rax, [rdx+rdx*2]
0x14000bc89  lea     rsi, [r8+rax*4]
0x14000bc8d  jmp     short loc_14000BCF8
0x14000bc8f  mov     eax, r10d
0x14000bc92  lea     rcx, [rax+rax*2]
0x14000bc96  lea     rdx, [rdx+rcx*4]
0x14000bc9a  lea     rax, [rsp+1090h+var_1040]
0x14000bc9f  cmp     rax, rdx
0x14000bca2  jz      short loc_14000BCC9
0x14000bca4  mov     r11d, [r8]
0x14000bca7  lea     rcx, [rsp+1090h+var_1040]
0x14000bcac  cmp     [rcx], r11d
0x14000bcaf  jnz     short loc_14000BCC0
0x14000bcb1  movzx   eax, word ptr [r8+4]
0x14000bcb6  cmp     [rcx+4], ax
0x14000bcba  jz      loc_14000BD62
0x14000bcc0  add     rcx, 0Ch
0x14000bcc4  cmp     rcx, rdx
0x14000bcc7  jnz     short loc_14000BCAC
0x14000bcc9  mov     eax, r9d
0x14000bccc  add     rax, 0Ch
0x14000bcd0  cmp     rax, 1000h
0x14000bcd6  ja      short loc_14000BCF4
0x14000bcd8  movsd   xmm0, qword ptr [r8]
0x14000bcdd  add     r9d, 0Ch
0x14000bce1  movsd   qword ptr [rdx], xmm0
0x14000bce5  inc     r10d
0x14000bce8  mov     eax, [r8+8]
0x14000bcec  mov     [rdx+8], eax
0x14000bcef  mov     [rsp+1090h+var_1050], r9d
0x14000bcf4  add     r8, 0Ch
0x14000bcf8  lea     rdx, [rsp+1090h+var_1040]
0x14000bcfd  cmp     r8, rsi
0x14000bd00  jnz     short loc_14000BC8F
0x14000bd02  mov     eax, [rsp+1090h+var_104C]
0x14000bd06  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x14000bd0d  mov     [rsp+1090h+var_1060], 1
0x14000bd15  mov     r8d, r9d
0x14000bd18  mov     dword ptr [rsp+1090h+var_1068], eax
0x14000bd1c  call    wil_details_NtUpdateWnfStateData
0x14000bd21  mov     esi, eax
0x14000bd23  cmp     esi, 0C0000001h
0x14000bd29  jnz     short loc_14000BD3C
0x14000bd2b  inc     r15d
0x14000bd2e  cmp     r15d, 64h ; 'd'
0x14000bd32  jge     short loc_14000BD3C
0x14000bd34  test    edi, edi
0x14000bd36  jz      loc_14000BB82
0x14000bd3c  test    ebx, ebx
0x14000bd3e  cmovz   ebx, esi
0x14000bd41  mov     eax, ebx
0x14000bd43  mov     rcx, [rbp+0F90h+var_40]
0x14000bd4a  xor     rcx, rsp; StackCookie
0x14000bd4d  call    __security_check_cookie
0x14000bd52  add     rsp, 1068h
0x14000bd59  pop     r15
0x14000bd5b  pop     r14
0x14000bd5d  pop     rdi
0x14000bd5e  pop     rsi
0x14000bd5f  pop     rbx
0x14000bd60  pop     rbp
0x14000bd61  retn
0x14000bd62  mov     eax, [r8+8]
0x14000bd66  add     [rcx+8], eax
0x14000bd69  mov     r9d, [rsp+1090h+var_1050]
0x14000bd6e  jmp     short loc_14000BCF4
```
