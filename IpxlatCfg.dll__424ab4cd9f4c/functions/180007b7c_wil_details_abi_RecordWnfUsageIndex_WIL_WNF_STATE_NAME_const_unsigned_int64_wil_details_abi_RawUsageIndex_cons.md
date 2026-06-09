# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180007b7c`
- end: `0x180007f54`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180007064`

## callees

- `0x180001d40`
- `0x180006b18`
- `0x180006f1c`
- `0x180007b7c`
- `0x1800086c4`
- `0x180009bbc`
- `0x18000a3f0`
- `0x180017e10`
- `0x180019010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ee8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f1e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007ee8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007f1e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007eda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f10`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007eda`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007f10`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007c73`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c5c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180007c5c`

## string_xrefs

- `0x180007c55`: `ntdll.dll`

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
0x180007b7c  mov     [rsp-8+arg_8], rbx
0x180007b81  push    rbp
0x180007b82  push    rsi
0x180007b83  push    rdi
0x180007b84  push    r12
0x180007b86  push    r13
0x180007b88  push    r14
0x180007b8a  push    r15
0x180007b8c  lea     rbp, [rsp-10A0h]
0x180007b94  mov     eax, 11A0h
0x180007b99  call    _alloca_probe
0x180007b9e  sub     rsp, rax
0x180007ba1  mov     rax, cs:__security_cookie
0x180007ba8  xor     rax, rsp
0x180007bab  mov     [rbp+10D0h+var_40], rax
0x180007bb2  mov     rdi, r8
0x180007bb5  mov     r14, rcx
0x180007bb8  lea     r13, [rcx+rdx*8]
0x180007bbc  xor     r15d, r15d
0x180007bbf  mov     r12d, r15d
0x180007bc2  mov     [rbp+10D0h+var_1128], r15
0x180007bc6  mov     cl, [rdi+8]
0x180007bc9  movzx   edx, word ptr [rdi+6]
0x180007bcd  movzx   eax, word ptr [rdi]
0x180007bd0  mov     [rsp+11D0h+var_1170], ax
0x180007bd5  movzx   eax, word ptr [rdi+2]
0x180007bd9  mov     [rsp+11D0h+var_116E], ax
0x180007bde  mov     al, [rdi+4]
0x180007be1  mov     [rsp+11D0h+var_116C], al
0x180007be5  mov     [rsp+11D0h+var_116A], dx
0x180007bea  mov     [rsp+11D0h+var_1168], cl
0x180007bee  test    dx, dx
0x180007bf1  jz      short loc_180007C10
0x180007bf3  mov     eax, edx
0x180007bf5  cmp     cl, 1
0x180007bf8  jnz     short loc_180007C00
0x180007bfa  add     rax, 2
0x180007bfe  jmp     short loc_180007C09
0x180007c00  cmp     cl, 2
0x180007c03  jnz     short loc_180007C09
0x180007c05  add     rax, 4
0x180007c09  mov     [rsp+11D0h+var_1160], rax
0x180007c0e  jmp     short loc_180007C15
0x180007c10  mov     [rsp+11D0h+var_1160], r15
0x180007c15  mov     [rsp+11D0h+var_1158], r15
0x180007c1a  xorps   xmm0, xmm0
0x180007c1d  movdqa  [rbp+10D0h+var_1150], xmm0
0x180007c22  mov     [rbp+10D0h+lpMem], r15
0x180007c26  mov     [rbp+10D0h+var_1138], 0
0x180007c2c  mov     [rbp+10D0h+var_1136], r15b
0x180007c30  mov     [rsp+11D0h+var_1188], r15d
0x180007c35  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180007c3d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180007c44  test    rax, rax
0x180007c47  jnz     short loc_180007C8C
0x180007c49  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007c50  test    rax, rax
0x180007c53  jnz     short loc_180007C69
0x180007c55  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180007c5c  call    cs:__imp_GetModuleHandleW
0x180007c62  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007c69  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180007c70  mov     rcx, rax; hModule
0x180007c73  call    cs:__imp_GetProcAddress
0x180007c79  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180007c80  test    rax, rax
0x180007c83  jnz     short loc_180007C8C
0x180007c85  mov     ebx, 0C0000139h
0x180007c8a  jmp     short loc_180007CB6
0x180007c8c  lea     rcx, [rsp+11D0h+var_1190]
0x180007c91  mov     [rsp+11D0h+var_11A8], rcx
0x180007c96  lea     rcx, [rbp+10D0h+var_1040]
0x180007c9d  mov     [rsp+11D0h+var_11B0], rcx
0x180007ca2  lea     r9, [rsp+11D0h+var_1188]
0x180007ca7  xor     r8d, r8d
0x180007caa  xor     edx, edx
0x180007cac  mov     rcx, r14
0x180007caf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007cb4  mov     ebx, eax
0x180007cb6  mov     ecx, ebx; this
0x180007cb8  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180007cbd  test    ebx, ebx
0x180007cbf  jz      short loc_180007CCF
0x180007cc1  mov     eax, r15d
0x180007cc4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180007cc8  mov     [rsp+11D0h+var_1188], r15d
0x180007ccd  jmp     short loc_180007CD3
0x180007ccf  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180007cd3  mov     r8d, eax; unsigned __int64
0x180007cd6  mov     r9d, 1000h; unsigned __int64
0x180007cdc  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180007ce3  lea     rcx, [rsp+11D0h+var_1170]; this
0x180007ce8  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180007ced  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180007cf1  jnz     loc_180007F03
0x180007cf7  mov     [rbp+10D0h+var_1130], r15
0x180007cfb  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180007d02  mov     [rbp+10D0h+var_10B0], rax
0x180007d06  lea     rax, [rbp+10D0h+var_1130]
0x180007d0a  mov     [rbp+10D0h+var_10A8], rax
0x180007d0e  lea     rax, [rbp+10D0h+var_1128]
0x180007d12  mov     [rbp+10D0h+var_10A0], rax
0x180007d16  lea     rax, [rsp+11D0h+var_1170]
0x180007d1b  mov     [rbp+10D0h+var_1098], rax
0x180007d1f  lea     rax, [rbp+10D0h+var_10B0]
0x180007d23  mov     [rbp+10D0h+var_1048], rax
0x180007d2a  lea     rax, [rbp+10D0h+var_10B8]
0x180007d2e  mov     [rbp+10D0h+var_10C0], rax
0x180007d32  mov     rax, [rdi+18h]
0x180007d36  add     rax, 0Ah
0x180007d3a  mov     [rsp+11D0h+var_1190], rax
0x180007d3f  movzx   eax, word ptr [rdi+2]
0x180007d43  mov     [rbp+10D0h+var_1120], ax
0x180007d47  mov     al, [rdi+4]
0x180007d4a  mov     [rbp+10D0h+var_111E], al
0x180007d4d  mov     [rbp+10D0h+var_111C], r15d
0x180007d51  mov     [rbp+10D0h+var_1118], r15w
0x180007d56  xorps   xmm0, xmm0
0x180007d59  movdqu  [rbp+10D0h+var_1110], xmm0
0x180007d5e  movzx   eax, word ptr [rdi+6]
0x180007d62  mov     [rbp+10D0h+var_1100], ax
0x180007d66  mov     al, [rdi+8]
0x180007d69  mov     [rbp+10D0h+var_10FE], al
0x180007d6c  mov     [rbp+10D0h+var_10FC], r15d
0x180007d70  mov     [rbp+10D0h+var_10F8], r15w
0x180007d75  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180007d7a  jmp     loc_180007E12
0x180007d7f  mov     ebx, r15d
0x180007d82  mov     esi, [rbp+10D0h+var_111C]
0x180007d85  test    esi, esi
0x180007d87  jz      loc_180007E12
0x180007d8d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180007d91  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007d95  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180007d9a  lea     rcx, [rbp+10D0h+var_1100]; this
0x180007d9e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007da3  test    al, al
0x180007da5  jz      short loc_180007E0F
0x180007da7  mov     eax, [rbp+10D0h+var_10FC]
0x180007daa  mov     [rsp+11D0h+var_1180], eax
0x180007dae  movzx   eax, [rbp+10D0h+var_10F8]
0x180007db2  mov     [rbp+10D0h+var_10E0], rax
0x180007db6  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180007dba  mov     [rbp+10D0h+var_10D8], rax
0x180007dbe  movzx   eax, [rbp+10D0h+var_1118]
0x180007dc2  mov     [rbp+10D0h+var_10D0], rax
0x180007dc6  mov     [rbp+10D0h+var_10C8], r15
0x180007dca  mov     rcx, [rbp+10D0h+var_1048]; this
0x180007dd1  test    rcx, rcx
0x180007dd4  jz      loc_180007F4E
0x180007dda  mov     rax, [rcx]
0x180007ddd  lea     rdx, [rsp+11D0h+var_1180]
0x180007de2  mov     [rsp+11D0h+var_11A8], rdx
0x180007de7  lea     rdx, [rbp+10D0h+var_10E0]
0x180007deb  mov     [rsp+11D0h+var_11B0], rdx
0x180007df0  lea     r9, [rbp+10D0h+var_10D8]
0x180007df4  lea     r8, [rbp+10D0h+var_10D0]
0x180007df8  lea     rdx, [rbp+10D0h+var_10C8]
0x180007dfc  mov     rax, [rax+20h]
0x180007e00  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e05  test    al, al
0x180007e07  jz      short loc_180007E7F
0x180007e09  inc     ebx
0x180007e0b  cmp     ebx, esi
0x180007e0d  jb      short loc_180007D91
0x180007e0f  xor     r15d, r15d
0x180007e12  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007e16  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180007e1b  lea     rcx, [rbp+10D0h+var_1120]; this
0x180007e1f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007e24  test    al, al
0x180007e26  jnz     loc_180007D7F
0x180007e2c  mov     rcx, [rbp+10D0h+var_1048]
0x180007e33  test    rcx, rcx
0x180007e36  jz      short loc_180007E44
0x180007e38  mov     rax, [rcx]
0x180007e3b  mov     rax, [rax+18h]
0x180007e3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e44  mov     bl, 1
0x180007e46  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180007e4a  jz      short loc_180007EC1
0x180007e4c  mov     eax, [rsp+11D0h+var_1188]
0x180007e50  mov     rdx, [rsp+11D0h+var_1158]
0x180007e55  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007e59  sub     r8d, edx
0x180007e5c  mov     [rsp+11D0h+var_11A0], 1
0x180007e64  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180007e68  mov     rcx, r14
0x180007e6b  call    wil_details_NtUpdateWnfStateData
0x180007e70  cmp     eax, 0C0000001h
0x180007e75  jnz     short loc_180007E9F
0x180007e77  inc     r12
0x180007e7a  mov     bl, r15b
0x180007e7d  jmp     short loc_180007ECD
0x180007e7f  mov     rcx, [rbp+10D0h+var_1048]
0x180007e86  xor     r15d, r15d
0x180007e89  test    rcx, rcx
0x180007e8c  jz      short loc_180007E9A
0x180007e8e  mov     rax, [rcx]
0x180007e91  mov     rax, [rax+18h]
0x180007e95  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007e9a  mov     bl, r15b
0x180007e9d  jmp     short loc_180007E46
0x180007e9f  test    eax, eax
0x180007ea1  jz      short loc_180007EC1
0x180007ea3  mov     rdx, [rsp+11D0h+var_1158]
0x180007ea8  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180007eac  sub     r8d, edx
0x180007eaf  mov     [rsp+11D0h+var_11A0], r15d
0x180007eb4  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180007eb9  mov     rcx, r14
0x180007ebc  call    wil_details_NtUpdateWnfStateData
0x180007ec1  add     r14, 8
0x180007ec5  mov     rax, [rbp+10D0h+var_1130]
0x180007ec9  mov     [rbp+10D0h+var_1128], rax
0x180007ecd  mov     rsi, [rbp+10D0h+lpMem]
0x180007ed1  mov     [rbp+10D0h+lpMem], r15
0x180007ed5  test    rsi, rsi
0x180007ed8  jz      short loc_180007EEE
0x180007eda  call    cs:__imp_GetProcessHeap
0x180007ee0  mov     rcx, rax; hHeap
0x180007ee3  mov     r8, rsi; lpMem
0x180007ee6  xor     edx, edx; dwFlags
0x180007ee8  call    cs:__imp_HeapFree
0x180007eee  test    bl, bl
0x180007ef0  jnz     short loc_180007F24
0x180007ef2  cmp     r14, r13
0x180007ef5  jnb     short loc_180007F24
0x180007ef7  cmp     r12, 32h ; '2'
0x180007efb  jb      loc_180007BC6
0x180007f01  jmp     short loc_180007F24
0x180007f03  mov     rbx, [rbp+10D0h+lpMem]
0x180007f07  mov     [rbp+10D0h+lpMem], r15
0x180007f0b  test    rbx, rbx
0x180007f0e  jz      short loc_180007F24
0x180007f10  call    cs:__imp_GetProcessHeap
0x180007f16  mov     rcx, rax; hHeap
0x180007f19  mov     r8, rbx; lpMem
0x180007f1c  xor     edx, edx; dwFlags
0x180007f1e  call    cs:__imp_HeapFree
0x180007f24  mov     rcx, [rbp+10D0h+var_40]
0x180007f2b  xor     rcx, rsp; StackCookie
0x180007f2e  call    __security_check_cookie
0x180007f33  mov     rbx, [rsp+11D0h+arg_8]
0x180007f3b  add     rsp, 11A0h
0x180007f42  pop     r15
0x180007f44  pop     r14
0x180007f46  pop     r13
0x180007f48  pop     r12
0x180007f4a  pop     rdi
0x180007f4b  pop     rsi
0x180007f4c  pop     rbp
0x180007f4d  retn
0x180007f4e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
