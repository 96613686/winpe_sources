# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x14000dcc4`
- end: `0x14000e0a8`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `996`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14000d408`

## callees

- `0x140002a30`
- `0x1400073b0`
- `0x14000cf9c`
- `0x14000d308`
- `0x14000dcc4`
- `0x14000e1d0`
- `0x14000ee14`
- `0x140011fc0`
- `0x140013010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ddc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000ddc7`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ddb0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000ddb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e03c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e072`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e03c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000e072`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e02e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e064`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e02e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000e064`

## string_xrefs

- `0x14000dda9`: `ntdll.dll`

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
  _QWORD v55[3]; // [rsp+108h] [rbp+8h] BYREF
  char v56; // [rsp+120h] [rbp+20h] BYREF
  _QWORD v57[13]; // [rsp+128h] [rbp+28h] BYREF
  wil::details::in1diag3 *v58; // [rsp+190h] [rbp+90h]
  _BYTE v59[4096]; // [rsp+1A0h] [rbp+A0h] BYREF

  v55[1] = -2;
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
    v55[2] = &v56;
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
0x14000dcc4  push    rbp
0x14000dcc6  push    rsi
0x14000dcc7  push    rdi
0x14000dcc8  push    r12
0x14000dcca  push    r13
0x14000dccc  push    r14
0x14000dcce  push    r15
0x14000dcd0  lea     rbp, [rsp-10B0h]
0x14000dcd8  mov     eax, 11B0h
0x14000dcdd  call    _alloca_probe
0x14000dce2  sub     rsp, rax
0x14000dce5  mov     [rbp+10E0h+var_10D0], 0FFFFFFFFFFFFFFFEh
0x14000dced  mov     [rsp+11E0h+arg_8], rbx
0x14000dcf5  mov     rax, cs:__security_cookie
0x14000dcfc  xor     rax, rsp
0x14000dcff  mov     [rbp+10E0h+var_40], rax
0x14000dd06  mov     rdi, r8
0x14000dd09  mov     r14, rcx
0x14000dd0c  lea     r13, [rcx+rdx*8]
0x14000dd10  xor     r15d, r15d
0x14000dd13  mov     r12d, r15d
0x14000dd16  mov     [rbp+10E0h+var_1138], r15
0x14000dd1a  mov     cl, [rdi+8]
0x14000dd1d  movzx   edx, word ptr [rdi+6]
0x14000dd21  movzx   eax, word ptr [rdi]
0x14000dd24  mov     [rsp+11E0h+var_1180], ax
0x14000dd29  movzx   eax, word ptr [rdi+2]
0x14000dd2d  mov     [rsp+11E0h+var_117E], ax
0x14000dd32  mov     al, [rdi+4]
0x14000dd35  mov     [rsp+11E0h+var_117C], al
0x14000dd39  mov     [rsp+11E0h+var_117A], dx
0x14000dd3e  mov     [rsp+11E0h+var_1178], cl
0x14000dd42  test    dx, dx
0x14000dd45  jz      short loc_14000DD64
0x14000dd47  mov     eax, edx
0x14000dd49  cmp     cl, 1
0x14000dd4c  jnz     short loc_14000DD54
0x14000dd4e  add     rax, 2
0x14000dd52  jmp     short loc_14000DD5D
0x14000dd54  cmp     cl, 2
0x14000dd57  jnz     short loc_14000DD5D
0x14000dd59  add     rax, 4
0x14000dd5d  mov     [rsp+11E0h+var_1170], rax
0x14000dd62  jmp     short loc_14000DD69
0x14000dd64  mov     [rsp+11E0h+var_1170], r15
0x14000dd69  mov     [rsp+11E0h+var_1168], r15
0x14000dd6e  xorps   xmm0, xmm0
0x14000dd71  movdqa  [rbp+10E0h+var_1160], xmm0
0x14000dd76  mov     [rbp+10E0h+lpMem], r15
0x14000dd7a  mov     [rbp+10E0h+var_1148], 0
0x14000dd80  mov     [rbp+10E0h+var_1146], r15b
0x14000dd84  mov     [rsp+11E0h+var_1198], r15d
0x14000dd89  mov     dword ptr [rsp+11E0h+var_11A0], 1000h
0x14000dd91  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000dd98  test    rax, rax
0x14000dd9b  jnz     short loc_14000DDE0
0x14000dd9d  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000dda4  test    rax, rax
0x14000dda7  jnz     short loc_14000DDBD
0x14000dda9  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x14000ddb0  call    cs:__imp_GetModuleHandleW
0x14000ddb6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000ddbd  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000ddc4  mov     rcx, rax; hModule
0x14000ddc7  call    cs:__imp_GetProcAddress
0x14000ddcd  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000ddd4  test    rax, rax
0x14000ddd7  jnz     short loc_14000DDE0
0x14000ddd9  mov     ebx, 0C0000139h
0x14000ddde  jmp     short loc_14000DE0A
0x14000dde0  lea     rcx, [rsp+11E0h+var_11A0]
0x14000dde5  mov     [rsp+11E0h+var_11B8], rcx
0x14000ddea  lea     rcx, [rbp+10E0h+var_1040]
0x14000ddf1  mov     [rsp+11E0h+var_11C0], rcx
0x14000ddf6  lea     r9, [rsp+11E0h+var_1198]
0x14000ddfb  xor     r8d, r8d
0x14000ddfe  xor     edx, edx
0x14000de00  mov     rcx, r14
0x14000de03  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000de08  mov     ebx, eax
0x14000de0a  mov     ecx, ebx; this
0x14000de0c  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000de11  test    ebx, ebx
0x14000de13  jz      short loc_14000DE23
0x14000de15  mov     eax, r15d
0x14000de18  mov     dword ptr [rsp+11E0h+var_11A0], eax
0x14000de1c  mov     [rsp+11E0h+var_1198], r15d
0x14000de21  jmp     short loc_14000DE27
0x14000de23  mov     eax, dword ptr [rsp+11E0h+var_11A0]
0x14000de27  mov     r8d, eax; unsigned __int64
0x14000de2a  mov     r9d, 1000h; unsigned __int64
0x14000de30  lea     rdx, [rbp+10E0h+var_1040]; void *
0x14000de37  lea     rcx, [rsp+11E0h+var_1180]; this
0x14000de3c  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x14000de41  cmp     byte ptr [rbp+10E0h+var_1148+1], r15b
0x14000de45  jnz     loc_14000E057
0x14000de4b  mov     [rbp+10E0h+var_1140], r15
0x14000de4f  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x14000de56  mov     [rbp+10E0h+var_10B8], rax
0x14000de5a  lea     rax, [rbp+10E0h+var_1140]
0x14000de5e  mov     [rbp+10E0h+var_10B0], rax
0x14000de62  lea     rax, [rbp+10E0h+var_1138]
0x14000de66  mov     [rbp+10E0h+var_10A8], rax
0x14000de6a  lea     rax, [rsp+11E0h+var_1180]
0x14000de6f  mov     [rbp+10E0h+var_10A0], rax
0x14000de73  lea     rax, [rbp+10E0h+var_10B8]
0x14000de77  mov     [rbp+10E0h+var_1050], rax
0x14000de7e  lea     rax, [rbp+10E0h+var_10C0]
0x14000de82  mov     [rbp+10E0h+var_10C8], rax
0x14000de86  mov     rax, [rdi+18h]
0x14000de8a  add     rax, 0Ah
0x14000de8e  mov     [rsp+11E0h+var_11A0], rax
0x14000de93  movzx   eax, word ptr [rdi+2]
0x14000de97  mov     [rbp+10E0h+var_1130], ax
0x14000de9b  mov     al, [rdi+4]
0x14000de9e  mov     [rbp+10E0h+var_112E], al
0x14000dea1  mov     [rbp+10E0h+var_112C], r15d
0x14000dea5  mov     [rbp+10E0h+var_1128], r15w
0x14000deaa  xorps   xmm0, xmm0
0x14000dead  movdqu  [rbp+10E0h+var_1120], xmm0
0x14000deb2  movzx   eax, word ptr [rdi+6]
0x14000deb6  mov     [rbp+10E0h+var_1110], ax
0x14000deba  mov     al, [rdi+8]
0x14000debd  mov     [rbp+10E0h+var_110E], al
0x14000dec0  mov     [rbp+10E0h+var_110C], r15d
0x14000dec4  mov     [rbp+10E0h+var_1108], r15w
0x14000dec9  movdqu  [rbp+10E0h+var_1100], xmm0
0x14000dece  jmp     loc_14000DF66
0x14000ded3  mov     ebx, r15d
0x14000ded6  mov     esi, [rbp+10E0h+var_112C]
0x14000ded9  test    esi, esi
0x14000dedb  jz      loc_14000DF66
0x14000dee1  mov     r15, qword ptr [rbp+10E0h+var_1120+8]
0x14000dee5  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000dee9  lea     rdx, [rsp+11E0h+var_11A0]; unsigned __int8 **
0x14000deee  lea     rcx, [rbp+10E0h+var_1110]; this
0x14000def2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000def7  test    al, al
0x14000def9  jz      short loc_14000DF63
0x14000defb  mov     eax, [rbp+10E0h+var_110C]
0x14000defe  mov     [rsp+11E0h+var_1190], eax
0x14000df02  movzx   eax, [rbp+10E0h+var_1108]
0x14000df06  mov     [rbp+10E0h+var_10F0], rax
0x14000df0a  mov     rax, qword ptr [rbp+10E0h+var_1100+8]
0x14000df0e  mov     [rbp+10E0h+var_10E8], rax
0x14000df12  movzx   eax, [rbp+10E0h+var_1128]
0x14000df16  mov     [rbp+10E0h+var_10E0], rax
0x14000df1a  mov     [rbp+10E0h+var_10D8], r15
0x14000df1e  mov     rcx, [rbp+10E0h+var_1050]; this
0x14000df25  test    rcx, rcx
0x14000df28  jz      loc_14000E0A2
0x14000df2e  mov     rax, [rcx]
0x14000df31  lea     rdx, [rsp+11E0h+var_1190]
0x14000df36  mov     [rsp+11E0h+var_11B8], rdx
0x14000df3b  lea     rdx, [rbp+10E0h+var_10F0]
0x14000df3f  mov     [rsp+11E0h+var_11C0], rdx
0x14000df44  lea     r9, [rbp+10E0h+var_10E8]
0x14000df48  lea     r8, [rbp+10E0h+var_10E0]
0x14000df4c  lea     rdx, [rbp+10E0h+var_10D8]
0x14000df50  mov     rax, [rax+20h]
0x14000df54  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df59  test    al, al
0x14000df5b  jz      short loc_14000DFD3
0x14000df5d  inc     ebx
0x14000df5f  cmp     ebx, esi
0x14000df61  jb      short loc_14000DEE5
0x14000df63  xor     r15d, r15d
0x14000df66  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000df6a  lea     rdx, [rsp+11E0h+var_11A0]; unsigned __int8 **
0x14000df6f  lea     rcx, [rbp+10E0h+var_1130]; this
0x14000df73  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000df78  test    al, al
0x14000df7a  jnz     loc_14000DED3
0x14000df80  mov     rcx, [rbp+10E0h+var_1050]
0x14000df87  test    rcx, rcx
0x14000df8a  jz      short loc_14000DF98
0x14000df8c  mov     rax, [rcx]
0x14000df8f  mov     rax, [rax+18h]
0x14000df93  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000df98  mov     bl, 1
0x14000df9a  cmp     byte ptr [rbp+10E0h+var_1148], r15b
0x14000df9e  jz      short loc_14000E015
0x14000dfa0  mov     eax, [rsp+11E0h+var_1198]
0x14000dfa4  mov     rdx, [rsp+11E0h+var_1168]
0x14000dfa9  mov     r8d, dword ptr [rbp+10E0h+var_1160]
0x14000dfad  sub     r8d, edx
0x14000dfb0  mov     [rsp+11E0h+var_11B0], 1
0x14000dfb8  mov     dword ptr [rsp+11E0h+var_11B8], eax
0x14000dfbc  mov     rcx, r14
0x14000dfbf  call    wil_details_NtUpdateWnfStateData
0x14000dfc4  cmp     eax, 0C0000001h
0x14000dfc9  jnz     short loc_14000DFF3
0x14000dfcb  inc     r12
0x14000dfce  mov     bl, r15b
0x14000dfd1  jmp     short loc_14000E021
0x14000dfd3  mov     rcx, [rbp+10E0h+var_1050]
0x14000dfda  xor     r15d, r15d
0x14000dfdd  test    rcx, rcx
0x14000dfe0  jz      short loc_14000DFEE
0x14000dfe2  mov     rax, [rcx]
0x14000dfe5  mov     rax, [rax+18h]
0x14000dfe9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000dfee  mov     bl, r15b
0x14000dff1  jmp     short loc_14000DF9A
0x14000dff3  test    eax, eax
0x14000dff5  jz      short loc_14000E015
0x14000dff7  mov     rdx, [rsp+11E0h+var_1168]
0x14000dffc  mov     r8d, dword ptr [rbp+10E0h+var_1160]
0x14000e000  sub     r8d, edx
0x14000e003  mov     [rsp+11E0h+var_11B0], r15d
0x14000e008  mov     dword ptr [rsp+11E0h+var_11B8], r15d
0x14000e00d  mov     rcx, r14
0x14000e010  call    wil_details_NtUpdateWnfStateData
0x14000e015  add     r14, 8
0x14000e019  mov     rax, [rbp+10E0h+var_1140]
0x14000e01d  mov     [rbp+10E0h+var_1138], rax
0x14000e021  mov     rsi, [rbp+10E0h+lpMem]
0x14000e025  mov     [rbp+10E0h+lpMem], r15
0x14000e029  test    rsi, rsi
0x14000e02c  jz      short loc_14000E042
0x14000e02e  call    cs:__imp_GetProcessHeap
0x14000e034  mov     rcx, rax; hHeap
0x14000e037  mov     r8, rsi; lpMem
0x14000e03a  xor     edx, edx; dwFlags
0x14000e03c  call    cs:__imp_HeapFree
0x14000e042  test    bl, bl
0x14000e044  jnz     short loc_14000E078
0x14000e046  cmp     r14, r13
0x14000e049  jnb     short loc_14000E078
0x14000e04b  cmp     r12, 32h ; '2'
0x14000e04f  jb      loc_14000DD1A
0x14000e055  jmp     short loc_14000E078
0x14000e057  mov     rbx, [rbp+10E0h+lpMem]
0x14000e05b  mov     [rbp+10E0h+lpMem], r15
0x14000e05f  test    rbx, rbx
0x14000e062  jz      short loc_14000E078
0x14000e064  call    cs:__imp_GetProcessHeap
0x14000e06a  mov     rcx, rax; hHeap
0x14000e06d  mov     r8, rbx; lpMem
0x14000e070  xor     edx, edx; dwFlags
0x14000e072  call    cs:__imp_HeapFree
0x14000e078  mov     rcx, [rbp+10E0h+var_40]
0x14000e07f  xor     rcx, rsp; StackCookie
0x14000e082  call    __security_check_cookie
0x14000e087  mov     rbx, [rsp+11E0h+arg_8]
0x14000e08f  add     rsp, 11B0h
0x14000e096  pop     r15
0x14000e098  pop     r14
0x14000e09a  pop     r13
0x14000e09c  pop     r12
0x14000e09e  pop     rdi
0x14000e09f  pop     rsi
0x14000e0a0  pop     rbp
0x14000e0a1  retn
0x14000e0a2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
