# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000d5a0`
- end: `0x18000d977`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000cad8`

## callees

- `0x18000bff8`
- `0x18000c9e8`
- `0x18000d5a0`
- `0x18000e308`
- `0x18001138c`
- `0x1800127f0`
- `0x180014310`
- `0x1800143d0`
- `0x180015010`

## import_xrefs

- `KERNEL32!GetProcAddress` at `0x18000d696`
- `KERNEL32!GetProcAddress` at `0x18000d696`
- `KERNEL32!GetModuleHandleW` at `0x18000d67f`
- `KERNEL32!GetModuleHandleW` at `0x18000d67f`
- `KERNEL32!GetProcessHeap` at `0x18000d8fc`
- `KERNEL32!GetProcessHeap` at `0x18000d933`
- `KERNEL32!GetProcessHeap` at `0x18000d8fc`
- `KERNEL32!GetProcessHeap` at `0x18000d933`
- `KERNEL32!HeapFree` at `0x18000d90a`
- `KERNEL32!HeapFree` at `0x18000d941`
- `KERNEL32!HeapFree` at `0x18000d90a`
- `KERNEL32!HeapFree` at `0x18000d941`

## string_xrefs

- `0x18000d678`: `ntdll.dll`

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
0x18000d5a0  mov     [rsp-8+arg_8], rbx
0x18000d5a5  push    rbp
0x18000d5a6  push    rsi
0x18000d5a7  push    rdi
0x18000d5a8  push    r12
0x18000d5aa  push    r13
0x18000d5ac  push    r14
0x18000d5ae  push    r15
0x18000d5b0  lea     rbp, [rsp-10A0h]
0x18000d5b8  mov     eax, 11A0h
0x18000d5bd  call    _alloca_probe
0x18000d5c2  sub     rsp, rax
0x18000d5c5  mov     rax, cs:__security_cookie
0x18000d5cc  xor     rax, rsp
0x18000d5cf  mov     [rbp+10D0h+var_40], rax
0x18000d5d6  mov     rbx, r8
0x18000d5d9  mov     r14, rcx
0x18000d5dc  lea     r12, [rcx+rdx*8]
0x18000d5e0  xor     r13d, r13d
0x18000d5e3  mov     r15d, r13d
0x18000d5e6  mov     [rbp+10D0h+var_1128], r13
0x18000d5ea  mov     cl, [rbx+8]
0x18000d5ed  movzx   edx, word ptr [rbx+6]
0x18000d5f1  movzx   eax, word ptr [rbx]
0x18000d5f4  mov     [rsp+11D0h+var_1170], ax
0x18000d5f9  movzx   eax, word ptr [rbx+2]
0x18000d5fd  mov     [rsp+11D0h+var_116E], ax
0x18000d602  mov     al, [rbx+4]
0x18000d605  mov     [rsp+11D0h+var_116C], al
0x18000d609  mov     [rsp+11D0h+var_116A], dx
0x18000d60e  mov     [rsp+11D0h+var_1168], cl
0x18000d612  test    dx, dx
0x18000d615  jz      short loc_18000D634
0x18000d617  mov     eax, edx
0x18000d619  cmp     cl, 1
0x18000d61c  jnz     short loc_18000D624
0x18000d61e  add     rax, 2
0x18000d622  jmp     short loc_18000D62D
0x18000d624  cmp     cl, 2
0x18000d627  jnz     short loc_18000D62D
0x18000d629  add     rax, 4
0x18000d62d  mov     [rsp+11D0h+var_1160], rax
0x18000d632  jmp     short loc_18000D639
0x18000d634  mov     [rsp+11D0h+var_1160], r13
0x18000d639  mov     [rsp+11D0h+var_1158], r13
0x18000d63e  xorps   xmm0, xmm0
0x18000d641  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000d646  mov     [rbp+10D0h+lpMem], r13
0x18000d64a  mov     [rbp+10D0h+var_1138], r13w
0x18000d64f  mov     [rbp+10D0h+var_1136], r13b
0x18000d653  mov     [rsp+11D0h+var_1188], r13d
0x18000d658  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000d660  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000d667  test    rax, rax
0x18000d66a  jnz     short loc_18000D6AF
0x18000d66c  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d673  test    rax, rax
0x18000d676  jnz     short loc_18000D68C
0x18000d678  lea     rcx, ModuleName; "ntdll.dll"
0x18000d67f  call    cs:__imp_GetModuleHandleW
0x18000d685  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000d68c  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000d693  mov     rcx, rax; hModule
0x18000d696  call    cs:__imp_GetProcAddress
0x18000d69c  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000d6a3  test    rax, rax
0x18000d6a6  jnz     short loc_18000D6AF
0x18000d6a8  mov     edi, 0C0000139h
0x18000d6ad  jmp     short loc_18000D6D9
0x18000d6af  lea     rcx, [rsp+11D0h+var_1190]
0x18000d6b4  mov     [rsp+11D0h+var_11A8], rcx
0x18000d6b9  lea     rcx, [rbp+10D0h+var_1040]
0x18000d6c0  mov     [rsp+11D0h+var_11B0], rcx
0x18000d6c5  lea     r9, [rsp+11D0h+var_1188]
0x18000d6ca  xor     r8d, r8d
0x18000d6cd  xor     edx, edx
0x18000d6cf  mov     rcx, r14
0x18000d6d2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d6d7  mov     edi, eax
0x18000d6d9  mov     ecx, edi; this
0x18000d6db  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000d6e0  test    edi, edi
0x18000d6e2  jz      short loc_18000D6F2
0x18000d6e4  mov     eax, r13d
0x18000d6e7  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000d6eb  mov     [rsp+11D0h+var_1188], r13d
0x18000d6f0  jmp     short loc_18000D6F6
0x18000d6f2  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000d6f6  mov     r8d, eax; unsigned __int64
0x18000d6f9  mov     r9d, 1000h; unsigned __int64
0x18000d6ff  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000d706  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000d70b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000d710  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18000d714  jnz     loc_18000D926
0x18000d71a  mov     [rbp+10D0h+var_1130], r13
0x18000d71e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000d725  mov     [rbp+10D0h+var_10B0], rax
0x18000d729  lea     rax, [rbp+10D0h+var_1130]
0x18000d72d  mov     [rbp+10D0h+var_10A8], rax
0x18000d731  lea     rax, [rbp+10D0h+var_1128]
0x18000d735  mov     [rbp+10D0h+var_10A0], rax
0x18000d739  lea     rax, [rsp+11D0h+var_1170]
0x18000d73e  mov     [rbp+10D0h+var_1098], rax
0x18000d742  lea     rax, [rbp+10D0h+var_10B0]
0x18000d746  mov     [rbp+10D0h+var_1048], rax
0x18000d74d  lea     rax, [rbp+10D0h+var_10B8]
0x18000d751  mov     [rbp+10D0h+var_10C0], rax
0x18000d755  mov     rax, [rbx+18h]
0x18000d759  add     rax, 0Ah
0x18000d75d  mov     [rsp+11D0h+var_1190], rax
0x18000d762  movzx   eax, word ptr [rbx+2]
0x18000d766  mov     [rbp+10D0h+var_1120], ax
0x18000d76a  mov     al, [rbx+4]
0x18000d76d  mov     [rbp+10D0h+var_111E], al
0x18000d770  mov     [rbp+10D0h+var_111C], r13d
0x18000d774  mov     [rbp+10D0h+var_1118], r13w
0x18000d779  xorps   xmm0, xmm0
0x18000d77c  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000d781  movzx   eax, word ptr [rbx+6]
0x18000d785  mov     [rbp+10D0h+var_1100], ax
0x18000d789  mov     al, [rbx+8]
0x18000d78c  mov     [rbp+10D0h+var_10FE], al
0x18000d78f  mov     [rbp+10D0h+var_10FC], r13d
0x18000d793  mov     [rbp+10D0h+var_10F8], r13w
0x18000d798  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000d79d  jmp     loc_18000D836
0x18000d7a2  mov     edi, r13d
0x18000d7a5  cmp     [rbp+10D0h+var_111C], r13d
0x18000d7a9  jbe     loc_18000D836
0x18000d7af  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000d7b3  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000d7b8  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000d7bc  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d7c1  test    al, al
0x18000d7c3  jz      short loc_18000D836
0x18000d7c5  mov     eax, [rbp+10D0h+var_10FC]
0x18000d7c8  mov     [rsp+11D0h+var_1180], eax
0x18000d7cc  movzx   eax, [rbp+10D0h+var_10F8]
0x18000d7d0  mov     [rbp+10D0h+var_10E0], rax
0x18000d7d4  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000d7d8  mov     [rbp+10D0h+var_10D8], rax
0x18000d7dc  movzx   eax, [rbp+10D0h+var_1118]
0x18000d7e0  mov     [rbp+10D0h+var_10D0], rax
0x18000d7e4  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000d7e8  mov     [rbp+10D0h+var_10C8], rax
0x18000d7ec  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000d7f3  test    rcx, rcx
0x18000d7f6  jz      loc_18000D971
0x18000d7fc  mov     rax, [rcx]
0x18000d7ff  lea     rdx, [rsp+11D0h+var_1180]
0x18000d804  mov     [rsp+11D0h+var_11A8], rdx
0x18000d809  lea     rdx, [rbp+10D0h+var_10E0]
0x18000d80d  mov     [rsp+11D0h+var_11B0], rdx
0x18000d812  lea     r9, [rbp+10D0h+var_10D8]
0x18000d816  lea     r8, [rbp+10D0h+var_10D0]
0x18000d81a  lea     rdx, [rbp+10D0h+var_10C8]
0x18000d81e  mov     rax, [rax+20h]
0x18000d822  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d827  test    al, al
0x18000d829  jz      short loc_18000D8A4
0x18000d82b  inc     edi
0x18000d82d  cmp     edi, [rbp+10D0h+var_111C]
0x18000d830  jb      loc_18000D7AF
0x18000d836  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000d83a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000d83f  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000d843  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000d848  test    al, al
0x18000d84a  jnz     loc_18000D7A2
0x18000d850  mov     rcx, [rbp+10D0h+var_1048]
0x18000d857  test    rcx, rcx
0x18000d85a  jz      short loc_18000D868
0x18000d85c  mov     rax, [rcx]
0x18000d85f  mov     rax, [rax+18h]
0x18000d863  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d868  mov     dil, 1
0x18000d86b  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18000d86f  jz      short loc_18000D8E3
0x18000d871  mov     eax, [rsp+11D0h+var_1188]
0x18000d875  mov     rdx, [rsp+11D0h+var_1158]
0x18000d87a  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000d87e  sub     r8d, edx
0x18000d881  mov     [rsp+11D0h+var_11A0], 1
0x18000d889  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000d88d  mov     rcx, r14
0x18000d890  call    wil_details_NtUpdateWnfStateData
0x18000d895  cmp     eax, 0C0000001h
0x18000d89a  jnz     short loc_18000D8C1
0x18000d89c  inc     r15
0x18000d89f  mov     dil, r13b
0x18000d8a2  jmp     short loc_18000D8EF
0x18000d8a4  mov     rcx, [rbp+10D0h+var_1048]
0x18000d8ab  test    rcx, rcx
0x18000d8ae  jz      short loc_18000D8BC
0x18000d8b0  mov     rax, [rcx]
0x18000d8b3  mov     rax, [rax+18h]
0x18000d8b7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8bc  mov     dil, r13b
0x18000d8bf  jmp     short loc_18000D86B
0x18000d8c1  test    eax, eax
0x18000d8c3  jz      short loc_18000D8E3
0x18000d8c5  mov     rdx, [rsp+11D0h+var_1158]
0x18000d8ca  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000d8ce  sub     r8d, edx
0x18000d8d1  mov     [rsp+11D0h+var_11A0], r13d
0x18000d8d6  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000d8db  mov     rcx, r14
0x18000d8de  call    wil_details_NtUpdateWnfStateData
0x18000d8e3  add     r14, 8
0x18000d8e7  mov     rax, [rbp+10D0h+var_1130]
0x18000d8eb  mov     [rbp+10D0h+var_1128], rax
0x18000d8ef  mov     rsi, [rbp+10D0h+lpMem]
0x18000d8f3  mov     [rbp+10D0h+lpMem], r13
0x18000d8f7  test    rsi, rsi
0x18000d8fa  jz      short loc_18000D910
0x18000d8fc  call    cs:__imp_GetProcessHeap
0x18000d902  mov     rcx, rax; hHeap
0x18000d905  mov     r8, rsi; lpMem
0x18000d908  xor     edx, edx; dwFlags
0x18000d90a  call    cs:__imp_HeapFree
0x18000d910  test    dil, dil
0x18000d913  jnz     short loc_18000D947
0x18000d915  cmp     r14, r12
0x18000d918  jnb     short loc_18000D947
0x18000d91a  cmp     r15, 32h ; '2'
0x18000d91e  jb      loc_18000D5EA
0x18000d924  jmp     short loc_18000D947
0x18000d926  mov     rbx, [rbp+10D0h+lpMem]
0x18000d92a  mov     [rbp+10D0h+lpMem], r13
0x18000d92e  test    rbx, rbx
0x18000d931  jz      short loc_18000D947
0x18000d933  call    cs:__imp_GetProcessHeap
0x18000d939  mov     rcx, rax; hHeap
0x18000d93c  mov     r8, rbx; lpMem
0x18000d93f  xor     edx, edx; dwFlags
0x18000d941  call    cs:__imp_HeapFree
0x18000d947  mov     rcx, [rbp+10D0h+var_40]
0x18000d94e  xor     rcx, rsp; StackCookie
0x18000d951  call    __security_check_cookie
0x18000d956  mov     rbx, [rsp+11D0h+arg_8]
0x18000d95e  add     rsp, 11A0h
0x18000d965  pop     r15
0x18000d967  pop     r14
0x18000d969  pop     r13
0x18000d96b  pop     r12
0x18000d96d  pop     rdi
0x18000d96e  pop     rsi
0x18000d96f  pop     rbp
0x18000d970  retn
0x18000d971  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
