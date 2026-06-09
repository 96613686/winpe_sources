# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18003b068`
- end: `0x18003b440`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18003a5b4`

## callees

- `0x180003a60`
- `0x18000986c`
- `0x180039c58`
- `0x18003a4b4`
- `0x18003b068`
- `0x18003b5e8`
- `0x18003cdf0`
- `0x18006b600`
- `0x18006f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b148`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18003b148`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b15f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18003b15f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b3c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b3fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b3c6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18003b3fc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b3d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b40a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b3d4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18003b40a`

## string_xrefs

- `0x18003b141`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v5; // r14
  wil::details_abi *v6; // r13
  unsigned __int64 v7; // r12
  char v8; // cl
  unsigned int v9; // edx
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // ebx
  unsigned int v15; // eax
  int v16; // ebx
  unsigned int v17; // esi
  __int64 v18; // r15
  __int64 v19; // r9
  char v20; // bl
  int updated; // eax
  __int64 v22; // r9
  void *v23; // rsi
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 *v27; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v30[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v31; // [rsp+64h] [rbp-9Ch]
  __int16 v32; // [rsp+66h] [rbp-9Ah]
  char v33; // [rsp+68h] [rbp-98h]
  __int64 v34; // [rsp+70h] [rbp-90h]
  __int64 v35; // [rsp+78h] [rbp-88h]
  __int128 v36; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v38; // [rsp+98h] [rbp-68h]
  char v39; // [rsp+9Ah] [rbp-66h]
  __int64 v40; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v41; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v42; // [rsp+B0h] [rbp-50h] BYREF
  char v43; // [rsp+B2h] [rbp-4Eh]
  unsigned int v44; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v45; // [rsp+B8h] [rbp-48h]
  __int128 v46; // [rsp+C0h] [rbp-40h]
  __int16 v47; // [rsp+D0h] [rbp-30h] BYREF
  char v48; // [rsp+D2h] [rbp-2Eh]
  int v49; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v50; // [rsp+D8h] [rbp-28h]
  __int128 v51; // [rsp+E0h] [rbp-20h]
  __int64 v52; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v53; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v54; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v55[2]; // [rsp+108h] [rbp+8h] BYREF
  char v56; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v57[13]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *v58; // [rsp+188h] [rbp+88h]
  _BYTE v59[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v41 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v30[0] = *(_WORD *)a3;
    v30[1] = *(_WORD *)(a3 + 2);
    v31 = *(_BYTE *)(a3 + 4);
    v32 = v9;
    v33 = v8;
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
      v34 = v10;
    }
    else
    {
      v34 = 0;
    }
    v35 = 0;
    v36 = 0;
    lpMem = 0;
    v38 = 0;
    v39 = 0;
    v29[0] = 0;
    LODWORD(v28) = 4096;
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    if ( g_wil_details_pfnNtQueryWnfStateData )
      goto LABEL_14;
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
      v27 = (__int64 *)v59;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v29);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v28) = 0;
      v29[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v28;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v30, v59, v15, 0x1000u);
    if ( HIBYTE(v38) )
      break;
    v40 = 0;
    v57[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v57[1] = &v40;
    v57[2] = &v41;
    v57[3] = v30;
    v58 = (wil::details::in1diag3 *)v57;
    v55[1] = &v56;
    v28 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v42 = *(_WORD *)(a3 + 2);
    v43 = *(_BYTE *)(a3 + 4);
    v44 = 0;
    v45 = 0;
    v46 = 0;
    v47 = *(_WORD *)(a3 + 6);
    v48 = *(_BYTE *)(a3 + 8);
    v49 = 0;
    v50 = 0;
    v51 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v42,
              &v28,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      v17 = v44;
      if ( v44 )
      {
        v18 = *((_QWORD *)&v46 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v47,
                  &v28,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v29[2] = v49;
          v52 = v50;
          v53 = *((_QWORD *)&v51 + 1);
          v54 = v45;
          v55[0] = v18;
          if ( !v58 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v27 = &v52;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v58 + 32LL))(
                  v58,
                  v55,
                  &v54,
                  &v53) )
          {
            if ( v58 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
            v20 = 0;
            goto LABEL_30;
          }
          if ( ++v16 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v58 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
    v20 = 1;
LABEL_30:
    if ( !(_BYTE)v38 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v35, (int)v36 - (int)v35, v19, (int)v27, v29[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v35, v36 - v35, v22, (int)v27, 0, 0);
LABEL_38:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v41 = v40;
      goto LABEL_39;
    }
    ++v7;
    v20 = 0;
LABEL_39:
    v23 = lpMem;
    lpMem = 0;
    if ( v23 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v23);
    }
    if ( v20 || v5 >= v6 || v7 >= 0x32 )
      return;
  }
  v25 = lpMem;
  lpMem = 0;
  if ( v25 )
  {
    v26 = GetProcessHeap();
    HeapFree(v26, 0, v25);
  }
}

```

