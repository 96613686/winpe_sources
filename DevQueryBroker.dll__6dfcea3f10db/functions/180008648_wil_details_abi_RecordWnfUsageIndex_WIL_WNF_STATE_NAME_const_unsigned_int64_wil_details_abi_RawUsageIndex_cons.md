# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180008648`
- end: `0x180008a15`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180007d7c`

## callees

- `0x180007938`
- `0x180007c8c`
- `0x180008648`
- `0x18000900c`
- `0x180009c9c`
- `0x18000a048`
- `0x18000a1d0`
- `0x18000a260`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000873e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000873e`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008727`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008727`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089df`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089a9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800089df`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000899b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089d1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000899b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800089d1`

## string_xrefs

- `0x180008720`: `ntdll.dll`

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
0x180008648  mov     [rsp-8+arg_8], rbx
0x18000864d  push    rbp
0x18000864e  push    rsi
0x18000864f  push    rdi
0x180008650  push    r12
0x180008652  push    r13
0x180008654  push    r14
0x180008656  push    r15
0x180008658  lea     rbp, [rsp-10A0h]
0x180008660  mov     eax, 11A0h
0x180008665  call    _alloca_probe
0x18000866a  sub     rsp, rax
0x18000866d  mov     rax, cs:__security_cookie
0x180008674  xor     rax, rsp
0x180008677  mov     [rbp+10D0h+var_40], rax
0x18000867e  xor     r13d, r13d
0x180008681  lea     r12, [rcx+rdx*8]
0x180008685  mov     r15d, r13d
0x180008688  mov     [rbp+10D0h+var_1128], r13
0x18000868c  mov     rdi, r8
0x18000868f  mov     r14, rcx
0x180008692  movzx   eax, word ptr [rdi]
0x180008695  movzx   edx, word ptr [rdi+6]
0x180008699  mov     cl, [rdi+8]
0x18000869c  mov     [rsp+11D0h+var_1170], ax
0x1800086a1  movzx   eax, word ptr [rdi+2]
0x1800086a5  mov     [rsp+11D0h+var_116E], ax
0x1800086aa  mov     al, [rdi+4]
0x1800086ad  mov     [rsp+11D0h+var_116C], al
0x1800086b1  mov     [rsp+11D0h+var_116A], dx
0x1800086b6  mov     [rsp+11D0h+var_1168], cl
0x1800086ba  test    dx, dx
0x1800086bd  jz      short loc_1800086DC
0x1800086bf  mov     eax, edx
0x1800086c1  cmp     cl, 1
0x1800086c4  jnz     short loc_1800086CC
0x1800086c6  add     rax, 2
0x1800086ca  jmp     short loc_1800086D5
0x1800086cc  cmp     cl, 2
0x1800086cf  jnz     short loc_1800086D5
0x1800086d1  add     rax, 4
0x1800086d5  mov     [rsp+11D0h+var_1160], rax
0x1800086da  jmp     short loc_1800086E1
0x1800086dc  mov     [rsp+11D0h+var_1160], r13
0x1800086e1  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800086e8  xorps   xmm0, xmm0
0x1800086eb  mov     [rsp+11D0h+var_1158], r13
0x1800086f0  movdqa  [rbp+10D0h+var_1150], xmm0
0x1800086f5  mov     [rbp+10D0h+lpMem], r13
0x1800086f9  mov     [rbp+10D0h+var_1138], r13w
0x1800086fe  mov     [rbp+10D0h+var_1136], r13b
0x180008702  mov     [rsp+11D0h+var_1188], r13d
0x180008707  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000870f  test    rax, rax
0x180008712  jnz     short loc_180008757
0x180008714  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000871b  test    rax, rax
0x18000871e  jnz     short loc_180008734
0x180008720  lea     rcx, ModuleName; "ntdll.dll"
0x180008727  call    cs:__imp_GetModuleHandleW
0x18000872d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008734  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000873b  mov     rcx, rax; hModule
0x18000873e  call    cs:__imp_GetProcAddress
0x180008744  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000874b  test    rax, rax
0x18000874e  jnz     short loc_180008757
0x180008750  mov     ebx, 0C0000139h
0x180008755  jmp     short loc_180008781
0x180008757  lea     rcx, [rsp+11D0h+var_1190]
0x18000875c  xor     r8d, r8d
0x18000875f  mov     [rsp+11D0h+var_11A8], rcx
0x180008764  lea     r9, [rsp+11D0h+var_1188]
0x180008769  lea     rcx, [rbp+10D0h+var_1040]
0x180008770  xor     edx, edx
0x180008772  mov     [rsp+11D0h+var_11B0], rcx
0x180008777  mov     rcx, r14
0x18000877a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000877f  mov     ebx, eax
0x180008781  mov     ecx, ebx; this
0x180008783  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180008788  test    ebx, ebx
0x18000878a  jz      short loc_18000879A
0x18000878c  mov     eax, r13d
0x18000878f  mov     [rsp+11D0h+var_1188], r13d
0x180008794  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180008798  jmp     short loc_18000879E
0x18000879a  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000879e  mov     r8d, eax; unsigned __int64
0x1800087a1  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1800087a8  mov     r9d, 1000h; unsigned __int64
0x1800087ae  lea     rcx, [rsp+11D0h+var_1170]; this
0x1800087b3  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1800087b8  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x1800087bc  jnz     loc_1800089C4
0x1800087c2  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800087c9  mov     [rbp+10D0h+var_1130], r13
0x1800087cd  mov     [rbp+10D0h+var_10B8], rax
0x1800087d1  xorps   xmm0, xmm0
0x1800087d4  lea     rax, [rbp+10D0h+var_1130]
0x1800087d8  mov     [rbp+10D0h+var_111C], r13d
0x1800087dc  mov     [rbp+10D0h+var_10B0], rax
0x1800087e0  lea     rax, [rbp+10D0h+var_1128]
0x1800087e4  mov     [rbp+10D0h+var_10A8], rax
0x1800087e8  lea     rax, [rsp+11D0h+var_1170]
0x1800087ed  mov     [rbp+10D0h+var_10A0], rax
0x1800087f1  lea     rax, [rbp+10D0h+var_10B8]
0x1800087f5  mov     [rbp+10D0h+var_1050], rax
0x1800087fc  mov     rax, [rdi+18h]
0x180008800  add     rax, 0Ah
0x180008804  mov     [rbp+10D0h+var_1118], r13w
0x180008809  mov     [rsp+11D0h+var_1190], rax
0x18000880e  movzx   eax, word ptr [rdi+2]
0x180008812  mov     [rbp+10D0h+var_1120], ax
0x180008816  mov     al, [rdi+4]
0x180008819  mov     [rbp+10D0h+var_111E], al
0x18000881c  movzx   eax, word ptr [rdi+6]
0x180008820  mov     [rbp+10D0h+var_1100], ax
0x180008824  mov     al, [rdi+8]
0x180008827  mov     [rbp+10D0h+var_10FE], al
0x18000882a  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000882f  mov     [rbp+10D0h+var_10FC], r13d
0x180008833  mov     [rbp+10D0h+var_10F8], r13w
0x180008838  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000883d  jmp     loc_1800088D6
0x180008842  mov     ebx, r13d
0x180008845  cmp     [rbp+10D0h+var_111C], r13d
0x180008849  jbe     loc_1800088D6
0x18000884f  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008853  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180008858  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000885c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008861  test    al, al
0x180008863  jz      short loc_1800088D6
0x180008865  mov     eax, [rbp+10D0h+var_10FC]
0x180008868  mov     rcx, [rbp+10D0h+var_1050]; this
0x18000886f  mov     [rsp+11D0h+var_1180], eax
0x180008873  movzx   eax, [rbp+10D0h+var_10F8]
0x180008877  mov     [rbp+10D0h+var_10E0], rax
0x18000887b  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000887f  mov     [rbp+10D0h+var_10D8], rax
0x180008883  movzx   eax, [rbp+10D0h+var_1118]
0x180008887  mov     [rbp+10D0h+var_10D0], rax
0x18000888b  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000888f  mov     [rbp+10D0h+var_10C8], rax
0x180008893  test    rcx, rcx
0x180008896  jz      loc_180008A0F
0x18000889c  mov     rax, [rcx]
0x18000889f  lea     rdx, [rsp+11D0h+var_1180]
0x1800088a4  mov     [rsp+11D0h+var_11A8], rdx
0x1800088a9  lea     r9, [rbp+10D0h+var_10D8]
0x1800088ad  lea     rdx, [rbp+10D0h+var_10E0]
0x1800088b1  mov     [rsp+11D0h+var_11B0], rdx
0x1800088b6  lea     r8, [rbp+10D0h+var_10D0]
0x1800088ba  mov     rax, [rax+20h]
0x1800088be  lea     rdx, [rbp+10D0h+var_10C8]
0x1800088c2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800088c7  test    al, al
0x1800088c9  jz      short loc_180008943
0x1800088cb  inc     ebx
0x1800088cd  cmp     ebx, [rbp+10D0h+var_111C]
0x1800088d0  jb      loc_18000884F
0x1800088d6  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800088da  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800088df  lea     rcx, [rbp+10D0h+var_1120]; this
0x1800088e3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800088e8  test    al, al
0x1800088ea  jnz     loc_180008842
0x1800088f0  mov     rcx, [rbp+10D0h+var_1050]
0x1800088f7  test    rcx, rcx
0x1800088fa  jz      short loc_180008908
0x1800088fc  mov     rax, [rcx]
0x1800088ff  mov     rax, [rax+18h]
0x180008903  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008908  mov     bl, 1
0x18000890a  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18000890e  jz      short loc_180008982
0x180008910  mov     rdx, [rsp+11D0h+var_1158]
0x180008915  mov     rcx, r14
0x180008918  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000891c  mov     eax, [rsp+11D0h+var_1188]
0x180008920  sub     r8d, edx
0x180008923  mov     [rsp+11D0h+var_11A0], 1
0x18000892b  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000892f  call    wil_details_NtUpdateWnfStateData
0x180008934  cmp     eax, 0C0000001h
0x180008939  jnz     short loc_180008960
0x18000893b  inc     r15
0x18000893e  mov     bl, r13b
0x180008941  jmp     short loc_18000898E
0x180008943  mov     rcx, [rbp+10D0h+var_1050]
0x18000894a  test    rcx, rcx
0x18000894d  jz      short loc_18000895B
0x18000894f  mov     rax, [rcx]
0x180008952  mov     rax, [rax+18h]
0x180008956  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000895b  mov     bl, r13b
0x18000895e  jmp     short loc_18000890A
0x180008960  test    eax, eax
0x180008962  jz      short loc_180008982
0x180008964  mov     rdx, [rsp+11D0h+var_1158]
0x180008969  mov     rcx, r14
0x18000896c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180008970  sub     r8d, edx
0x180008973  mov     [rsp+11D0h+var_11A0], r13d
0x180008978  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000897d  call    wil_details_NtUpdateWnfStateData
0x180008982  mov     rax, [rbp+10D0h+var_1130]
0x180008986  add     r14, 8
0x18000898a  mov     [rbp+10D0h+var_1128], rax
0x18000898e  mov     rsi, [rbp+10D0h+lpMem]
0x180008992  mov     [rbp+10D0h+lpMem], r13
0x180008996  test    rsi, rsi
0x180008999  jz      short loc_1800089AF
0x18000899b  call    cs:__imp_GetProcessHeap
0x1800089a1  mov     r8, rsi; lpMem
0x1800089a4  xor     edx, edx; dwFlags
0x1800089a6  mov     rcx, rax; hHeap
0x1800089a9  call    cs:__imp_HeapFree
0x1800089af  test    bl, bl
0x1800089b1  jnz     short loc_1800089E5
0x1800089b3  cmp     r14, r12
0x1800089b6  jnb     short loc_1800089E5
0x1800089b8  cmp     r15, 32h ; '2'
0x1800089bc  jb      loc_180008692
0x1800089c2  jmp     short loc_1800089E5
0x1800089c4  mov     rbx, [rbp+10D0h+lpMem]
0x1800089c8  mov     [rbp+10D0h+lpMem], r13
0x1800089cc  test    rbx, rbx
0x1800089cf  jz      short loc_1800089E5
0x1800089d1  call    cs:__imp_GetProcessHeap
0x1800089d7  mov     r8, rbx; lpMem
0x1800089da  xor     edx, edx; dwFlags
0x1800089dc  mov     rcx, rax; hHeap
0x1800089df  call    cs:__imp_HeapFree
0x1800089e5  mov     rcx, [rbp+10D0h+var_40]
0x1800089ec  xor     rcx, rsp; StackCookie
0x1800089ef  call    __security_check_cookie
0x1800089f4  mov     rbx, [rsp+11D0h+arg_8]
0x1800089fc  add     rsp, 11A0h
0x180008a03  pop     r15
0x180008a05  pop     r14
0x180008a07  pop     r13
0x180008a09  pop     r12
0x180008a0b  pop     rdi
0x180008a0c  pop     rsi
0x180008a0d  pop     rbp
0x180008a0e  retn
0x180008a0f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
