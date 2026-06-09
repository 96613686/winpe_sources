# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000683c`
- end: `0x180006c14`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180005f28`

## callees

- `0x1800016a0`
- `0x180005a78`
- `0x180005de0`
- `0x18000683c`
- `0x1800073d4`
- `0x18000870c`
- `0x180008f98`
- `0x18000caf0`
- `0x18000e010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006933`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006933`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000691c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000691c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ba8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bde`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ba8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006bde`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006bd0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006b9a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006bd0`

## string_xrefs

- `0x180006915`: `ntdll.dll`

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
0x18000683c  mov     [rsp-8+arg_8], rbx
0x180006841  push    rbp
0x180006842  push    rsi
0x180006843  push    rdi
0x180006844  push    r12
0x180006846  push    r13
0x180006848  push    r14
0x18000684a  push    r15
0x18000684c  lea     rbp, [rsp-10A0h]
0x180006854  mov     eax, 11A0h
0x180006859  call    _alloca_probe
0x18000685e  sub     rsp, rax
0x180006861  mov     rax, cs:__security_cookie
0x180006868  xor     rax, rsp
0x18000686b  mov     [rbp+10D0h+var_40], rax
0x180006872  mov     rdi, r8
0x180006875  mov     r14, rcx
0x180006878  lea     r13, [rcx+rdx*8]
0x18000687c  xor     r15d, r15d
0x18000687f  mov     r12d, r15d
0x180006882  mov     [rbp+10D0h+var_1128], r15
0x180006886  mov     cl, [rdi+8]
0x180006889  movzx   edx, word ptr [rdi+6]
0x18000688d  movzx   eax, word ptr [rdi]
0x180006890  mov     [rsp+11D0h+var_1170], ax
0x180006895  movzx   eax, word ptr [rdi+2]
0x180006899  mov     [rsp+11D0h+var_116E], ax
0x18000689e  mov     al, [rdi+4]
0x1800068a1  mov     [rsp+11D0h+var_116C], al
0x1800068a5  mov     [rsp+11D0h+var_116A], dx
0x1800068aa  mov     [rsp+11D0h+var_1168], cl
0x1800068ae  test    dx, dx
0x1800068b1  jz      short loc_1800068D0
0x1800068b3  mov     eax, edx
0x1800068b5  cmp     cl, 1
0x1800068b8  jnz     short loc_1800068C0
0x1800068ba  add     rax, 2
0x1800068be  jmp     short loc_1800068C9
0x1800068c0  cmp     cl, 2
0x1800068c3  jnz     short loc_1800068C9
0x1800068c5  add     rax, 4
0x1800068c9  mov     [rsp+11D0h+var_1160], rax
0x1800068ce  jmp     short loc_1800068D5
0x1800068d0  mov     [rsp+11D0h+var_1160], r15
0x1800068d5  mov     [rsp+11D0h+var_1158], r15
0x1800068da  xorps   xmm0, xmm0
0x1800068dd  movdqa  [rbp+10D0h+var_1150], xmm0
0x1800068e2  mov     [rbp+10D0h+lpMem], r15
0x1800068e6  mov     [rbp+10D0h+var_1138], 0
0x1800068ec  mov     [rbp+10D0h+var_1136], r15b
0x1800068f0  mov     [rsp+11D0h+var_1188], r15d
0x1800068f5  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1800068fd  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180006904  test    rax, rax
0x180006907  jnz     short loc_18000694C
0x180006909  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006910  test    rax, rax
0x180006913  jnz     short loc_180006929
0x180006915  lea     rcx, ModuleName; "ntdll.dll"
0x18000691c  call    cs:__imp_GetModuleHandleW
0x180006922  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006929  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180006930  mov     rcx, rax; hModule
0x180006933  call    cs:__imp_GetProcAddress
0x180006939  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180006940  test    rax, rax
0x180006943  jnz     short loc_18000694C
0x180006945  mov     ebx, 0C0000139h
0x18000694a  jmp     short loc_180006976
0x18000694c  lea     rcx, [rsp+11D0h+var_1190]
0x180006951  mov     [rsp+11D0h+var_11A8], rcx
0x180006956  lea     rcx, [rbp+10D0h+var_1040]
0x18000695d  mov     [rsp+11D0h+var_11B0], rcx
0x180006962  lea     r9, [rsp+11D0h+var_1188]
0x180006967  xor     r8d, r8d
0x18000696a  xor     edx, edx
0x18000696c  mov     rcx, r14
0x18000696f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006974  mov     ebx, eax
0x180006976  mov     ecx, ebx; this
0x180006978  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000697d  test    ebx, ebx
0x18000697f  jz      short loc_18000698F
0x180006981  mov     eax, r15d
0x180006984  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180006988  mov     [rsp+11D0h+var_1188], r15d
0x18000698d  jmp     short loc_180006993
0x18000698f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180006993  mov     r8d, eax; unsigned __int64
0x180006996  mov     r9d, 1000h; unsigned __int64
0x18000699c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1800069a3  lea     rcx, [rsp+11D0h+var_1170]; this
0x1800069a8  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1800069ad  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x1800069b1  jnz     loc_180006BC3
0x1800069b7  mov     [rbp+10D0h+var_1130], r15
0x1800069bb  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800069c2  mov     [rbp+10D0h+var_10B0], rax
0x1800069c6  lea     rax, [rbp+10D0h+var_1130]
0x1800069ca  mov     [rbp+10D0h+var_10A8], rax
0x1800069ce  lea     rax, [rbp+10D0h+var_1128]
0x1800069d2  mov     [rbp+10D0h+var_10A0], rax
0x1800069d6  lea     rax, [rsp+11D0h+var_1170]
0x1800069db  mov     [rbp+10D0h+var_1098], rax
0x1800069df  lea     rax, [rbp+10D0h+var_10B0]
0x1800069e3  mov     [rbp+10D0h+var_1048], rax
0x1800069ea  lea     rax, [rbp+10D0h+var_10B8]
0x1800069ee  mov     [rbp+10D0h+var_10C0], rax
0x1800069f2  mov     rax, [rdi+18h]
0x1800069f6  add     rax, 0Ah
0x1800069fa  mov     [rsp+11D0h+var_1190], rax
0x1800069ff  movzx   eax, word ptr [rdi+2]
0x180006a03  mov     [rbp+10D0h+var_1120], ax
0x180006a07  mov     al, [rdi+4]
0x180006a0a  mov     [rbp+10D0h+var_111E], al
0x180006a0d  mov     [rbp+10D0h+var_111C], r15d
0x180006a11  mov     [rbp+10D0h+var_1118], r15w
0x180006a16  xorps   xmm0, xmm0
0x180006a19  movdqu  [rbp+10D0h+var_1110], xmm0
0x180006a1e  movzx   eax, word ptr [rdi+6]
0x180006a22  mov     [rbp+10D0h+var_1100], ax
0x180006a26  mov     al, [rdi+8]
0x180006a29  mov     [rbp+10D0h+var_10FE], al
0x180006a2c  mov     [rbp+10D0h+var_10FC], r15d
0x180006a30  mov     [rbp+10D0h+var_10F8], r15w
0x180006a35  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180006a3a  jmp     loc_180006AD2
0x180006a3f  mov     ebx, r15d
0x180006a42  mov     esi, [rbp+10D0h+var_111C]
0x180006a45  test    esi, esi
0x180006a47  jz      loc_180006AD2
0x180006a4d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180006a51  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006a55  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180006a5a  lea     rcx, [rbp+10D0h+var_1100]; this
0x180006a5e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006a63  test    al, al
0x180006a65  jz      short loc_180006ACF
0x180006a67  mov     eax, [rbp+10D0h+var_10FC]
0x180006a6a  mov     [rsp+11D0h+var_1180], eax
0x180006a6e  movzx   eax, [rbp+10D0h+var_10F8]
0x180006a72  mov     [rbp+10D0h+var_10E0], rax
0x180006a76  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180006a7a  mov     [rbp+10D0h+var_10D8], rax
0x180006a7e  movzx   eax, [rbp+10D0h+var_1118]
0x180006a82  mov     [rbp+10D0h+var_10D0], rax
0x180006a86  mov     [rbp+10D0h+var_10C8], r15
0x180006a8a  mov     rcx, [rbp+10D0h+var_1048]; this
0x180006a91  test    rcx, rcx
0x180006a94  jz      loc_180006C0E
0x180006a9a  mov     rax, [rcx]
0x180006a9d  lea     rdx, [rsp+11D0h+var_1180]
0x180006aa2  mov     [rsp+11D0h+var_11A8], rdx
0x180006aa7  lea     rdx, [rbp+10D0h+var_10E0]
0x180006aab  mov     [rsp+11D0h+var_11B0], rdx
0x180006ab0  lea     r9, [rbp+10D0h+var_10D8]
0x180006ab4  lea     r8, [rbp+10D0h+var_10D0]
0x180006ab8  lea     rdx, [rbp+10D0h+var_10C8]
0x180006abc  mov     rax, [rax+20h]
0x180006ac0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ac5  test    al, al
0x180006ac7  jz      short loc_180006B3F
0x180006ac9  inc     ebx
0x180006acb  cmp     ebx, esi
0x180006acd  jb      short loc_180006A51
0x180006acf  xor     r15d, r15d
0x180006ad2  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006ad6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180006adb  lea     rcx, [rbp+10D0h+var_1120]; this
0x180006adf  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006ae4  test    al, al
0x180006ae6  jnz     loc_180006A3F
0x180006aec  mov     rcx, [rbp+10D0h+var_1048]
0x180006af3  test    rcx, rcx
0x180006af6  jz      short loc_180006B04
0x180006af8  mov     rax, [rcx]
0x180006afb  mov     rax, [rax+18h]
0x180006aff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b04  mov     bl, 1
0x180006b06  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180006b0a  jz      short loc_180006B81
0x180006b0c  mov     eax, [rsp+11D0h+var_1188]
0x180006b10  mov     rdx, [rsp+11D0h+var_1158]
0x180006b15  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006b19  sub     r8d, edx
0x180006b1c  mov     [rsp+11D0h+var_11A0], 1
0x180006b24  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180006b28  mov     rcx, r14
0x180006b2b  call    wil_details_NtUpdateWnfStateData
0x180006b30  cmp     eax, 0C0000001h
0x180006b35  jnz     short loc_180006B5F
0x180006b37  inc     r12
0x180006b3a  mov     bl, r15b
0x180006b3d  jmp     short loc_180006B8D
0x180006b3f  mov     rcx, [rbp+10D0h+var_1048]
0x180006b46  xor     r15d, r15d
0x180006b49  test    rcx, rcx
0x180006b4c  jz      short loc_180006B5A
0x180006b4e  mov     rax, [rcx]
0x180006b51  mov     rax, [rax+18h]
0x180006b55  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006b5a  mov     bl, r15b
0x180006b5d  jmp     short loc_180006B06
0x180006b5f  test    eax, eax
0x180006b61  jz      short loc_180006B81
0x180006b63  mov     rdx, [rsp+11D0h+var_1158]
0x180006b68  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006b6c  sub     r8d, edx
0x180006b6f  mov     [rsp+11D0h+var_11A0], r15d
0x180006b74  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180006b79  mov     rcx, r14
0x180006b7c  call    wil_details_NtUpdateWnfStateData
0x180006b81  add     r14, 8
0x180006b85  mov     rax, [rbp+10D0h+var_1130]
0x180006b89  mov     [rbp+10D0h+var_1128], rax
0x180006b8d  mov     rsi, [rbp+10D0h+lpMem]
0x180006b91  mov     [rbp+10D0h+lpMem], r15
0x180006b95  test    rsi, rsi
0x180006b98  jz      short loc_180006BAE
0x180006b9a  call    cs:__imp_GetProcessHeap
0x180006ba0  mov     rcx, rax; hHeap
0x180006ba3  mov     r8, rsi; lpMem
0x180006ba6  xor     edx, edx; dwFlags
0x180006ba8  call    cs:__imp_HeapFree
0x180006bae  test    bl, bl
0x180006bb0  jnz     short loc_180006BE4
0x180006bb2  cmp     r14, r13
0x180006bb5  jnb     short loc_180006BE4
0x180006bb7  cmp     r12, 32h ; '2'
0x180006bbb  jb      loc_180006886
0x180006bc1  jmp     short loc_180006BE4
0x180006bc3  mov     rbx, [rbp+10D0h+lpMem]
0x180006bc7  mov     [rbp+10D0h+lpMem], r15
0x180006bcb  test    rbx, rbx
0x180006bce  jz      short loc_180006BE4
0x180006bd0  call    cs:__imp_GetProcessHeap
0x180006bd6  mov     rcx, rax; hHeap
0x180006bd9  mov     r8, rbx; lpMem
0x180006bdc  xor     edx, edx; dwFlags
0x180006bde  call    cs:__imp_HeapFree
0x180006be4  mov     rcx, [rbp+10D0h+var_40]
0x180006beb  xor     rcx, rsp; StackCookie
0x180006bee  call    __security_check_cookie
0x180006bf3  mov     rbx, [rsp+11D0h+arg_8]
0x180006bfb  add     rsp, 11A0h
0x180006c02  pop     r15
0x180006c04  pop     r14
0x180006c06  pop     r13
0x180006c08  pop     r12
0x180006c0a  pop     rdi
0x180006c0b  pop     rsi
0x180006c0c  pop     rbp
0x180006c0d  retn
0x180006c0e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
