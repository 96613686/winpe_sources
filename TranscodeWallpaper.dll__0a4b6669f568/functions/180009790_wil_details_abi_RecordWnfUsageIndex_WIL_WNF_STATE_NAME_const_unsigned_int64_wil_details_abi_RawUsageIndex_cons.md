# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180009790`
- end: `0x180009b68`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180008ee4`

## callees

- `0x180002170`
- `0x18000697c`
- `0x180008ae4`
- `0x180008de4`
- `0x180009790`
- `0x18000a0a4`
- `0x18000adc8`
- `0x18000dd00`
- `0x18000f010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009887`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009887`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009870`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009870`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b24`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009aee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009b24`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009afc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b32`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009afc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009b32`

## string_xrefs

- `0x180009869`: `ntdll.dll`

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
0x180009790  mov     [rsp-8+arg_8], rbx
0x180009795  push    rbp
0x180009796  push    rsi
0x180009797  push    rdi
0x180009798  push    r12
0x18000979a  push    r13
0x18000979c  push    r14
0x18000979e  push    r15
0x1800097a0  lea     rbp, [rsp-10A0h]
0x1800097a8  mov     eax, 11A0h
0x1800097ad  call    _alloca_probe
0x1800097b2  sub     rsp, rax
0x1800097b5  mov     rax, cs:__security_cookie
0x1800097bc  xor     rax, rsp
0x1800097bf  mov     [rbp+10D0h+var_40], rax
0x1800097c6  mov     rdi, r8
0x1800097c9  mov     r14, rcx
0x1800097cc  lea     r13, [rcx+rdx*8]
0x1800097d0  xor     r15d, r15d
0x1800097d3  mov     r12d, r15d
0x1800097d6  mov     [rbp+10D0h+var_1128], r15
0x1800097da  mov     cl, [rdi+8]
0x1800097dd  movzx   edx, word ptr [rdi+6]
0x1800097e1  movzx   eax, word ptr [rdi]
0x1800097e4  mov     [rsp+11D0h+var_1170], ax
0x1800097e9  movzx   eax, word ptr [rdi+2]
0x1800097ed  mov     [rsp+11D0h+var_116E], ax
0x1800097f2  mov     al, [rdi+4]
0x1800097f5  mov     [rsp+11D0h+var_116C], al
0x1800097f9  mov     [rsp+11D0h+var_116A], dx
0x1800097fe  mov     [rsp+11D0h+var_1168], cl
0x180009802  test    dx, dx
0x180009805  jz      short loc_180009824
0x180009807  mov     eax, edx
0x180009809  cmp     cl, 1
0x18000980c  jnz     short loc_180009814
0x18000980e  add     rax, 2
0x180009812  jmp     short loc_18000981D
0x180009814  cmp     cl, 2
0x180009817  jnz     short loc_18000981D
0x180009819  add     rax, 4
0x18000981d  mov     [rsp+11D0h+var_1160], rax
0x180009822  jmp     short loc_180009829
0x180009824  mov     [rsp+11D0h+var_1160], r15
0x180009829  mov     [rsp+11D0h+var_1158], r15
0x18000982e  xorps   xmm0, xmm0
0x180009831  movdqa  [rbp+10D0h+var_1150], xmm0
0x180009836  mov     [rbp+10D0h+lpMem], r15
0x18000983a  mov     [rbp+10D0h+var_1138], 0
0x180009840  mov     [rbp+10D0h+var_1136], r15b
0x180009844  mov     [rsp+11D0h+var_1188], r15d
0x180009849  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180009851  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180009858  test    rax, rax
0x18000985b  jnz     short loc_1800098A0
0x18000985d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009864  test    rax, rax
0x180009867  jnz     short loc_18000987D
0x180009869  lea     rcx, ModuleName; "ntdll.dll"
0x180009870  call    cs:__imp_GetModuleHandleW
0x180009876  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000987d  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009884  mov     rcx, rax; hModule
0x180009887  call    cs:__imp_GetProcAddress
0x18000988d  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009894  test    rax, rax
0x180009897  jnz     short loc_1800098A0
0x180009899  mov     ebx, 0C0000139h
0x18000989e  jmp     short loc_1800098CA
0x1800098a0  lea     rcx, [rsp+11D0h+var_1190]
0x1800098a5  mov     [rsp+11D0h+var_11A8], rcx
0x1800098aa  lea     rcx, [rbp+10D0h+var_1040]
0x1800098b1  mov     [rsp+11D0h+var_11B0], rcx
0x1800098b6  lea     r9, [rsp+11D0h+var_1188]
0x1800098bb  xor     r8d, r8d
0x1800098be  xor     edx, edx
0x1800098c0  mov     rcx, r14
0x1800098c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098c8  mov     ebx, eax
0x1800098ca  mov     ecx, ebx; this
0x1800098cc  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800098d1  test    ebx, ebx
0x1800098d3  jz      short loc_1800098E3
0x1800098d5  mov     eax, r15d
0x1800098d8  mov     dword ptr [rsp+11D0h+var_1190], eax
0x1800098dc  mov     [rsp+11D0h+var_1188], r15d
0x1800098e1  jmp     short loc_1800098E7
0x1800098e3  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x1800098e7  mov     r8d, eax; unsigned __int64
0x1800098ea  mov     r9d, 1000h; unsigned __int64
0x1800098f0  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1800098f7  lea     rcx, [rsp+11D0h+var_1170]; this
0x1800098fc  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180009901  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180009905  jnz     loc_180009B17
0x18000990b  mov     [rbp+10D0h+var_1130], r15
0x18000990f  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180009916  mov     [rbp+10D0h+var_10B0], rax
0x18000991a  lea     rax, [rbp+10D0h+var_1130]
0x18000991e  mov     [rbp+10D0h+var_10A8], rax
0x180009922  lea     rax, [rbp+10D0h+var_1128]
0x180009926  mov     [rbp+10D0h+var_10A0], rax
0x18000992a  lea     rax, [rsp+11D0h+var_1170]
0x18000992f  mov     [rbp+10D0h+var_1098], rax
0x180009933  lea     rax, [rbp+10D0h+var_10B0]
0x180009937  mov     [rbp+10D0h+var_1048], rax
0x18000993e  lea     rax, [rbp+10D0h+var_10B8]
0x180009942  mov     [rbp+10D0h+var_10C0], rax
0x180009946  mov     rax, [rdi+18h]
0x18000994a  add     rax, 0Ah
0x18000994e  mov     [rsp+11D0h+var_1190], rax
0x180009953  movzx   eax, word ptr [rdi+2]
0x180009957  mov     [rbp+10D0h+var_1120], ax
0x18000995b  mov     al, [rdi+4]
0x18000995e  mov     [rbp+10D0h+var_111E], al
0x180009961  mov     [rbp+10D0h+var_111C], r15d
0x180009965  mov     [rbp+10D0h+var_1118], r15w
0x18000996a  xorps   xmm0, xmm0
0x18000996d  movdqu  [rbp+10D0h+var_1110], xmm0
0x180009972  movzx   eax, word ptr [rdi+6]
0x180009976  mov     [rbp+10D0h+var_1100], ax
0x18000997a  mov     al, [rdi+8]
0x18000997d  mov     [rbp+10D0h+var_10FE], al
0x180009980  mov     [rbp+10D0h+var_10FC], r15d
0x180009984  mov     [rbp+10D0h+var_10F8], r15w
0x180009989  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000998e  jmp     loc_180009A26
0x180009993  mov     ebx, r15d
0x180009996  mov     esi, [rbp+10D0h+var_111C]
0x180009999  test    esi, esi
0x18000999b  jz      loc_180009A26
0x1800099a1  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x1800099a5  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800099a9  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800099ae  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800099b2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800099b7  test    al, al
0x1800099b9  jz      short loc_180009A23
0x1800099bb  mov     eax, [rbp+10D0h+var_10FC]
0x1800099be  mov     [rsp+11D0h+var_1180], eax
0x1800099c2  movzx   eax, [rbp+10D0h+var_10F8]
0x1800099c6  mov     [rbp+10D0h+var_10E0], rax
0x1800099ca  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800099ce  mov     [rbp+10D0h+var_10D8], rax
0x1800099d2  movzx   eax, [rbp+10D0h+var_1118]
0x1800099d6  mov     [rbp+10D0h+var_10D0], rax
0x1800099da  mov     [rbp+10D0h+var_10C8], r15
0x1800099de  mov     rcx, [rbp+10D0h+var_1048]; this
0x1800099e5  test    rcx, rcx
0x1800099e8  jz      loc_180009B62
0x1800099ee  mov     rax, [rcx]
0x1800099f1  lea     rdx, [rsp+11D0h+var_1180]
0x1800099f6  mov     [rsp+11D0h+var_11A8], rdx
0x1800099fb  lea     rdx, [rbp+10D0h+var_10E0]
0x1800099ff  mov     [rsp+11D0h+var_11B0], rdx
0x180009a04  lea     r9, [rbp+10D0h+var_10D8]
0x180009a08  lea     r8, [rbp+10D0h+var_10D0]
0x180009a0c  lea     rdx, [rbp+10D0h+var_10C8]
0x180009a10  mov     rax, [rax+20h]
0x180009a14  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a19  test    al, al
0x180009a1b  jz      short loc_180009A93
0x180009a1d  inc     ebx
0x180009a1f  cmp     ebx, esi
0x180009a21  jb      short loc_1800099A5
0x180009a23  xor     r15d, r15d
0x180009a26  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009a2a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180009a2f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180009a33  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009a38  test    al, al
0x180009a3a  jnz     loc_180009993
0x180009a40  mov     rcx, [rbp+10D0h+var_1048]
0x180009a47  test    rcx, rcx
0x180009a4a  jz      short loc_180009A58
0x180009a4c  mov     rax, [rcx]
0x180009a4f  mov     rax, [rax+18h]
0x180009a53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a58  mov     bl, 1
0x180009a5a  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180009a5e  jz      short loc_180009AD5
0x180009a60  mov     eax, [rsp+11D0h+var_1188]
0x180009a64  mov     rdx, [rsp+11D0h+var_1158]
0x180009a69  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009a6d  sub     r8d, edx
0x180009a70  mov     [rsp+11D0h+var_11A0], 1
0x180009a78  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180009a7c  mov     rcx, r14
0x180009a7f  call    wil_details_NtUpdateWnfStateData
0x180009a84  cmp     eax, 0C0000001h
0x180009a89  jnz     short loc_180009AB3
0x180009a8b  inc     r12
0x180009a8e  mov     bl, r15b
0x180009a91  jmp     short loc_180009AE1
0x180009a93  mov     rcx, [rbp+10D0h+var_1048]
0x180009a9a  xor     r15d, r15d
0x180009a9d  test    rcx, rcx
0x180009aa0  jz      short loc_180009AAE
0x180009aa2  mov     rax, [rcx]
0x180009aa5  mov     rax, [rax+18h]
0x180009aa9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009aae  mov     bl, r15b
0x180009ab1  jmp     short loc_180009A5A
0x180009ab3  test    eax, eax
0x180009ab5  jz      short loc_180009AD5
0x180009ab7  mov     rdx, [rsp+11D0h+var_1158]
0x180009abc  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009ac0  sub     r8d, edx
0x180009ac3  mov     [rsp+11D0h+var_11A0], r15d
0x180009ac8  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180009acd  mov     rcx, r14
0x180009ad0  call    wil_details_NtUpdateWnfStateData
0x180009ad5  add     r14, 8
0x180009ad9  mov     rax, [rbp+10D0h+var_1130]
0x180009add  mov     [rbp+10D0h+var_1128], rax
0x180009ae1  mov     rsi, [rbp+10D0h+lpMem]
0x180009ae5  mov     [rbp+10D0h+lpMem], r15
0x180009ae9  test    rsi, rsi
0x180009aec  jz      short loc_180009B02
0x180009aee  call    cs:__imp_GetProcessHeap
0x180009af4  mov     rcx, rax; hHeap
0x180009af7  mov     r8, rsi; lpMem
0x180009afa  xor     edx, edx; dwFlags
0x180009afc  call    cs:__imp_HeapFree
0x180009b02  test    bl, bl
0x180009b04  jnz     short loc_180009B38
0x180009b06  cmp     r14, r13
0x180009b09  jnb     short loc_180009B38
0x180009b0b  cmp     r12, 32h ; '2'
0x180009b0f  jb      loc_1800097DA
0x180009b15  jmp     short loc_180009B38
0x180009b17  mov     rbx, [rbp+10D0h+lpMem]
0x180009b1b  mov     [rbp+10D0h+lpMem], r15
0x180009b1f  test    rbx, rbx
0x180009b22  jz      short loc_180009B38
0x180009b24  call    cs:__imp_GetProcessHeap
0x180009b2a  mov     rcx, rax; hHeap
0x180009b2d  mov     r8, rbx; lpMem
0x180009b30  xor     edx, edx; dwFlags
0x180009b32  call    cs:__imp_HeapFree
0x180009b38  mov     rcx, [rbp+10D0h+var_40]
0x180009b3f  xor     rcx, rsp; StackCookie
0x180009b42  call    __security_check_cookie
0x180009b47  mov     rbx, [rsp+11D0h+arg_8]
0x180009b4f  add     rsp, 11A0h
0x180009b56  pop     r15
0x180009b58  pop     r14
0x180009b5a  pop     r13
0x180009b5c  pop     r12
0x180009b5e  pop     rdi
0x180009b5f  pop     rsi
0x180009b60  pop     rbp
0x180009b61  retn
0x180009b62  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
