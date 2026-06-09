# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18002cf80`
- end: `0x18002d357`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18002c4b8`

## callees

- `0x18002bc54`
- `0x18002c3c8`
- `0x18002cf80`
- `0x18002ddc4`
- `0x18002febc`
- `0x180031150`
- `0x1800350e0`
- `0x1800351a0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d076`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18002d076`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d05f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18002d05f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d2ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d321`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d2ea`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002d321`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d2dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d313`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d2dc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002d313`

## string_xrefs

- `0x18002d058`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v5; // r14
  wil::details_abi *v6; // r12
  unsigned __int64 v7; // r15
  char v8; // cl
  unsigned int v9; // edx
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // edi
  unsigned int v15; // eax
  int v16; // edi
  int v17; // r9d
  char v18; // di
  int updated; // eax
  int v20; // r9d
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  __int64 *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v26; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v27[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+64h] [rbp-9Ch]
  __int16 v30; // [rsp+66h] [rbp-9Ah]
  char v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  __int128 v34; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v36; // [rsp+98h] [rbp-68h]
  char v37; // [rsp+9Ah] [rbp-66h]
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v40; // [rsp+B0h] [rbp-50h] BYREF
  char v41; // [rsp+B2h] [rbp-4Eh]
  unsigned int v42; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v43; // [rsp+B8h] [rbp-48h]
  __int128 v44; // [rsp+C0h] [rbp-40h]
  __int16 v45; // [rsp+D0h] [rbp-30h] BYREF
  char v46; // [rsp+D2h] [rbp-2Eh]
  int v47; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v48; // [rsp+D8h] [rbp-28h]
  __int128 v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v52; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v53[2]; // [rsp+108h] [rbp+8h] BYREF
  char v54; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v55[13]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *v56; // [rsp+188h] [rbp+88h]
  _BYTE v57[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v39 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v28[0] = *(_WORD *)a3;
    v28[1] = *(_WORD *)(a3 + 2);
    v29 = *(_BYTE *)(a3 + 4);
    v30 = v9;
    v31 = v8;
    if ( (_WORD)v9 )
    {
      v10 = v9;
      if ( v8 == 1 )
      {
        v10 = v9 + 2LL;
      }
      else if ( v8 == 2 )
      {
        v10 = v9 + 4LL;
      }
      v32 = v10;
    }
    else
    {
      v32 = 0;
    }
    v33 = 0;
    v34 = 0;
    lpMem = 0;
    v36 = 0;
    v37 = 0;
    v27[0] = 0;
    LODWORD(v26) = 4096;
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    if ( g_wil_details_pfnNtQueryWnfStateData )
      goto LABEL_14;
    ModuleHandleW = `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
    if ( !`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle )
    {
      ModuleHandleW = GetModuleHandleW(L"ntdll.dll");
      `wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle = ModuleHandleW;
    }
    ProcAddress = GetProcAddress(ModuleHandleW, "NtQueryWnfStateData");
    g_wil_details_pfnNtQueryWnfStateData = (__int64)ProcAddress;
    if ( ProcAddress )
    {
LABEL_14:
      v25 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v5, 0, 0, v27);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v26) = 0;
      v27[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v26;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v28, v57, v15, 0x1000u);
    if ( HIBYTE(v36) )
      break;
    v38 = 0;
    v55[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v55[1] = &v38;
    v55[2] = &v39;
    v55[3] = v28;
    v56 = (wil::details::in1diag3 *)v55;
    v53[1] = &v54;
    v26 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v40 = *(_WORD *)(a3 + 2);
    v41 = *(_BYTE *)(a3 + 4);
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = *(_WORD *)(a3 + 6);
    v46 = *(_BYTE *)(a3 + 8);
    v47 = 0;
    v48 = 0;
    v49 = 0;
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v40,
              &v26,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      if ( v42 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v45,
                  &v26,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v27[2] = v47;
          v50 = v48;
          v51 = *((_QWORD *)&v49 + 1);
          v52 = v43;
          v53[0] = *((_QWORD *)&v44 + 1);
          if ( !v56 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v25 = &v50;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  v53,
                  &v52,
                  &v51) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
            v18 = 0;
            goto LABEL_29;
          }
          if ( ++v16 >= v42 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
    v18 = 1;
LABEL_29:
    if ( !(_BYTE)v36 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v5, v33, (int)v34 - (int)v33, v17, (_DWORD)v25, v27[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v5, v33, v34 - v33, v20, (_DWORD)v25, 0, 0);
LABEL_37:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v39 = v38;
      goto LABEL_38;
    }
    ++v7;
    v18 = 0;
LABEL_38:
    v21 = lpMem;
    lpMem = 0;
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
    if ( v18 || v5 >= v6 || v7 >= 0x32 )
      return;
  }
  v23 = lpMem;
  lpMem = 0;
  if ( v23 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v23);
  }
}

