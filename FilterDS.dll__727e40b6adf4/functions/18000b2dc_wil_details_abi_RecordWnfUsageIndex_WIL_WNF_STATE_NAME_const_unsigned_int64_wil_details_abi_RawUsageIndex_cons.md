# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000b2dc`
- end: `0x18000b6b3`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `983`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000aa70`

## callees

- `0x180006ba4`
- `0x18000a578`
- `0x18000a980`
- `0x18000b2dc`
- `0x18000b9a0`
- `0x18000da64`
- `0x180021850`
- `0x180021910`
- `0x180024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b3d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b3d2`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b3bb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b3bb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b638`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b66f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b638`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b66f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b646`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b67d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b646`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b67d`

## string_xrefs

- `0x18000b3b4`: `ntdll.dll`

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
0x18000b2dc  mov     [rsp-8+arg_8], rbx
0x18000b2e1  push    rbp
0x18000b2e2  push    rsi
0x18000b2e3  push    rdi
0x18000b2e4  push    r12
0x18000b2e6  push    r13
0x18000b2e8  push    r14
0x18000b2ea  push    r15
0x18000b2ec  lea     rbp, [rsp-10A0h]
0x18000b2f4  mov     eax, 11A0h
0x18000b2f9  call    _alloca_probe
0x18000b2fe  sub     rsp, rax
0x18000b301  mov     rax, cs:__security_cookie
0x18000b308  xor     rax, rsp
0x18000b30b  mov     [rbp+10D0h+var_40], rax
0x18000b312  mov     rbx, r8
0x18000b315  mov     r14, rcx
0x18000b318  lea     r12, [rcx+rdx*8]
0x18000b31c  xor     r13d, r13d
0x18000b31f  mov     r15d, r13d
0x18000b322  mov     [rbp+10D0h+var_1128], r13
0x18000b326  mov     cl, [rbx+8]
0x18000b329  movzx   edx, word ptr [rbx+6]
0x18000b32d  movzx   eax, word ptr [rbx]
0x18000b330  mov     [rsp+11D0h+var_1170], ax
0x18000b335  movzx   eax, word ptr [rbx+2]
0x18000b339  mov     [rsp+11D0h+var_116E], ax
0x18000b33e  mov     al, [rbx+4]
0x18000b341  mov     [rsp+11D0h+var_116C], al
0x18000b345  mov     [rsp+11D0h+var_116A], dx
0x18000b34a  mov     [rsp+11D0h+var_1168], cl
0x18000b34e  test    dx, dx
0x18000b351  jz      short loc_18000B370
0x18000b353  mov     eax, edx
0x18000b355  cmp     cl, 1
0x18000b358  jnz     short loc_18000B360
0x18000b35a  add     rax, 2
0x18000b35e  jmp     short loc_18000B369
0x18000b360  cmp     cl, 2
0x18000b363  jnz     short loc_18000B369
0x18000b365  add     rax, 4
0x18000b369  mov     [rsp+11D0h+var_1160], rax
0x18000b36e  jmp     short loc_18000B375
0x18000b370  mov     [rsp+11D0h+var_1160], r13
0x18000b375  mov     [rsp+11D0h+var_1158], r13
0x18000b37a  xorps   xmm0, xmm0
0x18000b37d  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000b382  mov     [rbp+10D0h+lpMem], r13
0x18000b386  mov     [rbp+10D0h+var_1138], r13w
0x18000b38b  mov     [rbp+10D0h+var_1136], r13b
0x18000b38f  mov     [rsp+11D0h+var_1188], r13d
0x18000b394  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000b39c  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b3a3  test    rax, rax
0x18000b3a6  jnz     short loc_18000B3EB
0x18000b3a8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b3af  test    rax, rax
0x18000b3b2  jnz     short loc_18000B3C8
0x18000b3b4  lea     rcx, ModuleName; "ntdll.dll"
0x18000b3bb  call    cs:__imp_GetModuleHandleW
0x18000b3c1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b3c8  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b3cf  mov     rcx, rax; hModule
0x18000b3d2  call    cs:__imp_GetProcAddress
0x18000b3d8  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b3df  test    rax, rax
0x18000b3e2  jnz     short loc_18000B3EB
0x18000b3e4  mov     edi, 0C0000139h
0x18000b3e9  jmp     short loc_18000B415
0x18000b3eb  lea     rcx, [rsp+11D0h+var_1190]
0x18000b3f0  mov     [rsp+11D0h+var_11A8], rcx
0x18000b3f5  lea     rcx, [rbp+10D0h+var_1040]
0x18000b3fc  mov     [rsp+11D0h+var_11B0], rcx
0x18000b401  lea     r9, [rsp+11D0h+var_1188]
0x18000b406  xor     r8d, r8d
0x18000b409  xor     edx, edx
0x18000b40b  mov     rcx, r14
0x18000b40e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b413  mov     edi, eax
0x18000b415  mov     ecx, edi; this
0x18000b417  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000b41c  test    edi, edi
0x18000b41e  jz      short loc_18000B42E
0x18000b420  mov     eax, r13d
0x18000b423  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000b427  mov     [rsp+11D0h+var_1188], r13d
0x18000b42c  jmp     short loc_18000B432
0x18000b42e  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000b432  mov     r8d, eax; unsigned __int64
0x18000b435  mov     r9d, 1000h; unsigned __int64
0x18000b43b  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000b442  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000b447  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000b44c  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18000b450  jnz     loc_18000B662
0x18000b456  mov     [rbp+10D0h+var_1130], r13
0x18000b45a  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000b461  mov     [rbp+10D0h+var_10B0], rax
0x18000b465  lea     rax, [rbp+10D0h+var_1130]
0x18000b469  mov     [rbp+10D0h+var_10A8], rax
0x18000b46d  lea     rax, [rbp+10D0h+var_1128]
0x18000b471  mov     [rbp+10D0h+var_10A0], rax
0x18000b475  lea     rax, [rsp+11D0h+var_1170]
0x18000b47a  mov     [rbp+10D0h+var_1098], rax
0x18000b47e  lea     rax, [rbp+10D0h+var_10B0]
0x18000b482  mov     [rbp+10D0h+var_1048], rax
0x18000b489  lea     rax, [rbp+10D0h+var_10B8]
0x18000b48d  mov     [rbp+10D0h+var_10C0], rax
0x18000b491  mov     rax, [rbx+18h]
0x18000b495  add     rax, 0Ah
0x18000b499  mov     [rsp+11D0h+var_1190], rax
0x18000b49e  movzx   eax, word ptr [rbx+2]
0x18000b4a2  mov     [rbp+10D0h+var_1120], ax
0x18000b4a6  mov     al, [rbx+4]
0x18000b4a9  mov     [rbp+10D0h+var_111E], al
0x18000b4ac  mov     [rbp+10D0h+var_111C], r13d
0x18000b4b0  mov     [rbp+10D0h+var_1118], r13w
0x18000b4b5  xorps   xmm0, xmm0
0x18000b4b8  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000b4bd  movzx   eax, word ptr [rbx+6]
0x18000b4c1  mov     [rbp+10D0h+var_1100], ax
0x18000b4c5  mov     al, [rbx+8]
0x18000b4c8  mov     [rbp+10D0h+var_10FE], al
0x18000b4cb  mov     [rbp+10D0h+var_10FC], r13d
0x18000b4cf  mov     [rbp+10D0h+var_10F8], r13w
0x18000b4d4  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000b4d9  jmp     loc_18000B572
0x18000b4de  mov     edi, r13d
0x18000b4e1  cmp     [rbp+10D0h+var_111C], r13d
0x18000b4e5  jbe     loc_18000B572
0x18000b4eb  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000b4ef  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b4f4  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000b4f8  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b4fd  test    al, al
0x18000b4ff  jz      short loc_18000B572
0x18000b501  mov     eax, [rbp+10D0h+var_10FC]
0x18000b504  mov     [rsp+11D0h+var_1180], eax
0x18000b508  movzx   eax, [rbp+10D0h+var_10F8]
0x18000b50c  mov     [rbp+10D0h+var_10E0], rax
0x18000b510  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000b514  mov     [rbp+10D0h+var_10D8], rax
0x18000b518  movzx   eax, [rbp+10D0h+var_1118]
0x18000b51c  mov     [rbp+10D0h+var_10D0], rax
0x18000b520  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x18000b524  mov     [rbp+10D0h+var_10C8], rax
0x18000b528  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000b52f  test    rcx, rcx
0x18000b532  jz      loc_18000B6AD
0x18000b538  mov     rax, [rcx]
0x18000b53b  lea     rdx, [rsp+11D0h+var_1180]
0x18000b540  mov     [rsp+11D0h+var_11A8], rdx
0x18000b545  lea     rdx, [rbp+10D0h+var_10E0]
0x18000b549  mov     [rsp+11D0h+var_11B0], rdx
0x18000b54e  lea     r9, [rbp+10D0h+var_10D8]
0x18000b552  lea     r8, [rbp+10D0h+var_10D0]
0x18000b556  lea     rdx, [rbp+10D0h+var_10C8]
0x18000b55a  mov     rax, [rax+20h]
0x18000b55e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b563  test    al, al
0x18000b565  jz      short loc_18000B5E0
0x18000b567  inc     edi
0x18000b569  cmp     edi, [rbp+10D0h+var_111C]
0x18000b56c  jb      loc_18000B4EB
0x18000b572  mov     r8, [rbx+20h]; unsigned __int8 *
0x18000b576  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b57b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000b57f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b584  test    al, al
0x18000b586  jnz     loc_18000B4DE
0x18000b58c  mov     rcx, [rbp+10D0h+var_1048]
0x18000b593  test    rcx, rcx
0x18000b596  jz      short loc_18000B5A4
0x18000b598  mov     rax, [rcx]
0x18000b59b  mov     rax, [rax+18h]
0x18000b59f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5a4  mov     dil, 1
0x18000b5a7  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18000b5ab  jz      short loc_18000B61F
0x18000b5ad  mov     eax, [rsp+11D0h+var_1188]
0x18000b5b1  mov     rdx, [rsp+11D0h+var_1158]
0x18000b5b6  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b5ba  sub     r8d, edx
0x18000b5bd  mov     [rsp+11D0h+var_11A0], 1
0x18000b5c5  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000b5c9  mov     rcx, r14
0x18000b5cc  call    wil_details_NtUpdateWnfStateData
0x18000b5d1  cmp     eax, 0C0000001h
0x18000b5d6  jnz     short loc_18000B5FD
0x18000b5d8  inc     r15
0x18000b5db  mov     dil, r13b
0x18000b5de  jmp     short loc_18000B62B
0x18000b5e0  mov     rcx, [rbp+10D0h+var_1048]
0x18000b5e7  test    rcx, rcx
0x18000b5ea  jz      short loc_18000B5F8
0x18000b5ec  mov     rax, [rcx]
0x18000b5ef  mov     rax, [rax+18h]
0x18000b5f3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b5f8  mov     dil, r13b
0x18000b5fb  jmp     short loc_18000B5A7
0x18000b5fd  test    eax, eax
0x18000b5ff  jz      short loc_18000B61F
0x18000b601  mov     rdx, [rsp+11D0h+var_1158]
0x18000b606  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b60a  sub     r8d, edx
0x18000b60d  mov     [rsp+11D0h+var_11A0], r13d
0x18000b612  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x18000b617  mov     rcx, r14
0x18000b61a  call    wil_details_NtUpdateWnfStateData
0x18000b61f  add     r14, 8
0x18000b623  mov     rax, [rbp+10D0h+var_1130]
0x18000b627  mov     [rbp+10D0h+var_1128], rax
0x18000b62b  mov     rsi, [rbp+10D0h+lpMem]
0x18000b62f  mov     [rbp+10D0h+lpMem], r13
0x18000b633  test    rsi, rsi
0x18000b636  jz      short loc_18000B64C
0x18000b638  call    cs:__imp_GetProcessHeap
0x18000b63e  mov     rcx, rax; hHeap
0x18000b641  mov     r8, rsi; lpMem
0x18000b644  xor     edx, edx; dwFlags
0x18000b646  call    cs:__imp_HeapFree
0x18000b64c  test    dil, dil
0x18000b64f  jnz     short loc_18000B683
0x18000b651  cmp     r14, r12
0x18000b654  jnb     short loc_18000B683
0x18000b656  cmp     r15, 32h ; '2'
0x18000b65a  jb      loc_18000B326
0x18000b660  jmp     short loc_18000B683
0x18000b662  mov     rbx, [rbp+10D0h+lpMem]
0x18000b666  mov     [rbp+10D0h+lpMem], r13
0x18000b66a  test    rbx, rbx
0x18000b66d  jz      short loc_18000B683
0x18000b66f  call    cs:__imp_GetProcessHeap
0x18000b675  mov     rcx, rax; hHeap
0x18000b678  mov     r8, rbx; lpMem
0x18000b67b  xor     edx, edx; dwFlags
0x18000b67d  call    cs:__imp_HeapFree
0x18000b683  mov     rcx, [rbp+10D0h+var_40]
0x18000b68a  xor     rcx, rsp; StackCookie
0x18000b68d  call    __security_check_cookie
0x18000b692  mov     rbx, [rsp+11D0h+arg_8]
0x18000b69a  add     rsp, 11A0h
0x18000b6a1  pop     r15
0x18000b6a3  pop     r14
0x18000b6a5  pop     r13
0x18000b6a7  pop     r12
0x18000b6a9  pop     rdi
0x18000b6aa  pop     rsi
0x18000b6ab  pop     rbp
0x18000b6ac  retn
0x18000b6ad  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
