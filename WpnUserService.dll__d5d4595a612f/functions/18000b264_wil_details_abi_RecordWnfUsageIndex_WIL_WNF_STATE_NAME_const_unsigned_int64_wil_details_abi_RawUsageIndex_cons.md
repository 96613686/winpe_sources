# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000b264`
- end: `0x18000b63c`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a9ac`

## callees

- `0x180002bc0`
- `0x180007198`
- `0x180009be4`
- `0x18000a8ac`
- `0x18000b264`
- `0x18000c12c`
- `0x18000d3e0`
- `0x180010ba0`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b344`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b344`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b35b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b35b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b606`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b5d0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b606`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5f8`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5c2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b5f8`

## string_xrefs

- `0x18000b33d`: `ntdll.dll`

## pseudocode

```c
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
  int v19; // r9d
  char v20; // bl
  int updated; // eax
  int v22; // r9d
  void *v23; // rsi
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 *v27; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v28; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v29[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v5, 0, 0, v29);
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
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v5, v35, (int)v36 - (int)v35, v19, (_DWORD)v27, v29[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v5, v35, v36 - v35, v22, (_DWORD)v27, 0, 0);
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
0x18000b264  mov     [rsp-8+arg_8], rbx
0x18000b269  push    rbp
0x18000b26a  push    rsi
0x18000b26b  push    rdi
0x18000b26c  push    r12
0x18000b26e  push    r13
0x18000b270  push    r14
0x18000b272  push    r15
0x18000b274  lea     rbp, [rsp-10A0h]
0x18000b27c  mov     eax, 11A0h
0x18000b281  call    _alloca_probe
0x18000b286  sub     rsp, rax
0x18000b289  mov     rax, cs:__security_cookie
0x18000b290  xor     rax, rsp
0x18000b293  mov     [rbp+10D0h+var_40], rax
0x18000b29a  mov     rdi, r8
0x18000b29d  mov     r14, rcx
0x18000b2a0  lea     r13, [rcx+rdx*8]
0x18000b2a4  xor     r15d, r15d
0x18000b2a7  mov     r12d, r15d
0x18000b2aa  mov     [rbp+10D0h+var_1128], r15
0x18000b2ae  mov     cl, [rdi+8]
0x18000b2b1  movzx   edx, word ptr [rdi+6]
0x18000b2b5  movzx   eax, word ptr [rdi]
0x18000b2b8  mov     [rsp+11D0h+var_1170], ax
0x18000b2bd  movzx   eax, word ptr [rdi+2]
0x18000b2c1  mov     [rsp+11D0h+var_116E], ax
0x18000b2c6  mov     al, [rdi+4]
0x18000b2c9  mov     [rsp+11D0h+var_116C], al
0x18000b2cd  mov     [rsp+11D0h+var_116A], dx
0x18000b2d2  mov     [rsp+11D0h+var_1168], cl
0x18000b2d6  test    dx, dx
0x18000b2d9  jz      short loc_18000B2F8
0x18000b2db  mov     eax, edx
0x18000b2dd  cmp     cl, 1
0x18000b2e0  jnz     short loc_18000B2E8
0x18000b2e2  add     rax, 2
0x18000b2e6  jmp     short loc_18000B2F1
0x18000b2e8  cmp     cl, 2
0x18000b2eb  jnz     short loc_18000B2F1
0x18000b2ed  add     rax, 4
0x18000b2f1  mov     [rsp+11D0h+var_1160], rax
0x18000b2f6  jmp     short loc_18000B2FD
0x18000b2f8  mov     [rsp+11D0h+var_1160], r15
0x18000b2fd  mov     [rsp+11D0h+var_1158], r15
0x18000b302  xorps   xmm0, xmm0
0x18000b305  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000b30a  mov     [rbp+10D0h+lpMem], r15
0x18000b30e  mov     [rbp+10D0h+var_1138], 0
0x18000b314  mov     [rbp+10D0h+var_1136], r15b
0x18000b318  mov     [rsp+11D0h+var_1188], r15d
0x18000b31d  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000b325  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b32c  test    rax, rax
0x18000b32f  jnz     short loc_18000B374
0x18000b331  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b338  test    rax, rax
0x18000b33b  jnz     short loc_18000B351
0x18000b33d  lea     rcx, ModuleName; "ntdll.dll"
0x18000b344  call    cs:__imp_GetModuleHandleW
0x18000b34a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b351  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b358  mov     rcx, rax; hModule
0x18000b35b  call    cs:__imp_GetProcAddress
0x18000b361  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b368  test    rax, rax
0x18000b36b  jnz     short loc_18000B374
0x18000b36d  mov     ebx, 0C0000139h
0x18000b372  jmp     short loc_18000B39E
0x18000b374  lea     rcx, [rsp+11D0h+var_1190]
0x18000b379  mov     [rsp+11D0h+var_11A8], rcx
0x18000b37e  lea     rcx, [rbp+10D0h+var_1040]
0x18000b385  mov     [rsp+11D0h+var_11B0], rcx
0x18000b38a  lea     r9, [rsp+11D0h+var_1188]
0x18000b38f  xor     r8d, r8d
0x18000b392  xor     edx, edx
0x18000b394  mov     rcx, r14
0x18000b397  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b39c  mov     ebx, eax
0x18000b39e  mov     ecx, ebx; this
0x18000b3a0  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000b3a5  test    ebx, ebx
0x18000b3a7  jz      short loc_18000B3B7
0x18000b3a9  mov     eax, r15d
0x18000b3ac  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000b3b0  mov     [rsp+11D0h+var_1188], r15d
0x18000b3b5  jmp     short loc_18000B3BB
0x18000b3b7  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000b3bb  mov     r8d, eax; unsigned __int64
0x18000b3be  mov     r9d, 1000h; unsigned __int64
0x18000b3c4  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000b3cb  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000b3d0  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000b3d5  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000b3d9  jnz     loc_18000B5EB
0x18000b3df  mov     [rbp+10D0h+var_1130], r15
0x18000b3e3  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000b3ea  mov     [rbp+10D0h+var_10B0], rax
0x18000b3ee  lea     rax, [rbp+10D0h+var_1130]
0x18000b3f2  mov     [rbp+10D0h+var_10A8], rax
0x18000b3f6  lea     rax, [rbp+10D0h+var_1128]
0x18000b3fa  mov     [rbp+10D0h+var_10A0], rax
0x18000b3fe  lea     rax, [rsp+11D0h+var_1170]
0x18000b403  mov     [rbp+10D0h+var_1098], rax
0x18000b407  lea     rax, [rbp+10D0h+var_10B0]
0x18000b40b  mov     [rbp+10D0h+var_1048], rax
0x18000b412  lea     rax, [rbp+10D0h+var_10B8]
0x18000b416  mov     [rbp+10D0h+var_10C0], rax
0x18000b41a  mov     rax, [rdi+18h]
0x18000b41e  add     rax, 0Ah
0x18000b422  mov     [rsp+11D0h+var_1190], rax
0x18000b427  movzx   eax, word ptr [rdi+2]
0x18000b42b  mov     [rbp+10D0h+var_1120], ax
0x18000b42f  mov     al, [rdi+4]
0x18000b432  mov     [rbp+10D0h+var_111E], al
0x18000b435  mov     [rbp+10D0h+var_111C], r15d
0x18000b439  mov     [rbp+10D0h+var_1118], r15w
0x18000b43e  xorps   xmm0, xmm0
0x18000b441  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000b446  movzx   eax, word ptr [rdi+6]
0x18000b44a  mov     [rbp+10D0h+var_1100], ax
0x18000b44e  mov     al, [rdi+8]
0x18000b451  mov     [rbp+10D0h+var_10FE], al
0x18000b454  mov     [rbp+10D0h+var_10FC], r15d
0x18000b458  mov     [rbp+10D0h+var_10F8], r15w
0x18000b45d  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000b462  jmp     loc_18000B4FA
0x18000b467  mov     ebx, r15d
0x18000b46a  mov     esi, [rbp+10D0h+var_111C]
0x18000b46d  test    esi, esi
0x18000b46f  jz      loc_18000B4FA
0x18000b475  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000b479  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b47d  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b482  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000b486  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b48b  test    al, al
0x18000b48d  jz      short loc_18000B4F7
0x18000b48f  mov     eax, [rbp+10D0h+var_10FC]
0x18000b492  mov     [rsp+11D0h+var_1180], eax
0x18000b496  movzx   eax, [rbp+10D0h+var_10F8]
0x18000b49a  mov     [rbp+10D0h+var_10E0], rax
0x18000b49e  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000b4a2  mov     [rbp+10D0h+var_10D8], rax
0x18000b4a6  movzx   eax, [rbp+10D0h+var_1118]
0x18000b4aa  mov     [rbp+10D0h+var_10D0], rax
0x18000b4ae  mov     [rbp+10D0h+var_10C8], r15
0x18000b4b2  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000b4b9  test    rcx, rcx
0x18000b4bc  jz      loc_18000B636
0x18000b4c2  mov     rax, [rcx]
0x18000b4c5  lea     rdx, [rsp+11D0h+var_1180]
0x18000b4ca  mov     [rsp+11D0h+var_11A8], rdx
0x18000b4cf  lea     rdx, [rbp+10D0h+var_10E0]
0x18000b4d3  mov     [rsp+11D0h+var_11B0], rdx
0x18000b4d8  lea     r9, [rbp+10D0h+var_10D8]
0x18000b4dc  lea     r8, [rbp+10D0h+var_10D0]
0x18000b4e0  lea     rdx, [rbp+10D0h+var_10C8]
0x18000b4e4  mov     rax, [rax+20h]
0x18000b4e8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b4ed  test    al, al
0x18000b4ef  jz      short loc_18000B567
0x18000b4f1  inc     ebx
0x18000b4f3  cmp     ebx, esi
0x18000b4f5  jb      short loc_18000B479
0x18000b4f7  xor     r15d, r15d
0x18000b4fa  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b4fe  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b503  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000b507  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b50c  test    al, al
0x18000b50e  jnz     loc_18000B467
0x18000b514  mov     rcx, [rbp+10D0h+var_1048]
0x18000b51b  test    rcx, rcx
0x18000b51e  jz      short loc_18000B52C
0x18000b520  mov     rax, [rcx]
0x18000b523  mov     rax, [rax+18h]
0x18000b527  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b52c  mov     bl, 1
0x18000b52e  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000b532  jz      short loc_18000B5A9
0x18000b534  mov     eax, [rsp+11D0h+var_1188]
0x18000b538  mov     rdx, [rsp+11D0h+var_1158]
0x18000b53d  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b541  sub     r8d, edx
0x18000b544  mov     [rsp+11D0h+var_11A0], 1
0x18000b54c  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000b550  mov     rcx, r14
0x18000b553  call    wil_details_NtUpdateWnfStateData
0x18000b558  cmp     eax, 0C0000001h
0x18000b55d  jnz     short loc_18000B587
0x18000b55f  inc     r12
0x18000b562  mov     bl, r15b
0x18000b565  jmp     short loc_18000B5B5
0x18000b567  mov     rcx, [rbp+10D0h+var_1048]
0x18000b56e  xor     r15d, r15d
0x18000b571  test    rcx, rcx
0x18000b574  jz      short loc_18000B582
0x18000b576  mov     rax, [rcx]
0x18000b579  mov     rax, [rax+18h]
0x18000b57d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b582  mov     bl, r15b
0x18000b585  jmp     short loc_18000B52E
0x18000b587  test    eax, eax
0x18000b589  jz      short loc_18000B5A9
0x18000b58b  mov     rdx, [rsp+11D0h+var_1158]
0x18000b590  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b594  sub     r8d, edx
0x18000b597  mov     [rsp+11D0h+var_11A0], r15d
0x18000b59c  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000b5a1  mov     rcx, r14
0x18000b5a4  call    wil_details_NtUpdateWnfStateData
0x18000b5a9  add     r14, 8
0x18000b5ad  mov     rax, [rbp+10D0h+var_1130]
0x18000b5b1  mov     [rbp+10D0h+var_1128], rax
0x18000b5b5  mov     rsi, [rbp+10D0h+lpMem]
0x18000b5b9  mov     [rbp+10D0h+lpMem], r15
0x18000b5bd  test    rsi, rsi
0x18000b5c0  jz      short loc_18000B5D6
0x18000b5c2  call    cs:__imp_GetProcessHeap
0x18000b5c8  mov     rcx, rax; hHeap
0x18000b5cb  mov     r8, rsi; lpMem
0x18000b5ce  xor     edx, edx; dwFlags
0x18000b5d0  call    cs:__imp_HeapFree
0x18000b5d6  test    bl, bl
0x18000b5d8  jnz     short loc_18000B60C
0x18000b5da  cmp     r14, r13
0x18000b5dd  jnb     short loc_18000B60C
0x18000b5df  cmp     r12, 32h ; '2'
0x18000b5e3  jb      loc_18000B2AE
0x18000b5e9  jmp     short loc_18000B60C
0x18000b5eb  mov     rbx, [rbp+10D0h+lpMem]
0x18000b5ef  mov     [rbp+10D0h+lpMem], r15
0x18000b5f3  test    rbx, rbx
0x18000b5f6  jz      short loc_18000B60C
0x18000b5f8  call    cs:__imp_GetProcessHeap
0x18000b5fe  mov     rcx, rax; hHeap
0x18000b601  mov     r8, rbx; lpMem
0x18000b604  xor     edx, edx; dwFlags
0x18000b606  call    cs:__imp_HeapFree
0x18000b60c  mov     rcx, [rbp+10D0h+var_40]
0x18000b613  xor     rcx, rsp; StackCookie
0x18000b616  call    __security_check_cookie
0x18000b61b  mov     rbx, [rsp+11D0h+arg_8]
0x18000b623  add     rsp, 11A0h
0x18000b62a  pop     r15
0x18000b62c  pop     r14
0x18000b62e  pop     r13
0x18000b630  pop     r12
0x18000b632  pop     rdi
0x18000b633  pop     rsi
0x18000b634  pop     rbp
0x18000b635  retn
0x18000b636  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
