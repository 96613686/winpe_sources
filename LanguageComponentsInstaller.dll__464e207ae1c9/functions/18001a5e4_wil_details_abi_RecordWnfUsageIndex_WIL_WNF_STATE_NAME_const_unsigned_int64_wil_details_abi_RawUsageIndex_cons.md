# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18001a5e4`
- end: `0x18001a9b9`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `981`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180019a9c`

## callees

- `0x180003520`
- `0x18000a364`
- `0x180019004`
- `0x180019994`
- `0x18001a5e4`
- `0x18001b4a4`
- `0x180023c18`
- `0x180027cb0`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a6d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001a6d1`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a6ba`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18001a6ba`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a94d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a983`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a94d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001a983`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a93f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a975`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a93f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001a975`

## string_xrefs

- `0x18001a6b3`: `ntdll.dll`

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
  __int16 v28; // [rsp+40h] [rbp-C0h] BYREF
  char v29; // [rsp+42h] [rbp-BEh]
  unsigned int v30; // [rsp+44h] [rbp-BCh]
  unsigned __int16 v31; // [rsp+48h] [rbp-B8h]
  __int128 v32; // [rsp+50h] [rbp-B0h]
  __int16 v33; // [rsp+60h] [rbp-A0h] BYREF
  char v34; // [rsp+62h] [rbp-9Eh]
  int v35; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 v36; // [rsp+68h] [rbp-98h]
  __int128 v37; // [rsp+70h] [rbp-90h]
  char *v38; // [rsp+80h] [rbp-80h]
  char v39; // [rsp+88h] [rbp-78h] BYREF
  _QWORD v40[13]; // [rsp+90h] [rbp-70h] BYREF
  wil::details::in1diag3 *v41; // [rsp+F8h] [rbp-8h]
  __int64 v42; // [rsp+100h] [rbp+0h] BYREF
  __int64 v43; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int8 *v44; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v45[6]; // [rsp+118h] [rbp+18h] BYREF
  _WORD v46[2]; // [rsp+130h] [rbp+30h] BYREF
  char v47; // [rsp+134h] [rbp+34h]
  __int16 v48; // [rsp+136h] [rbp+36h]
  char v49; // [rsp+138h] [rbp+38h]
  __int64 v50; // [rsp+140h] [rbp+40h]
  __int64 v51; // [rsp+148h] [rbp+48h]
  __int128 v52; // [rsp+150h] [rbp+50h]
  LPVOID lpMem; // [rsp+160h] [rbp+60h]
  __int16 v54; // [rsp+168h] [rbp+68h]
  char v55; // [rsp+16Ah] [rbp+6Ah]
  __int64 v56; // [rsp+170h] [rbp+70h] BYREF
  __int64 v57; // [rsp+178h] [rbp+78h] BYREF
  __int64 v58; // [rsp+180h] [rbp+80h] BYREF
  __int64 v59; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v60[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v57 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v46[0] = *(_WORD *)a3;
    v46[1] = *(_WORD *)(a3 + 2);
    v47 = *(_BYTE *)(a3 + 4);
    v48 = v9;
    v49 = v8;
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
      v50 = v10;
    }
    else
    {
      v50 = 0;
    }
    v51 = 0;
    v52 = 0;
    lpMem = 0;
    v54 = 0;
    v55 = 0;
    v45[0] = 0;
    LODWORD(v44) = 4096;
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
      v27 = (__int64 *)v60;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v5, 0, 0, v45);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v44) = 0;
      v45[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v44;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v46, v60, v15, 0x1000u);
    if ( HIBYTE(v54) )
      break;
    v56 = 0;
    v40[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v40[1] = &v56;
    v40[2] = &v57;
    v40[3] = v46;
    v41 = (wil::details::in1diag3 *)v40;
    v38 = &v39;
    v44 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v28 = *(_WORD *)(a3 + 2);
    v29 = *(_BYTE *)(a3 + 4);
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = *(_WORD *)(a3 + 6);
    v34 = *(_BYTE *)(a3 + 8);
    v35 = 0;
    v36 = 0;
    v37 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v28,
              &v44,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      v17 = v30;
      if ( v30 )
      {
        v18 = *((_QWORD *)&v32 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v33,
                  &v44,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v45[2] = v35;
          v58 = v36;
          v42 = *((_QWORD *)&v37 + 1);
          v59 = v31;
          v43 = v18;
          if ( !v41 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v27 = &v58;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v41 + 32LL))(
                  v41,
                  &v43,
                  &v59,
                  &v42) )
          {
            if ( v41 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v41 + 24LL))(v41);
            v20 = 0;
            goto LABEL_30;
          }
          if ( ++v16 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v41 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v41 + 24LL))(v41);
    v20 = 1;
