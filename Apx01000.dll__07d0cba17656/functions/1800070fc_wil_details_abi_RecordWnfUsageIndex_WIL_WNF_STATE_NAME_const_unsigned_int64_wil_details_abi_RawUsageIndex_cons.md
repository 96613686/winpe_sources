# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800070fc`
- end: `0x1800074d4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800065dc`

## callees

- `0x180001d30`
- `0x1800060d8`
- `0x1800064dc`
- `0x1800070fc`
- `0x180007ad4`
- `0x180008fcc`
- `0x1800097f0`
- `0x180029820`
- `0x18002a010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800071dc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071f3`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x1800071f3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007468`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000749e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007468`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000749e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000745a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007490`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000745a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007490`

## string_xrefs

- `0x1800071d5`: `ntdll.dll`

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
0x1800070fc  mov     [rsp-8+arg_8], rbx
0x180007101  push    rbp
0x180007102  push    rsi
0x180007103  push    rdi
0x180007104  push    r12
0x180007106  push    r13
0x180007108  push    r14
0x18000710a  push    r15
0x18000710c  lea     rbp, [rsp-10A0h]
0x180007114  mov     eax, 11A0h
0x180007119  call    _alloca_probe
0x18000711e  sub     rsp, rax
0x180007121  mov     rax, cs:__security_cookie
0x180007128  xor     rax, rsp
0x18000712b  mov     [rbp+10D0h+var_40], rax
0x180007132  mov     rdi, r8
0x180007135  mov     r14, rcx
0x180007138  lea     r13, [rcx+rdx*8]
0x18000713c  xor     r15d, r15d
0x18000713f  mov     r12d, r15d
0x180007142  mov     [rbp+10D0h+var_1128], r15
0x180007146  mov     cl, [rdi+8]
0x180007149  movzx   edx, word ptr [rdi+6]
0x18000714d  movzx   eax, word ptr [rdi]
0x180007150  mov     [rsp+11D0h+var_1170], ax
0x180007155  movzx   eax, word ptr [rdi+2]
0x180007159  mov     [rsp+11D0h+var_116E], ax
0x18000715e  mov     al, [rdi+4]
0x180007161  mov     [rsp+11D0h+var_116C], al
0x180007165  mov     [rsp+11D0h+var_116A], dx
0x18000716a  mov     [rsp+11D0h+var_1168], cl
0x18000716e  test    dx, dx
0x180007171  jz      short loc_180007190
0x180007173  mov     eax, edx
0x180007175  cmp     cl, 1
0x180007178  jnz     short loc_180007180
0x18000717a  add     rax, 2
0x18000717e  jmp     short loc_180007189
0x180007180  cmp     cl, 2
0x180007183  jnz     short loc_180007189
0x180007185  add     rax, 4
0x180007189  mov     [rsp+11D0h+var_1160], rax
0x18000718e  jmp     short loc_180007195
0x180007190  mov     [rsp+11D0h+var_1160], r15
0x180007195  mov     [rsp+11D0h+var_1158], r15
0x18000719a  xorps   xmm0, xmm0
0x18000719d  movdqa  [rbp+10D0h+var_1150], xmm0
0x1800071a2  mov     [rbp+10D0h+lpMem], r15
0x1800071a6  mov     [rbp+10D0h+var_1138], 0
0x1800071ac  mov     [rbp+10D0h+var_1136], r15b
0x1800071b0  mov     [rsp+11D0h+var_1188], r15d
0x1800071b5  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1800071bd  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800071c4  test    rax, rax
0x1800071c7  jnz     short loc_18000720C
0x1800071c9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800071d0  test    rax, rax
0x1800071d3  jnz     short loc_1800071E9
0x1800071d5  lea     rcx, ModuleName; "ntdll.dll"
0x1800071dc  call    cs:__imp_GetModuleHandleW
0x1800071e2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800071e9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800071f0  mov     rcx, rax; hModule
0x1800071f3  call    cs:__imp_GetProcAddress
0x1800071f9  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180007200  test    rax, rax
0x180007203  jnz     short loc_18000720C
0x180007205  mov     ebx, 0C0000139h
0x18000720a  jmp     short loc_180007236
0x18000720c  lea     rcx, [rsp+11D0h+var_1190]
0x180007211  mov     [rsp+11D0h+var_11A8], rcx
0x180007216  lea     rcx, [rbp+10D0h+var_1040]
0x18000721d  mov     [rsp+11D0h+var_11B0], rcx
0x180007222  lea     r9, [rsp+11D0h+var_1188]
0x180007227  xor     r8d, r8d
0x18000722a  xor     edx, edx
0x18000722c  mov     rcx, r14
0x18000722f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007234  mov     ebx, eax
0x180007236  mov     ecx, ebx; this
0x180007238  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000723d  test    ebx, ebx
0x18000723f  jz      short loc_18000724F
0x180007241  mov     eax, r15d
0x180007244  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180007248  mov     [rsp+11D0h+var_1188], r15d
0x18000724d  jmp     short loc_180007253
0x18000724f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180007253  mov     r8d, eax; unsigned __int64
0x180007256  mov     r9d, 1000h; unsigned __int64
0x18000725c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180007263  lea     rcx, [rsp+11D0h+var_1170]; this
0x180007268  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000726d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180007271  jnz     loc_180007483
0x180007277  mov     [rbp+10D0h+var_1130], r15
0x18000727b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180007282  mov     [rbp+10D0h+var_10B0], rax
0x180007286  lea     rax, [rbp+10D0h+var_1130]
0x18000728a  mov     [rbp+10D0h+var_10A8], rax
0x18000728e  lea     rax, [rbp+10D0h+var_1128]
0x180007292  mov     [rbp+10D0h+var_10A0], rax
0x180007296  lea     rax, [rsp+11D0h+var_1170]
0x18000729b  mov     [rbp+10D0h+var_1098], rax
0x18000729f  lea     rax, [rbp+10D0h+var_10B0]
0x1800072a3  mov     [rbp+10D0h+var_1048], rax
0x1800072aa  lea     rax, [rbp+10D0h+var_10B8]
0x1800072ae  mov     [rbp+10D0h+var_10C0], rax
0x1800072b2  mov     rax, [rdi+18h]
0x1800072b6  add     rax, 0Ah
0x1800072ba  mov     [rsp+11D0h+var_1190], rax
0x1800072bf  movzx   eax, word ptr [rdi+2]
0x1800072c3  mov     [rbp+10D0h+var_1120], ax
0x1800072c7  mov     al, [rdi+4]
0x1800072ca  mov     [rbp+10D0h+var_111E], al
0x1800072cd  mov     [rbp+10D0h+var_111C], r15d
0x1800072d1  mov     [rbp+10D0h+var_1118], r15w
0x1800072d6  xorps   xmm0, xmm0
0x1800072d9  movdqu  [rbp+10D0h+var_1110], xmm0
0x1800072de  movzx   eax, word ptr [rdi+6]
0x1800072e2  mov     [rbp+10D0h+var_1100], ax
0x1800072e6  mov     al, [rdi+8]
0x1800072e9  mov     [rbp+10D0h+var_10FE], al
0x1800072ec  mov     [rbp+10D0h+var_10FC], r15d
0x1800072f0  mov     [rbp+10D0h+var_10F8], r15w
0x1800072f5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800072fa  jmp     loc_180007392
0x1800072ff  mov     ebx, r15d
0x180007302  mov     esi, [rbp+10D0h+var_111C]
0x180007305  test    esi, esi
0x180007307  jz      loc_180007392
0x18000730d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180007311  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007315  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000731a  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000731e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007323  test    al, al
0x180007325  jz      short loc_18000738F
0x180007327  mov     eax, [rbp+10D0h+var_10FC]
0x18000732a  mov     [rsp+11D0h+var_1180], eax
0x18000732e  movzx   eax, [rbp+10D0h+var_10F8]
0x180007332  mov     [rbp+10D0h+var_10E0], rax
0x180007336  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000733a  mov     [rbp+10D0h+var_10D8], rax
0x18000733e  movzx   eax, [rbp+10D0h+var_1118]
0x180007342  mov     [rbp+10D0h+var_10D0], rax
0x180007346  mov     [rbp+10D0h+var_10C8], r15
0x18000734a  mov     rcx, [rbp+10D0h+var_1048]; this
0x180007351  test    rcx, rcx
0x180007354  jz      loc_1800074CE
0x18000735a  mov     rax, [rcx]
0x18000735d  lea     rdx, [rsp+11D0h+var_1180]
0x180007362  mov     [rsp+11D0h+var_11A8], rdx
0x180007367  lea     rdx, [rbp+10D0h+var_10E0]
0x18000736b  mov     [rsp+11D0h+var_11B0], rdx
0x180007370  lea     r9, [rbp+10D0h+var_10D8]
0x180007374  lea     r8, [rbp+10D0h+var_10D0]
0x180007378  lea     rdx, [rbp+10D0h+var_10C8]
0x18000737c  mov     rax, [rax+20h]
0x180007380  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007385  test    al, al
0x180007387  jz      short loc_1800073FF
0x180007389  inc     ebx
0x18000738b  cmp     ebx, esi
0x18000738d  jb      short loc_180007311
0x18000738f  xor     r15d, r15d
0x180007392  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007396  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000739b  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000739f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800073a4  test    al, al
0x1800073a6  jnz     loc_1800072FF
0x1800073ac  mov     rcx, [rbp+10D0h+var_1048]
0x1800073b3  test    rcx, rcx
0x1800073b6  jz      short loc_1800073C4
0x1800073b8  mov     rax, [rcx]
0x1800073bb  mov     rax, [rax+18h]
0x1800073bf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800073c4  mov     bl, 1
0x1800073c6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x1800073ca  jz      short loc_180007441
0x1800073cc  mov     eax, [rsp+11D0h+var_1188]
0x1800073d0  mov     rdx, [rsp+11D0h+var_1158]
0x1800073d5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800073d9  sub     r8d, edx
0x1800073dc  mov     [rsp+11D0h+var_11A0], 1
0x1800073e4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800073e8  mov     rcx, r14
0x1800073eb  call    wil_details_NtUpdateWnfStateData
0x1800073f0  cmp     eax, 0C0000001h
0x1800073f5  jnz     short loc_18000741F
0x1800073f7  inc     r12
0x1800073fa  mov     bl, r15b
0x1800073fd  jmp     short loc_18000744D
0x1800073ff  mov     rcx, [rbp+10D0h+var_1048]
0x180007406  xor     r15d, r15d
0x180007409  test    rcx, rcx
0x18000740c  jz      short loc_18000741A
0x18000740e  mov     rax, [rcx]
0x180007411  mov     rax, [rax+18h]
0x180007415  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000741a  mov     bl, r15b
0x18000741d  jmp     short loc_1800073C6
0x18000741f  test    eax, eax
0x180007421  jz      short loc_180007441
0x180007423  mov     rdx, [rsp+11D0h+var_1158]
0x180007428  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000742c  sub     r8d, edx
0x18000742f  mov     [rsp+11D0h+var_11A0], r15d
0x180007434  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180007439  mov     rcx, r14
0x18000743c  call    wil_details_NtUpdateWnfStateData
0x180007441  add     r14, 8
0x180007445  mov     rax, [rbp+10D0h+var_1130]
0x180007449  mov     [rbp+10D0h+var_1128], rax
0x18000744d  mov     rsi, [rbp+10D0h+lpMem]
0x180007451  mov     [rbp+10D0h+lpMem], r15
0x180007455  test    rsi, rsi
0x180007458  jz      short loc_18000746E
0x18000745a  call    cs:__imp_GetProcessHeap
0x180007460  mov     rcx, rax; hHeap
0x180007463  mov     r8, rsi; lpMem
0x180007466  xor     edx, edx; dwFlags
0x180007468  call    cs:__imp_HeapFree
0x18000746e  test    bl, bl
0x180007470  jnz     short loc_1800074A4
0x180007472  cmp     r14, r13
0x180007475  jnb     short loc_1800074A4
0x180007477  cmp     r12, 32h ; '2'
0x18000747b  jb      loc_180007146
0x180007481  jmp     short loc_1800074A4
0x180007483  mov     rbx, [rbp+10D0h+lpMem]
0x180007487  mov     [rbp+10D0h+lpMem], r15
0x18000748b  test    rbx, rbx
0x18000748e  jz      short loc_1800074A4
0x180007490  call    cs:__imp_GetProcessHeap
0x180007496  mov     rcx, rax; hHeap
0x180007499  mov     r8, rbx; lpMem
0x18000749c  xor     edx, edx; dwFlags
0x18000749e  call    cs:__imp_HeapFree
0x1800074a4  mov     rcx, [rbp+10D0h+var_40]
0x1800074ab  xor     rcx, rsp; StackCookie
0x1800074ae  call    __security_check_cookie
0x1800074b3  mov     rbx, [rsp+11D0h+arg_8]
0x1800074bb  add     rsp, 11A0h
0x1800074c2  pop     r15
0x1800074c4  pop     r14
0x1800074c6  pop     r13
0x1800074c8  pop     r12
0x1800074ca  pop     rdi
0x1800074cb  pop     rsi
0x1800074cc  pop     rbp
0x1800074cd  retn
0x1800074ce  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
