# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800073bc`
- end: `0x180007794`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800068a4`

## callees

- `0x180001790`
- `0x180006358`
- `0x18000675c`
- `0x1800073bc`
- `0x180007ef4`
- `0x18000943c`
- `0x180009c70`
- `0x180032bf0`
- `0x180037010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000749c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000749c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074b3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800074b3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000771a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007750`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000771a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007750`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000775e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007728`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000775e`

## string_xrefs

- `0x180007495`: `ntdll.dll`

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
0x1800073bc  mov     [rsp-8+arg_8], rbx
0x1800073c1  push    rbp
0x1800073c2  push    rsi
0x1800073c3  push    rdi
0x1800073c4  push    r12
0x1800073c6  push    r13
0x1800073c8  push    r14
0x1800073ca  push    r15
0x1800073cc  lea     rbp, [rsp-10A0h]
0x1800073d4  mov     eax, 11A0h
0x1800073d9  call    _alloca_probe
0x1800073de  sub     rsp, rax
0x1800073e1  mov     rax, cs:__security_cookie
0x1800073e8  xor     rax, rsp
0x1800073eb  mov     [rbp+10D0h+var_40], rax
0x1800073f2  mov     rdi, r8
0x1800073f5  mov     r14, rcx
0x1800073f8  lea     r13, [rcx+rdx*8]
0x1800073fc  xor     r15d, r15d
0x1800073ff  mov     r12d, r15d
0x180007402  mov     [rbp+10D0h+var_1128], r15
0x180007406  mov     cl, [rdi+8]
0x180007409  movzx   edx, word ptr [rdi+6]
0x18000740d  movzx   eax, word ptr [rdi]
0x180007410  mov     [rsp+11D0h+var_1170], ax
0x180007415  movzx   eax, word ptr [rdi+2]
0x180007419  mov     [rsp+11D0h+var_116E], ax
0x18000741e  mov     al, [rdi+4]
0x180007421  mov     [rsp+11D0h+var_116C], al
0x180007425  mov     [rsp+11D0h+var_116A], dx
0x18000742a  mov     [rsp+11D0h+var_1168], cl
0x18000742e  test    dx, dx
0x180007431  jz      short loc_180007450
0x180007433  mov     eax, edx
0x180007435  cmp     cl, 1
0x180007438  jnz     short loc_180007440
0x18000743a  add     rax, 2
0x18000743e  jmp     short loc_180007449
0x180007440  cmp     cl, 2
0x180007443  jnz     short loc_180007449
0x180007445  add     rax, 4
0x180007449  mov     [rsp+11D0h+var_1160], rax
0x18000744e  jmp     short loc_180007455
0x180007450  mov     [rsp+11D0h+var_1160], r15
0x180007455  mov     [rsp+11D0h+var_1158], r15
0x18000745a  xorps   xmm0, xmm0
0x18000745d  movdqa  [rbp+10D0h+var_1150], xmm0
0x180007462  mov     [rbp+10D0h+lpMem], r15
0x180007466  mov     [rbp+10D0h+var_1138], 0
0x18000746c  mov     [rbp+10D0h+var_1136], r15b
0x180007470  mov     [rsp+11D0h+var_1188], r15d
0x180007475  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000747d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180007484  test    rax, rax
0x180007487  jnz     short loc_1800074CC
0x180007489  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007490  test    rax, rax
0x180007493  jnz     short loc_1800074A9
0x180007495  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x18000749c  call    cs:__imp_GetModuleHandleW
0x1800074a2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800074a9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800074b0  mov     rcx, rax; hModule
0x1800074b3  call    cs:__imp_GetProcAddress
0x1800074b9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800074c0  test    rax, rax
0x1800074c3  jnz     short loc_1800074CC
0x1800074c5  mov     ebx, 0C0000139h
0x1800074ca  jmp     short loc_1800074F6
0x1800074cc  lea     rcx, [rsp+11D0h+var_1190]
0x1800074d1  mov     [rsp+11D0h+var_11A8], rcx
0x1800074d6  lea     rcx, [rbp+10D0h+var_1040]
0x1800074dd  mov     [rsp+11D0h+var_11B0], rcx
0x1800074e2  lea     r9, [rsp+11D0h+var_1188]
0x1800074e7  xor     r8d, r8d
0x1800074ea  xor     edx, edx
0x1800074ec  mov     rcx, r14
0x1800074ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074f4  mov     ebx, eax
0x1800074f6  mov     ecx, ebx; this
0x1800074f8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800074fd  test    ebx, ebx
0x1800074ff  jz      short loc_18000750F
0x180007501  mov     eax, r15d
0x180007504  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180007508  mov     [rsp+11D0h+var_1188], r15d
0x18000750d  jmp     short loc_180007513
0x18000750f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180007513  mov     r8d, eax; unsigned __int64
0x180007516  mov     r9d, 1000h; unsigned __int64
0x18000751c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180007523  lea     rcx, [rsp+11D0h+var_1170]; this
0x180007528  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000752d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180007531  jnz     loc_180007743
0x180007537  mov     [rbp+10D0h+var_1130], r15
0x18000753b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180007542  mov     [rbp+10D0h+var_10B0], rax
0x180007546  lea     rax, [rbp+10D0h+var_1130]
0x18000754a  mov     [rbp+10D0h+var_10A8], rax
0x18000754e  lea     rax, [rbp+10D0h+var_1128]
0x180007552  mov     [rbp+10D0h+var_10A0], rax
0x180007556  lea     rax, [rsp+11D0h+var_1170]
0x18000755b  mov     [rbp+10D0h+var_1098], rax
0x18000755f  lea     rax, [rbp+10D0h+var_10B0]
0x180007563  mov     [rbp+10D0h+var_1048], rax
0x18000756a  lea     rax, [rbp+10D0h+var_10B8]
0x18000756e  mov     [rbp+10D0h+var_10C0], rax
0x180007572  mov     rax, [rdi+18h]
0x180007576  add     rax, 0Ah
0x18000757a  mov     [rsp+11D0h+var_1190], rax
0x18000757f  movzx   eax, word ptr [rdi+2]
0x180007583  mov     [rbp+10D0h+var_1120], ax
0x180007587  mov     al, [rdi+4]
0x18000758a  mov     [rbp+10D0h+var_111E], al
0x18000758d  mov     [rbp+10D0h+var_111C], r15d
0x180007591  mov     [rbp+10D0h+var_1118], r15w
0x180007596  xorps   xmm0, xmm0
0x180007599  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000759e  movzx   eax, word ptr [rdi+6]
0x1800075a2  mov     [rbp+10D0h+var_1100], ax
0x1800075a6  mov     al, [rdi+8]
0x1800075a9  mov     [rbp+10D0h+var_10FE], al
0x1800075ac  mov     [rbp+10D0h+var_10FC], r15d
0x1800075b0  mov     [rbp+10D0h+var_10F8], r15w
0x1800075b5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800075ba  jmp     loc_180007652
0x1800075bf  mov     ebx, r15d
0x1800075c2  mov     esi, [rbp+10D0h+var_111C]
0x1800075c5  test    esi, esi
0x1800075c7  jz      loc_180007652
0x1800075cd  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x1800075d1  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800075d5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800075da  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800075de  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800075e3  test    al, al
0x1800075e5  jz      short loc_18000764F
0x1800075e7  mov     eax, [rbp+10D0h+var_10FC]
0x1800075ea  mov     [rsp+11D0h+var_1180], eax
0x1800075ee  movzx   eax, [rbp+10D0h+var_10F8]
0x1800075f2  mov     [rbp+10D0h+var_10E0], rax
0x1800075f6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800075fa  mov     [rbp+10D0h+var_10D8], rax
0x1800075fe  movzx   eax, [rbp+10D0h+var_1118]
0x180007602  mov     [rbp+10D0h+var_10D0], rax
0x180007606  mov     [rbp+10D0h+var_10C8], r15
0x18000760a  mov     rcx, [rbp+10D0h+var_1048]; this
0x180007611  test    rcx, rcx
0x180007614  jz      loc_18000778E
0x18000761a  mov     rax, [rcx]
0x18000761d  lea     rdx, [rsp+11D0h+var_1180]
0x180007622  mov     [rsp+11D0h+var_11A8], rdx
0x180007627  lea     rdx, [rbp+10D0h+var_10E0]
0x18000762b  mov     [rsp+11D0h+var_11B0], rdx
0x180007630  lea     r9, [rbp+10D0h+var_10D8]
0x180007634  lea     r8, [rbp+10D0h+var_10D0]
0x180007638  lea     rdx, [rbp+10D0h+var_10C8]
0x18000763c  mov     rax, [rax+20h]
0x180007640  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007645  test    al, al
0x180007647  jz      short loc_1800076BF
0x180007649  inc     ebx
0x18000764b  cmp     ebx, esi
0x18000764d  jb      short loc_1800075D1
0x18000764f  xor     r15d, r15d
0x180007652  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007656  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000765b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000765f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007664  test    al, al
0x180007666  jnz     loc_1800075BF
0x18000766c  mov     rcx, [rbp+10D0h+var_1048]
0x180007673  test    rcx, rcx
0x180007676  jz      short loc_180007684
0x180007678  mov     rax, [rcx]
0x18000767b  mov     rax, [rax+18h]
0x18000767f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007684  mov     bl, 1
0x180007686  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000768a  jz      short loc_180007701
0x18000768c  mov     eax, [rsp+11D0h+var_1188]
0x180007690  mov     rdx, [rsp+11D0h+var_1158]
0x180007695  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007699  sub     r8d, edx
0x18000769c  mov     [rsp+11D0h+var_11A0], 1
0x1800076a4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800076a8  mov     rcx, r14
0x1800076ab  call    wil_details_NtUpdateWnfStateData
0x1800076b0  cmp     eax, 0C0000001h
0x1800076b5  jnz     short loc_1800076DF
0x1800076b7  inc     r12
0x1800076ba  mov     bl, r15b
0x1800076bd  jmp     short loc_18000770D
0x1800076bf  mov     rcx, [rbp+10D0h+var_1048]
0x1800076c6  xor     r15d, r15d
0x1800076c9  test    rcx, rcx
0x1800076cc  jz      short loc_1800076DA
0x1800076ce  mov     rax, [rcx]
0x1800076d1  mov     rax, [rax+18h]
0x1800076d5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800076da  mov     bl, r15b
0x1800076dd  jmp     short loc_180007686
0x1800076df  test    eax, eax
0x1800076e1  jz      short loc_180007701
0x1800076e3  mov     rdx, [rsp+11D0h+var_1158]
0x1800076e8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800076ec  sub     r8d, edx
0x1800076ef  mov     [rsp+11D0h+var_11A0], r15d
0x1800076f4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x1800076f9  mov     rcx, r14
0x1800076fc  call    wil_details_NtUpdateWnfStateData
0x180007701  add     r14, 8
0x180007705  mov     rax, [rbp+10D0h+var_1130]
0x180007709  mov     [rbp+10D0h+var_1128], rax
0x18000770d  mov     rsi, [rbp+10D0h+lpMem]
0x180007711  mov     [rbp+10D0h+lpMem], r15
0x180007715  test    rsi, rsi
0x180007718  jz      short loc_18000772E
0x18000771a  call    cs:__imp_GetProcessHeap
0x180007720  mov     rcx, rax; hHeap
0x180007723  mov     r8, rsi; lpMem
0x180007726  xor     edx, edx; dwFlags
0x180007728  call    cs:__imp_HeapFree
0x18000772e  test    bl, bl
0x180007730  jnz     short loc_180007764
0x180007732  cmp     r14, r13
0x180007735  jnb     short loc_180007764
0x180007737  cmp     r12, 32h ; '2'
0x18000773b  jb      loc_180007406
0x180007741  jmp     short loc_180007764
0x180007743  mov     rbx, [rbp+10D0h+lpMem]
0x180007747  mov     [rbp+10D0h+lpMem], r15
0x18000774b  test    rbx, rbx
0x18000774e  jz      short loc_180007764
0x180007750  call    cs:__imp_GetProcessHeap
0x180007756  mov     rcx, rax; hHeap
0x180007759  mov     r8, rbx; lpMem
0x18000775c  xor     edx, edx; dwFlags
0x18000775e  call    cs:__imp_HeapFree
0x180007764  mov     rcx, [rbp+10D0h+var_40]
0x18000776b  xor     rcx, rsp; StackCookie
0x18000776e  call    __security_check_cookie
0x180007773  mov     rbx, [rsp+11D0h+arg_8]
0x18000777b  add     rsp, 11A0h
0x180007782  pop     r15
0x180007784  pop     r14
0x180007786  pop     r13
0x180007788  pop     r12
0x18000778a  pop     rdi
0x18000778b  pop     rsi
0x18000778c  pop     rbp
0x18000778d  retn
0x18000778e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
