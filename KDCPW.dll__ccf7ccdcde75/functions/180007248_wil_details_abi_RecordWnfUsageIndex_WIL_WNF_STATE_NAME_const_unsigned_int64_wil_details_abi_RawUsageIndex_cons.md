# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180007248`
- end: `0x180007618`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `976`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180006744`

## callees

- `0x180001630`
- `0x180006088`
- `0x180006644`
- `0x180007248`
- `0x180007ee8`
- `0x180008eac`
- `0x180009a20`
- `0x18000ca90`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000733f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000733f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007328`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007328`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075e2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075ac`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800075e2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000759e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075d4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000759e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800075d4`

## string_xrefs

- `0x180007321`: `ntdll.dll`

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
    v57[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
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
0x180007248  mov     [rsp-8+arg_8], rbx
0x18000724d  push    rbp
0x18000724e  push    rsi
0x18000724f  push    rdi
0x180007250  push    r12
0x180007252  push    r13
0x180007254  push    r14
0x180007256  push    r15
0x180007258  lea     rbp, [rsp-10A0h]
0x180007260  mov     eax, 11A0h
0x180007265  call    _alloca_probe
0x18000726a  sub     rsp, rax
0x18000726d  mov     rax, cs:__security_cookie
0x180007274  xor     rax, rsp
0x180007277  mov     [rbp+10D0h+var_40], rax
0x18000727e  xor     r15d, r15d
0x180007281  lea     r13, [rcx+rdx*8]
0x180007285  mov     r12d, r15d
0x180007288  mov     [rbp+10D0h+var_1128], r15
0x18000728c  mov     rdi, r8
0x18000728f  mov     r14, rcx
0x180007292  movzx   eax, word ptr [rdi]
0x180007295  movzx   edx, word ptr [rdi+6]
0x180007299  mov     cl, [rdi+8]
0x18000729c  mov     [rsp+11D0h+var_1170], ax
0x1800072a1  movzx   eax, word ptr [rdi+2]
0x1800072a5  mov     [rsp+11D0h+var_116E], ax
0x1800072aa  mov     al, [rdi+4]
0x1800072ad  mov     [rsp+11D0h+var_116C], al
0x1800072b1  mov     [rsp+11D0h+var_116A], dx
0x1800072b6  mov     [rsp+11D0h+var_1168], cl
0x1800072ba  test    dx, dx
0x1800072bd  jz      short loc_1800072DC
0x1800072bf  mov     eax, edx
0x1800072c1  cmp     cl, 1
0x1800072c4  jnz     short loc_1800072CC
0x1800072c6  add     rax, 2
0x1800072ca  jmp     short loc_1800072D5
0x1800072cc  cmp     cl, 2
0x1800072cf  jnz     short loc_1800072D5
0x1800072d1  add     rax, 4
0x1800072d5  mov     [rsp+11D0h+var_1160], rax
0x1800072da  jmp     short loc_1800072E1
0x1800072dc  mov     [rsp+11D0h+var_1160], r15
0x1800072e1  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800072e8  xorps   xmm0, xmm0
0x1800072eb  mov     [rsp+11D0h+var_1158], r15
0x1800072f0  movdqa  [rbp+10D0h+var_1150], xmm0
0x1800072f5  mov     [rbp+10D0h+lpMem], r15
0x1800072f9  mov     [rbp+10D0h+var_1138], 0
0x1800072ff  mov     [rbp+10D0h+var_1136], r15b
0x180007303  mov     [rsp+11D0h+var_1188], r15d
0x180007308  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180007310  test    rax, rax
0x180007313  jnz     short loc_180007358
0x180007315  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000731c  test    rax, rax
0x18000731f  jnz     short loc_180007335
0x180007321  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180007328  call    cs:__imp_GetModuleHandleW
0x18000732e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007335  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000733c  mov     rcx, rax; hModule
0x18000733f  call    cs:__imp_GetProcAddress
0x180007345  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000734c  test    rax, rax
0x18000734f  jnz     short loc_180007358
0x180007351  mov     ebx, 0C0000139h
0x180007356  jmp     short loc_180007382
0x180007358  lea     rcx, [rsp+11D0h+var_1190]
0x18000735d  xor     r8d, r8d
0x180007360  mov     [rsp+11D0h+var_11A8], rcx
0x180007365  lea     r9, [rsp+11D0h+var_1188]
0x18000736a  lea     rcx, [rbp+10D0h+var_1040]
0x180007371  xor     edx, edx
0x180007373  mov     [rsp+11D0h+var_11B0], rcx
0x180007378  mov     rcx, r14
0x18000737b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007380  mov     ebx, eax
0x180007382  mov     ecx, ebx; this
0x180007384  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180007389  test    ebx, ebx
0x18000738b  jz      short loc_18000739B
0x18000738d  mov     eax, r15d
0x180007390  mov     [rsp+11D0h+var_1188], r15d
0x180007395  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180007399  jmp     short loc_18000739F
0x18000739b  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000739f  mov     r8d, eax; unsigned __int64
0x1800073a2  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1800073a9  mov     r9d, 1000h; unsigned __int64
0x1800073af  lea     rcx, [rsp+11D0h+var_1170]; this
0x1800073b4  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1800073b9  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x1800073bd  jnz     loc_1800075C7
0x1800073c3  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800073ca  mov     [rbp+10D0h+var_1130], r15
0x1800073ce  mov     [rbp+10D0h+var_10B8], rax
0x1800073d2  xorps   xmm0, xmm0
0x1800073d5  lea     rax, [rbp+10D0h+var_1130]
0x1800073d9  mov     [rbp+10D0h+var_111C], r15d
0x1800073dd  mov     [rbp+10D0h+var_10B0], rax
0x1800073e1  lea     rax, [rbp+10D0h+var_1128]
0x1800073e5  mov     [rbp+10D0h+var_10A8], rax
0x1800073e9  lea     rax, [rsp+11D0h+var_1170]
0x1800073ee  mov     [rbp+10D0h+var_10A0], rax
0x1800073f2  lea     rax, [rbp+10D0h+var_10B8]
0x1800073f6  mov     [rbp+10D0h+var_1050], rax
0x1800073fd  mov     rax, [rdi+18h]
0x180007401  add     rax, 0Ah
0x180007405  mov     [rbp+10D0h+var_1118], r15w
0x18000740a  mov     [rsp+11D0h+var_1190], rax
0x18000740f  movzx   eax, word ptr [rdi+2]
0x180007413  mov     [rbp+10D0h+var_1120], ax
0x180007417  mov     al, [rdi+4]
0x18000741a  mov     [rbp+10D0h+var_111E], al
0x18000741d  movzx   eax, word ptr [rdi+6]
0x180007421  mov     [rbp+10D0h+var_1100], ax
0x180007425  mov     al, [rdi+8]
0x180007428  mov     [rbp+10D0h+var_10FE], al
0x18000742b  movdqu  [rbp+10D0h+var_1110], xmm0
0x180007430  mov     [rbp+10D0h+var_10FC], r15d
0x180007434  mov     [rbp+10D0h+var_10F8], r15w
0x180007439  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000743e  jmp     loc_1800074D6
0x180007443  mov     esi, [rbp+10D0h+var_111C]
0x180007446  mov     ebx, r15d
0x180007449  test    esi, esi
0x18000744b  jz      loc_1800074D6
0x180007451  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180007455  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007459  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000745e  lea     rcx, [rbp+10D0h+var_1100]; this
0x180007462  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007467  test    al, al
0x180007469  jz      short loc_1800074D3
0x18000746b  mov     eax, [rbp+10D0h+var_10FC]
0x18000746e  mov     rcx, [rbp+10D0h+var_1050]; this
0x180007475  mov     [rsp+11D0h+var_1180], eax
0x180007479  movzx   eax, [rbp+10D0h+var_10F8]
0x18000747d  mov     [rbp+10D0h+var_10E0], rax
0x180007481  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180007485  mov     [rbp+10D0h+var_10D8], rax
0x180007489  movzx   eax, [rbp+10D0h+var_1118]
0x18000748d  mov     [rbp+10D0h+var_10D0], rax
0x180007491  mov     [rbp+10D0h+var_10C8], r15
0x180007495  test    rcx, rcx
0x180007498  jz      loc_180007612
0x18000749e  mov     rax, [rcx]
0x1800074a1  lea     rdx, [rsp+11D0h+var_1180]
0x1800074a6  mov     [rsp+11D0h+var_11A8], rdx
0x1800074ab  lea     r9, [rbp+10D0h+var_10D8]
0x1800074af  lea     rdx, [rbp+10D0h+var_10E0]
0x1800074b3  mov     [rsp+11D0h+var_11B0], rdx
0x1800074b8  lea     r8, [rbp+10D0h+var_10D0]
0x1800074bc  mov     rax, [rax+20h]
0x1800074c0  lea     rdx, [rbp+10D0h+var_10C8]
0x1800074c4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800074c9  test    al, al
0x1800074cb  jz      short loc_180007543
0x1800074cd  inc     ebx
0x1800074cf  cmp     ebx, esi
0x1800074d1  jb      short loc_180007455
0x1800074d3  xor     r15d, r15d
0x1800074d6  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800074da  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800074df  lea     rcx, [rbp+10D0h+var_1120]; this
0x1800074e3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800074e8  test    al, al
0x1800074ea  jnz     loc_180007443
0x1800074f0  mov     rcx, [rbp+10D0h+var_1050]
0x1800074f7  test    rcx, rcx
0x1800074fa  jz      short loc_180007508
0x1800074fc  mov     rax, [rcx]
0x1800074ff  mov     rax, [rax+18h]
0x180007503  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007508  mov     bl, 1
0x18000750a  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000750e  jz      short loc_180007585
0x180007510  mov     rdx, [rsp+11D0h+var_1158]
0x180007515  mov     rcx, r14
0x180007518  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000751c  mov     eax, [rsp+11D0h+var_1188]
0x180007520  sub     r8d, edx
0x180007523  mov     [rsp+11D0h+var_11A0], 1
0x18000752b  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000752f  call    wil_details_NtUpdateWnfStateData
0x180007534  cmp     eax, 0C0000001h
0x180007539  jnz     short loc_180007563
0x18000753b  inc     r12
0x18000753e  mov     bl, r15b
0x180007541  jmp     short loc_180007591
0x180007543  mov     rcx, [rbp+10D0h+var_1050]
0x18000754a  xor     r15d, r15d
0x18000754d  test    rcx, rcx
0x180007550  jz      short loc_18000755E
0x180007552  mov     rax, [rcx]
0x180007555  mov     rax, [rax+18h]
0x180007559  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000755e  mov     bl, r15b
0x180007561  jmp     short loc_18000750A
0x180007563  test    eax, eax
0x180007565  jz      short loc_180007585
0x180007567  mov     rdx, [rsp+11D0h+var_1158]
0x18000756c  mov     rcx, r14
0x18000756f  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007573  sub     r8d, edx
0x180007576  mov     [rsp+11D0h+var_11A0], r15d
0x18000757b  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180007580  call    wil_details_NtUpdateWnfStateData
0x180007585  mov     rax, [rbp+10D0h+var_1130]
0x180007589  add     r14, 8
0x18000758d  mov     [rbp+10D0h+var_1128], rax
0x180007591  mov     rsi, [rbp+10D0h+lpMem]
0x180007595  mov     [rbp+10D0h+lpMem], r15
0x180007599  test    rsi, rsi
0x18000759c  jz      short loc_1800075B2
0x18000759e  call    cs:__imp_GetProcessHeap
0x1800075a4  mov     r8, rsi; lpMem
0x1800075a7  xor     edx, edx; dwFlags
0x1800075a9  mov     rcx, rax; hHeap
0x1800075ac  call    cs:__imp_HeapFree
0x1800075b2  test    bl, bl
0x1800075b4  jnz     short loc_1800075E8
0x1800075b6  cmp     r14, r13
0x1800075b9  jnb     short loc_1800075E8
0x1800075bb  cmp     r12, 32h ; '2'
0x1800075bf  jb      loc_180007292
0x1800075c5  jmp     short loc_1800075E8
0x1800075c7  mov     rbx, [rbp+10D0h+lpMem]
0x1800075cb  mov     [rbp+10D0h+lpMem], r15
0x1800075cf  test    rbx, rbx
0x1800075d2  jz      short loc_1800075E8
0x1800075d4  call    cs:__imp_GetProcessHeap
0x1800075da  mov     r8, rbx; lpMem
0x1800075dd  xor     edx, edx; dwFlags
0x1800075df  mov     rcx, rax; hHeap
0x1800075e2  call    cs:__imp_HeapFree
0x1800075e8  mov     rcx, [rbp+10D0h+var_40]
0x1800075ef  xor     rcx, rsp; StackCookie
0x1800075f2  call    __security_check_cookie
0x1800075f7  mov     rbx, [rsp+11D0h+arg_8]
0x1800075ff  add     rsp, 11A0h
0x180007606  pop     r15
0x180007608  pop     r14
0x18000760a  pop     r13
0x18000760c  pop     r12
0x18000760e  pop     rdi
0x18000760f  pop     rsi
0x180007610  pop     rbp
0x180007611  retn
0x180007612  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
