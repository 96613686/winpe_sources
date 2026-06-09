# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x1800260ac`
- end: `0x1800262e4`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180023750`

## callees

- `0x1800021c0`
- `0x180002c04`
- `0x1800260ac`
- `0x1800262ec`
- `0x180029890`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026135`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180026135`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002614c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002614c`

## string_xrefs

- `0x18002612e`: `ntdll.dll`

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
0x1800260ac  push    rbp
0x1800260ae  push    rbx
0x1800260af  push    rsi
0x1800260b0  push    rdi
0x1800260b1  push    r14
0x1800260b3  push    r15
0x1800260b5  lea     rbp, [rsp-0F68h]
0x1800260bd  mov     eax, 1068h
0x1800260c2  call    _alloca_probe
0x1800260c7  sub     rsp, rax
0x1800260ca  mov     rax, cs:__security_cookie
0x1800260d1  xor     rax, rsp
0x1800260d4  mov     [rbp+0F90h+var_40], rax
0x1800260db  mov     rax, [rcx+8]
0x1800260df  xor     ebx, ebx
0x1800260e1  sub     rax, [rcx]
0x1800260e4  xor     esi, esi
0x1800260e6  mov     r14, rcx
0x1800260e9  cmp     rax, 0Ch
0x1800260ed  jb      loc_1800262B0
0x1800260f3  xor     r15d, r15d
0x1800260f6  xor     edx, edx; Val
0x1800260f8  lea     rcx, [rsp+1090h+var_1040]; void *
0x1800260fd  mov     r8d, 1000h; Size
0x180026103  call    memset_0
0x180026108  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180026110  mov     [rsp+1090h+var_1050], 1000h
0x180026118  mov     [rsp+1090h+var_104C], 0
0x180026120  jnz     short loc_18002616A
0x180026122  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180026129  test    rax, rax
0x18002612c  jnz     short loc_180026142
0x18002612e  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180026135  call    cs:__imp_GetModuleHandleW
0x18002613b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180026142  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180026149  mov     rcx, rax; hModule
0x18002614c  call    cs:__imp_GetProcAddress
0x180026152  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180026159  test    rax, rax
0x18002615c  jnz     short loc_18002616A
0x18002615e  mov     edi, 0C0000139h
0x180026163  mov     ebx, edi
0x180026165  jmp     loc_180026297
0x18002616a  lea     rax, [rsp+1090h+var_1050]
0x18002616f  xor     r8d, r8d
0x180026172  mov     [rsp+1090h+var_1068], rax
0x180026177  lea     r9, [rsp+1090h+var_104C]
0x18002617c  lea     rax, [rsp+1090h+var_1040]
0x180026181  xor     edx, edx
0x180026183  mov     [rsp+1090h+var_1070], rax
0x180026188  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18002618f  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180026196  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002619b  mov     ebx, eax
0x18002619d  mov     edi, eax
0x18002619f  test    eax, eax
0x1800261a1  jnz     loc_180026297
0x1800261a7  mov     r9d, [rsp+1090h+var_1050]
0x1800261ac  mov     r11, 0AAAAAAAAAAAAAAABh
0x1800261b6  mov     rax, r11
0x1800261b9  mul     r9
0x1800261bc  shr     rdx, 3
0x1800261c0  lea     rcx, [rdx+rdx*2]
0x1800261c4  shl     rcx, 2
0x1800261c8  cmp     r9, rcx
0x1800261cb  jz      short loc_1800261D5
0x1800261cd  xor     r9d, r9d
0x1800261d0  mov     [rsp+1090h+var_1050], r9d
0x1800261d5  mov     r8, [r14]
0x1800261d8  mov     rax, r11
0x1800261db  mov     ecx, r9d
0x1800261de  mul     rcx
0x1800261e1  mov     rcx, [r14+8]
0x1800261e5  mov     rax, r11
0x1800261e8  mov     r10, rdx
0x1800261eb  sub     rcx, r8
0x1800261ee  mul     rcx
0x1800261f1  shr     r10, 3
0x1800261f5  shr     rdx, 3
0x1800261f9  lea     rax, [rdx+rdx*2]
0x1800261fd  lea     rsi, [r8+rax*4]
0x180026201  jmp     short loc_18002626C
0x180026203  mov     eax, r10d
0x180026206  lea     rcx, [rax+rax*2]
0x18002620a  lea     rdx, [rdx+rcx*4]
0x18002620e  lea     rax, [rsp+1090h+var_1040]
0x180026213  cmp     rax, rdx
0x180026216  jz      short loc_18002623D
0x180026218  mov     r11d, [r8]
0x18002621b  lea     rcx, [rsp+1090h+var_1040]
0x180026220  cmp     [rcx], r11d
0x180026223  jnz     short loc_180026234
0x180026225  movzx   eax, word ptr [r8+4]
0x18002622a  cmp     [rcx+4], ax
0x18002622e  jz      loc_1800262D6
0x180026234  add     rcx, 0Ch
0x180026238  cmp     rcx, rdx
0x18002623b  jnz     short loc_180026220
0x18002623d  mov     eax, r9d
0x180026240  add     rax, 0Ch
0x180026244  cmp     rax, 1000h
0x18002624a  ja      short loc_180026268
0x18002624c  movsd   xmm0, qword ptr [r8]
0x180026251  add     r9d, 0Ch
0x180026255  movsd   qword ptr [rdx], xmm0
0x180026259  inc     r10d
0x18002625c  mov     eax, [r8+8]
0x180026260  mov     [rdx+8], eax
0x180026263  mov     [rsp+1090h+var_1050], r9d
0x180026268  add     r8, 0Ch
0x18002626c  lea     rdx, [rsp+1090h+var_1040]
0x180026271  cmp     r8, rsi
0x180026274  jnz     short loc_180026203
0x180026276  mov     eax, [rsp+1090h+var_104C]
0x18002627a  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180026281  mov     [rsp+1090h+var_1060], 1
0x180026289  mov     r8d, r9d
0x18002628c  mov     dword ptr [rsp+1090h+var_1068], eax
0x180026290  call    wil_details_NtUpdateWnfStateData
0x180026295  mov     esi, eax
0x180026297  cmp     esi, 0C0000001h
0x18002629d  jnz     short loc_1800262B0
0x18002629f  inc     r15d
0x1800262a2  cmp     r15d, 64h ; 'd'
0x1800262a6  jge     short loc_1800262B0
0x1800262a8  test    edi, edi
0x1800262aa  jz      loc_1800260F6
0x1800262b0  test    ebx, ebx
0x1800262b2  cmovz   ebx, esi
0x1800262b5  mov     eax, ebx
0x1800262b7  mov     rcx, [rbp+0F90h+var_40]
0x1800262be  xor     rcx, rsp; StackCookie
0x1800262c1  call    __security_check_cookie
0x1800262c6  add     rsp, 1068h
0x1800262cd  pop     r15
0x1800262cf  pop     r14
0x1800262d1  pop     rdi
0x1800262d2  pop     rsi
0x1800262d3  pop     rbx
0x1800262d4  pop     rbp
0x1800262d5  retn
0x1800262d6  mov     eax, [r8+8]
0x1800262da  add     [rcx+8], eax
0x1800262dd  mov     r9d, [rsp+1090h+var_1050]
0x1800262e2  jmp     short loc_180026268
```
