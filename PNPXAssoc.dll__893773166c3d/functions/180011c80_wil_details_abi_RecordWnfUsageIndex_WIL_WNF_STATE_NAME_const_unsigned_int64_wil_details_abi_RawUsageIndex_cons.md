# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180011c80`
- end: `0x18001204d`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180011428`

## callees

- `0x18000533c`
- `0x180011088`
- `0x180011338`
- `0x180011c80`
- `0x1800121f4`
- `0x180012d00`
- `0x180012e00`
- `0x180012e90`
- `0x180014010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180011fe1`
- `KERNEL32!HeapFree` at `0x180012017`
- `KERNEL32!HeapFree` at `0x180011fe1`
- `KERNEL32!HeapFree` at `0x180012017`
- `KERNEL32!GetProcAddress` at `0x180011d76`
- `KERNEL32!GetProcAddress` at `0x180011d76`
- `KERNEL32!GetProcessHeap` at `0x180011fd3`
- `KERNEL32!GetProcessHeap` at `0x180012009`
- `KERNEL32!GetProcessHeap` at `0x180011fd3`
- `KERNEL32!GetProcessHeap` at `0x180012009`
- `KERNEL32!GetModuleHandleW` at `0x180011d5f`
- `KERNEL32!GetModuleHandleW` at `0x180011d5f`

## string_xrefs

- `0x180011d58`: `ntdll.dll`

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
  __int64 v18; // r9
  char v19; // bl
  int updated; // eax
  __int64 v21; // r9
  void *v22; // rsi
  HANDLE ProcessHeap; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  __int64 *v26; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v26 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v7, 0, 0, v28);
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v7, v34, (int)v35 - (int)v34, v18, (int)v26, v28[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v7, v34, v35 - v34, v21, (int)v26, 0, 0);
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
0x180011c80  mov     [rsp-8+arg_8], rbx
0x180011c85  push    rbp
0x180011c86  push    rsi
0x180011c87  push    rdi
0x180011c88  push    r12
0x180011c8a  push    r13
0x180011c8c  push    r14
0x180011c8e  push    r15
0x180011c90  lea     rbp, [rsp-10A0h]
0x180011c98  mov     eax, 11A0h
0x180011c9d  call    _alloca_probe
0x180011ca2  sub     rsp, rax
0x180011ca5  mov     rax, cs:__security_cookie
0x180011cac  xor     rax, rsp
0x180011caf  mov     [rbp+10D0h+var_40], rax
0x180011cb6  xor     r13d, r13d
0x180011cb9  lea     r12, [rcx+rdx*8]
0x180011cbd  mov     r15d, r13d
0x180011cc0  mov     [rbp+10D0h+var_1128], r13
0x180011cc4  mov     rdi, r8
0x180011cc7  mov     r14, rcx
0x180011cca  movzx   eax, word ptr [rdi]
0x180011ccd  movzx   edx, word ptr [rdi+6]
0x180011cd1  mov     cl, [rdi+8]
0x180011cd4  mov     [rsp+11D0h+var_1170], ax
0x180011cd9  movzx   eax, word ptr [rdi+2]
0x180011cdd  mov     [rsp+11D0h+var_116E], ax
0x180011ce2  mov     al, [rdi+4]
0x180011ce5  mov     [rsp+11D0h+var_116C], al
0x180011ce9  mov     [rsp+11D0h+var_116A], dx
0x180011cee  mov     [rsp+11D0h+var_1168], cl
0x180011cf2  test    dx, dx
0x180011cf5  jz      short loc_180011D14
0x180011cf7  mov     eax, edx
0x180011cf9  cmp     cl, 1
0x180011cfc  jnz     short loc_180011D04
0x180011cfe  add     rax, 2
0x180011d02  jmp     short loc_180011D0D
0x180011d04  cmp     cl, 2
0x180011d07  jnz     short loc_180011D0D
0x180011d09  add     rax, 4
0x180011d0d  mov     [rsp+11D0h+var_1160], rax
0x180011d12  jmp     short loc_180011D19
0x180011d14  mov     [rsp+11D0h+var_1160], r13
0x180011d19  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180011d20  xorps   xmm0, xmm0
0x180011d23  mov     [rsp+11D0h+var_1158], r13
0x180011d28  movdqa  [rbp+10D0h+var_1150], xmm0
0x180011d2d  mov     [rbp+10D0h+lpMem], r13
0x180011d31  mov     [rbp+10D0h+var_1138], r13w
0x180011d36  mov     [rbp+10D0h+var_1136], r13b
0x180011d3a  mov     [rsp+11D0h+var_1188], r13d
0x180011d3f  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180011d47  test    rax, rax
0x180011d4a  jnz     short loc_180011D8F
0x180011d4c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011d53  test    rax, rax
0x180011d56  jnz     short loc_180011D6C
0x180011d58  lea     rcx, ModuleName; "ntdll.dll"
0x180011d5f  call    cs:__imp_GetModuleHandleW
0x180011d65  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011d6c  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180011d73  mov     rcx, rax; hModule
0x180011d76  call    cs:__imp_GetProcAddress
0x180011d7c  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180011d83  test    rax, rax
0x180011d86  jnz     short loc_180011D8F
0x180011d88  mov     ebx, 0C0000139h
0x180011d8d  jmp     short loc_180011DB9
0x180011d8f  lea     rcx, [rsp+11D0h+var_1190]
0x180011d94  xor     r8d, r8d
0x180011d97  mov     [rsp+11D0h+var_11A8], rcx
0x180011d9c  lea     r9, [rsp+11D0h+var_1188]
0x180011da1  lea     rcx, [rbp+10D0h+var_1040]
0x180011da8  xor     edx, edx
0x180011daa  mov     [rsp+11D0h+var_11B0], rcx
0x180011daf  mov     rcx, r14
0x180011db2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011db7  mov     ebx, eax
0x180011db9  mov     ecx, ebx; this
0x180011dbb  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180011dc0  test    ebx, ebx
0x180011dc2  jz      short loc_180011DD2
0x180011dc4  mov     eax, r13d
0x180011dc7  mov     [rsp+11D0h+var_1188], r13d
0x180011dcc  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180011dd0  jmp     short loc_180011DD6
0x180011dd2  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180011dd6  mov     r8d, eax; unsigned __int64
0x180011dd9  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180011de0  mov     r9d, 1000h; unsigned __int64
0x180011de6  lea     rcx, [rsp+11D0h+var_1170]; this
0x180011deb  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180011df0  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180011df4  jnz     loc_180011FFC
0x180011dfa  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180011e01  mov     [rbp+10D0h+var_1130], r13
0x180011e05  mov     [rbp+10D0h+var_10B8], rax
0x180011e09  xorps   xmm0, xmm0
0x180011e0c  lea     rax, [rbp+10D0h+var_1130]
0x180011e10  mov     [rbp+10D0h+var_111C], r13d
0x180011e14  mov     [rbp+10D0h+var_10B0], rax
0x180011e18  lea     rax, [rbp+10D0h+var_1128]
0x180011e1c  mov     [rbp+10D0h+var_10A8], rax
0x180011e20  lea     rax, [rsp+11D0h+var_1170]
0x180011e25  mov     [rbp+10D0h+var_10A0], rax
0x180011e29  lea     rax, [rbp+10D0h+var_10B8]
0x180011e2d  mov     [rbp+10D0h+var_1050], rax
0x180011e34  mov     rax, [rdi+18h]
0x180011e38  add     rax, 0Ah
0x180011e3c  mov     [rbp+10D0h+var_1118], r13w
0x180011e41  mov     [rsp+11D0h+var_1190], rax
0x180011e46  movzx   eax, word ptr [rdi+2]
0x180011e4a  mov     [rbp+10D0h+var_1120], ax
0x180011e4e  mov     al, [rdi+4]
0x180011e51  mov     [rbp+10D0h+var_111E], al
0x180011e54  movzx   eax, word ptr [rdi+6]
0x180011e58  mov     [rbp+10D0h+var_1100], ax
0x180011e5c  mov     al, [rdi+8]
0x180011e5f  mov     [rbp+10D0h+var_10FE], al
0x180011e62  movdqu  [rbp+10D0h+var_1110], xmm0
0x180011e67  mov     [rbp+10D0h+var_10FC], r13d
0x180011e6b  mov     [rbp+10D0h+var_10F8], r13w
0x180011e70  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180011e75  jmp     loc_180011F0E
0x180011e7a  mov     ebx, r13d
0x180011e7d  cmp     [rbp+10D0h+var_111C], r13d
0x180011e81  jbe     loc_180011F0E
0x180011e87  mov     r8, [rdi+20h]; unsigned __int8 *
0x180011e8b  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180011e90  lea     rcx, [rbp+10D0h+var_1100]; this
0x180011e94  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180011e99  test    al, al
0x180011e9b  jz      short loc_180011F0E
0x180011e9d  mov     eax, [rbp+10D0h+var_10FC]
0x180011ea0  mov     rcx, [rbp+10D0h+var_1050]; this
0x180011ea7  mov     [rsp+11D0h+var_1180], eax
0x180011eab  movzx   eax, [rbp+10D0h+var_10F8]
0x180011eaf  mov     [rbp+10D0h+var_10E0], rax
0x180011eb3  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180011eb7  mov     [rbp+10D0h+var_10D8], rax
0x180011ebb  movzx   eax, [rbp+10D0h+var_1118]
0x180011ebf  mov     [rbp+10D0h+var_10D0], rax
0x180011ec3  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x180011ec7  mov     [rbp+10D0h+var_10C8], rax
0x180011ecb  test    rcx, rcx
0x180011ece  jz      loc_180012047
0x180011ed4  mov     rax, [rcx]
0x180011ed7  lea     rdx, [rsp+11D0h+var_1180]
0x180011edc  mov     [rsp+11D0h+var_11A8], rdx
0x180011ee1  lea     r9, [rbp+10D0h+var_10D8]
0x180011ee5  lea     rdx, [rbp+10D0h+var_10E0]
0x180011ee9  mov     [rsp+11D0h+var_11B0], rdx
0x180011eee  lea     r8, [rbp+10D0h+var_10D0]
0x180011ef2  mov     rax, [rax+20h]
0x180011ef6  lea     rdx, [rbp+10D0h+var_10C8]
0x180011efa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011eff  test    al, al
0x180011f01  jz      short loc_180011F7B
0x180011f03  inc     ebx
0x180011f05  cmp     ebx, [rbp+10D0h+var_111C]
0x180011f08  jb      loc_180011E87
0x180011f0e  mov     r8, [rdi+20h]; unsigned __int8 *
0x180011f12  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180011f17  lea     rcx, [rbp+10D0h+var_1120]; this
0x180011f1b  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180011f20  test    al, al
0x180011f22  jnz     loc_180011E7A
0x180011f28  mov     rcx, [rbp+10D0h+var_1050]
0x180011f2f  test    rcx, rcx
0x180011f32  jz      short loc_180011F40
0x180011f34  mov     rax, [rcx]
0x180011f37  mov     rax, [rax+18h]
0x180011f3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f40  mov     bl, 1
0x180011f42  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x180011f46  jz      short loc_180011FBA
0x180011f48  mov     rdx, [rsp+11D0h+var_1158]
0x180011f4d  mov     rcx, r14
0x180011f50  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180011f54  mov     eax, [rsp+11D0h+var_1188]
0x180011f58  sub     r8d, edx
0x180011f5b  mov     [rsp+11D0h+var_11A0], 1
0x180011f63  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180011f67  call    wil_details_NtUpdateWnfStateData
0x180011f6c  cmp     eax, 0C0000001h
0x180011f71  jnz     short loc_180011F98
0x180011f73  inc     r15
0x180011f76  mov     bl, r13b
0x180011f79  jmp     short loc_180011FC6
0x180011f7b  mov     rcx, [rbp+10D0h+var_1050]
0x180011f82  test    rcx, rcx
0x180011f85  jz      short loc_180011F93
0x180011f87  mov     rax, [rcx]
0x180011f8a  mov     rax, [rax+18h]
0x180011f8e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011f93  mov     bl, r13b
0x180011f96  jmp     short loc_180011F42
0x180011f98  test    eax, eax
0x180011f9a  jz      short loc_180011FBA
0x180011f9c  mov     rdx, [rsp+11D0h+var_1158]
0x180011fa1  mov     rcx, r14
0x180011fa4  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180011fa8  sub     r8d, edx
0x180011fab  mov     [rsp+11D0h+var_11A0], r13d
0x180011fb0  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x180011fb5  call    wil_details_NtUpdateWnfStateData
0x180011fba  mov     rax, [rbp+10D0h+var_1130]
0x180011fbe  add     r14, 8
0x180011fc2  mov     [rbp+10D0h+var_1128], rax
0x180011fc6  mov     rsi, [rbp+10D0h+lpMem]
0x180011fca  mov     [rbp+10D0h+lpMem], r13
0x180011fce  test    rsi, rsi
0x180011fd1  jz      short loc_180011FE7
0x180011fd3  call    cs:__imp_GetProcessHeap
0x180011fd9  mov     r8, rsi; lpMem
0x180011fdc  xor     edx, edx; dwFlags
0x180011fde  mov     rcx, rax; hHeap
0x180011fe1  call    cs:__imp_HeapFree
0x180011fe7  test    bl, bl
0x180011fe9  jnz     short loc_18001201D
0x180011feb  cmp     r14, r12
0x180011fee  jnb     short loc_18001201D
0x180011ff0  cmp     r15, 32h ; '2'
0x180011ff4  jb      loc_180011CCA
0x180011ffa  jmp     short loc_18001201D
0x180011ffc  mov     rbx, [rbp+10D0h+lpMem]
0x180012000  mov     [rbp+10D0h+lpMem], r13
0x180012004  test    rbx, rbx
0x180012007  jz      short loc_18001201D
0x180012009  call    cs:__imp_GetProcessHeap
0x18001200f  mov     r8, rbx; lpMem
0x180012012  xor     edx, edx; dwFlags
0x180012014  mov     rcx, rax; hHeap
0x180012017  call    cs:__imp_HeapFree
0x18001201d  mov     rcx, [rbp+10D0h+var_40]
0x180012024  xor     rcx, rsp; StackCookie
0x180012027  call    __security_check_cookie
0x18001202c  mov     rbx, [rsp+11D0h+arg_8]
0x180012034  add     rsp, 11A0h
0x18001203b  pop     r15
0x18001203d  pop     r14
0x18001203f  pop     r13
0x180012041  pop     r12
0x180012043  pop     rdi
0x180012044  pop     rsi
0x180012045  pop     rbp
0x180012046  retn
0x180012047  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
