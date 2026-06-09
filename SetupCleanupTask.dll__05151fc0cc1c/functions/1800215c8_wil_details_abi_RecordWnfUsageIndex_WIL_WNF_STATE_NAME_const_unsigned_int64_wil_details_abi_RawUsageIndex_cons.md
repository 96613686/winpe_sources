# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800215c8`
- end: `0x180021995`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180020d04`

## callees

- `0x18001e9a8`
- `0x18001f724`
- `0x1800215c8`
- `0x1800222e8`
- `0x1800247e4`
- `0x180025074`
- `0x180032310`
- `0x1800323d0`
- `0x180036010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800216a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800216a7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800216be`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800216be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002191b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021951`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18002191b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180021951`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021929`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002195f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180021929`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18002195f`

## string_xrefs

- `0x1800216a0`: `ntdll.dll`

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
0x1800215c8  mov     [rsp-8+arg_8], rbx
0x1800215cd  push    rbp
0x1800215ce  push    rsi
0x1800215cf  push    rdi
0x1800215d0  push    r12
0x1800215d2  push    r13
0x1800215d4  push    r14
0x1800215d6  push    r15
0x1800215d8  lea     rbp, [rsp-10A0h]
0x1800215e0  mov     eax, 11A0h
0x1800215e5  call    _alloca_probe
0x1800215ea  sub     rsp, rax
0x1800215ed  mov     rax, cs:__security_cookie
0x1800215f4  xor     rax, rsp
0x1800215f7  mov     [rbp+10D0h+var_40], rax
0x1800215fe  xor     r13d, r13d
0x180021601  lea     r12, [rcx+rdx*8]
0x180021605  mov     r15d, r13d
0x180021608  mov     [rbp+10D0h+var_1128], r13
0x18002160c  mov     rdi, r8
0x18002160f  mov     r14, rcx
0x180021612  movzx   eax, word ptr [rdi]
0x180021615  movzx   edx, word ptr [rdi+6]
0x180021619  mov     cl, [rdi+8]
0x18002161c  mov     [rsp+11D0h+var_1170], ax
0x180021621  movzx   eax, word ptr [rdi+2]
0x180021625  mov     [rsp+11D0h+var_116E], ax
0x18002162a  mov     al, [rdi+4]
0x18002162d  mov     [rsp+11D0h+var_116C], al
0x180021631  mov     [rsp+11D0h+var_116A], dx
0x180021636  mov     [rsp+11D0h+var_1168], cl
0x18002163a  test    dx, dx
0x18002163d  jz      short loc_18002165C
0x18002163f  mov     eax, edx
0x180021641  cmp     cl, 1
0x180021644  jnz     short loc_18002164C
0x180021646  add     rax, 2
0x18002164a  jmp     short loc_180021655
0x18002164c  cmp     cl, 2
0x18002164f  jnz     short loc_180021655
0x180021651  add     rax, 4
0x180021655  mov     [rsp+11D0h+var_1160], rax
0x18002165a  jmp     short loc_180021661
0x18002165c  mov     [rsp+11D0h+var_1160], r13
0x180021661  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180021668  xorps   xmm0, xmm0
0x18002166b  mov     [rsp+11D0h+var_1158], r13
0x180021670  movdqa  [rbp+10D0h+var_1150], xmm0
0x180021675  mov     [rbp+10D0h+lpMem], r13
0x180021679  mov     [rbp+10D0h+var_1138], r13w
0x18002167e  mov     [rbp+10D0h+var_1136], r13b
0x180021682  mov     [rsp+11D0h+var_1188], r13d
0x180021687  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18002168f  test    rax, rax
0x180021692  jnz     short loc_1800216D7
0x180021694  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18002169b  test    rax, rax
0x18002169e  jnz     short loc_1800216B4
0x1800216a0  lea     rcx, LibFileName; "ntdll.dll"
0x1800216a7  call    cs:__imp_GetModuleHandleW
0x1800216ad  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800216b4  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800216bb  mov     rcx, rax; hModule
0x1800216be  call    cs:__imp_GetProcAddress
0x1800216c4  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800216cb  test    rax, rax
0x1800216ce  jnz     short loc_1800216D7
0x1800216d0  mov     ebx, 0C0000139h
0x1800216d5  jmp     short loc_180021701
0x1800216d7  lea     rcx, [rsp+11D0h+var_1190]
0x1800216dc  xor     r8d, r8d
0x1800216df  mov     [rsp+11D0h+var_11A8], rcx
0x1800216e4  lea     r9, [rsp+11D0h+var_1188]
0x1800216e9  lea     rcx, [rbp+10D0h+var_1040]
0x1800216f0  xor     edx, edx
0x1800216f2  mov     [rsp+11D0h+var_11B0], rcx
0x1800216f7  mov     rcx, r14
0x1800216fa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800216ff  mov     ebx, eax
0x180021701  mov     ecx, ebx; this
0x180021703  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180021708  test    ebx, ebx
0x18002170a  jz      short loc_18002171A
0x18002170c  mov     eax, r13d
0x18002170f  mov     [rsp+11D0h+var_1188], r13d
0x180021714  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180021718  jmp     short loc_18002171E
0x18002171a  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18002171e  mov     r8d, eax; unsigned __int64
0x180021721  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180021728  mov     r9d, 1000h; unsigned __int64
0x18002172e  lea     rcx, [rsp+11D0h+var_1170]; this
0x180021733  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180021738  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18002173c  jnz     loc_180021944
0x180021742  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180021749  mov     [rbp+10D0h+var_1130], r13
0x18002174d  mov     [rbp+10D0h+var_10B8], rax
0x180021751  xorps   xmm0, xmm0
0x180021754  lea     rax, [rbp+10D0h+var_1130]
0x180021758  mov     [rbp+10D0h+var_111C], r13d
0x18002175c  mov     [rbp+10D0h+var_10B0], rax
0x180021760  lea     rax, [rbp+10D0h+var_1128]
0x180021764  mov     [rbp+10D0h+var_10A8], rax
0x180021768  lea     rax, [rsp+11D0h+var_1170]
0x18002176d  mov     [rbp+10D0h+var_10A0], rax
0x180021771  lea     rax, [rbp+10D0h+var_10B8]
0x180021775  mov     [rbp+10D0h+var_1050], rax
0x18002177c  mov     rax, [rdi+18h]
0x180021780  add     rax, 0Ah
0x180021784  mov     [rbp+10D0h+var_1118], r13w
0x180021789  mov     [rsp+11D0h+var_1190], rax
0x18002178e  movzx   eax, word ptr [rdi+2]
0x180021792  mov     [rbp+10D0h+var_1120], ax
0x180021796  mov     al, [rdi+4]
0x180021799  mov     [rbp+10D0h+var_111E], al
0x18002179c  movzx   eax, word ptr [rdi+6]
0x1800217a0  mov     [rbp+10D0h+var_1100], ax
0x1800217a4  mov     al, [rdi+8]
0x1800217a7  mov     [rbp+10D0h+var_10FE], al
0x1800217aa  movdqu  [rbp+10D0h+var_1110], xmm0
0x1800217af  mov     [rbp+10D0h+var_10FC], r13d
0x1800217b3  mov     [rbp+10D0h+var_10F8], r13w
0x1800217b8  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800217bd  jmp     loc_180021856
0x1800217c2  mov     ebx, r13d
0x1800217c5  cmp     [rbp+10D0h+var_111C], r13d
0x1800217c9  jbe     loc_180021856
0x1800217cf  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800217d3  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800217d8  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800217dc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800217e1  test    al, al
0x1800217e3  jz      short loc_180021856
0x1800217e5  mov     eax, [rbp+10D0h+var_10FC]
0x1800217e8  mov     rcx, [rbp+10D0h+var_1050]; this
0x1800217ef  mov     [rsp+11D0h+var_1180], eax
0x1800217f3  movzx   eax, [rbp+10D0h+var_10F8]
0x1800217f7  mov     [rbp+10D0h+var_10E0], rax
0x1800217fb  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800217ff  mov     [rbp+10D0h+var_10D8], rax
0x180021803  movzx   eax, [rbp+10D0h+var_1118]
0x180021807  mov     [rbp+10D0h+var_10D0], rax
0x18002180b  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18002180f  mov     [rbp+10D0h+var_10C8], rax
0x180021813  test    rcx, rcx
0x180021816  jz      loc_18002198F
0x18002181c  mov     rax, [rcx]
0x18002181f  lea     rdx, [rsp+11D0h+var_1180]
0x180021824  mov     [rsp+11D0h+var_11A8], rdx
0x180021829  lea     r9, [rbp+10D0h+var_10D8]
0x18002182d  lea     rdx, [rbp+10D0h+var_10E0]
0x180021831  mov     [rsp+11D0h+var_11B0], rdx
0x180021836  lea     r8, [rbp+10D0h+var_10D0]
0x18002183a  mov     rax, [rax+20h]
0x18002183e  lea     rdx, [rbp+10D0h+var_10C8]
0x180021842  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021847  test    al, al
0x180021849  jz      short loc_1800218C3
0x18002184b  inc     ebx
0x18002184d  cmp     ebx, [rbp+10D0h+var_111C]
0x180021850  jb      loc_1800217CF
0x180021856  mov     r8, [rdi+20h]; unsigned __int8 *
0x18002185a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18002185f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180021863  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180021868  test    al, al
0x18002186a  jnz     loc_1800217C2
0x180021870  mov     rcx, [rbp+10D0h+var_1050]
0x180021877  test    rcx, rcx
0x18002187a  jz      short loc_180021888
0x18002187c  mov     rax, [rcx]
0x18002187f  mov     rax, [rax+18h]
0x180021883  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180021888  mov     bl, 1
0x18002188a  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18002188e  jz      short loc_180021902
0x180021890  mov     rdx, [rsp+11D0h+var_1158]
0x180021895  mov     rcx, r14
0x180021898  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18002189c  mov     eax, [rsp+11D0h+var_1188]
0x1800218a0  sub     r8d, edx
0x1800218a3  mov     [rsp+11D0h+var_11A0], 1
0x1800218ab  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800218af  call    wil_details_NtUpdateWnfStateData
0x1800218b4  cmp     eax, 0C0000001h
0x1800218b9  jnz     short loc_1800218E0
0x1800218bb  inc     r15
0x1800218be  mov     bl, r13b
0x1800218c1  jmp     short loc_18002190E
0x1800218c3  mov     rcx, [rbp+10D0h+var_1050]
0x1800218ca  test    rcx, rcx
0x1800218cd  jz      short loc_1800218DB
0x1800218cf  mov     rax, [rcx]
0x1800218d2  mov     rax, [rax+18h]
0x1800218d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800218db  mov     bl, r13b
0x1800218de  jmp     short loc_18002188A
0x1800218e0  test    eax, eax
0x1800218e2  jz      short loc_180021902
0x1800218e4  mov     rdx, [rsp+11D0h+var_1158]
0x1800218e9  mov     rcx, r14
0x1800218ec  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800218f0  sub     r8d, edx
0x1800218f3  mov     [rsp+11D0h+var_11A0], r13d
0x1800218f8  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x1800218fd  call    wil_details_NtUpdateWnfStateData
0x180021902  mov     rax, [rbp+10D0h+var_1130]
0x180021906  add     r14, 8
0x18002190a  mov     [rbp+10D0h+var_1128], rax
0x18002190e  mov     rsi, [rbp+10D0h+lpMem]
0x180021912  mov     [rbp+10D0h+lpMem], r13
0x180021916  test    rsi, rsi
0x180021919  jz      short loc_18002192F
0x18002191b  call    cs:__imp_GetProcessHeap
0x180021921  mov     r8, rsi; lpMem
0x180021924  xor     edx, edx; dwFlags
0x180021926  mov     rcx, rax; hHeap
0x180021929  call    cs:__imp_HeapFree
0x18002192f  test    bl, bl
0x180021931  jnz     short loc_180021965
0x180021933  cmp     r14, r12
0x180021936  jnb     short loc_180021965
0x180021938  cmp     r15, 32h ; '2'
0x18002193c  jb      loc_180021612
0x180021942  jmp     short loc_180021965
0x180021944  mov     rbx, [rbp+10D0h+lpMem]
0x180021948  mov     [rbp+10D0h+lpMem], r13
0x18002194c  test    rbx, rbx
0x18002194f  jz      short loc_180021965
0x180021951  call    cs:__imp_GetProcessHeap
0x180021957  mov     r8, rbx; lpMem
0x18002195a  xor     edx, edx; dwFlags
0x18002195c  mov     rcx, rax; hHeap
0x18002195f  call    cs:__imp_HeapFree
0x180021965  mov     rcx, [rbp+10D0h+var_40]
0x18002196c  xor     rcx, rsp; StackCookie
0x18002196f  call    __security_check_cookie
0x180021974  mov     rbx, [rsp+11D0h+arg_8]
0x18002197c  add     rsp, 11A0h
0x180021983  pop     r15
0x180021985  pop     r14
0x180021987  pop     r13
0x180021989  pop     r12
0x18002198b  pop     rdi
0x18002198c  pop     rsi
0x18002198d  pop     rbp
0x18002198e  retn
0x18002198f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
