# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140011b70`
- end: `0x140011f45`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `981`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140011228`

## callees

- `0x140002310`
- `0x14000e394`
- `0x1400109f8`
- `0x140011120`
- `0x140011b70`
- `0x1400120e0`
- `0x140012f4c`
- `0x140021f90`
- `0x140024010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011c5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140011c5d`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011c46`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140011c46`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011ed9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011f0f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011ed9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140011f0f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011ecb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011f01`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011ecb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140011f01`

## string_xrefs

- `0x140011c3f`: `ntdll.dll`

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
0x140011b70  mov     [rsp-8+arg_8], rbx
0x140011b75  push    rbp
0x140011b76  push    rsi
0x140011b77  push    rdi
0x140011b78  push    r12
0x140011b7a  push    r13
0x140011b7c  push    r14
0x140011b7e  push    r15
0x140011b80  lea     rbp, [rsp-10A0h]
0x140011b88  mov     eax, 11A0h
0x140011b8d  call    _alloca_probe
0x140011b92  sub     rsp, rax
0x140011b95  mov     rax, cs:__security_cookie
0x140011b9c  xor     rax, rsp
0x140011b9f  mov     [rbp+10D0h+var_40], rax
0x140011ba6  mov     rdi, r8
0x140011ba9  mov     r14, rcx
0x140011bac  lea     r13, [rcx+rdx*8]
0x140011bb0  xor     r15d, r15d
0x140011bb3  mov     r12d, r15d
0x140011bb6  mov     [rbp+10D0h+var_1058], r15
0x140011bba  mov     cl, [rdi+8]
0x140011bbd  movzx   edx, word ptr [rdi+6]
0x140011bc1  movzx   eax, word ptr [rdi]
0x140011bc4  mov     [rbp+10D0h+var_10A0], ax
0x140011bc8  movzx   eax, word ptr [rdi+2]
0x140011bcc  mov     [rbp+10D0h+var_109E], ax
0x140011bd0  mov     al, [rdi+4]
0x140011bd3  mov     [rbp+10D0h+var_109C], al
0x140011bd6  mov     [rbp+10D0h+var_109A], dx
0x140011bda  mov     [rbp+10D0h+var_1098], cl
0x140011bdd  test    dx, dx
0x140011be0  jz      short loc_140011BFE
0x140011be2  mov     eax, edx
0x140011be4  cmp     cl, 1
0x140011be7  jnz     short loc_140011BEF
0x140011be9  add     rax, 2
0x140011bed  jmp     short loc_140011BF8
0x140011bef  cmp     cl, 2
0x140011bf2  jnz     short loc_140011BF8
0x140011bf4  add     rax, 4
0x140011bf8  mov     [rbp+10D0h+var_1090], rax
0x140011bfc  jmp     short loc_140011C02
0x140011bfe  mov     [rbp+10D0h+var_1090], r15
0x140011c02  mov     [rbp+10D0h+var_1088], r15
0x140011c06  xorps   xmm0, xmm0
0x140011c09  movdqa  [rbp+10D0h+var_1080], xmm0
0x140011c0e  mov     [rbp+10D0h+lpMem], r15
0x140011c12  mov     [rbp+10D0h+var_1068], 0
0x140011c18  mov     [rbp+10D0h+var_1066], r15b
0x140011c1c  mov     [rbp+10D0h+var_10B8], r15d
0x140011c20  mov     dword ptr [rbp+10D0h+var_10C0], 1000h
0x140011c27  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140011c2e  test    rax, rax
0x140011c31  jnz     short loc_140011C76
0x140011c33  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140011c3a  test    rax, rax
0x140011c3d  jnz     short loc_140011C53
0x140011c3f  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x140011c46  call    cs:__imp_GetModuleHandleW
0x140011c4c  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140011c53  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140011c5a  mov     rcx, rax; hModule
0x140011c5d  call    cs:__imp_GetProcAddress
0x140011c63  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140011c6a  test    rax, rax
0x140011c6d  jnz     short loc_140011C76
0x140011c6f  mov     ebx, 0C0000139h
0x140011c74  jmp     short loc_140011C9E
0x140011c76  lea     rcx, [rbp+10D0h+var_10C0]
0x140011c7a  mov     [rsp+11D0h+var_11A8], rcx
0x140011c7f  lea     rcx, [rbp+10D0h+var_1040]
0x140011c86  mov     [rsp+11D0h+var_11B0], rcx
0x140011c8b  lea     r9, [rbp+10D0h+var_10B8]
0x140011c8f  xor     r8d, r8d
0x140011c92  xor     edx, edx
0x140011c94  mov     rcx, r14
0x140011c97  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011c9c  mov     ebx, eax
0x140011c9e  mov     ecx, ebx; this
0x140011ca0  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x140011ca5  test    ebx, ebx
0x140011ca7  jz      short loc_140011CB5
0x140011ca9  mov     eax, r15d
0x140011cac  mov     dword ptr [rbp+10D0h+var_10C0], eax
0x140011caf  mov     [rbp+10D0h+var_10B8], r15d
0x140011cb3  jmp     short loc_140011CB8
0x140011cb5  mov     eax, dword ptr [rbp+10D0h+var_10C0]
0x140011cb8  mov     r8d, eax; unsigned __int64
0x140011cbb  mov     r9d, 1000h; unsigned __int64
0x140011cc1  lea     rdx, [rbp+10D0h+var_1040]; void *
0x140011cc8  lea     rcx, [rbp+10D0h+var_10A0]; this
0x140011ccc  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140011cd1  cmp     byte ptr [rbp+10D0h+var_1068+1], r15b
0x140011cd5  jnz     loc_140011EF4
0x140011cdb  mov     [rbp+10D0h+var_1060], r15
0x140011cdf  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x140011ce6  mov     [rbp+10D0h+var_1140], rax
0x140011cea  lea     rax, [rbp+10D0h+var_1060]
0x140011cee  mov     [rbp+10D0h+var_1138], rax
0x140011cf2  lea     rax, [rbp+10D0h+var_1058]
0x140011cf6  mov     [rbp+10D0h+var_1130], rax
0x140011cfa  lea     rax, [rbp+10D0h+var_10A0]
0x140011cfe  mov     [rbp+10D0h+var_1128], rax
0x140011d02  lea     rax, [rbp+10D0h+var_1140]
0x140011d06  mov     [rbp+10D0h+var_10D8], rax
0x140011d0a  lea     rax, [rbp+10D0h+var_1148]
0x140011d0e  mov     [rbp+10D0h+var_1150], rax
0x140011d12  mov     rax, [rdi+18h]
0x140011d16  add     rax, 0Ah
0x140011d1a  mov     [rbp+10D0h+var_10C0], rax
0x140011d1e  movzx   eax, word ptr [rdi+2]
0x140011d22  mov     [rsp+11D0h+var_1190], ax
0x140011d27  mov     al, [rdi+4]
0x140011d2a  mov     [rsp+11D0h+var_118E], al
0x140011d2e  mov     [rsp+11D0h+var_118C], r15d
0x140011d33  mov     [rsp+11D0h+var_1188], r15w
0x140011d39  xorps   xmm0, xmm0
0x140011d3c  movdqu  [rsp+11D0h+var_1180], xmm0
0x140011d42  movzx   eax, word ptr [rdi+6]
0x140011d46  mov     [rsp+11D0h+var_1170], ax
0x140011d4b  mov     al, [rdi+8]
0x140011d4e  mov     [rsp+11D0h+var_116E], al
0x140011d52  mov     [rsp+11D0h+var_116C], r15d
0x140011d57  mov     [rsp+11D0h+var_1168], r15w
0x140011d5d  movdqu  [rsp+11D0h+var_1160], xmm0
0x140011d63  jmp     loc_140011E0C
0x140011d68  mov     ebx, r15d
0x140011d6b  mov     esi, [rsp+11D0h+var_118C]
0x140011d6f  test    esi, esi
0x140011d71  jz      loc_140011E0C
0x140011d77  mov     r15, qword ptr [rsp+11D0h+var_1180+8]
0x140011d7c  mov     r8, [rdi+20h]; unsigned __int8 *
0x140011d80  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x140011d84  lea     rcx, [rsp+11D0h+var_1170]; this
0x140011d89  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140011d8e  test    al, al
0x140011d90  jz      short loc_140011E09
0x140011d92  mov     eax, [rsp+11D0h+var_116C]
0x140011d96  mov     [rbp+10D0h+var_10B0], eax
0x140011d99  movzx   eax, [rsp+11D0h+var_1168]
0x140011d9e  mov     [rbp+10D0h+var_1050], rax
0x140011da5  mov     rax, qword ptr [rsp+11D0h+var_1160+8]
0x140011daa  mov     [rbp+10D0h+var_10D0], rax
0x140011dae  movzx   eax, [rsp+11D0h+var_1188]
0x140011db3  mov     [rbp+10D0h+var_1048], rax
0x140011dba  mov     [rbp+10D0h+var_10C8], r15
0x140011dbe  mov     rcx, [rbp+10D0h+var_10D8]; this
0x140011dc2  test    rcx, rcx
0x140011dc5  jz      loc_140011F3F
0x140011dcb  mov     rax, [rcx]
0x140011dce  lea     rdx, [rbp+10D0h+var_10B0]
0x140011dd2  mov     [rsp+11D0h+var_11A8], rdx
0x140011dd7  lea     rdx, [rbp+10D0h+var_1050]
0x140011dde  mov     [rsp+11D0h+var_11B0], rdx
0x140011de3  lea     r9, [rbp+10D0h+var_10D0]
0x140011de7  lea     r8, [rbp+10D0h+var_1048]
0x140011dee  lea     rdx, [rbp+10D0h+var_10C8]
0x140011df2  mov     rax, [rax+20h]
0x140011df6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011dfb  test    al, al
0x140011dfd  jz      short loc_140011E74
0x140011dff  inc     ebx
0x140011e01  cmp     ebx, esi
0x140011e03  jb      loc_140011D7C
0x140011e09  xor     r15d, r15d
0x140011e0c  mov     r8, [rdi+20h]; unsigned __int8 *
0x140011e10  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x140011e14  lea     rcx, [rsp+11D0h+var_1190]; this
0x140011e19  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140011e1e  test    al, al
0x140011e20  jnz     loc_140011D68
0x140011e26  mov     rcx, [rbp+10D0h+var_10D8]
0x140011e2a  test    rcx, rcx
0x140011e2d  jz      short loc_140011E3B
0x140011e2f  mov     rax, [rcx]
0x140011e32  mov     rax, [rax+18h]
0x140011e36  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e3b  mov     bl, 1
0x140011e3d  cmp     byte ptr [rbp+10D0h+var_1068], r15b
0x140011e41  jz      short loc_140011EB2
0x140011e43  mov     eax, [rbp+10D0h+var_10B8]
0x140011e46  mov     rdx, [rbp+10D0h+var_1088]
0x140011e4a  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x140011e4e  sub     r8d, edx
0x140011e51  mov     [rsp+11D0h+var_11A0], 1
0x140011e59  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x140011e5d  mov     rcx, r14
0x140011e60  call    wil_details_NtUpdateWnfStateData
0x140011e65  cmp     eax, 0C0000001h
0x140011e6a  jnz     short loc_140011E91
0x140011e6c  inc     r12
0x140011e6f  mov     bl, r15b
0x140011e72  jmp     short loc_140011EBE
0x140011e74  mov     rcx, [rbp+10D0h+var_10D8]
0x140011e78  xor     r15d, r15d
0x140011e7b  test    rcx, rcx
0x140011e7e  jz      short loc_140011E8C
0x140011e80  mov     rax, [rcx]
0x140011e83  mov     rax, [rax+18h]
0x140011e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140011e8c  mov     bl, r15b
0x140011e8f  jmp     short loc_140011E3D
0x140011e91  test    eax, eax
0x140011e93  jz      short loc_140011EB2
0x140011e95  mov     rdx, [rbp+10D0h+var_1088]
0x140011e99  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x140011e9d  sub     r8d, edx
0x140011ea0  mov     [rsp+11D0h+var_11A0], r15d
0x140011ea5  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x140011eaa  mov     rcx, r14
0x140011ead  call    wil_details_NtUpdateWnfStateData
0x140011eb2  add     r14, 8
0x140011eb6  mov     rax, [rbp+10D0h+var_1060]
0x140011eba  mov     [rbp+10D0h+var_1058], rax
0x140011ebe  mov     rsi, [rbp+10D0h+lpMem]
0x140011ec2  mov     [rbp+10D0h+lpMem], r15
0x140011ec6  test    rsi, rsi
0x140011ec9  jz      short loc_140011EDF
0x140011ecb  call    cs:__imp_GetProcessHeap
0x140011ed1  mov     rcx, rax; hHeap
0x140011ed4  mov     r8, rsi; lpMem
0x140011ed7  xor     edx, edx; dwFlags
0x140011ed9  call    cs:__imp_HeapFree
0x140011edf  test    bl, bl
0x140011ee1  jnz     short loc_140011F15
0x140011ee3  cmp     r14, r13
0x140011ee6  jnb     short loc_140011F15
0x140011ee8  cmp     r12, 32h ; '2'
0x140011eec  jb      loc_140011BBA
0x140011ef2  jmp     short loc_140011F15
0x140011ef4  mov     rbx, [rbp+10D0h+lpMem]
0x140011ef8  mov     [rbp+10D0h+lpMem], r15
0x140011efc  test    rbx, rbx
0x140011eff  jz      short loc_140011F15
0x140011f01  call    cs:__imp_GetProcessHeap
0x140011f07  mov     rcx, rax; hHeap
0x140011f0a  mov     r8, rbx; lpMem
0x140011f0d  xor     edx, edx; dwFlags
0x140011f0f  call    cs:__imp_HeapFree
0x140011f15  mov     rcx, [rbp+10D0h+var_40]
0x140011f1c  xor     rcx, rsp; StackCookie
0x140011f1f  call    __security_check_cookie
0x140011f24  mov     rbx, [rsp+11D0h+arg_8]
0x140011f2c  add     rsp, 11A0h
0x140011f33  pop     r15
0x140011f35  pop     r14
0x140011f37  pop     r13
0x140011f39  pop     r12
0x140011f3b  pop     rdi
0x140011f3c  pop     rsi
0x140011f3d  pop     rbp
0x140011f3e  retn
0x140011f3f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
