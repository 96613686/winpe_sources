# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180007f30`
- end: `0x1800082f5`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `965`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800073d8`

## callees

- `0x180006ec4`
- `0x1800072cc`
- `0x180007f30`
- `0x180008b24`
- `0x18000ab0c`
- `0x18000be00`
- `0x18000c610`
- `0x18000c6d0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000801c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000801c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008005`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008005`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008288`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800082bf`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008288`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800082bf`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000827a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082b1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000827a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800082b1`

## string_xrefs

- `0x180007ffe`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v5; // r14
  wil::details_abi *v6; // r12
  unsigned __int64 v7; // r15
  char v8; // cl
  unsigned int v9; // edx
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // edi
  unsigned int v15; // eax
  int v16; // edi
  int v17; // r9d
  char v18; // di
  int updated; // eax
  int v20; // r9d
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  __int64 *v25; // [rsp+20h] [rbp-E0h]
  _QWORD v26[13]; // [rsp+50h] [rbp-B0h] BYREF
  wil::details::in1diag3 *v27; // [rsp+B8h] [rbp-48h]
  __int16 v28; // [rsp+C0h] [rbp-40h] BYREF
  char v29; // [rsp+C2h] [rbp-3Eh]
  unsigned int v30; // [rsp+C4h] [rbp-3Ch]
  unsigned __int16 v31; // [rsp+C8h] [rbp-38h]
  __int128 v32; // [rsp+D0h] [rbp-30h]
  __int16 v33; // [rsp+E0h] [rbp-20h] BYREF
  char v34; // [rsp+E2h] [rbp-1Eh]
  int v35; // [rsp+E4h] [rbp-1Ch]
  unsigned __int16 v36; // [rsp+E8h] [rbp-18h]
  __int128 v37; // [rsp+F0h] [rbp-10h]
  __int64 v38; // [rsp+100h] [rbp+0h] BYREF
  __int64 v39; // [rsp+108h] [rbp+8h] BYREF
  unsigned __int8 *v40; // [rsp+110h] [rbp+10h] BYREF
  _DWORD v41[6]; // [rsp+118h] [rbp+18h] BYREF
  _WORD v42[2]; // [rsp+130h] [rbp+30h] BYREF
  char v43; // [rsp+134h] [rbp+34h]
  __int16 v44; // [rsp+136h] [rbp+36h]
  char v45; // [rsp+138h] [rbp+38h]
  __int64 v46; // [rsp+140h] [rbp+40h]
  __int64 v47; // [rsp+148h] [rbp+48h]
  __int128 v48; // [rsp+150h] [rbp+50h]
  LPVOID lpMem; // [rsp+160h] [rbp+60h]
  __int16 v50; // [rsp+168h] [rbp+68h]
  char v51; // [rsp+16Ah] [rbp+6Ah]
  __int64 v52; // [rsp+170h] [rbp+70h] BYREF
  __int64 v53; // [rsp+178h] [rbp+78h] BYREF
  __int64 v54; // [rsp+180h] [rbp+80h] BYREF
  __int64 v55; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v56[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v53 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v42[0] = *(_WORD *)a3;
    v42[1] = *(_WORD *)(a3 + 2);
    v43 = *(_BYTE *)(a3 + 4);
    v44 = v9;
    v45 = v8;
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
      v46 = v10;
    }
    else
    {
      v46 = 0;
    }
    v47 = 0;
    v48 = 0;
    lpMem = 0;
    v50 = 0;
    v51 = 0;
    v41[0] = 0;
    LODWORD(v40) = 4096;
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
      v25 = (__int64 *)v56;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v5, 0, 0, v41);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v40) = 0;
      v41[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v40;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v42, v56, v15, 0x1000u);
    if ( HIBYTE(v50) )
      break;
    v52 = 0;
    v26[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v26[1] = &v52;
    v26[2] = &v53;
    v26[3] = v42;
    v27 = (wil::details::in1diag3 *)v26;
    v40 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
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
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v28,
              &v40,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      if ( v30 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v33,
                  &v40,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v41[2] = v35;
          v54 = v36;
          v38 = *((_QWORD *)&v37 + 1);
          v55 = v31;
          v39 = *((_QWORD *)&v32 + 1);
          if ( !v27 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v25 = &v54;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v27 + 32LL))(
                  v27,
                  &v39,
                  &v55,
                  &v38) )
          {
            if ( v27 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v27 + 24LL))(v27);
            v18 = 0;
            goto LABEL_29;
          }
          if ( ++v16 >= v30 )
            goto LABEL_25;
        }
      }
    }
    if ( v27 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v27 + 24LL))(v27);
    v18 = 1;
LABEL_29:
    if ( !(_BYTE)v50 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v5, v47, (int)v48 - (int)v47, v17, (_DWORD)v25, v41[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v5, v47, v48 - v47, v20, (_DWORD)v25, 0, 0);
LABEL_37:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v53 = v52;
      goto LABEL_38;
    }
    ++v7;
    v18 = 0;
LABEL_38:
    v21 = lpMem;
    lpMem = 0;
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
    if ( v18 || v5 >= v6 || v7 >= 0x32 )
      return;
  }
  v23 = lpMem;
  lpMem = 0;
  if ( v23 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v23);
  }
}

```

