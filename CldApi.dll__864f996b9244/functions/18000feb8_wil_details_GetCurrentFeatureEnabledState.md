# wil_details_GetCurrentFeatureEnabledState

- ea: `0x18000feb8`
- end: `0x1800100fd`
- name: `wil_details_GetCurrentFeatureEnabledState`
- size: `581`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, loader_planting`

## callers

- `0x18000fd5c`

## callees

- `0x180001a80`
- `0x18000fd5c`
- `0x18000feb8`
- `0x18001c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ff4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000ff4a`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ff33`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000ff33`

## string_xrefs

- `0x18000ff2c`: `ntdll.dll`
- `0x18000ff40`: `RtlQueryFeatureConfiguration`

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
  _DWORD *v21; // r9
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
        v21 = *(_DWORD **)v20;
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
0x18000feb8  mov     [rsp-28h+arg_10], rbx
0x18000febd  mov     [rsp-28h+arg_18], rsi
0x18000fec2  push    rbp
0x18000fec3  push    rdi
0x18000fec4  push    r12
0x18000fec6  push    r14
0x18000fec8  push    r15
0x18000feca  mov     rbp, rsp
0x18000fecd  sub     rsp, 70h
0x18000fed1  mov     rax, cs:__security_cookie
0x18000fed8  xor     rax, rsp
0x18000fedb  mov     [rbp+var_10], rax
0x18000fedf  mov     al, [rcx+1Ch]
0x18000fee2  xor     ebx, ebx
0x18000fee4  mov     r14d, [rcx+18h]
0x18000fee8  sub     al, 2
0x18000feea  xorps   xmm0, xmm0
0x18000feed  mov     rsi, rcx
0x18000fef0  movups  [rbp+var_38], xmm0
0x18000fef4  lea     edi, [rbx+1]
0x18000fef7  cmp     al, dil
0x18000fefa  mov     [rdx], edi
0x18000fefc  setnbe  bl
0x18000feff  xor     eax, eax
0x18000ff01  mov     [rbp+var_28], rax
0x18000ff05  mov     [rbp+var_40], rax
0x18000ff09  mov     [rbp+var_20], rax
0x18000ff0d  mov     [rbp+var_18], eax
0x18000ff10  mov     rax, cs:g_wil_details_pfnRtlQueryFeatureConfiguration
0x18000ff17  test    rax, rax
0x18000ff1a  jnz     loc_18000FFAF
0x18000ff20  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000ff27  test    rax, rax
0x18000ff2a  jnz     short loc_18000FF40
0x18000ff2c  lea     rcx, ModuleName; "ntdll.dll"
0x18000ff33  call    cs:__imp_GetModuleHandleW
0x18000ff39  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@9@9, rax; `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle
0x18000ff40  lea     rdx, aRtlqueryfeatur; "RtlQueryFeatureConfiguration"
0x18000ff47  mov     rcx, rax; hModule
0x18000ff4a  call    cs:__imp_GetProcAddress
0x18000ff50  mov     cs:g_wil_details_pfnRtlQueryFeatureConfiguration, rax
0x18000ff57  test    rax, rax
0x18000ff5a  jnz     short loc_18000FFAF
0x18000ff5c  xor     r9d, r9d
0x18000ff5f  mov     eax, dword ptr [rbp+var_28]
0x18000ff62  mov     r8d, dword ptr [rbp+var_38]
0x18000ff66  neg     eax
0x18000ff68  mov     [rbp+var_40], 0
0x18000ff70  mov     eax, dword ptr [rbp+var_28+4]
0x18000ff73  mov     r14d, 40h ; '@'
0x18000ff79  sbb     ecx, ecx
0x18000ff7b  and     ecx, 400h
0x18000ff81  neg     eax
0x18000ff83  sbb     edx, edx
0x18000ff85  and     edx, 800h
0x18000ff8b  or      edx, ecx
0x18000ff8d  neg     r9d
0x18000ff90  sbb     eax, eax
0x18000ff92  and     eax, r8d
0x18000ff95  and     eax, 3
0x18000ff98  mov     ecx, eax
0x18000ff9a  shl     ecx, 7
0x18000ff9d  or      ecx, edx
0x18000ff9f  test    eax, eax
0x18000ffa1  jnz     short loc_18001000C
0x18000ffa3  mov     al, [rsi+1Fh]
0x18000ffa6  neg     al
0x18000ffa8  sbb     edx, edx
0x18000ffaa  and     edx, r14d
0x18000ffad  jmp     short loc_180010016
0x18000ffaf  lea     r9, [rbp+var_20]
0x18000ffb3  mov     edx, ebx
0x18000ffb5  lea     r8, [rbp+var_40]
0x18000ffb9  mov     ecx, r14d
0x18000ffbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000ffc1  test    eax, eax
0x18000ffc3  jnz     short loc_18000FFEC
0x18000ffc5  mov     ecx, dword ptr [rbp+var_20+4]
0x18000ffc8  mov     r9d, edi
0x18000ffcb  movzx   eax, cl
0x18000ffce  mov     r8d, ecx
0x18000ffd1  shr     eax, 6
0x18000ffd4  and     eax, edi
0x18000ffd6  shr     r8d, 4
0x18000ffda  mov     dword ptr [rbp+var_28+4], eax
0x18000ffdd  and     r8d, 3
0x18000ffe1  movzx   eax, cl
0x18000ffe4  shr     eax, 7
0x18000ffe7  jmp     loc_18000FF66
0x18000ffec  xor     r9d, r9d
0x18000ffef  cmp     eax, 117h
0x18000fff4  jnz     loc_18000FF5F
0x18000fffa  test    byte ptr [rbp+var_20+4], 80h
0x18000fffe  mov     r9d, edi
0x180010001  mov     eax, dword ptr [rbp+var_28]
0x180010004  cmovnz  eax, edi
0x180010007  jmp     loc_18000FF62
0x18001000c  xor     edx, edx
0x18001000e  cmp     r8d, 2
0x180010012  cmovz   edx, r14d
0x180010016  or      ecx, edx
0x180010018  mov     edx, 0C00h
0x18001001d  mov     eax, ecx
0x18001001f  and     eax, edx
0x180010021  cmp     eax, edx
0x180010023  jnz     short loc_18001002A
0x180010025  mov     r12d, edi
0x180010028  jmp     short loc_180010038
0x18001002a  xor     r12d, r12d
0x18001002d  xor     ebx, ebx
0x18001002f  test    r14b, cl
0x180010032  jz      loc_1800100CA
0x180010038  mov     rsi, [rsi+20h]
0x18001003c  mov     r15d, ecx
0x18001003f  mov     ebx, edi
0x180010041  test    rsi, rsi
0x180010044  jz      short loc_1800100B1
0x180010046  mov     rcx, [rsi]
0x180010049  test    rcx, rcx
0x18001004c  jz      short loc_1800100B1
0x18001004e  cmp     byte ptr [rcx+1Eh], 0
0x180010052  jnz     short loc_18001009D
0x180010054  cmp     byte ptr [rcx+1Dh], 0
0x180010058  jnz     short loc_18001009D
0x18001005a  mov     r9, [rcx]
0x18001005d  mov     [rbp+var_20], 0
0x180010065  mov     eax, [r9]
0x180010068  mov     dword ptr [rbp+var_20], eax
0x18001006b  test    al, 2
0x18001006d  jz      short loc_180010075
0x18001006f  mov     rax, [rbp+var_20]
0x180010073  jmp     short loc_180010084
0x180010075  mov     rdx, [rbp+var_20]
0x180010079  mov     r8, rcx
0x18001007c  mov     rcx, r9
0x18001007f  call    wil_details_FeatureStateCache_ReevaluateCachedFeatureEnabledState
0x180010084  test    ebx, ebx
0x180010086  jz      short loc_180010091
0x180010088  test    dil, al
0x18001008b  jz      short loc_180010091
0x18001008d  mov     ebx, edi
0x18001008f  jmp     short loc_180010093
0x180010091  xor     ebx, ebx
0x180010093  add     rsi, 8
0x180010097  test    ebx, ebx
0x180010099  jnz     short loc_180010046
0x18001009b  jmp     short loc_1800100B1
0x18001009d  test    ebx, ebx
0x18001009f  jz      short loc_1800100AF
0x1800100a1  cmp     byte ptr [rcx+1Fh], 0
0x1800100a5  jz      short loc_1800100AF
0x1800100a7  mov     ebx, edi
0x1800100a9  add     rsi, 8
0x1800100ad  jmp     short loc_180010046
0x1800100af  xor     ebx, ebx
0x1800100b1  mov     ecx, r15d
0x1800100b4  test    r12d, r12d
0x1800100b7  jz      short loc_1800100C1
0x1800100b9  test    ebx, ebx
0x1800100bb  jnz     short loc_1800100C1
0x1800100bd  btr     ecx, 0Ah
0x1800100c1  test    r14b, cl
0x1800100c4  jz      short loc_1800100CA
0x1800100c6  test    ebx, ebx
0x1800100c8  jnz     short loc_1800100CC
0x1800100ca  xor     edi, edi
0x1800100cc  and     ecx, 0FFFFFFFEh
0x1800100cf  or      ecx, edi
0x1800100d1  mov     dword ptr [rbp+var_40], ecx
0x1800100d4  mov     rax, [rbp+var_40]
0x1800100d8  mov     rcx, [rbp+var_10]
0x1800100dc  xor     rcx, rsp; StackCookie
0x1800100df  call    __security_check_cookie
0x1800100e4  lea     r11, [rsp+70h+var_s0]
0x1800100e9  mov     rbx, [r11+40h]
0x1800100ed  mov     rsi, [r11+48h]
0x1800100f1  mov     rsp, r11
0x1800100f4  pop     r15
0x1800100f6  pop     r14
0x1800100f8  pop     r12
0x1800100fa  pop     rdi
0x1800100fb  pop     rbp
0x1800100fc  retn
```
