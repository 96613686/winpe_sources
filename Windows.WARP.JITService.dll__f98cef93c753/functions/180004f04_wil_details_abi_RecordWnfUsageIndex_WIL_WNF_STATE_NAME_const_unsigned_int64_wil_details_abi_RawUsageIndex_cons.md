# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180004f04`
- end: `0x1800052dc`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800053e4`

## callees

- `0x180001bf0`
- `0x180002e94`
- `0x180003118`
- `0x1800043ec`
- `0x1800045b4`
- `0x180004f04`
- `0x180008a80`
- `0x180009830`
- `0x18000a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004fe4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180004fe4`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ffb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180004ffb`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005270`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052a6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180005270`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800052a6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005262`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005298`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005262`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180005298`

## string_xrefs

- `0x180004fdd`: `ntdll.dll`

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
0x180004f04  mov     [rsp-8+arg_8], rbx
0x180004f09  push    rbp
0x180004f0a  push    rsi
0x180004f0b  push    rdi
0x180004f0c  push    r12
0x180004f0e  push    r13
0x180004f10  push    r14
0x180004f12  push    r15
0x180004f14  lea     rbp, [rsp-10A0h]
0x180004f1c  mov     eax, 11A0h
0x180004f21  call    _alloca_probe
0x180004f26  sub     rsp, rax
0x180004f29  mov     rax, cs:__security_cookie
0x180004f30  xor     rax, rsp
0x180004f33  mov     [rbp+10D0h+var_40], rax
0x180004f3a  mov     rdi, r8
0x180004f3d  mov     r14, rcx
0x180004f40  lea     r13, [rcx+rdx*8]
0x180004f44  xor     r15d, r15d
0x180004f47  mov     r12d, r15d
0x180004f4a  mov     [rbp+10D0h+var_1128], r15
0x180004f4e  mov     cl, [rdi+8]
0x180004f51  movzx   edx, word ptr [rdi+6]
0x180004f55  movzx   eax, word ptr [rdi]
0x180004f58  mov     [rsp+11D0h+var_1170], ax
0x180004f5d  movzx   eax, word ptr [rdi+2]
0x180004f61  mov     [rsp+11D0h+var_116E], ax
0x180004f66  mov     al, [rdi+4]
0x180004f69  mov     [rsp+11D0h+var_116C], al
0x180004f6d  mov     [rsp+11D0h+var_116A], dx
0x180004f72  mov     [rsp+11D0h+var_1168], cl
0x180004f76  test    dx, dx
0x180004f79  jz      short loc_180004F98
0x180004f7b  mov     eax, edx
0x180004f7d  cmp     cl, 1
0x180004f80  jnz     short loc_180004F88
0x180004f82  add     rax, 2
0x180004f86  jmp     short loc_180004F91
0x180004f88  cmp     cl, 2
0x180004f8b  jnz     short loc_180004F91
0x180004f8d  add     rax, 4
0x180004f91  mov     [rsp+11D0h+var_1160], rax
0x180004f96  jmp     short loc_180004F9D
0x180004f98  mov     [rsp+11D0h+var_1160], r15
0x180004f9d  mov     [rsp+11D0h+var_1158], r15
0x180004fa2  xorps   xmm0, xmm0
0x180004fa5  movdqa  [rbp+10D0h+var_1150], xmm0
0x180004faa  mov     [rbp+10D0h+lpMem], r15
0x180004fae  mov     [rbp+10D0h+var_1138], 0
0x180004fb4  mov     [rbp+10D0h+var_1136], r15b
0x180004fb8  mov     [rsp+11D0h+var_1188], r15d
0x180004fbd  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180004fc5  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180004fcc  test    rax, rax
0x180004fcf  jnz     short loc_180005014
0x180004fd1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004fd8  test    rax, rax
0x180004fdb  jnz     short loc_180004FF1
0x180004fdd  lea     rcx, ModuleName; "ntdll.dll"
0x180004fe4  call    cs:__imp_GetModuleHandleW
0x180004fea  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180004ff1  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180004ff8  mov     rcx, rax; hModule
0x180004ffb  call    cs:__imp_GetProcAddress
0x180005001  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180005008  test    rax, rax
0x18000500b  jnz     short loc_180005014
0x18000500d  mov     ebx, 0C0000139h
0x180005012  jmp     short loc_18000503E
0x180005014  lea     rcx, [rsp+11D0h+var_1190]
0x180005019  mov     [rsp+11D0h+var_11A8], rcx
0x18000501e  lea     rcx, [rbp+10D0h+var_1040]
0x180005025  mov     [rsp+11D0h+var_11B0], rcx
0x18000502a  lea     r9, [rsp+11D0h+var_1188]
0x18000502f  xor     r8d, r8d
0x180005032  xor     edx, edx
0x180005034  mov     rcx, r14
0x180005037  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000503c  mov     ebx, eax
0x18000503e  mov     ecx, ebx; this
0x180005040  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180005045  test    ebx, ebx
0x180005047  jz      short loc_180005057
0x180005049  mov     eax, r15d
0x18000504c  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180005050  mov     [rsp+11D0h+var_1188], r15d
0x180005055  jmp     short loc_18000505B
0x180005057  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000505b  mov     r8d, eax; unsigned __int64
0x18000505e  mov     r9d, 1000h; unsigned __int64
0x180005064  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000506b  lea     rcx, [rsp+11D0h+var_1170]; this
0x180005070  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180005075  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180005079  jnz     loc_18000528B
0x18000507f  mov     [rbp+10D0h+var_1130], r15
0x180005083  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000508a  mov     [rbp+10D0h+var_10B0], rax
0x18000508e  lea     rax, [rbp+10D0h+var_1130]
0x180005092  mov     [rbp+10D0h+var_10A8], rax
0x180005096  lea     rax, [rbp+10D0h+var_1128]
0x18000509a  mov     [rbp+10D0h+var_10A0], rax
0x18000509e  lea     rax, [rsp+11D0h+var_1170]
0x1800050a3  mov     [rbp+10D0h+var_1098], rax
0x1800050a7  lea     rax, [rbp+10D0h+var_10B0]
0x1800050ab  mov     [rbp+10D0h+var_1048], rax
0x1800050b2  lea     rax, [rbp+10D0h+var_10B8]
0x1800050b6  mov     [rbp+10D0h+var_10C0], rax
0x1800050ba  mov     rax, [rdi+18h]
0x1800050be  add     rax, 0Ah
0x1800050c2  mov     [rsp+11D0h+var_1190], rax
0x1800050c7  movzx   eax, word ptr [rdi+2]
0x1800050cb  mov     [rbp+10D0h+var_1120], ax
0x1800050cf  mov     al, [rdi+4]
0x1800050d2  mov     [rbp+10D0h+var_111E], al
0x1800050d5  mov     [rbp+10D0h+var_111C], r15d
0x1800050d9  mov     [rbp+10D0h+var_1118], r15w
0x1800050de  xorps   xmm0, xmm0
0x1800050e1  movdqu  [rbp+10D0h+var_1110], xmm0
0x1800050e6  movzx   eax, word ptr [rdi+6]
0x1800050ea  mov     [rbp+10D0h+var_1100], ax
0x1800050ee  mov     al, [rdi+8]
0x1800050f1  mov     [rbp+10D0h+var_10FE], al
0x1800050f4  mov     [rbp+10D0h+var_10FC], r15d
0x1800050f8  mov     [rbp+10D0h+var_10F8], r15w
0x1800050fd  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180005102  jmp     loc_18000519A
0x180005107  mov     ebx, r15d
0x18000510a  mov     esi, [rbp+10D0h+var_111C]
0x18000510d  test    esi, esi
0x18000510f  jz      loc_18000519A
0x180005115  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180005119  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000511d  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180005122  lea     rcx, [rbp+10D0h+var_1100]; this
0x180005126  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000512b  test    al, al
0x18000512d  jz      short loc_180005197
0x18000512f  mov     eax, [rbp+10D0h+var_10FC]
0x180005132  mov     [rsp+11D0h+var_1180], eax
0x180005136  movzx   eax, [rbp+10D0h+var_10F8]
0x18000513a  mov     [rbp+10D0h+var_10E0], rax
0x18000513e  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180005142  mov     [rbp+10D0h+var_10D8], rax
0x180005146  movzx   eax, [rbp+10D0h+var_1118]
0x18000514a  mov     [rbp+10D0h+var_10D0], rax
0x18000514e  mov     [rbp+10D0h+var_10C8], r15
0x180005152  mov     rcx, [rbp+10D0h+var_1048]; this
0x180005159  test    rcx, rcx
0x18000515c  jz      loc_1800052D6
0x180005162  mov     rax, [rcx]
0x180005165  lea     rdx, [rsp+11D0h+var_1180]
0x18000516a  mov     [rsp+11D0h+var_11A8], rdx
0x18000516f  lea     rdx, [rbp+10D0h+var_10E0]
0x180005173  mov     [rsp+11D0h+var_11B0], rdx
0x180005178  lea     r9, [rbp+10D0h+var_10D8]
0x18000517c  lea     r8, [rbp+10D0h+var_10D0]
0x180005180  lea     rdx, [rbp+10D0h+var_10C8]
0x180005184  mov     rax, [rax+20h]
0x180005188  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000518d  test    al, al
0x18000518f  jz      short loc_180005207
0x180005191  inc     ebx
0x180005193  cmp     ebx, esi
0x180005195  jb      short loc_180005119
0x180005197  xor     r15d, r15d
0x18000519a  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000519e  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800051a3  lea     rcx, [rbp+10D0h+var_1120]; this
0x1800051a7  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800051ac  test    al, al
0x1800051ae  jnz     loc_180005107
0x1800051b4  mov     rcx, [rbp+10D0h+var_1048]
0x1800051bb  test    rcx, rcx
0x1800051be  jz      short loc_1800051CC
0x1800051c0  mov     rax, [rcx]
0x1800051c3  mov     rax, [rax+18h]
0x1800051c7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800051cc  mov     bl, 1
0x1800051ce  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x1800051d2  jz      short loc_180005249
0x1800051d4  mov     eax, [rsp+11D0h+var_1188]
0x1800051d8  mov     rdx, [rsp+11D0h+var_1158]
0x1800051dd  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800051e1  sub     r8d, edx
0x1800051e4  mov     [rsp+11D0h+var_11A0], 1
0x1800051ec  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800051f0  mov     rcx, r14
0x1800051f3  call    wil_details_NtUpdateWnfStateData
0x1800051f8  cmp     eax, 0C0000001h
0x1800051fd  jnz     short loc_180005227
0x1800051ff  inc     r12
0x180005202  mov     bl, r15b
0x180005205  jmp     short loc_180005255
0x180005207  mov     rcx, [rbp+10D0h+var_1048]
0x18000520e  xor     r15d, r15d
0x180005211  test    rcx, rcx
0x180005214  jz      short loc_180005222
0x180005216  mov     rax, [rcx]
0x180005219  mov     rax, [rax+18h]
0x18000521d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180005222  mov     bl, r15b
0x180005225  jmp     short loc_1800051CE
0x180005227  test    eax, eax
0x180005229  jz      short loc_180005249
0x18000522b  mov     rdx, [rsp+11D0h+var_1158]
0x180005230  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180005234  sub     r8d, edx
0x180005237  mov     [rsp+11D0h+var_11A0], r15d
0x18000523c  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180005241  mov     rcx, r14
0x180005244  call    wil_details_NtUpdateWnfStateData
0x180005249  add     r14, 8
0x18000524d  mov     rax, [rbp+10D0h+var_1130]
0x180005251  mov     [rbp+10D0h+var_1128], rax
0x180005255  mov     rsi, [rbp+10D0h+lpMem]
0x180005259  mov     [rbp+10D0h+lpMem], r15
0x18000525d  test    rsi, rsi
0x180005260  jz      short loc_180005276
0x180005262  call    cs:__imp_GetProcessHeap
0x180005268  mov     rcx, rax; hHeap
0x18000526b  mov     r8, rsi; lpMem
0x18000526e  xor     edx, edx; dwFlags
0x180005270  call    cs:__imp_HeapFree
0x180005276  test    bl, bl
0x180005278  jnz     short loc_1800052AC
0x18000527a  cmp     r14, r13
0x18000527d  jnb     short loc_1800052AC
0x18000527f  cmp     r12, 32h ; '2'
0x180005283  jb      loc_180004F4E
0x180005289  jmp     short loc_1800052AC
0x18000528b  mov     rbx, [rbp+10D0h+lpMem]
0x18000528f  mov     [rbp+10D0h+lpMem], r15
0x180005293  test    rbx, rbx
0x180005296  jz      short loc_1800052AC
0x180005298  call    cs:__imp_GetProcessHeap
0x18000529e  mov     rcx, rax; hHeap
0x1800052a1  mov     r8, rbx; lpMem
0x1800052a4  xor     edx, edx; dwFlags
0x1800052a6  call    cs:__imp_HeapFree
0x1800052ac  mov     rcx, [rbp+10D0h+var_40]
0x1800052b3  xor     rcx, rsp; StackCookie
0x1800052b6  call    __security_check_cookie
0x1800052bb  mov     rbx, [rsp+11D0h+arg_8]
0x1800052c3  add     rsp, 11A0h
0x1800052ca  pop     r15
0x1800052cc  pop     r14
0x1800052ce  pop     r13
0x1800052d0  pop     r12
0x1800052d2  pop     rdi
0x1800052d3  pop     rsi
0x1800052d4  pop     rbp
0x1800052d5  retn
0x1800052d6  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
