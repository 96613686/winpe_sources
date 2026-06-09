# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180008438`
- end: `0x180008670`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x1800024a0`

## callees

- `0x180008438`
- `0x180008bc0`
- `0x18001623a`
- `0x180016280`
- `0x180016310`
- `0x180017010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800084c1`
- `KERNEL32!GetModuleHandleW` at `0x1800084c1`
- `KERNEL32!GetProcAddress` at `0x1800084d8`
- `KERNEL32!GetProcAddress` at `0x1800084d8`

## string_xrefs

- `0x1800084ba`: `ntdll.dll`

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
0x180008438  push    rbp
0x18000843a  push    rbx
0x18000843b  push    rsi
0x18000843c  push    rdi
0x18000843d  push    r14
0x18000843f  push    r15
0x180008441  lea     rbp, [rsp-0F68h]
0x180008449  mov     eax, 1068h
0x18000844e  call    _alloca_probe
0x180008453  sub     rsp, rax
0x180008456  mov     rax, cs:__security_cookie
0x18000845d  xor     rax, rsp
0x180008460  mov     [rbp+0F90h+var_40], rax
0x180008467  mov     rax, [rcx+8]
0x18000846b  xor     ebx, ebx
0x18000846d  sub     rax, [rcx]
0x180008470  xor     esi, esi
0x180008472  mov     r14, rcx
0x180008475  cmp     rax, 0Ch
0x180008479  jb      loc_18000863C
0x18000847f  xor     r15d, r15d
0x180008482  xor     edx, edx; Val
0x180008484  lea     rcx, [rsp+1090h+var_1040]; void *
0x180008489  mov     r8d, 1000h; Size
0x18000848f  call    memset_0
0x180008494  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x18000849c  mov     [rsp+1090h+var_1050], 1000h
0x1800084a4  mov     [rsp+1090h+var_104C], 0
0x1800084ac  jnz     short loc_1800084F6
0x1800084ae  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800084b5  test    rax, rax
0x1800084b8  jnz     short loc_1800084CE
0x1800084ba  lea     rcx, ModuleName; "ntdll.dll"
0x1800084c1  call    cs:__imp_GetModuleHandleW
0x1800084c7  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800084ce  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800084d5  mov     rcx, rax; hModule
0x1800084d8  call    cs:__imp_GetProcAddress
0x1800084de  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800084e5  test    rax, rax
0x1800084e8  jnz     short loc_1800084F6
0x1800084ea  mov     edi, 0C0000139h
0x1800084ef  mov     ebx, edi
0x1800084f1  jmp     loc_180008623
0x1800084f6  lea     rax, [rsp+1090h+var_1050]
0x1800084fb  xor     r8d, r8d
0x1800084fe  mov     [rsp+1090h+var_1068], rax
0x180008503  lea     r9, [rsp+1090h+var_104C]
0x180008508  lea     rax, [rsp+1090h+var_1040]
0x18000850d  xor     edx, edx
0x18000850f  mov     [rsp+1090h+var_1070], rax
0x180008514  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000851b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008522  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008527  mov     ebx, eax
0x180008529  mov     edi, eax
0x18000852b  test    eax, eax
0x18000852d  jnz     loc_180008623
0x180008533  mov     r9d, [rsp+1090h+var_1050]
0x180008538  mov     r11, 0AAAAAAAAAAAAAAABh
0x180008542  mov     rax, r11
0x180008545  mul     r9
0x180008548  shr     rdx, 3
0x18000854c  lea     rcx, [rdx+rdx*2]
0x180008550  shl     rcx, 2
0x180008554  cmp     r9, rcx
0x180008557  jz      short loc_180008561
0x180008559  xor     r9d, r9d
0x18000855c  mov     [rsp+1090h+var_1050], r9d
0x180008561  mov     r8, [r14]
0x180008564  mov     rax, r11
0x180008567  mov     ecx, r9d
0x18000856a  mul     rcx
0x18000856d  mov     rcx, [r14+8]
0x180008571  mov     rax, r11
0x180008574  mov     r10, rdx
0x180008577  sub     rcx, r8
0x18000857a  mul     rcx
0x18000857d  shr     r10, 3
0x180008581  shr     rdx, 3
0x180008585  lea     rax, [rdx+rdx*2]
0x180008589  lea     rsi, [r8+rax*4]
0x18000858d  jmp     short loc_1800085F8
0x18000858f  mov     eax, r10d
0x180008592  lea     rcx, [rax+rax*2]
0x180008596  lea     rdx, [rdx+rcx*4]
0x18000859a  lea     rax, [rsp+1090h+var_1040]
0x18000859f  cmp     rax, rdx
0x1800085a2  jz      short loc_1800085C9
0x1800085a4  mov     r11d, [r8]
0x1800085a7  lea     rcx, [rsp+1090h+var_1040]
0x1800085ac  cmp     [rcx], r11d
0x1800085af  jnz     short loc_1800085C0
0x1800085b1  movzx   eax, word ptr [r8+4]
0x1800085b6  cmp     [rcx+4], ax
0x1800085ba  jz      loc_180008662
0x1800085c0  add     rcx, 0Ch
0x1800085c4  cmp     rcx, rdx
0x1800085c7  jnz     short loc_1800085AC
0x1800085c9  mov     eax, r9d
0x1800085cc  add     rax, 0Ch
0x1800085d0  cmp     rax, 1000h
0x1800085d6  ja      short loc_1800085F4
0x1800085d8  movsd   xmm0, qword ptr [r8]
0x1800085dd  add     r9d, 0Ch
0x1800085e1  movsd   qword ptr [rdx], xmm0
0x1800085e5  inc     r10d
0x1800085e8  mov     eax, [r8+8]
0x1800085ec  mov     [rdx+8], eax
0x1800085ef  mov     [rsp+1090h+var_1050], r9d
0x1800085f4  add     r8, 0Ch
0x1800085f8  lea     rdx, [rsp+1090h+var_1040]
0x1800085fd  cmp     r8, rsi
0x180008600  jnz     short loc_18000858F
0x180008602  mov     eax, [rsp+1090h+var_104C]
0x180008606  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x18000860d  mov     [rsp+1090h+var_1060], 1
0x180008615  mov     r8d, r9d
0x180008618  mov     dword ptr [rsp+1090h+var_1068], eax
0x18000861c  call    wil_details_NtUpdateWnfStateData
0x180008621  mov     esi, eax
0x180008623  cmp     esi, 0C0000001h
0x180008629  jnz     short loc_18000863C
0x18000862b  inc     r15d
0x18000862e  cmp     r15d, 64h ; 'd'
0x180008632  jge     short loc_18000863C
0x180008634  test    edi, edi
0x180008636  jz      loc_180008482
0x18000863c  test    ebx, ebx
0x18000863e  cmovz   ebx, esi
0x180008641  mov     eax, ebx
0x180008643  mov     rcx, [rbp+0F90h+var_40]
0x18000864a  xor     rcx, rsp; StackCookie
0x18000864d  call    __security_check_cookie
0x180008652  add     rsp, 1068h
0x180008659  pop     r15
0x18000865b  pop     r14
0x18000865d  pop     rdi
0x18000865e  pop     rsi
0x18000865f  pop     rbx
0x180008660  pop     rbp
0x180008661  retn
0x180008662  mov     eax, [r8+8]
0x180008666  add     [rcx+8], eax
0x180008669  mov     r9d, [rsp+1090h+var_1050]
0x18000866e  jmp     short loc_1800085F4
```
