# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140015230`
- end: `0x140015608`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140014984`

## callees

- `0x140008660`
- `0x14000d2dc`
- `0x140014584`
- `0x140014884`
- `0x140015230`
- `0x140015a8c`
- `0x1400165cc`
- `0x1400167a0`
- `0x140018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140015310`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140015310`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140015327`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140015327`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001559c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400155d2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14001559c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400155d2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001558e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400155c4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14001558e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400155c4`

## string_xrefs

- `0x140015309`: `ntdll.dll`

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
    v57[0] = wistd::__function::Z::$$A6A_NPEAX131I::Z::__func<`wil::details_abi::RecordWnfUsageIndex'::`4'::_lambda_1_,AXPEBU__WIL__WNF_STATE_NAME,unsigned __int64,wil::details_abi::RawUsageIndex const &>::`vftable';
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
0x140015230  mov     [rsp-8+arg_8], rbx
0x140015235  push    rbp
0x140015236  push    rsi
0x140015237  push    rdi
0x140015238  push    r12
0x14001523a  push    r13
0x14001523c  push    r14
0x14001523e  push    r15
0x140015240  lea     rbp, [rsp-10A0h]
0x140015248  mov     eax, 11A0h
0x14001524d  call    _alloca_probe
0x140015252  sub     rsp, rax
0x140015255  mov     rax, cs:__security_cookie
0x14001525c  xor     rax, rsp
0x14001525f  mov     [rbp+10D0h+var_40], rax
0x140015266  mov     rdi, r8
0x140015269  mov     r14, rcx
0x14001526c  lea     r13, [rcx+rdx*8]
0x140015270  xor     r15d, r15d
0x140015273  mov     r12d, r15d
0x140015276  mov     [rbp+10D0h+var_1128], r15
0x14001527a  mov     cl, [rdi+8]
0x14001527d  movzx   edx, word ptr [rdi+6]
0x140015281  movzx   eax, word ptr [rdi]
0x140015284  mov     [rsp+11D0h+var_1170], ax
0x140015289  movzx   eax, word ptr [rdi+2]
0x14001528d  mov     [rsp+11D0h+var_116E], ax
0x140015292  mov     al, [rdi+4]
0x140015295  mov     [rsp+11D0h+var_116C], al
0x140015299  mov     [rsp+11D0h+var_116A], dx
0x14001529e  mov     [rsp+11D0h+var_1168], cl
0x1400152a2  test    dx, dx
0x1400152a5  jz      short loc_1400152C4
0x1400152a7  mov     eax, edx
0x1400152a9  cmp     cl, 1
0x1400152ac  jnz     short loc_1400152B4
0x1400152ae  add     rax, 2
0x1400152b2  jmp     short loc_1400152BD
0x1400152b4  cmp     cl, 2
0x1400152b7  jnz     short loc_1400152BD
0x1400152b9  add     rax, 4
0x1400152bd  mov     [rsp+11D0h+var_1160], rax
0x1400152c2  jmp     short loc_1400152C9
0x1400152c4  mov     [rsp+11D0h+var_1160], r15
0x1400152c9  mov     [rsp+11D0h+var_1158], r15
0x1400152ce  xorps   xmm0, xmm0
0x1400152d1  movdqa  [rbp+10D0h+var_1150], xmm0
0x1400152d6  mov     [rbp+10D0h+lpMem], r15
0x1400152da  mov     [rbp+10D0h+var_1138], 0
0x1400152e0  mov     [rbp+10D0h+var_1136], r15b
0x1400152e4  mov     [rsp+11D0h+var_1188], r15d
0x1400152e9  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1400152f1  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1400152f8  test    rax, rax
0x1400152fb  jnz     short loc_140015340
0x1400152fd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140015304  test    rax, rax
0x140015307  jnz     short loc_14001531D
0x140015309  lea     rcx, ModuleName; "ntdll.dll"
0x140015310  call    cs:__imp_GetModuleHandleW
0x140015316  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14001531d  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140015324  mov     rcx, rax; hModule
0x140015327  call    cs:__imp_GetProcAddress
0x14001532d  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140015334  test    rax, rax
0x140015337  jnz     short loc_140015340
0x140015339  mov     ebx, 0C0000139h
0x14001533e  jmp     short loc_14001536A
0x140015340  lea     rcx, [rsp+11D0h+var_1190]
0x140015345  mov     [rsp+11D0h+var_11A8], rcx
0x14001534a  lea     rcx, [rbp+10D0h+var_1040]
0x140015351  mov     [rsp+11D0h+var_11B0], rcx
0x140015356  lea     r9, [rsp+11D0h+var_1188]
0x14001535b  xor     r8d, r8d
0x14001535e  xor     edx, edx
0x140015360  mov     rcx, r14
0x140015363  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140015368  mov     ebx, eax
0x14001536a  mov     ecx, ebx; this
0x14001536c  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x140015371  test    ebx, ebx
0x140015373  jz      short loc_140015383
0x140015375  mov     eax, r15d
0x140015378  mov     dword ptr [rsp+11D0h+var_1190], eax
0x14001537c  mov     [rsp+11D0h+var_1188], r15d
0x140015381  jmp     short loc_140015387
0x140015383  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x140015387  mov     r8d, eax; unsigned __int64
0x14001538a  mov     r9d, 1000h; unsigned __int64
0x140015390  lea     rdx, [rbp+10D0h+var_1040]; void *
0x140015397  lea     rcx, [rsp+11D0h+var_1170]; this
0x14001539c  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1400153a1  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x1400153a5  jnz     loc_1400155B7
0x1400153ab  mov     [rbp+10D0h+var_1130], r15
0x1400153af  lea     rax, ??_7?$__func@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@$$A6A_NPEAX131I@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1400153b6  mov     [rbp+10D0h+var_10B0], rax
0x1400153ba  lea     rax, [rbp+10D0h+var_1130]
0x1400153be  mov     [rbp+10D0h+var_10A8], rax
0x1400153c2  lea     rax, [rbp+10D0h+var_1128]
0x1400153c6  mov     [rbp+10D0h+var_10A0], rax
0x1400153ca  lea     rax, [rsp+11D0h+var_1170]
0x1400153cf  mov     [rbp+10D0h+var_1098], rax
0x1400153d3  lea     rax, [rbp+10D0h+var_10B0]
0x1400153d7  mov     [rbp+10D0h+var_1048], rax
0x1400153de  lea     rax, [rbp+10D0h+var_10B8]
0x1400153e2  mov     [rbp+10D0h+var_10C0], rax
0x1400153e6  mov     rax, [rdi+18h]
0x1400153ea  add     rax, 0Ah
0x1400153ee  mov     [rsp+11D0h+var_1190], rax
0x1400153f3  movzx   eax, word ptr [rdi+2]
0x1400153f7  mov     [rbp+10D0h+var_1120], ax
0x1400153fb  mov     al, [rdi+4]
0x1400153fe  mov     [rbp+10D0h+var_111E], al
0x140015401  mov     [rbp+10D0h+var_111C], r15d
0x140015405  mov     [rbp+10D0h+var_1118], r15w
0x14001540a  xorps   xmm0, xmm0
0x14001540d  movdqu  [rbp+10D0h+var_1110], xmm0
0x140015412  movzx   eax, word ptr [rdi+6]
0x140015416  mov     [rbp+10D0h+var_1100], ax
0x14001541a  mov     al, [rdi+8]
0x14001541d  mov     [rbp+10D0h+var_10FE], al
0x140015420  mov     [rbp+10D0h+var_10FC], r15d
0x140015424  mov     [rbp+10D0h+var_10F8], r15w
0x140015429  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14001542e  jmp     loc_1400154C6
0x140015433  mov     ebx, r15d
0x140015436  mov     esi, [rbp+10D0h+var_111C]
0x140015439  test    esi, esi
0x14001543b  jz      loc_1400154C6
0x140015441  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x140015445  mov     r8, [rdi+20h]; unsigned __int8 *
0x140015449  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14001544e  lea     rcx, [rbp+10D0h+var_1100]; this
0x140015452  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140015457  test    al, al
0x140015459  jz      short loc_1400154C3
0x14001545b  mov     eax, [rbp+10D0h+var_10FC]
0x14001545e  mov     [rsp+11D0h+var_1180], eax
0x140015462  movzx   eax, [rbp+10D0h+var_10F8]
0x140015466  mov     [rbp+10D0h+var_10E0], rax
0x14001546a  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14001546e  mov     [rbp+10D0h+var_10D8], rax
0x140015472  movzx   eax, [rbp+10D0h+var_1118]
0x140015476  mov     [rbp+10D0h+var_10D0], rax
0x14001547a  mov     [rbp+10D0h+var_10C8], r15
0x14001547e  mov     rcx, [rbp+10D0h+var_1048]; this
0x140015485  test    rcx, rcx
0x140015488  jz      loc_140015602
0x14001548e  mov     rax, [rcx]
0x140015491  lea     rdx, [rsp+11D0h+var_1180]
0x140015496  mov     [rsp+11D0h+var_11A8], rdx
0x14001549b  lea     rdx, [rbp+10D0h+var_10E0]
0x14001549f  mov     [rsp+11D0h+var_11B0], rdx
0x1400154a4  lea     r9, [rbp+10D0h+var_10D8]
0x1400154a8  lea     r8, [rbp+10D0h+var_10D0]
0x1400154ac  lea     rdx, [rbp+10D0h+var_10C8]
0x1400154b0  mov     rax, [rax+20h]
0x1400154b4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400154b9  test    al, al
0x1400154bb  jz      short loc_140015533
0x1400154bd  inc     ebx
0x1400154bf  cmp     ebx, esi
0x1400154c1  jb      short loc_140015445
0x1400154c3  xor     r15d, r15d
0x1400154c6  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400154ca  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1400154cf  lea     rcx, [rbp+10D0h+var_1120]; this
0x1400154d3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400154d8  test    al, al
0x1400154da  jnz     loc_140015433
0x1400154e0  mov     rcx, [rbp+10D0h+var_1048]
0x1400154e7  test    rcx, rcx
0x1400154ea  jz      short loc_1400154F8
0x1400154ec  mov     rax, [rcx]
0x1400154ef  mov     rax, [rax+18h]
0x1400154f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400154f8  mov     bl, 1
0x1400154fa  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x1400154fe  jz      short loc_140015575
0x140015500  mov     eax, [rsp+11D0h+var_1188]
0x140015504  mov     rdx, [rsp+11D0h+var_1158]
0x140015509  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14001550d  sub     r8d, edx
0x140015510  mov     [rsp+11D0h+var_11A0], 1
0x140015518  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14001551c  mov     rcx, r14
0x14001551f  call    wil_details_NtUpdateWnfStateData
0x140015524  cmp     eax, 0C0000001h
0x140015529  jnz     short loc_140015553
0x14001552b  inc     r12
0x14001552e  mov     bl, r15b
0x140015531  jmp     short loc_140015581
0x140015533  mov     rcx, [rbp+10D0h+var_1048]
0x14001553a  xor     r15d, r15d
0x14001553d  test    rcx, rcx
0x140015540  jz      short loc_14001554E
0x140015542  mov     rax, [rcx]
0x140015545  mov     rax, [rax+18h]
0x140015549  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14001554e  mov     bl, r15b
0x140015551  jmp     short loc_1400154FA
0x140015553  test    eax, eax
0x140015555  jz      short loc_140015575
0x140015557  mov     rdx, [rsp+11D0h+var_1158]
0x14001555c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x140015560  sub     r8d, edx
0x140015563  mov     [rsp+11D0h+var_11A0], r15d
0x140015568  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x14001556d  mov     rcx, r14
0x140015570  call    wil_details_NtUpdateWnfStateData
0x140015575  add     r14, 8
0x140015579  mov     rax, [rbp+10D0h+var_1130]
0x14001557d  mov     [rbp+10D0h+var_1128], rax
0x140015581  mov     rsi, [rbp+10D0h+lpMem]
0x140015585  mov     [rbp+10D0h+lpMem], r15
0x140015589  test    rsi, rsi
0x14001558c  jz      short loc_1400155A2
0x14001558e  call    cs:__imp_GetProcessHeap
0x140015594  mov     rcx, rax; hHeap
0x140015597  mov     r8, rsi; lpMem
0x14001559a  xor     edx, edx; dwFlags
0x14001559c  call    cs:__imp_HeapFree
0x1400155a2  test    bl, bl
0x1400155a4  jnz     short loc_1400155D8
0x1400155a6  cmp     r14, r13
0x1400155a9  jnb     short loc_1400155D8
0x1400155ab  cmp     r12, 32h ; '2'
0x1400155af  jb      loc_14001527A
0x1400155b5  jmp     short loc_1400155D8
0x1400155b7  mov     rbx, [rbp+10D0h+lpMem]
0x1400155bb  mov     [rbp+10D0h+lpMem], r15
0x1400155bf  test    rbx, rbx
0x1400155c2  jz      short loc_1400155D8
0x1400155c4  call    cs:__imp_GetProcessHeap
0x1400155ca  mov     rcx, rax; hHeap
0x1400155cd  mov     r8, rbx; lpMem
0x1400155d0  xor     edx, edx; dwFlags
0x1400155d2  call    cs:__imp_HeapFree
0x1400155d8  mov     rcx, [rbp+10D0h+var_40]
0x1400155df  xor     rcx, rsp; StackCookie
0x1400155e2  call    __security_check_cookie
0x1400155e7  mov     rbx, [rsp+11D0h+arg_8]
0x1400155ef  add     rsp, 11A0h
0x1400155f6  pop     r15
0x1400155f8  pop     r14
0x1400155fa  pop     r13
0x1400155fc  pop     r12
0x1400155fe  pop     rdi
0x1400155ff  pop     rsi
0x140015600  pop     rbp
0x140015601  retn
0x140015602  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