## disassembly

```asm
0x180007f30  mov     [rsp-8+arg_8], rbx
0x180007f35  push    rbp
0x180007f36  push    rsi
0x180007f37  push    rdi
0x180007f38  push    r12
0x180007f3a  push    r13
0x180007f3c  push    r14
0x180007f3e  push    r15
0x180007f40  lea     rbp, [rsp-10A0h]
0x180007f48  mov     eax, 11A0h
0x180007f4d  call    _alloca_probe
0x180007f52  sub     rsp, rax
0x180007f55  mov     rax, cs:__security_cookie
0x180007f5c  xor     rax, rsp
0x180007f5f  mov     [rbp+10D0h+var_40], rax
0x180007f66  mov     rbx, r8
0x180007f69  mov     r14, rcx
0x180007f6c  lea     r12, [rcx+rdx*8]
0x180007f70  xor     r13d, r13d
0x180007f73  mov     r15d, r13d
0x180007f76  mov     [rbp+10D0h+var_1058], r13
0x180007f7a  mov     cl, [rbx+8]
0x180007f7d  movzx   edx, word ptr [rbx+6]
0x180007f81  movzx   eax, word ptr [rbx]
0x180007f84  mov     [rbp+10D0h+var_10A0], ax
0x180007f88  movzx   eax, word ptr [rbx+2]
0x180007f8c  mov     [rbp+10D0h+var_109E], ax
0x180007f90  mov     al, [rbx+4]
0x180007f93  mov     [rbp+10D0h+var_109C], al
0x180007f96  mov     [rbp+10D0h+var_109A], dx
0x180007f9a  mov     [rbp+10D0h+var_1098], cl
0x180007f9d  test    dx, dx
0x180007fa0  jz      short loc_180007FBE
0x180007fa2  mov     eax, edx
0x180007fa4  cmp     cl, 1
0x180007fa7  jnz     short loc_180007FAF
0x180007fa9  add     rax, 2
0x180007fad  jmp     short loc_180007FB8
0x180007faf  cmp     cl, 2
0x180007fb2  jnz     short loc_180007FB8
0x180007fb4  add     rax, 4
0x180007fb8  mov     [rbp+10D0h+var_1090], rax
0x180007fbc  jmp     short loc_180007FC2
0x180007fbe  mov     [rbp+10D0h+var_1090], r13
0x180007fc2  mov     [rbp+10D0h+var_1088], r13
0x180007fc6  xorps   xmm0, xmm0
0x180007fc9  movdqa  [rbp+10D0h+var_1080], xmm0
0x180007fce  mov     [rbp+10D0h+lpMem], r13
0x180007fd2  mov     [rbp+10D0h+var_1068], r13w
0x180007fd7  mov     [rbp+10D0h+var_1066], r13b
0x180007fdb  mov     [rbp+10D0h+var_10B8], r13d
0x180007fdf  mov     dword ptr [rbp+10D0h+var_10C0], 1000h
0x180007fe6  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180007fed  test    rax, rax
0x180007ff0  jnz     short loc_180008035
0x180007ff2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007ff9  test    rax, rax
0x180007ffc  jnz     short loc_180008012
0x180007ffe  lea     rcx, ModuleName; "ntdll.dll"
0x180008005  call    cs:__imp_GetModuleHandleW
0x18000800b  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008012  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008019  mov     rcx, rax; hModule
0x18000801c  call    cs:__imp_GetProcAddress
0x180008022  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008029  test    rax, rax
0x18000802c  jnz     short loc_180008035
0x18000802e  mov     edi, 0C0000139h
0x180008033  jmp     short loc_18000805D
0x180008035  lea     rcx, [rbp+10D0h+var_10C0]
0x180008039  mov     [rsp+11D0h+var_11A8], rcx
0x18000803e  lea     rcx, [rbp+10D0h+var_1040]
0x180008045  mov     [rsp+11D0h+var_11B0], rcx
0x18000804a  lea     r9, [rbp+10D0h+var_10B8]
0x18000804e  xor     r8d, r8d
0x180008051  xor     edx, edx
0x180008053  mov     rcx, r14
0x180008056  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000805b  mov     edi, eax
0x18000805d  mov     ecx, edi; this
0x18000805f  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180008064  test    edi, edi
0x180008066  jz      short loc_180008074
0x180008068  mov     eax, r13d
0x18000806b  mov     dword ptr [rbp+10D0h+var_10C0], eax
0x18000806e  mov     [rbp+10D0h+var_10B8], r13d
0x180008072  jmp     short loc_180008077
0x180008074  mov     eax, dword ptr [rbp+10D0h+var_10C0]
0x180008077  mov     r8d, eax; unsigned __int64
0x18000807a  mov     r9d, 1000h; unsigned __int64
0x180008080  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180008087  lea     rcx, [rbp+10D0h+var_10A0]; this
0x18000808b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180008090  cmp     byte ptr [rbp+10D0h+var_1068+1], r13b
0x180008094  jnz     loc_1800082A4
0x18000809a  mov     [rbp+10D0h+var_1060], r13
0x18000809e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800080a5  mov     [rsp+11D0h+var_1180], rax
0x1800080aa  lea     rax, [rbp+10D0h+var_1060]
0x1800080ae  mov     [rsp+11D0h+var_1178], rax
0x1800080b3  lea     rax, [rbp+10D0h+var_1058]
0x1800080b7  mov     [rsp+11D0h+var_1170], rax
0x1800080bc  lea     rax, [rbp+10D0h+var_10A0]
0x1800080c0  mov     [rsp+11D0h+var_1168], rax
0x1800080c5  lea     rax, [rsp+11D0h+var_1180]
0x1800080ca  mov     [rbp+10D0h+var_1118], rax
0x1800080ce  lea     rax, [rsp+11D0h+var_1188]
0x1800080d3  mov     [rsp+11D0h+var_1190], rax
0x1800080d8  mov     rax, [rbx+18h]
0x1800080dc  add     rax, 0Ah
0x1800080e0  mov     [rbp+10D0h+var_10C0], rax
0x1800080e4  movzx   eax, word ptr [rbx+2]
0x1800080e8  mov     [rbp+10D0h+var_1110], ax
0x1800080ec  mov     al, [rbx+4]
0x1800080ef  mov     [rbp+10D0h+var_110E], al
0x1800080f2  mov     [rbp+10D0h+var_110C], r13d
0x1800080f6  mov     [rbp+10D0h+var_1108], r13w
0x1800080fb  xorps   xmm0, xmm0
0x1800080fe  movdqu  [rbp+10D0h+var_1100], xmm0
0x180008103  movzx   eax, word ptr [rbx+6]
0x180008107  mov     [rbp+10D0h+var_10F0], ax
0x18000810b  mov     al, [rbx+8]
0x18000810e  mov     [rbp+10D0h+var_10EE], al
0x180008111  mov     [rbp+10D0h+var_10EC], r13d
0x180008115  mov     [rbp+10D0h+var_10E8], r13w
0x18000811a  movdqu  [rbp+10D0h+var_10E0], xmm0
0x18000811f  jmp     loc_1800081BE
0x180008124  mov     edi, r13d
0x180008127  cmp     [rbp+10D0h+var_110C], r13d
0x18000812b  jbe     loc_1800081BE
0x180008131  mov     r8, [rbx+20h]; unsigned __int8 *
0x180008135  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x180008139  lea     rcx, [rbp+10D0h+var_10F0]; this
0x18000813d  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008142  test    al, al
0x180008144  jz      short loc_1800081BE
0x180008146  mov     eax, [rbp+10D0h+var_10EC]
0x180008149  mov     [rbp+10D0h+var_10B0], eax
0x18000814c  movzx   eax, [rbp+10D0h+var_10E8]
0x180008150  mov     [rbp+10D0h+var_1050], rax
0x180008157  mov     rax, qword ptr [rbp+10D0h+var_10E0+8]
0x18000815b  mov     [rbp+10D0h+var_10D0], rax
0x18000815f  movzx   eax, [rbp+10D0h+var_1108]
0x180008163  mov     [rbp+10D0h+var_1048], rax
0x18000816a  mov     rax, qword ptr [rbp+10D0h+var_1100+8]
0x18000816e  mov     [rbp+10D0h+var_10C8], rax
0x180008172  mov     rcx, [rbp+10D0h+var_1118]; this
0x180008176  test    rcx, rcx
0x180008179  jz      loc_1800082EF
0x18000817f  mov     rax, [rcx]
0x180008182  lea     rdx, [rbp+10D0h+var_10B0]
0x180008186  mov     [rsp+11D0h+var_11A8], rdx
0x18000818b  lea     rdx, [rbp+10D0h+var_1050]
0x180008192  mov     [rsp+11D0h+var_11B0], rdx
0x180008197  lea     r9, [rbp+10D0h+var_10D0]
0x18000819b  lea     r8, [rbp+10D0h+var_1048]
0x1800081a2  lea     rdx, [rbp+10D0h+var_10C8]
0x1800081a6  mov     rax, [rax+20h]
0x1800081aa  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081af  test    al, al
0x1800081b1  jz      short loc_180008226
0x1800081b3  inc     edi
0x1800081b5  cmp     edi, [rbp+10D0h+var_110C]
0x1800081b8  jb      loc_180008131
0x1800081be  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800081c2  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x1800081c6  lea     rcx, [rbp+10D0h+var_1110]; this
0x1800081ca  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800081cf  test    al, al
0x1800081d1  jnz     loc_180008124
0x1800081d7  mov     rcx, [rbp+10D0h+var_1118]
0x1800081db  test    rcx, rcx
0x1800081de  jz      short loc_1800081EC
0x1800081e0  mov     rax, [rcx]
0x1800081e3  mov     rax, [rax+18h]
0x1800081e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081ec  mov     dil, 1
0x1800081ef  cmp     byte ptr [rbp+10D0h+var_1068], r13b
0x1800081f3  jz      short loc_180008261
0x1800081f5  mov     eax, [rbp+10D0h+var_10B8]
0x1800081f8  mov     rdx, [rbp+10D0h+var_1088]
0x1800081fc  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x180008200  sub     r8d, edx
0x180008203  mov     [rsp+11D0h+var_11A0], 1
0x18000820b  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000820f  mov     rcx, r14
0x180008212  call    wil_details_NtUpdateWnfStateData
0x180008217  cmp     eax, 0C0000001h
0x18000821c  jnz     short loc_180008240
0x18000821e  inc     r15
0x180008221  mov     dil, r13b
0x180008224  jmp     short loc_18000826D
0x180008226  mov     rcx, [rbp+10D0h+var_1118]
0x18000822a  test    rcx, rcx
0x18000822d  jz      short loc_18000823B
0x18000822f  mov     rax, [rcx]
0x180008232  mov     rax, [rax+18h]
0x180008236  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000823b  mov     dil, r13b
0x18000823e  jmp     short loc_1800081EF
0x180008240  test    eax, eax
0x180008242  jz      short loc_180008261
0x180008244  mov     rdx, [rbp+10D0h+var_1088]
0x180008248  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x18000824c  sub     r8d, edx
0x18000824f  mov     [rsp+11D0h+var_11A0], r13d
0x180008254  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x180008259  mov     rcx, r14
0x18000825c  call    wil_details_NtUpdateWnfStateData
0x180008261  add     r14, 8
0x180008265  mov     rax, [rbp+10D0h+var_1060]
0x180008269  mov     [rbp+10D0h+var_1058], rax
0x18000826d  mov     rsi, [rbp+10D0h+lpMem]
0x180008271  mov     [rbp+10D0h+lpMem], r13
0x180008275  test    rsi, rsi
0x180008278  jz      short loc_18000828E
0x18000827a  call    cs:__imp_GetProcessHeap
0x180008280  mov     rcx, rax; hHeap
0x180008283  mov     r8, rsi; lpMem
0x180008286  xor     edx, edx; dwFlags
0x180008288  call    cs:__imp_HeapFree
0x18000828e  test    dil, dil
0x180008291  jnz     short loc_1800082C5
0x180008293  cmp     r14, r12
0x180008296  jnb     short loc_1800082C5
0x180008298  cmp     r15, 32h ; '2'
0x18000829c  jb      loc_180007F7A
0x1800082a2  jmp     short loc_1800082C5
0x1800082a4  mov     rbx, [rbp+10D0h+lpMem]
0x1800082a8  mov     [rbp+10D0h+lpMem], r13
0x1800082ac  test    rbx, rbx
0x1800082af  jz      short loc_1800082C5
0x1800082b1  call    cs:__imp_GetProcessHeap
0x1800082b7  mov     rcx, rax; hHeap
0x1800082ba  mov     r8, rbx; lpMem
0x1800082bd  xor     edx, edx; dwFlags
0x1800082bf  call    cs:__imp_HeapFree
0x1800082c5  mov     rcx, [rbp+10D0h+var_40]
0x1800082cc  xor     rcx, rsp; StackCookie
0x1800082cf  call    __security_check_cookie
0x1800082d4  mov     rbx, [rsp+11D0h+arg_8]
0x1800082dc  add     rsp, 11A0h
0x1800082e3  pop     r15
0x1800082e5  pop     r14
0x1800082e7  pop     r13
0x1800082e9  pop     r12
0x1800082eb  pop     rdi
0x1800082ec  pop     rsi
0x1800082ed  pop     rbp
0x1800082ee  retn
0x1800082ef  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
