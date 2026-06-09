# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180008020`
- end: `0x1800083e5`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `965`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800074c8`

## callees

- `0x180006fb4`
- `0x1800073bc`
- `0x180008020`
- `0x180008d74`
- `0x18000b848`
- `0x18000cdd0`
- `0x1800107c0`
- `0x180010880`
- `0x180012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000810c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000810c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800080f5`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800080f5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000836a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083a1`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000836a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083a1`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008378`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083af`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180008378`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083af`

## string_xrefs

- `0x1800080ee`: `ntdll.dll`

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
0x180008020  mov     [rsp-8+arg_8], rbx
0x180008025  push    rbp
0x180008026  push    rsi
0x180008027  push    rdi
0x180008028  push    r12
0x18000802a  push    r13
0x18000802c  push    r14
0x18000802e  push    r15
0x180008030  lea     rbp, [rsp-10A0h]
0x180008038  mov     eax, 11A0h
0x18000803d  call    _alloca_probe
0x180008042  sub     rsp, rax
0x180008045  mov     rax, cs:__security_cookie
0x18000804c  xor     rax, rsp
0x18000804f  mov     [rbp+10D0h+var_40], rax
0x180008056  mov     rbx, r8
0x180008059  mov     r14, rcx
0x18000805c  lea     r12, [rcx+rdx*8]
0x180008060  xor     r13d, r13d
0x180008063  mov     r15d, r13d
0x180008066  mov     [rbp+10D0h+var_1058], r13
0x18000806a  mov     cl, [rbx+8]
0x18000806d  movzx   edx, word ptr [rbx+6]
0x180008071  movzx   eax, word ptr [rbx]
0x180008074  mov     [rbp+10D0h+var_10A0], ax
0x180008078  movzx   eax, word ptr [rbx+2]
0x18000807c  mov     [rbp+10D0h+var_109E], ax
0x180008080  mov     al, [rbx+4]
0x180008083  mov     [rbp+10D0h+var_109C], al
0x180008086  mov     [rbp+10D0h+var_109A], dx
0x18000808a  mov     [rbp+10D0h+var_1098], cl
0x18000808d  test    dx, dx
0x180008090  jz      short loc_1800080AE
0x180008092  mov     eax, edx
0x180008094  cmp     cl, 1
0x180008097  jnz     short loc_18000809F
0x180008099  add     rax, 2
0x18000809d  jmp     short loc_1800080A8
0x18000809f  cmp     cl, 2
0x1800080a2  jnz     short loc_1800080A8
0x1800080a4  add     rax, 4
0x1800080a8  mov     [rbp+10D0h+var_1090], rax
0x1800080ac  jmp     short loc_1800080B2
0x1800080ae  mov     [rbp+10D0h+var_1090], r13
0x1800080b2  mov     [rbp+10D0h+var_1088], r13
0x1800080b6  xorps   xmm0, xmm0
0x1800080b9  movdqa  [rbp+10D0h+var_1080], xmm0
0x1800080be  mov     [rbp+10D0h+lpMem], r13
0x1800080c2  mov     [rbp+10D0h+var_1068], r13w
0x1800080c7  mov     [rbp+10D0h+var_1066], r13b
0x1800080cb  mov     [rbp+10D0h+var_10B8], r13d
0x1800080cf  mov     dword ptr [rbp+10D0h+var_10C0], 1000h
0x1800080d6  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800080dd  test    rax, rax
0x1800080e0  jnz     short loc_180008125
0x1800080e2  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800080e9  test    rax, rax
0x1800080ec  jnz     short loc_180008102
0x1800080ee  lea     rcx, ModuleName; "ntdll.dll"
0x1800080f5  call    cs:__imp_GetModuleHandleW
0x1800080fb  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008102  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008109  mov     rcx, rax; hModule
0x18000810c  call    cs:__imp_GetProcAddress
0x180008112  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008119  test    rax, rax
0x18000811c  jnz     short loc_180008125
0x18000811e  mov     edi, 0C0000139h
0x180008123  jmp     short loc_18000814D
0x180008125  lea     rcx, [rbp+10D0h+var_10C0]
0x180008129  mov     [rsp+11D0h+var_11A8], rcx
0x18000812e  lea     rcx, [rbp+10D0h+var_1040]
0x180008135  mov     [rsp+11D0h+var_11B0], rcx
0x18000813a  lea     r9, [rbp+10D0h+var_10B8]
0x18000813e  xor     r8d, r8d
0x180008141  xor     edx, edx
0x180008143  mov     rcx, r14
0x180008146  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000814b  mov     edi, eax
0x18000814d  mov     ecx, edi; this
0x18000814f  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180008154  test    edi, edi
0x180008156  jz      short loc_180008164
0x180008158  mov     eax, r13d
0x18000815b  mov     dword ptr [rbp+10D0h+var_10C0], eax
0x18000815e  mov     [rbp+10D0h+var_10B8], r13d
0x180008162  jmp     short loc_180008167
0x180008164  mov     eax, dword ptr [rbp+10D0h+var_10C0]
0x180008167  mov     r8d, eax; unsigned __int64
0x18000816a  mov     r9d, 1000h; unsigned __int64
0x180008170  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180008177  lea     rcx, [rbp+10D0h+var_10A0]; this
0x18000817b  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180008180  cmp     byte ptr [rbp+10D0h+var_1068+1], r13b
0x180008184  jnz     loc_180008394
0x18000818a  mov     [rbp+10D0h+var_1060], r13
0x18000818e  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180008195  mov     [rsp+11D0h+var_1180], rax
0x18000819a  lea     rax, [rbp+10D0h+var_1060]
0x18000819e  mov     [rsp+11D0h+var_1178], rax
0x1800081a3  lea     rax, [rbp+10D0h+var_1058]
0x1800081a7  mov     [rsp+11D0h+var_1170], rax
0x1800081ac  lea     rax, [rbp+10D0h+var_10A0]
0x1800081b0  mov     [rsp+11D0h+var_1168], rax
0x1800081b5  lea     rax, [rsp+11D0h+var_1180]
0x1800081ba  mov     [rbp+10D0h+var_1118], rax
0x1800081be  lea     rax, [rsp+11D0h+var_1188]
0x1800081c3  mov     [rsp+11D0h+var_1190], rax
0x1800081c8  mov     rax, [rbx+18h]
0x1800081cc  add     rax, 0Ah
0x1800081d0  mov     [rbp+10D0h+var_10C0], rax
0x1800081d4  movzx   eax, word ptr [rbx+2]
0x1800081d8  mov     [rbp+10D0h+var_1110], ax
0x1800081dc  mov     al, [rbx+4]
0x1800081df  mov     [rbp+10D0h+var_110E], al
0x1800081e2  mov     [rbp+10D0h+var_110C], r13d
0x1800081e6  mov     [rbp+10D0h+var_1108], r13w
0x1800081eb  xorps   xmm0, xmm0
0x1800081ee  movdqu  [rbp+10D0h+var_1100], xmm0
0x1800081f3  movzx   eax, word ptr [rbx+6]
0x1800081f7  mov     [rbp+10D0h+var_10F0], ax
0x1800081fb  mov     al, [rbx+8]
0x1800081fe  mov     [rbp+10D0h+var_10EE], al
0x180008201  mov     [rbp+10D0h+var_10EC], r13d
0x180008205  mov     [rbp+10D0h+var_10E8], r13w
0x18000820a  movdqu  [rbp+10D0h+var_10E0], xmm0
0x18000820f  jmp     loc_1800082AE
0x180008214  mov     edi, r13d
0x180008217  cmp     [rbp+10D0h+var_110C], r13d
0x18000821b  jbe     loc_1800082AE
0x180008221  mov     r8, [rbx+20h]; unsigned __int8 *
0x180008225  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x180008229  lea     rcx, [rbp+10D0h+var_10F0]; this
0x18000822d  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008232  test    al, al
0x180008234  jz      short loc_1800082AE
0x180008236  mov     eax, [rbp+10D0h+var_10EC]
0x180008239  mov     [rbp+10D0h+var_10B0], eax
0x18000823c  movzx   eax, [rbp+10D0h+var_10E8]
0x180008240  mov     [rbp+10D0h+var_1050], rax
0x180008247  mov     rax, qword ptr [rbp+10D0h+var_10E0+8]
0x18000824b  mov     [rbp+10D0h+var_10D0], rax
0x18000824f  movzx   eax, [rbp+10D0h+var_1108]
0x180008253  mov     [rbp+10D0h+var_1048], rax
0x18000825a  mov     rax, qword ptr [rbp+10D0h+var_1100+8]
0x18000825e  mov     [rbp+10D0h+var_10C8], rax
0x180008262  mov     rcx, [rbp+10D0h+var_1118]; this
0x180008266  test    rcx, rcx
0x180008269  jz      loc_1800083DF
0x18000826f  mov     rax, [rcx]
0x180008272  lea     rdx, [rbp+10D0h+var_10B0]
0x180008276  mov     [rsp+11D0h+var_11A8], rdx
0x18000827b  lea     rdx, [rbp+10D0h+var_1050]
0x180008282  mov     [rsp+11D0h+var_11B0], rdx
0x180008287  lea     r9, [rbp+10D0h+var_10D0]
0x18000828b  lea     r8, [rbp+10D0h+var_1048]
0x180008292  lea     rdx, [rbp+10D0h+var_10C8]
0x180008296  mov     rax, [rax+20h]
0x18000829a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000829f  test    al, al
0x1800082a1  jz      short loc_180008316
0x1800082a3  inc     edi
0x1800082a5  cmp     edi, [rbp+10D0h+var_110C]
0x1800082a8  jb      loc_180008221
0x1800082ae  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800082b2  lea     rdx, [rbp+10D0h+var_10C0]; unsigned __int8 **
0x1800082b6  lea     rcx, [rbp+10D0h+var_1110]; this
0x1800082ba  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800082bf  test    al, al
0x1800082c1  jnz     loc_180008214
0x1800082c7  mov     rcx, [rbp+10D0h+var_1118]
0x1800082cb  test    rcx, rcx
0x1800082ce  jz      short loc_1800082DC
0x1800082d0  mov     rax, [rcx]
0x1800082d3  mov     rax, [rax+18h]
0x1800082d7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800082dc  mov     dil, 1
0x1800082df  cmp     byte ptr [rbp+10D0h+var_1068], r13b
0x1800082e3  jz      short loc_180008351
0x1800082e5  mov     eax, [rbp+10D0h+var_10B8]
0x1800082e8  mov     rdx, [rbp+10D0h+var_1088]
0x1800082ec  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x1800082f0  sub     r8d, edx
0x1800082f3  mov     [rsp+11D0h+var_11A0], 1
0x1800082fb  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800082ff  mov     rcx, r14
0x180008302  call    wil_details_NtUpdateWnfStateData
0x180008307  cmp     eax, 0C0000001h
0x18000830c  jnz     short loc_180008330
0x18000830e  inc     r15
0x180008311  mov     dil, r13b
0x180008314  jmp     short loc_18000835D
0x180008316  mov     rcx, [rbp+10D0h+var_1118]
0x18000831a  test    rcx, rcx
0x18000831d  jz      short loc_18000832B
0x18000831f  mov     rax, [rcx]
0x180008322  mov     rax, [rax+18h]
0x180008326  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000832b  mov     dil, r13b
0x18000832e  jmp     short loc_1800082DF
0x180008330  test    eax, eax
0x180008332  jz      short loc_180008351
0x180008334  mov     rdx, [rbp+10D0h+var_1088]
0x180008338  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x18000833c  sub     r8d, edx
0x18000833f  mov     [rsp+11D0h+var_11A0], r13d
0x180008344  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x180008349  mov     rcx, r14
0x18000834c  call    wil_details_NtUpdateWnfStateData
0x180008351  add     r14, 8
0x180008355  mov     rax, [rbp+10D0h+var_1060]
0x180008359  mov     [rbp+10D0h+var_1058], rax
0x18000835d  mov     rsi, [rbp+10D0h+lpMem]
0x180008361  mov     [rbp+10D0h+lpMem], r13
0x180008365  test    rsi, rsi
0x180008368  jz      short loc_18000837E
0x18000836a  call    cs:__imp_GetProcessHeap
0x180008370  mov     rcx, rax; hHeap
0x180008373  mov     r8, rsi; lpMem
0x180008376  xor     edx, edx; dwFlags
0x180008378  call    cs:__imp_HeapFree
0x18000837e  test    dil, dil
0x180008381  jnz     short loc_1800083B5
0x180008383  cmp     r14, r12
0x180008386  jnb     short loc_1800083B5
0x180008388  cmp     r15, 32h ; '2'
0x18000838c  jb      loc_18000806A
0x180008392  jmp     short loc_1800083B5
0x180008394  mov     rbx, [rbp+10D0h+lpMem]
0x180008398  mov     [rbp+10D0h+lpMem], r13
0x18000839c  test    rbx, rbx
0x18000839f  jz      short loc_1800083B5
0x1800083a1  call    cs:__imp_GetProcessHeap
0x1800083a7  mov     rcx, rax; hHeap
0x1800083aa  mov     r8, rbx; lpMem
0x1800083ad  xor     edx, edx; dwFlags
0x1800083af  call    cs:__imp_HeapFree
0x1800083b5  mov     rcx, [rbp+10D0h+var_40]
0x1800083bc  xor     rcx, rsp; StackCookie
0x1800083bf  call    __security_check_cookie
0x1800083c4  mov     rbx, [rsp+11D0h+arg_8]
0x1800083cc  add     rsp, 11A0h
0x1800083d3  pop     r15
0x1800083d5  pop     r14
0x1800083d7  pop     r13
0x1800083d9  pop     r12
0x1800083db  pop     rdi
0x1800083dc  pop     rsi
0x1800083dd  pop     rbp
0x1800083de  retn
0x1800083df  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
