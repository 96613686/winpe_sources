# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180006434`
- end: `0x180006804`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `976`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180005b1c`

## callees

- `0x1800018e0`
- `0x1800056b8`
- `0x180005a1c`
- `0x180006434`
- `0x180006df8`
- `0x180007b2c`
- `0x180007f64`
- `0x1800265e0`
- `0x180027010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006514`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006514`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000652b`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000652b`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000678a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067c0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000678a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800067c0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006798`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067ce`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006798`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800067ce`

## string_xrefs

- `0x18000650d`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v4; // r13
  unsigned __int64 v5; // r12
  wil::details_abi *v7; // r14
  unsigned int v8; // edx
  char v9; // cl
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // ebx
  unsigned int v15; // eax
  __int64 v16; // rax
  unsigned int v17; // esi
  int v18; // ebx
  __int64 v19; // r15
  int v20; // r9d
  char v21; // bl
  int updated; // eax
  int v23; // r9d
  void *v24; // rsi
  HANDLE ProcessHeap; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  __int64 *v28; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v29; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v30[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v31[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v32; // [rsp+64h] [rbp-9Ch]
  __int16 v33; // [rsp+66h] [rbp-9Ah]
  char v34; // [rsp+68h] [rbp-98h]
  __int64 v35; // [rsp+70h] [rbp-90h]
  __int64 v36; // [rsp+78h] [rbp-88h]
  __int128 v37; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v39; // [rsp+98h] [rbp-68h]
  char v40; // [rsp+9Ah] [rbp-66h]
  __int64 v41; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v42; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v43; // [rsp+B0h] [rbp-50h] BYREF
  char v44; // [rsp+B2h] [rbp-4Eh]
  unsigned int v45; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v46; // [rsp+B8h] [rbp-48h]
  __int128 v47; // [rsp+C0h] [rbp-40h]
  __int16 v48; // [rsp+D0h] [rbp-30h] BYREF
  char v49; // [rsp+D2h] [rbp-2Eh]
  int v50; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v51; // [rsp+D8h] [rbp-28h]
  __int128 v52; // [rsp+E0h] [rbp-20h]
  __int64 v53; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v54; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v55; // [rsp+100h] [rbp+0h] BYREF
  __int64 v56; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v57[13]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *v58; // [rsp+180h] [rbp+80h]
  _BYTE v59[4096]; // [rsp+190h] [rbp+90h] BYREF

  v4 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v5 = 0;
  v42 = 0;
  v7 = this;
  while ( 1 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6);
    v9 = *(_BYTE *)(a3 + 8);
    v31[0] = *(_WORD *)a3;
    v31[1] = *(_WORD *)(a3 + 2);
    v32 = *(_BYTE *)(a3 + 4);
    v33 = v8;
    v34 = v9;
    if ( (_WORD)v8 )
    {
      v10 = v8;
      if ( v9 == 1 )
      {
        v10 = v8 + 2LL;
      }
      else if ( v9 == 2 )
      {
        v10 = v8 + 4LL;
      }
      v35 = v10;
    }
    else
    {
      v35 = 0;
    }
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v36 = 0;
    v37 = 0;
    lpMem = 0;
    v39 = 0;
    v40 = 0;
    v30[0] = 0;
    LODWORD(v29) = 4096;
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
      v28 = (__int64 *)v59;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v7, 0, 0, v30);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      v30[0] = 0;
      LODWORD(v29) = 0;
    }
    else
    {
      v15 = (unsigned int)v29;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v31, v59, v15, 0x1000u);
    if ( HIBYTE(v39) )
      break;
    v41 = 0;
    v57[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v45 = 0;
    v57[1] = &v41;
    v57[2] = &v42;
    v57[3] = v31;
    v58 = (wil::details::in1diag3 *)v57;
    v16 = *(_QWORD *)(a3 + 24);
    v46 = 0;
    v29 = (unsigned __int8 *)(v16 + 10);
    v43 = *(_WORD *)(a3 + 2);
    v44 = *(_BYTE *)(a3 + 4);
    v48 = *(_WORD *)(a3 + 6);
    v49 = *(_BYTE *)(a3 + 8);
    v47 = 0;
    v50 = 0;
    v51 = 0;
    v52 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v43,
              &v29,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v17 = v45;
      v18 = 0;
      if ( v45 )
      {
        v19 = *((_QWORD *)&v47 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v48,
                  &v29,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v30[2] = v50;
          v53 = v51;
          v54 = *((_QWORD *)&v52 + 1);
          v55 = v46;
          v56 = v19;
          if ( !v58 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v28 = &v53;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v58 + 32LL))(
                  v58,
                  &v56,
                  &v55,
                  &v54) )
          {
            if ( v58 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
            v21 = 0;
            goto LABEL_30;
          }
          if ( ++v18 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v58 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v58 + 24LL))(v58);
    v21 = 1;
LABEL_30:
    if ( !(_BYTE)v39 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v7, v36, (int)v37 - (int)v36, v20, (_DWORD)v28, v30[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v7, v36, v37 - v36, v23, (_DWORD)v28, 0, 0);
LABEL_38:
      v7 = (wil::details_abi *)((char *)v7 + 8);
      v42 = v41;
      goto LABEL_39;
    }
    ++v5;
    v21 = 0;
LABEL_39:
    v24 = lpMem;
    lpMem = 0;
    if ( v24 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v24);
    }
    if ( v21 || v7 >= v4 || v5 >= 0x32 )
      return;
  }
  v26 = lpMem;
  lpMem = 0;
  if ( v26 )
  {
    v27 = GetProcessHeap();
    HeapFree(v27, 0, v26);
  }
}

