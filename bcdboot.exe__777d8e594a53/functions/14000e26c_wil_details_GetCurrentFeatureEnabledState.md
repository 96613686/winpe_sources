# wil_details_GetCurrentFeatureEnabledState

- ea: `0x14000e26c`
- end: `0x14000e4b1`
- name: `wil_details_GetCurrentFeatureEnabledState`
- size: `581`
- prototype: `__int64 __fastcall(__int64, _DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x14000e100`

## callees

- `0x14000e100`
- `0x14000e26c`
- `0x140026650`
- `0x140027010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x14000e2fe`
- `KERNEL32!GetProcAddress` at `0x14000e2fe`
- `KERNEL32!GetModuleHandleW` at `0x14000e2e7`
- `KERNEL32!GetModuleHandleW` at `0x14000e2e7`

## string_xrefs

- `0x14000e2e0`: `ntdll.dll`
- `0x14000e2f4`: `RtlQueryFeatureConfiguration`

## pseudocode

```c
__int64 __fastcall wil_details_GetCurrentFeatureEnabledState(__int64 a1, _DWORD *a2)
{
  unsigned int v2; // r14d
  unsigned __int8 v3; // al
  int v5; // edi
  BOOL v6; // ebx
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v9; // r9d
  int v10; // eax
  int v11; // r8d
  int v12; // r9d
  int v13; // edx
  int v14; // eax
  unsigned int v15; // ecx
  int v16; // r12d
  __int64 *v17; // rsi
  int v18; // r15d
  BOOL v19; // ebx
  __int64 v20; // rcx
  volatile signed __int32 *v21; // r9
  char v22; // al
  __int64 v24; // [rsp+30h] [rbp-40h] BYREF
  __int128 v25; // [rsp+38h] [rbp-38h]
  __int64 v26; // [rsp+48h] [rbp-28h]
  __int64 v27; // [rsp+50h] [rbp-20h] BYREF
  int v28; // [rsp+58h] [rbp-18h]

  v2 = *(_DWORD *)(a1 + 24);
  v3 = *(_BYTE *)(a1 + 28) - 2;
  v25 = 0;
  v5 = 1;
  *a2 = 1;
  v6 = v3 > 1u;
  v26 = 0;
  v24 = 0;
  v27 = 0;
  v28 = 0;
  ProcAddress = (FARPROC)g_wil_details_pfnRtlQueryFeatureConfiguration;
  if ( !g_wil_details_pfnRtlQueryFeatureConfiguration )
  {
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "RtlQueryFeatureConfiguration");
    g_wil_details_pfnRtlQueryFeatureConfiguration = (__int64)ProcAddress;
    if ( !ProcAddress )
    {
      v9 = 0;
      goto LABEL_6;
    }
  }
  v14 = ((__int64 (__fastcall *)(_QWORD, BOOL, __int64 *, __int64 *))ProcAddress)(v2, v6, &v24, &v27);
  if ( v14 )
  {
    v9 = 0;
    if ( v14 == 279 )
    {
      v9 = 1;
      v10 = v26;
      if ( (v27 & 0x8000000000LL) != 0 )
        v10 = 1;
      goto LABEL_7;
    }
LABEL_6:
    v10 = v26;
LABEL_7:
    v11 = v25;
    goto LABEL_8;
  }
  v9 = 1;
  HIDWORD(v26) = (BYTE4(v27) >> 6) & 1;
  v11 = (HIDWORD(v27) >> 4) & 3;
  v10 = BYTE4(v27) >> 7;
LABEL_8:
  v24 = 0;
  v12 = -v9;
  if ( ((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) != 0 )
  {
    v13 = 0;
    if ( v11 == 2 )
      v13 = 64;
  }
  else
  {
    v13 = *(_BYTE *)(a1 + 31) != 0 ? 0x40 : 0;
  }
  v15 = v13
      | (v10 != 0 ? 0x400 : 0)
      | (HIDWORD(v26) != 0 ? 0x800 : 0)
      | (((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) << 7);
  if ( (v13 & 0xC00
      | (v10 != 0 ? 0x400 : 0)
      | (HIDWORD(v26) != 0 ? 0x800 : 0)
      | (((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) << 7) & 0xC00) == 0xC00 )
  {
    v16 = 1;
  }
  else
  {
    v16 = 0;
    if ( (v13 & 0x40) == 0 )
    {
LABEL_38:
      v5 = 0;
      goto LABEL_39;
    }
  }
  v17 = *(__int64 **)(a1 + 32);
  v18 = v13
      | (v10 != 0 ? 0x400 : 0)
      | (HIDWORD(v26) != 0 ? 0x800 : 0)
      | (((unsigned __int8)v11 & (unsigned __int8)-(v12 != 0) & 3) << 7);
  v19 = 1;
  if ( v17 )
  {
    while ( 1 )
    {
      v20 = *v17;
      if ( !*v17 )
        break;
      if ( *(_BYTE *)(v20 + 30) || *(_BYTE *)(v20 + 29) )
      {
        if ( !*(_BYTE *)(v20 + 31) )
        {
          v19 = 0;
          break;
        }
        v19 = 1;
        ++v17;
      }
      else
      {
        v21 = *(volatile signed __int32 **)v20;
        v27 = 0;
        LODWORD(v27) = *v21;
        if ( (v27 & 2) != 0 )
          v22 = v27;
        else
          v22 = wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState(v21, v27, v20);
        v19 = (v22 & 1) != 0;
        ++v17;
        if ( (v22 & 1) == 0 )
          break;
      }
    }
  }
  v15 = v18;
  if ( v16 && !v19 )
    v15 = v18 & 0xFFFFFBFF;
  if ( (v15 & 0x40) == 0 || !v19 )
    goto LABEL_38;
LABEL_39:
  LODWORD(v24) = v5 | v15 & 0xFFFFFFFE;
  return v24;
}

```