## disassembly

```asm
0x18003b068  mov     [rsp-8+arg_8], rbx
0x18003b06d  push    rbp
0x18003b06e  push    rsi
0x18003b06f  push    rdi
0x18003b070  push    r12
0x18003b072  push    r13
0x18003b074  push    r14
0x18003b076  push    r15
0x18003b078  lea     rbp, [rsp-10A0h]
0x18003b080  mov     eax, 11A0h
0x18003b085  call    _alloca_probe
0x18003b08a  sub     rsp, rax
0x18003b08d  mov     rax, cs:__security_cookie
0x18003b094  xor     rax, rsp
0x18003b097  mov     [rbp+10D0h+var_40], rax
0x18003b09e  mov     rdi, r8
0x18003b0a1  mov     r14, rcx
0x18003b0a4  lea     r13, [rcx+rdx*8]
0x18003b0a8  xor     r15d, r15d
0x18003b0ab  mov     r12d, r15d
0x18003b0ae  mov     [rbp+10D0h+var_1128], r15
0x18003b0b2  mov     cl, [rdi+8]
0x18003b0b5  movzx   edx, word ptr [rdi+6]
0x18003b0b9  movzx   eax, word ptr [rdi]
0x18003b0bc  mov     [rsp+11D0h+var_1170], ax
0x18003b0c1  movzx   eax, word ptr [rdi+2]
0x18003b0c5  mov     [rsp+11D0h+var_116E], ax
0x18003b0ca  mov     al, [rdi+4]
0x18003b0cd  mov     [rsp+11D0h+var_116C], al
0x18003b0d1  mov     [rsp+11D0h+var_116A], dx
0x18003b0d6  mov     [rsp+11D0h+var_1168], cl
0x18003b0da  test    dx, dx
0x18003b0dd  jz      short loc_18003B0FC
0x18003b0df  mov     eax, edx
0x18003b0e1  cmp     cl, 1
0x18003b0e4  jnz     short loc_18003B0EC
0x18003b0e6  add     rax, 2
0x18003b0ea  jmp     short loc_18003B0F5
0x18003b0ec  cmp     cl, 2
0x18003b0ef  jnz     short loc_18003B0F5
0x18003b0f1  add     rax, 4
0x18003b0f5  mov     [rsp+11D0h+var_1160], rax
0x18003b0fa  jmp     short loc_18003B101
0x18003b0fc  mov     [rsp+11D0h+var_1160], r15
0x18003b101  mov     [rsp+11D0h+var_1158], r15
0x18003b106  xorps   xmm0, xmm0
0x18003b109  movdqa  [rbp+10D0h+var_1150], xmm0
0x18003b10e  mov     [rbp+10D0h+lpMem], r15
0x18003b112  mov     [rbp+10D0h+var_1138], 0
0x18003b118  mov     [rbp+10D0h+var_1136], r15b
0x18003b11c  mov     [rsp+11D0h+var_1188], r15d
0x18003b121  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18003b129  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18003b130  test    rax, rax
0x18003b133  jnz     short loc_18003B178
0x18003b135  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003b13c  test    rax, rax
0x18003b13f  jnz     short loc_18003B155
0x18003b141  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18003b148  call    cs:__imp_GetModuleHandleW
0x18003b14e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18003b155  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18003b15c  mov     rcx, rax; hModule
0x18003b15f  call    cs:__imp_GetProcAddress
0x18003b165  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18003b16c  test    rax, rax
0x18003b16f  jnz     short loc_18003B178
0x18003b171  mov     ebx, 0C0000139h
0x18003b176  jmp     short loc_18003B1A2
0x18003b178  lea     rcx, [rsp+11D0h+var_1190]
0x18003b17d  mov     [rsp+11D0h+var_11A8], rcx
0x18003b182  lea     rcx, [rbp+10D0h+var_1040]
0x18003b189  mov     [rsp+11D0h+var_11B0], rcx
0x18003b18e  lea     r9, [rsp+11D0h+var_1188]
0x18003b193  xor     r8d, r8d
0x18003b196  xor     edx, edx
0x18003b198  mov     rcx, r14
0x18003b19b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b1a0  mov     ebx, eax
0x18003b1a2  mov     ecx, ebx; this
0x18003b1a4  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18003b1a9  test    ebx, ebx
0x18003b1ab  jz      short loc_18003B1BB
0x18003b1ad  mov     eax, r15d
0x18003b1b0  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18003b1b4  mov     [rsp+11D0h+var_1188], r15d
0x18003b1b9  jmp     short loc_18003B1BF
0x18003b1bb  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18003b1bf  mov     r8d, eax; unsigned __int64
0x18003b1c2  mov     r9d, 1000h; unsigned __int64
0x18003b1c8  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18003b1cf  lea     rcx, [rsp+11D0h+var_1170]; this
0x18003b1d4  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18003b1d9  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18003b1dd  jnz     loc_18003B3EF
0x18003b1e3  mov     [rbp+10D0h+var_1130], r15
0x18003b1e7  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18003b1ee  mov     [rbp+10D0h+var_10B0], rax
0x18003b1f2  lea     rax, [rbp+10D0h+var_1130]
0x18003b1f6  mov     [rbp+10D0h+var_10A8], rax
0x18003b1fa  lea     rax, [rbp+10D0h+var_1128]
0x18003b1fe  mov     [rbp+10D0h+var_10A0], rax
0x18003b202  lea     rax, [rsp+11D0h+var_1170]
0x18003b207  mov     [rbp+10D0h+var_1098], rax
0x18003b20b  lea     rax, [rbp+10D0h+var_10B0]
0x18003b20f  mov     [rbp+10D0h+var_1048], rax
0x18003b216  lea     rax, [rbp+10D0h+var_10B8]
0x18003b21a  mov     [rbp+10D0h+var_10C0], rax
0x18003b21e  mov     rax, [rdi+18h]
0x18003b222  add     rax, 0Ah
0x18003b226  mov     [rsp+11D0h+var_1190], rax
0x18003b22b  movzx   eax, word ptr [rdi+2]
0x18003b22f  mov     [rbp+10D0h+var_1120], ax
0x18003b233  mov     al, [rdi+4]
0x18003b236  mov     [rbp+10D0h+var_111E], al
0x18003b239  mov     [rbp+10D0h+var_111C], r15d
0x18003b23d  mov     [rbp+10D0h+var_1118], r15w
0x18003b242  xorps   xmm0, xmm0
0x18003b245  movdqu  [rbp+10D0h+var_1110], xmm0
0x18003b24a  movzx   eax, word ptr [rdi+6]
0x18003b24e  mov     [rbp+10D0h+var_1100], ax
0x18003b252  mov     al, [rdi+8]
0x18003b255  mov     [rbp+10D0h+var_10FE], al
0x18003b258  mov     [rbp+10D0h+var_10FC], r15d
0x18003b25c  mov     [rbp+10D0h+var_10F8], r15w
0x18003b261  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18003b266  jmp     loc_18003B2FE
0x18003b26b  mov     ebx, r15d
0x18003b26e  mov     esi, [rbp+10D0h+var_111C]
0x18003b271  test    esi, esi
0x18003b273  jz      loc_18003B2FE
0x18003b279  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18003b27d  mov     r8, [rdi+20h]; unsigned __int8 *
0x18003b281  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18003b286  lea     rcx, [rbp+10D0h+var_1100]; this
0x18003b28a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18003b28f  test    al, al
0x18003b291  jz      short loc_18003B2FB
0x18003b293  mov     eax, [rbp+10D0h+var_10FC]
0x18003b296  mov     [rsp+11D0h+var_1180], eax
0x18003b29a  movzx   eax, [rbp+10D0h+var_10F8]
0x18003b29e  mov     [rbp+10D0h+var_10E0], rax
0x18003b2a2  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18003b2a6  mov     [rbp+10D0h+var_10D8], rax
0x18003b2aa  movzx   eax, [rbp+10D0h+var_1118]
0x18003b2ae  mov     [rbp+10D0h+var_10D0], rax
0x18003b2b2  mov     [rbp+10D0h+var_10C8], r15
0x18003b2b6  mov     rcx, [rbp+10D0h+var_1048]; this
0x18003b2bd  test    rcx, rcx
0x18003b2c0  jz      loc_18003B43A
0x18003b2c6  mov     rax, [rcx]
0x18003b2c9  lea     rdx, [rsp+11D0h+var_1180]
0x18003b2ce  mov     [rsp+11D0h+var_11A8], rdx
0x18003b2d3  lea     rdx, [rbp+10D0h+var_10E0]
0x18003b2d7  mov     [rsp+11D0h+var_11B0], rdx
0x18003b2dc  lea     r9, [rbp+10D0h+var_10D8]
0x18003b2e0  lea     r8, [rbp+10D0h+var_10D0]
0x18003b2e4  lea     rdx, [rbp+10D0h+var_10C8]
0x18003b2e8  mov     rax, [rax+20h]
0x18003b2ec  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b2f1  test    al, al
0x18003b2f3  jz      short loc_18003B36B
0x18003b2f5  inc     ebx
0x18003b2f7  cmp     ebx, esi
0x18003b2f9  jb      short loc_18003B27D
0x18003b2fb  xor     r15d, r15d
0x18003b2fe  mov     r8, [rdi+20h]; unsigned __int8 *
0x18003b302  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18003b307  lea     rcx, [rbp+10D0h+var_1120]; this
0x18003b30b  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18003b310  test    al, al
0x18003b312  jnz     loc_18003B26B
0x18003b318  mov     rcx, [rbp+10D0h+var_1048]
0x18003b31f  test    rcx, rcx
0x18003b322  jz      short loc_18003B330
0x18003b324  mov     rax, [rcx]
0x18003b327  mov     rax, [rax+18h]
0x18003b32b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b330  mov     bl, 1
0x18003b332  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18003b336  jz      short loc_18003B3AD
0x18003b338  mov     eax, [rsp+11D0h+var_1188]
0x18003b33c  mov     rdx, [rsp+11D0h+var_1158]
0x18003b341  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18003b345  sub     r8d, edx
0x18003b348  mov     [rsp+11D0h+var_11A0], 1
0x18003b350  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18003b354  mov     rcx, r14
0x18003b357  call    wil_details_NtUpdateWnfStateData
0x18003b35c  cmp     eax, 0C0000001h
0x18003b361  jnz     short loc_18003B38B
0x18003b363  inc     r12
0x18003b366  mov     bl, r15b
0x18003b369  jmp     short loc_18003B3B9
0x18003b36b  mov     rcx, [rbp+10D0h+var_1048]
0x18003b372  xor     r15d, r15d
0x18003b375  test    rcx, rcx
0x18003b378  jz      short loc_18003B386
0x18003b37a  mov     rax, [rcx]
0x18003b37d  mov     rax, [rax+18h]
0x18003b381  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18003b386  mov     bl, r15b
0x18003b389  jmp     short loc_18003B332
0x18003b38b  test    eax, eax
0x18003b38d  jz      short loc_18003B3AD
0x18003b38f  mov     rdx, [rsp+11D0h+var_1158]
0x18003b394  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18003b398  sub     r8d, edx
0x18003b39b  mov     [rsp+11D0h+var_11A0], r15d
0x18003b3a0  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18003b3a5  mov     rcx, r14
0x18003b3a8  call    wil_details_NtUpdateWnfStateData
0x18003b3ad  add     r14, 8
0x18003b3b1  mov     rax, [rbp+10D0h+var_1130]
0x18003b3b5  mov     [rbp+10D0h+var_1128], rax
0x18003b3b9  mov     rsi, [rbp+10D0h+lpMem]
0x18003b3bd  mov     [rbp+10D0h+lpMem], r15
0x18003b3c1  test    rsi, rsi
0x18003b3c4  jz      short loc_18003B3DA
0x18003b3c6  call    cs:__imp_GetProcessHeap
0x18003b3cc  mov     rcx, rax; hHeap
0x18003b3cf  mov     r8, rsi; lpMem
0x18003b3d2  xor     edx, edx; dwFlags
0x18003b3d4  call    cs:__imp_HeapFree
0x18003b3da  test    bl, bl
0x18003b3dc  jnz     short loc_18003B410
0x18003b3de  cmp     r14, r13
0x18003b3e1  jnb     short loc_18003B410
0x18003b3e3  cmp     r12, 32h ; '2'
0x18003b3e7  jb      loc_18003B0B2
0x18003b3ed  jmp     short loc_18003B410
0x18003b3ef  mov     rbx, [rbp+10D0h+lpMem]
0x18003b3f3  mov     [rbp+10D0h+lpMem], r15
0x18003b3f7  test    rbx, rbx
0x18003b3fa  jz      short loc_18003B410
0x18003b3fc  call    cs:__imp_GetProcessHeap
0x18003b402  mov     rcx, rax; hHeap
0x18003b405  mov     r8, rbx; lpMem
0x18003b408  xor     edx, edx; dwFlags
0x18003b40a  call    cs:__imp_HeapFree
0x18003b410  mov     rcx, [rbp+10D0h+var_40]
0x18003b417  xor     rcx, rsp; StackCookie
0x18003b41a  call    __security_check_cookie
0x18003b41f  mov     rbx, [rsp+11D0h+arg_8]
0x18003b427  add     rsp, 11A0h
0x18003b42e  pop     r15
0x18003b430  pop     r14
0x18003b432  pop     r13
0x18003b434  pop     r12
0x18003b436  pop     rdi
0x18003b437  pop     rsi
0x18003b438  pop     rbp
0x18003b439  retn
0x18003b43a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
