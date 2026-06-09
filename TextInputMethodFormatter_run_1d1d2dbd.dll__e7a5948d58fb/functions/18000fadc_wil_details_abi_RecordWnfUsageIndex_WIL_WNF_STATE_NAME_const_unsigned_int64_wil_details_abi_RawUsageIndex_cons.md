# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000fadc`
- end: `0x18000feb4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000f028`

## callees

- `0x180002240`
- `0x180007a48`
- `0x18000dd24`
- `0x18000ef24`
- `0x18000fadc`
- `0x180010bd8`
- `0x1800131d0`
- `0x180056f80`
- `0x180058010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fbd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000fbd3`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fbbc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000fbbc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe7e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe48`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000fe7e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe70`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe3a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000fe70`

## string_xrefs

- `0x18000fbb5`: `ntdll.dll`

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
0x18000fadc  mov     [rsp-8+arg_8], rbx
0x18000fae1  push    rbp
0x18000fae2  push    rsi
0x18000fae3  push    rdi
0x18000fae4  push    r12
0x18000fae6  push    r13
0x18000fae8  push    r14
0x18000faea  push    r15
0x18000faec  lea     rbp, [rsp-10A0h]
0x18000faf4  mov     eax, 11A0h
0x18000faf9  call    _alloca_probe
0x18000fafe  sub     rsp, rax
0x18000fb01  mov     rax, cs:__security_cookie
0x18000fb08  xor     rax, rsp
0x18000fb0b  mov     [rbp+10D0h+var_40], rax
0x18000fb12  mov     rdi, r8
0x18000fb15  mov     r14, rcx
0x18000fb18  lea     r13, [rcx+rdx*8]
0x18000fb1c  xor     r15d, r15d
0x18000fb1f  mov     r12d, r15d
0x18000fb22  mov     [rbp+10D0h+var_1128], r15
0x18000fb26  mov     cl, [rdi+8]
0x18000fb29  movzx   edx, word ptr [rdi+6]
0x18000fb2d  movzx   eax, word ptr [rdi]
0x18000fb30  mov     [rsp+11D0h+var_1170], ax
0x18000fb35  movzx   eax, word ptr [rdi+2]
0x18000fb39  mov     [rsp+11D0h+var_116E], ax
0x18000fb3e  mov     al, [rdi+4]
0x18000fb41  mov     [rsp+11D0h+var_116C], al
0x18000fb45  mov     [rsp+11D0h+var_116A], dx
0x18000fb4a  mov     [rsp+11D0h+var_1168], cl
0x18000fb4e  test    dx, dx
0x18000fb51  jz      short loc_18000FB70
0x18000fb53  mov     eax, edx
0x18000fb55  cmp     cl, 1
0x18000fb58  jnz     short loc_18000FB60
0x18000fb5a  add     rax, 2
0x18000fb5e  jmp     short loc_18000FB69
0x18000fb60  cmp     cl, 2
0x18000fb63  jnz     short loc_18000FB69
0x18000fb65  add     rax, 4
0x18000fb69  mov     [rsp+11D0h+var_1160], rax
0x18000fb6e  jmp     short loc_18000FB75
0x18000fb70  mov     [rsp+11D0h+var_1160], r15
0x18000fb75  mov     [rsp+11D0h+var_1158], r15
0x18000fb7a  xorps   xmm0, xmm0
0x18000fb7d  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000fb82  mov     [rbp+10D0h+lpMem], r15
0x18000fb86  mov     [rbp+10D0h+var_1138], 0
0x18000fb8c  mov     [rbp+10D0h+var_1136], r15b
0x18000fb90  mov     [rsp+11D0h+var_1188], r15d
0x18000fb95  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000fb9d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000fba4  test    rax, rax
0x18000fba7  jnz     short loc_18000FBEC
0x18000fba9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fbb0  test    rax, rax
0x18000fbb3  jnz     short loc_18000FBC9
0x18000fbb5  lea     rcx, ModuleName; "ntdll.dll"
0x18000fbbc  call    cs:__imp_GetModuleHandleW
0x18000fbc2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000fbc9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000fbd0  mov     rcx, rax; hModule
0x18000fbd3  call    cs:__imp_GetProcAddress
0x18000fbd9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000fbe0  test    rax, rax
0x18000fbe3  jnz     short loc_18000FBEC
0x18000fbe5  mov     ebx, 0C0000139h
0x18000fbea  jmp     short loc_18000FC16
0x18000fbec  lea     rcx, [rsp+11D0h+var_1190]
0x18000fbf1  mov     [rsp+11D0h+var_11A8], rcx
0x18000fbf6  lea     rcx, [rbp+10D0h+var_1040]
0x18000fbfd  mov     [rsp+11D0h+var_11B0], rcx
0x18000fc02  lea     r9, [rsp+11D0h+var_1188]
0x18000fc07  xor     r8d, r8d
0x18000fc0a  xor     edx, edx
0x18000fc0c  mov     rcx, r14
0x18000fc0f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fc14  mov     ebx, eax
0x18000fc16  mov     ecx, ebx; this
0x18000fc18  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000fc1d  test    ebx, ebx
0x18000fc1f  jz      short loc_18000FC2F
0x18000fc21  mov     eax, r15d
0x18000fc24  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000fc28  mov     [rsp+11D0h+var_1188], r15d
0x18000fc2d  jmp     short loc_18000FC33
0x18000fc2f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000fc33  mov     r8d, eax; unsigned __int64
0x18000fc36  mov     r9d, 1000h; unsigned __int64
0x18000fc3c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000fc43  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000fc48  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000fc4d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000fc51  jnz     loc_18000FE63
0x18000fc57  mov     [rbp+10D0h+var_1130], r15
0x18000fc5b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000fc62  mov     [rbp+10D0h+var_10B0], rax
0x18000fc66  lea     rax, [rbp+10D0h+var_1130]
0x18000fc6a  mov     [rbp+10D0h+var_10A8], rax
0x18000fc6e  lea     rax, [rbp+10D0h+var_1128]
0x18000fc72  mov     [rbp+10D0h+var_10A0], rax
0x18000fc76  lea     rax, [rsp+11D0h+var_1170]
0x18000fc7b  mov     [rbp+10D0h+var_1098], rax
0x18000fc7f  lea     rax, [rbp+10D0h+var_10B0]
0x18000fc83  mov     [rbp+10D0h+var_1048], rax
0x18000fc8a  lea     rax, [rbp+10D0h+var_10B8]
0x18000fc8e  mov     [rbp+10D0h+var_10C0], rax
0x18000fc92  mov     rax, [rdi+18h]
0x18000fc96  add     rax, 0Ah
0x18000fc9a  mov     [rsp+11D0h+var_1190], rax
0x18000fc9f  movzx   eax, word ptr [rdi+2]
0x18000fca3  mov     [rbp+10D0h+var_1120], ax
0x18000fca7  mov     al, [rdi+4]
0x18000fcaa  mov     [rbp+10D0h+var_111E], al
0x18000fcad  mov     [rbp+10D0h+var_111C], r15d
0x18000fcb1  mov     [rbp+10D0h+var_1118], r15w
0x18000fcb6  xorps   xmm0, xmm0
0x18000fcb9  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000fcbe  movzx   eax, word ptr [rdi+6]
0x18000fcc2  mov     [rbp+10D0h+var_1100], ax
0x18000fcc6  mov     al, [rdi+8]
0x18000fcc9  mov     [rbp+10D0h+var_10FE], al
0x18000fccc  mov     [rbp+10D0h+var_10FC], r15d
0x18000fcd0  mov     [rbp+10D0h+var_10F8], r15w
0x18000fcd5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000fcda  jmp     loc_18000FD72
0x18000fcdf  mov     ebx, r15d
0x18000fce2  mov     esi, [rbp+10D0h+var_111C]
0x18000fce5  test    esi, esi
0x18000fce7  jz      loc_18000FD72
0x18000fced  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000fcf1  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000fcf5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000fcfa  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000fcfe  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000fd03  test    al, al
0x18000fd05  jz      short loc_18000FD6F
0x18000fd07  mov     eax, [rbp+10D0h+var_10FC]
0x18000fd0a  mov     [rsp+11D0h+var_1180], eax
0x18000fd0e  movzx   eax, [rbp+10D0h+var_10F8]
0x18000fd12  mov     [rbp+10D0h+var_10E0], rax
0x18000fd16  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000fd1a  mov     [rbp+10D0h+var_10D8], rax
0x18000fd1e  movzx   eax, [rbp+10D0h+var_1118]
0x18000fd22  mov     [rbp+10D0h+var_10D0], rax
0x18000fd26  mov     [rbp+10D0h+var_10C8], r15
0x18000fd2a  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000fd31  test    rcx, rcx
0x18000fd34  jz      loc_18000FEAE
0x18000fd3a  mov     rax, [rcx]
0x18000fd3d  lea     rdx, [rsp+11D0h+var_1180]
0x18000fd42  mov     [rsp+11D0h+var_11A8], rdx
0x18000fd47  lea     rdx, [rbp+10D0h+var_10E0]
0x18000fd4b  mov     [rsp+11D0h+var_11B0], rdx
0x18000fd50  lea     r9, [rbp+10D0h+var_10D8]
0x18000fd54  lea     r8, [rbp+10D0h+var_10D0]
0x18000fd58  lea     rdx, [rbp+10D0h+var_10C8]
0x18000fd5c  mov     rax, [rax+20h]
0x18000fd60  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fd65  test    al, al
0x18000fd67  jz      short loc_18000FDDF
0x18000fd69  inc     ebx
0x18000fd6b  cmp     ebx, esi
0x18000fd6d  jb      short loc_18000FCF1
0x18000fd6f  xor     r15d, r15d
0x18000fd72  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000fd76  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000fd7b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000fd7f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000fd84  test    al, al
0x18000fd86  jnz     loc_18000FCDF
0x18000fd8c  mov     rcx, [rbp+10D0h+var_1048]
0x18000fd93  test    rcx, rcx
0x18000fd96  jz      short loc_18000FDA4
0x18000fd98  mov     rax, [rcx]
0x18000fd9b  mov     rax, [rax+18h]
0x18000fd9f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fda4  mov     bl, 1
0x18000fda6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000fdaa  jz      short loc_18000FE21
0x18000fdac  mov     eax, [rsp+11D0h+var_1188]
0x18000fdb0  mov     rdx, [rsp+11D0h+var_1158]
0x18000fdb5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000fdb9  sub     r8d, edx
0x18000fdbc  mov     [rsp+11D0h+var_11A0], 1
0x18000fdc4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000fdc8  mov     rcx, r14
0x18000fdcb  call    wil_details_NtUpdateWnfStateData
0x18000fdd0  cmp     eax, 0C0000001h
0x18000fdd5  jnz     short loc_18000FDFF
0x18000fdd7  inc     r12
0x18000fdda  mov     bl, r15b
0x18000fddd  jmp     short loc_18000FE2D
0x18000fddf  mov     rcx, [rbp+10D0h+var_1048]
0x18000fde6  xor     r15d, r15d
0x18000fde9  test    rcx, rcx
0x18000fdec  jz      short loc_18000FDFA
0x18000fdee  mov     rax, [rcx]
0x18000fdf1  mov     rax, [rax+18h]
0x18000fdf5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000fdfa  mov     bl, r15b
0x18000fdfd  jmp     short loc_18000FDA6
0x18000fdff  test    eax, eax
0x18000fe01  jz      short loc_18000FE21
0x18000fe03  mov     rdx, [rsp+11D0h+var_1158]
0x18000fe08  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000fe0c  sub     r8d, edx
0x18000fe0f  mov     [rsp+11D0h+var_11A0], r15d
0x18000fe14  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000fe19  mov     rcx, r14
0x18000fe1c  call    wil_details_NtUpdateWnfStateData
0x18000fe21  add     r14, 8
0x18000fe25  mov     rax, [rbp+10D0h+var_1130]
0x18000fe29  mov     [rbp+10D0h+var_1128], rax
0x18000fe2d  mov     rsi, [rbp+10D0h+lpMem]
0x18000fe31  mov     [rbp+10D0h+lpMem], r15
0x18000fe35  test    rsi, rsi
0x18000fe38  jz      short loc_18000FE4E
0x18000fe3a  call    cs:__imp_GetProcessHeap
0x18000fe40  mov     rcx, rax; hHeap
0x18000fe43  mov     r8, rsi; lpMem
0x18000fe46  xor     edx, edx; dwFlags
0x18000fe48  call    cs:__imp_HeapFree
0x18000fe4e  test    bl, bl
0x18000fe50  jnz     short loc_18000FE84
0x18000fe52  cmp     r14, r13
0x18000fe55  jnb     short loc_18000FE84
0x18000fe57  cmp     r12, 32h ; '2'
0x18000fe5b  jb      loc_18000FB26
0x18000fe61  jmp     short loc_18000FE84
0x18000fe63  mov     rbx, [rbp+10D0h+lpMem]
0x18000fe67  mov     [rbp+10D0h+lpMem], r15
0x18000fe6b  test    rbx, rbx
0x18000fe6e  jz      short loc_18000FE84
0x18000fe70  call    cs:__imp_GetProcessHeap
0x18000fe76  mov     rcx, rax; hHeap
0x18000fe79  mov     r8, rbx; lpMem
0x18000fe7c  xor     edx, edx; dwFlags
0x18000fe7e  call    cs:__imp_HeapFree
0x18000fe84  mov     rcx, [rbp+10D0h+var_40]
0x18000fe8b  xor     rcx, rsp; StackCookie
0x18000fe8e  call    __security_check_cookie
0x18000fe93  mov     rbx, [rsp+11D0h+arg_8]
0x18000fe9b  add     rsp, 11A0h
0x18000fea2  pop     r15
0x18000fea4  pop     r14
0x18000fea6  pop     r13
0x18000fea8  pop     r12
0x18000feaa  pop     rdi
0x18000feab  pop     rsi
0x18000feac  pop     rbp
0x18000fead  retn
0x18000feae  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
