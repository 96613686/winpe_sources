# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140010a9c`
- end: `0x140010e69`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14001004c`

## callees

- `0x1400054ec`
- `0x14000fa5c`
- `0x14000ff5c`
- `0x140010a9c`
- `0x140011250`
- `0x1400127c0`
- `0x1400134a0`
- `0x140013530`
- `0x140014010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010b92`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140010b92`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140010b7b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140010b7b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010def`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010e25`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010def`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140010e25`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010dfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010e33`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010dfd`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140010e33`

## string_xrefs

- `0x140010b74`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v4; // r12
  unsigned __int64 v5; // r15
  wil::details_abi *v7; // r14
  unsigned int v8; // edx
  char v9; // cl
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rax
  int v17; // ebx
  int v18; // r9d
  char v19; // bl
  int updated; // eax
  int v21; // r9d
  void *v22; // rsi
  HANDLE ProcessHeap; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  __int64 *v26; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v27; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v28[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v29[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v30; // [rsp+64h] [rbp-9Ch]
  __int16 v31; // [rsp+66h] [rbp-9Ah]
  char v32; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+78h] [rbp-88h]
  __int128 v35; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v37; // [rsp+98h] [rbp-68h]
  char v38; // [rsp+9Ah] [rbp-66h]
  __int64 v39; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v41; // [rsp+B0h] [rbp-50h] BYREF
  char v42; // [rsp+B2h] [rbp-4Eh]
  unsigned int v43; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v44; // [rsp+B8h] [rbp-48h]
  __int128 v45; // [rsp+C0h] [rbp-40h]
  __int16 v46; // [rsp+D0h] [rbp-30h] BYREF
  char v47; // [rsp+D2h] [rbp-2Eh]
  int v48; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v49; // [rsp+D8h] [rbp-28h]
  __int128 v50; // [rsp+E0h] [rbp-20h]
  __int64 v51; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v52; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v53; // [rsp+100h] [rbp+0h] BYREF
  __int64 v54; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v55[13]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *v56; // [rsp+180h] [rbp+80h]
  _BYTE v57[4096]; // [rsp+190h] [rbp+90h] BYREF

  v4 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v5 = 0;
  v40 = 0;
  v7 = this;
  while ( 1 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6);
    v9 = *(_BYTE *)(a3 + 8);
    v29[0] = *(_WORD *)a3;
    v29[1] = *(_WORD *)(a3 + 2);
    v30 = *(_BYTE *)(a3 + 4);
    v31 = v8;
    v32 = v9;
    if ( (_WORD)v8 )
    {
      v10 = v8;
      if ( v9 == 1 )
      {
        v10 = v8 + 2LL;
      }
      else if ( v9 == 2 )
      {
        v10 = v8 + 4LL;
      }
      v33 = v10;
    }
    else
    {
      v33 = 0;
    }
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v34 = 0;
    v35 = 0;
    lpMem = 0;
    v37 = 0;
    v38 = 0;
    v28[0] = 0;
    LODWORD(v27) = 4096;
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
      v26 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v7, 0, 0, v28);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      v28[0] = 0;
      LODWORD(v27) = 0;
    }
    else
    {
      v15 = (unsigned int)v27;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v29, v57, v15, 0x1000u);
    if ( HIBYTE(v37) )
      break;
    v39 = 0;
    v55[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v43 = 0;
    v55[1] = &v39;
    v55[2] = &v40;
    v55[3] = v29;
    v56 = (wil::details::in1diag3 *)v55;
    v16 = *(_QWORD *)(a3 + 24);
    v44 = 0;
    v27 = (unsigned __int8 *)(v16 + 10);
    v41 = *(_WORD *)(a3 + 2);
    v42 = *(_BYTE *)(a3 + 4);
    v46 = *(_WORD *)(a3 + 6);
    v47 = *(_BYTE *)(a3 + 8);
    v45 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v41,
              &v27,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v17 = 0;
      if ( v43 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v46,
                  &v27,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v28[2] = v48;
          v51 = v49;
          v52 = *((_QWORD *)&v50 + 1);
          v53 = v44;
          v54 = *((_QWORD *)&v45 + 1);
          if ( !v56 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v26 = &v51;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  &v54,
                  &v53,
                  &v52) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
            v19 = 0;
            goto LABEL_29;
          }
          if ( ++v17 >= v43 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
    v19 = 1;
LABEL_29:
    if ( !(_BYTE)v37 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v7, v34, (int)v35 - (int)v34, v18, (_DWORD)v26, v28[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v7, v34, v35 - v34, v21, (_DWORD)v26, 0, 0);
LABEL_37:
      v7 = (wil::details_abi *)((char *)v7 + 8);
      v40 = v39;
      goto LABEL_38;
    }
    ++v5;
    v19 = 0;
LABEL_38:
    v22 = lpMem;
    lpMem = 0;
    if ( v22 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v22);
    }
    if ( v19 || v7 >= v4 || v5 >= 0x32 )
      return;
  }
  v24 = lpMem;
  lpMem = 0;
  if ( v24 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
  }
}

```

