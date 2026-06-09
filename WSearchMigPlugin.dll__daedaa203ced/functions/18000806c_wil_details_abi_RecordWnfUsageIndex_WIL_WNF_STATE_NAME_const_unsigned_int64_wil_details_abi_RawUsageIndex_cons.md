# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000806c`
- end: `0x180008450`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `996`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x18000757c`

## callees

- `0x1800026f0`
- `0x180006fc4`
- `0x18000747c`
- `0x18000806c`
- `0x180008a00`
- `0x180009efc`
- `0x18000a730`
- `0x180016d70`
- `0x180018010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180008158`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x180008158`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000816f`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x18000816f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000840c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800083d6`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000840c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000841a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800083e4`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000841a`

## string_xrefs

- `0x180008151`: `ntdll.dll`

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
0x18000806c  push    rbp
0x18000806e  push    rsi
0x18000806f  push    rdi
0x180008070  push    r12
0x180008072  push    r13
0x180008074  push    r14
0x180008076  push    r15
0x180008078  lea     rbp, [rsp-10B0h]
0x180008080  mov     eax, 11B0h
0x180008085  call    _alloca_probe
0x18000808a  sub     rsp, rax
0x18000808d  mov     [rbp+10E0h+var_10D0], 0FFFFFFFFFFFFFFFEh
0x180008095  mov     [rsp+11E0h+arg_8], rbx
0x18000809d  mov     rax, cs:__security_cookie
0x1800080a4  xor     rax, rsp
0x1800080a7  mov     [rbp+10E0h+var_40], rax
0x1800080ae  mov     rdi, r8
0x1800080b1  mov     r14, rcx
0x1800080b4  lea     r13, [rcx+rdx*8]
0x1800080b8  xor     r15d, r15d
0x1800080bb  mov     r12d, r15d
0x1800080be  mov     [rbp+10E0h+var_1138], r15
0x1800080c2  mov     cl, [rdi+8]
0x1800080c5  movzx   edx, word ptr [rdi+6]
0x1800080c9  movzx   eax, word ptr [rdi]
0x1800080cc  mov     [rsp+11E0h+var_1180], ax
0x1800080d1  movzx   eax, word ptr [rdi+2]
0x1800080d5  mov     [rsp+11E0h+var_117E], ax
0x1800080da  mov     al, [rdi+4]
0x1800080dd  mov     [rsp+11E0h+var_117C], al
0x1800080e1  mov     [rsp+11E0h+var_117A], dx
0x1800080e6  mov     [rsp+11E0h+var_1178], cl
0x1800080ea  test    dx, dx
0x1800080ed  jz      short loc_18000810C
0x1800080ef  mov     eax, edx
0x1800080f1  cmp     cl, 1
0x1800080f4  jnz     short loc_1800080FC
0x1800080f6  add     rax, 2
0x1800080fa  jmp     short loc_180008105
0x1800080fc  cmp     cl, 2
0x1800080ff  jnz     short loc_180008105
0x180008101  add     rax, 4
0x180008105  mov     [rsp+11E0h+var_1170], rax
0x18000810a  jmp     short loc_180008111
0x18000810c  mov     [rsp+11E0h+var_1170], r15
0x180008111  mov     [rsp+11E0h+var_1168], r15
0x180008116  xorps   xmm0, xmm0
0x180008119  movdqa  [rbp+10E0h+var_1160], xmm0
0x18000811e  mov     [rbp+10E0h+lpMem], r15
0x180008122  mov     [rbp+10E0h+var_1148], 0
0x180008128  mov     [rbp+10E0h+var_1146], r15b
0x18000812c  mov     [rsp+11E0h+var_1198], r15d
0x180008131  mov     dword ptr [rsp+11E0h+var_11A0], 1000h
0x180008139  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008140  test    rax, rax
0x180008143  jnz     short loc_180008188
0x180008145  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000814c  test    rax, rax
0x18000814f  jnz     short loc_180008165
0x180008151  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008158  call    cs:__imp_GetModuleHandleW
0x18000815e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008165  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000816c  mov     rcx, rax; hModule
0x18000816f  call    cs:__imp_GetProcAddress
0x180008175  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000817c  test    rax, rax
0x18000817f  jnz     short loc_180008188
0x180008181  mov     ebx, 0C0000139h
0x180008186  jmp     short loc_1800081B2
0x180008188  lea     rcx, [rsp+11E0h+var_11A0]
0x18000818d  mov     [rsp+11E0h+var_11B8], rcx
0x180008192  lea     rcx, [rbp+10E0h+var_1040]
0x180008199  mov     [rsp+11E0h+var_11C0], rcx
0x18000819e  lea     r9, [rsp+11E0h+var_1198]
0x1800081a3  xor     r8d, r8d
0x1800081a6  xor     edx, edx
0x1800081a8  mov     rcx, r14
0x1800081ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800081b0  mov     ebx, eax
0x1800081b2  mov     ecx, ebx; this
0x1800081b4  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800081b9  test    ebx, ebx
0x1800081bb  jz      short loc_1800081CB
0x1800081bd  mov     eax, r15d
0x1800081c0  mov     dword ptr [rsp+11E0h+var_11A0], eax
0x1800081c4  mov     [rsp+11E0h+var_1198], r15d
0x1800081c9  jmp     short loc_1800081CF
0x1800081cb  mov     eax, dword ptr [rsp+11E0h+var_11A0]
0x1800081cf  mov     r8d, eax; unsigned __int64
0x1800081d2  mov     r9d, 1000h; unsigned __int64
0x1800081d8  lea     rdx, [rbp+10E0h+var_1040]; void *
0x1800081df  lea     rcx, [rsp+11E0h+var_1180]; this
0x1800081e4  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1800081e9  cmp     byte ptr [rbp+10E0h+var_1148+1], r15b
0x1800081ed  jnz     loc_1800083FF
0x1800081f3  mov     [rbp+10E0h+var_1140], r15
0x1800081f7  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800081fe  mov     [rbp+10E0h+var_10B8], rax
0x180008202  lea     rax, [rbp+10E0h+var_1140]
0x180008206  mov     [rbp+10E0h+var_10B0], rax
0x18000820a  lea     rax, [rbp+10E0h+var_1138]
0x18000820e  mov     [rbp+10E0h+var_10A8], rax
0x180008212  lea     rax, [rsp+11E0h+var_1180]
0x180008217  mov     [rbp+10E0h+var_10A0], rax
0x18000821b  lea     rax, [rbp+10E0h+var_10B8]
0x18000821f  mov     [rbp+10E0h+var_1050], rax
0x180008226  lea     rax, [rbp+10E0h+var_10C0]
0x18000822a  mov     [rbp+10E0h+var_10C8], rax
0x18000822e  mov     rax, [rdi+18h]
0x180008232  add     rax, 0Ah
0x180008236  mov     [rsp+11E0h+var_11A0], rax
0x18000823b  movzx   eax, word ptr [rdi+2]
0x18000823f  mov     [rbp+10E0h+var_1130], ax
0x180008243  mov     al, [rdi+4]
0x180008246  mov     [rbp+10E0h+var_112E], al
0x180008249  mov     [rbp+10E0h+var_112C], r15d
0x18000824d  mov     [rbp+10E0h+var_1128], r15w
0x180008252  xorps   xmm0, xmm0
0x180008255  movdqu  [rbp+10E0h+var_1120], xmm0
0x18000825a  movzx   eax, word ptr [rdi+6]
0x18000825e  mov     [rbp+10E0h+var_1110], ax
0x180008262  mov     al, [rdi+8]
0x180008265  mov     [rbp+10E0h+var_110E], al
0x180008268  mov     [rbp+10E0h+var_110C], r15d
0x18000826c  mov     [rbp+10E0h+var_1108], r15w
0x180008271  movdqu  [rbp+10E0h+var_1100], xmm0
0x180008276  jmp     loc_18000830E
0x18000827b  mov     ebx, r15d
0x18000827e  mov     esi, [rbp+10E0h+var_112C]
0x180008281  test    esi, esi
0x180008283  jz      loc_18000830E
0x180008289  mov     r15, qword ptr [rbp+10E0h+var_1120+8]
0x18000828d  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008291  lea     rdx, [rsp+11E0h+var_11A0]; unsigned __int8 **
0x180008296  lea     rcx, [rbp+10E0h+var_1110]; this
0x18000829a  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000829f  test    al, al
0x1800082a1  jz      short loc_18000830B
0x1800082a3  mov     eax, [rbp+10E0h+var_110C]
0x1800082a6  mov     [rsp+11E0h+var_1190], eax
0x1800082aa  movzx   eax, [rbp+10E0h+var_1108]
0x1800082ae  mov     [rbp+10E0h+var_10F0], rax
0x1800082b2  mov     rax, qword ptr [rbp+10E0h+var_1100+8]
0x1800082b6  mov     [rbp+10E0h+var_10E8], rax
0x1800082ba  movzx   eax, [rbp+10E0h+var_1128]
0x1800082be  mov     [rbp+10E0h+var_10E0], rax
0x1800082c2  mov     [rbp+10E0h+var_10D8], r15
0x1800082c6  mov     rcx, [rbp+10E0h+var_1050]; this
0x1800082cd  test    rcx, rcx
0x1800082d0  jz      loc_18000844A
0x1800082d6  mov     rax, [rcx]
0x1800082d9  lea     rdx, [rsp+11E0h+var_1190]
0x1800082de  mov     [rsp+11E0h+var_11B8], rdx
0x1800082e3  lea     rdx, [rbp+10E0h+var_10F0]
0x1800082e7  mov     [rsp+11E0h+var_11C0], rdx
0x1800082ec  lea     r9, [rbp+10E0h+var_10E8]
0x1800082f0  lea     r8, [rbp+10E0h+var_10E0]
0x1800082f4  lea     rdx, [rbp+10E0h+var_10D8]
0x1800082f8  mov     rax, [rax+20h]
0x1800082fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008301  test    al, al
0x180008303  jz      short loc_18000837B
0x180008305  inc     ebx
0x180008307  cmp     ebx, esi
0x180008309  jb      short loc_18000828D
0x18000830b  xor     r15d, r15d
0x18000830e  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008312  lea     rdx, [rsp+11E0h+var_11A0]; unsigned __int8 **
0x180008317  lea     rcx, [rbp+10E0h+var_1130]; this
0x18000831b  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008320  test    al, al
0x180008322  jnz     loc_18000827B
0x180008328  mov     rcx, [rbp+10E0h+var_1050]
0x18000832f  test    rcx, rcx
0x180008332  jz      short loc_180008340
0x180008334  mov     rax, [rcx]
0x180008337  mov     rax, [rax+18h]
0x18000833b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008340  mov     bl, 1
0x180008342  cmp     byte ptr [rbp+10E0h+var_1148], r15b
0x180008346  jz      short loc_1800083BD
0x180008348  mov     eax, [rsp+11E0h+var_1198]
0x18000834c  mov     rdx, [rsp+11E0h+var_1168]
0x180008351  mov     r8d, dword ptr [rbp+10E0h+var_1160]
0x180008355  sub     r8d, edx
0x180008358  mov     [rsp+11E0h+var_11B0], 1
0x180008360  mov     dword ptr [rsp+11E0h+var_11B8], eax
0x180008364  mov     rcx, r14
0x180008367  call    wil_details_NtUpdateWnfStateData
0x18000836c  cmp     eax, 0C0000001h
0x180008371  jnz     short loc_18000839B
0x180008373  inc     r12
0x180008376  mov     bl, r15b
0x180008379  jmp     short loc_1800083C9
0x18000837b  mov     rcx, [rbp+10E0h+var_1050]
0x180008382  xor     r15d, r15d
0x180008385  test    rcx, rcx
0x180008388  jz      short loc_180008396
0x18000838a  mov     rax, [rcx]
0x18000838d  mov     rax, [rax+18h]
0x180008391  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008396  mov     bl, r15b
0x180008399  jmp     short loc_180008342
0x18000839b  test    eax, eax
0x18000839d  jz      short loc_1800083BD
0x18000839f  mov     rdx, [rsp+11E0h+var_1168]
0x1800083a4  mov     r8d, dword ptr [rbp+10E0h+var_1160]
0x1800083a8  sub     r8d, edx
0x1800083ab  mov     [rsp+11E0h+var_11B0], r15d
0x1800083b0  mov     dword ptr [rsp+11E0h+var_11B8], r15d
0x1800083b5  mov     rcx, r14
0x1800083b8  call    wil_details_NtUpdateWnfStateData
0x1800083bd  add     r14, 8
0x1800083c1  mov     rax, [rbp+10E0h+var_1140]
0x1800083c5  mov     [rbp+10E0h+var_1138], rax
0x1800083c9  mov     rsi, [rbp+10E0h+lpMem]
0x1800083cd  mov     [rbp+10E0h+lpMem], r15
0x1800083d1  test    rsi, rsi
0x1800083d4  jz      short loc_1800083EA
0x1800083d6  call    cs:__imp_GetProcessHeap
0x1800083dc  mov     rcx, rax; hHeap
0x1800083df  mov     r8, rsi; lpMem
0x1800083e2  xor     edx, edx; dwFlags
0x1800083e4  call    cs:__imp_HeapFree
0x1800083ea  test    bl, bl
0x1800083ec  jnz     short loc_180008420
0x1800083ee  cmp     r14, r13
0x1800083f1  jnb     short loc_180008420
0x1800083f3  cmp     r12, 32h ; '2'
0x1800083f7  jb      loc_1800080C2
0x1800083fd  jmp     short loc_180008420
0x1800083ff  mov     rbx, [rbp+10E0h+lpMem]
0x180008403  mov     [rbp+10E0h+lpMem], r15
0x180008407  test    rbx, rbx
0x18000840a  jz      short loc_180008420
0x18000840c  call    cs:__imp_GetProcessHeap
0x180008412  mov     rcx, rax; hHeap
0x180008415  mov     r8, rbx; lpMem
0x180008418  xor     edx, edx; dwFlags
0x18000841a  call    cs:__imp_HeapFree
0x180008420  mov     rcx, [rbp+10E0h+var_40]
0x180008427  xor     rcx, rsp; StackCookie
0x18000842a  call    __security_check_cookie
0x18000842f  mov     rbx, [rsp+11E0h+arg_8]
0x180008437  add     rsp, 11B0h
0x18000843e  pop     r15
0x180008440  pop     r14
0x180008442  pop     r13
0x180008444  pop     r12
0x180008446  pop     rdi
0x180008447  pop     rsi
0x180008448  pop     rbp
0x180008449  retn
0x18000844a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
