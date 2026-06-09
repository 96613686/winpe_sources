# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180009f90`
- end: `0x18000a367`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180009730`

## callees

- `0x18000669c`
- `0x180009354`
- `0x180009640`
- `0x180009f90`
- `0x18000a7e0`
- `0x18000b45c`
- `0x18000b640`
- `0x18000b700`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a086`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a086`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a06f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a06f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a323`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a2ec`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a323`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a331`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a2fa`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a331`

## string_xrefs

- `0x18000a068`: `ntdll.dll`

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
0x180009f90  mov     [rsp-8+arg_8], rbx
0x180009f95  push    rbp
0x180009f96  push    rsi
0x180009f97  push    rdi
0x180009f98  push    r12
0x180009f9a  push    r13
0x180009f9c  push    r14
0x180009f9e  push    r15
0x180009fa0  lea     rbp, [rsp-10A0h]
0x180009fa8  mov     eax, 11A0h
0x180009fad  call    _alloca_probe
0x180009fb2  sub     rsp, rax
0x180009fb5  mov     rax, cs:__security_cookie
0x180009fbc  xor     rax, rsp
0x180009fbf  mov     [rbp+10D0h+var_40], rax
0x180009fc6  mov     rbx, r8
0x180009fc9  mov     r14, rcx
0x180009fcc  lea     r12, [rcx+rdx*8]
0x180009fd0  xor     r13d, r13d
0x180009fd3  mov     r15d, r13d
0x180009fd6  mov     [rbp+10D0h+var_1128], r13
0x180009fda  mov     cl, [rbx+8]
0x180009fdd  movzx   edx, word ptr [rbx+6]
0x180009fe1  movzx   eax, word ptr [rbx]
0x180009fe4  mov     [rsp+11D0h+var_1170], ax
0x180009fe9  movzx   eax, word ptr [rbx+2]
0x180009fed  mov     [rsp+11D0h+var_116E], ax
0x180009ff2  mov     al, [rbx+4]
0x180009ff5  mov     [rsp+11D0h+var_116C], al
0x180009ff9  mov     [rsp+11D0h+var_116A], dx
0x180009ffe  mov     [rsp+11D0h+var_1168], cl
0x18000a002  test    dx, dx
0x18000a005  jz      short loc_18000A024
0x18000a007  mov     eax, edx
0x18000a009  cmp     cl, 1
0x18000a00c  jnz     short loc_18000A014
0x18000a00e  add     rax, 2
0x18000a012  jmp     short loc_18000A01D
0x18000a014  cmp     cl, 2
0x18000a017  jnz     short loc_18000A01D
0x18000a019  add     rax, 4
0x18000a01d  mov     [rsp+11D0h+var_1160], rax
0x18000a022  jmp     short loc_18000A029
0x18000a024  mov     [rsp+11D0h+var_1160], r13
0x18000a029  mov     [rsp+11D0h+var_1158], r13
0x18000a02e  xorps   xmm0, xmm0
0x18000a031  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000a036  mov     [rbp+10D0h+lpMem], r13
0x18000a03a  mov     [rbp+10D0h+var_1138], r13w
0x18000a03f  mov     [rbp+10D0h+var_1136], r13b
0x18000a043  mov     [rsp+11D0h+var_1188], r13d
0x18000a048  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000a050  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000a057  test    rax, rax
0x18000a05a  jnz     short loc_18000A09F
0x18000a05c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a063  test    rax, rax
0x18000a066  jnz     short loc_18000A07C
0x18000a068  lea     rcx, ModuleName; "ntdll.dll"
0x18000a06f  call    cs:__imp_GetModuleHandleW
0x18000a075  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a07c  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000a083  mov     rcx, rax; hModule
0x18000a086  call    cs:__imp_GetProcAddress
0x18000a08c  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000a093  test    rax, rax
0x18000a096  jnz     short loc_18000A09F
0x18000a098  mov     edi, 0C0000139h
0x18000a09d  jmp     short loc_18000A0C9
0x18000a09f  lea     rcx, [rsp+11D0h+var_1190]
0x18000a0a4  mov     [rsp+11D0h+var_11A8], rcx
0x18000a0a9  lea     rcx, [rbp+10D0h+var_1040]
0x18000a0b0  mov     [rsp+11D0h+var_11B0], rcx
0x18000a0b5  lea     r9, [rsp+11D0h+var_1188]
0x18000a0ba  xor     r8d, r8d
0x18000a0bd  xor     edx, edx
0x18000a0bf  mov     rcx, r14
0x18000a0c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a0c7  mov     edi, eax
0x18000a0c9  mov     ecx, edi; this
0x18000a0cb  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000a0d0  test    edi, edi
0x18000a0d2  jz      short loc_18000A0E2
0x18000a0d4  mov     eax, r13d
0x18000a0d7  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000a0db  mov     [rsp+11D0h+var_1188], r13d
0x18000a0e0  jmp     short loc_18000A0E6
0x18000a0e2  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000a0e6  mov     r8d, eax; unsigned __int64
0x18000a0e9  mov     r9d, 1000h; unsigned __int64
0x18000a0ef  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000a0f6  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000a0fb  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000a100  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18000a104  jnz     loc_18000A316
0x18000a10a  mov     [rbp+10D0h+var_1130], r13
0x18000a10e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000a115  mov     [rbp+10D0h+var_10B0], rax
0x18000a119  lea     rax, [rbp+10D0h+var_1130]
0x18000a11d  mov     [rbp+10D0h+var_10A8], rax
0x18000a121  lea     rax, [rbp+10D0h+var_1128]
0x18000a125  mov     [rbp+10D0h+var_10A0], rax
0x18000a129  lea     rax, [rsp+11D0h+var_1170]
0x18000a12e  mov     [rbp+10D0h+var_1098], rax
0x18000a132  lea     rax, [rbp+10D0h+var_10B0]
0x18000a136  mov     [rbp+10D0h+var_1048], rax
0x18000a13d  lea     rax, [rbp+10D0h+var_10B8]
0x18000a141  mov     [rbp+10D0h+var_10C0], rax
0x18000a145  mov     rax, [rbx+18h]
0x18000a149  add     rax, 0Ah
0x18000a14d  mov     [rsp+11D0h+var_1190], rax
0x18000a152  movzx   eax, word ptr [rbx+2]
0x18000a156  mov     [rbp+10D0h+var_1120], ax
0x18000a15a  mov     al, [rbx+4]
0x18000a15d  mov     [rbp+10D0h+var_111E], al
0x18000a160  mov     [rbp+10D0h+var_111C], r13d
0x18000a164  mov     [rbp+10D0h+var_1118], r13w
0x18000a169  xorps   xmm0, xmm0
0x18000a16c  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000a171  movzx   eax, word ptr [rbx+6]
0x18000a175  mov     [rbp+10D0h+var_1100], ax
0x18000a179  mov     al, [rbx+8]
0x18000a17c  mov     [rbp+10D0h+var_10FE], al
0x18000a17f  mov     [rbp+10D0h+var_10FC], r13d
0x18000a183  mov     [rbp+10D0h+var_10F8], r13w
0x18000a188  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000a18d  jmp     loc_18000A226
0x18000a192  mov     edi, r13d
0x18000a195  cmp     [rbp+10D0h+var_111C], r13d
0x18000a199  jbe     loc_18000A226
0x18000a19f  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000a1a3  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000a1a8  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000a1ac  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000a1b1  test    al, al
0x18000a1b3  jz      short loc_18000A226
0x18000a1b5  mov     eax, [rbp+10D0h+var_10FC]
0x18000a1b8  mov     [rsp+11D0h+var_1180], eax
0x18000a1bc  movzx   eax, [rbp+10D0h+var_10F8]
0x18000a1c0  mov     [rbp+10D0h+var_10E0], rax
0x18000a1c4  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000a1c8  mov     [rbp+10D0h+var_10D8], rax
0x18000a1cc  movzx   eax, [rbp+10D0h+var_1118]
0x18000a1d0  mov     [rbp+10D0h+var_10D0], rax
0x18000a1d4  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000a1d8  mov     [rbp+10D0h+var_10C8], rax
0x18000a1dc  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000a1e3  test    rcx, rcx
0x18000a1e6  jz      loc_18000A361
0x18000a1ec  mov     rax, [rcx]
0x18000a1ef  lea     rdx, [rsp+11D0h+var_1180]
0x18000a1f4  mov     [rsp+11D0h+var_11A8], rdx
0x18000a1f9  lea     rdx, [rbp+10D0h+var_10E0]
0x18000a1fd  mov     [rsp+11D0h+var_11B0], rdx
0x18000a202  lea     r9, [rbp+10D0h+var_10D8]
0x18000a206  lea     r8, [rbp+10D0h+var_10D0]
0x18000a20a  lea     rdx, [rbp+10D0h+var_10C8]
0x18000a20e  mov     rax, [rax+20h]
0x18000a212  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a217  test    al, al
0x18000a219  jz      short loc_18000A294
0x18000a21b  inc     edi
0x18000a21d  cmp     edi, [rbp+10D0h+var_111C]
0x18000a220  jb      loc_18000A19F
0x18000a226  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000a22a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000a22f  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000a233  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000a238  test    al, al
0x18000a23a  jnz     loc_18000A192
0x18000a240  mov     rcx, [rbp+10D0h+var_1048]
0x18000a247  test    rcx, rcx
0x18000a24a  jz      short loc_18000A258
0x18000a24c  mov     rax, [rcx]
0x18000a24f  mov     rax, [rax+18h]
0x18000a253  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a258  mov     dil, 1
0x18000a25b  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18000a25f  jz      short loc_18000A2D3
0x18000a261  mov     eax, [rsp+11D0h+var_1188]
0x18000a265  mov     rdx, [rsp+11D0h+var_1158]
0x18000a26a  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000a26e  sub     r8d, edx
0x18000a271  mov     [rsp+11D0h+var_11A0], 1
0x18000a279  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000a27d  mov     rcx, r14
0x18000a280  call    wil_details_NtUpdateWnfStateData
0x18000a285  cmp     eax, 0C0000001h
0x18000a28a  jnz     short loc_18000A2B1
0x18000a28c  inc     r15
0x18000a28f  mov     dil, r13b
0x18000a292  jmp     short loc_18000A2DF
0x18000a294  mov     rcx, [rbp+10D0h+var_1048]
0x18000a29b  test    rcx, rcx
0x18000a29e  jz      short loc_18000A2AC
0x18000a2a0  mov     rax, [rcx]
0x18000a2a3  mov     rax, [rax+18h]
0x18000a2a7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a2ac  mov     dil, r13b
0x18000a2af  jmp     short loc_18000A25B
0x18000a2b1  test    eax, eax
0x18000a2b3  jz      short loc_18000A2D3
0x18000a2b5  mov     rdx, [rsp+11D0h+var_1158]
0x18000a2ba  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000a2be  sub     r8d, edx
0x18000a2c1  mov     [rsp+11D0h+var_11A0], r13d
0x18000a2c6  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000a2cb  mov     rcx, r14
0x18000a2ce  call    wil_details_NtUpdateWnfStateData
0x18000a2d3  add     r14, 8
0x18000a2d7  mov     rax, [rbp+10D0h+var_1130]
0x18000a2db  mov     [rbp+10D0h+var_1128], rax
0x18000a2df  mov     rsi, [rbp+10D0h+lpMem]
0x18000a2e3  mov     [rbp+10D0h+lpMem], r13
0x18000a2e7  test    rsi, rsi
0x18000a2ea  jz      short loc_18000A300
0x18000a2ec  call    cs:__imp_GetProcessHeap
0x18000a2f2  mov     rcx, rax; hHeap
0x18000a2f5  mov     r8, rsi; lpMem
0x18000a2f8  xor     edx, edx; dwFlags
0x18000a2fa  call    cs:__imp_HeapFree
0x18000a300  test    dil, dil
0x18000a303  jnz     short loc_18000A337
0x18000a305  cmp     r14, r12
0x18000a308  jnb     short loc_18000A337
0x18000a30a  cmp     r15, 32h ; '2'
0x18000a30e  jb      loc_180009FDA
0x18000a314  jmp     short loc_18000A337
0x18000a316  mov     rbx, [rbp+10D0h+lpMem]
0x18000a31a  mov     [rbp+10D0h+lpMem], r13
0x18000a31e  test    rbx, rbx
0x18000a321  jz      short loc_18000A337
0x18000a323  call    cs:__imp_GetProcessHeap
0x18000a329  mov     rcx, rax; hHeap
0x18000a32c  mov     r8, rbx; lpMem
0x18000a32f  xor     edx, edx; dwFlags
0x18000a331  call    cs:__imp_HeapFree
0x18000a337  mov     rcx, [rbp+10D0h+var_40]
0x18000a33e  xor     rcx, rsp; StackCookie
0x18000a341  call    __security_check_cookie
0x18000a346  mov     rbx, [rsp+11D0h+arg_8]
0x18000a34e  add     rsp, 11A0h
0x18000a355  pop     r15
0x18000a357  pop     r14
0x18000a359  pop     r13
0x18000a35b  pop     r12
0x18000a35d  pop     rdi
0x18000a35e  pop     rsi
0x18000a35f  pop     rbp
0x18000a360  retn
0x18000a361  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