```

## disassembly

```asm
0x18002cf80  mov     [rsp-8+arg_8], rbx
0x18002cf85  push    rbp
0x18002cf86  push    rsi
0x18002cf87  push    rdi
0x18002cf88  push    r12
0x18002cf8a  push    r13
0x18002cf8c  push    r14
0x18002cf8e  push    r15
0x18002cf90  lea     rbp, [rsp-10A0h]
0x18002cf98  mov     eax, 11A0h
0x18002cf9d  call    _alloca_probe
0x18002cfa2  sub     rsp, rax
0x18002cfa5  mov     rax, cs:__security_cookie
0x18002cfac  xor     rax, rsp
0x18002cfaf  mov     [rbp+10D0h+var_40], rax
0x18002cfb6  mov     rbx, r8
0x18002cfb9  mov     r14, rcx
0x18002cfbc  lea     r12, [rcx+rdx*8]
0x18002cfc0  xor     r13d, r13d
0x18002cfc3  mov     r15d, r13d
0x18002cfc6  mov     [rbp+10D0h+var_1128], r13
0x18002cfca  mov     cl, [rbx+8]
0x18002cfcd  movzx   edx, word ptr [rbx+6]
0x18002cfd1  movzx   eax, word ptr [rbx]
0x18002cfd4  mov     [rsp+11D0h+var_1170], ax
0x18002cfd9  movzx   eax, word ptr [rbx+2]
0x18002cfdd  mov     [rsp+11D0h+var_116E], ax
0x18002cfe2  mov     al, [rbx+4]
0x18002cfe5  mov     [rsp+11D0h+var_116C], al
0x18002cfe9  mov     [rsp+11D0h+var_116A], dx
0x18002cfee  mov     [rsp+11D0h+var_1168], cl
0x18002cff2  test    dx, dx
0x18002cff5  jz      short loc_18002D014
0x18002cff7  mov     eax, edx
0x18002cff9  cmp     cl, 1
0x18002cffc  jnz     short loc_18002D004
0x18002cffe  add     rax, 2
0x18002d002  jmp     short loc_18002D00D
0x18002d004  cmp     cl, 2
0x18002d007  jnz     short loc_18002D00D
0x18002d009  add     rax, 4
0x18002d00d  mov     [rsp+11D0h+var_1160], rax
0x18002d012  jmp     short loc_18002D019
0x18002d014  mov     [rsp+11D0h+var_1160], r13
0x18002d019  mov     [rsp+11D0h+var_1158], r13
0x18002d01e  xorps   xmm0, xmm0
0x18002d021  movdqa  [rbp+10D0h+var_1150], xmm0
0x18002d026  mov     [rbp+10D0h+lpMem], r13
0x18002d02a  mov     [rbp+10D0h+var_1138], r13w
0x18002d02f  mov     [rbp+10D0h+var_1136], r13b
0x18002d033  mov     [rsp+11D0h+var_1188], r13d
0x18002d038  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18002d040  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18002d047  test    rax, rax
0x18002d04a  jnz     short loc_18002D08F
0x18002d04c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002d053  test    rax, rax
0x18002d056  jnz     short loc_18002D06C
0x18002d058  lea     rcx, ModuleName; "ntdll.dll"
0x18002d05f  call    cs:__imp_GetModuleHandleW
0x18002d065  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002d06c  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18002d073  mov     rcx, rax; hModule
0x18002d076  call    cs:__imp_GetProcAddress
0x18002d07c  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18002d083  test    rax, rax
0x18002d086  jnz     short loc_18002D08F
0x18002d088  mov     edi, 0C0000139h
0x18002d08d  jmp     short loc_18002D0B9
0x18002d08f  lea     rcx, [rsp+11D0h+var_1190]
0x18002d094  mov     [rsp+11D0h+var_11A8], rcx
0x18002d099  lea     rcx, [rbp+10D0h+var_1040]
0x18002d0a0  mov     [rsp+11D0h+var_11B0], rcx
0x18002d0a5  lea     r9, [rsp+11D0h+var_1188]
0x18002d0aa  xor     r8d, r8d
0x18002d0ad  xor     edx, edx
0x18002d0af  mov     rcx, r14
0x18002d0b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d0b7  mov     edi, eax
0x18002d0b9  mov     ecx, edi; this
0x18002d0bb  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18002d0c0  test    edi, edi
0x18002d0c2  jz      short loc_18002D0D2
0x18002d0c4  mov     eax, r13d
0x18002d0c7  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18002d0cb  mov     [rsp+11D0h+var_1188], r13d
0x18002d0d0  jmp     short loc_18002D0D6
0x18002d0d2  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18002d0d6  mov     r8d, eax; unsigned __int64
0x18002d0d9  mov     r9d, 1000h; unsigned __int64
0x18002d0df  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18002d0e6  lea     rcx, [rsp+11D0h+var_1170]; this
0x18002d0eb  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18002d0f0  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18002d0f4  jnz     loc_18002D306
0x18002d0fa  mov     [rbp+10D0h+var_1130], r13
0x18002d0fe  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18002d105  mov     [rbp+10D0h+var_10B0], rax
0x18002d109  lea     rax, [rbp+10D0h+var_1130]
0x18002d10d  mov     [rbp+10D0h+var_10A8], rax
0x18002d111  lea     rax, [rbp+10D0h+var_1128]
0x18002d115  mov     [rbp+10D0h+var_10A0], rax
0x18002d119  lea     rax, [rsp+11D0h+var_1170]
0x18002d11e  mov     [rbp+10D0h+var_1098], rax
0x18002d122  lea     rax, [rbp+10D0h+var_10B0]
0x18002d126  mov     [rbp+10D0h+var_1048], rax
0x18002d12d  lea     rax, [rbp+10D0h+var_10B8]
0x18002d131  mov     [rbp+10D0h+var_10C0], rax
0x18002d135  mov     rax, [rbx+18h]
0x18002d139  add     rax, 0Ah
0x18002d13d  mov     [rsp+11D0h+var_1190], rax
0x18002d142  movzx   eax, word ptr [rbx+2]
0x18002d146  mov     [rbp+10D0h+var_1120], ax
0x18002d14a  mov     al, [rbx+4]
0x18002d14d  mov     [rbp+10D0h+var_111E], al
0x18002d150  mov     [rbp+10D0h+var_111C], r13d
0x18002d154  mov     [rbp+10D0h+var_1118], r13w
0x18002d159  xorps   xmm0, xmm0
0x18002d15c  movdqu  [rbp+10D0h+var_1110], xmm0
0x18002d161  movzx   eax, word ptr [rbx+6]
0x18002d165  mov     [rbp+10D0h+var_1100], ax
0x18002d169  mov     al, [rbx+8]
0x18002d16c  mov     [rbp+10D0h+var_10FE], al
0x18002d16f  mov     [rbp+10D0h+var_10FC], r13d
0x18002d173  mov     [rbp+10D0h+var_10F8], r13w
0x18002d178  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18002d17d  jmp     loc_18002D216
0x18002d182  mov     edi, r13d
0x18002d185  cmp     [rbp+10D0h+var_111C], r13d
0x18002d189  jbe     loc_18002D216
0x18002d18f  mov     r8, [rbx+20h]; unsigned __int8 *
0x18002d193  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18002d198  lea     rcx, [rbp+10D0h+var_1100]; this
0x18002d19c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002d1a1  test    al, al
0x18002d1a3  jz      short loc_18002D216
0x18002d1a5  mov     eax, [rbp+10D0h+var_10FC]
0x18002d1a8  mov     [rsp+11D0h+var_1180], eax
0x18002d1ac  movzx   eax, [rbp+10D0h+var_10F8]
0x18002d1b0  mov     [rbp+10D0h+var_10E0], rax
0x18002d1b4  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18002d1b8  mov     [rbp+10D0h+var_10D8], rax
0x18002d1bc  movzx   eax, [rbp+10D0h+var_1118]
0x18002d1c0  mov     [rbp+10D0h+var_10D0], rax
0x18002d1c4  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18002d1c8  mov     [rbp+10D0h+var_10C8], rax
0x18002d1cc  mov     rcx, [rbp+10D0h+var_1048]; this
0x18002d1d3  test    rcx, rcx
0x18002d1d6  jz      loc_18002D351
0x18002d1dc  mov     rax, [rcx]
0x18002d1df  lea     rdx, [rsp+11D0h+var_1180]
0x18002d1e4  mov     [rsp+11D0h+var_11A8], rdx
0x18002d1e9  lea     rdx, [rbp+10D0h+var_10E0]
0x18002d1ed  mov     [rsp+11D0h+var_11B0], rdx
0x18002d1f2  lea     r9, [rbp+10D0h+var_10D8]
0x18002d1f6  lea     r8, [rbp+10D0h+var_10D0]
0x18002d1fa  lea     rdx, [rbp+10D0h+var_10C8]
0x18002d1fe  mov     rax, [rax+20h]
0x18002d202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d207  test    al, al
0x18002d209  jz      short loc_18002D284
0x18002d20b  inc     edi
0x18002d20d  cmp     edi, [rbp+10D0h+var_111C]
0x18002d210  jb      loc_18002D18F
0x18002d216  mov     r8, [rbx+20h]; unsigned __int8 *
0x18002d21a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18002d21f  lea     rcx, [rbp+10D0h+var_1120]; this
0x18002d223  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18002d228  test    al, al
0x18002d22a  jnz     loc_18002D182
0x18002d230  mov     rcx, [rbp+10D0h+var_1048]
0x18002d237  test    rcx, rcx
0x18002d23a  jz      short loc_18002D248
0x18002d23c  mov     rax, [rcx]
0x18002d23f  mov     rax, [rax+18h]
0x18002d243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d248  mov     dil, 1
0x18002d24b  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18002d24f  jz      short loc_18002D2C3
0x18002d251  mov     eax, [rsp+11D0h+var_1188]
0x18002d255  mov     rdx, [rsp+11D0h+var_1158]
0x18002d25a  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18002d25e  sub     r8d, edx
0x18002d261  mov     [rsp+11D0h+var_11A0], 1
0x18002d269  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18002d26d  mov     rcx, r14
0x18002d270  call    wil_details_NtUpdateWnfStateData
0x18002d275  cmp     eax, 0C0000001h
0x18002d27a  jnz     short loc_18002D2A1
0x18002d27c  inc     r15
0x18002d27f  mov     dil, r13b
0x18002d282  jmp     short loc_18002D2CF
0x18002d284  mov     rcx, [rbp+10D0h+var_1048]
0x18002d28b  test    rcx, rcx
0x18002d28e  jz      short loc_18002D29C
0x18002d290  mov     rax, [rcx]
0x18002d293  mov     rax, [rax+18h]
0x18002d297  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002d29c  mov     dil, r13b
0x18002d29f  jmp     short loc_18002D24B
0x18002d2a1  test    eax, eax
0x18002d2a3  jz      short loc_18002D2C3
0x18002d2a5  mov     rdx, [rsp+11D0h+var_1158]
0x18002d2aa  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18002d2ae  sub     r8d, edx
0x18002d2b1  mov     [rsp+11D0h+var_11A0], r13d
0x18002d2b6  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18002d2bb  mov     rcx, r14
0x18002d2be  call    wil_details_NtUpdateWnfStateData
0x18002d2c3  add     r14, 8
0x18002d2c7  mov     rax, [rbp+10D0h+var_1130]
0x18002d2cb  mov     [rbp+10D0h+var_1128], rax
0x18002d2cf  mov     rsi, [rbp+10D0h+lpMem]
0x18002d2d3  mov     [rbp+10D0h+lpMem], r13
0x18002d2d7  test    rsi, rsi
0x18002d2da  jz      short loc_18002D2F0
0x18002d2dc  call    cs:__imp_GetProcessHeap
0x18002d2e2  mov     rcx, rax; hHeap
0x18002d2e5  mov     r8, rsi; lpMem
0x18002d2e8  xor     edx, edx; dwFlags
0x18002d2ea  call    cs:__imp_HeapFree
0x18002d2f0  test    dil, dil
0x18002d2f3  jnz     short loc_18002D327
0x18002d2f5  cmp     r14, r12
0x18002d2f8  jnb     short loc_18002D327
0x18002d2fa  cmp     r15, 32h ; '2'
0x18002d2fe  jb      loc_18002CFCA
0x18002d304  jmp     short loc_18002D327
0x18002d306  mov     rbx, [rbp+10D0h+lpMem]
0x18002d30a  mov     [rbp+10D0h+lpMem], r13
0x18002d30e  test    rbx, rbx
0x18002d311  jz      short loc_18002D327
0x18002d313  call    cs:__imp_GetProcessHeap
0x18002d319  mov     rcx, rax; hHeap
0x18002d31c  mov     r8, rbx; lpMem
0x18002d31f  xor     edx, edx; dwFlags
0x18002d321  call    cs:__imp_HeapFree
0x18002d327  mov     rcx, [rbp+10D0h+var_40]
0x18002d32e  xor     rcx, rsp; StackCookie
0x18002d331  call    __security_check_cookie
0x18002d336  mov     rbx, [rsp+11D0h+arg_8]
0x18002d33e  add     rsp, 11A0h
0x18002d345  pop     r15
0x18002d347  pop     r14
0x18002d349  pop     r13
0x18002d34b  pop     r12
0x18002d34d  pop     rdi
0x18002d34e  pop     rsi
0x18002d34f  pop     rbp
0x18002d350  retn
0x18002d351  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
