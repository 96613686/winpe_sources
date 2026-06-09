# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180025260`
- end: `0x180025638`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800249a8`

## callees

- `0x1800021c0`
- `0x18000a938`
- `0x18001f978`
- `0x1800248a8`
- `0x180025260`
- `0x1800257e0`
- `0x1800262ec`
- `0x180029890`
- `0x18002d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025340`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180025340`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025357`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180025357`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255f4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800255f4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800255cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025602`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800255cc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180025602`

## string_xrefs

- `0x180025339`: `ntdll.dll`

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
0x180025260  mov     [rsp-8+arg_8], rbx
0x180025265  push    rbp
0x180025266  push    rsi
0x180025267  push    rdi
0x180025268  push    r12
0x18002526a  push    r13
0x18002526c  push    r14
0x18002526e  push    r15
0x180025270  lea     rbp, [rsp-10A0h]
0x180025278  mov     eax, 11A0h
0x18002527d  call    _alloca_probe
0x180025282  sub     rsp, rax
0x180025285  mov     rax, cs:__security_cookie
0x18002528c  xor     rax, rsp
0x18002528f  mov     [rbp+10D0h+var_40], rax
0x180025296  mov     rdi, r8
0x180025299  mov     r14, rcx
0x18002529c  lea     r13, [rcx+rdx*8]
0x1800252a0  xor     r15d, r15d
0x1800252a3  mov     r12d, r15d
0x1800252a6  mov     [rbp+10D0h+var_1128], r15
0x1800252aa  mov     cl, [rdi+8]
0x1800252ad  movzx   edx, word ptr [rdi+6]
0x1800252b1  movzx   eax, word ptr [rdi]
0x1800252b4  mov     [rsp+11D0h+var_1170], ax
0x1800252b9  movzx   eax, word ptr [rdi+2]
0x1800252bd  mov     [rsp+11D0h+var_116E], ax
0x1800252c2  mov     al, [rdi+4]
0x1800252c5  mov     [rsp+11D0h+var_116C], al
0x1800252c9  mov     [rsp+11D0h+var_116A], dx
0x1800252ce  mov     [rsp+11D0h+var_1168], cl
0x1800252d2  test    dx, dx
0x1800252d5  jz      short loc_1800252F4
0x1800252d7  mov     eax, edx
0x1800252d9  cmp     cl, 1
0x1800252dc  jnz     short loc_1800252E4
0x1800252de  add     rax, 2
0x1800252e2  jmp     short loc_1800252ED
0x1800252e4  cmp     cl, 2
0x1800252e7  jnz     short loc_1800252ED
0x1800252e9  add     rax, 4
0x1800252ed  mov     [rsp+11D0h+var_1160], rax
0x1800252f2  jmp     short loc_1800252F9
0x1800252f4  mov     [rsp+11D0h+var_1160], r15
0x1800252f9  mov     [rsp+11D0h+var_1158], r15
0x1800252fe  xorps   xmm0, xmm0
0x180025301  movdqa  [rbp+10D0h+var_1150], xmm0
0x180025306  mov     [rbp+10D0h+lpMem], r15
0x18002530a  mov     [rbp+10D0h+var_1138], 0
0x180025310  mov     [rbp+10D0h+var_1136], r15b
0x180025314  mov     [rsp+11D0h+var_1188], r15d
0x180025319  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180025321  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180025328  test    rax, rax
0x18002532b  jnz     short loc_180025370
0x18002532d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180025334  test    rax, rax
0x180025337  jnz     short loc_18002534D
0x180025339  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x180025340  call    cs:__imp_GetModuleHandleW
0x180025346  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002534d  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180025354  mov     rcx, rax; hModule
0x180025357  call    cs:__imp_GetProcAddress
0x18002535d  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180025364  test    rax, rax
0x180025367  jnz     short loc_180025370
0x180025369  mov     ebx, 0C0000139h
0x18002536e  jmp     short loc_18002539A
0x180025370  lea     rcx, [rsp+11D0h+var_1190]
0x180025375  mov     [rsp+11D0h+var_11A8], rcx
0x18002537a  lea     rcx, [rbp+10D0h+var_1040]
0x180025381  mov     [rsp+11D0h+var_11B0], rcx
0x180025386  lea     r9, [rsp+11D0h+var_1188]
0x18002538b  xor     r8d, r8d
0x18002538e  xor     edx, edx
0x180025390  mov     rcx, r14
0x180025393  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025398  mov     ebx, eax
0x18002539a  mov     ecx, ebx; this
0x18002539c  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800253a1  test    ebx, ebx
0x1800253a3  jz      short loc_1800253B3
0x1800253a5  mov     eax, r15d
0x1800253a8  mov     dword ptr [rsp+11D0h+var_1190], eax
0x1800253ac  mov     [rsp+11D0h+var_1188], r15d
0x1800253b1  jmp     short loc_1800253B7
0x1800253b3  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x1800253b7  mov     r8d, eax; unsigned __int64
0x1800253ba  mov     r9d, 1000h; unsigned __int64
0x1800253c0  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1800253c7  lea     rcx, [rsp+11D0h+var_1170]; this
0x1800253cc  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1800253d1  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x1800253d5  jnz     loc_1800255E7
0x1800253db  mov     [rbp+10D0h+var_1130], r15
0x1800253df  lea     rax, ??_7?$__func@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@$$A6A_NPEAX131I@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800253e6  mov     [rbp+10D0h+var_10B0], rax
0x1800253ea  lea     rax, [rbp+10D0h+var_1130]
0x1800253ee  mov     [rbp+10D0h+var_10A8], rax
0x1800253f2  lea     rax, [rbp+10D0h+var_1128]
0x1800253f6  mov     [rbp+10D0h+var_10A0], rax
0x1800253fa  lea     rax, [rsp+11D0h+var_1170]
0x1800253ff  mov     [rbp+10D0h+var_1098], rax
0x180025403  lea     rax, [rbp+10D0h+var_10B0]
0x180025407  mov     [rbp+10D0h+var_1048], rax
0x18002540e  lea     rax, [rbp+10D0h+var_10B8]
0x180025412  mov     [rbp+10D0h+var_10C0], rax
0x180025416  mov     rax, [rdi+18h]
0x18002541a  add     rax, 0Ah
0x18002541e  mov     [rsp+11D0h+var_1190], rax
0x180025423  movzx   eax, word ptr [rdi+2]
0x180025427  mov     [rbp+10D0h+var_1120], ax
0x18002542b  mov     al, [rdi+4]
0x18002542e  mov     [rbp+10D0h+var_111E], al
0x180025431  mov     [rbp+10D0h+var_111C], r15d
0x180025435  mov     [rbp+10D0h+var_1118], r15w
0x18002543a  xorps   xmm0, xmm0
0x18002543d  movdqu  [rbp+10D0h+var_1110], xmm0
0x180025442  movzx   eax, word ptr [rdi+6]
0x180025446  mov     [rbp+10D0h+var_1100], ax
0x18002544a  mov     al, [rdi+8]
0x18002544d  mov     [rbp+10D0h+var_10FE], al
0x180025450  mov     [rbp+10D0h+var_10FC], r15d
0x180025454  mov     [rbp+10D0h+var_10F8], r15w
0x180025459  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18002545e  jmp     loc_1800254F6
0x180025463  mov     ebx, r15d
0x180025466  mov     esi, [rbp+10D0h+var_111C]
0x180025469  test    esi, esi
0x18002546b  jz      loc_1800254F6
0x180025471  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180025475  mov     r8, [rdi+20h]; unsigned __int8 *
0x180025479  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18002547e  lea     rcx, [rbp+10D0h+var_1100]; this
0x180025482  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180025487  test    al, al
0x180025489  jz      short loc_1800254F3
0x18002548b  mov     eax, [rbp+10D0h+var_10FC]
0x18002548e  mov     [rsp+11D0h+var_1180], eax
0x180025492  movzx   eax, [rbp+10D0h+var_10F8]
0x180025496  mov     [rbp+10D0h+var_10E0], rax
0x18002549a  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18002549e  mov     [rbp+10D0h+var_10D8], rax
0x1800254a2  movzx   eax, [rbp+10D0h+var_1118]
0x1800254a6  mov     [rbp+10D0h+var_10D0], rax
0x1800254aa  mov     [rbp+10D0h+var_10C8], r15
0x1800254ae  mov     rcx, [rbp+10D0h+var_1048]; this
0x1800254b5  test    rcx, rcx
0x1800254b8  jz      loc_180025632
0x1800254be  mov     rax, [rcx]
0x1800254c1  lea     rdx, [rsp+11D0h+var_1180]
0x1800254c6  mov     [rsp+11D0h+var_11A8], rdx
0x1800254cb  lea     rdx, [rbp+10D0h+var_10E0]
0x1800254cf  mov     [rsp+11D0h+var_11B0], rdx
0x1800254d4  lea     r9, [rbp+10D0h+var_10D8]
0x1800254d8  lea     r8, [rbp+10D0h+var_10D0]
0x1800254dc  lea     rdx, [rbp+10D0h+var_10C8]
0x1800254e0  mov     rax, [rax+20h]
0x1800254e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800254e9  test    al, al
0x1800254eb  jz      short loc_180025563
0x1800254ed  inc     ebx
0x1800254ef  cmp     ebx, esi
0x1800254f1  jb      short loc_180025475
0x1800254f3  xor     r15d, r15d
0x1800254f6  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800254fa  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800254ff  lea     rcx, [rbp+10D0h+var_1120]; this
0x180025503  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180025508  test    al, al
0x18002550a  jnz     loc_180025463
0x180025510  mov     rcx, [rbp+10D0h+var_1048]
0x180025517  test    rcx, rcx
0x18002551a  jz      short loc_180025528
0x18002551c  mov     rax, [rcx]
0x18002551f  mov     rax, [rax+18h]
0x180025523  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180025528  mov     bl, 1
0x18002552a  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18002552e  jz      short loc_1800255A5
0x180025530  mov     eax, [rsp+11D0h+var_1188]
0x180025534  mov     rdx, [rsp+11D0h+var_1158]
0x180025539  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18002553d  sub     r8d, edx
0x180025540  mov     [rsp+11D0h+var_11A0], 1
0x180025548  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18002554c  mov     rcx, r14
0x18002554f  call    wil_details_NtUpdateWnfStateData
0x180025554  cmp     eax, 0C0000001h
0x180025559  jnz     short loc_180025583
0x18002555b  inc     r12
0x18002555e  mov     bl, r15b
0x180025561  jmp     short loc_1800255B1
0x180025563  mov     rcx, [rbp+10D0h+var_1048]
0x18002556a  xor     r15d, r15d
0x18002556d  test    rcx, rcx
0x180025570  jz      short loc_18002557E
0x180025572  mov     rax, [rcx]
0x180025575  mov     rax, [rax+18h]
0x180025579  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002557e  mov     bl, r15b
0x180025581  jmp     short loc_18002552A
0x180025583  test    eax, eax
0x180025585  jz      short loc_1800255A5
0x180025587  mov     rdx, [rsp+11D0h+var_1158]
0x18002558c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180025590  sub     r8d, edx
0x180025593  mov     [rsp+11D0h+var_11A0], r15d
0x180025598  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18002559d  mov     rcx, r14
0x1800255a0  call    wil_details_NtUpdateWnfStateData
0x1800255a5  add     r14, 8
0x1800255a9  mov     rax, [rbp+10D0h+var_1130]
0x1800255ad  mov     [rbp+10D0h+var_1128], rax
0x1800255b1  mov     rsi, [rbp+10D0h+lpMem]
0x1800255b5  mov     [rbp+10D0h+lpMem], r15
0x1800255b9  test    rsi, rsi
0x1800255bc  jz      short loc_1800255D2
0x1800255be  call    cs:__imp_GetProcessHeap
0x1800255c4  mov     rcx, rax; hHeap
0x1800255c7  mov     r8, rsi; lpMem
0x1800255ca  xor     edx, edx; dwFlags
0x1800255cc  call    cs:__imp_HeapFree
0x1800255d2  test    bl, bl
0x1800255d4  jnz     short loc_180025608
0x1800255d6  cmp     r14, r13
0x1800255d9  jnb     short loc_180025608
0x1800255db  cmp     r12, 32h ; '2'
0x1800255df  jb      loc_1800252AA
0x1800255e5  jmp     short loc_180025608
0x1800255e7  mov     rbx, [rbp+10D0h+lpMem]
0x1800255eb  mov     [rbp+10D0h+lpMem], r15
0x1800255ef  test    rbx, rbx
0x1800255f2  jz      short loc_180025608
0x1800255f4  call    cs:__imp_GetProcessHeap
0x1800255fa  mov     rcx, rax; hHeap
0x1800255fd  mov     r8, rbx; lpMem
0x180025600  xor     edx, edx; dwFlags
0x180025602  call    cs:__imp_HeapFree
0x180025608  mov     rcx, [rbp+10D0h+var_40]
0x18002560f  xor     rcx, rsp; StackCookie
0x180025612  call    __security_check_cookie
0x180025617  mov     rbx, [rsp+11D0h+arg_8]
0x18002561f  add     rsp, 11A0h
0x180025626  pop     r15
0x180025628  pop     r14
0x18002562a  pop     r13
0x18002562c  pop     r12
0x18002562e  pop     rdi
0x18002562f  pop     rsi
0x180025630  pop     rbp
0x180025631  retn
0x180025632  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
