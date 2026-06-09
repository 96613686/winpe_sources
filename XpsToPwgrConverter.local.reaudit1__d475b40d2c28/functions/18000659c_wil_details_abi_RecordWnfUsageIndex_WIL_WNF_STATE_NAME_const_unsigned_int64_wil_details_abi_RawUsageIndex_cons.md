# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000659c`
- end: `0x180006974`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180005c88`

## callees

- `0x180001760`
- `0x1800057d8`
- `0x180005b40`
- `0x18000659c`
- `0x1800070c4`
- `0x1800083fc`
- `0x180008a28`
- `0x18000f4f0`
- `0x180011010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006693`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006693`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000667c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000667c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006908`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000693e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006908`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000693e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006930`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800068fa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006930`

## string_xrefs

- `0x180006675`: `ntdll.dll`

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
0x18000659c  mov     [rsp-8+arg_8], rbx
0x1800065a1  push    rbp
0x1800065a2  push    rsi
0x1800065a3  push    rdi
0x1800065a4  push    r12
0x1800065a6  push    r13
0x1800065a8  push    r14
0x1800065aa  push    r15
0x1800065ac  lea     rbp, [rsp-10A0h]
0x1800065b4  mov     eax, 11A0h
0x1800065b9  call    _alloca_probe
0x1800065be  sub     rsp, rax
0x1800065c1  mov     rax, cs:__security_cookie
0x1800065c8  xor     rax, rsp
0x1800065cb  mov     [rbp+10D0h+var_40], rax
0x1800065d2  mov     rdi, r8
0x1800065d5  mov     r14, rcx
0x1800065d8  lea     r13, [rcx+rdx*8]
0x1800065dc  xor     r15d, r15d
0x1800065df  mov     r12d, r15d
0x1800065e2  mov     [rbp+10D0h+var_1128], r15
0x1800065e6  mov     cl, [rdi+8]
0x1800065e9  movzx   edx, word ptr [rdi+6]
0x1800065ed  movzx   eax, word ptr [rdi]
0x1800065f0  mov     [rsp+11D0h+var_1170], ax
0x1800065f5  movzx   eax, word ptr [rdi+2]
0x1800065f9  mov     [rsp+11D0h+var_116E], ax
0x1800065fe  mov     al, [rdi+4]
0x180006601  mov     [rsp+11D0h+var_116C], al
0x180006605  mov     [rsp+11D0h+var_116A], dx
0x18000660a  mov     [rsp+11D0h+var_1168], cl
0x18000660e  test    dx, dx
0x180006611  jz      short loc_180006630
0x180006613  mov     eax, edx
0x180006615  cmp     cl, 1
0x180006618  jnz     short loc_180006620
0x18000661a  add     rax, 2
0x18000661e  jmp     short loc_180006629
0x180006620  cmp     cl, 2
0x180006623  jnz     short loc_180006629
0x180006625  add     rax, 4
0x180006629  mov     [rsp+11D0h+var_1160], rax
0x18000662e  jmp     short loc_180006635
0x180006630  mov     [rsp+11D0h+var_1160], r15
0x180006635  mov     [rsp+11D0h+var_1158], r15
0x18000663a  xorps   xmm0, xmm0
0x18000663d  movdqa  [rbp+10D0h+var_1150], xmm0
0x180006642  mov     [rbp+10D0h+lpMem], r15
0x180006646  mov     [rbp+10D0h+var_1138], 0
0x18000664c  mov     [rbp+10D0h+var_1136], r15b
0x180006650  mov     [rsp+11D0h+var_1188], r15d
0x180006655  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000665d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180006664  test    rax, rax
0x180006667  jnz     short loc_1800066AC
0x180006669  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006670  test    rax, rax
0x180006673  jnz     short loc_180006689
0x180006675  lea     rcx, ModuleName; "ntdll.dll"
0x18000667c  call    cs:__imp_GetModuleHandleW
0x180006682  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006689  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180006690  mov     rcx, rax; hModule
0x180006693  call    cs:__imp_GetProcAddress
0x180006699  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800066a0  test    rax, rax
0x1800066a3  jnz     short loc_1800066AC
0x1800066a5  mov     ebx, 0C0000139h
0x1800066aa  jmp     short loc_1800066D6
0x1800066ac  lea     rcx, [rsp+11D0h+var_1190]
0x1800066b1  mov     [rsp+11D0h+var_11A8], rcx
0x1800066b6  lea     rcx, [rbp+10D0h+var_1040]
0x1800066bd  mov     [rsp+11D0h+var_11B0], rcx
0x1800066c2  lea     r9, [rsp+11D0h+var_1188]
0x1800066c7  xor     r8d, r8d
0x1800066ca  xor     edx, edx
0x1800066cc  mov     rcx, r14
0x1800066cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066d4  mov     ebx, eax
0x1800066d6  mov     ecx, ebx; this
0x1800066d8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800066dd  test    ebx, ebx
0x1800066df  jz      short loc_1800066EF
0x1800066e1  mov     eax, r15d
0x1800066e4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x1800066e8  mov     [rsp+11D0h+var_1188], r15d
0x1800066ed  jmp     short loc_1800066F3
0x1800066ef  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x1800066f3  mov     r8d, eax; unsigned __int64
0x1800066f6  mov     r9d, 1000h; unsigned __int64
0x1800066fc  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180006703  lea     rcx, [rsp+11D0h+var_1170]; this
0x180006708  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000670d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180006711  jnz     loc_180006923
0x180006717  mov     [rbp+10D0h+var_1130], r15
0x18000671b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180006722  mov     [rbp+10D0h+var_10B0], rax
0x180006726  lea     rax, [rbp+10D0h+var_1130]
0x18000672a  mov     [rbp+10D0h+var_10A8], rax
0x18000672e  lea     rax, [rbp+10D0h+var_1128]
0x180006732  mov     [rbp+10D0h+var_10A0], rax
0x180006736  lea     rax, [rsp+11D0h+var_1170]
0x18000673b  mov     [rbp+10D0h+var_1098], rax
0x18000673f  lea     rax, [rbp+10D0h+var_10B0]
0x180006743  mov     [rbp+10D0h+var_1048], rax
0x18000674a  lea     rax, [rbp+10D0h+var_10B8]
0x18000674e  mov     [rbp+10D0h+var_10C0], rax
0x180006752  mov     rax, [rdi+18h]
0x180006756  add     rax, 0Ah
0x18000675a  mov     [rsp+11D0h+var_1190], rax
0x18000675f  movzx   eax, word ptr [rdi+2]
0x180006763  mov     [rbp+10D0h+var_1120], ax
0x180006767  mov     al, [rdi+4]
0x18000676a  mov     [rbp+10D0h+var_111E], al
0x18000676d  mov     [rbp+10D0h+var_111C], r15d
0x180006771  mov     [rbp+10D0h+var_1118], r15w
0x180006776  xorps   xmm0, xmm0
0x180006779  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000677e  movzx   eax, word ptr [rdi+6]
0x180006782  mov     [rbp+10D0h+var_1100], ax
0x180006786  mov     al, [rdi+8]
0x180006789  mov     [rbp+10D0h+var_10FE], al
0x18000678c  mov     [rbp+10D0h+var_10FC], r15d
0x180006790  mov     [rbp+10D0h+var_10F8], r15w
0x180006795  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000679a  jmp     loc_180006832
0x18000679f  mov     ebx, r15d
0x1800067a2  mov     esi, [rbp+10D0h+var_111C]
0x1800067a5  test    esi, esi
0x1800067a7  jz      loc_180006832
0x1800067ad  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x1800067b1  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800067b5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800067ba  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800067be  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800067c3  test    al, al
0x1800067c5  jz      short loc_18000682F
0x1800067c7  mov     eax, [rbp+10D0h+var_10FC]
0x1800067ca  mov     [rsp+11D0h+var_1180], eax
0x1800067ce  movzx   eax, [rbp+10D0h+var_10F8]
0x1800067d2  mov     [rbp+10D0h+var_10E0], rax
0x1800067d6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800067da  mov     [rbp+10D0h+var_10D8], rax
0x1800067de  movzx   eax, [rbp+10D0h+var_1118]
0x1800067e2  mov     [rbp+10D0h+var_10D0], rax
0x1800067e6  mov     [rbp+10D0h+var_10C8], r15
0x1800067ea  mov     rcx, [rbp+10D0h+var_1048]; this
0x1800067f1  test    rcx, rcx
0x1800067f4  jz      loc_18000696E
0x1800067fa  mov     rax, [rcx]
0x1800067fd  lea     rdx, [rsp+11D0h+var_1180]
0x180006802  mov     [rsp+11D0h+var_11A8], rdx
0x180006807  lea     rdx, [rbp+10D0h+var_10E0]
0x18000680b  mov     [rsp+11D0h+var_11B0], rdx
0x180006810  lea     r9, [rbp+10D0h+var_10D8]
0x180006814  lea     r8, [rbp+10D0h+var_10D0]
0x180006818  lea     rdx, [rbp+10D0h+var_10C8]
0x18000681c  mov     rax, [rax+20h]
0x180006820  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006825  test    al, al
0x180006827  jz      short loc_18000689F
0x180006829  inc     ebx
0x18000682b  cmp     ebx, esi
0x18000682d  jb      short loc_1800067B1
0x18000682f  xor     r15d, r15d
0x180006832  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006836  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000683b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000683f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006844  test    al, al
0x180006846  jnz     loc_18000679F
0x18000684c  mov     rcx, [rbp+10D0h+var_1048]
0x180006853  test    rcx, rcx
0x180006856  jz      short loc_180006864
0x180006858  mov     rax, [rcx]
0x18000685b  mov     rax, [rax+18h]
0x18000685f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006864  mov     bl, 1
0x180006866  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000686a  jz      short loc_1800068E1
0x18000686c  mov     eax, [rsp+11D0h+var_1188]
0x180006870  mov     rdx, [rsp+11D0h+var_1158]
0x180006875  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006879  sub     r8d, edx
0x18000687c  mov     [rsp+11D0h+var_11A0], 1
0x180006884  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180006888  mov     rcx, r14
0x18000688b  call    wil_details_NtUpdateWnfStateData
0x180006890  cmp     eax, 0C0000001h
0x180006895  jnz     short loc_1800068BF
0x180006897  inc     r12
0x18000689a  mov     bl, r15b
0x18000689d  jmp     short loc_1800068ED
0x18000689f  mov     rcx, [rbp+10D0h+var_1048]
0x1800068a6  xor     r15d, r15d
0x1800068a9  test    rcx, rcx
0x1800068ac  jz      short loc_1800068BA
0x1800068ae  mov     rax, [rcx]
0x1800068b1  mov     rax, [rax+18h]
0x1800068b5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800068ba  mov     bl, r15b
0x1800068bd  jmp     short loc_180006866
0x1800068bf  test    eax, eax
0x1800068c1  jz      short loc_1800068E1
0x1800068c3  mov     rdx, [rsp+11D0h+var_1158]
0x1800068c8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800068cc  sub     r8d, edx
0x1800068cf  mov     [rsp+11D0h+var_11A0], r15d
0x1800068d4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x1800068d9  mov     rcx, r14
0x1800068dc  call    wil_details_NtUpdateWnfStateData
0x1800068e1  add     r14, 8
0x1800068e5  mov     rax, [rbp+10D0h+var_1130]
0x1800068e9  mov     [rbp+10D0h+var_1128], rax
0x1800068ed  mov     rsi, [rbp+10D0h+lpMem]
0x1800068f1  mov     [rbp+10D0h+lpMem], r15
0x1800068f5  test    rsi, rsi
0x1800068f8  jz      short loc_18000690E
0x1800068fa  call    cs:__imp_GetProcessHeap
0x180006900  mov     rcx, rax; hHeap
0x180006903  mov     r8, rsi; lpMem
0x180006906  xor     edx, edx; dwFlags
0x180006908  call    cs:__imp_HeapFree
0x18000690e  test    bl, bl
0x180006910  jnz     short loc_180006944
0x180006912  cmp     r14, r13
0x180006915  jnb     short loc_180006944
0x180006917  cmp     r12, 32h ; '2'
0x18000691b  jb      loc_1800065E6
0x180006921  jmp     short loc_180006944
0x180006923  mov     rbx, [rbp+10D0h+lpMem]
0x180006927  mov     [rbp+10D0h+lpMem], r15
0x18000692b  test    rbx, rbx
0x18000692e  jz      short loc_180006944
0x180006930  call    cs:__imp_GetProcessHeap
0x180006936  mov     rcx, rax; hHeap
0x180006939  mov     r8, rbx; lpMem
0x18000693c  xor     edx, edx; dwFlags
0x18000693e  call    cs:__imp_HeapFree
0x180006944  mov     rcx, [rbp+10D0h+var_40]
0x18000694b  xor     rcx, rsp; StackCookie
0x18000694e  call    __security_check_cookie
0x180006953  mov     rbx, [rsp+11D0h+arg_8]
0x18000695b  add     rsp, 11A0h
0x180006962  pop     r15
0x180006964  pop     r14
0x180006966  pop     r13
0x180006968  pop     r12
0x18000696a  pop     rdi
0x18000696b  pop     rsi
0x18000696c  pop     rbp
0x18000696d  retn
0x18000696e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
