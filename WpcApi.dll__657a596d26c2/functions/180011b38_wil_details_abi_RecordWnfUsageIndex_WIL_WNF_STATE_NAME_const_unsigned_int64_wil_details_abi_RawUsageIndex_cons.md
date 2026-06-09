# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180011b38`
- end: `0x180011f10`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18001128c`

## callees

- `0x1800032a0`
- `0x18000a8dc`
- `0x180010c34`
- `0x18001118c`
- `0x180011b38`
- `0x18001279c`
- `0x180014b74`
- `0x180028fe0`
- `0x18002c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011c18`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180011c18`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011c2f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180011c2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011e96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ecc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011e96`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180011ecc`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011ea4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011eda`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011ea4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180011eda`

## string_xrefs

- `0x180011c11`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
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
0x180011b38  mov     [rsp-8+arg_8], rbx
0x180011b3d  push    rbp
0x180011b3e  push    rsi
0x180011b3f  push    rdi
0x180011b40  push    r12
0x180011b42  push    r13
0x180011b44  push    r14
0x180011b46  push    r15
0x180011b48  lea     rbp, [rsp-10A0h]
0x180011b50  mov     eax, 11A0h
0x180011b55  call    _alloca_probe
0x180011b5a  sub     rsp, rax
0x180011b5d  mov     rax, cs:__security_cookie
0x180011b64  xor     rax, rsp
0x180011b67  mov     [rbp+10D0h+var_40], rax
0x180011b6e  mov     rdi, r8
0x180011b71  mov     r14, rcx
0x180011b74  lea     r13, [rcx+rdx*8]
0x180011b78  xor     r15d, r15d
0x180011b7b  mov     r12d, r15d
0x180011b7e  mov     [rbp+10D0h+var_1128], r15
0x180011b82  mov     cl, [rdi+8]
0x180011b85  movzx   edx, word ptr [rdi+6]
0x180011b89  movzx   eax, word ptr [rdi]
0x180011b8c  mov     [rsp+11D0h+var_1170], ax
0x180011b91  movzx   eax, word ptr [rdi+2]
0x180011b95  mov     [rsp+11D0h+var_116E], ax
0x180011b9a  mov     al, [rdi+4]
0x180011b9d  mov     [rsp+11D0h+var_116C], al
0x180011ba1  mov     [rsp+11D0h+var_116A], dx
0x180011ba6  mov     [rsp+11D0h+var_1168], cl
0x180011baa  test    dx, dx
0x180011bad  jz      short loc_180011BCC
0x180011baf  mov     eax, edx
0x180011bb1  cmp     cl, 1
0x180011bb4  jnz     short loc_180011BBC
0x180011bb6  add     rax, 2
0x180011bba  jmp     short loc_180011BC5
0x180011bbc  cmp     cl, 2
0x180011bbf  jnz     short loc_180011BC5
0x180011bc1  add     rax, 4
0x180011bc5  mov     [rsp+11D0h+var_1160], rax
0x180011bca  jmp     short loc_180011BD1
0x180011bcc  mov     [rsp+11D0h+var_1160], r15
0x180011bd1  mov     [rsp+11D0h+var_1158], r15
0x180011bd6  xorps   xmm0, xmm0
0x180011bd9  movdqa  [rbp+10D0h+var_1150], xmm0
0x180011bde  mov     [rbp+10D0h+lpMem], r15
0x180011be2  mov     [rbp+10D0h+var_1138], 0
0x180011be8  mov     [rbp+10D0h+var_1136], r15b
0x180011bec  mov     [rsp+11D0h+var_1188], r15d
0x180011bf1  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180011bf9  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180011c00  test    rax, rax
0x180011c03  jnz     short loc_180011C48
0x180011c05  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011c0c  test    rax, rax
0x180011c0f  jnz     short loc_180011C25
0x180011c11  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180011c18  call    cs:__imp_GetModuleHandleW
0x180011c1e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180011c25  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180011c2c  mov     rcx, rax; hModule
0x180011c2f  call    cs:__imp_GetProcAddress
0x180011c35  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180011c3c  test    rax, rax
0x180011c3f  jnz     short loc_180011C48
0x180011c41  mov     ebx, 0C0000139h
0x180011c46  jmp     short loc_180011C72
0x180011c48  lea     rcx, [rsp+11D0h+var_1190]
0x180011c4d  mov     [rsp+11D0h+var_11A8], rcx
0x180011c52  lea     rcx, [rbp+10D0h+var_1040]
0x180011c59  mov     [rsp+11D0h+var_11B0], rcx
0x180011c5e  lea     r9, [rsp+11D0h+var_1188]
0x180011c63  xor     r8d, r8d
0x180011c66  xor     edx, edx
0x180011c68  mov     rcx, r14
0x180011c6b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011c70  mov     ebx, eax
0x180011c72  mov     ecx, ebx; this
0x180011c74  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180011c79  test    ebx, ebx
0x180011c7b  jz      short loc_180011C8B
0x180011c7d  mov     eax, r15d
0x180011c80  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180011c84  mov     [rsp+11D0h+var_1188], r15d
0x180011c89  jmp     short loc_180011C8F
0x180011c8b  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180011c8f  mov     r8d, eax; unsigned __int64
0x180011c92  mov     r9d, 1000h; unsigned __int64
0x180011c98  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180011c9f  lea     rcx, [rsp+11D0h+var_1170]; this
0x180011ca4  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180011ca9  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180011cad  jnz     loc_180011EBF
0x180011cb3  mov     [rbp+10D0h+var_1130], r15
0x180011cb7  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180011cbe  mov     [rbp+10D0h+var_10B0], rax
0x180011cc2  lea     rax, [rbp+10D0h+var_1130]
0x180011cc6  mov     [rbp+10D0h+var_10A8], rax
0x180011cca  lea     rax, [rbp+10D0h+var_1128]
0x180011cce  mov     [rbp+10D0h+var_10A0], rax
0x180011cd2  lea     rax, [rsp+11D0h+var_1170]
0x180011cd7  mov     [rbp+10D0h+var_1098], rax
0x180011cdb  lea     rax, [rbp+10D0h+var_10B0]
0x180011cdf  mov     [rbp+10D0h+var_1048], rax
0x180011ce6  lea     rax, [rbp+10D0h+var_10B8]
0x180011cea  mov     [rbp+10D0h+var_10C0], rax
0x180011cee  mov     rax, [rdi+18h]
0x180011cf2  add     rax, 0Ah
0x180011cf6  mov     [rsp+11D0h+var_1190], rax
0x180011cfb  movzx   eax, word ptr [rdi+2]
0x180011cff  mov     [rbp+10D0h+var_1120], ax
0x180011d03  mov     al, [rdi+4]
0x180011d06  mov     [rbp+10D0h+var_111E], al
0x180011d09  mov     [rbp+10D0h+var_111C], r15d
0x180011d0d  mov     [rbp+10D0h+var_1118], r15w
0x180011d12  xorps   xmm0, xmm0
0x180011d15  movdqu  [rbp+10D0h+var_1110], xmm0
0x180011d1a  movzx   eax, word ptr [rdi+6]
0x180011d1e  mov     [rbp+10D0h+var_1100], ax
0x180011d22  mov     al, [rdi+8]
0x180011d25  mov     [rbp+10D0h+var_10FE], al
0x180011d28  mov     [rbp+10D0h+var_10FC], r15d
0x180011d2c  mov     [rbp+10D0h+var_10F8], r15w
0x180011d31  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180011d36  jmp     loc_180011DCE
0x180011d3b  mov     ebx, r15d
0x180011d3e  mov     esi, [rbp+10D0h+var_111C]
0x180011d41  test    esi, esi
0x180011d43  jz      loc_180011DCE
0x180011d49  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180011d4d  mov     r8, [rdi+20h]; unsigned __int8 *
0x180011d51  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180011d56  lea     rcx, [rbp+10D0h+var_1100]; this
0x180011d5a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180011d5f  test    al, al
0x180011d61  jz      short loc_180011DCB
0x180011d63  mov     eax, [rbp+10D0h+var_10FC]
0x180011d66  mov     [rsp+11D0h+var_1180], eax
0x180011d6a  movzx   eax, [rbp+10D0h+var_10F8]
0x180011d6e  mov     [rbp+10D0h+var_10E0], rax
0x180011d72  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180011d76  mov     [rbp+10D0h+var_10D8], rax
0x180011d7a  movzx   eax, [rbp+10D0h+var_1118]
0x180011d7e  mov     [rbp+10D0h+var_10D0], rax
0x180011d82  mov     [rbp+10D0h+var_10C8], r15
0x180011d86  mov     rcx, [rbp+10D0h+var_1048]; this
0x180011d8d  test    rcx, rcx
0x180011d90  jz      loc_180011F0A
0x180011d96  mov     rax, [rcx]
0x180011d99  lea     rdx, [rsp+11D0h+var_1180]
0x180011d9e  mov     [rsp+11D0h+var_11A8], rdx
0x180011da3  lea     rdx, [rbp+10D0h+var_10E0]
0x180011da7  mov     [rsp+11D0h+var_11B0], rdx
0x180011dac  lea     r9, [rbp+10D0h+var_10D8]
0x180011db0  lea     r8, [rbp+10D0h+var_10D0]
0x180011db4  lea     rdx, [rbp+10D0h+var_10C8]
0x180011db8  mov     rax, [rax+20h]
0x180011dbc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011dc1  test    al, al
0x180011dc3  jz      short loc_180011E3B
0x180011dc5  inc     ebx
0x180011dc7  cmp     ebx, esi
0x180011dc9  jb      short loc_180011D4D
0x180011dcb  xor     r15d, r15d
0x180011dce  mov     r8, [rdi+20h]; unsigned __int8 *
0x180011dd2  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180011dd7  lea     rcx, [rbp+10D0h+var_1120]; this
0x180011ddb  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180011de0  test    al, al
0x180011de2  jnz     loc_180011D3B
0x180011de8  mov     rcx, [rbp+10D0h+var_1048]
0x180011def  test    rcx, rcx
0x180011df2  jz      short loc_180011E00
0x180011df4  mov     rax, [rcx]
0x180011df7  mov     rax, [rax+18h]
0x180011dfb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e00  mov     bl, 1
0x180011e02  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180011e06  jz      short loc_180011E7D
0x180011e08  mov     eax, [rsp+11D0h+var_1188]
0x180011e0c  mov     rdx, [rsp+11D0h+var_1158]
0x180011e11  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180011e15  sub     r8d, edx
0x180011e18  mov     [rsp+11D0h+var_11A0], 1
0x180011e20  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180011e24  mov     rcx, r14
0x180011e27  call    wil_details_NtUpdateWnfStateData
0x180011e2c  cmp     eax, 0C0000001h
0x180011e31  jnz     short loc_180011E5B
0x180011e33  inc     r12
0x180011e36  mov     bl, r15b
0x180011e39  jmp     short loc_180011E89
0x180011e3b  mov     rcx, [rbp+10D0h+var_1048]
0x180011e42  xor     r15d, r15d
0x180011e45  test    rcx, rcx
0x180011e48  jz      short loc_180011E56
0x180011e4a  mov     rax, [rcx]
0x180011e4d  mov     rax, [rax+18h]
0x180011e51  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180011e56  mov     bl, r15b
0x180011e59  jmp     short loc_180011E02
0x180011e5b  test    eax, eax
0x180011e5d  jz      short loc_180011E7D
0x180011e5f  mov     rdx, [rsp+11D0h+var_1158]
0x180011e64  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180011e68  sub     r8d, edx
0x180011e6b  mov     [rsp+11D0h+var_11A0], r15d
0x180011e70  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180011e75  mov     rcx, r14
0x180011e78  call    wil_details_NtUpdateWnfStateData
0x180011e7d  add     r14, 8
0x180011e81  mov     rax, [rbp+10D0h+var_1130]
0x180011e85  mov     [rbp+10D0h+var_1128], rax
0x180011e89  mov     rsi, [rbp+10D0h+lpMem]
0x180011e8d  mov     [rbp+10D0h+lpMem], r15
0x180011e91  test    rsi, rsi
0x180011e94  jz      short loc_180011EAA
0x180011e96  call    cs:__imp_GetProcessHeap
0x180011e9c  mov     rcx, rax; hHeap
0x180011e9f  mov     r8, rsi; lpMem
0x180011ea2  xor     edx, edx; dwFlags
0x180011ea4  call    cs:__imp_HeapFree
0x180011eaa  test    bl, bl
0x180011eac  jnz     short loc_180011EE0
0x180011eae  cmp     r14, r13
0x180011eb1  jnb     short loc_180011EE0
0x180011eb3  cmp     r12, 32h ; '2'
0x180011eb7  jb      loc_180011B82
0x180011ebd  jmp     short loc_180011EE0
0x180011ebf  mov     rbx, [rbp+10D0h+lpMem]
0x180011ec3  mov     [rbp+10D0h+lpMem], r15
0x180011ec7  test    rbx, rbx
0x180011eca  jz      short loc_180011EE0
0x180011ecc  call    cs:__imp_GetProcessHeap
0x180011ed2  mov     rcx, rax; hHeap
0x180011ed5  mov     r8, rbx; lpMem
0x180011ed8  xor     edx, edx; dwFlags
0x180011eda  call    cs:__imp_HeapFree
0x180011ee0  mov     rcx, [rbp+10D0h+var_40]
0x180011ee7  xor     rcx, rsp; StackCookie
0x180011eea  call    __security_check_cookie
0x180011eef  mov     rbx, [rsp+11D0h+arg_8]
0x180011ef7  add     rsp, 11A0h
0x180011efe  pop     r15
0x180011f00  pop     r14
0x180011f02  pop     r13
0x180011f04  pop     r12
0x180011f06  pop     rdi
0x180011f07  pop     rsi
0x180011f08  pop     rbp
0x180011f09  retn
0x180011f0a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
