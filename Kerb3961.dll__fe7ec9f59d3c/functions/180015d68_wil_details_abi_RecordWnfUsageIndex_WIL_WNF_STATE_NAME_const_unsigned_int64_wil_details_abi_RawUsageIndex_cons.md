# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180015d68`
- end: `0x180016138`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `976`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800152d0`

## callees

- `0x180001d40`
- `0x18000a074`
- `0x180014b18`
- `0x1800151d0`
- `0x180015d68`
- `0x180016c20`
- `0x180018b10`
- `0x18001d300`
- `0x18001e010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800160be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800160f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800160be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800160f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800160cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016102`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800160cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180016102`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180015e5f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015e48`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015e48`

## string_xrefs

- `0x180015e41`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v4; // r13
  unsigned __int64 v5; // r12
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
  unsigned int v17; // esi
  int v18; // ebx
  __int64 v19; // r15
  __int64 v20; // r9
  char v21; // bl
  int updated; // eax
  __int64 v23; // r9
  void *v24; // rsi
  HANDLE ProcessHeap; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  __int64 *v28; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v32; // [rsp+64h] [rbp-9Ch]
  __int16 v33; // [rsp+66h] [rbp-9Ah]
  char v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+78h] [rbp-88h]
  __int128 v37; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v39; // [rsp+98h] [rbp-68h]
  char v40; // [rsp+9Ah] [rbp-66h]
  __int64 v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v43; // [rsp+B0h] [rbp-50h] BYREF
  char v44; // [rsp+B2h] [rbp-4Eh]
  unsigned int v45; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v46; // [rsp+B8h] [rbp-48h]
  __int128 v47; // [rsp+C0h] [rbp-40h]
  __int16 v48; // [rsp+D0h] [rbp-30h] BYREF
  char v49; // [rsp+D2h] [rbp-2Eh]
  int v50; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v51; // [rsp+D8h] [rbp-28h]
  __int128 v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v55; // [rsp+100h] [rbp+0h] BYREF
  __int64 v56; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v57[13]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *v58; // [rsp+180h] [rbp+80h]
  _BYTE v59[4096]; // [rsp+190h] [rbp+90h] BYREF

  v4 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v5 = 0;
  v42 = 0;
  v7 = this;
  while ( 1 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6);
    v9 = *(_BYTE *)(a3 + 8);
    v31[0] = *(_WORD *)a3;
    v31[1] = *(_WORD *)(a3 + 2);
    v32 = *(_BYTE *)(a3 + 4);
    v33 = v8;
    v34 = v9;
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
      v35 = v10;
    }
    else
    {
      v35 = 0;
    }
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v36 = 0;
    v37 = 0;
    lpMem = 0;
    v39 = 0;
    v40 = 0;
    v30[0] = 0;
    LODWORD(v29) = 4096;
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
      v28 = (__int64 *)v59;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v7, 0, 0, v30);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      v30[0] = 0;
      LODWORD(v29) = 0;
    }
    else
    {
      v15 = (unsigned int)v29;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v31, v59, v15, 0x1000u);
    if ( HIBYTE(v39) )
      break;
    v41 = 0;
    v57[0] = wistd::__function::Z::$$A6A_NPEAX131I::Z::__func<`wil::details_abi::RecordWnfUsageIndex'::`4'::_lambda_1_,AXPEBU__WIL__WNF_STATE_NAME,unsigned __int64,wil::details_abi::RawUsageIndex const &>::`vftable';
    v45 = 0;
    v57[1] = &v41;
    v57[2] = &v42;
    v57[3] = v31;
    v58 = (wil::details::in1diag3 *)v57;
    v16 = *(_QWORD *)(a3 + 24);
    v46 = 0;
    v29 = (unsigned __int8 *)(v16 + 10);
    v43 = *(_WORD *)(a3 + 2);
    v44 = *(_BYTE *)(a3 + 4);
    v48 = *(_WORD *)(a3 + 6);
    v49 = *(_BYTE *)(a3 + 8);
    v47 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v43,
              &v29,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v17 = v45;
      v18 = 0;
      if ( v45 )
      {
        v19 = *((_QWORD *)&v47 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v48,
                  &v29,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v30[2] = v50;
          v53 = v51;
          v54 = *((_QWORD *)&v52 + 1);
          v55 = v46;
          v56 = v19;
          if ( !v58 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v28 = &v53;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v58 + 32LL))(
                  v58,
                  &v56,
                  &v55,
                  &v54) )
          {
            if ( v58 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
            v21 = 0;
            goto LABEL_30;
          }
          if ( ++v18 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v58 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
    v21 = 1;
LABEL_30:
    if ( !(_BYTE)v39 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((__int64)v7, v36, (int)v37 - (int)v36, v20, (int)v28, v30[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v7, v36, v37 - v36, v23, (int)v28, 0, 0);
LABEL_38:
      v7 = (wil::details_abi *)((char *)v7 + 8);
      v42 = v41;
      goto LABEL_39;
    }
    ++v5;
    v21 = 0;
LABEL_39:
    v24 = lpMem;
    lpMem = 0;
    if ( v24 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v24);
    }
    if ( v21 || v7 >= v4 || v5 >= 0x32 )
      return;
  }
  v26 = lpMem;
  lpMem = 0;
  if ( v26 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
  }
}