```

## disassembly

```asm
0x180006434  mov     [rsp-8+arg_8], rbx
0x180006439  push    rbp
0x18000643a  push    rsi
0x18000643b  push    rdi
0x18000643c  push    r12
0x18000643e  push    r13
0x180006440  push    r14
0x180006442  push    r15
0x180006444  lea     rbp, [rsp-10A0h]
0x18000644c  mov     eax, 11A0h
0x180006451  call    _alloca_probe
0x180006456  sub     rsp, rax
0x180006459  mov     rax, cs:__security_cookie
0x180006460  xor     rax, rsp
0x180006463  mov     [rbp+10D0h+var_40], rax
0x18000646a  xor     r15d, r15d
0x18000646d  lea     r13, [rcx+rdx*8]
0x180006471  mov     r12d, r15d
0x180006474  mov     [rbp+10D0h+var_1128], r15
0x180006478  mov     rdi, r8
0x18000647b  mov     r14, rcx
0x18000647e  movzx   eax, word ptr [rdi]
0x180006481  movzx   edx, word ptr [rdi+6]
0x180006485  mov     cl, [rdi+8]
0x180006488  mov     [rsp+11D0h+var_1170], ax
0x18000648d  movzx   eax, word ptr [rdi+2]
0x180006491  mov     [rsp+11D0h+var_116E], ax
0x180006496  mov     al, [rdi+4]
0x180006499  mov     [rsp+11D0h+var_116C], al
0x18000649d  mov     [rsp+11D0h+var_116A], dx
0x1800064a2  mov     [rsp+11D0h+var_1168], cl
0x1800064a6  test    dx, dx
0x1800064a9  jz      short loc_1800064C8
0x1800064ab  mov     eax, edx
0x1800064ad  cmp     cl, 1
0x1800064b0  jnz     short loc_1800064B8
0x1800064b2  add     rax, 2
0x1800064b6  jmp     short loc_1800064C1
0x1800064b8  cmp     cl, 2
0x1800064bb  jnz     short loc_1800064C1
0x1800064bd  add     rax, 4
0x1800064c1  mov     [rsp+11D0h+var_1160], rax
0x1800064c6  jmp     short loc_1800064CD
0x1800064c8  mov     [rsp+11D0h+var_1160], r15
0x1800064cd  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800064d4  xorps   xmm0, xmm0
0x1800064d7  mov     [rsp+11D0h+var_1158], r15
0x1800064dc  movdqa  [rbp+10D0h+var_1150], xmm0
0x1800064e1  mov     [rbp+10D0h+lpMem], r15
0x1800064e5  mov     [rbp+10D0h+var_1138], 0
0x1800064eb  mov     [rbp+10D0h+var_1136], r15b
0x1800064ef  mov     [rsp+11D0h+var_1188], r15d
0x1800064f4  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1800064fc  test    rax, rax
0x1800064ff  jnz     short loc_180006544
0x180006501  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006508  test    rax, rax
0x18000650b  jnz     short loc_180006521
0x18000650d  lea     rcx, ModuleName; "ntdll.dll"
0x180006514  call    cs:__imp_GetModuleHandleW
0x18000651a  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006521  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180006528  mov     rcx, rax; hModule
0x18000652b  call    cs:__imp_GetProcAddress
0x180006531  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180006538  test    rax, rax
0x18000653b  jnz     short loc_180006544
0x18000653d  mov     ebx, 0C0000139h
0x180006542  jmp     short loc_18000656E
0x180006544  lea     rcx, [rsp+11D0h+var_1190]
0x180006549  xor     r8d, r8d
0x18000654c  mov     [rsp+11D0h+var_11A8], rcx
0x180006551  lea     r9, [rsp+11D0h+var_1188]
0x180006556  lea     rcx, [rbp+10D0h+var_1040]
0x18000655d  xor     edx, edx
0x18000655f  mov     [rsp+11D0h+var_11B0], rcx
0x180006564  mov     rcx, r14
0x180006567  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000656c  mov     ebx, eax
0x18000656e  mov     ecx, ebx; this
0x180006570  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180006575  test    ebx, ebx
0x180006577  jz      short loc_180006587
0x180006579  mov     eax, r15d
0x18000657c  mov     [rsp+11D0h+var_1188], r15d
0x180006581  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180006585  jmp     short loc_18000658B
0x180006587  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000658b  mov     r8d, eax; unsigned __int64
0x18000658e  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180006595  mov     r9d, 1000h; unsigned __int64
0x18000659b  lea     rcx, [rsp+11D0h+var_1170]; this
0x1800065a0  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1800065a5  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x1800065a9  jnz     loc_1800067B3
0x1800065af  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800065b6  mov     [rbp+10D0h+var_1130], r15
0x1800065ba  mov     [rbp+10D0h+var_10B8], rax
0x1800065be  xorps   xmm0, xmm0
0x1800065c1  lea     rax, [rbp+10D0h+var_1130]
0x1800065c5  mov     [rbp+10D0h+var_111C], r15d
0x1800065c9  mov     [rbp+10D0h+var_10B0], rax
0x1800065cd  lea     rax, [rbp+10D0h+var_1128]
0x1800065d1  mov     [rbp+10D0h+var_10A8], rax
0x1800065d5  lea     rax, [rsp+11D0h+var_1170]
0x1800065da  mov     [rbp+10D0h+var_10A0], rax
0x1800065de  lea     rax, [rbp+10D0h+var_10B8]
0x1800065e2  mov     [rbp+10D0h+var_1050], rax
0x1800065e9  mov     rax, [rdi+18h]
0x1800065ed  add     rax, 0Ah
0x1800065f1  mov     [rbp+10D0h+var_1118], r15w
0x1800065f6  mov     [rsp+11D0h+var_1190], rax
0x1800065fb  movzx   eax, word ptr [rdi+2]
0x1800065ff  mov     [rbp+10D0h+var_1120], ax
0x180006603  mov     al, [rdi+4]
0x180006606  mov     [rbp+10D0h+var_111E], al
0x180006609  movzx   eax, word ptr [rdi+6]
0x18000660d  mov     [rbp+10D0h+var_1100], ax
0x180006611  mov     al, [rdi+8]
0x180006614  mov     [rbp+10D0h+var_10FE], al
0x180006617  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000661c  mov     [rbp+10D0h+var_10FC], r15d
0x180006620  mov     [rbp+10D0h+var_10F8], r15w
0x180006625  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000662a  jmp     loc_1800066C2
0x18000662f  mov     esi, [rbp+10D0h+var_111C]
0x180006632  mov     ebx, r15d
0x180006635  test    esi, esi
0x180006637  jz      loc_1800066C2
0x18000663d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180006641  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006645  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000664a  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000664e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006653  test    al, al
0x180006655  jz      short loc_1800066BF
0x180006657  mov     eax, [rbp+10D0h+var_10FC]
0x18000665a  mov     rcx, [rbp+10D0h+var_1050]; this
0x180006661  mov     [rsp+11D0h+var_1180], eax
0x180006665  movzx   eax, [rbp+10D0h+var_10F8]
0x180006669  mov     [rbp+10D0h+var_10E0], rax
0x18000666d  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180006671  mov     [rbp+10D0h+var_10D8], rax
0x180006675  movzx   eax, [rbp+10D0h+var_1118]
0x180006679  mov     [rbp+10D0h+var_10D0], rax
0x18000667d  mov     [rbp+10D0h+var_10C8], r15
0x180006681  test    rcx, rcx
0x180006684  jz      loc_1800067FE
0x18000668a  mov     rax, [rcx]
0x18000668d  lea     rdx, [rsp+11D0h+var_1180]
0x180006692  mov     [rsp+11D0h+var_11A8], rdx
0x180006697  lea     r9, [rbp+10D0h+var_10D8]
0x18000669b  lea     rdx, [rbp+10D0h+var_10E0]
0x18000669f  mov     [rsp+11D0h+var_11B0], rdx
0x1800066a4  lea     r8, [rbp+10D0h+var_10D0]
0x1800066a8  mov     rax, [rax+20h]
0x1800066ac  lea     rdx, [rbp+10D0h+var_10C8]
0x1800066b0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066b5  test    al, al
0x1800066b7  jz      short loc_18000672F
0x1800066b9  inc     ebx
0x1800066bb  cmp     ebx, esi
0x1800066bd  jb      short loc_180006641
0x1800066bf  xor     r15d, r15d
0x1800066c2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800066c6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800066cb  lea     rcx, [rbp+10D0h+var_1120]; this
0x1800066cf  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800066d4  test    al, al
0x1800066d6  jnz     loc_18000662F
0x1800066dc  mov     rcx, [rbp+10D0h+var_1050]
0x1800066e3  test    rcx, rcx
0x1800066e6  jz      short loc_1800066F4
0x1800066e8  mov     rax, [rcx]
0x1800066eb  mov     rax, [rax+18h]
0x1800066ef  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800066f4  mov     bl, 1
0x1800066f6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x1800066fa  jz      short loc_180006771
0x1800066fc  mov     rdx, [rsp+11D0h+var_1158]
0x180006701  mov     rcx, r14
0x180006704  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006708  mov     eax, [rsp+11D0h+var_1188]
0x18000670c  sub     r8d, edx
0x18000670f  mov     [rsp+11D0h+var_11A0], 1
0x180006717  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000671b  call    wil_details_NtUpdateWnfStateData
0x180006720  cmp     eax, 0C0000001h
0x180006725  jnz     short loc_18000674F
0x180006727  inc     r12
0x18000672a  mov     bl, r15b
0x18000672d  jmp     short loc_18000677D
0x18000672f  mov     rcx, [rbp+10D0h+var_1050]
0x180006736  xor     r15d, r15d
0x180006739  test    rcx, rcx
0x18000673c  jz      short loc_18000674A
0x18000673e  mov     rax, [rcx]
0x180006741  mov     rax, [rax+18h]
0x180006745  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000674a  mov     bl, r15b
0x18000674d  jmp     short loc_1800066F6
0x18000674f  test    eax, eax
0x180006751  jz      short loc_180006771
0x180006753  mov     rdx, [rsp+11D0h+var_1158]
0x180006758  mov     rcx, r14
0x18000675b  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000675f  sub     r8d, edx
0x180006762  mov     [rsp+11D0h+var_11A0], r15d
0x180006767  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000676c  call    wil_details_NtUpdateWnfStateData
0x180006771  mov     rax, [rbp+10D0h+var_1130]
0x180006775  add     r14, 8
0x180006779  mov     [rbp+10D0h+var_1128], rax
0x18000677d  mov     rsi, [rbp+10D0h+lpMem]
0x180006781  mov     [rbp+10D0h+lpMem], r15
0x180006785  test    rsi, rsi
0x180006788  jz      short loc_18000679E
0x18000678a  call    cs:__imp_GetProcessHeap
0x180006790  mov     r8, rsi; lpMem
0x180006793  xor     edx, edx; dwFlags
0x180006795  mov     rcx, rax; hHeap
0x180006798  call    cs:__imp_HeapFree
0x18000679e  test    bl, bl
0x1800067a0  jnz     short loc_1800067D4
0x1800067a2  cmp     r14, r13
0x1800067a5  jnb     short loc_1800067D4
0x1800067a7  cmp     r12, 32h ; '2'
0x1800067ab  jb      loc_18000647E
0x1800067b1  jmp     short loc_1800067D4
0x1800067b3  mov     rbx, [rbp+10D0h+lpMem]
0x1800067b7  mov     [rbp+10D0h+lpMem], r15
0x1800067bb  test    rbx, rbx
0x1800067be  jz      short loc_1800067D4
0x1800067c0  call    cs:__imp_GetProcessHeap
0x1800067c6  mov     r8, rbx; lpMem
0x1800067c9  xor     edx, edx; dwFlags
0x1800067cb  mov     rcx, rax; hHeap
0x1800067ce  call    cs:__imp_HeapFree
0x1800067d4  mov     rcx, [rbp+10D0h+var_40]
0x1800067db  xor     rcx, rsp; StackCookie
0x1800067de  call    __security_check_cookie
0x1800067e3  mov     rbx, [rsp+11D0h+arg_8]
0x1800067eb  add     rsp, 11A0h
0x1800067f2  pop     r15
0x1800067f4  pop     r14
0x1800067f6  pop     r13
0x1800067f8  pop     r12
0x1800067fa  pop     rdi
0x1800067fb  pop     rsi
0x1800067fc  pop     rbp
0x1800067fd  retn
0x1800067fe  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
