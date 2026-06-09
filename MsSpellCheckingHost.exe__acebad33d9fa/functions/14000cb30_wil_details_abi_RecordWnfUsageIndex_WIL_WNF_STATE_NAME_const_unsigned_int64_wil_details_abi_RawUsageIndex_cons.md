# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x14000cb30`
- end: `0x14000cf07`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14000c068`

## callees

- `0x14000bb5c`
- `0x14000bf78`
- `0x14000cb30`
- `0x14000d394`
- `0x14000ecd4`
- `0x14000fc00`
- `0x140011e10`
- `0x140011ed0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000cc0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000cc0f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000cc26`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000cc26`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ce9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ced1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ce9a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ced1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ce8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cec3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ce8c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000cec3`

## string_xrefs

- `0x14000cc08`: `ntdll.dll`

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
0x14000cb30  mov     [rsp-8+arg_8], rbx
0x14000cb35  push    rbp
0x14000cb36  push    rsi
0x14000cb37  push    rdi
0x14000cb38  push    r12
0x14000cb3a  push    r13
0x14000cb3c  push    r14
0x14000cb3e  push    r15
0x14000cb40  lea     rbp, [rsp-10A0h]
0x14000cb48  mov     eax, 11A0h
0x14000cb4d  call    _alloca_probe
0x14000cb52  sub     rsp, rax
0x14000cb55  mov     rax, cs:__security_cookie
0x14000cb5c  xor     rax, rsp
0x14000cb5f  mov     [rbp+10D0h+var_40], rax
0x14000cb66  mov     rbx, r8
0x14000cb69  mov     r14, rcx
0x14000cb6c  lea     r12, [rcx+rdx*8]
0x14000cb70  xor     r13d, r13d
0x14000cb73  mov     r15d, r13d
0x14000cb76  mov     [rbp+10D0h+var_1128], r13
0x14000cb7a  mov     cl, [rbx+8]
0x14000cb7d  movzx   edx, word ptr [rbx+6]
0x14000cb81  movzx   eax, word ptr [rbx]
0x14000cb84  mov     [rsp+11D0h+var_1170], ax
0x14000cb89  movzx   eax, word ptr [rbx+2]
0x14000cb8d  mov     [rsp+11D0h+var_116E], ax
0x14000cb92  mov     al, [rbx+4]
0x14000cb95  mov     [rsp+11D0h+var_116C], al
0x14000cb99  mov     [rsp+11D0h+var_116A], dx
0x14000cb9e  mov     [rsp+11D0h+var_1168], cl
0x14000cba2  test    dx, dx
0x14000cba5  jz      short loc_14000CBC4
0x14000cba7  mov     eax, edx
0x14000cba9  cmp     cl, 1
0x14000cbac  jnz     short loc_14000CBB4
0x14000cbae  add     rax, 2
0x14000cbb2  jmp     short loc_14000CBBD
0x14000cbb4  cmp     cl, 2
0x14000cbb7  jnz     short loc_14000CBBD
0x14000cbb9  add     rax, 4
0x14000cbbd  mov     [rsp+11D0h+var_1160], rax
0x14000cbc2  jmp     short loc_14000CBC9
0x14000cbc4  mov     [rsp+11D0h+var_1160], r13
0x14000cbc9  mov     [rsp+11D0h+var_1158], r13
0x14000cbce  xorps   xmm0, xmm0
0x14000cbd1  movdqa  [rbp+10D0h+var_1150], xmm0
0x14000cbd6  mov     [rbp+10D0h+lpMem], r13
0x14000cbda  mov     [rbp+10D0h+var_1138], r13w
0x14000cbdf  mov     [rbp+10D0h+var_1136], r13b
0x14000cbe3  mov     [rsp+11D0h+var_1188], r13d
0x14000cbe8  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14000cbf0  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000cbf7  test    rax, rax
0x14000cbfa  jnz     short loc_14000CC3F
0x14000cbfc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000cc03  test    rax, rax
0x14000cc06  jnz     short loc_14000CC1C
0x14000cc08  lea     rcx, aNtdllDll; "ntdll.dll"
0x14000cc0f  call    cs:__imp_GetModuleHandleW
0x14000cc15  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000cc1c  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000cc23  mov     rcx, rax; hModule
0x14000cc26  call    cs:__imp_GetProcAddress
0x14000cc2c  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000cc33  test    rax, rax
0x14000cc36  jnz     short loc_14000CC3F
0x14000cc38  mov     edi, 0C0000139h
0x14000cc3d  jmp     short loc_14000CC69
0x14000cc3f  lea     rcx, [rsp+11D0h+var_1190]
0x14000cc44  mov     [rsp+11D0h+var_11A8], rcx
0x14000cc49  lea     rcx, [rbp+10D0h+var_1040]
0x14000cc50  mov     [rsp+11D0h+var_11B0], rcx
0x14000cc55  lea     r9, [rsp+11D0h+var_1188]
0x14000cc5a  xor     r8d, r8d
0x14000cc5d  xor     edx, edx
0x14000cc5f  mov     rcx, r14
0x14000cc62  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cc67  mov     edi, eax
0x14000cc69  mov     ecx, edi; this
0x14000cc6b  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000cc70  test    edi, edi
0x14000cc72  jz      short loc_14000CC82
0x14000cc74  mov     eax, r13d
0x14000cc77  mov     dword ptr [rsp+11D0h+var_1190], eax
0x14000cc7b  mov     [rsp+11D0h+var_1188], r13d
0x14000cc80  jmp     short loc_14000CC86
0x14000cc82  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x14000cc86  mov     r8d, eax; unsigned __int64
0x14000cc89  mov     r9d, 1000h; unsigned __int64
0x14000cc8f  lea     rdx, [rbp+10D0h+var_1040]; void *
0x14000cc96  lea     rcx, [rsp+11D0h+var_1170]; this
0x14000cc9b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x14000cca0  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x14000cca4  jnz     loc_14000CEB6
0x14000ccaa  mov     [rbp+10D0h+var_1130], r13
0x14000ccae  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x14000ccb5  mov     [rbp+10D0h+var_10B0], rax
0x14000ccb9  lea     rax, [rbp+10D0h+var_1130]
0x14000ccbd  mov     [rbp+10D0h+var_10A8], rax
0x14000ccc1  lea     rax, [rbp+10D0h+var_1128]
0x14000ccc5  mov     [rbp+10D0h+var_10A0], rax
0x14000ccc9  lea     rax, [rsp+11D0h+var_1170]
0x14000ccce  mov     [rbp+10D0h+var_1098], rax
0x14000ccd2  lea     rax, [rbp+10D0h+var_10B0]
0x14000ccd6  mov     [rbp+10D0h+var_1048], rax
0x14000ccdd  lea     rax, [rbp+10D0h+var_10B8]
0x14000cce1  mov     [rbp+10D0h+var_10C0], rax
0x14000cce5  mov     rax, [rbx+18h]
0x14000cce9  add     rax, 0Ah
0x14000cced  mov     [rsp+11D0h+var_1190], rax
0x14000ccf2  movzx   eax, word ptr [rbx+2]
0x14000ccf6  mov     [rbp+10D0h+var_1120], ax
0x14000ccfa  mov     al, [rbx+4]
0x14000ccfd  mov     [rbp+10D0h+var_111E], al
0x14000cd00  mov     [rbp+10D0h+var_111C], r13d
0x14000cd04  mov     [rbp+10D0h+var_1118], r13w
0x14000cd09  xorps   xmm0, xmm0
0x14000cd0c  movdqu  [rbp+10D0h+var_1110], xmm0
0x14000cd11  movzx   eax, word ptr [rbx+6]
0x14000cd15  mov     [rbp+10D0h+var_1100], ax
0x14000cd19  mov     al, [rbx+8]
0x14000cd1c  mov     [rbp+10D0h+var_10FE], al
0x14000cd1f  mov     [rbp+10D0h+var_10FC], r13d
0x14000cd23  mov     [rbp+10D0h+var_10F8], r13w
0x14000cd28  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14000cd2d  jmp     loc_14000CDC6
0x14000cd32  mov     edi, r13d
0x14000cd35  cmp     [rbp+10D0h+var_111C], r13d
0x14000cd39  jbe     loc_14000CDC6
0x14000cd3f  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000cd43  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000cd48  lea     rcx, [rbp+10D0h+var_1100]; this
0x14000cd4c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000cd51  test    al, al
0x14000cd53  jz      short loc_14000CDC6
0x14000cd55  mov     eax, [rbp+10D0h+var_10FC]
0x14000cd58  mov     [rsp+11D0h+var_1180], eax
0x14000cd5c  movzx   eax, [rbp+10D0h+var_10F8]
0x14000cd60  mov     [rbp+10D0h+var_10E0], rax
0x14000cd64  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000cd68  mov     [rbp+10D0h+var_10D8], rax
0x14000cd6c  movzx   eax, [rbp+10D0h+var_1118]
0x14000cd70  mov     [rbp+10D0h+var_10D0], rax
0x14000cd74  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x14000cd78  mov     [rbp+10D0h+var_10C8], rax
0x14000cd7c  mov     rcx, [rbp+10D0h+var_1048]; this
0x14000cd83  test    rcx, rcx
0x14000cd86  jz      loc_14000CF01
0x14000cd8c  mov     rax, [rcx]
0x14000cd8f  lea     rdx, [rsp+11D0h+var_1180]
0x14000cd94  mov     [rsp+11D0h+var_11A8], rdx
0x14000cd99  lea     rdx, [rbp+10D0h+var_10E0]
0x14000cd9d  mov     [rsp+11D0h+var_11B0], rdx
0x14000cda2  lea     r9, [rbp+10D0h+var_10D8]
0x14000cda6  lea     r8, [rbp+10D0h+var_10D0]
0x14000cdaa  lea     rdx, [rbp+10D0h+var_10C8]
0x14000cdae  mov     rax, [rax+20h]
0x14000cdb2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cdb7  test    al, al
0x14000cdb9  jz      short loc_14000CE34
0x14000cdbb  inc     edi
0x14000cdbd  cmp     edi, [rbp+10D0h+var_111C]
0x14000cdc0  jb      loc_14000CD3F
0x14000cdc6  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000cdca  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000cdcf  lea     rcx, [rbp+10D0h+var_1120]; this
0x14000cdd3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000cdd8  test    al, al
0x14000cdda  jnz     loc_14000CD32
0x14000cde0  mov     rcx, [rbp+10D0h+var_1048]
0x14000cde7  test    rcx, rcx
0x14000cdea  jz      short loc_14000CDF8
0x14000cdec  mov     rax, [rcx]
0x14000cdef  mov     rax, [rax+18h]
0x14000cdf3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000cdf8  mov     dil, 1
0x14000cdfb  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x14000cdff  jz      short loc_14000CE73
0x14000ce01  mov     eax, [rsp+11D0h+var_1188]
0x14000ce05  mov     rdx, [rsp+11D0h+var_1158]
0x14000ce0a  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000ce0e  sub     r8d, edx
0x14000ce11  mov     [rsp+11D0h+var_11A0], 1
0x14000ce19  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14000ce1d  mov     rcx, r14
0x14000ce20  call    wil_details_NtUpdateWnfStateData
0x14000ce25  cmp     eax, 0C0000001h
0x14000ce2a  jnz     short loc_14000CE51
0x14000ce2c  inc     r15
0x14000ce2f  mov     dil, r13b
0x14000ce32  jmp     short loc_14000CE7F
0x14000ce34  mov     rcx, [rbp+10D0h+var_1048]
0x14000ce3b  test    rcx, rcx
0x14000ce3e  jz      short loc_14000CE4C
0x14000ce40  mov     rax, [rcx]
0x14000ce43  mov     rax, [rax+18h]
0x14000ce47  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ce4c  mov     dil, r13b
0x14000ce4f  jmp     short loc_14000CDFB
0x14000ce51  test    eax, eax
0x14000ce53  jz      short loc_14000CE73
0x14000ce55  mov     rdx, [rsp+11D0h+var_1158]
0x14000ce5a  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000ce5e  sub     r8d, edx
0x14000ce61  mov     [rsp+11D0h+var_11A0], r13d
0x14000ce66  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x14000ce6b  mov     rcx, r14
0x14000ce6e  call    wil_details_NtUpdateWnfStateData
0x14000ce73  add     r14, 8
0x14000ce77  mov     rax, [rbp+10D0h+var_1130]
0x14000ce7b  mov     [rbp+10D0h+var_1128], rax
0x14000ce7f  mov     rsi, [rbp+10D0h+lpMem]
0x14000ce83  mov     [rbp+10D0h+lpMem], r13
0x14000ce87  test    rsi, rsi
0x14000ce8a  jz      short loc_14000CEA0
0x14000ce8c  call    cs:__imp_GetProcessHeap
0x14000ce92  mov     rcx, rax; hHeap
0x14000ce95  mov     r8, rsi; lpMem
0x14000ce98  xor     edx, edx; dwFlags
0x14000ce9a  call    cs:__imp_HeapFree
0x14000cea0  test    dil, dil
0x14000cea3  jnz     short loc_14000CED7
0x14000cea5  cmp     r14, r12
0x14000cea8  jnb     short loc_14000CED7
0x14000ceaa  cmp     r15, 32h ; '2'
0x14000ceae  jb      loc_14000CB7A
0x14000ceb4  jmp     short loc_14000CED7
0x14000ceb6  mov     rbx, [rbp+10D0h+lpMem]
0x14000ceba  mov     [rbp+10D0h+lpMem], r13
0x14000cebe  test    rbx, rbx
0x14000cec1  jz      short loc_14000CED7
0x14000cec3  call    cs:__imp_GetProcessHeap
0x14000cec9  mov     rcx, rax; hHeap
0x14000cecc  mov     r8, rbx; lpMem
0x14000cecf  xor     edx, edx; dwFlags
0x14000ced1  call    cs:__imp_HeapFree
0x14000ced7  mov     rcx, [rbp+10D0h+var_40]
0x14000cede  xor     rcx, rsp; StackCookie
0x14000cee1  call    __security_check_cookie
0x14000cee6  mov     rbx, [rsp+11D0h+arg_8]
0x14000ceee  add     rsp, 11A0h
0x14000cef5  pop     r15
0x14000cef7  pop     r14
0x14000cef9  pop     r13
0x14000cefb  pop     r12
0x14000cefd  pop     rdi
0x14000cefe  pop     rsi
0x14000ceff  pop     rbp
0x14000cf00  retn
0x14000cf01  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
