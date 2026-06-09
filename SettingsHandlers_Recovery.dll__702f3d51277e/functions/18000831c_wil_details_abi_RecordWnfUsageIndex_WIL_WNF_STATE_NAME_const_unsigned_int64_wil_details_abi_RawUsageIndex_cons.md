# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000831c`
- end: `0x1800086f4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180007804`

## callees

- `0x180002350`
- `0x180007238`
- `0x1800076bc`
- `0x18000831c`
- `0x180008f34`
- `0x18000a48c`
- `0x18000acb0`
- `0x1800291b0`
- `0x18002b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008413`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008413`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800083fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800083fc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000867a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000867a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800086b0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008688`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008688`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800086be`

## string_xrefs

- `0x1800083f5`: `ntdll.dll`

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
0x18000831c  mov     [rsp-8+arg_8], rbx
0x180008321  push    rbp
0x180008322  push    rsi
0x180008323  push    rdi
0x180008324  push    r12
0x180008326  push    r13
0x180008328  push    r14
0x18000832a  push    r15
0x18000832c  lea     rbp, [rsp-10A0h]
0x180008334  mov     eax, 11A0h
0x180008339  call    _alloca_probe
0x18000833e  sub     rsp, rax
0x180008341  mov     rax, cs:__security_cookie
0x180008348  xor     rax, rsp
0x18000834b  mov     [rbp+10D0h+var_40], rax
0x180008352  mov     rdi, r8
0x180008355  mov     r14, rcx
0x180008358  lea     r13, [rcx+rdx*8]
0x18000835c  xor     r15d, r15d
0x18000835f  mov     r12d, r15d
0x180008362  mov     [rbp+10D0h+var_1128], r15
0x180008366  mov     cl, [rdi+8]
0x180008369  movzx   edx, word ptr [rdi+6]
0x18000836d  movzx   eax, word ptr [rdi]
0x180008370  mov     [rsp+11D0h+var_1170], ax
0x180008375  movzx   eax, word ptr [rdi+2]
0x180008379  mov     [rsp+11D0h+var_116E], ax
0x18000837e  mov     al, [rdi+4]
0x180008381  mov     [rsp+11D0h+var_116C], al
0x180008385  mov     [rsp+11D0h+var_116A], dx
0x18000838a  mov     [rsp+11D0h+var_1168], cl
0x18000838e  test    dx, dx
0x180008391  jz      short loc_1800083B0
0x180008393  mov     eax, edx
0x180008395  cmp     cl, 1
0x180008398  jnz     short loc_1800083A0
0x18000839a  add     rax, 2
0x18000839e  jmp     short loc_1800083A9
0x1800083a0  cmp     cl, 2
0x1800083a3  jnz     short loc_1800083A9
0x1800083a5  add     rax, 4
0x1800083a9  mov     [rsp+11D0h+var_1160], rax
0x1800083ae  jmp     short loc_1800083B5
0x1800083b0  mov     [rsp+11D0h+var_1160], r15
0x1800083b5  mov     [rsp+11D0h+var_1158], r15
0x1800083ba  xorps   xmm0, xmm0
0x1800083bd  movdqa  [rbp+10D0h+var_1150], xmm0
0x1800083c2  mov     [rbp+10D0h+lpMem], r15
0x1800083c6  mov     [rbp+10D0h+var_1138], 0
0x1800083cc  mov     [rbp+10D0h+var_1136], r15b
0x1800083d0  mov     [rsp+11D0h+var_1188], r15d
0x1800083d5  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1800083dd  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800083e4  test    rax, rax
0x1800083e7  jnz     short loc_18000842C
0x1800083e9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800083f0  test    rax, rax
0x1800083f3  jnz     short loc_180008409
0x1800083f5  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800083fc  call    cs:__imp_GetModuleHandleW
0x180008402  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008409  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008410  mov     rcx, rax; hModule
0x180008413  call    cs:__imp_GetProcAddress
0x180008419  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008420  test    rax, rax
0x180008423  jnz     short loc_18000842C
0x180008425  mov     ebx, 0C0000139h
0x18000842a  jmp     short loc_180008456
0x18000842c  lea     rcx, [rsp+11D0h+var_1190]
0x180008431  mov     [rsp+11D0h+var_11A8], rcx
0x180008436  lea     rcx, [rbp+10D0h+var_1040]
0x18000843d  mov     [rsp+11D0h+var_11B0], rcx
0x180008442  lea     r9, [rsp+11D0h+var_1188]
0x180008447  xor     r8d, r8d
0x18000844a  xor     edx, edx
0x18000844c  mov     rcx, r14
0x18000844f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008454  mov     ebx, eax
0x180008456  mov     ecx, ebx; this
0x180008458  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000845d  test    ebx, ebx
0x18000845f  jz      short loc_18000846F
0x180008461  mov     eax, r15d
0x180008464  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180008468  mov     [rsp+11D0h+var_1188], r15d
0x18000846d  jmp     short loc_180008473
0x18000846f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180008473  mov     r8d, eax; unsigned __int64
0x180008476  mov     r9d, 1000h; unsigned __int64
0x18000847c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180008483  lea     rcx, [rsp+11D0h+var_1170]; this
0x180008488  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000848d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180008491  jnz     loc_1800086A3
0x180008497  mov     [rbp+10D0h+var_1130], r15
0x18000849b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800084a2  mov     [rbp+10D0h+var_10B0], rax
0x1800084a6  lea     rax, [rbp+10D0h+var_1130]
0x1800084aa  mov     [rbp+10D0h+var_10A8], rax
0x1800084ae  lea     rax, [rbp+10D0h+var_1128]
0x1800084b2  mov     [rbp+10D0h+var_10A0], rax
0x1800084b6  lea     rax, [rsp+11D0h+var_1170]
0x1800084bb  mov     [rbp+10D0h+var_1098], rax
0x1800084bf  lea     rax, [rbp+10D0h+var_10B0]
0x1800084c3  mov     [rbp+10D0h+var_1048], rax
0x1800084ca  lea     rax, [rbp+10D0h+var_10B8]
0x1800084ce  mov     [rbp+10D0h+var_10C0], rax
0x1800084d2  mov     rax, [rdi+18h]
0x1800084d6  add     rax, 0Ah
0x1800084da  mov     [rsp+11D0h+var_1190], rax
0x1800084df  movzx   eax, word ptr [rdi+2]
0x1800084e3  mov     [rbp+10D0h+var_1120], ax
0x1800084e7  mov     al, [rdi+4]
0x1800084ea  mov     [rbp+10D0h+var_111E], al
0x1800084ed  mov     [rbp+10D0h+var_111C], r15d
0x1800084f1  mov     [rbp+10D0h+var_1118], r15w
0x1800084f6  xorps   xmm0, xmm0
0x1800084f9  movdqu  [rbp+10D0h+var_1110], xmm0
0x1800084fe  movzx   eax, word ptr [rdi+6]
0x180008502  mov     [rbp+10D0h+var_1100], ax
0x180008506  mov     al, [rdi+8]
0x180008509  mov     [rbp+10D0h+var_10FE], al
0x18000850c  mov     [rbp+10D0h+var_10FC], r15d
0x180008510  mov     [rbp+10D0h+var_10F8], r15w
0x180008515  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000851a  jmp     loc_1800085B2
0x18000851f  mov     ebx, r15d
0x180008522  mov     esi, [rbp+10D0h+var_111C]
0x180008525  test    esi, esi
0x180008527  jz      loc_1800085B2
0x18000852d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180008531  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008535  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000853a  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000853e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008543  test    al, al
0x180008545  jz      short loc_1800085AF
0x180008547  mov     eax, [rbp+10D0h+var_10FC]
0x18000854a  mov     [rsp+11D0h+var_1180], eax
0x18000854e  movzx   eax, [rbp+10D0h+var_10F8]
0x180008552  mov     [rbp+10D0h+var_10E0], rax
0x180008556  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000855a  mov     [rbp+10D0h+var_10D8], rax
0x18000855e  movzx   eax, [rbp+10D0h+var_1118]
0x180008562  mov     [rbp+10D0h+var_10D0], rax
0x180008566  mov     [rbp+10D0h+var_10C8], r15
0x18000856a  mov     rcx, [rbp+10D0h+var_1048]; this
0x180008571  test    rcx, rcx
0x180008574  jz      loc_1800086EE
0x18000857a  mov     rax, [rcx]
0x18000857d  lea     rdx, [rsp+11D0h+var_1180]
0x180008582  mov     [rsp+11D0h+var_11A8], rdx
0x180008587  lea     rdx, [rbp+10D0h+var_10E0]
0x18000858b  mov     [rsp+11D0h+var_11B0], rdx
0x180008590  lea     r9, [rbp+10D0h+var_10D8]
0x180008594  lea     r8, [rbp+10D0h+var_10D0]
0x180008598  lea     rdx, [rbp+10D0h+var_10C8]
0x18000859c  mov     rax, [rax+20h]
0x1800085a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085a5  test    al, al
0x1800085a7  jz      short loc_18000861F
0x1800085a9  inc     ebx
0x1800085ab  cmp     ebx, esi
0x1800085ad  jb      short loc_180008531
0x1800085af  xor     r15d, r15d
0x1800085b2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800085b6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800085bb  lea     rcx, [rbp+10D0h+var_1120]; this
0x1800085bf  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800085c4  test    al, al
0x1800085c6  jnz     loc_18000851F
0x1800085cc  mov     rcx, [rbp+10D0h+var_1048]
0x1800085d3  test    rcx, rcx
0x1800085d6  jz      short loc_1800085E4
0x1800085d8  mov     rax, [rcx]
0x1800085db  mov     rax, [rax+18h]
0x1800085df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800085e4  mov     bl, 1
0x1800085e6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x1800085ea  jz      short loc_180008661
0x1800085ec  mov     eax, [rsp+11D0h+var_1188]
0x1800085f0  mov     rdx, [rsp+11D0h+var_1158]
0x1800085f5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800085f9  sub     r8d, edx
0x1800085fc  mov     [rsp+11D0h+var_11A0], 1
0x180008604  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180008608  mov     rcx, r14
0x18000860b  call    wil_details_NtUpdateWnfStateData
0x180008610  cmp     eax, 0C0000001h
0x180008615  jnz     short loc_18000863F
0x180008617  inc     r12
0x18000861a  mov     bl, r15b
0x18000861d  jmp     short loc_18000866D
0x18000861f  mov     rcx, [rbp+10D0h+var_1048]
0x180008626  xor     r15d, r15d
0x180008629  test    rcx, rcx
0x18000862c  jz      short loc_18000863A
0x18000862e  mov     rax, [rcx]
0x180008631  mov     rax, [rax+18h]
0x180008635  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000863a  mov     bl, r15b
0x18000863d  jmp     short loc_1800085E6
0x18000863f  test    eax, eax
0x180008641  jz      short loc_180008661
0x180008643  mov     rdx, [rsp+11D0h+var_1158]
0x180008648  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000864c  sub     r8d, edx
0x18000864f  mov     [rsp+11D0h+var_11A0], r15d
0x180008654  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180008659  mov     rcx, r14
0x18000865c  call    wil_details_NtUpdateWnfStateData
0x180008661  add     r14, 8
0x180008665  mov     rax, [rbp+10D0h+var_1130]
0x180008669  mov     [rbp+10D0h+var_1128], rax
0x18000866d  mov     rsi, [rbp+10D0h+lpMem]
0x180008671  mov     [rbp+10D0h+lpMem], r15
0x180008675  test    rsi, rsi
0x180008678  jz      short loc_18000868E
0x18000867a  call    cs:__imp_GetProcessHeap
0x180008680  mov     rcx, rax; hHeap
0x180008683  mov     r8, rsi; lpMem
0x180008686  xor     edx, edx; dwFlags
0x180008688  call    cs:__imp_HeapFree
0x18000868e  test    bl, bl
0x180008690  jnz     short loc_1800086C4
0x180008692  cmp     r14, r13
0x180008695  jnb     short loc_1800086C4
0x180008697  cmp     r12, 32h ; '2'
0x18000869b  jb      loc_180008366
0x1800086a1  jmp     short loc_1800086C4
0x1800086a3  mov     rbx, [rbp+10D0h+lpMem]
0x1800086a7  mov     [rbp+10D0h+lpMem], r15
0x1800086ab  test    rbx, rbx
0x1800086ae  jz      short loc_1800086C4
0x1800086b0  call    cs:__imp_GetProcessHeap
0x1800086b6  mov     rcx, rax; hHeap
0x1800086b9  mov     r8, rbx; lpMem
0x1800086bc  xor     edx, edx; dwFlags
0x1800086be  call    cs:__imp_HeapFree
0x1800086c4  mov     rcx, [rbp+10D0h+var_40]
0x1800086cb  xor     rcx, rsp; StackCookie
0x1800086ce  call    __security_check_cookie
0x1800086d3  mov     rbx, [rsp+11D0h+arg_8]
0x1800086db  add     rsp, 11A0h
0x1800086e2  pop     r15
0x1800086e4  pop     r14
0x1800086e6  pop     r13
0x1800086e8  pop     r12
0x1800086ea  pop     rdi
0x1800086eb  pop     rsi
0x1800086ec  pop     rbp
0x1800086ed  retn
0x1800086ee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
