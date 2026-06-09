# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180014cec`
- end: `0x1800150c3`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18001428c`

## callees

- `0x18000f6e0`
- `0x180013774`
- `0x18001419c`
- `0x180014cec`
- `0x18001581c`
- `0x180016ab0`
- `0x180019760`
- `0x180019820`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014de2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180014de2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014dcb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180014dcb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015048`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001507f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015048`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001507f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015056`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001508d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180015056`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001508d`

## string_xrefs

- `0x180014dc4`: `ntdll.dll`

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
  __int64 v17; // r9
  char v18; // di
  int updated; // eax
  __int64 v20; // r9
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  __int64 *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v27);
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v33, (int)v34 - (int)v33, v17, (int)v25, v27[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v33, v34 - v33, v20, (int)v25, 0, 0);
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
0x180014cec  mov     [rsp-8+arg_8], rbx
0x180014cf1  push    rbp
0x180014cf2  push    rsi
0x180014cf3  push    rdi
0x180014cf4  push    r12
0x180014cf6  push    r13
0x180014cf8  push    r14
0x180014cfa  push    r15
0x180014cfc  lea     rbp, [rsp-10A0h]
0x180014d04  mov     eax, 11A0h
0x180014d09  call    _alloca_probe
0x180014d0e  sub     rsp, rax
0x180014d11  mov     rax, cs:__security_cookie
0x180014d18  xor     rax, rsp
0x180014d1b  mov     [rbp+10D0h+var_40], rax
0x180014d22  mov     rbx, r8
0x180014d25  mov     r14, rcx
0x180014d28  lea     r12, [rcx+rdx*8]
0x180014d2c  xor     r13d, r13d
0x180014d2f  mov     r15d, r13d
0x180014d32  mov     [rbp+10D0h+var_1128], r13
0x180014d36  mov     cl, [rbx+8]
0x180014d39  movzx   edx, word ptr [rbx+6]
0x180014d3d  movzx   eax, word ptr [rbx]
0x180014d40  mov     [rsp+11D0h+var_1170], ax
0x180014d45  movzx   eax, word ptr [rbx+2]
0x180014d49  mov     [rsp+11D0h+var_116E], ax
0x180014d4e  mov     al, [rbx+4]
0x180014d51  mov     [rsp+11D0h+var_116C], al
0x180014d55  mov     [rsp+11D0h+var_116A], dx
0x180014d5a  mov     [rsp+11D0h+var_1168], cl
0x180014d5e  test    dx, dx
0x180014d61  jz      short loc_180014D80
0x180014d63  mov     eax, edx
0x180014d65  cmp     cl, 1
0x180014d68  jnz     short loc_180014D70
0x180014d6a  add     rax, 2
0x180014d6e  jmp     short loc_180014D79
0x180014d70  cmp     cl, 2
0x180014d73  jnz     short loc_180014D79
0x180014d75  add     rax, 4
0x180014d79  mov     [rsp+11D0h+var_1160], rax
0x180014d7e  jmp     short loc_180014D85
0x180014d80  mov     [rsp+11D0h+var_1160], r13
0x180014d85  mov     [rsp+11D0h+var_1158], r13
0x180014d8a  xorps   xmm0, xmm0
0x180014d8d  movdqa  [rbp+10D0h+var_1150], xmm0
0x180014d92  mov     [rbp+10D0h+lpMem], r13
0x180014d96  mov     [rbp+10D0h+var_1138], r13w
0x180014d9b  mov     [rbp+10D0h+var_1136], r13b
0x180014d9f  mov     [rsp+11D0h+var_1188], r13d
0x180014da4  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180014dac  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180014db3  test    rax, rax
0x180014db6  jnz     short loc_180014DFB
0x180014db8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014dbf  test    rax, rax
0x180014dc2  jnz     short loc_180014DD8
0x180014dc4  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180014dcb  call    cs:__imp_GetModuleHandleW
0x180014dd1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014dd8  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180014ddf  mov     rcx, rax; hModule
0x180014de2  call    cs:__imp_GetProcAddress
0x180014de8  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180014def  test    rax, rax
0x180014df2  jnz     short loc_180014DFB
0x180014df4  mov     edi, 0C0000139h
0x180014df9  jmp     short loc_180014E25
0x180014dfb  lea     rcx, [rsp+11D0h+var_1190]
0x180014e00  mov     [rsp+11D0h+var_11A8], rcx
0x180014e05  lea     rcx, [rbp+10D0h+var_1040]
0x180014e0c  mov     [rsp+11D0h+var_11B0], rcx
0x180014e11  lea     r9, [rsp+11D0h+var_1188]
0x180014e16  xor     r8d, r8d
0x180014e19  xor     edx, edx
0x180014e1b  mov     rcx, r14
0x180014e1e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014e23  mov     edi, eax
0x180014e25  mov     ecx, edi; this
0x180014e27  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180014e2c  test    edi, edi
0x180014e2e  jz      short loc_180014E3E
0x180014e30  mov     eax, r13d
0x180014e33  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180014e37  mov     [rsp+11D0h+var_1188], r13d
0x180014e3c  jmp     short loc_180014E42
0x180014e3e  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180014e42  mov     r8d, eax; unsigned __int64
0x180014e45  mov     r9d, 1000h; unsigned __int64
0x180014e4b  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180014e52  lea     rcx, [rsp+11D0h+var_1170]; this
0x180014e57  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180014e5c  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180014e60  jnz     loc_180015072
0x180014e66  mov     [rbp+10D0h+var_1130], r13
0x180014e6a  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180014e71  mov     [rbp+10D0h+var_10B0], rax
0x180014e75  lea     rax, [rbp+10D0h+var_1130]
0x180014e79  mov     [rbp+10D0h+var_10A8], rax
0x180014e7d  lea     rax, [rbp+10D0h+var_1128]
0x180014e81  mov     [rbp+10D0h+var_10A0], rax
0x180014e85  lea     rax, [rsp+11D0h+var_1170]
0x180014e8a  mov     [rbp+10D0h+var_1098], rax
0x180014e8e  lea     rax, [rbp+10D0h+var_10B0]
0x180014e92  mov     [rbp+10D0h+var_1048], rax
0x180014e99  lea     rax, [rbp+10D0h+var_10B8]
0x180014e9d  mov     [rbp+10D0h+var_10C0], rax
0x180014ea1  mov     rax, [rbx+18h]
0x180014ea5  add     rax, 0Ah
0x180014ea9  mov     [rsp+11D0h+var_1190], rax
0x180014eae  movzx   eax, word ptr [rbx+2]
0x180014eb2  mov     [rbp+10D0h+var_1120], ax
0x180014eb6  mov     al, [rbx+4]
0x180014eb9  mov     [rbp+10D0h+var_111E], al
0x180014ebc  mov     [rbp+10D0h+var_111C], r13d
0x180014ec0  mov     [rbp+10D0h+var_1118], r13w
0x180014ec5  xorps   xmm0, xmm0
0x180014ec8  movdqu  [rbp+10D0h+var_1110], xmm0
0x180014ecd  movzx   eax, word ptr [rbx+6]
0x180014ed1  mov     [rbp+10D0h+var_1100], ax
0x180014ed5  mov     al, [rbx+8]
0x180014ed8  mov     [rbp+10D0h+var_10FE], al
0x180014edb  mov     [rbp+10D0h+var_10FC], r13d
0x180014edf  mov     [rbp+10D0h+var_10F8], r13w
0x180014ee4  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180014ee9  jmp     loc_180014F82
0x180014eee  mov     edi, r13d
0x180014ef1  cmp     [rbp+10D0h+var_111C], r13d
0x180014ef5  jbe     loc_180014F82
0x180014efb  mov     r8, [rbx+20h]; unsigned __int8 *
0x180014eff  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180014f04  lea     rcx, [rbp+10D0h+var_1100]; this
0x180014f08  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180014f0d  test    al, al
0x180014f0f  jz      short loc_180014F82
0x180014f11  mov     eax, [rbp+10D0h+var_10FC]
0x180014f14  mov     [rsp+11D0h+var_1180], eax
0x180014f18  movzx   eax, [rbp+10D0h+var_10F8]
0x180014f1c  mov     [rbp+10D0h+var_10E0], rax
0x180014f20  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180014f24  mov     [rbp+10D0h+var_10D8], rax
0x180014f28  movzx   eax, [rbp+10D0h+var_1118]
0x180014f2c  mov     [rbp+10D0h+var_10D0], rax
0x180014f30  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x180014f34  mov     [rbp+10D0h+var_10C8], rax
0x180014f38  mov     rcx, [rbp+10D0h+var_1048]; this
0x180014f3f  test    rcx, rcx
0x180014f42  jz      loc_1800150BD
0x180014f48  mov     rax, [rcx]
0x180014f4b  lea     rdx, [rsp+11D0h+var_1180]
0x180014f50  mov     [rsp+11D0h+var_11A8], rdx
0x180014f55  lea     rdx, [rbp+10D0h+var_10E0]
0x180014f59  mov     [rsp+11D0h+var_11B0], rdx
0x180014f5e  lea     r9, [rbp+10D0h+var_10D8]
0x180014f62  lea     r8, [rbp+10D0h+var_10D0]
0x180014f66  lea     rdx, [rbp+10D0h+var_10C8]
0x180014f6a  mov     rax, [rax+20h]
0x180014f6e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014f73  test    al, al
0x180014f75  jz      short loc_180014FF0
0x180014f77  inc     edi
0x180014f79  cmp     edi, [rbp+10D0h+var_111C]
0x180014f7c  jb      loc_180014EFB
0x180014f82  mov     r8, [rbx+20h]; unsigned __int8 *
0x180014f86  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180014f8b  lea     rcx, [rbp+10D0h+var_1120]; this
0x180014f8f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180014f94  test    al, al
0x180014f96  jnz     loc_180014EEE
0x180014f9c  mov     rcx, [rbp+10D0h+var_1048]
0x180014fa3  test    rcx, rcx
0x180014fa6  jz      short loc_180014FB4
0x180014fa8  mov     rax, [rcx]
0x180014fab  mov     rax, [rax+18h]
0x180014faf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014fb4  mov     dil, 1
0x180014fb7  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x180014fbb  jz      short loc_18001502F
0x180014fbd  mov     eax, [rsp+11D0h+var_1188]
0x180014fc1  mov     rdx, [rsp+11D0h+var_1158]
0x180014fc6  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180014fca  sub     r8d, edx
0x180014fcd  mov     [rsp+11D0h+var_11A0], 1
0x180014fd5  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180014fd9  mov     rcx, r14
0x180014fdc  call    wil_details_NtUpdateWnfStateData
0x180014fe1  cmp     eax, 0C0000001h
0x180014fe6  jnz     short loc_18001500D
0x180014fe8  inc     r15
0x180014feb  mov     dil, r13b
0x180014fee  jmp     short loc_18001503B
0x180014ff0  mov     rcx, [rbp+10D0h+var_1048]
0x180014ff7  test    rcx, rcx
0x180014ffa  jz      short loc_180015008
0x180014ffc  mov     rax, [rcx]
0x180014fff  mov     rax, [rax+18h]
0x180015003  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015008  mov     dil, r13b
0x18001500b  jmp     short loc_180014FB7
0x18001500d  test    eax, eax
0x18001500f  jz      short loc_18001502F
0x180015011  mov     rdx, [rsp+11D0h+var_1158]
0x180015016  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18001501a  sub     r8d, edx
0x18001501d  mov     [rsp+11D0h+var_11A0], r13d
0x180015022  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x180015027  mov     rcx, r14
0x18001502a  call    wil_details_NtUpdateWnfStateData
0x18001502f  add     r14, 8
0x180015033  mov     rax, [rbp+10D0h+var_1130]
0x180015037  mov     [rbp+10D0h+var_1128], rax
0x18001503b  mov     rsi, [rbp+10D0h+lpMem]
0x18001503f  mov     [rbp+10D0h+lpMem], r13
0x180015043  test    rsi, rsi
0x180015046  jz      short loc_18001505C
0x180015048  call    cs:__imp_GetProcessHeap
0x18001504e  mov     rcx, rax; hHeap
0x180015051  mov     r8, rsi; lpMem
0x180015054  xor     edx, edx; dwFlags
0x180015056  call    cs:__imp_HeapFree
0x18001505c  test    dil, dil
0x18001505f  jnz     short loc_180015093
0x180015061  cmp     r14, r12
0x180015064  jnb     short loc_180015093
0x180015066  cmp     r15, 32h ; '2'
0x18001506a  jb      loc_180014D36
0x180015070  jmp     short loc_180015093
0x180015072  mov     rbx, [rbp+10D0h+lpMem]
0x180015076  mov     [rbp+10D0h+lpMem], r13
0x18001507a  test    rbx, rbx
0x18001507d  jz      short loc_180015093
0x18001507f  call    cs:__imp_GetProcessHeap
0x180015085  mov     rcx, rax; hHeap
0x180015088  mov     r8, rbx; lpMem
0x18001508b  xor     edx, edx; dwFlags
0x18001508d  call    cs:__imp_HeapFree
0x180015093  mov     rcx, [rbp+10D0h+var_40]
0x18001509a  xor     rcx, rsp; StackCookie
0x18001509d  call    __security_check_cookie
0x1800150a2  mov     rbx, [rsp+11D0h+arg_8]
0x1800150aa  add     rsp, 11A0h
0x1800150b1  pop     r15
0x1800150b3  pop     r14
0x1800150b5  pop     r13
0x1800150b7  pop     r12
0x1800150b9  pop     rdi
0x1800150ba  pop     rsi
0x1800150bb  pop     rbp
0x1800150bc  retn
0x1800150bd  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