## disassembly

```asm
0x14000e26c  mov     [rsp-28h+arg_10], rbx
0x14000e271  mov     [rsp-28h+arg_18], rsi
0x14000e276  push    rbp
0x14000e277  push    rdi
0x14000e278  push    r12
0x14000e27a  push    r14
0x14000e27c  push    r15
0x14000e27e  mov     rbp, rsp
0x14000e281  sub     rsp, 70h
0x14000e285  mov     rax, cs:__security_cookie
0x14000e28c  xor     rax, rsp
0x14000e28f  mov     [rbp+var_10], rax
0x14000e293  mov     al, [rcx+1Ch]
0x14000e296  xor     ebx, ebx
0x14000e298  mov     r14d, [rcx+18h]
0x14000e29c  sub     al, 2
0x14000e29e  xorps   xmm0, xmm0
0x14000e2a1  mov     rsi, rcx
0x14000e2a4  movups  [rbp+var_38], xmm0
0x14000e2a8  lea     edi, [rbx+1]
0x14000e2ab  cmp     al, dil
0x14000e2ae  mov     [rdx], edi
0x14000e2b0  setnbe  bl
0x14000e2b3  xor     eax, eax
0x14000e2b5  mov     [rbp+var_28], rax
0x14000e2b9  mov     [rbp+var_40], rax
0x14000e2bd  mov     [rbp+var_20], rax
0x14000e2c1  mov     [rbp+var_18], eax
0x14000e2c4  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x14000e2cb  test    rax, rax
0x14000e2ce  jnz     loc_14000E363
0x14000e2d4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14000e2db  test    rax, rax
0x14000e2de  jnz     short loc_14000E2F4
0x14000e2e0  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000e2e7  call    cs:__imp_GetModuleHandleW
0x14000e2ed  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x14000e2f4  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x14000e2fb  mov     rcx, rax; hModule
0x14000e2fe  call    cs:__imp_GetProcAddress
0x14000e304  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x14000e30b  test    rax, rax
0x14000e30e  jnz     short loc_14000E363
0x14000e310  xor     r9d, r9d
0x14000e313  mov     eax, dword ptr [rbp+var_28]
0x14000e316  mov     r8d, dword ptr [rbp+var_38]
0x14000e31a  neg     eax
0x14000e31c  mov     [rbp+var_40], 0
0x14000e324  mov     eax, dword ptr [rbp+var_28+4]
0x14000e327  mov     r14d, 40h ; '@'
0x14000e32d  sbb     ecx, ecx
0x14000e32f  and     ecx, 400h
0x14000e335  neg     eax
0x14000e337  sbb     edx, edx
0x14000e339  and     edx, 800h
0x14000e33f  or      edx, ecx
0x14000e341  neg     r9d
0x14000e344  sbb     eax, eax
0x14000e346  and     eax, r8d
0x14000e349  and     eax, 3
0x14000e34c  mov     ecx, eax
0x14000e34e  shl     ecx, 7
0x14000e351  or      ecx, edx
0x14000e353  test    eax, eax
0x14000e355  jnz     short loc_14000E3C0
0x14000e357  mov     al, [rsi+1Fh]
0x14000e35a  neg     al
0x14000e35c  sbb     edx, edx
0x14000e35e  and     edx, r14d
0x14000e361  jmp     short loc_14000E3CA
0x14000e363  lea     r9, [rbp+var_20]
0x14000e367  mov     edx, ebx
0x14000e369  lea     r8, [rbp+var_40]
0x14000e36d  mov     ecx, r14d
0x14000e370  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000e375  test    eax, eax
0x14000e377  jnz     short loc_14000E3A0
0x14000e379  mov     ecx, dword ptr [rbp+var_20+4]
0x14000e37c  mov     r9d, edi
0x14000e37f  movzx   eax, cl
0x14000e382  mov     r8d, ecx
0x14000e385  shr     eax, 6
0x14000e388  and     eax, edi
0x14000e38a  shr     r8d, 4
0x14000e38e  mov     dword ptr [rbp+var_28+4], eax
0x14000e391  and     r8d, 3
0x14000e395  movzx   eax, cl
0x14000e398  shr     eax, 7
0x14000e39b  jmp     loc_14000E31A
0x14000e3a0  xor     r9d, r9d
0x14000e3a3  cmp     eax, 117h
0x14000e3a8  jnz     loc_14000E313
0x14000e3ae  test    byte ptr [rbp+var_20+4], 80h
0x14000e3b2  mov     r9d, edi
0x14000e3b5  mov     eax, dword ptr [rbp+var_28]
0x14000e3b8  cmovnz  eax, edi
0x14000e3bb  jmp     loc_14000E316
0x14000e3c0  xor     edx, edx
0x14000e3c2  cmp     r8d, 2
0x14000e3c6  cmovz   edx, r14d
0x14000e3ca  or      ecx, edx
0x14000e3cc  mov     edx, 0C00h
0x14000e3d1  mov     eax, ecx
0x14000e3d3  and     eax, edx
0x14000e3d5  cmp     eax, edx
0x14000e3d7  jnz     short loc_14000E3DE
0x14000e3d9  mov     r12d, edi
0x14000e3dc  jmp     short loc_14000E3EC
0x14000e3de  xor     r12d, r12d
0x14000e3e1  xor     ebx, ebx
0x14000e3e3  test    r14b, cl
0x14000e3e6  jz      loc_14000E47E
0x14000e3ec  mov     rsi, [rsi+20h]
0x14000e3f0  mov     r15d, ecx
0x14000e3f3  mov     ebx, edi
0x14000e3f5  test    rsi, rsi
0x14000e3f8  jz      short loc_14000E465
0x14000e3fa  mov     rcx, [rsi]
0x14000e3fd  test    rcx, rcx
0x14000e400  jz      short loc_14000E465
0x14000e402  cmp     byte ptr [rcx+1Eh], 0
0x14000e406  jnz     short loc_14000E451
0x14000e408  cmp     byte ptr [rcx+1Dh], 0
0x14000e40c  jnz     short loc_14000E451
0x14000e40e  mov     r9, [rcx]
0x14000e411  mov     [rbp+var_20], 0
0x14000e419  mov     eax, [r9]
0x14000e41c  mov     dword ptr [rbp+var_20], eax
0x14000e41f  test    al, 2
0x14000e421  jz      short loc_14000E429
0x14000e423  mov     rax, [rbp+var_20]
0x14000e427  jmp     short loc_14000E438
0x14000e429  mov     rdx, [rbp+var_20]
0x14000e42d  mov     r8, rcx
0x14000e430  mov     rcx, r9
0x14000e433  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x14000e438  test    ebx, ebx
0x14000e43a  jz      short loc_14000E445
0x14000e43c  test    dil, al
0x14000e43f  jz      short loc_14000E445
0x14000e441  mov     ebx, edi
0x14000e443  jmp     short loc_14000E447
0x14000e445  xor     ebx, ebx
0x14000e447  add     rsi, 8
0x14000e44b  test    ebx, ebx
0x14000e44d  jnz     short loc_14000E3FA
0x14000e44f  jmp     short loc_14000E465
0x14000e451  test    ebx, ebx
0x14000e453  jz      short loc_14000E463
0x14000e455  cmp     byte ptr [rcx+1Fh], 0
0x14000e459  jz      short loc_14000E463
0x14000e45b  mov     ebx, edi
0x14000e45d  add     rsi, 8
0x14000e461  jmp     short loc_14000E3FA
0x14000e463  xor     ebx, ebx
0x14000e465  mov     ecx, r15d
0x14000e468  test    r12d, r12d
0x14000e46b  jz      short loc_14000E475
0x14000e46d  test    ebx, ebx
0x14000e46f  jnz     short loc_14000E475
0x14000e471  btr     ecx, 0Ah
0x14000e475  test    r14b, cl
0x14000e478  jz      short loc_14000E47E
0x14000e47a  test    ebx, ebx
0x14000e47c  jnz     short loc_14000E480
0x14000e47e  xor     edi, edi
0x14000e480  and     ecx, 0FFFFFFFEh
0x14000e483  or      ecx, edi
0x14000e485  mov     dword ptr [rbp+var_40], ecx
0x14000e488  mov     rax, [rbp+var_40]
0x14000e48c  mov     rcx, [rbp+var_10]
0x14000e490  xor     rcx, rsp; StackCookie
0x14000e493  call    __security_check_cookie
0x14000e498  lea     r11, [rsp+70h+var_s0]
0x14000e49d  mov     rbx, [r11+40h]
0x14000e4a1  mov     rsi, [r11+48h]
0x14000e4a5  mov     rsp, r11
0x14000e4a8  pop     r15
0x14000e4aa  pop     r14
0x14000e4ac  pop     r12
0x14000e4ae  pop     rdi
0x14000e4af  pop     rbp
0x14000e4b0  retn
```
