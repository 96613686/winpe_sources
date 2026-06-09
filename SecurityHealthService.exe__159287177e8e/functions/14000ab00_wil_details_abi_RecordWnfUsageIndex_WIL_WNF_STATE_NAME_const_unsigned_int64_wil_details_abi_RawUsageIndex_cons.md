# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x14000ab00`
- end: `0x14000aed8`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14000a228`

## callees

- `0x1400015d0`
- `0x140006e3c`
- `0x140009eb8`
- `0x14000a124`
- `0x14000ab00`
- `0x14000b4a4`
- `0x14000cb68`
- `0x140012180`
- `0x140013010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000abe0`
- `KERNEL32!GetModuleHandleW` at `0x14000abe0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ae6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000aea2`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000ae6c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000aea2`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ae5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ae94`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ae5e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000ae94`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000abf7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000abf7`

## string_xrefs

- `0x14000abd9`: `ntdll.dll`

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
0x14000ab00  mov     [rsp-8+arg_8], rbx
0x14000ab05  push    rbp
0x14000ab06  push    rsi
0x14000ab07  push    rdi
0x14000ab08  push    r12
0x14000ab0a  push    r13
0x14000ab0c  push    r14
0x14000ab0e  push    r15
0x14000ab10  lea     rbp, [rsp-10A0h]
0x14000ab18  mov     eax, 11A0h
0x14000ab1d  call    _alloca_probe
0x14000ab22  sub     rsp, rax
0x14000ab25  mov     rax, cs:__security_cookie
0x14000ab2c  xor     rax, rsp
0x14000ab2f  mov     [rbp+10D0h+var_40], rax
0x14000ab36  mov     rdi, r8
0x14000ab39  mov     r14, rcx
0x14000ab3c  lea     r13, [rcx+rdx*8]
0x14000ab40  xor     r15d, r15d
0x14000ab43  mov     r12d, r15d
0x14000ab46  mov     [rbp+10D0h+var_1128], r15
0x14000ab4a  mov     cl, [rdi+8]
0x14000ab4d  movzx   edx, word ptr [rdi+6]
0x14000ab51  movzx   eax, word ptr [rdi]
0x14000ab54  mov     [rsp+11D0h+var_1170], ax
0x14000ab59  movzx   eax, word ptr [rdi+2]
0x14000ab5d  mov     [rsp+11D0h+var_116E], ax
0x14000ab62  mov     al, [rdi+4]
0x14000ab65  mov     [rsp+11D0h+var_116C], al
0x14000ab69  mov     [rsp+11D0h+var_116A], dx
0x14000ab6e  mov     [rsp+11D0h+var_1168], cl
0x14000ab72  test    dx, dx
0x14000ab75  jz      short loc_14000AB94
0x14000ab77  mov     eax, edx
0x14000ab79  cmp     cl, 1
0x14000ab7c  jnz     short loc_14000AB84
0x14000ab7e  add     rax, 2
0x14000ab82  jmp     short loc_14000AB8D
0x14000ab84  cmp     cl, 2
0x14000ab87  jnz     short loc_14000AB8D
0x14000ab89  add     rax, 4
0x14000ab8d  mov     [rsp+11D0h+var_1160], rax
0x14000ab92  jmp     short loc_14000AB99
0x14000ab94  mov     [rsp+11D0h+var_1160], r15
0x14000ab99  mov     [rsp+11D0h+var_1158], r15
0x14000ab9e  xorps   xmm0, xmm0
0x14000aba1  movdqa  [rbp+10D0h+var_1150], xmm0
0x14000aba6  mov     [rbp+10D0h+lpMem], r15
0x14000abaa  mov     [rbp+10D0h+var_1138], 0
0x14000abb0  mov     [rbp+10D0h+var_1136], r15b
0x14000abb4  mov     [rsp+11D0h+var_1188], r15d
0x14000abb9  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14000abc1  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000abc8  test    rax, rax
0x14000abcb  jnz     short loc_14000AC10
0x14000abcd  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000abd4  test    rax, rax
0x14000abd7  jnz     short loc_14000ABED
0x14000abd9  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000abe0  call    cs:__imp_GetModuleHandleW
0x14000abe6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000abed  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000abf4  mov     rcx, rax; hModule
0x14000abf7  call    cs:__imp_GetProcAddress
0x14000abfd  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000ac04  test    rax, rax
0x14000ac07  jnz     short loc_14000AC10
0x14000ac09  mov     ebx, 0C0000139h
0x14000ac0e  jmp     short loc_14000AC3A
0x14000ac10  lea     rcx, [rsp+11D0h+var_1190]
0x14000ac15  mov     [rsp+11D0h+var_11A8], rcx
0x14000ac1a  lea     rcx, [rbp+10D0h+var_1040]
0x14000ac21  mov     [rsp+11D0h+var_11B0], rcx
0x14000ac26  lea     r9, [rsp+11D0h+var_1188]
0x14000ac2b  xor     r8d, r8d
0x14000ac2e  xor     edx, edx
0x14000ac30  mov     rcx, r14
0x14000ac33  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ac38  mov     ebx, eax
0x14000ac3a  mov     ecx, ebx; this
0x14000ac3c  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000ac41  test    ebx, ebx
0x14000ac43  jz      short loc_14000AC53
0x14000ac45  mov     eax, r15d
0x14000ac48  mov     dword ptr [rsp+11D0h+var_1190], eax
0x14000ac4c  mov     [rsp+11D0h+var_1188], r15d
0x14000ac51  jmp     short loc_14000AC57
0x14000ac53  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x14000ac57  mov     r8d, eax; unsigned __int64
0x14000ac5a  mov     r9d, 1000h; unsigned __int64
0x14000ac60  lea     rdx, [rbp+10D0h+var_1040]; void *
0x14000ac67  lea     rcx, [rsp+11D0h+var_1170]; this
0x14000ac6c  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x14000ac71  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x14000ac75  jnz     loc_14000AE87
0x14000ac7b  mov     [rbp+10D0h+var_1130], r15
0x14000ac7f  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x14000ac86  mov     [rbp+10D0h+var_10B0], rax
0x14000ac8a  lea     rax, [rbp+10D0h+var_1130]
0x14000ac8e  mov     [rbp+10D0h+var_10A8], rax
0x14000ac92  lea     rax, [rbp+10D0h+var_1128]
0x14000ac96  mov     [rbp+10D0h+var_10A0], rax
0x14000ac9a  lea     rax, [rsp+11D0h+var_1170]
0x14000ac9f  mov     [rbp+10D0h+var_1098], rax
0x14000aca3  lea     rax, [rbp+10D0h+var_10B0]
0x14000aca7  mov     [rbp+10D0h+var_1048], rax
0x14000acae  lea     rax, [rbp+10D0h+var_10B8]
0x14000acb2  mov     [rbp+10D0h+var_10C0], rax
0x14000acb6  mov     rax, [rdi+18h]
0x14000acba  add     rax, 0Ah
0x14000acbe  mov     [rsp+11D0h+var_1190], rax
0x14000acc3  movzx   eax, word ptr [rdi+2]
0x14000acc7  mov     [rbp+10D0h+var_1120], ax
0x14000accb  mov     al, [rdi+4]
0x14000acce  mov     [rbp+10D0h+var_111E], al
0x14000acd1  mov     [rbp+10D0h+var_111C], r15d
0x14000acd5  mov     [rbp+10D0h+var_1118], r15w
0x14000acda  xorps   xmm0, xmm0
0x14000acdd  movdqu  [rbp+10D0h+var_1110], xmm0
0x14000ace2  movzx   eax, word ptr [rdi+6]
0x14000ace6  mov     [rbp+10D0h+var_1100], ax
0x14000acea  mov     al, [rdi+8]
0x14000aced  mov     [rbp+10D0h+var_10FE], al
0x14000acf0  mov     [rbp+10D0h+var_10FC], r15d
0x14000acf4  mov     [rbp+10D0h+var_10F8], r15w
0x14000acf9  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14000acfe  jmp     loc_14000AD96
0x14000ad03  mov     ebx, r15d
0x14000ad06  mov     esi, [rbp+10D0h+var_111C]
0x14000ad09  test    esi, esi
0x14000ad0b  jz      loc_14000AD96
0x14000ad11  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x14000ad15  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000ad19  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000ad1e  lea     rcx, [rbp+10D0h+var_1100]; this
0x14000ad22  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000ad27  test    al, al
0x14000ad29  jz      short loc_14000AD93
0x14000ad2b  mov     eax, [rbp+10D0h+var_10FC]
0x14000ad2e  mov     [rsp+11D0h+var_1180], eax
0x14000ad32  movzx   eax, [rbp+10D0h+var_10F8]
0x14000ad36  mov     [rbp+10D0h+var_10E0], rax
0x14000ad3a  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000ad3e  mov     [rbp+10D0h+var_10D8], rax
0x14000ad42  movzx   eax, [rbp+10D0h+var_1118]
0x14000ad46  mov     [rbp+10D0h+var_10D0], rax
0x14000ad4a  mov     [rbp+10D0h+var_10C8], r15
0x14000ad4e  mov     rcx, [rbp+10D0h+var_1048]; this
0x14000ad55  test    rcx, rcx
0x14000ad58  jz      loc_14000AED2
0x14000ad5e  mov     rax, [rcx]
0x14000ad61  lea     rdx, [rsp+11D0h+var_1180]
0x14000ad66  mov     [rsp+11D0h+var_11A8], rdx
0x14000ad6b  lea     rdx, [rbp+10D0h+var_10E0]
0x14000ad6f  mov     [rsp+11D0h+var_11B0], rdx
0x14000ad74  lea     r9, [rbp+10D0h+var_10D8]
0x14000ad78  lea     r8, [rbp+10D0h+var_10D0]
0x14000ad7c  lea     rdx, [rbp+10D0h+var_10C8]
0x14000ad80  mov     rax, [rax+20h]
0x14000ad84  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ad89  test    al, al
0x14000ad8b  jz      short loc_14000AE03
0x14000ad8d  inc     ebx
0x14000ad8f  cmp     ebx, esi
0x14000ad91  jb      short loc_14000AD15
0x14000ad93  xor     r15d, r15d
0x14000ad96  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000ad9a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000ad9f  lea     rcx, [rbp+10D0h+var_1120]; this
0x14000ada3  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000ada8  test    al, al
0x14000adaa  jnz     loc_14000AD03
0x14000adb0  mov     rcx, [rbp+10D0h+var_1048]
0x14000adb7  test    rcx, rcx
0x14000adba  jz      short loc_14000ADC8
0x14000adbc  mov     rax, [rcx]
0x14000adbf  mov     rax, [rax+18h]
0x14000adc3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000adc8  mov     bl, 1
0x14000adca  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x14000adce  jz      short loc_14000AE45
0x14000add0  mov     eax, [rsp+11D0h+var_1188]
0x14000add4  mov     rdx, [rsp+11D0h+var_1158]
0x14000add9  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000addd  sub     r8d, edx
0x14000ade0  mov     [rsp+11D0h+var_11A0], 1
0x14000ade8  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14000adec  mov     rcx, r14
0x14000adef  call    wil_details_NtUpdateWnfStateData
0x14000adf4  cmp     eax, 0C0000001h
0x14000adf9  jnz     short loc_14000AE23
0x14000adfb  inc     r12
0x14000adfe  mov     bl, r15b
0x14000ae01  jmp     short loc_14000AE51
0x14000ae03  mov     rcx, [rbp+10D0h+var_1048]
0x14000ae0a  xor     r15d, r15d
0x14000ae0d  test    rcx, rcx
0x14000ae10  jz      short loc_14000AE1E
0x14000ae12  mov     rax, [rcx]
0x14000ae15  mov     rax, [rax+18h]
0x14000ae19  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ae1e  mov     bl, r15b
0x14000ae21  jmp     short loc_14000ADCA
0x14000ae23  test    eax, eax
0x14000ae25  jz      short loc_14000AE45
0x14000ae27  mov     rdx, [rsp+11D0h+var_1158]
0x14000ae2c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000ae30  sub     r8d, edx
0x14000ae33  mov     [rsp+11D0h+var_11A0], r15d
0x14000ae38  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x14000ae3d  mov     rcx, r14
0x14000ae40  call    wil_details_NtUpdateWnfStateData
0x14000ae45  add     r14, 8
0x14000ae49  mov     rax, [rbp+10D0h+var_1130]
0x14000ae4d  mov     [rbp+10D0h+var_1128], rax
0x14000ae51  mov     rsi, [rbp+10D0h+lpMem]
0x14000ae55  mov     [rbp+10D0h+lpMem], r15
0x14000ae59  test    rsi, rsi
0x14000ae5c  jz      short loc_14000AE72
0x14000ae5e  call    cs:__imp_GetProcessHeap
0x14000ae64  mov     rcx, rax; hHeap
0x14000ae67  mov     r8, rsi; lpMem
0x14000ae6a  xor     edx, edx; dwFlags
0x14000ae6c  call    cs:__imp_HeapFree
0x14000ae72  test    bl, bl
0x14000ae74  jnz     short loc_14000AEA8
0x14000ae76  cmp     r14, r13
0x14000ae79  jnb     short loc_14000AEA8
0x14000ae7b  cmp     r12, 32h ; '2'
0x14000ae7f  jb      loc_14000AB4A
0x14000ae85  jmp     short loc_14000AEA8
0x14000ae87  mov     rbx, [rbp+10D0h+lpMem]
0x14000ae8b  mov     [rbp+10D0h+lpMem], r15
0x14000ae8f  test    rbx, rbx
0x14000ae92  jz      short loc_14000AEA8
0x14000ae94  call    cs:__imp_GetProcessHeap
0x14000ae9a  mov     rcx, rax; hHeap
0x14000ae9d  mov     r8, rbx; lpMem
0x14000aea0  xor     edx, edx; dwFlags
0x14000aea2  call    cs:__imp_HeapFree
0x14000aea8  mov     rcx, [rbp+10D0h+var_40]
0x14000aeaf  xor     rcx, rsp; StackCookie
0x14000aeb2  call    __security_check_cookie
0x14000aeb7  mov     rbx, [rsp+11D0h+arg_8]
0x14000aebf  add     rsp, 11A0h
0x14000aec6  pop     r15
0x14000aec8  pop     r14
0x14000aeca  pop     r13
0x14000aecc  pop     r12
0x14000aece  pop     rdi
0x14000aecf  pop     rsi
0x14000aed0  pop     rbp
0x14000aed1  retn
0x14000aed2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
