# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x14000ba10`
- end: `0x14000bde7`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14000afbc`

## callees

- `0x140006234`
- `0x14000a7d4`
- `0x14000aecc`
- `0x14000ba10`
- `0x14000c934`
- `0x14000dfe0`
- `0x14000e1c0`
- `0x14000e280`
- `0x14000f010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x14000bd7a`
- `KERNEL32!HeapFree` at `0x14000bdb1`
- `KERNEL32!HeapFree` at `0x14000bd7a`
- `KERNEL32!HeapFree` at `0x14000bdb1`
- `KERNEL32!GetProcAddress` at `0x14000bb06`
- `KERNEL32!GetProcAddress` at `0x14000bb06`
- `KERNEL32!GetProcessHeap` at `0x14000bd6c`
- `KERNEL32!GetProcessHeap` at `0x14000bda3`
- `KERNEL32!GetProcessHeap` at `0x14000bd6c`
- `KERNEL32!GetProcessHeap` at `0x14000bda3`
- `KERNEL32!GetModuleHandleW` at `0x14000baef`
- `KERNEL32!GetModuleHandleW` at `0x14000baef`

## string_xrefs

- `0x14000bae8`: `ntdll.dll`

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
0x14000ba10  mov     [rsp-8+arg_8], rbx
0x14000ba15  push    rbp
0x14000ba16  push    rsi
0x14000ba17  push    rdi
0x14000ba18  push    r12
0x14000ba1a  push    r13
0x14000ba1c  push    r14
0x14000ba1e  push    r15
0x14000ba20  lea     rbp, [rsp-10A0h]
0x14000ba28  mov     eax, 11A0h
0x14000ba2d  call    _alloca_probe
0x14000ba32  sub     rsp, rax
0x14000ba35  mov     rax, cs:__security_cookie
0x14000ba3c  xor     rax, rsp
0x14000ba3f  mov     [rbp+10D0h+var_40], rax
0x14000ba46  mov     rbx, r8
0x14000ba49  mov     r14, rcx
0x14000ba4c  lea     r12, [rcx+rdx*8]
0x14000ba50  xor     r13d, r13d
0x14000ba53  mov     r15d, r13d
0x14000ba56  mov     [rbp+10D0h+var_1128], r13
0x14000ba5a  mov     cl, [rbx+8]
0x14000ba5d  movzx   edx, word ptr [rbx+6]
0x14000ba61  movzx   eax, word ptr [rbx]
0x14000ba64  mov     [rsp+11D0h+var_1170], ax
0x14000ba69  movzx   eax, word ptr [rbx+2]
0x14000ba6d  mov     [rsp+11D0h+var_116E], ax
0x14000ba72  mov     al, [rbx+4]
0x14000ba75  mov     [rsp+11D0h+var_116C], al
0x14000ba79  mov     [rsp+11D0h+var_116A], dx
0x14000ba7e  mov     [rsp+11D0h+var_1168], cl
0x14000ba82  test    dx, dx
0x14000ba85  jz      short loc_14000BAA4
0x14000ba87  mov     eax, edx
0x14000ba89  cmp     cl, 1
0x14000ba8c  jnz     short loc_14000BA94
0x14000ba8e  add     rax, 2
0x14000ba92  jmp     short loc_14000BA9D
0x14000ba94  cmp     cl, 2
0x14000ba97  jnz     short loc_14000BA9D
0x14000ba99  add     rax, 4
0x14000ba9d  mov     [rsp+11D0h+var_1160], rax
0x14000baa2  jmp     short loc_14000BAA9
0x14000baa4  mov     [rsp+11D0h+var_1160], r13
0x14000baa9  mov     [rsp+11D0h+var_1158], r13
0x14000baae  xorps   xmm0, xmm0
0x14000bab1  movdqa  [rbp+10D0h+var_1150], xmm0
0x14000bab6  mov     [rbp+10D0h+lpMem], r13
0x14000baba  mov     [rbp+10D0h+var_1138], r13w
0x14000babf  mov     [rbp+10D0h+var_1136], r13b
0x14000bac3  mov     [rsp+11D0h+var_1188], r13d
0x14000bac8  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14000bad0  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000bad7  test    rax, rax
0x14000bada  jnz     short loc_14000BB1F
0x14000badc  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bae3  test    rax, rax
0x14000bae6  jnz     short loc_14000BAFC
0x14000bae8  lea     rcx, ModuleName; "ntdll.dll"
0x14000baef  call    cs:__imp_GetModuleHandleW
0x14000baf5  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000bafc  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000bb03  mov     rcx, rax; hModule
0x14000bb06  call    cs:__imp_GetProcAddress
0x14000bb0c  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000bb13  test    rax, rax
0x14000bb16  jnz     short loc_14000BB1F
0x14000bb18  mov     edi, 0C0000139h
0x14000bb1d  jmp     short loc_14000BB49
0x14000bb1f  lea     rcx, [rsp+11D0h+var_1190]
0x14000bb24  mov     [rsp+11D0h+var_11A8], rcx
0x14000bb29  lea     rcx, [rbp+10D0h+var_1040]
0x14000bb30  mov     [rsp+11D0h+var_11B0], rcx
0x14000bb35  lea     r9, [rsp+11D0h+var_1188]
0x14000bb3a  xor     r8d, r8d
0x14000bb3d  xor     edx, edx
0x14000bb3f  mov     rcx, r14
0x14000bb42  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb47  mov     edi, eax
0x14000bb49  mov     ecx, edi; this
0x14000bb4b  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000bb50  test    edi, edi
0x14000bb52  jz      short loc_14000BB62
0x14000bb54  mov     eax, r13d
0x14000bb57  mov     dword ptr [rsp+11D0h+var_1190], eax
0x14000bb5b  mov     [rsp+11D0h+var_1188], r13d
0x14000bb60  jmp     short loc_14000BB66
0x14000bb62  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x14000bb66  mov     r8d, eax; unsigned __int64
0x14000bb69  mov     r9d, 1000h; unsigned __int64
0x14000bb6f  lea     rdx, [rbp+10D0h+var_1040]; void *
0x14000bb76  lea     rcx, [rsp+11D0h+var_1170]; this
0x14000bb7b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x14000bb80  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x14000bb84  jnz     loc_14000BD96
0x14000bb8a  mov     [rbp+10D0h+var_1130], r13
0x14000bb8e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x14000bb95  mov     [rbp+10D0h+var_10B0], rax
0x14000bb99  lea     rax, [rbp+10D0h+var_1130]
0x14000bb9d  mov     [rbp+10D0h+var_10A8], rax
0x14000bba1  lea     rax, [rbp+10D0h+var_1128]
0x14000bba5  mov     [rbp+10D0h+var_10A0], rax
0x14000bba9  lea     rax, [rsp+11D0h+var_1170]
0x14000bbae  mov     [rbp+10D0h+var_1098], rax
0x14000bbb2  lea     rax, [rbp+10D0h+var_10B0]
0x14000bbb6  mov     [rbp+10D0h+var_1048], rax
0x14000bbbd  lea     rax, [rbp+10D0h+var_10B8]
0x14000bbc1  mov     [rbp+10D0h+var_10C0], rax
0x14000bbc5  mov     rax, [rbx+18h]
0x14000bbc9  add     rax, 0Ah
0x14000bbcd  mov     [rsp+11D0h+var_1190], rax
0x14000bbd2  movzx   eax, word ptr [rbx+2]
0x14000bbd6  mov     [rbp+10D0h+var_1120], ax
0x14000bbda  mov     al, [rbx+4]
0x14000bbdd  mov     [rbp+10D0h+var_111E], al
0x14000bbe0  mov     [rbp+10D0h+var_111C], r13d
0x14000bbe4  mov     [rbp+10D0h+var_1118], r13w
0x14000bbe9  xorps   xmm0, xmm0
0x14000bbec  movdqu  [rbp+10D0h+var_1110], xmm0
0x14000bbf1  movzx   eax, word ptr [rbx+6]
0x14000bbf5  mov     [rbp+10D0h+var_1100], ax
0x14000bbf9  mov     al, [rbx+8]
0x14000bbfc  mov     [rbp+10D0h+var_10FE], al
0x14000bbff  mov     [rbp+10D0h+var_10FC], r13d
0x14000bc03  mov     [rbp+10D0h+var_10F8], r13w
0x14000bc08  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14000bc0d  jmp     loc_14000BCA6
0x14000bc12  mov     edi, r13d
0x14000bc15  cmp     [rbp+10D0h+var_111C], r13d
0x14000bc19  jbe     loc_14000BCA6
0x14000bc1f  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000bc23  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000bc28  lea     rcx, [rbp+10D0h+var_1100]; this
0x14000bc2c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000bc31  test    al, al
0x14000bc33  jz      short loc_14000BCA6
0x14000bc35  mov     eax, [rbp+10D0h+var_10FC]
0x14000bc38  mov     [rsp+11D0h+var_1180], eax
0x14000bc3c  movzx   eax, [rbp+10D0h+var_10F8]
0x14000bc40  mov     [rbp+10D0h+var_10E0], rax
0x14000bc44  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000bc48  mov     [rbp+10D0h+var_10D8], rax
0x14000bc4c  movzx   eax, [rbp+10D0h+var_1118]
0x14000bc50  mov     [rbp+10D0h+var_10D0], rax
0x14000bc54  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x14000bc58  mov     [rbp+10D0h+var_10C8], rax
0x14000bc5c  mov     rcx, [rbp+10D0h+var_1048]; this
0x14000bc63  test    rcx, rcx
0x14000bc66  jz      loc_14000BDE1
0x14000bc6c  mov     rax, [rcx]
0x14000bc6f  lea     rdx, [rsp+11D0h+var_1180]
0x14000bc74  mov     [rsp+11D0h+var_11A8], rdx
0x14000bc79  lea     rdx, [rbp+10D0h+var_10E0]
0x14000bc7d  mov     [rsp+11D0h+var_11B0], rdx
0x14000bc82  lea     r9, [rbp+10D0h+var_10D8]
0x14000bc86  lea     r8, [rbp+10D0h+var_10D0]
0x14000bc8a  lea     rdx, [rbp+10D0h+var_10C8]
0x14000bc8e  mov     rax, [rax+20h]
0x14000bc92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bc97  test    al, al
0x14000bc99  jz      short loc_14000BD14
0x14000bc9b  inc     edi
0x14000bc9d  cmp     edi, [rbp+10D0h+var_111C]
0x14000bca0  jb      loc_14000BC1F
0x14000bca6  mov     r8, [rbx+20h]; unsigned __int8 *
0x14000bcaa  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000bcaf  lea     rcx, [rbp+10D0h+var_1120]; this
0x14000bcb3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000bcb8  test    al, al
0x14000bcba  jnz     loc_14000BC12
0x14000bcc0  mov     rcx, [rbp+10D0h+var_1048]
0x14000bcc7  test    rcx, rcx
0x14000bcca  jz      short loc_14000BCD8
0x14000bccc  mov     rax, [rcx]
0x14000bccf  mov     rax, [rax+18h]
0x14000bcd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bcd8  mov     dil, 1
0x14000bcdb  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x14000bcdf  jz      short loc_14000BD53
0x14000bce1  mov     eax, [rsp+11D0h+var_1188]
0x14000bce5  mov     rdx, [rsp+11D0h+var_1158]
0x14000bcea  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000bcee  sub     r8d, edx
0x14000bcf1  mov     [rsp+11D0h+var_11A0], 1
0x14000bcf9  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14000bcfd  mov     rcx, r14
0x14000bd00  call    wil_details_NtUpdateWnfStateData
0x14000bd05  cmp     eax, 0C0000001h
0x14000bd0a  jnz     short loc_14000BD31
0x14000bd0c  inc     r15
0x14000bd0f  mov     dil, r13b
0x14000bd12  jmp     short loc_14000BD5F
0x14000bd14  mov     rcx, [rbp+10D0h+var_1048]
0x14000bd1b  test    rcx, rcx
0x14000bd1e  jz      short loc_14000BD2C
0x14000bd20  mov     rax, [rcx]
0x14000bd23  mov     rax, [rax+18h]
0x14000bd27  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bd2c  mov     dil, r13b
0x14000bd2f  jmp     short loc_14000BCDB
0x14000bd31  test    eax, eax
0x14000bd33  jz      short loc_14000BD53
0x14000bd35  mov     rdx, [rsp+11D0h+var_1158]
0x14000bd3a  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000bd3e  sub     r8d, edx
0x14000bd41  mov     [rsp+11D0h+var_11A0], r13d
0x14000bd46  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x14000bd4b  mov     rcx, r14
0x14000bd4e  call    wil_details_NtUpdateWnfStateData
0x14000bd53  add     r14, 8
0x14000bd57  mov     rax, [rbp+10D0h+var_1130]
0x14000bd5b  mov     [rbp+10D0h+var_1128], rax
0x14000bd5f  mov     rsi, [rbp+10D0h+lpMem]
0x14000bd63  mov     [rbp+10D0h+lpMem], r13
0x14000bd67  test    rsi, rsi
0x14000bd6a  jz      short loc_14000BD80
0x14000bd6c  call    cs:__imp_GetProcessHeap
0x14000bd72  mov     rcx, rax; hHeap
0x14000bd75  mov     r8, rsi; lpMem
0x14000bd78  xor     edx, edx; dwFlags
0x14000bd7a  call    cs:__imp_HeapFree
0x14000bd80  test    dil, dil
0x14000bd83  jnz     short loc_14000BDB7
0x14000bd85  cmp     r14, r12
0x14000bd88  jnb     short loc_14000BDB7
0x14000bd8a  cmp     r15, 32h ; '2'
0x14000bd8e  jb      loc_14000BA5A
0x14000bd94  jmp     short loc_14000BDB7
0x14000bd96  mov     rbx, [rbp+10D0h+lpMem]
0x14000bd9a  mov     [rbp+10D0h+lpMem], r13
0x14000bd9e  test    rbx, rbx
0x14000bda1  jz      short loc_14000BDB7
0x14000bda3  call    cs:__imp_GetProcessHeap
0x14000bda9  mov     rcx, rax; hHeap
0x14000bdac  mov     r8, rbx; lpMem
0x14000bdaf  xor     edx, edx; dwFlags
0x14000bdb1  call    cs:__imp_HeapFree
0x14000bdb7  mov     rcx, [rbp+10D0h+var_40]
0x14000bdbe  xor     rcx, rsp; StackCookie
0x14000bdc1  call    __security_check_cookie
0x14000bdc6  mov     rbx, [rsp+11D0h+arg_8]
0x14000bdce  add     rsp, 11A0h
0x14000bdd5  pop     r15
0x14000bdd7  pop     r14
0x14000bdd9  pop     r13
0x14000bddb  pop     r12
0x14000bddd  pop     rdi
0x14000bdde  pop     rsi
0x14000bddf  pop     rbp
0x14000bde0  retn
0x14000bde1  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
