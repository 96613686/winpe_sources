# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000afdc`
- end: `0x18000b3b4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000a4c4`

## callees

- `0x180002300`
- `0x180009b64`
- `0x18000a37c`
- `0x18000afdc`
- `0x18000c2c4`
- `0x18000e804`
- `0x180010160`
- `0x180010290`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b0d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000b0d3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b0bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000b0bc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b348`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b37e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b348`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000b37e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b33a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b370`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b33a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000b370`

## string_xrefs

- `0x18000b0b5`: `ntdll.dll`

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
0x18000afdc  mov     [rsp-8+arg_8], rbx
0x18000afe1  push    rbp
0x18000afe2  push    rsi
0x18000afe3  push    rdi
0x18000afe4  push    r12
0x18000afe6  push    r13
0x18000afe8  push    r14
0x18000afea  push    r15
0x18000afec  lea     rbp, [rsp-10A0h]
0x18000aff4  mov     eax, 11A0h
0x18000aff9  call    _alloca_probe
0x18000affe  sub     rsp, rax
0x18000b001  mov     rax, cs:__security_cookie
0x18000b008  xor     rax, rsp
0x18000b00b  mov     [rbp+10D0h+var_40], rax
0x18000b012  mov     rdi, r8
0x18000b015  mov     r14, rcx
0x18000b018  lea     r13, [rcx+rdx*8]
0x18000b01c  xor     r15d, r15d
0x18000b01f  mov     r12d, r15d
0x18000b022  mov     [rbp+10D0h+var_1128], r15
0x18000b026  mov     cl, [rdi+8]
0x18000b029  movzx   edx, word ptr [rdi+6]
0x18000b02d  movzx   eax, word ptr [rdi]
0x18000b030  mov     [rsp+11D0h+var_1170], ax
0x18000b035  movzx   eax, word ptr [rdi+2]
0x18000b039  mov     [rsp+11D0h+var_116E], ax
0x18000b03e  mov     al, [rdi+4]
0x18000b041  mov     [rsp+11D0h+var_116C], al
0x18000b045  mov     [rsp+11D0h+var_116A], dx
0x18000b04a  mov     [rsp+11D0h+var_1168], cl
0x18000b04e  test    dx, dx
0x18000b051  jz      short loc_18000B070
0x18000b053  mov     eax, edx
0x18000b055  cmp     cl, 1
0x18000b058  jnz     short loc_18000B060
0x18000b05a  add     rax, 2
0x18000b05e  jmp     short loc_18000B069
0x18000b060  cmp     cl, 2
0x18000b063  jnz     short loc_18000B069
0x18000b065  add     rax, 4
0x18000b069  mov     [rsp+11D0h+var_1160], rax
0x18000b06e  jmp     short loc_18000B075
0x18000b070  mov     [rsp+11D0h+var_1160], r15
0x18000b075  mov     [rsp+11D0h+var_1158], r15
0x18000b07a  xorps   xmm0, xmm0
0x18000b07d  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000b082  mov     [rbp+10D0h+lpMem], r15
0x18000b086  mov     [rbp+10D0h+var_1138], 0
0x18000b08c  mov     [rbp+10D0h+var_1136], r15b
0x18000b090  mov     [rsp+11D0h+var_1188], r15d
0x18000b095  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000b09d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000b0a4  test    rax, rax
0x18000b0a7  jnz     short loc_18000B0EC
0x18000b0a9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b0b0  test    rax, rax
0x18000b0b3  jnz     short loc_18000B0C9
0x18000b0b5  lea     rcx, ModuleName; "ntdll.dll"
0x18000b0bc  call    cs:__imp_GetModuleHandleW
0x18000b0c2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000b0c9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000b0d0  mov     rcx, rax; hModule
0x18000b0d3  call    cs:__imp_GetProcAddress
0x18000b0d9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000b0e0  test    rax, rax
0x18000b0e3  jnz     short loc_18000B0EC
0x18000b0e5  mov     ebx, 0C0000139h
0x18000b0ea  jmp     short loc_18000B116
0x18000b0ec  lea     rcx, [rsp+11D0h+var_1190]
0x18000b0f1  mov     [rsp+11D0h+var_11A8], rcx
0x18000b0f6  lea     rcx, [rbp+10D0h+var_1040]
0x18000b0fd  mov     [rsp+11D0h+var_11B0], rcx
0x18000b102  lea     r9, [rsp+11D0h+var_1188]
0x18000b107  xor     r8d, r8d
0x18000b10a  xor     edx, edx
0x18000b10c  mov     rcx, r14
0x18000b10f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b114  mov     ebx, eax
0x18000b116  mov     ecx, ebx; this
0x18000b118  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000b11d  test    ebx, ebx
0x18000b11f  jz      short loc_18000B12F
0x18000b121  mov     eax, r15d
0x18000b124  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000b128  mov     [rsp+11D0h+var_1188], r15d
0x18000b12d  jmp     short loc_18000B133
0x18000b12f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000b133  mov     r8d, eax; unsigned __int64
0x18000b136  mov     r9d, 1000h; unsigned __int64
0x18000b13c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000b143  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000b148  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000b14d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000b151  jnz     loc_18000B363
0x18000b157  mov     [rbp+10D0h+var_1130], r15
0x18000b15b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000b162  mov     [rbp+10D0h+var_10B0], rax
0x18000b166  lea     rax, [rbp+10D0h+var_1130]
0x18000b16a  mov     [rbp+10D0h+var_10A8], rax
0x18000b16e  lea     rax, [rbp+10D0h+var_1128]
0x18000b172  mov     [rbp+10D0h+var_10A0], rax
0x18000b176  lea     rax, [rsp+11D0h+var_1170]
0x18000b17b  mov     [rbp+10D0h+var_1098], rax
0x18000b17f  lea     rax, [rbp+10D0h+var_10B0]
0x18000b183  mov     [rbp+10D0h+var_1048], rax
0x18000b18a  lea     rax, [rbp+10D0h+var_10B8]
0x18000b18e  mov     [rbp+10D0h+var_10C0], rax
0x18000b192  mov     rax, [rdi+18h]
0x18000b196  add     rax, 0Ah
0x18000b19a  mov     [rsp+11D0h+var_1190], rax
0x18000b19f  movzx   eax, word ptr [rdi+2]
0x18000b1a3  mov     [rbp+10D0h+var_1120], ax
0x18000b1a7  mov     al, [rdi+4]
0x18000b1aa  mov     [rbp+10D0h+var_111E], al
0x18000b1ad  mov     [rbp+10D0h+var_111C], r15d
0x18000b1b1  mov     [rbp+10D0h+var_1118], r15w
0x18000b1b6  xorps   xmm0, xmm0
0x18000b1b9  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000b1be  movzx   eax, word ptr [rdi+6]
0x18000b1c2  mov     [rbp+10D0h+var_1100], ax
0x18000b1c6  mov     al, [rdi+8]
0x18000b1c9  mov     [rbp+10D0h+var_10FE], al
0x18000b1cc  mov     [rbp+10D0h+var_10FC], r15d
0x18000b1d0  mov     [rbp+10D0h+var_10F8], r15w
0x18000b1d5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000b1da  jmp     loc_18000B272
0x18000b1df  mov     ebx, r15d
0x18000b1e2  mov     esi, [rbp+10D0h+var_111C]
0x18000b1e5  test    esi, esi
0x18000b1e7  jz      loc_18000B272
0x18000b1ed  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000b1f1  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b1f5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b1fa  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000b1fe  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b203  test    al, al
0x18000b205  jz      short loc_18000B26F
0x18000b207  mov     eax, [rbp+10D0h+var_10FC]
0x18000b20a  mov     [rsp+11D0h+var_1180], eax
0x18000b20e  movzx   eax, [rbp+10D0h+var_10F8]
0x18000b212  mov     [rbp+10D0h+var_10E0], rax
0x18000b216  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000b21a  mov     [rbp+10D0h+var_10D8], rax
0x18000b21e  movzx   eax, [rbp+10D0h+var_1118]
0x18000b222  mov     [rbp+10D0h+var_10D0], rax
0x18000b226  mov     [rbp+10D0h+var_10C8], r15
0x18000b22a  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000b231  test    rcx, rcx
0x18000b234  jz      loc_18000B3AE
0x18000b23a  mov     rax, [rcx]
0x18000b23d  lea     rdx, [rsp+11D0h+var_1180]
0x18000b242  mov     [rsp+11D0h+var_11A8], rdx
0x18000b247  lea     rdx, [rbp+10D0h+var_10E0]
0x18000b24b  mov     [rsp+11D0h+var_11B0], rdx
0x18000b250  lea     r9, [rbp+10D0h+var_10D8]
0x18000b254  lea     r8, [rbp+10D0h+var_10D0]
0x18000b258  lea     rdx, [rbp+10D0h+var_10C8]
0x18000b25c  mov     rax, [rax+20h]
0x18000b260  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b265  test    al, al
0x18000b267  jz      short loc_18000B2DF
0x18000b269  inc     ebx
0x18000b26b  cmp     ebx, esi
0x18000b26d  jb      short loc_18000B1F1
0x18000b26f  xor     r15d, r15d
0x18000b272  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000b276  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000b27b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000b27f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000b284  test    al, al
0x18000b286  jnz     loc_18000B1DF
0x18000b28c  mov     rcx, [rbp+10D0h+var_1048]
0x18000b293  test    rcx, rcx
0x18000b296  jz      short loc_18000B2A4
0x18000b298  mov     rax, [rcx]
0x18000b29b  mov     rax, [rax+18h]
0x18000b29f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2a4  mov     bl, 1
0x18000b2a6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000b2aa  jz      short loc_18000B321
0x18000b2ac  mov     eax, [rsp+11D0h+var_1188]
0x18000b2b0  mov     rdx, [rsp+11D0h+var_1158]
0x18000b2b5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b2b9  sub     r8d, edx
0x18000b2bc  mov     [rsp+11D0h+var_11A0], 1
0x18000b2c4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000b2c8  mov     rcx, r14
0x18000b2cb  call    wil_details_NtUpdateWnfStateData
0x18000b2d0  cmp     eax, 0C0000001h
0x18000b2d5  jnz     short loc_18000B2FF
0x18000b2d7  inc     r12
0x18000b2da  mov     bl, r15b
0x18000b2dd  jmp     short loc_18000B32D
0x18000b2df  mov     rcx, [rbp+10D0h+var_1048]
0x18000b2e6  xor     r15d, r15d
0x18000b2e9  test    rcx, rcx
0x18000b2ec  jz      short loc_18000B2FA
0x18000b2ee  mov     rax, [rcx]
0x18000b2f1  mov     rax, [rax+18h]
0x18000b2f5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000b2fa  mov     bl, r15b
0x18000b2fd  jmp     short loc_18000B2A6
0x18000b2ff  test    eax, eax
0x18000b301  jz      short loc_18000B321
0x18000b303  mov     rdx, [rsp+11D0h+var_1158]
0x18000b308  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000b30c  sub     r8d, edx
0x18000b30f  mov     [rsp+11D0h+var_11A0], r15d
0x18000b314  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000b319  mov     rcx, r14
0x18000b31c  call    wil_details_NtUpdateWnfStateData
0x18000b321  add     r14, 8
0x18000b325  mov     rax, [rbp+10D0h+var_1130]
0x18000b329  mov     [rbp+10D0h+var_1128], rax
0x18000b32d  mov     rsi, [rbp+10D0h+lpMem]
0x18000b331  mov     [rbp+10D0h+lpMem], r15
0x18000b335  test    rsi, rsi
0x18000b338  jz      short loc_18000B34E
0x18000b33a  call    cs:__imp_GetProcessHeap
0x18000b340  mov     rcx, rax; hHeap
0x18000b343  mov     r8, rsi; lpMem
0x18000b346  xor     edx, edx; dwFlags
0x18000b348  call    cs:__imp_HeapFree
0x18000b34e  test    bl, bl
0x18000b350  jnz     short loc_18000B384
0x18000b352  cmp     r14, r13
0x18000b355  jnb     short loc_18000B384
0x18000b357  cmp     r12, 32h ; '2'
0x18000b35b  jb      loc_18000B026
0x18000b361  jmp     short loc_18000B384
0x18000b363  mov     rbx, [rbp+10D0h+lpMem]
0x18000b367  mov     [rbp+10D0h+lpMem], r15
0x18000b36b  test    rbx, rbx
0x18000b36e  jz      short loc_18000B384
0x18000b370  call    cs:__imp_GetProcessHeap
0x18000b376  mov     rcx, rax; hHeap
0x18000b379  mov     r8, rbx; lpMem
0x18000b37c  xor     edx, edx; dwFlags
0x18000b37e  call    cs:__imp_HeapFree
0x18000b384  mov     rcx, [rbp+10D0h+var_40]
0x18000b38b  xor     rcx, rsp; StackCookie
0x18000b38e  call    __security_check_cookie
0x18000b393  mov     rbx, [rsp+11D0h+arg_8]
0x18000b39b  add     rsp, 11A0h
0x18000b3a2  pop     r15
0x18000b3a4  pop     r14
0x18000b3a6  pop     r13
0x18000b3a8  pop     r12
0x18000b3aa  pop     rdi
0x18000b3ab  pop     rsi
0x18000b3ac  pop     rbp
0x18000b3ad  retn
0x18000b3ae  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