## disassembly

```asm
0x140010a9c  mov     [rsp-8+arg_8], rbx
0x140010aa1  push    rbp
0x140010aa2  push    rsi
0x140010aa3  push    rdi
0x140010aa4  push    r12
0x140010aa6  push    r13
0x140010aa8  push    r14
0x140010aaa  push    r15
0x140010aac  lea     rbp, [rsp-10A0h]
0x140010ab4  mov     eax, 11A0h
0x140010ab9  call    _alloca_probe
0x140010abe  sub     rsp, rax
0x140010ac1  mov     rax, cs:__security_cookie
0x140010ac8  xor     rax, rsp
0x140010acb  mov     [rbp+10D0h+var_40], rax
0x140010ad2  xor     r13d, r13d
0x140010ad5  lea     r12, [rcx+rdx*8]
0x140010ad9  mov     r15d, r13d
0x140010adc  mov     [rbp+10D0h+var_1128], r13
0x140010ae0  mov     rdi, r8
0x140010ae3  mov     r14, rcx
0x140010ae6  movzx   eax, word ptr [rdi]
0x140010ae9  movzx   edx, word ptr [rdi+6]
0x140010aed  mov     cl, [rdi+8]
0x140010af0  mov     [rsp+11D0h+var_1170], ax
0x140010af5  movzx   eax, word ptr [rdi+2]
0x140010af9  mov     [rsp+11D0h+var_116E], ax
0x140010afe  mov     al, [rdi+4]
0x140010b01  mov     [rsp+11D0h+var_116C], al
0x140010b05  mov     [rsp+11D0h+var_116A], dx
0x140010b0a  mov     [rsp+11D0h+var_1168], cl
0x140010b0e  test    dx, dx
0x140010b11  jz      short loc_140010B30
0x140010b13  mov     eax, edx
0x140010b15  cmp     cl, 1
0x140010b18  jnz     short loc_140010B20
0x140010b1a  add     rax, 2
0x140010b1e  jmp     short loc_140010B29
0x140010b20  cmp     cl, 2
0x140010b23  jnz     short loc_140010B29
0x140010b25  add     rax, 4
0x140010b29  mov     [rsp+11D0h+var_1160], rax
0x140010b2e  jmp     short loc_140010B35
0x140010b30  mov     [rsp+11D0h+var_1160], r13
0x140010b35  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140010b3c  xorps   xmm0, xmm0
0x140010b3f  mov     [rsp+11D0h+var_1158], r13
0x140010b44  movdqa  [rbp+10D0h+var_1150], xmm0
0x140010b49  mov     [rbp+10D0h+lpMem], r13
0x140010b4d  mov     [rbp+10D0h+var_1138], r13w
0x140010b52  mov     [rbp+10D0h+var_1136], r13b
0x140010b56  mov     [rsp+11D0h+var_1188], r13d
0x140010b5b  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x140010b63  test    rax, rax
0x140010b66  jnz     short loc_140010BAB
0x140010b68  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140010b6f  test    rax, rax
0x140010b72  jnz     short loc_140010B88
0x140010b74  lea     rcx, ModuleName; "ntdll.dll"
0x140010b7b  call    cs:__imp_GetModuleHandleW
0x140010b81  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140010b88  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140010b8f  mov     rcx, rax; hModule
0x140010b92  call    cs:__imp_GetProcAddress
0x140010b98  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140010b9f  test    rax, rax
0x140010ba2  jnz     short loc_140010BAB
0x140010ba4  mov     ebx, 0C0000139h
0x140010ba9  jmp     short loc_140010BD5
0x140010bab  lea     rcx, [rsp+11D0h+var_1190]
0x140010bb0  xor     r8d, r8d
0x140010bb3  mov     [rsp+11D0h+var_11A8], rcx
0x140010bb8  lea     r9, [rsp+11D0h+var_1188]
0x140010bbd  lea     rcx, [rbp+10D0h+var_1040]
0x140010bc4  xor     edx, edx
0x140010bc6  mov     [rsp+11D0h+var_11B0], rcx
0x140010bcb  mov     rcx, r14
0x140010bce  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010bd3  mov     ebx, eax
0x140010bd5  mov     ecx, ebx; this
0x140010bd7  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x140010bdc  test    ebx, ebx
0x140010bde  jz      short loc_140010BEE
0x140010be0  mov     eax, r13d
0x140010be3  mov     [rsp+11D0h+var_1188], r13d
0x140010be8  mov     dword ptr [rsp+11D0h+var_1190], eax
0x140010bec  jmp     short loc_140010BF2
0x140010bee  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x140010bf2  mov     r8d, eax; unsigned __int64
0x140010bf5  lea     rdx, [rbp+10D0h+var_1040]; void *
0x140010bfc  mov     r9d, 1000h; unsigned __int64
0x140010c02  lea     rcx, [rsp+11D0h+var_1170]; this
0x140010c07  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140010c0c  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x140010c10  jnz     loc_140010E18
0x140010c16  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x140010c1d  mov     [rbp+10D0h+var_1130], r13
0x140010c21  mov     [rbp+10D0h+var_10B8], rax
0x140010c25  xorps   xmm0, xmm0
0x140010c28  lea     rax, [rbp+10D0h+var_1130]
0x140010c2c  mov     [rbp+10D0h+var_111C], r13d
0x140010c30  mov     [rbp+10D0h+var_10B0], rax
0x140010c34  lea     rax, [rbp+10D0h+var_1128]
0x140010c38  mov     [rbp+10D0h+var_10A8], rax
0x140010c3c  lea     rax, [rsp+11D0h+var_1170]
0x140010c41  mov     [rbp+10D0h+var_10A0], rax
0x140010c45  lea     rax, [rbp+10D0h+var_10B8]
0x140010c49  mov     [rbp+10D0h+var_1050], rax
0x140010c50  mov     rax, [rdi+18h]
0x140010c54  add     rax, 0Ah
0x140010c58  mov     [rbp+10D0h+var_1118], r13w
0x140010c5d  mov     [rsp+11D0h+var_1190], rax
0x140010c62  movzx   eax, word ptr [rdi+2]
0x140010c66  mov     [rbp+10D0h+var_1120], ax
0x140010c6a  mov     al, [rdi+4]
0x140010c6d  mov     [rbp+10D0h+var_111E], al
0x140010c70  movzx   eax, word ptr [rdi+6]
0x140010c74  mov     [rbp+10D0h+var_1100], ax
0x140010c78  mov     al, [rdi+8]
0x140010c7b  mov     [rbp+10D0h+var_10FE], al
0x140010c7e  movdqu  [rbp+10D0h+var_1110], xmm0
0x140010c83  mov     [rbp+10D0h+var_10FC], r13d
0x140010c87  mov     [rbp+10D0h+var_10F8], r13w
0x140010c8c  movdqu  [rbp+10D0h+var_10F0], xmm0
0x140010c91  jmp     loc_140010D2A
0x140010c96  mov     ebx, r13d
0x140010c99  cmp     [rbp+10D0h+var_111C], r13d
0x140010c9d  jbe     loc_140010D2A
0x140010ca3  mov     r8, [rdi+20h]; unsigned __int8 *
0x140010ca7  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140010cac  lea     rcx, [rbp+10D0h+var_1100]; this
0x140010cb0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140010cb5  test    al, al
0x140010cb7  jz      short loc_140010D2A
0x140010cb9  mov     eax, [rbp+10D0h+var_10FC]
0x140010cbc  mov     rcx, [rbp+10D0h+var_1050]; this
0x140010cc3  mov     [rsp+11D0h+var_1180], eax
0x140010cc7  movzx   eax, [rbp+10D0h+var_10F8]
0x140010ccb  mov     [rbp+10D0h+var_10E0], rax
0x140010ccf  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x140010cd3  mov     [rbp+10D0h+var_10D8], rax
0x140010cd7  movzx   eax, [rbp+10D0h+var_1118]
0x140010cdb  mov     [rbp+10D0h+var_10D0], rax
0x140010cdf  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x140010ce3  mov     [rbp+10D0h+var_10C8], rax
0x140010ce7  test    rcx, rcx
0x140010cea  jz      loc_140010E63
0x140010cf0  mov     rax, [rcx]
0x140010cf3  lea     rdx, [rsp+11D0h+var_1180]
0x140010cf8  mov     [rsp+11D0h+var_11A8], rdx
0x140010cfd  lea     r9, [rbp+10D0h+var_10D8]
0x140010d01  lea     rdx, [rbp+10D0h+var_10E0]
0x140010d05  mov     [rsp+11D0h+var_11B0], rdx
0x140010d0a  lea     r8, [rbp+10D0h+var_10D0]
0x140010d0e  mov     rax, [rax+20h]
0x140010d12  lea     rdx, [rbp+10D0h+var_10C8]
0x140010d16  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d1b  test    al, al
0x140010d1d  jz      short loc_140010D97
0x140010d1f  inc     ebx
0x140010d21  cmp     ebx, [rbp+10D0h+var_111C]
0x140010d24  jb      loc_140010CA3
0x140010d2a  mov     r8, [rdi+20h]; unsigned __int8 *
0x140010d2e  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140010d33  lea     rcx, [rbp+10D0h+var_1120]; this
0x140010d37  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140010d3c  test    al, al
0x140010d3e  jnz     loc_140010C96
0x140010d44  mov     rcx, [rbp+10D0h+var_1050]
0x140010d4b  test    rcx, rcx
0x140010d4e  jz      short loc_140010D5C
0x140010d50  mov     rax, [rcx]
0x140010d53  mov     rax, [rax+18h]
0x140010d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010d5c  mov     bl, 1
0x140010d5e  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x140010d62  jz      short loc_140010DD6
0x140010d64  mov     rdx, [rsp+11D0h+var_1158]
0x140010d69  mov     rcx, r14
0x140010d6c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x140010d70  mov     eax, [rsp+11D0h+var_1188]
0x140010d74  sub     r8d, edx
0x140010d77  mov     [rsp+11D0h+var_11A0], 1
0x140010d7f  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x140010d83  call    wil_details_NtUpdateWnfStateData
0x140010d88  cmp     eax, 0C0000001h
0x140010d8d  jnz     short loc_140010DB4
0x140010d8f  inc     r15
0x140010d92  mov     bl, r13b
0x140010d95  jmp     short loc_140010DE2
0x140010d97  mov     rcx, [rbp+10D0h+var_1050]
0x140010d9e  test    rcx, rcx
0x140010da1  jz      short loc_140010DAF
0x140010da3  mov     rax, [rcx]
0x140010da6  mov     rax, [rax+18h]
0x140010daa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140010daf  mov     bl, r13b
0x140010db2  jmp     short loc_140010D5E
0x140010db4  test    eax, eax
0x140010db6  jz      short loc_140010DD6
0x140010db8  mov     rdx, [rsp+11D0h+var_1158]
0x140010dbd  mov     rcx, r14
0x140010dc0  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x140010dc4  sub     r8d, edx
0x140010dc7  mov     [rsp+11D0h+var_11A0], r13d
0x140010dcc  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x140010dd1  call    wil_details_NtUpdateWnfStateData
0x140010dd6  mov     rax, [rbp+10D0h+var_1130]
0x140010dda  add     r14, 8
0x140010dde  mov     [rbp+10D0h+var_1128], rax
0x140010de2  mov     rsi, [rbp+10D0h+lpMem]
0x140010de6  mov     [rbp+10D0h+lpMem], r13
0x140010dea  test    rsi, rsi
0x140010ded  jz      short loc_140010E03
0x140010def  call    cs:__imp_GetProcessHeap
0x140010df5  mov     r8, rsi; lpMem
0x140010df8  xor     edx, edx; dwFlags
0x140010dfa  mov     rcx, rax; hHeap
0x140010dfd  call    cs:__imp_HeapFree
0x140010e03  test    bl, bl
0x140010e05  jnz     short loc_140010E39
0x140010e07  cmp     r14, r12
0x140010e0a  jnb     short loc_140010E39
0x140010e0c  cmp     r15, 32h ; '2'
0x140010e10  jb      loc_140010AE6
0x140010e16  jmp     short loc_140010E39
0x140010e18  mov     rbx, [rbp+10D0h+lpMem]
0x140010e1c  mov     [rbp+10D0h+lpMem], r13
0x140010e20  test    rbx, rbx
0x140010e23  jz      short loc_140010E39
0x140010e25  call    cs:__imp_GetProcessHeap
0x140010e2b  mov     r8, rbx; lpMem
0x140010e2e  xor     edx, edx; dwFlags
0x140010e30  mov     rcx, rax; hHeap
0x140010e33  call    cs:__imp_HeapFree
0x140010e39  mov     rcx, [rbp+10D0h+var_40]
0x140010e40  xor     rcx, rsp; StackCookie
0x140010e43  call    __security_check_cookie
0x140010e48  mov     rbx, [rsp+11D0h+arg_8]
0x140010e50  add     rsp, 11A0h
0x140010e57  pop     r15
0x140010e59  pop     r14
0x140010e5b  pop     r13
0x140010e5d  pop     r12
0x140010e5f  pop     rdi
0x140010e60  pop     rsi
0x140010e61  pop     rbp
0x140010e62  retn
0x140010e63  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