```

## disassembly

```asm
0x180015d68  mov     [rsp-8+arg_8], rbx
0x180015d6d  push    rbp
0x180015d6e  push    rsi
0x180015d6f  push    rdi
0x180015d70  push    r12
0x180015d72  push    r13
0x180015d74  push    r14
0x180015d76  push    r15
0x180015d78  lea     rbp, [rsp-10A0h]
0x180015d80  mov     eax, 11A0h
0x180015d85  call    _alloca_probe
0x180015d8a  sub     rsp, rax
0x180015d8d  mov     rax, cs:__security_cookie
0x180015d94  xor     rax, rsp
0x180015d97  mov     [rbp+10D0h+var_40], rax
0x180015d9e  xor     r15d, r15d
0x180015da1  lea     r13, [rcx+rdx*8]
0x180015da5  mov     r12d, r15d
0x180015da8  mov     [rbp+10D0h+var_1128], r15
0x180015dac  mov     rdi, r8
0x180015daf  mov     r14, rcx
0x180015db2  movzx   eax, word ptr [rdi]
0x180015db5  movzx   edx, word ptr [rdi+6]
0x180015db9  mov     cl, [rdi+8]
0x180015dbc  mov     [rsp+11D0h+var_1170], ax
0x180015dc1  movzx   eax, word ptr [rdi+2]
0x180015dc5  mov     [rsp+11D0h+var_116E], ax
0x180015dca  mov     al, [rdi+4]
0x180015dcd  mov     [rsp+11D0h+var_116C], al
0x180015dd1  mov     [rsp+11D0h+var_116A], dx
0x180015dd6  mov     [rsp+11D0h+var_1168], cl
0x180015dda  test    dx, dx
0x180015ddd  jz      short loc_180015DFC
0x180015ddf  mov     eax, edx
0x180015de1  cmp     cl, 1
0x180015de4  jnz     short loc_180015DEC
0x180015de6  add     rax, 2
0x180015dea  jmp     short loc_180015DF5
0x180015dec  cmp     cl, 2
0x180015def  jnz     short loc_180015DF5
0x180015df1  add     rax, 4
0x180015df5  mov     [rsp+11D0h+var_1160], rax
0x180015dfa  jmp     short loc_180015E01
0x180015dfc  mov     [rsp+11D0h+var_1160], r15
0x180015e01  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180015e08  xorps   xmm0, xmm0
0x180015e0b  mov     [rsp+11D0h+var_1158], r15
0x180015e10  movdqa  [rbp+10D0h+var_1150], xmm0
0x180015e15  mov     [rbp+10D0h+lpMem], r15
0x180015e19  mov     [rbp+10D0h+var_1138], 0
0x180015e1f  mov     [rbp+10D0h+var_1136], r15b
0x180015e23  mov     [rsp+11D0h+var_1188], r15d
0x180015e28  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180015e30  test    rax, rax
0x180015e33  jnz     short loc_180015E78
0x180015e35  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015e3c  test    rax, rax
0x180015e3f  jnz     short loc_180015E55
0x180015e41  lea     rcx, ModuleName; "ntdll.dll"
0x180015e48  call    cs:__imp_GetModuleHandleW
0x180015e4e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015e55  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180015e5c  mov     rcx, rax; hModule
0x180015e5f  call    cs:__imp_GetProcAddress
0x180015e65  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180015e6c  test    rax, rax
0x180015e6f  jnz     short loc_180015E78
0x180015e71  mov     ebx, 0C0000139h
0x180015e76  jmp     short loc_180015EA2
0x180015e78  lea     rcx, [rsp+11D0h+var_1190]
0x180015e7d  xor     r8d, r8d
0x180015e80  mov     [rsp+11D0h+var_11A8], rcx
0x180015e85  lea     r9, [rsp+11D0h+var_1188]
0x180015e8a  lea     rcx, [rbp+10D0h+var_1040]
0x180015e91  xor     edx, edx
0x180015e93  mov     [rsp+11D0h+var_11B0], rcx
0x180015e98  mov     rcx, r14
0x180015e9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015ea0  mov     ebx, eax
0x180015ea2  mov     ecx, ebx; this
0x180015ea4  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180015ea9  test    ebx, ebx
0x180015eab  jz      short loc_180015EBB
0x180015ead  mov     eax, r15d
0x180015eb0  mov     [rsp+11D0h+var_1188], r15d
0x180015eb5  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180015eb9  jmp     short loc_180015EBF
0x180015ebb  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180015ebf  mov     r8d, eax; unsigned __int64
0x180015ec2  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180015ec9  mov     r9d, 1000h; unsigned __int64
0x180015ecf  lea     rcx, [rsp+11D0h+var_1170]; this
0x180015ed4  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180015ed9  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180015edd  jnz     loc_1800160E7
0x180015ee3  lea     rax, ??_7?$__func@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@$$A6A_NPEAX131I@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180015eea  mov     [rbp+10D0h+var_1130], r15
0x180015eee  mov     [rbp+10D0h+var_10B8], rax
0x180015ef2  xorps   xmm0, xmm0
0x180015ef5  lea     rax, [rbp+10D0h+var_1130]
0x180015ef9  mov     [rbp+10D0h+var_111C], r15d
0x180015efd  mov     [rbp+10D0h+var_10B0], rax
0x180015f01  lea     rax, [rbp+10D0h+var_1128]
0x180015f05  mov     [rbp+10D0h+var_10A8], rax
0x180015f09  lea     rax, [rsp+11D0h+var_1170]
0x180015f0e  mov     [rbp+10D0h+var_10A0], rax
0x180015f12  lea     rax, [rbp+10D0h+var_10B8]
0x180015f16  mov     [rbp+10D0h+var_1050], rax
0x180015f1d  mov     rax, [rdi+18h]
0x180015f21  add     rax, 0Ah
0x180015f25  mov     [rbp+10D0h+var_1118], r15w
0x180015f2a  mov     [rsp+11D0h+var_1190], rax
0x180015f2f  movzx   eax, word ptr [rdi+2]
0x180015f33  mov     [rbp+10D0h+var_1120], ax
0x180015f37  mov     al, [rdi+4]
0x180015f3a  mov     [rbp+10D0h+var_111E], al
0x180015f3d  movzx   eax, word ptr [rdi+6]
0x180015f41  mov     [rbp+10D0h+var_1100], ax
0x180015f45  mov     al, [rdi+8]
0x180015f48  mov     [rbp+10D0h+var_10FE], al
0x180015f4b  movdqu  [rbp+10D0h+var_1110], xmm0
0x180015f50  mov     [rbp+10D0h+var_10FC], r15d
0x180015f54  mov     [rbp+10D0h+var_10F8], r15w
0x180015f59  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180015f5e  jmp     loc_180015FF6
0x180015f63  mov     esi, [rbp+10D0h+var_111C]
0x180015f66  mov     ebx, r15d
0x180015f69  test    esi, esi
0x180015f6b  jz      loc_180015FF6
0x180015f71  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180015f75  mov     r8, [rdi+20h]; unsigned __int8 *
0x180015f79  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180015f7e  lea     rcx, [rbp+10D0h+var_1100]; this
0x180015f82  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180015f87  test    al, al
0x180015f89  jz      short loc_180015FF3
0x180015f8b  mov     eax, [rbp+10D0h+var_10FC]
0x180015f8e  mov     rcx, [rbp+10D0h+var_1050]; this
0x180015f95  mov     [rsp+11D0h+var_1180], eax
0x180015f99  movzx   eax, [rbp+10D0h+var_10F8]
0x180015f9d  mov     [rbp+10D0h+var_10E0], rax
0x180015fa1  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180015fa5  mov     [rbp+10D0h+var_10D8], rax
0x180015fa9  movzx   eax, [rbp+10D0h+var_1118]
0x180015fad  mov     [rbp+10D0h+var_10D0], rax
0x180015fb1  mov     [rbp+10D0h+var_10C8], r15
0x180015fb5  test    rcx, rcx
0x180015fb8  jz      loc_180016132
0x180015fbe  mov     rax, [rcx]
0x180015fc1  lea     rdx, [rsp+11D0h+var_1180]
0x180015fc6  mov     [rsp+11D0h+var_11A8], rdx
0x180015fcb  lea     r9, [rbp+10D0h+var_10D8]
0x180015fcf  lea     rdx, [rbp+10D0h+var_10E0]
0x180015fd3  mov     [rsp+11D0h+var_11B0], rdx
0x180015fd8  lea     r8, [rbp+10D0h+var_10D0]
0x180015fdc  mov     rax, [rax+20h]
0x180015fe0  lea     rdx, [rbp+10D0h+var_10C8]
0x180015fe4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015fe9  test    al, al
0x180015feb  jz      short loc_180016063
0x180015fed  inc     ebx
0x180015fef  cmp     ebx, esi
0x180015ff1  jb      short loc_180015F75
0x180015ff3  xor     r15d, r15d
0x180015ff6  mov     r8, [rdi+20h]; unsigned __int8 *
0x180015ffa  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180015fff  lea     rcx, [rbp+10D0h+var_1120]; this
0x180016003  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180016008  test    al, al
0x18001600a  jnz     loc_180015F63
0x180016010  mov     rcx, [rbp+10D0h+var_1050]
0x180016017  test    rcx, rcx
0x18001601a  jz      short loc_180016028
0x18001601c  mov     rax, [rcx]
0x18001601f  mov     rax, [rax+18h]
0x180016023  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180016028  mov     bl, 1
0x18001602a  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18001602e  jz      short loc_1800160A5
0x180016030  mov     rdx, [rsp+11D0h+var_1158]
0x180016035  mov     rcx, r14
0x180016038  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18001603c  mov     eax, [rsp+11D0h+var_1188]
0x180016040  sub     r8d, edx
0x180016043  mov     [rsp+11D0h+var_11A0], 1
0x18001604b  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18001604f  call    wil_details_NtUpdateWnfStateData
0x180016054  cmp     eax, 0C0000001h
0x180016059  jnz     short loc_180016083
0x18001605b  inc     r12
0x18001605e  mov     bl, r15b
0x180016061  jmp     short loc_1800160B1
0x180016063  mov     rcx, [rbp+10D0h+var_1050]
0x18001606a  xor     r15d, r15d
0x18001606d  test    rcx, rcx
0x180016070  jz      short loc_18001607E
0x180016072  mov     rax, [rcx]
0x180016075  mov     rax, [rax+18h]
0x180016079  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001607e  mov     bl, r15b
0x180016081  jmp     short loc_18001602A
0x180016083  test    eax, eax
0x180016085  jz      short loc_1800160A5
0x180016087  mov     rdx, [rsp+11D0h+var_1158]
0x18001608c  mov     rcx, r14
0x18001608f  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180016093  sub     r8d, edx
0x180016096  mov     [rsp+11D0h+var_11A0], r15d
0x18001609b  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x1800160a0  call    wil_details_NtUpdateWnfStateData
0x1800160a5  mov     rax, [rbp+10D0h+var_1130]
0x1800160a9  add     r14, 8
0x1800160ad  mov     [rbp+10D0h+var_1128], rax
0x1800160b1  mov     rsi, [rbp+10D0h+lpMem]
0x1800160b5  mov     [rbp+10D0h+lpMem], r15
0x1800160b9  test    rsi, rsi
0x1800160bc  jz      short loc_1800160D2
0x1800160be  call    cs:__imp_GetProcessHeap
0x1800160c4  mov     r8, rsi; lpMem
0x1800160c7  xor     edx, edx; dwFlags
0x1800160c9  mov     rcx, rax; hHeap
0x1800160cc  call    cs:__imp_HeapFree
0x1800160d2  test    bl, bl
0x1800160d4  jnz     short loc_180016108
0x1800160d6  cmp     r14, r13
0x1800160d9  jnb     short loc_180016108
0x1800160db  cmp     r12, 32h ; '2'
0x1800160df  jb      loc_180015DB2
0x1800160e5  jmp     short loc_180016108
0x1800160e7  mov     rbx, [rbp+10D0h+lpMem]
0x1800160eb  mov     [rbp+10D0h+lpMem], r15
0x1800160ef  test    rbx, rbx
0x1800160f2  jz      short loc_180016108
0x1800160f4  call    cs:__imp_GetProcessHeap
0x1800160fa  mov     r8, rbx; lpMem
0x1800160fd  xor     edx, edx; dwFlags
0x1800160ff  mov     rcx, rax; hHeap
0x180016102  call    cs:__imp_HeapFree
0x180016108  mov     rcx, [rbp+10D0h+var_40]
0x18001610f  xor     rcx, rsp; StackCookie
0x180016112  call    __security_check_cookie
0x180016117  mov     rbx, [rsp+11D0h+arg_8]
0x18001611f  add     rsp, 11A0h
0x180016126  pop     r15
0x180016128  pop     r14
0x18001612a  pop     r13
0x18001612c  pop     r12
0x18001612e  pop     rdi
0x18001612f  pop     rsi
0x180016130  pop     rbp
0x180016131  retn
0x180016132  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
