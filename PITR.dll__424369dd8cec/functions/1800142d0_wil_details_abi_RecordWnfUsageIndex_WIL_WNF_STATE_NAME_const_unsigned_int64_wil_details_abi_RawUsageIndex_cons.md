# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800142d0`
- end: `0x180014695`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `965`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180013774`

## callees

- `0x180012000`
- `0x1800130b8`
- `0x1800142d0`
- `0x18001b404`
- `0x18001dd64`
- `0x1800226a0`
- `0x180050300`
- `0x1800503c0`
- `0x180053010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800143a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800143a5`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800143bc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800143bc`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001461a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014651`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18001461a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180014651`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014628`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001465f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180014628`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001465f`

## string_xrefs

- `0x18001439e`: `ntdll.dll`

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
  __int64 v17; // r9
  char v18; // di
  int updated; // eax
  __int64 v20; // r9
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
  int v41[6]; // [rsp+118h] [rbp+18h] BYREF
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v41);
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v47, (int)v48 - (int)v47, v17, (int)v25, v41[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v47, v48 - v47, v20, (int)v25, 0, 0);
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
0x1800142d0  mov     [rsp-8+arg_8], rbx
0x1800142d5  push    rbp
0x1800142d6  push    rsi
0x1800142d7  push    rdi
0x1800142d8  push    r12
0x1800142da  push    r13
0x1800142dc  push    r14
0x1800142de  push    r15
0x1800142e0  lea     rbp, [rsp-10A0h]
0x1800142e8  mov     eax, 11A0h
0x1800142ed  call    _alloca_probe
0x1800142f2  sub     rsp, rax
0x1800142f5  mov     rax, cs:__security_cookie
0x1800142fc  xor     rax, rsp
0x1800142ff  mov     [rbp+10D0h+var_40], rax
0x180014306  mov     rbx, r8
0x180014309  mov     r14, rcx
0x18001430c  lea     r12, [rcx+rdx*8]
0x180014310  xor     r13d, r13d
0x180014313  mov     r15d, r13d
0x180014316  mov     [rbp+10D0h+var_1058], r13
0x18001431a  mov     cl, [rbx+8]
0x18001431d  movzx   edx, word ptr [rbx+6]
0x180014321  movzx   eax, word ptr [rbx]
0x180014324  mov     [rbp+10D0h+var_10A0], ax
0x180014328  movzx   eax, word ptr [rbx+2]
0x18001432c  mov     [rbp+10D0h+var_109E], ax
0x180014330  mov     al, [rbx+4]
0x180014333  mov     [rbp+10D0h+var_109C], al
0x180014336  mov     [rbp+10D0h+var_109A], dx
0x18001433a  mov     [rbp+10D0h+var_1098], cl
0x18001433d  test    dx, dx
0x180014340  jz      short loc_18001435E
0x180014342  mov     eax, edx
0x180014344  cmp     cl, 1
0x180014347  jnz     short loc_18001434F
0x180014349  add     rax, 2
0x18001434d  jmp     short loc_180014358
0x18001434f  cmp     cl, 2
0x180014352  jnz     short loc_180014358
0x180014354  add     rax, 4
0x180014358  mov     [rbp+10D0h+var_1090], rax
0x18001435c  jmp     short loc_180014362
0x18001435e  mov     [rbp+10D0h+var_1090], r13
0x180014362  mov     [rbp+10D0h+var_1088], r13
0x180014366  xorps   xmm0, xmm0
0x180014369  movdqa  [rbp+10D0h+var_1080], xmm0
0x18001436e  mov     [rbp+10D0h+lpMem], r13
0x180014372  mov     [rbp+10D0h+var_1068], r13w
0x180014377  mov     [rbp+10D0h+var_1066], r13b
0x18001437b  mov     [rbp+10D0h+var_10B8], r13d
0x18001437f  mov     dword ptr [rbp+10D0h+var_10C0], 1000h
0x180014386  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18001438d  test    rax, rax
0x180014390  jnz     short loc_1800143D5
0x180014392  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180014399  test    rax, rax
0x18001439c  jnz     short loc_1800143B2
0x18001439e  lea     rcx, aNtdllDll_2; "ntdll.dll"
0x1800143a5  call    cs:__imp_GetModuleHandleW
0x1800143ab  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800143b2  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800143b9  mov     rcx, rax; hModule
0x1800143bc  call    cs:__imp_GetProcAddress
0x1800143c2  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800143c9  test    rax, rax
0x1800143cc  jnz     short loc_1800143D5
0x1800143ce  mov     edi, 0C0000139h
0x1800143d3  jmp     short loc_1800143FD
0x1800143d5  lea     rcx, [rbp+10D0h+var_10C0]
0x1800143d9  mov     [rsp+11D0h+var_11A8], rcx
0x1800143de  lea     rcx, [rbp+10D0h+var_1040]
0x1800143e5  mov     [rsp+11D0h+var_11B0], rcx
0x1800143ea  lea     r9, [rbp+10D0h+var_10B8]
0x1800143ee  xor     r8d, r8d
0x1800143f1  xor     edx, edx
0x1800143f3  mov     rcx, r14
0x1800143f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800143fb  mov     edi, eax
0x1800143fd  mov     ecx, edi; this
0x1800143ff  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180014404  test    edi, edi
0x180014406  jz      short loc_180014414
0x180014408  mov     eax, r13d
0x18001440b  mov     dword ptr [rbp+10D0h+var_10C0], eax
0x18001440e  mov     [rbp+10D0h+var_10B8], r13d
0x180014412  jmp     short loc_180014417
0x180014414  mov     eax, dword ptr [rbp+10D0h+var_10C0]
0x180014417  mov     r8d, eax; unsigned __int64
0x18001441a  mov     r9d, 1000h; unsigned __int64
0x180014420  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180014427  lea     rcx, [rbp+10D0h+var_10A0]; this
0x18001442b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180014430  cmp     byte ptr [rbp+10D0h+var_1068+1], r13b
0x180014434  jnz     loc_180014644
0x18001443a  mov     [rbp+10D0h+var_1060], r13
0x18001443e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180014445  mov     [rsp+11D0h+var_1180], rax
0x18001444a  lea     rax, [rbp+10D0h+var_1060]
0x18001444e  mov     [rsp+11D0h+var_1178], rax
0x180014453  lea     rax, [rbp+10D0h+var_1058]
0x180014457  mov     [rsp+11D0h+var_1170], rax
0x18001445c  lea     rax, [rbp+10D0h+var_10A0]
0x180014460  mov     [rsp+11D0h+var_1168], rax
0x180014465  lea     rax, [rsp+11D0h+var_1180]
0x18001446a  mov     [rbp+10D0h+var_1118], rax
0x18001446e  lea     rax, [rsp+11D0h+var_1188]
0x180014473  mov     [rsp+11D0h+var_1190], rax
0x180014478  mov     rax, [rbx+18h]
0x18001447c  add     rax, 0Ah
0x180014480  mov     [rbp+10D0h+var_10C0], rax
0x180014484  movzx   eax, word ptr [rbx+2]
0x180014488  mov     [rbp+10D0h+var_1110], ax
0x18001448c  mov     al, [rbx+4]
0x18001448f  mov     [rbp+10D0h+var_110E], al
0x180014492  mov     [rbp+10D0h+var_110C], r13d
0x180014496  mov     [rbp+10D0h+var_1108], r13w
0x18001449b  xorps   xmm0, xmm0
0x18001449e  movdqu  [rbp+10D0h+var_1100], xmm0
0x1800144a3  movzx   eax, word ptr [rbx+6]
0x1800144a7  mov     [rbp+10D0h+var_10F0], ax
0x1800144ab  mov     al, [rbx+8]
0x1800144ae  mov     [rbp+10D0h+var_10EE], al
0x1800144b1  mov     [rbp+10D0h+var_10EC], r13d
0x1800144b5  mov     [rbp+10D0h+var_10E8], r13w
0x1800144ba  movdqu  [rbp+10D0h+var_10E0], xmm0
0x1800144bf  jmp     loc_18001455E
0x1800144c4  mov     edi, r13d
0x1800144c7  cmp     [rbp+10D0h+var_110C], r13d
0x1800144cb  jbe     loc_18001455E
0x1800144d1  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800144d5  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x1800144d9  lea     rcx, [rbp+10D0h+var_10F0]; this
0x1800144dd  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800144e2  test    al, al
0x1800144e4  jz      short loc_18001455E
0x1800144e6  mov     eax, [rbp+10D0h+var_10EC]
0x1800144e9  mov     [rbp+10D0h+var_10B0], eax
0x1800144ec  movzx   eax, [rbp+10D0h+var_10E8]
0x1800144f0  mov     [rbp+10D0h+var_1050], rax
0x1800144f7  mov     rax, qword ptr [rbp+10D0h+var_10E0+8]
0x1800144fb  mov     [rbp+10D0h+var_10D0], rax
0x1800144ff  movzx   eax, [rbp+10D0h+var_1108]
0x180014503  mov     [rbp+10D0h+var_1048], rax
0x18001450a  mov     rax, qword ptr [rbp+10D0h+var_1100+8]
0x18001450e  mov     [rbp+10D0h+var_10C8], rax
0x180014512  mov     rcx, [rbp+10D0h+var_1118]; this
0x180014516  test    rcx, rcx
0x180014519  jz      loc_18001468F
0x18001451f  mov     rax, [rcx]
0x180014522  lea     rdx, [rbp+10D0h+var_10B0]
0x180014526  mov     [rsp+11D0h+var_11A8], rdx
0x18001452b  lea     rdx, [rbp+10D0h+var_1050]
0x180014532  mov     [rsp+11D0h+var_11B0], rdx
0x180014537  lea     r9, [rbp+10D0h+var_10D0]
0x18001453b  lea     r8, [rbp+10D0h+var_1048]
0x180014542  lea     rdx, [rbp+10D0h+var_10C8]
0x180014546  mov     rax, [rax+20h]
0x18001454a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001454f  test    al, al
0x180014551  jz      short loc_1800145C6
0x180014553  inc     edi
0x180014555  cmp     edi, [rbp+10D0h+var_110C]
0x180014558  jb      loc_1800144D1
0x18001455e  mov     r8, [rbx+20h]; unsigned __int8 *
0x180014562  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x180014566  lea     rcx, [rbp+10D0h+var_1110]; this
0x18001456a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18001456f  test    al, al
0x180014571  jnz     loc_1800144C4
0x180014577  mov     rcx, [rbp+10D0h+var_1118]
0x18001457b  test    rcx, rcx
0x18001457e  jz      short loc_18001458C
0x180014580  mov     rax, [rcx]
0x180014583  mov     rax, [rax+18h]
0x180014587  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001458c  mov     dil, 1
0x18001458f  cmp     byte ptr [rbp+10D0h+var_1068], r13b
0x180014593  jz      short loc_180014601
0x180014595  mov     eax, [rbp+10D0h+var_10B8]
0x180014598  mov     rdx, [rbp+10D0h+var_1088]
0x18001459c  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x1800145a0  sub     r8d, edx
0x1800145a3  mov     [rsp+11D0h+var_11A0], 1
0x1800145ab  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800145af  mov     rcx, r14
0x1800145b2  call    wil_details_NtUpdateWnfStateData
0x1800145b7  cmp     eax, 0C0000001h
0x1800145bc  jnz     short loc_1800145E0
0x1800145be  inc     r15
0x1800145c1  mov     dil, r13b
0x1800145c4  jmp     short loc_18001460D
0x1800145c6  mov     rcx, [rbp+10D0h+var_1118]
0x1800145ca  test    rcx, rcx
0x1800145cd  jz      short loc_1800145DB
0x1800145cf  mov     rax, [rcx]
0x1800145d2  mov     rax, [rax+18h]
0x1800145d6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800145db  mov     dil, r13b
0x1800145de  jmp     short loc_18001458F
0x1800145e0  test    eax, eax
0x1800145e2  jz      short loc_180014601
0x1800145e4  mov     rdx, [rbp+10D0h+var_1088]
0x1800145e8  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x1800145ec  sub     r8d, edx
0x1800145ef  mov     [rsp+11D0h+var_11A0], r13d
0x1800145f4  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x1800145f9  mov     rcx, r14
0x1800145fc  call    wil_details_NtUpdateWnfStateData
0x180014601  add     r14, 8
0x180014605  mov     rax, [rbp+10D0h+var_1060]
0x180014609  mov     [rbp+10D0h+var_1058], rax
0x18001460d  mov     rsi, [rbp+10D0h+lpMem]
0x180014611  mov     [rbp+10D0h+lpMem], r13
0x180014615  test    rsi, rsi
0x180014618  jz      short loc_18001462E
0x18001461a  call    cs:__imp_GetProcessHeap
0x180014620  mov     rcx, rax; hHeap
0x180014623  mov     r8, rsi; lpMem
0x180014626  xor     edx, edx; dwFlags
0x180014628  call    cs:__imp_HeapFree
0x18001462e  test    dil, dil
0x180014631  jnz     short loc_180014665
0x180014633  cmp     r14, r12
0x180014636  jnb     short loc_180014665
0x180014638  cmp     r15, 32h ; '2'
0x18001463c  jb      loc_18001431A
0x180014642  jmp     short loc_180014665
0x180014644  mov     rbx, [rbp+10D0h+lpMem]
0x180014648  mov     [rbp+10D0h+lpMem], r13
0x18001464c  test    rbx, rbx
0x18001464f  jz      short loc_180014665
0x180014651  call    cs:__imp_GetProcessHeap
0x180014657  mov     rcx, rax; hHeap
0x18001465a  mov     r8, rbx; lpMem
0x18001465d  xor     edx, edx; dwFlags
0x18001465f  call    cs:__imp_HeapFree
0x180014665  mov     rcx, [rbp+10D0h+var_40]
0x18001466c  xor     rcx, rsp; StackCookie
0x18001466f  call    __security_check_cookie
0x180014674  mov     rbx, [rsp+11D0h+arg_8]
0x18001467c  add     rsp, 11A0h
0x180014683  pop     r15
0x180014685  pop     r14
0x180014687  pop     r13
0x180014689  pop     r12
0x18001468b  pop     rdi
0x18001468c  pop     rsi
0x18001468d  pop     rbp
0x18001468e  retn
0x18001468f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
