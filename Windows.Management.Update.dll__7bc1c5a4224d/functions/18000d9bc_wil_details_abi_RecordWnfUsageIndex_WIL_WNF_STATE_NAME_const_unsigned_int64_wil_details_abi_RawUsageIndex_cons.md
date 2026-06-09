# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000d9bc`
- end: `0x18000dd94`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000cea4`

## callees

- `0x1800028f0`
- `0x18000c964`
- `0x18000cda4`
- `0x18000d9bc`
- `0x18000e664`
- `0x18000fb7c`
- `0x180010390`
- `0x180027600`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000da9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000da9c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dab3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000dab3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd50`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd1a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000dd50`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd5e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd28`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000dd5e`

## string_xrefs

- `0x18000da95`: `ntdll.dll`

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
0x18000d9bc  mov     [rsp-8+arg_8], rbx
0x18000d9c1  push    rbp
0x18000d9c2  push    rsi
0x18000d9c3  push    rdi
0x18000d9c4  push    r12
0x18000d9c6  push    r13
0x18000d9c8  push    r14
0x18000d9ca  push    r15
0x18000d9cc  lea     rbp, [rsp-10A0h]
0x18000d9d4  mov     eax, 11A0h
0x18000d9d9  call    _alloca_probe
0x18000d9de  sub     rsp, rax
0x18000d9e1  mov     rax, cs:__security_cookie
0x18000d9e8  xor     rax, rsp
0x18000d9eb  mov     [rbp+10D0h+var_40], rax
0x18000d9f2  mov     rdi, r8
0x18000d9f5  mov     r14, rcx
0x18000d9f8  lea     r13, [rcx+rdx*8]
0x18000d9fc  xor     r15d, r15d
0x18000d9ff  mov     r12d, r15d
0x18000da02  mov     [rbp+10D0h+var_1128], r15
0x18000da06  mov     cl, [rdi+8]
0x18000da09  movzx   edx, word ptr [rdi+6]
0x18000da0d  movzx   eax, word ptr [rdi]
0x18000da10  mov     [rsp+11D0h+var_1170], ax
0x18000da15  movzx   eax, word ptr [rdi+2]
0x18000da19  mov     [rsp+11D0h+var_116E], ax
0x18000da1e  mov     al, [rdi+4]
0x18000da21  mov     [rsp+11D0h+var_116C], al
0x18000da25  mov     [rsp+11D0h+var_116A], dx
0x18000da2a  mov     [rsp+11D0h+var_1168], cl
0x18000da2e  test    dx, dx
0x18000da31  jz      short loc_18000DA50
0x18000da33  mov     eax, edx
0x18000da35  cmp     cl, 1
0x18000da38  jnz     short loc_18000DA40
0x18000da3a  add     rax, 2
0x18000da3e  jmp     short loc_18000DA49
0x18000da40  cmp     cl, 2
0x18000da43  jnz     short loc_18000DA49
0x18000da45  add     rax, 4
0x18000da49  mov     [rsp+11D0h+var_1160], rax
0x18000da4e  jmp     short loc_18000DA55
0x18000da50  mov     [rsp+11D0h+var_1160], r15
0x18000da55  mov     [rsp+11D0h+var_1158], r15
0x18000da5a  xorps   xmm0, xmm0
0x18000da5d  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000da62  mov     [rbp+10D0h+lpMem], r15
0x18000da66  mov     [rbp+10D0h+var_1138], 0
0x18000da6c  mov     [rbp+10D0h+var_1136], r15b
0x18000da70  mov     [rsp+11D0h+var_1188], r15d
0x18000da75  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000da7d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000da84  test    rax, rax
0x18000da87  jnz     short loc_18000DACC
0x18000da89  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000da90  test    rax, rax
0x18000da93  jnz     short loc_18000DAA9
0x18000da95  lea     rcx, aNtdllDll; "ntdll.dll"
0x18000da9c  call    cs:__imp_GetModuleHandleW
0x18000daa2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000daa9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000dab0  mov     rcx, rax; hModule
0x18000dab3  call    cs:__imp_GetProcAddress
0x18000dab9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000dac0  test    rax, rax
0x18000dac3  jnz     short loc_18000DACC
0x18000dac5  mov     ebx, 0C0000139h
0x18000daca  jmp     short loc_18000DAF6
0x18000dacc  lea     rcx, [rsp+11D0h+var_1190]
0x18000dad1  mov     [rsp+11D0h+var_11A8], rcx
0x18000dad6  lea     rcx, [rbp+10D0h+var_1040]
0x18000dadd  mov     [rsp+11D0h+var_11B0], rcx
0x18000dae2  lea     r9, [rsp+11D0h+var_1188]
0x18000dae7  xor     r8d, r8d
0x18000daea  xor     edx, edx
0x18000daec  mov     rcx, r14
0x18000daef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000daf4  mov     ebx, eax
0x18000daf6  mov     ecx, ebx; this
0x18000daf8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000dafd  test    ebx, ebx
0x18000daff  jz      short loc_18000DB0F
0x18000db01  mov     eax, r15d
0x18000db04  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000db08  mov     [rsp+11D0h+var_1188], r15d
0x18000db0d  jmp     short loc_18000DB13
0x18000db0f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000db13  mov     r8d, eax; unsigned __int64
0x18000db16  mov     r9d, 1000h; unsigned __int64
0x18000db1c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000db23  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000db28  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000db2d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000db31  jnz     loc_18000DD43
0x18000db37  mov     [rbp+10D0h+var_1130], r15
0x18000db3b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000db42  mov     [rbp+10D0h+var_10B0], rax
0x18000db46  lea     rax, [rbp+10D0h+var_1130]
0x18000db4a  mov     [rbp+10D0h+var_10A8], rax
0x18000db4e  lea     rax, [rbp+10D0h+var_1128]
0x18000db52  mov     [rbp+10D0h+var_10A0], rax
0x18000db56  lea     rax, [rsp+11D0h+var_1170]
0x18000db5b  mov     [rbp+10D0h+var_1098], rax
0x18000db5f  lea     rax, [rbp+10D0h+var_10B0]
0x18000db63  mov     [rbp+10D0h+var_1048], rax
0x18000db6a  lea     rax, [rbp+10D0h+var_10B8]
0x18000db6e  mov     [rbp+10D0h+var_10C0], rax
0x18000db72  mov     rax, [rdi+18h]
0x18000db76  add     rax, 0Ah
0x18000db7a  mov     [rsp+11D0h+var_1190], rax
0x18000db7f  movzx   eax, word ptr [rdi+2]
0x18000db83  mov     [rbp+10D0h+var_1120], ax
0x18000db87  mov     al, [rdi+4]
0x18000db8a  mov     [rbp+10D0h+var_111E], al
0x18000db8d  mov     [rbp+10D0h+var_111C], r15d
0x18000db91  mov     [rbp+10D0h+var_1118], r15w
0x18000db96  xorps   xmm0, xmm0
0x18000db99  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000db9e  movzx   eax, word ptr [rdi+6]
0x18000dba2  mov     [rbp+10D0h+var_1100], ax
0x18000dba6  mov     al, [rdi+8]
0x18000dba9  mov     [rbp+10D0h+var_10FE], al
0x18000dbac  mov     [rbp+10D0h+var_10FC], r15d
0x18000dbb0  mov     [rbp+10D0h+var_10F8], r15w
0x18000dbb5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000dbba  jmp     loc_18000DC52
0x18000dbbf  mov     ebx, r15d
0x18000dbc2  mov     esi, [rbp+10D0h+var_111C]
0x18000dbc5  test    esi, esi
0x18000dbc7  jz      loc_18000DC52
0x18000dbcd  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000dbd1  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000dbd5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000dbda  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000dbde  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000dbe3  test    al, al
0x18000dbe5  jz      short loc_18000DC4F
0x18000dbe7  mov     eax, [rbp+10D0h+var_10FC]
0x18000dbea  mov     [rsp+11D0h+var_1180], eax
0x18000dbee  movzx   eax, [rbp+10D0h+var_10F8]
0x18000dbf2  mov     [rbp+10D0h+var_10E0], rax
0x18000dbf6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000dbfa  mov     [rbp+10D0h+var_10D8], rax
0x18000dbfe  movzx   eax, [rbp+10D0h+var_1118]
0x18000dc02  mov     [rbp+10D0h+var_10D0], rax
0x18000dc06  mov     [rbp+10D0h+var_10C8], r15
0x18000dc0a  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000dc11  test    rcx, rcx
0x18000dc14  jz      loc_18000DD8E
0x18000dc1a  mov     rax, [rcx]
0x18000dc1d  lea     rdx, [rsp+11D0h+var_1180]
0x18000dc22  mov     [rsp+11D0h+var_11A8], rdx
0x18000dc27  lea     rdx, [rbp+10D0h+var_10E0]
0x18000dc2b  mov     [rsp+11D0h+var_11B0], rdx
0x18000dc30  lea     r9, [rbp+10D0h+var_10D8]
0x18000dc34  lea     r8, [rbp+10D0h+var_10D0]
0x18000dc38  lea     rdx, [rbp+10D0h+var_10C8]
0x18000dc3c  mov     rax, [rax+20h]
0x18000dc40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc45  test    al, al
0x18000dc47  jz      short loc_18000DCBF
0x18000dc49  inc     ebx
0x18000dc4b  cmp     ebx, esi
0x18000dc4d  jb      short loc_18000DBD1
0x18000dc4f  xor     r15d, r15d
0x18000dc52  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000dc56  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000dc5b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000dc5f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000dc64  test    al, al
0x18000dc66  jnz     loc_18000DBBF
0x18000dc6c  mov     rcx, [rbp+10D0h+var_1048]
0x18000dc73  test    rcx, rcx
0x18000dc76  jz      short loc_18000DC84
0x18000dc78  mov     rax, [rcx]
0x18000dc7b  mov     rax, [rax+18h]
0x18000dc7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dc84  mov     bl, 1
0x18000dc86  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000dc8a  jz      short loc_18000DD01
0x18000dc8c  mov     eax, [rsp+11D0h+var_1188]
0x18000dc90  mov     rdx, [rsp+11D0h+var_1158]
0x18000dc95  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000dc99  sub     r8d, edx
0x18000dc9c  mov     [rsp+11D0h+var_11A0], 1
0x18000dca4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000dca8  mov     rcx, r14
0x18000dcab  call    wil_details_NtUpdateWnfStateData
0x18000dcb0  cmp     eax, 0C0000001h
0x18000dcb5  jnz     short loc_18000DCDF
0x18000dcb7  inc     r12
0x18000dcba  mov     bl, r15b
0x18000dcbd  jmp     short loc_18000DD0D
0x18000dcbf  mov     rcx, [rbp+10D0h+var_1048]
0x18000dcc6  xor     r15d, r15d
0x18000dcc9  test    rcx, rcx
0x18000dccc  jz      short loc_18000DCDA
0x18000dcce  mov     rax, [rcx]
0x18000dcd1  mov     rax, [rax+18h]
0x18000dcd5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000dcda  mov     bl, r15b
0x18000dcdd  jmp     short loc_18000DC86
0x18000dcdf  test    eax, eax
0x18000dce1  jz      short loc_18000DD01
0x18000dce3  mov     rdx, [rsp+11D0h+var_1158]
0x18000dce8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000dcec  sub     r8d, edx
0x18000dcef  mov     [rsp+11D0h+var_11A0], r15d
0x18000dcf4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000dcf9  mov     rcx, r14
0x18000dcfc  call    wil_details_NtUpdateWnfStateData
0x18000dd01  add     r14, 8
0x18000dd05  mov     rax, [rbp+10D0h+var_1130]
0x18000dd09  mov     [rbp+10D0h+var_1128], rax
0x18000dd0d  mov     rsi, [rbp+10D0h+lpMem]
0x18000dd11  mov     [rbp+10D0h+lpMem], r15
0x18000dd15  test    rsi, rsi
0x18000dd18  jz      short loc_18000DD2E
0x18000dd1a  call    cs:__imp_GetProcessHeap
0x18000dd20  mov     rcx, rax; hHeap
0x18000dd23  mov     r8, rsi; lpMem
0x18000dd26  xor     edx, edx; dwFlags
0x18000dd28  call    cs:__imp_HeapFree
0x18000dd2e  test    bl, bl
0x18000dd30  jnz     short loc_18000DD64
0x18000dd32  cmp     r14, r13
0x18000dd35  jnb     short loc_18000DD64
0x18000dd37  cmp     r12, 32h ; '2'
0x18000dd3b  jb      loc_18000DA06
0x18000dd41  jmp     short loc_18000DD64
0x18000dd43  mov     rbx, [rbp+10D0h+lpMem]
0x18000dd47  mov     [rbp+10D0h+lpMem], r15
0x18000dd4b  test    rbx, rbx
0x18000dd4e  jz      short loc_18000DD64
0x18000dd50  call    cs:__imp_GetProcessHeap
0x18000dd56  mov     rcx, rax; hHeap
0x18000dd59  mov     r8, rbx; lpMem
0x18000dd5c  xor     edx, edx; dwFlags
0x18000dd5e  call    cs:__imp_HeapFree
0x18000dd64  mov     rcx, [rbp+10D0h+var_40]
0x18000dd6b  xor     rcx, rsp; StackCookie
0x18000dd6e  call    __security_check_cookie
0x18000dd73  mov     rbx, [rsp+11D0h+arg_8]
0x18000dd7b  add     rsp, 11A0h
0x18000dd82  pop     r15
0x18000dd84  pop     r14
0x18000dd86  pop     r13
0x18000dd88  pop     r12
0x18000dd8a  pop     rdi
0x18000dd8b  pop     rsi
0x18000dd8c  pop     rbp
0x18000dd8d  retn
0x18000dd8e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
