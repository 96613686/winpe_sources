# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180009ad8`
- end: `0x180009eb0`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180008fb8`

## callees

- `0x180002590`
- `0x1800086c4`
- `0x180008e70`
- `0x180009ad8`
- `0x18000ae24`
- `0x18000c5c4`
- `0x18000d348`
- `0x1800300f0`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e7a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e44`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009e7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e6c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e36`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009e6c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009bb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180009bb8`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009bcf`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180009bcf`

## string_xrefs

- `0x180009bb1`: `ntdll.dll`

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
0x180009ad8  mov     [rsp-8+arg_8], rbx
0x180009add  push    rbp
0x180009ade  push    rsi
0x180009adf  push    rdi
0x180009ae0  push    r12
0x180009ae2  push    r13
0x180009ae4  push    r14
0x180009ae6  push    r15
0x180009ae8  lea     rbp, [rsp-10A0h]
0x180009af0  mov     eax, 11A0h
0x180009af5  call    _alloca_probe
0x180009afa  sub     rsp, rax
0x180009afd  mov     rax, cs:__security_cookie
0x180009b04  xor     rax, rsp
0x180009b07  mov     [rbp+10D0h+var_40], rax
0x180009b0e  mov     rdi, r8
0x180009b11  mov     r14, rcx
0x180009b14  lea     r13, [rcx+rdx*8]
0x180009b18  xor     r15d, r15d
0x180009b1b  mov     r12d, r15d
0x180009b1e  mov     [rbp+10D0h+var_1128], r15
0x180009b22  mov     cl, [rdi+8]
0x180009b25  movzx   edx, word ptr [rdi+6]
0x180009b29  movzx   eax, word ptr [rdi]
0x180009b2c  mov     [rsp+11D0h+var_1170], ax
0x180009b31  movzx   eax, word ptr [rdi+2]
0x180009b35  mov     [rsp+11D0h+var_116E], ax
0x180009b3a  mov     al, [rdi+4]
0x180009b3d  mov     [rsp+11D0h+var_116C], al
0x180009b41  mov     [rsp+11D0h+var_116A], dx
0x180009b46  mov     [rsp+11D0h+var_1168], cl
0x180009b4a  test    dx, dx
0x180009b4d  jz      short loc_180009B6C
0x180009b4f  mov     eax, edx
0x180009b51  cmp     cl, 1
0x180009b54  jnz     short loc_180009B5C
0x180009b56  add     rax, 2
0x180009b5a  jmp     short loc_180009B65
0x180009b5c  cmp     cl, 2
0x180009b5f  jnz     short loc_180009B65
0x180009b61  add     rax, 4
0x180009b65  mov     [rsp+11D0h+var_1160], rax
0x180009b6a  jmp     short loc_180009B71
0x180009b6c  mov     [rsp+11D0h+var_1160], r15
0x180009b71  mov     [rsp+11D0h+var_1158], r15
0x180009b76  xorps   xmm0, xmm0
0x180009b79  movdqa  [rbp+10D0h+var_1150], xmm0
0x180009b7e  mov     [rbp+10D0h+lpMem], r15
0x180009b82  mov     [rbp+10D0h+var_1138], 0
0x180009b88  mov     [rbp+10D0h+var_1136], r15b
0x180009b8c  mov     [rsp+11D0h+var_1188], r15d
0x180009b91  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180009b99  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180009ba0  test    rax, rax
0x180009ba3  jnz     short loc_180009BE8
0x180009ba5  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009bac  test    rax, rax
0x180009baf  jnz     short loc_180009BC5
0x180009bb1  lea     rcx, ModuleName; "ntdll.dll"
0x180009bb8  call    cs:__imp_GetModuleHandleW
0x180009bbe  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180009bc5  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009bcc  mov     rcx, rax; hModule
0x180009bcf  call    cs:__imp_GetProcAddress
0x180009bd5  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009bdc  test    rax, rax
0x180009bdf  jnz     short loc_180009BE8
0x180009be1  mov     ebx, 0C0000139h
0x180009be6  jmp     short loc_180009C12
0x180009be8  lea     rcx, [rsp+11D0h+var_1190]
0x180009bed  mov     [rsp+11D0h+var_11A8], rcx
0x180009bf2  lea     rcx, [rbp+10D0h+var_1040]
0x180009bf9  mov     [rsp+11D0h+var_11B0], rcx
0x180009bfe  lea     r9, [rsp+11D0h+var_1188]
0x180009c03  xor     r8d, r8d
0x180009c06  xor     edx, edx
0x180009c08  mov     rcx, r14
0x180009c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c10  mov     ebx, eax
0x180009c12  mov     ecx, ebx; this
0x180009c14  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180009c19  test    ebx, ebx
0x180009c1b  jz      short loc_180009C2B
0x180009c1d  mov     eax, r15d
0x180009c20  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180009c24  mov     [rsp+11D0h+var_1188], r15d
0x180009c29  jmp     short loc_180009C2F
0x180009c2b  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180009c2f  mov     r8d, eax; unsigned __int64
0x180009c32  mov     r9d, 1000h; unsigned __int64
0x180009c38  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180009c3f  lea     rcx, [rsp+11D0h+var_1170]; this
0x180009c44  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180009c49  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180009c4d  jnz     loc_180009E5F
0x180009c53  mov     [rbp+10D0h+var_1130], r15
0x180009c57  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180009c5e  mov     [rbp+10D0h+var_10B0], rax
0x180009c62  lea     rax, [rbp+10D0h+var_1130]
0x180009c66  mov     [rbp+10D0h+var_10A8], rax
0x180009c6a  lea     rax, [rbp+10D0h+var_1128]
0x180009c6e  mov     [rbp+10D0h+var_10A0], rax
0x180009c72  lea     rax, [rsp+11D0h+var_1170]
0x180009c77  mov     [rbp+10D0h+var_1098], rax
0x180009c7b  lea     rax, [rbp+10D0h+var_10B0]
0x180009c7f  mov     [rbp+10D0h+var_1048], rax
0x180009c86  lea     rax, [rbp+10D0h+var_10B8]
0x180009c8a  mov     [rbp+10D0h+var_10C0], rax
0x180009c8e  mov     rax, [rdi+18h]
0x180009c92  add     rax, 0Ah
0x180009c96  mov     [rsp+11D0h+var_1190], rax
0x180009c9b  movzx   eax, word ptr [rdi+2]
0x180009c9f  mov     [rbp+10D0h+var_1120], ax
0x180009ca3  mov     al, [rdi+4]
0x180009ca6  mov     [rbp+10D0h+var_111E], al
0x180009ca9  mov     [rbp+10D0h+var_111C], r15d
0x180009cad  mov     [rbp+10D0h+var_1118], r15w
0x180009cb2  xorps   xmm0, xmm0
0x180009cb5  movdqu  [rbp+10D0h+var_1110], xmm0
0x180009cba  movzx   eax, word ptr [rdi+6]
0x180009cbe  mov     [rbp+10D0h+var_1100], ax
0x180009cc2  mov     al, [rdi+8]
0x180009cc5  mov     [rbp+10D0h+var_10FE], al
0x180009cc8  mov     [rbp+10D0h+var_10FC], r15d
0x180009ccc  mov     [rbp+10D0h+var_10F8], r15w
0x180009cd1  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180009cd6  jmp     loc_180009D6E
0x180009cdb  mov     ebx, r15d
0x180009cde  mov     esi, [rbp+10D0h+var_111C]
0x180009ce1  test    esi, esi
0x180009ce3  jz      loc_180009D6E
0x180009ce9  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180009ced  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009cf1  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180009cf6  lea     rcx, [rbp+10D0h+var_1100]; this
0x180009cfa  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009cff  test    al, al
0x180009d01  jz      short loc_180009D6B
0x180009d03  mov     eax, [rbp+10D0h+var_10FC]
0x180009d06  mov     [rsp+11D0h+var_1180], eax
0x180009d0a  movzx   eax, [rbp+10D0h+var_10F8]
0x180009d0e  mov     [rbp+10D0h+var_10E0], rax
0x180009d12  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180009d16  mov     [rbp+10D0h+var_10D8], rax
0x180009d1a  movzx   eax, [rbp+10D0h+var_1118]
0x180009d1e  mov     [rbp+10D0h+var_10D0], rax
0x180009d22  mov     [rbp+10D0h+var_10C8], r15
0x180009d26  mov     rcx, [rbp+10D0h+var_1048]; this
0x180009d2d  test    rcx, rcx
0x180009d30  jz      loc_180009EAA
0x180009d36  mov     rax, [rcx]
0x180009d39  lea     rdx, [rsp+11D0h+var_1180]
0x180009d3e  mov     [rsp+11D0h+var_11A8], rdx
0x180009d43  lea     rdx, [rbp+10D0h+var_10E0]
0x180009d47  mov     [rsp+11D0h+var_11B0], rdx
0x180009d4c  lea     r9, [rbp+10D0h+var_10D8]
0x180009d50  lea     r8, [rbp+10D0h+var_10D0]
0x180009d54  lea     rdx, [rbp+10D0h+var_10C8]
0x180009d58  mov     rax, [rax+20h]
0x180009d5c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d61  test    al, al
0x180009d63  jz      short loc_180009DDB
0x180009d65  inc     ebx
0x180009d67  cmp     ebx, esi
0x180009d69  jb      short loc_180009CED
0x180009d6b  xor     r15d, r15d
0x180009d6e  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009d72  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180009d77  lea     rcx, [rbp+10D0h+var_1120]; this
0x180009d7b  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009d80  test    al, al
0x180009d82  jnz     loc_180009CDB
0x180009d88  mov     rcx, [rbp+10D0h+var_1048]
0x180009d8f  test    rcx, rcx
0x180009d92  jz      short loc_180009DA0
0x180009d94  mov     rax, [rcx]
0x180009d97  mov     rax, [rax+18h]
0x180009d9b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009da0  mov     bl, 1
0x180009da2  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180009da6  jz      short loc_180009E1D
0x180009da8  mov     eax, [rsp+11D0h+var_1188]
0x180009dac  mov     rdx, [rsp+11D0h+var_1158]
0x180009db1  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009db5  sub     r8d, edx
0x180009db8  mov     [rsp+11D0h+var_11A0], 1
0x180009dc0  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180009dc4  mov     rcx, r14
0x180009dc7  call    wil_details_NtUpdateWnfStateData
0x180009dcc  cmp     eax, 0C0000001h
0x180009dd1  jnz     short loc_180009DFB
0x180009dd3  inc     r12
0x180009dd6  mov     bl, r15b
0x180009dd9  jmp     short loc_180009E29
0x180009ddb  mov     rcx, [rbp+10D0h+var_1048]
0x180009de2  xor     r15d, r15d
0x180009de5  test    rcx, rcx
0x180009de8  jz      short loc_180009DF6
0x180009dea  mov     rax, [rcx]
0x180009ded  mov     rax, [rax+18h]
0x180009df1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009df6  mov     bl, r15b
0x180009df9  jmp     short loc_180009DA2
0x180009dfb  test    eax, eax
0x180009dfd  jz      short loc_180009E1D
0x180009dff  mov     rdx, [rsp+11D0h+var_1158]
0x180009e04  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009e08  sub     r8d, edx
0x180009e0b  mov     [rsp+11D0h+var_11A0], r15d
0x180009e10  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180009e15  mov     rcx, r14
0x180009e18  call    wil_details_NtUpdateWnfStateData
0x180009e1d  add     r14, 8
0x180009e21  mov     rax, [rbp+10D0h+var_1130]
0x180009e25  mov     [rbp+10D0h+var_1128], rax
0x180009e29  mov     rsi, [rbp+10D0h+lpMem]
0x180009e2d  mov     [rbp+10D0h+lpMem], r15
0x180009e31  test    rsi, rsi
0x180009e34  jz      short loc_180009E4A
0x180009e36  call    cs:__imp_GetProcessHeap
0x180009e3c  mov     rcx, rax; hHeap
0x180009e3f  mov     r8, rsi; lpMem
0x180009e42  xor     edx, edx; dwFlags
0x180009e44  call    cs:__imp_HeapFree
0x180009e4a  test    bl, bl
0x180009e4c  jnz     short loc_180009E80
0x180009e4e  cmp     r14, r13
0x180009e51  jnb     short loc_180009E80
0x180009e53  cmp     r12, 32h ; '2'
0x180009e57  jb      loc_180009B22
0x180009e5d  jmp     short loc_180009E80
0x180009e5f  mov     rbx, [rbp+10D0h+lpMem]
0x180009e63  mov     [rbp+10D0h+lpMem], r15
0x180009e67  test    rbx, rbx
0x180009e6a  jz      short loc_180009E80
0x180009e6c  call    cs:__imp_GetProcessHeap
0x180009e72  mov     rcx, rax; hHeap
0x180009e75  mov     r8, rbx; lpMem
0x180009e78  xor     edx, edx; dwFlags
0x180009e7a  call    cs:__imp_HeapFree
0x180009e80  mov     rcx, [rbp+10D0h+var_40]
0x180009e87  xor     rcx, rsp; StackCookie
0x180009e8a  call    __security_check_cookie
0x180009e8f  mov     rbx, [rsp+11D0h+arg_8]
0x180009e97  add     rsp, 11A0h
0x180009e9e  pop     r15
0x180009ea0  pop     r14
0x180009ea2  pop     r13
0x180009ea4  pop     r12
0x180009ea6  pop     rdi
0x180009ea7  pop     rsi
0x180009ea8  pop     rbp
0x180009ea9  retn
0x180009eaa  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