LABEL_30:
    if ( !(_BYTE)v54 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v5, v51, (int)v52 - (int)v51, v19, (_DWORD)v27, v45[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v5, v51, v52 - v51, v22, (_DWORD)v27, 0, 0);
LABEL_38:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v57 = v56;
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
0x18001a5e4  mov     [rsp-8+arg_8], rbx
0x18001a5e9  push    rbp
0x18001a5ea  push    rsi
0x18001a5eb  push    rdi
0x18001a5ec  push    r12
0x18001a5ee  push    r13
0x18001a5f0  push    r14
0x18001a5f2  push    r15
0x18001a5f4  lea     rbp, [rsp-10A0h]
0x18001a5fc  mov     eax, 11A0h
0x18001a601  call    _alloca_probe
0x18001a606  sub     rsp, rax
0x18001a609  mov     rax, cs:__security_cookie
0x18001a610  xor     rax, rsp
0x18001a613  mov     [rbp+10D0h+var_40], rax
0x18001a61a  mov     rdi, r8
0x18001a61d  mov     r14, rcx
0x18001a620  lea     r13, [rcx+rdx*8]
0x18001a624  xor     r15d, r15d
0x18001a627  mov     r12d, r15d
0x18001a62a  mov     [rbp+10D0h+var_1058], r15
0x18001a62e  mov     cl, [rdi+8]
0x18001a631  movzx   edx, word ptr [rdi+6]
0x18001a635  movzx   eax, word ptr [rdi]
0x18001a638  mov     [rbp+10D0h+var_10A0], ax
0x18001a63c  movzx   eax, word ptr [rdi+2]
0x18001a640  mov     [rbp+10D0h+var_109E], ax
0x18001a644  mov     al, [rdi+4]
0x18001a647  mov     [rbp+10D0h+var_109C], al
0x18001a64a  mov     [rbp+10D0h+var_109A], dx
0x18001a64e  mov     [rbp+10D0h+var_1098], cl
0x18001a651  test    dx, dx
0x18001a654  jz      short loc_18001A672
0x18001a656  mov     eax, edx
0x18001a658  cmp     cl, 1
0x18001a65b  jnz     short loc_18001A663
0x18001a65d  add     rax, 2
0x18001a661  jmp     short loc_18001A66C
0x18001a663  cmp     cl, 2
0x18001a666  jnz     short loc_18001A66C
0x18001a668  add     rax, 4
0x18001a66c  mov     [rbp+10D0h+var_1090], rax
0x18001a670  jmp     short loc_18001A676
0x18001a672  mov     [rbp+10D0h+var_1090], r15
0x18001a676  mov     [rbp+10D0h+var_1088], r15
0x18001a67a  xorps   xmm0, xmm0
0x18001a67d  movdqa  [rbp+10D0h+var_1080], xmm0
0x18001a682  mov     [rbp+10D0h+lpMem], r15
0x18001a686  mov     [rbp+10D0h+var_1068], 0
0x18001a68c  mov     [rbp+10D0h+var_1066], r15b
0x18001a690  mov     [rbp+10D0h+var_10B8], r15d
0x18001a694  mov     dword ptr [rbp+10D0h+var_10C0], 1000h
0x18001a69b  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18001a6a2  test    rax, rax
0x18001a6a5  jnz     short loc_18001A6EA
0x18001a6a7  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001a6ae  test    rax, rax
0x18001a6b1  jnz     short loc_18001A6C7
0x18001a6b3  lea     rcx, ModuleName; "ntdll.dll"
0x18001a6ba  call    cs:__imp_GetModuleHandleW
0x18001a6c0  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001a6c7  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18001a6ce  mov     rcx, rax; hModule
0x18001a6d1  call    cs:__imp_GetProcAddress
0x18001a6d7  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18001a6de  test    rax, rax
0x18001a6e1  jnz     short loc_18001A6EA
0x18001a6e3  mov     ebx, 0C0000139h
0x18001a6e8  jmp     short loc_18001A712
0x18001a6ea  lea     rcx, [rbp+10D0h+var_10C0]
0x18001a6ee  mov     [rsp+11D0h+var_11A8], rcx
0x18001a6f3  lea     rcx, [rbp+10D0h+var_1040]
0x18001a6fa  mov     [rsp+11D0h+var_11B0], rcx
0x18001a6ff  lea     r9, [rbp+10D0h+var_10B8]
0x18001a703  xor     r8d, r8d
0x18001a706  xor     edx, edx
0x18001a708  mov     rcx, r14
0x18001a70b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a710  mov     ebx, eax
0x18001a712  mov     ecx, ebx; this
0x18001a714  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18001a719  test    ebx, ebx
0x18001a71b  jz      short loc_18001A729
0x18001a71d  mov     eax, r15d
0x18001a720  mov     dword ptr [rbp+10D0h+var_10C0], eax
0x18001a723  mov     [rbp+10D0h+var_10B8], r15d
0x18001a727  jmp     short loc_18001A72C
0x18001a729  mov     eax, dword ptr [rbp+10D0h+var_10C0]
0x18001a72c  mov     r8d, eax; unsigned __int64
0x18001a72f  mov     r9d, 1000h; unsigned __int64
0x18001a735  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18001a73c  lea     rcx, [rbp+10D0h+var_10A0]; this
0x18001a740  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18001a745  cmp     byte ptr [rbp+10D0h+var_1068+1], r15b
0x18001a749  jnz     loc_18001A968
0x18001a74f  mov     [rbp+10D0h+var_1060], r15
0x18001a753  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18001a75a  mov     [rbp+10D0h+var_1140], rax
0x18001a75e  lea     rax, [rbp+10D0h+var_1060]
0x18001a762  mov     [rbp+10D0h+var_1138], rax
0x18001a766  lea     rax, [rbp+10D0h+var_1058]
0x18001a76a  mov     [rbp+10D0h+var_1130], rax
0x18001a76e  lea     rax, [rbp+10D0h+var_10A0]
0x18001a772  mov     [rbp+10D0h+var_1128], rax
0x18001a776  lea     rax, [rbp+10D0h+var_1140]
0x18001a77a  mov     [rbp+10D0h+var_10D8], rax
0x18001a77e  lea     rax, [rbp+10D0h+var_1148]
0x18001a782  mov     [rbp+10D0h+var_1150], rax
0x18001a786  mov     rax, [rdi+18h]
0x18001a78a  add     rax, 0Ah
0x18001a78e  mov     [rbp+10D0h+var_10C0], rax
0x18001a792  movzx   eax, word ptr [rdi+2]
0x18001a796  mov     [rsp+11D0h+var_1190], ax
0x18001a79b  mov     al, [rdi+4]
0x18001a79e  mov     [rsp+11D0h+var_118E], al
0x18001a7a2  mov     [rsp+11D0h+var_118C], r15d
0x18001a7a7  mov     [rsp+11D0h+var_1188], r15w
0x18001a7ad  xorps   xmm0, xmm0
0x18001a7b0  movdqu  [rsp+11D0h+var_1180], xmm0
0x18001a7b6  movzx   eax, word ptr [rdi+6]
0x18001a7ba  mov     [rsp+11D0h+var_1170], ax
0x18001a7bf  mov     al, [rdi+8]
0x18001a7c2  mov     [rsp+11D0h+var_116E], al
0x18001a7c6  mov     [rsp+11D0h+var_116C], r15d
0x18001a7cb  mov     [rsp+11D0h+var_1168], r15w
0x18001a7d1  movdqu  [rsp+11D0h+var_1160], xmm0
0x18001a7d7  jmp     loc_18001A880
0x18001a7dc  mov     ebx, r15d
0x18001a7df  mov     esi, [rsp+11D0h+var_118C]
0x18001a7e3  test    esi, esi
0x18001a7e5  jz      loc_18001A880
0x18001a7eb  mov     r15, qword ptr [rsp+11D0h+var_1180+8]
0x18001a7f0  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001a7f4  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x18001a7f8  lea     rcx, [rsp+11D0h+var_1170]; this
0x18001a7fd  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001a802  test    al, al
0x18001a804  jz      short loc_18001A87D
0x18001a806  mov     eax, [rsp+11D0h+var_116C]
0x18001a80a  mov     [rbp+10D0h+var_10B0], eax
0x18001a80d  movzx   eax, [rsp+11D0h+var_1168]
0x18001a812  mov     [rbp+10D0h+var_1050], rax
0x18001a819  mov     rax, qword ptr [rsp+11D0h+var_1160+8]
0x18001a81e  mov     [rbp+10D0h+var_10D0], rax
0x18001a822  movzx   eax, [rsp+11D0h+var_1188]
0x18001a827  mov     [rbp+10D0h+var_1048], rax
0x18001a82e  mov     [rbp+10D0h+var_10C8], r15
0x18001a832  mov     rcx, [rbp+10D0h+var_10D8]; this
0x18001a836  test    rcx, rcx
0x18001a839  jz      loc_18001A9B3
0x18001a83f  mov     rax, [rcx]
0x18001a842  lea     rdx, [rbp+10D0h+var_10B0]
0x18001a846  mov     [rsp+11D0h+var_11A8], rdx
0x18001a84b  lea     rdx, [rbp+10D0h+var_1050]
0x18001a852  mov     [rsp+11D0h+var_11B0], rdx
0x18001a857  lea     r9, [rbp+10D0h+var_10D0]
0x18001a85b  lea     r8, [rbp+10D0h+var_1048]
0x18001a862  lea     rdx, [rbp+10D0h+var_10C8]
0x18001a866  mov     rax, [rax+20h]
0x18001a86a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a86f  test    al, al
0x18001a871  jz      short loc_18001A8E8
0x18001a873  inc     ebx
0x18001a875  cmp     ebx, esi
0x18001a877  jb      loc_18001A7F0
0x18001a87d  xor     r15d, r15d
0x18001a880  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001a884  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x18001a888  lea     rcx, [rsp+11D0h+var_1190]; this
0x18001a88d  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001a892  test    al, al
0x18001a894  jnz     loc_18001A7DC
0x18001a89a  mov     rcx, [rbp+10D0h+var_10D8]
0x18001a89e  test    rcx, rcx
0x18001a8a1  jz      short loc_18001A8AF
0x18001a8a3  mov     rax, [rcx]
0x18001a8a6  mov     rax, [rax+18h]
0x18001a8aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a8af  mov     bl, 1
0x18001a8b1  cmp     byte ptr [rbp+10D0h+var_1068], r15b
0x18001a8b5  jz      short loc_18001A926
0x18001a8b7  mov     eax, [rbp+10D0h+var_10B8]
0x18001a8ba  mov     rdx, [rbp+10D0h+var_1088]
0x18001a8be  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x18001a8c2  sub     r8d, edx
0x18001a8c5  mov     [rsp+11D0h+var_11A0], 1
0x18001a8cd  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18001a8d1  mov     rcx, r14
0x18001a8d4  call    wil_details_NtUpdateWnfStateData
0x18001a8d9  cmp     eax, 0C0000001h
0x18001a8de  jnz     short loc_18001A905
0x18001a8e0  inc     r12
0x18001a8e3  mov     bl, r15b
0x18001a8e6  jmp     short loc_18001A932
0x18001a8e8  mov     rcx, [rbp+10D0h+var_10D8]
0x18001a8ec  xor     r15d, r15d
0x18001a8ef  test    rcx, rcx
0x18001a8f2  jz      short loc_18001A900
0x18001a8f4  mov     rax, [rcx]
0x18001a8f7  mov     rax, [rax+18h]
0x18001a8fb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001a900  mov     bl, r15b
0x18001a903  jmp     short loc_18001A8B1
0x18001a905  test    eax, eax
0x18001a907  jz      short loc_18001A926
0x18001a909  mov     rdx, [rbp+10D0h+var_1088]
0x18001a90d  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x18001a911  sub     r8d, edx
0x18001a914  mov     [rsp+11D0h+var_11A0], r15d
0x18001a919  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18001a91e  mov     rcx, r14
0x18001a921  call    wil_details_NtUpdateWnfStateData
0x18001a926  add     r14, 8
0x18001a92a  mov     rax, [rbp+10D0h+var_1060]
0x18001a92e  mov     [rbp+10D0h+var_1058], rax
0x18001a932  mov     rsi, [rbp+10D0h+lpMem]
0x18001a936  mov     [rbp+10D0h+lpMem], r15
0x18001a93a  test    rsi, rsi
0x18001a93d  jz      short loc_18001A953
0x18001a93f  call    cs:__imp_GetProcessHeap
0x18001a945  mov     rcx, rax; hHeap
0x18001a948  mov     r8, rsi; lpMem
0x18001a94b  xor     edx, edx; dwFlags
0x18001a94d  call    cs:__imp_HeapFree
0x18001a953  test    bl, bl
0x18001a955  jnz     short loc_18001A989
0x18001a957  cmp     r14, r13
0x18001a95a  jnb     short loc_18001A989
0x18001a95c  cmp     r12, 32h ; '2'
0x18001a960  jb      loc_18001A62E
0x18001a966  jmp     short loc_18001A989
0x18001a968  mov     rbx, [rbp+10D0h+lpMem]
0x18001a96c  mov     [rbp+10D0h+lpMem], r15
0x18001a970  test    rbx, rbx
0x18001a973  jz      short loc_18001A989
0x18001a975  call    cs:__imp_GetProcessHeap
0x18001a97b  mov     rcx, rax; hHeap
0x18001a97e  mov     r8, rbx; lpMem
0x18001a981  xor     edx, edx; dwFlags
0x18001a983  call    cs:__imp_HeapFree
0x18001a989  mov     rcx, [rbp+10D0h+var_40]
0x18001a990  xor     rcx, rsp; StackCookie
0x18001a993  call    __security_check_cookie
0x18001a998  mov     rbx, [rsp+11D0h+arg_8]
0x18001a9a0  add     rsp, 11A0h
0x18001a9a7  pop     r15
0x18001a9a9  pop     r14
0x18001a9ab  pop     r13
0x18001a9ad  pop     r12
0x18001a9af  pop     rdi
0x18001a9b0  pop     rsi
0x18001a9b1  pop     rbp
0x18001a9b2  retn
0x18001a9b3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
