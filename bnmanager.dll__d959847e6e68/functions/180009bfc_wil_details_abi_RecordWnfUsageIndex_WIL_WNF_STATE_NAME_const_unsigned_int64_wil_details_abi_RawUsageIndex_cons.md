# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180009bfc`
- end: `0x180009fd4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800092e0`

## callees

- `0x1800017c0`
- `0x180008d78`
- `0x1800091e0`
- `0x180009bfc`
- `0x18000a844`
- `0x18000bb7c`
- `0x18000c428`
- `0x18000ca80`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f9e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009f9e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f90`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f5a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009f90`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009cdc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009cdc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009cf3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009cf3`

## string_xrefs

- `0x180009cd5`: `ntdll.dll`

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
0x180009bfc  mov     [rsp-8+arg_8], rbx
0x180009c01  push    rbp
0x180009c02  push    rsi
0x180009c03  push    rdi
0x180009c04  push    r12
0x180009c06  push    r13
0x180009c08  push    r14
0x180009c0a  push    r15
0x180009c0c  lea     rbp, [rsp-10A0h]
0x180009c14  mov     eax, 11A0h
0x180009c19  call    _alloca_probe
0x180009c1e  sub     rsp, rax
0x180009c21  mov     rax, cs:__security_cookie
0x180009c28  xor     rax, rsp
0x180009c2b  mov     [rbp+10D0h+var_40], rax
0x180009c32  mov     rdi, r8
0x180009c35  mov     r14, rcx
0x180009c38  lea     r13, [rcx+rdx*8]
0x180009c3c  xor     r15d, r15d
0x180009c3f  mov     r12d, r15d
0x180009c42  mov     [rbp+10D0h+var_1128], r15
0x180009c46  mov     cl, [rdi+8]
0x180009c49  movzx   edx, word ptr [rdi+6]
0x180009c4d  movzx   eax, word ptr [rdi]
0x180009c50  mov     [rsp+11D0h+var_1170], ax
0x180009c55  movzx   eax, word ptr [rdi+2]
0x180009c59  mov     [rsp+11D0h+var_116E], ax
0x180009c5e  mov     al, [rdi+4]
0x180009c61  mov     [rsp+11D0h+var_116C], al
0x180009c65  mov     [rsp+11D0h+var_116A], dx
0x180009c6a  mov     [rsp+11D0h+var_1168], cl
0x180009c6e  test    dx, dx
0x180009c71  jz      short loc_180009C90
0x180009c73  mov     eax, edx
0x180009c75  cmp     cl, 1
0x180009c78  jnz     short loc_180009C80
0x180009c7a  add     rax, 2
0x180009c7e  jmp     short loc_180009C89
0x180009c80  cmp     cl, 2
0x180009c83  jnz     short loc_180009C89
0x180009c85  add     rax, 4
0x180009c89  mov     [rsp+11D0h+var_1160], rax
0x180009c8e  jmp     short loc_180009C95
0x180009c90  mov     [rsp+11D0h+var_1160], r15
0x180009c95  mov     [rsp+11D0h+var_1158], r15
0x180009c9a  xorps   xmm0, xmm0
0x180009c9d  movdqa  [rbp+10D0h+var_1150], xmm0
0x180009ca2  mov     [rbp+10D0h+lpMem], r15
0x180009ca6  mov     [rbp+10D0h+var_1138], 0
0x180009cac  mov     [rbp+10D0h+var_1136], r15b
0x180009cb0  mov     [rsp+11D0h+var_1188], r15d
0x180009cb5  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180009cbd  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180009cc4  test    rax, rax
0x180009cc7  jnz     short loc_180009D0C
0x180009cc9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009cd0  test    rax, rax
0x180009cd3  jnz     short loc_180009CE9
0x180009cd5  lea     rcx, ModuleName; "ntdll.dll"
0x180009cdc  call    cs:__imp_GetModuleHandleW
0x180009ce2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009ce9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009cf0  mov     rcx, rax; hModule
0x180009cf3  call    cs:__imp_GetProcAddress
0x180009cf9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009d00  test    rax, rax
0x180009d03  jnz     short loc_180009D0C
0x180009d05  mov     ebx, 0C0000139h
0x180009d0a  jmp     short loc_180009D36
0x180009d0c  lea     rcx, [rsp+11D0h+var_1190]
0x180009d11  mov     [rsp+11D0h+var_11A8], rcx
0x180009d16  lea     rcx, [rbp+10D0h+var_1040]
0x180009d1d  mov     [rsp+11D0h+var_11B0], rcx
0x180009d22  lea     r9, [rsp+11D0h+var_1188]
0x180009d27  xor     r8d, r8d
0x180009d2a  xor     edx, edx
0x180009d2c  mov     rcx, r14
0x180009d2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d34  mov     ebx, eax
0x180009d36  mov     ecx, ebx; this
0x180009d38  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180009d3d  test    ebx, ebx
0x180009d3f  jz      short loc_180009D4F
0x180009d41  mov     eax, r15d
0x180009d44  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180009d48  mov     [rsp+11D0h+var_1188], r15d
0x180009d4d  jmp     short loc_180009D53
0x180009d4f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180009d53  mov     r8d, eax; unsigned __int64
0x180009d56  mov     r9d, 1000h; unsigned __int64
0x180009d5c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180009d63  lea     rcx, [rsp+11D0h+var_1170]; this
0x180009d68  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180009d6d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180009d71  jnz     loc_180009F83
0x180009d77  mov     [rbp+10D0h+var_1130], r15
0x180009d7b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180009d82  mov     [rbp+10D0h+var_10B0], rax
0x180009d86  lea     rax, [rbp+10D0h+var_1130]
0x180009d8a  mov     [rbp+10D0h+var_10A8], rax
0x180009d8e  lea     rax, [rbp+10D0h+var_1128]
0x180009d92  mov     [rbp+10D0h+var_10A0], rax
0x180009d96  lea     rax, [rsp+11D0h+var_1170]
0x180009d9b  mov     [rbp+10D0h+var_1098], rax
0x180009d9f  lea     rax, [rbp+10D0h+var_10B0]
0x180009da3  mov     [rbp+10D0h+var_1048], rax
0x180009daa  lea     rax, [rbp+10D0h+var_10B8]
0x180009dae  mov     [rbp+10D0h+var_10C0], rax
0x180009db2  mov     rax, [rdi+18h]
0x180009db6  add     rax, 0Ah
0x180009dba  mov     [rsp+11D0h+var_1190], rax
0x180009dbf  movzx   eax, word ptr [rdi+2]
0x180009dc3  mov     [rbp+10D0h+var_1120], ax
0x180009dc7  mov     al, [rdi+4]
0x180009dca  mov     [rbp+10D0h+var_111E], al
0x180009dcd  mov     [rbp+10D0h+var_111C], r15d
0x180009dd1  mov     [rbp+10D0h+var_1118], r15w
0x180009dd6  xorps   xmm0, xmm0
0x180009dd9  movdqu  [rbp+10D0h+var_1110], xmm0
0x180009dde  movzx   eax, word ptr [rdi+6]
0x180009de2  mov     [rbp+10D0h+var_1100], ax
0x180009de6  mov     al, [rdi+8]
0x180009de9  mov     [rbp+10D0h+var_10FE], al
0x180009dec  mov     [rbp+10D0h+var_10FC], r15d
0x180009df0  mov     [rbp+10D0h+var_10F8], r15w
0x180009df5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180009dfa  jmp     loc_180009E92
0x180009dff  mov     ebx, r15d
0x180009e02  mov     esi, [rbp+10D0h+var_111C]
0x180009e05  test    esi, esi
0x180009e07  jz      loc_180009E92
0x180009e0d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180009e11  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009e15  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180009e1a  lea     rcx, [rbp+10D0h+var_1100]; this
0x180009e1e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009e23  test    al, al
0x180009e25  jz      short loc_180009E8F
0x180009e27  mov     eax, [rbp+10D0h+var_10FC]
0x180009e2a  mov     [rsp+11D0h+var_1180], eax
0x180009e2e  movzx   eax, [rbp+10D0h+var_10F8]
0x180009e32  mov     [rbp+10D0h+var_10E0], rax
0x180009e36  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180009e3a  mov     [rbp+10D0h+var_10D8], rax
0x180009e3e  movzx   eax, [rbp+10D0h+var_1118]
0x180009e42  mov     [rbp+10D0h+var_10D0], rax
0x180009e46  mov     [rbp+10D0h+var_10C8], r15
0x180009e4a  mov     rcx, [rbp+10D0h+var_1048]; this
0x180009e51  test    rcx, rcx
0x180009e54  jz      loc_180009FCE
0x180009e5a  mov     rax, [rcx]
0x180009e5d  lea     rdx, [rsp+11D0h+var_1180]
0x180009e62  mov     [rsp+11D0h+var_11A8], rdx
0x180009e67  lea     rdx, [rbp+10D0h+var_10E0]
0x180009e6b  mov     [rsp+11D0h+var_11B0], rdx
0x180009e70  lea     r9, [rbp+10D0h+var_10D8]
0x180009e74  lea     r8, [rbp+10D0h+var_10D0]
0x180009e78  lea     rdx, [rbp+10D0h+var_10C8]
0x180009e7c  mov     rax, [rax+20h]
0x180009e80  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009e85  test    al, al
0x180009e87  jz      short loc_180009EFF
0x180009e89  inc     ebx
0x180009e8b  cmp     ebx, esi
0x180009e8d  jb      short loc_180009E11
0x180009e8f  xor     r15d, r15d
0x180009e92  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009e96  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180009e9b  lea     rcx, [rbp+10D0h+var_1120]; this
0x180009e9f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009ea4  test    al, al
0x180009ea6  jnz     loc_180009DFF
0x180009eac  mov     rcx, [rbp+10D0h+var_1048]
0x180009eb3  test    rcx, rcx
0x180009eb6  jz      short loc_180009EC4
0x180009eb8  mov     rax, [rcx]
0x180009ebb  mov     rax, [rax+18h]
0x180009ebf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ec4  mov     bl, 1
0x180009ec6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180009eca  jz      short loc_180009F41
0x180009ecc  mov     eax, [rsp+11D0h+var_1188]
0x180009ed0  mov     rdx, [rsp+11D0h+var_1158]
0x180009ed5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009ed9  sub     r8d, edx
0x180009edc  mov     [rsp+11D0h+var_11A0], 1
0x180009ee4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180009ee8  mov     rcx, r14
0x180009eeb  call    wil_details_NtUpdateWnfStateData
0x180009ef0  cmp     eax, 0C0000001h
0x180009ef5  jnz     short loc_180009F1F
0x180009ef7  inc     r12
0x180009efa  mov     bl, r15b
0x180009efd  jmp     short loc_180009F4D
0x180009eff  mov     rcx, [rbp+10D0h+var_1048]
0x180009f06  xor     r15d, r15d
0x180009f09  test    rcx, rcx
0x180009f0c  jz      short loc_180009F1A
0x180009f0e  mov     rax, [rcx]
0x180009f11  mov     rax, [rax+18h]
0x180009f15  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009f1a  mov     bl, r15b
0x180009f1d  jmp     short loc_180009EC6
0x180009f1f  test    eax, eax
0x180009f21  jz      short loc_180009F41
0x180009f23  mov     rdx, [rsp+11D0h+var_1158]
0x180009f28  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009f2c  sub     r8d, edx
0x180009f2f  mov     [rsp+11D0h+var_11A0], r15d
0x180009f34  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180009f39  mov     rcx, r14
0x180009f3c  call    wil_details_NtUpdateWnfStateData
0x180009f41  add     r14, 8
0x180009f45  mov     rax, [rbp+10D0h+var_1130]
0x180009f49  mov     [rbp+10D0h+var_1128], rax
0x180009f4d  mov     rsi, [rbp+10D0h+lpMem]
0x180009f51  mov     [rbp+10D0h+lpMem], r15
0x180009f55  test    rsi, rsi
0x180009f58  jz      short loc_180009F6E
0x180009f5a  call    cs:__imp_GetProcessHeap
0x180009f60  mov     rcx, rax; hHeap
0x180009f63  mov     r8, rsi; lpMem
0x180009f66  xor     edx, edx; dwFlags
0x180009f68  call    cs:__imp_HeapFree
0x180009f6e  test    bl, bl
0x180009f70  jnz     short loc_180009FA4
0x180009f72  cmp     r14, r13
0x180009f75  jnb     short loc_180009FA4
0x180009f77  cmp     r12, 32h ; '2'
0x180009f7b  jb      loc_180009C46
0x180009f81  jmp     short loc_180009FA4
0x180009f83  mov     rbx, [rbp+10D0h+lpMem]
0x180009f87  mov     [rbp+10D0h+lpMem], r15
0x180009f8b  test    rbx, rbx
0x180009f8e  jz      short loc_180009FA4
0x180009f90  call    cs:__imp_GetProcessHeap
0x180009f96  mov     rcx, rax; hHeap
0x180009f99  mov     r8, rbx; lpMem
0x180009f9c  xor     edx, edx; dwFlags
0x180009f9e  call    cs:__imp_HeapFree
0x180009fa4  mov     rcx, [rbp+10D0h+var_40]
0x180009fab  xor     rcx, rsp; StackCookie
0x180009fae  call    __security_check_cookie
0x180009fb3  mov     rbx, [rsp+11D0h+arg_8]
0x180009fbb  add     rsp, 11A0h
0x180009fc2  pop     r15
0x180009fc4  pop     r14
0x180009fc6  pop     r13
0x180009fc8  pop     r12
0x180009fca  pop     rdi
0x180009fcb  pop     rsi
0x180009fcc  pop     rbp
0x180009fcd  retn
0x180009fce  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
