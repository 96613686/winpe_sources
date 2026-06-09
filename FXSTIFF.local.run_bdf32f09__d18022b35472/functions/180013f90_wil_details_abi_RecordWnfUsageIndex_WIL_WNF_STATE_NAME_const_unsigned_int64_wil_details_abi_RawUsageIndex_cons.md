# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180013f90`
- end: `0x180014368`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800136bc`

## callees

- `0x180013038`
- `0x1800135cc`
- `0x180013f90`
- `0x180014758`
- `0x180015b5c`
- `0x180016254`
- `0x180017c00`
- `0x180017c90`
- `0x180019010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x1800142fb`
- `KERNEL32!HeapFree` at `0x180014332`
- `KERNEL32!HeapFree` at `0x1800142fb`
- `KERNEL32!HeapFree` at `0x180014332`
- `KERNEL32!GetProcessHeap` at `0x1800142ed`
- `KERNEL32!GetProcessHeap` at `0x180014324`
- `KERNEL32!GetProcessHeap` at `0x1800142ed`
- `KERNEL32!GetProcessHeap` at `0x180014324`
- `KERNEL32!GetModuleHandleW` at `0x18001406f`
- `KERNEL32!GetModuleHandleW` at `0x18001406f`
- `KERNEL32!GetProcAddress` at `0x180014086`
- `KERNEL32!GetProcAddress` at `0x180014086`

## string_xrefs

- `0x180014068`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v5; // r14
  wil::details_abi *v6; // r12
  unsigned __int64 v7; // r15
  char v8; // cl
  unsigned int v9; // edx
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // edi
  unsigned int v15; // eax
  int v16; // edi
  __int64 v17; // r9
  char v18; // di
  int updated; // eax
  __int64 v20; // r9
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  __int64 *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+64h] [rbp-9Ch]
  __int16 v30; // [rsp+66h] [rbp-9Ah]
  char v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  __int128 v34; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v36; // [rsp+98h] [rbp-68h]
  char v37; // [rsp+9Ah] [rbp-66h]
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v40; // [rsp+B0h] [rbp-50h] BYREF
  char v41; // [rsp+B2h] [rbp-4Eh]
  unsigned int v42; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v43; // [rsp+B8h] [rbp-48h]
  __int128 v44; // [rsp+C0h] [rbp-40h]
  __int16 v45; // [rsp+D0h] [rbp-30h] BYREF
  char v46; // [rsp+D2h] [rbp-2Eh]
  int v47; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v48; // [rsp+D8h] [rbp-28h]
  __int128 v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v52; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v53[2]; // [rsp+108h] [rbp+8h] BYREF
  char v54; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v55[13]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *v56; // [rsp+188h] [rbp+88h]
  _BYTE v57[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v39 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v28[0] = *(_WORD *)a3;
    v28[1] = *(_WORD *)(a3 + 2);
    v29 = *(_BYTE *)(a3 + 4);
    v30 = v9;
    v31 = v8;
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
      v32 = v10;
    }
    else
    {
      v32 = 0;
    }
    v33 = 0;
    v34 = 0;
    lpMem = 0;
    v36 = 0;
    v37 = 0;
    v27[0] = 0;
    LODWORD(v26) = 4096;
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
      v25 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v27);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v26) = 0;
      v27[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v26;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v28, v57, v15, 0x1000u);
    if ( HIBYTE(v36) )
      break;
    v38 = 0;
    v55[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v55[1] = &v38;
    v55[2] = &v39;
    v55[3] = v28;
    v56 = (wil::details::in1diag3 *)v55;
    v53[1] = &v54;
    v26 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v40 = *(_WORD *)(a3 + 2);
    v41 = *(_BYTE *)(a3 + 4);
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = *(_WORD *)(a3 + 6);
    v46 = *(_BYTE *)(a3 + 8);
    v47 = 0;
    v48 = 0;
    v49 = 0;
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v40,
              &v26,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      if ( v42 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v45,
                  &v26,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v27[2] = v47;
          v50 = v48;
          v51 = *((_QWORD *)&v49 + 1);
          v52 = v43;
          v53[0] = *((_QWORD *)&v44 + 1);
          if ( !v56 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v25 = &v50;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  v53,
                  &v52,
                  &v51) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
            v18 = 0;
            goto LABEL_29;
          }
          if ( ++v16 >= v42 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
    v18 = 1;
LABEL_29:
    if ( !(_BYTE)v36 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v33, (int)v34 - (int)v33, v17, (int)v25, v27[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v33, v34 - v33, v20, (int)v25, 0, 0);
LABEL_37:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v39 = v38;
      goto LABEL_38;
    }
    ++v7;
    v18 = 0;
LABEL_38:
    v21 = lpMem;
    lpMem = 0;
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
    if ( v18 || v5 >= v6 || v7 >= 0x32 )
      return;
  }
  v23 = lpMem;
  lpMem = 0;
  if ( v23 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v23);
  }
}

```

