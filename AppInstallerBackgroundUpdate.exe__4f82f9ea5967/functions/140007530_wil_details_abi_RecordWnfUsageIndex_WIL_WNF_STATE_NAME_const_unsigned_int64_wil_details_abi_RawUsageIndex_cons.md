# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140007530`
- end: `0x140007908`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140006c84`

## callees

- `0x140001530`
- `0x1400055dc`
- `0x1400068c0`
- `0x140006b84`
- `0x140007530`
- `0x140007ab0`
- `0x1400087dc`
- `0x140008990`
- `0x140009010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007610`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140007610`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007627`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140007627`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000788e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400078c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000788e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400078c4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000789c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400078d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000789c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400078d2`

## string_xrefs

- `0x140007609`: `ntdll.dll`

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
0x140007530  mov     [rsp-8+arg_8], rbx
0x140007535  push    rbp
0x140007536  push    rsi
0x140007537  push    rdi
0x140007538  push    r12
0x14000753a  push    r13
0x14000753c  push    r14
0x14000753e  push    r15
0x140007540  lea     rbp, [rsp-10A0h]
0x140007548  mov     eax, 11A0h
0x14000754d  call    _alloca_probe
0x140007552  sub     rsp, rax
0x140007555  mov     rax, cs:__security_cookie
0x14000755c  xor     rax, rsp
0x14000755f  mov     [rbp+10D0h+var_40], rax
0x140007566  mov     rdi, r8
0x140007569  mov     r14, rcx
0x14000756c  lea     r13, [rcx+rdx*8]
0x140007570  xor     r15d, r15d
0x140007573  mov     r12d, r15d
0x140007576  mov     [rbp+10D0h+var_1128], r15
0x14000757a  mov     cl, [rdi+8]
0x14000757d  movzx   edx, word ptr [rdi+6]
0x140007581  movzx   eax, word ptr [rdi]
0x140007584  mov     [rsp+11D0h+var_1170], ax
0x140007589  movzx   eax, word ptr [rdi+2]
0x14000758d  mov     [rsp+11D0h+var_116E], ax
0x140007592  mov     al, [rdi+4]
0x140007595  mov     [rsp+11D0h+var_116C], al
0x140007599  mov     [rsp+11D0h+var_116A], dx
0x14000759e  mov     [rsp+11D0h+var_1168], cl
0x1400075a2  test    dx, dx
0x1400075a5  jz      short loc_1400075C4
0x1400075a7  mov     eax, edx
0x1400075a9  cmp     cl, 1
0x1400075ac  jnz     short loc_1400075B4
0x1400075ae  add     rax, 2
0x1400075b2  jmp     short loc_1400075BD
0x1400075b4  cmp     cl, 2
0x1400075b7  jnz     short loc_1400075BD
0x1400075b9  add     rax, 4
0x1400075bd  mov     [rsp+11D0h+var_1160], rax
0x1400075c2  jmp     short loc_1400075C9
0x1400075c4  mov     [rsp+11D0h+var_1160], r15
0x1400075c9  mov     [rsp+11D0h+var_1158], r15
0x1400075ce  xorps   xmm0, xmm0
0x1400075d1  movdqa  [rbp+10D0h+var_1150], xmm0
0x1400075d6  mov     [rbp+10D0h+lpMem], r15
0x1400075da  mov     [rbp+10D0h+var_1138], 0
0x1400075e0  mov     [rbp+10D0h+var_1136], r15b
0x1400075e4  mov     [rsp+11D0h+var_1188], r15d
0x1400075e9  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1400075f1  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1400075f8  test    rax, rax
0x1400075fb  jnz     short loc_140007640
0x1400075fd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140007604  test    rax, rax
0x140007607  jnz     short loc_14000761D
0x140007609  lea     rcx, ModuleName; "ntdll.dll"
0x140007610  call    cs:__imp_GetModuleHandleW
0x140007616  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000761d  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140007624  mov     rcx, rax; hModule
0x140007627  call    cs:__imp_GetProcAddress
0x14000762d  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140007634  test    rax, rax
0x140007637  jnz     short loc_140007640
0x140007639  mov     ebx, 0C0000139h
0x14000763e  jmp     short loc_14000766A
0x140007640  lea     rcx, [rsp+11D0h+var_1190]
0x140007645  mov     [rsp+11D0h+var_11A8], rcx
0x14000764a  lea     rcx, [rbp+10D0h+var_1040]
0x140007651  mov     [rsp+11D0h+var_11B0], rcx
0x140007656  lea     r9, [rsp+11D0h+var_1188]
0x14000765b  xor     r8d, r8d
0x14000765e  xor     edx, edx
0x140007660  mov     rcx, r14
0x140007663  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140007668  mov     ebx, eax
0x14000766a  mov     ecx, ebx; this
0x14000766c  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x140007671  test    ebx, ebx
0x140007673  jz      short loc_140007683
0x140007675  mov     eax, r15d
0x140007678  mov     dword ptr [rsp+11D0h+var_1190], eax
0x14000767c  mov     [rsp+11D0h+var_1188], r15d
0x140007681  jmp     short loc_140007687
0x140007683  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x140007687  mov     r8d, eax; unsigned __int64
0x14000768a  mov     r9d, 1000h; unsigned __int64
0x140007690  lea     rdx, [rbp+10D0h+var_1040]; void *
0x140007697  lea     rcx, [rsp+11D0h+var_1170]; this
0x14000769c  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1400076a1  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x1400076a5  jnz     loc_1400078B7
0x1400076ab  mov     [rbp+10D0h+var_1130], r15
0x1400076af  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1400076b6  mov     [rbp+10D0h+var_10B0], rax
0x1400076ba  lea     rax, [rbp+10D0h+var_1130]
0x1400076be  mov     [rbp+10D0h+var_10A8], rax
0x1400076c2  lea     rax, [rbp+10D0h+var_1128]
0x1400076c6  mov     [rbp+10D0h+var_10A0], rax
0x1400076ca  lea     rax, [rsp+11D0h+var_1170]
0x1400076cf  mov     [rbp+10D0h+var_1098], rax
0x1400076d3  lea     rax, [rbp+10D0h+var_10B0]
0x1400076d7  mov     [rbp+10D0h+var_1048], rax
0x1400076de  lea     rax, [rbp+10D0h+var_10B8]
0x1400076e2  mov     [rbp+10D0h+var_10C0], rax
0x1400076e6  mov     rax, [rdi+18h]
0x1400076ea  add     rax, 0Ah
0x1400076ee  mov     [rsp+11D0h+var_1190], rax
0x1400076f3  movzx   eax, word ptr [rdi+2]
0x1400076f7  mov     [rbp+10D0h+var_1120], ax
0x1400076fb  mov     al, [rdi+4]
0x1400076fe  mov     [rbp+10D0h+var_111E], al
0x140007701  mov     [rbp+10D0h+var_111C], r15d
0x140007705  mov     [rbp+10D0h+var_1118], r15w
0x14000770a  xorps   xmm0, xmm0
0x14000770d  movdqu  [rbp+10D0h+var_1110], xmm0
0x140007712  movzx   eax, word ptr [rdi+6]
0x140007716  mov     [rbp+10D0h+var_1100], ax
0x14000771a  mov     al, [rdi+8]
0x14000771d  mov     [rbp+10D0h+var_10FE], al
0x140007720  mov     [rbp+10D0h+var_10FC], r15d
0x140007724  mov     [rbp+10D0h+var_10F8], r15w
0x140007729  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14000772e  jmp     loc_1400077C6
0x140007733  mov     ebx, r15d
0x140007736  mov     esi, [rbp+10D0h+var_111C]
0x140007739  test    esi, esi
0x14000773b  jz      loc_1400077C6
0x140007741  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x140007745  mov     r8, [rdi+20h]; unsigned __int8 *
0x140007749  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000774e  lea     rcx, [rbp+10D0h+var_1100]; this
0x140007752  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140007757  test    al, al
0x140007759  jz      short loc_1400077C3
0x14000775b  mov     eax, [rbp+10D0h+var_10FC]
0x14000775e  mov     [rsp+11D0h+var_1180], eax
0x140007762  movzx   eax, [rbp+10D0h+var_10F8]
0x140007766  mov     [rbp+10D0h+var_10E0], rax
0x14000776a  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000776e  mov     [rbp+10D0h+var_10D8], rax
0x140007772  movzx   eax, [rbp+10D0h+var_1118]
0x140007776  mov     [rbp+10D0h+var_10D0], rax
0x14000777a  mov     [rbp+10D0h+var_10C8], r15
0x14000777e  mov     rcx, [rbp+10D0h+var_1048]; this
0x140007785  test    rcx, rcx
0x140007788  jz      loc_140007902
0x14000778e  mov     rax, [rcx]
0x140007791  lea     rdx, [rsp+11D0h+var_1180]
0x140007796  mov     [rsp+11D0h+var_11A8], rdx
0x14000779b  lea     rdx, [rbp+10D0h+var_10E0]
0x14000779f  mov     [rsp+11D0h+var_11B0], rdx
0x1400077a4  lea     r9, [rbp+10D0h+var_10D8]
0x1400077a8  lea     r8, [rbp+10D0h+var_10D0]
0x1400077ac  lea     rdx, [rbp+10D0h+var_10C8]
0x1400077b0  mov     rax, [rax+20h]
0x1400077b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077b9  test    al, al
0x1400077bb  jz      short loc_140007833
0x1400077bd  inc     ebx
0x1400077bf  cmp     ebx, esi
0x1400077c1  jb      short loc_140007745
0x1400077c3  xor     r15d, r15d
0x1400077c6  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400077ca  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1400077cf  lea     rcx, [rbp+10D0h+var_1120]; this
0x1400077d3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400077d8  test    al, al
0x1400077da  jnz     loc_140007733
0x1400077e0  mov     rcx, [rbp+10D0h+var_1048]
0x1400077e7  test    rcx, rcx
0x1400077ea  jz      short loc_1400077F8
0x1400077ec  mov     rax, [rcx]
0x1400077ef  mov     rax, [rax+18h]
0x1400077f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400077f8  mov     bl, 1
0x1400077fa  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x1400077fe  jz      short loc_140007875
0x140007800  mov     eax, [rsp+11D0h+var_1188]
0x140007804  mov     rdx, [rsp+11D0h+var_1158]
0x140007809  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000780d  sub     r8d, edx
0x140007810  mov     [rsp+11D0h+var_11A0], 1
0x140007818  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14000781c  mov     rcx, r14
0x14000781f  call    wil_details_NtUpdateWnfStateData
0x140007824  cmp     eax, 0C0000001h
0x140007829  jnz     short loc_140007853
0x14000782b  inc     r12
0x14000782e  mov     bl, r15b
0x140007831  jmp     short loc_140007881
0x140007833  mov     rcx, [rbp+10D0h+var_1048]
0x14000783a  xor     r15d, r15d
0x14000783d  test    rcx, rcx
0x140007840  jz      short loc_14000784E
0x140007842  mov     rax, [rcx]
0x140007845  mov     rax, [rax+18h]
0x140007849  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000784e  mov     bl, r15b
0x140007851  jmp     short loc_1400077FA
0x140007853  test    eax, eax
0x140007855  jz      short loc_140007875
0x140007857  mov     rdx, [rsp+11D0h+var_1158]
0x14000785c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x140007860  sub     r8d, edx
0x140007863  mov     [rsp+11D0h+var_11A0], r15d
0x140007868  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x14000786d  mov     rcx, r14
0x140007870  call    wil_details_NtUpdateWnfStateData
0x140007875  add     r14, 8
0x140007879  mov     rax, [rbp+10D0h+var_1130]
0x14000787d  mov     [rbp+10D0h+var_1128], rax
0x140007881  mov     rsi, [rbp+10D0h+lpMem]
0x140007885  mov     [rbp+10D0h+lpMem], r15
0x140007889  test    rsi, rsi
0x14000788c  jz      short loc_1400078A2
0x14000788e  call    cs:__imp_GetProcessHeap
0x140007894  mov     rcx, rax; hHeap
0x140007897  mov     r8, rsi; lpMem
0x14000789a  xor     edx, edx; dwFlags
0x14000789c  call    cs:__imp_HeapFree
0x1400078a2  test    bl, bl
0x1400078a4  jnz     short loc_1400078D8
0x1400078a6  cmp     r14, r13
0x1400078a9  jnb     short loc_1400078D8
0x1400078ab  cmp     r12, 32h ; '2'
0x1400078af  jb      loc_14000757A
0x1400078b5  jmp     short loc_1400078D8
0x1400078b7  mov     rbx, [rbp+10D0h+lpMem]
0x1400078bb  mov     [rbp+10D0h+lpMem], r15
0x1400078bf  test    rbx, rbx
0x1400078c2  jz      short loc_1400078D8
0x1400078c4  call    cs:__imp_GetProcessHeap
0x1400078ca  mov     rcx, rax; hHeap
0x1400078cd  mov     r8, rbx; lpMem
0x1400078d0  xor     edx, edx; dwFlags
0x1400078d2  call    cs:__imp_HeapFree
0x1400078d8  mov     rcx, [rbp+10D0h+var_40]
0x1400078df  xor     rcx, rsp; StackCookie
0x1400078e2  call    __security_check_cookie
0x1400078e7  mov     rbx, [rsp+11D0h+arg_8]
0x1400078ef  add     rsp, 11A0h
0x1400078f6  pop     r15
0x1400078f8  pop     r14
0x1400078fa  pop     r13
0x1400078fc  pop     r12
0x1400078fe  pop     rdi
0x1400078ff  pop     rsi
0x140007900  pop     rbp
0x140007901  retn
0x140007902  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
