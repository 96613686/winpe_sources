# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000d7f0`
- end: `0x18000dbc7`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000cf90`

## callees

- `0x1800057d4`
- `0x18000c984`
- `0x18000cea0`
- `0x18000d7f0`
- `0x18000df3c`
- `0x18000edbc`
- `0x180011460`
- `0x180011520`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d8e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000d8e6`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d8cf`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000d8cf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db83`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db4c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000db83`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db91`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db5a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000db91`

## string_xrefs

- `0x18000d8c8`: `ntdll.dll`

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
0x18000d7f0  mov     [rsp-8+arg_8], rbx
0x18000d7f5  push    rbp
0x18000d7f6  push    rsi
0x18000d7f7  push    rdi
0x18000d7f8  push    r12
0x18000d7fa  push    r13
0x18000d7fc  push    r14
0x18000d7fe  push    r15
0x18000d800  lea     rbp, [rsp-10A0h]
0x18000d808  mov     eax, 11A0h
0x18000d80d  call    _alloca_probe
0x18000d812  sub     rsp, rax
0x18000d815  mov     rax, cs:__security_cookie
0x18000d81c  xor     rax, rsp
0x18000d81f  mov     [rbp+10D0h+var_40], rax
0x18000d826  mov     rbx, r8
0x18000d829  mov     r14, rcx
0x18000d82c  lea     r12, [rcx+rdx*8]
0x18000d830  xor     r13d, r13d
0x18000d833  mov     r15d, r13d
0x18000d836  mov     [rbp+10D0h+var_1128], r13
0x18000d83a  mov     cl, [rbx+8]
0x18000d83d  movzx   edx, word ptr [rbx+6]
0x18000d841  movzx   eax, word ptr [rbx]
0x18000d844  mov     [rsp+11D0h+var_1170], ax
0x18000d849  movzx   eax, word ptr [rbx+2]
0x18000d84d  mov     [rsp+11D0h+var_116E], ax
0x18000d852  mov     al, [rbx+4]
0x18000d855  mov     [rsp+11D0h+var_116C], al
0x18000d859  mov     [rsp+11D0h+var_116A], dx
0x18000d85e  mov     [rsp+11D0h+var_1168], cl
0x18000d862  test    dx, dx
0x18000d865  jz      short loc_18000D884
0x18000d867  mov     eax, edx
0x18000d869  cmp     cl, 1
0x18000d86c  jnz     short loc_18000D874
0x18000d86e  add     rax, 2
0x18000d872  jmp     short loc_18000D87D
0x18000d874  cmp     cl, 2
0x18000d877  jnz     short loc_18000D87D
0x18000d879  add     rax, 4
0x18000d87d  mov     [rsp+11D0h+var_1160], rax
0x18000d882  jmp     short loc_18000D889
0x18000d884  mov     [rsp+11D0h+var_1160], r13
0x18000d889  mov     [rsp+11D0h+var_1158], r13
0x18000d88e  xorps   xmm0, xmm0
0x18000d891  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000d896  mov     [rbp+10D0h+lpMem], r13
0x18000d89a  mov     [rbp+10D0h+var_1138], r13w
0x18000d89f  mov     [rbp+10D0h+var_1136], r13b
0x18000d8a3  mov     [rsp+11D0h+var_1188], r13d
0x18000d8a8  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000d8b0  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000d8b7  test    rax, rax
0x18000d8ba  jnz     short loc_18000D8FF
0x18000d8bc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d8c3  test    rax, rax
0x18000d8c6  jnz     short loc_18000D8DC
0x18000d8c8  lea     rcx, ModuleName; "ntdll.dll"
0x18000d8cf  call    cs:__imp_GetModuleHandleW
0x18000d8d5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d8dc  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000d8e3  mov     rcx, rax; hModule
0x18000d8e6  call    cs:__imp_GetProcAddress
0x18000d8ec  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000d8f3  test    rax, rax
0x18000d8f6  jnz     short loc_18000D8FF
0x18000d8f8  mov     edi, 0C0000139h
0x18000d8fd  jmp     short loc_18000D929
0x18000d8ff  lea     rcx, [rsp+11D0h+var_1190]
0x18000d904  mov     [rsp+11D0h+var_11A8], rcx
0x18000d909  lea     rcx, [rbp+10D0h+var_1040]
0x18000d910  mov     [rsp+11D0h+var_11B0], rcx
0x18000d915  lea     r9, [rsp+11D0h+var_1188]
0x18000d91a  xor     r8d, r8d
0x18000d91d  xor     edx, edx
0x18000d91f  mov     rcx, r14
0x18000d922  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d927  mov     edi, eax
0x18000d929  mov     ecx, edi; this
0x18000d92b  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000d930  test    edi, edi
0x18000d932  jz      short loc_18000D942
0x18000d934  mov     eax, r13d
0x18000d937  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000d93b  mov     [rsp+11D0h+var_1188], r13d
0x18000d940  jmp     short loc_18000D946
0x18000d942  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000d946  mov     r8d, eax; unsigned __int64
0x18000d949  mov     r9d, 1000h; unsigned __int64
0x18000d94f  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000d956  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000d95b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000d960  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18000d964  jnz     loc_18000DB76
0x18000d96a  mov     [rbp+10D0h+var_1130], r13
0x18000d96e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000d975  mov     [rbp+10D0h+var_10B0], rax
0x18000d979  lea     rax, [rbp+10D0h+var_1130]
0x18000d97d  mov     [rbp+10D0h+var_10A8], rax
0x18000d981  lea     rax, [rbp+10D0h+var_1128]
0x18000d985  mov     [rbp+10D0h+var_10A0], rax
0x18000d989  lea     rax, [rsp+11D0h+var_1170]
0x18000d98e  mov     [rbp+10D0h+var_1098], rax
0x18000d992  lea     rax, [rbp+10D0h+var_10B0]
0x18000d996  mov     [rbp+10D0h+var_1048], rax
0x18000d99d  lea     rax, [rbp+10D0h+var_10B8]
0x18000d9a1  mov     [rbp+10D0h+var_10C0], rax
0x18000d9a5  mov     rax, [rbx+18h]
0x18000d9a9  add     rax, 0Ah
0x18000d9ad  mov     [rsp+11D0h+var_1190], rax
0x18000d9b2  movzx   eax, word ptr [rbx+2]
0x18000d9b6  mov     [rbp+10D0h+var_1120], ax
0x18000d9ba  mov     al, [rbx+4]
0x18000d9bd  mov     [rbp+10D0h+var_111E], al
0x18000d9c0  mov     [rbp+10D0h+var_111C], r13d
0x18000d9c4  mov     [rbp+10D0h+var_1118], r13w
0x18000d9c9  xorps   xmm0, xmm0
0x18000d9cc  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000d9d1  movzx   eax, word ptr [rbx+6]
0x18000d9d5  mov     [rbp+10D0h+var_1100], ax
0x18000d9d9  mov     al, [rbx+8]
0x18000d9dc  mov     [rbp+10D0h+var_10FE], al
0x18000d9df  mov     [rbp+10D0h+var_10FC], r13d
0x18000d9e3  mov     [rbp+10D0h+var_10F8], r13w
0x18000d9e8  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000d9ed  jmp     loc_18000DA86
0x18000d9f2  mov     edi, r13d
0x18000d9f5  cmp     [rbp+10D0h+var_111C], r13d
0x18000d9f9  jbe     loc_18000DA86
0x18000d9ff  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000da03  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000da08  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000da0c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000da11  test    al, al
0x18000da13  jz      short loc_18000DA86
0x18000da15  mov     eax, [rbp+10D0h+var_10FC]
0x18000da18  mov     [rsp+11D0h+var_1180], eax
0x18000da1c  movzx   eax, [rbp+10D0h+var_10F8]
0x18000da20  mov     [rbp+10D0h+var_10E0], rax
0x18000da24  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000da28  mov     [rbp+10D0h+var_10D8], rax
0x18000da2c  movzx   eax, [rbp+10D0h+var_1118]
0x18000da30  mov     [rbp+10D0h+var_10D0], rax
0x18000da34  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000da38  mov     [rbp+10D0h+var_10C8], rax
0x18000da3c  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000da43  test    rcx, rcx
0x18000da46  jz      loc_18000DBC1
0x18000da4c  mov     rax, [rcx]
0x18000da4f  lea     rdx, [rsp+11D0h+var_1180]
0x18000da54  mov     [rsp+11D0h+var_11A8], rdx
0x18000da59  lea     rdx, [rbp+10D0h+var_10E0]
0x18000da5d  mov     [rsp+11D0h+var_11B0], rdx
0x18000da62  lea     r9, [rbp+10D0h+var_10D8]
0x18000da66  lea     r8, [rbp+10D0h+var_10D0]
0x18000da6a  lea     rdx, [rbp+10D0h+var_10C8]
0x18000da6e  mov     rax, [rax+20h]
0x18000da72  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000da77  test    al, al
0x18000da79  jz      short loc_18000DAF4
0x18000da7b  inc     edi
0x18000da7d  cmp     edi, [rbp+10D0h+var_111C]
0x18000da80  jb      loc_18000D9FF
0x18000da86  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000da8a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000da8f  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000da93  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000da98  test    al, al
0x18000da9a  jnz     loc_18000D9F2
0x18000daa0  mov     rcx, [rbp+10D0h+var_1048]
0x18000daa7  test    rcx, rcx
0x18000daaa  jz      short loc_18000DAB8
0x18000daac  mov     rax, [rcx]
0x18000daaf  mov     rax, [rax+18h]
0x18000dab3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dab8  mov     dil, 1
0x18000dabb  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18000dabf  jz      short loc_18000DB33
0x18000dac1  mov     eax, [rsp+11D0h+var_1188]
0x18000dac5  mov     rdx, [rsp+11D0h+var_1158]
0x18000daca  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000dace  sub     r8d, edx
0x18000dad1  mov     [rsp+11D0h+var_11A0], 1
0x18000dad9  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000dadd  mov     rcx, r14
0x18000dae0  call    wil_details_NtUpdateWnfStateData
0x18000dae5  cmp     eax, 0C0000001h
0x18000daea  jnz     short loc_18000DB11
0x18000daec  inc     r15
0x18000daef  mov     dil, r13b
0x18000daf2  jmp     short loc_18000DB3F
0x18000daf4  mov     rcx, [rbp+10D0h+var_1048]
0x18000dafb  test    rcx, rcx
0x18000dafe  jz      short loc_18000DB0C
0x18000db00  mov     rax, [rcx]
0x18000db03  mov     rax, [rax+18h]
0x18000db07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000db0c  mov     dil, r13b
0x18000db0f  jmp     short loc_18000DABB
0x18000db11  test    eax, eax
0x18000db13  jz      short loc_18000DB33
0x18000db15  mov     rdx, [rsp+11D0h+var_1158]
0x18000db1a  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000db1e  sub     r8d, edx
0x18000db21  mov     [rsp+11D0h+var_11A0], r13d
0x18000db26  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000db2b  mov     rcx, r14
0x18000db2e  call    wil_details_NtUpdateWnfStateData
0x18000db33  add     r14, 8
0x18000db37  mov     rax, [rbp+10D0h+var_1130]
0x18000db3b  mov     [rbp+10D0h+var_1128], rax
0x18000db3f  mov     rsi, [rbp+10D0h+lpMem]
0x18000db43  mov     [rbp+10D0h+lpMem], r13
0x18000db47  test    rsi, rsi
0x18000db4a  jz      short loc_18000DB60
0x18000db4c  call    cs:__imp_GetProcessHeap
0x18000db52  mov     rcx, rax; hHeap
0x18000db55  mov     r8, rsi; lpMem
0x18000db58  xor     edx, edx; dwFlags
0x18000db5a  call    cs:__imp_HeapFree
0x18000db60  test    dil, dil
0x18000db63  jnz     short loc_18000DB97
0x18000db65  cmp     r14, r12
0x18000db68  jnb     short loc_18000DB97
0x18000db6a  cmp     r15, 32h ; '2'
0x18000db6e  jb      loc_18000D83A
0x18000db74  jmp     short loc_18000DB97
0x18000db76  mov     rbx, [rbp+10D0h+lpMem]
0x18000db7a  mov     [rbp+10D0h+lpMem], r13
0x18000db7e  test    rbx, rbx
0x18000db81  jz      short loc_18000DB97
0x18000db83  call    cs:__imp_GetProcessHeap
0x18000db89  mov     rcx, rax; hHeap
0x18000db8c  mov     r8, rbx; lpMem
0x18000db8f  xor     edx, edx; dwFlags
0x18000db91  call    cs:__imp_HeapFree
0x18000db97  mov     rcx, [rbp+10D0h+var_40]
0x18000db9e  xor     rcx, rsp; StackCookie
0x18000dba1  call    __security_check_cookie
0x18000dba6  mov     rbx, [rsp+11D0h+arg_8]
0x18000dbae  add     rsp, 11A0h
0x18000dbb5  pop     r15
0x18000dbb7  pop     r14
0x18000dbb9  pop     r13
0x18000dbbb  pop     r12
0x18000dbbd  pop     rdi
0x18000dbbe  pop     rsi
0x18000dbbf  pop     rbp
0x18000dbc0  retn
0x18000dbc1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