## disassembly

```asm
0x180013f90  mov     [rsp-8+arg_8], rbx
0x180013f95  push    rbp
0x180013f96  push    rsi
0x180013f97  push    rdi
0x180013f98  push    r12
0x180013f9a  push    r13
0x180013f9c  push    r14
0x180013f9e  push    r15
0x180013fa0  lea     rbp, [rsp-10A0h]
0x180013fa8  mov     eax, 11A0h
0x180013fad  call    _alloca_probe
0x180013fb2  sub     rsp, rax
0x180013fb5  mov     rax, cs:__security_cookie
0x180013fbc  xor     rax, rsp
0x180013fbf  mov     [rbp+10D0h+var_40], rax
0x180013fc6  mov     rbx, r8
0x180013fc9  mov     r14, rcx
0x180013fcc  lea     r12, [rcx+rdx*8]
0x180013fd0  xor     r13d, r13d
0x180013fd3  mov     r15d, r13d
0x180013fd6  mov     [rbp+10D0h+var_1128], r13
0x180013fda  mov     cl, [rbx+8]
0x180013fdd  movzx   edx, word ptr [rbx+6]
0x180013fe1  movzx   eax, word ptr [rbx]
0x180013fe4  mov     [rsp+11D0h+var_1170], ax
0x180013fe9  movzx   eax, word ptr [rbx+2]
0x180013fed  mov     [rsp+11D0h+var_116E], ax
0x180013ff2  mov     al, [rbx+4]
0x180013ff5  mov     [rsp+11D0h+var_116C], al
0x180013ff9  mov     [rsp+11D0h+var_116A], dx
0x180013ffe  mov     [rsp+11D0h+var_1168], cl
0x180014002  test    dx, dx
0x180014005  jz      short loc_180014024
0x180014007  mov     eax, edx
0x180014009  cmp     cl, 1
0x18001400c  jnz     short loc_180014014
0x18001400e  add     rax, 2
0x180014012  jmp     short loc_18001401D
0x180014014  cmp     cl, 2
0x180014017  jnz     short loc_18001401D
0x180014019  add     rax, 4
0x18001401d  mov     [rsp+11D0h+var_1160], rax
0x180014022  jmp     short loc_180014029
0x180014024  mov     [rsp+11D0h+var_1160], r13
0x180014029  mov     [rsp+11D0h+var_1158], r13
0x18001402e  xorps   xmm0, xmm0
0x180014031  movdqa  [rbp+10D0h+var_1150], xmm0
0x180014036  mov     [rbp+10D0h+lpMem], r13
0x18001403a  mov     [rbp+10D0h+var_1138], r13w
0x18001403f  mov     [rbp+10D0h+var_1136], r13b
0x180014043  mov     [rsp+11D0h+var_1188], r13d
0x180014048  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180014050  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180014057  test    rax, rax
0x18001405a  jnz     short loc_1800140A0
0x18001405c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014063  test    rax, rax
0x180014066  jnz     short loc_18001407C
0x180014068  lea     rcx, ModuleName; "ntdll.dll"
0x18001406f  call    cs:__imp_GetModuleHandleW
0x180014075  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001407c  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180014083  mov     rcx, rax; hModule
0x180014086  call    cs:__imp_GetProcAddress
0x18001408c  nop
0x18001408d  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180014094  test    rax, rax
0x180014097  jnz     short loc_1800140A0
0x180014099  mov     edi, 0C0000139h
0x18001409e  jmp     short loc_1800140CA
0x1800140a0  lea     rcx, [rsp+11D0h+var_1190]
0x1800140a5  mov     [rsp+11D0h+var_11A8], rcx
0x1800140aa  lea     rcx, [rbp+10D0h+var_1040]
0x1800140b1  mov     [rsp+11D0h+var_11B0], rcx
0x1800140b6  lea     r9, [rsp+11D0h+var_1188]
0x1800140bb  xor     r8d, r8d
0x1800140be  xor     edx, edx
0x1800140c0  mov     rcx, r14
0x1800140c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800140c8  mov     edi, eax
0x1800140ca  mov     ecx, edi; this
0x1800140cc  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800140d1  test    edi, edi
0x1800140d3  jz      short loc_1800140E3
0x1800140d5  mov     eax, r13d
0x1800140d8  mov     dword ptr [rsp+11D0h+var_1190], eax
0x1800140dc  mov     [rsp+11D0h+var_1188], r13d
0x1800140e1  jmp     short loc_1800140E7
0x1800140e3  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x1800140e7  mov     r8d, eax; unsigned __int64
0x1800140ea  mov     r9d, 1000h; unsigned __int64
0x1800140f0  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1800140f7  lea     rcx, [rsp+11D0h+var_1170]; this
0x1800140fc  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180014101  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180014105  jnz     loc_180014317
0x18001410b  mov     [rbp+10D0h+var_1130], r13
0x18001410f  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180014116  mov     [rbp+10D0h+var_10B0], rax
0x18001411a  lea     rax, [rbp+10D0h+var_1130]
0x18001411e  mov     [rbp+10D0h+var_10A8], rax
0x180014122  lea     rax, [rbp+10D0h+var_1128]
0x180014126  mov     [rbp+10D0h+var_10A0], rax
0x18001412a  lea     rax, [rsp+11D0h+var_1170]
0x18001412f  mov     [rbp+10D0h+var_1098], rax
0x180014133  lea     rax, [rbp+10D0h+var_10B0]
0x180014137  mov     [rbp+10D0h+var_1048], rax
0x18001413e  lea     rax, [rbp+10D0h+var_10B8]
0x180014142  mov     [rbp+10D0h+var_10C0], rax
0x180014146  mov     rax, [rbx+18h]
0x18001414a  add     rax, 0Ah
0x18001414e  mov     [rsp+11D0h+var_1190], rax
0x180014153  movzx   eax, word ptr [rbx+2]
0x180014157  mov     [rbp+10D0h+var_1120], ax
0x18001415b  mov     al, [rbx+4]
0x18001415e  mov     [rbp+10D0h+var_111E], al
0x180014161  mov     [rbp+10D0h+var_111C], r13d
0x180014165  mov     [rbp+10D0h+var_1118], r13w
0x18001416a  xorps   xmm0, xmm0
0x18001416d  movdqu  [rbp+10D0h+var_1110], xmm0
0x180014172  movzx   eax, word ptr [rbx+6]
0x180014176  mov     [rbp+10D0h+var_1100], ax
0x18001417a  mov     al, [rbx+8]
0x18001417d  mov     [rbp+10D0h+var_10FE], al
0x180014180  mov     [rbp+10D0h+var_10FC], r13d
0x180014184  mov     [rbp+10D0h+var_10F8], r13w
0x180014189  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18001418e  jmp     loc_180014227
0x180014193  mov     edi, r13d
0x180014196  cmp     [rbp+10D0h+var_111C], r13d
0x18001419a  jbe     loc_180014227
0x1800141a0  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800141a4  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800141a9  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800141ad  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800141b2  test    al, al
0x1800141b4  jz      short loc_180014227
0x1800141b6  mov     eax, [rbp+10D0h+var_10FC]
0x1800141b9  mov     [rsp+11D0h+var_1180], eax
0x1800141bd  movzx   eax, [rbp+10D0h+var_10F8]
0x1800141c1  mov     [rbp+10D0h+var_10E0], rax
0x1800141c5  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800141c9  mov     [rbp+10D0h+var_10D8], rax
0x1800141cd  movzx   eax, [rbp+10D0h+var_1118]
0x1800141d1  mov     [rbp+10D0h+var_10D0], rax
0x1800141d5  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x1800141d9  mov     [rbp+10D0h+var_10C8], rax
0x1800141dd  mov     rcx, [rbp+10D0h+var_1048]; this
0x1800141e4  test    rcx, rcx
0x1800141e7  jz      loc_180014362
0x1800141ed  mov     rax, [rcx]
0x1800141f0  lea     rdx, [rsp+11D0h+var_1180]
0x1800141f5  mov     [rsp+11D0h+var_11A8], rdx
0x1800141fa  lea     rdx, [rbp+10D0h+var_10E0]
0x1800141fe  mov     [rsp+11D0h+var_11B0], rdx
0x180014203  lea     r9, [rbp+10D0h+var_10D8]
0x180014207  lea     r8, [rbp+10D0h+var_10D0]
0x18001420b  lea     rdx, [rbp+10D0h+var_10C8]
0x18001420f  mov     rax, [rax+20h]
0x180014213  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014218  test    al, al
0x18001421a  jz      short loc_180014295
0x18001421c  inc     edi
0x18001421e  cmp     edi, [rbp+10D0h+var_111C]
0x180014221  jb      loc_1800141A0
0x180014227  mov     r8, [rbx+20h]; unsigned __int8 *
0x18001422b  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180014230  lea     rcx, [rbp+10D0h+var_1120]; this
0x180014234  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180014239  test    al, al
0x18001423b  jnz     loc_180014193
0x180014241  mov     rcx, [rbp+10D0h+var_1048]
0x180014248  test    rcx, rcx
0x18001424b  jz      short loc_180014259
0x18001424d  mov     rax, [rcx]
0x180014250  mov     rax, [rax+18h]
0x180014254  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180014259  mov     dil, 1
0x18001425c  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x180014260  jz      short loc_1800142D4
0x180014262  mov     eax, [rsp+11D0h+var_1188]
0x180014266  mov     rdx, [rsp+11D0h+var_1158]
0x18001426b  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18001426f  sub     r8d, edx
0x180014272  mov     [rsp+11D0h+var_11A0], 1
0x18001427a  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18001427e  mov     rcx, r14
0x180014281  call    wil_details_NtUpdateWnfStateData
0x180014286  cmp     eax, 0C0000001h
0x18001428b  jnz     short loc_1800142B2
0x18001428d  inc     r15
0x180014290  mov     dil, r13b
0x180014293  jmp     short loc_1800142E0
0x180014295  mov     rcx, [rbp+10D0h+var_1048]
0x18001429c  test    rcx, rcx
0x18001429f  jz      short loc_1800142AD
0x1800142a1  mov     rax, [rcx]
0x1800142a4  mov     rax, [rax+18h]
0x1800142a8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800142ad  mov     dil, r13b
0x1800142b0  jmp     short loc_18001425C
0x1800142b2  test    eax, eax
0x1800142b4  jz      short loc_1800142D4
0x1800142b6  mov     rdx, [rsp+11D0h+var_1158]
0x1800142bb  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800142bf  sub     r8d, edx
0x1800142c2  mov     [rsp+11D0h+var_11A0], r13d
0x1800142c7  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x1800142cc  mov     rcx, r14
0x1800142cf  call    wil_details_NtUpdateWnfStateData
0x1800142d4  add     r14, 8
0x1800142d8  mov     rax, [rbp+10D0h+var_1130]
0x1800142dc  mov     [rbp+10D0h+var_1128], rax
0x1800142e0  mov     rsi, [rbp+10D0h+lpMem]
0x1800142e4  mov     [rbp+10D0h+lpMem], r13
0x1800142e8  test    rsi, rsi
0x1800142eb  jz      short loc_180014301
0x1800142ed  call    cs:__imp_GetProcessHeap
0x1800142f3  mov     rcx, rax; hHeap
0x1800142f6  mov     r8, rsi; lpMem
0x1800142f9  xor     edx, edx; dwFlags
0x1800142fb  call    cs:__imp_HeapFree
0x180014301  test    dil, dil
0x180014304  jnz     short loc_180014338
0x180014306  cmp     r14, r12
0x180014309  jnb     short loc_180014338
0x18001430b  cmp     r15, 32h ; '2'
0x18001430f  jb      loc_180013FDA
0x180014315  jmp     short loc_180014338
0x180014317  mov     rbx, [rbp+10D0h+lpMem]
0x18001431b  mov     [rbp+10D0h+lpMem], r13
0x18001431f  test    rbx, rbx
0x180014322  jz      short loc_180014338
0x180014324  call    cs:__imp_GetProcessHeap
0x18001432a  mov     rcx, rax; hHeap
0x18001432d  mov     r8, rbx; lpMem
0x180014330  xor     edx, edx; dwFlags
0x180014332  call    cs:__imp_HeapFree
0x180014338  mov     rcx, [rbp+10D0h+var_40]
0x18001433f  xor     rcx, rsp; StackCookie
0x180014342  call    __security_check_cookie
0x180014347  mov     rbx, [rsp+11D0h+arg_8]
0x18001434f  add     rsp, 11A0h
0x180014356  pop     r15
0x180014358  pop     r14
0x18001435a  pop     r13
0x18001435c  pop     r12
0x18001435e  pop     rdi
0x18001435f  pop     rsi
0x180014360  pop     rbp
0x180014361  retn
0x180014362  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
