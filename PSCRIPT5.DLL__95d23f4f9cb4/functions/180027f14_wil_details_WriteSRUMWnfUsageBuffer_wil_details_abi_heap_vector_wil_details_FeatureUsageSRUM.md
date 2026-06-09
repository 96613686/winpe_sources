# wil_details_WriteSRUMWnfUsageBuffer(wil::details_abi::heap_vector<wil_details_FeatureUsageSRUM> *)

- ea: `0x180027f14`
- end: `0x18002814c`
- name: `?wil_details_WriteSRUMWnfUsageBuffer@@YAJPEAV?$heap_vector@Uwil_details_FeatureUsageSRUM@@@details_abi@wil@@@Z`
- size: `568`
- prototype: ``
- caller_count: `1`
- callee_count: `6`
- tags: `loader_planting, installer_update`

## callers

- `0x180022580`

## callees

- `0x180001ee0`
- `0x1800028d8`
- `0x180027f14`
- `0x1800287dc`
- `0x18005c3b0`
- `0x18005d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x180027f9d`
- `KERNEL32!GetModuleHandleW` at `0x180027f9d`
- `KERNEL32!GetProcAddress` at `0x180027fb4`
- `KERNEL32!GetProcAddress` at `0x180027fb4`

## string_xrefs

- `0x180027f96`: `ntdll.dll`

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
0x180027f14  push    rbp
0x180027f16  push    rbx
0x180027f17  push    rsi
0x180027f18  push    rdi
0x180027f19  push    r14
0x180027f1b  push    r15
0x180027f1d  lea     rbp, [rsp-0F68h]
0x180027f25  mov     eax, 1068h
0x180027f2a  call    _alloca_probe
0x180027f2f  sub     rsp, rax
0x180027f32  mov     rax, cs:__security_cookie
0x180027f39  xor     rax, rsp
0x180027f3c  mov     [rbp+0F90h+var_40], rax
0x180027f43  mov     rax, [rcx+8]
0x180027f47  xor     ebx, ebx
0x180027f49  sub     rax, [rcx]
0x180027f4c  xor     esi, esi
0x180027f4e  mov     r14, rcx
0x180027f51  cmp     rax, 0Ch
0x180027f55  jb      loc_180028118
0x180027f5b  xor     r15d, r15d
0x180027f5e  xor     edx, edx; Val
0x180027f60  lea     rcx, [rsp+1090h+var_1040]; void *
0x180027f65  mov     r8d, 1000h; Size
0x180027f6b  call    memset_0
0x180027f70  cmp     cs:g_wil_details_pfnNtQueryWnfStateData, 0
0x180027f78  mov     [rsp+1090h+var_1050], 1000h
0x180027f80  mov     [rsp+1090h+var_104C], 0
0x180027f88  jnz     short loc_180027FD2
0x180027f8a  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027f91  test    rax, rax
0x180027f94  jnz     short loc_180027FAA
0x180027f96  lea     rcx, aNtdllDll; "ntdll.dll"
0x180027f9d  call    cs:__imp_GetModuleHandleW
0x180027fa3  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180027faa  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180027fb1  mov     rcx, rax; hModule
0x180027fb4  call    cs:__imp_GetProcAddress
0x180027fba  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180027fc1  test    rax, rax
0x180027fc4  jnz     short loc_180027FD2
0x180027fc6  mov     edi, 0C0000139h
0x180027fcb  mov     ebx, edi
0x180027fcd  jmp     loc_1800280FF
0x180027fd2  lea     rax, [rsp+1090h+var_1050]
0x180027fd7  xor     r8d, r8d
0x180027fda  mov     [rsp+1090h+var_1068], rax
0x180027fdf  lea     r9, [rsp+1090h+var_104C]
0x180027fe4  lea     rax, [rsp+1090h+var_1040]
0x180027fe9  xor     edx, edx
0x180027feb  mov     [rsp+1090h+var_1070], rax
0x180027ff0  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x180027ff7  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180027ffe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180028003  mov     ebx, eax
0x180028005  mov     edi, eax
0x180028007  test    eax, eax
0x180028009  jnz     loc_1800280FF
0x18002800f  mov     r9d, [rsp+1090h+var_1050]
0x180028014  mov     r11, 0AAAAAAAAAAAAAAABh
0x18002801e  mov     rax, r11
0x180028021  mul     r9
0x180028024  shr     rdx, 3
0x180028028  lea     rcx, [rdx+rdx*2]
0x18002802c  shl     rcx, 2
0x180028030  cmp     r9, rcx
0x180028033  jz      short loc_18002803D
0x180028035  xor     r9d, r9d
0x180028038  mov     [rsp+1090h+var_1050], r9d
0x18002803d  mov     r8, [r14]
0x180028040  mov     rax, r11
0x180028043  mov     ecx, r9d
0x180028046  mul     rcx
0x180028049  mov     rcx, [r14+8]
0x18002804d  mov     rax, r11
0x180028050  mov     r10, rdx
0x180028053  sub     rcx, r8
0x180028056  mul     rcx
0x180028059  shr     r10, 3
0x18002805d  shr     rdx, 3
0x180028061  lea     rax, [rdx+rdx*2]
0x180028065  lea     rsi, [r8+rax*4]
0x180028069  jmp     short loc_1800280D4
0x18002806b  mov     eax, r10d
0x18002806e  lea     rcx, [rax+rax*2]
0x180028072  lea     rdx, [rdx+rcx*4]
0x180028076  lea     rax, [rsp+1090h+var_1040]
0x18002807b  cmp     rax, rdx
0x18002807e  jz      short loc_1800280A5
0x180028080  mov     r11d, [r8]
0x180028083  lea     rcx, [rsp+1090h+var_1040]
0x180028088  cmp     [rcx], r11d
0x18002808b  jnz     short loc_18002809C
0x18002808d  movzx   eax, word ptr [r8+4]
0x180028092  cmp     [rcx+4], ax
0x180028096  jz      loc_18002813E
0x18002809c  add     rcx, 0Ch
0x1800280a0  cmp     rcx, rdx
0x1800280a3  jnz     short loc_180028088
0x1800280a5  mov     eax, r9d
0x1800280a8  add     rax, 0Ch
0x1800280ac  cmp     rax, 1000h
0x1800280b2  ja      short loc_1800280D0
0x1800280b4  movsd   xmm0, qword ptr [r8]
0x1800280b9  add     r9d, 0Ch
0x1800280bd  movsd   qword ptr [rdx], xmm0
0x1800280c1  inc     r10d
0x1800280c4  mov     eax, [r8+8]
0x1800280c8  mov     [rdx+8], eax
0x1800280cb  mov     [rsp+1090h+var_1050], r9d
0x1800280d0  add     r8, 0Ch
0x1800280d4  lea     rdx, [rsp+1090h+var_1040]
0x1800280d9  cmp     r8, rsi
0x1800280dc  jnz     short loc_18002806B
0x1800280de  mov     eax, [rsp+1090h+var_104C]
0x1800280e2  lea     rcx, ?__WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM@@3U__WIL__WNF_STATE_NAME@@B; __WIL__WNF_STATE_NAME const __WIL_WNF_WIL_FEATURE_USAGE_FOR_SRUM
0x1800280e9  mov     [rsp+1090h+var_1060], 1
0x1800280f1  mov     r8d, r9d
0x1800280f4  mov     dword ptr [rsp+1090h+var_1068], eax
0x1800280f8  call    wil_details_NtUpdateWnfStateData
0x1800280fd  mov     esi, eax
0x1800280ff  cmp     esi, 0C0000001h
0x180028105  jnz     short loc_180028118
0x180028107  inc     r15d
0x18002810a  cmp     r15d, 64h ; 'd'
0x18002810e  jge     short loc_180028118
0x180028110  test    edi, edi
0x180028112  jz      loc_180027F5E
0x180028118  test    ebx, ebx
0x18002811a  cmovz   ebx, esi
0x18002811d  mov     eax, ebx
0x18002811f  mov     rcx, [rbp+0F90h+var_40]
0x180028126  xor     rcx, rsp; StackCookie
0x180028129  call    __security_check_cookie
0x18002812e  add     rsp, 1068h
0x180028135  pop     r15
0x180028137  pop     r14
0x180028139  pop     rdi
0x18002813a  pop     rsi
0x18002813b  pop     rbx
0x18002813c  pop     rbp
0x18002813d  retn
0x18002813e  mov     eax, [r8+8]
0x180028142  add     [rcx+8], eax
0x180028145  mov     r9d, [rsp+1090h+var_1050]
0x18002814a  jmp     short loc_1800280D0
```
