# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000701c`
- end: `0x1800073f4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180006508`

## callees

- `0x180001670`
- `0x180005e48`
- `0x180006408`
- `0x18000701c`
- `0x180007c74`
- `0x18000916c`
- `0x18000ebd0`
- `0x1800136a0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007388`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073be`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007388`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800073be`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000737a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073b0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000737a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800073b0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007113`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180007113`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800070fc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x1800070fc`

## string_xrefs

- `0x1800070f5`: `ntdll.dll`

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
    v57[0] = wistd::__function::Z::$$A6A_NPEAX131I::Z::__func<`wil::details_abi::RecordWnfUsageIndex'::`4'::_lambda_1_,AXPEBU__WIL__WNF_STATE_NAME,unsigned __int64,wil::details_abi::RawUsageIndex const &>::`vftable';
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
0x18000701c  mov     [rsp-8+arg_8], rbx
0x180007021  push    rbp
0x180007022  push    rsi
0x180007023  push    rdi
0x180007024  push    r12
0x180007026  push    r13
0x180007028  push    r14
0x18000702a  push    r15
0x18000702c  lea     rbp, [rsp-10A0h]
0x180007034  mov     eax, 11A0h
0x180007039  call    _alloca_probe
0x18000703e  sub     rsp, rax
0x180007041  mov     rax, cs:__security_cookie
0x180007048  xor     rax, rsp
0x18000704b  mov     [rbp+10D0h+var_40], rax
0x180007052  mov     rdi, r8
0x180007055  mov     r14, rcx
0x180007058  lea     r13, [rcx+rdx*8]
0x18000705c  xor     r15d, r15d
0x18000705f  mov     r12d, r15d
0x180007062  mov     [rbp+10D0h+var_1128], r15
0x180007066  mov     cl, [rdi+8]
0x180007069  movzx   edx, word ptr [rdi+6]
0x18000706d  movzx   eax, word ptr [rdi]
0x180007070  mov     [rsp+11D0h+var_1170], ax
0x180007075  movzx   eax, word ptr [rdi+2]
0x180007079  mov     [rsp+11D0h+var_116E], ax
0x18000707e  mov     al, [rdi+4]
0x180007081  mov     [rsp+11D0h+var_116C], al
0x180007085  mov     [rsp+11D0h+var_116A], dx
0x18000708a  mov     [rsp+11D0h+var_1168], cl
0x18000708e  test    dx, dx
0x180007091  jz      short loc_1800070B0
0x180007093  mov     eax, edx
0x180007095  cmp     cl, 1
0x180007098  jnz     short loc_1800070A0
0x18000709a  add     rax, 2
0x18000709e  jmp     short loc_1800070A9
0x1800070a0  cmp     cl, 2
0x1800070a3  jnz     short loc_1800070A9
0x1800070a5  add     rax, 4
0x1800070a9  mov     [rsp+11D0h+var_1160], rax
0x1800070ae  jmp     short loc_1800070B5
0x1800070b0  mov     [rsp+11D0h+var_1160], r15
0x1800070b5  mov     [rsp+11D0h+var_1158], r15
0x1800070ba  xorps   xmm0, xmm0
0x1800070bd  movdqa  [rbp+10D0h+var_1150], xmm0
0x1800070c2  mov     [rbp+10D0h+lpMem], r15
0x1800070c6  mov     [rbp+10D0h+var_1138], 0
0x1800070cc  mov     [rbp+10D0h+var_1136], r15b
0x1800070d0  mov     [rsp+11D0h+var_1188], r15d
0x1800070d5  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1800070dd  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800070e4  test    rax, rax
0x1800070e7  jnz     short loc_18000712C
0x1800070e9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800070f0  test    rax, rax
0x1800070f3  jnz     short loc_180007109
0x1800070f5  lea     rcx, ModuleName; "ntdll.dll"
0x1800070fc  call    cs:__imp_GetModuleHandleW
0x180007102  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180007109  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180007110  mov     rcx, rax; hModule
0x180007113  call    cs:__imp_GetProcAddress
0x180007119  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180007120  test    rax, rax
0x180007123  jnz     short loc_18000712C
0x180007125  mov     ebx, 0C0000139h
0x18000712a  jmp     short loc_180007156
0x18000712c  lea     rcx, [rsp+11D0h+var_1190]
0x180007131  mov     [rsp+11D0h+var_11A8], rcx
0x180007136  lea     rcx, [rbp+10D0h+var_1040]
0x18000713d  mov     [rsp+11D0h+var_11B0], rcx
0x180007142  lea     r9, [rsp+11D0h+var_1188]
0x180007147  xor     r8d, r8d
0x18000714a  xor     edx, edx
0x18000714c  mov     rcx, r14
0x18000714f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007154  mov     ebx, eax
0x180007156  mov     ecx, ebx; this
0x180007158  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000715d  test    ebx, ebx
0x18000715f  jz      short loc_18000716F
0x180007161  mov     eax, r15d
0x180007164  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180007168  mov     [rsp+11D0h+var_1188], r15d
0x18000716d  jmp     short loc_180007173
0x18000716f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180007173  mov     r8d, eax; unsigned __int64
0x180007176  mov     r9d, 1000h; unsigned __int64
0x18000717c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180007183  lea     rcx, [rsp+11D0h+var_1170]; this
0x180007188  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000718d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180007191  jnz     loc_1800073A3
0x180007197  mov     [rbp+10D0h+var_1130], r15
0x18000719b  lea     rax, ??_7?$__func@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@$$A6A_NPEAX131I@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800071a2  mov     [rbp+10D0h+var_10B0], rax
0x1800071a6  lea     rax, [rbp+10D0h+var_1130]
0x1800071aa  mov     [rbp+10D0h+var_10A8], rax
0x1800071ae  lea     rax, [rbp+10D0h+var_1128]
0x1800071b2  mov     [rbp+10D0h+var_10A0], rax
0x1800071b6  lea     rax, [rsp+11D0h+var_1170]
0x1800071bb  mov     [rbp+10D0h+var_1098], rax
0x1800071bf  lea     rax, [rbp+10D0h+var_10B0]
0x1800071c3  mov     [rbp+10D0h+var_1048], rax
0x1800071ca  lea     rax, [rbp+10D0h+var_10B8]
0x1800071ce  mov     [rbp+10D0h+var_10C0], rax
0x1800071d2  mov     rax, [rdi+18h]
0x1800071d6  add     rax, 0Ah
0x1800071da  mov     [rsp+11D0h+var_1190], rax
0x1800071df  movzx   eax, word ptr [rdi+2]
0x1800071e3  mov     [rbp+10D0h+var_1120], ax
0x1800071e7  mov     al, [rdi+4]
0x1800071ea  mov     [rbp+10D0h+var_111E], al
0x1800071ed  mov     [rbp+10D0h+var_111C], r15d
0x1800071f1  mov     [rbp+10D0h+var_1118], r15w
0x1800071f6  xorps   xmm0, xmm0
0x1800071f9  movdqu  [rbp+10D0h+var_1110], xmm0
0x1800071fe  movzx   eax, word ptr [rdi+6]
0x180007202  mov     [rbp+10D0h+var_1100], ax
0x180007206  mov     al, [rdi+8]
0x180007209  mov     [rbp+10D0h+var_10FE], al
0x18000720c  mov     [rbp+10D0h+var_10FC], r15d
0x180007210  mov     [rbp+10D0h+var_10F8], r15w
0x180007215  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000721a  jmp     loc_1800072B2
0x18000721f  mov     ebx, r15d
0x180007222  mov     esi, [rbp+10D0h+var_111C]
0x180007225  test    esi, esi
0x180007227  jz      loc_1800072B2
0x18000722d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180007231  mov     r8, [rdi+20h]; unsigned __int8 *
0x180007235  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000723a  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000723e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007243  test    al, al
0x180007245  jz      short loc_1800072AF
0x180007247  mov     eax, [rbp+10D0h+var_10FC]
0x18000724a  mov     [rsp+11D0h+var_1180], eax
0x18000724e  movzx   eax, [rbp+10D0h+var_10F8]
0x180007252  mov     [rbp+10D0h+var_10E0], rax
0x180007256  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000725a  mov     [rbp+10D0h+var_10D8], rax
0x18000725e  movzx   eax, [rbp+10D0h+var_1118]
0x180007262  mov     [rbp+10D0h+var_10D0], rax
0x180007266  mov     [rbp+10D0h+var_10C8], r15
0x18000726a  mov     rcx, [rbp+10D0h+var_1048]; this
0x180007271  test    rcx, rcx
0x180007274  jz      loc_1800073EE
0x18000727a  mov     rax, [rcx]
0x18000727d  lea     rdx, [rsp+11D0h+var_1180]
0x180007282  mov     [rsp+11D0h+var_11A8], rdx
0x180007287  lea     rdx, [rbp+10D0h+var_10E0]
0x18000728b  mov     [rsp+11D0h+var_11B0], rdx
0x180007290  lea     r9, [rbp+10D0h+var_10D8]
0x180007294  lea     r8, [rbp+10D0h+var_10D0]
0x180007298  lea     rdx, [rbp+10D0h+var_10C8]
0x18000729c  mov     rax, [rax+20h]
0x1800072a0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072a5  test    al, al
0x1800072a7  jz      short loc_18000731F
0x1800072a9  inc     ebx
0x1800072ab  cmp     ebx, esi
0x1800072ad  jb      short loc_180007231
0x1800072af  xor     r15d, r15d
0x1800072b2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800072b6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800072bb  lea     rcx, [rbp+10D0h+var_1120]; this
0x1800072bf  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800072c4  test    al, al
0x1800072c6  jnz     loc_18000721F
0x1800072cc  mov     rcx, [rbp+10D0h+var_1048]
0x1800072d3  test    rcx, rcx
0x1800072d6  jz      short loc_1800072E4
0x1800072d8  mov     rax, [rcx]
0x1800072db  mov     rax, [rax+18h]
0x1800072df  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800072e4  mov     bl, 1
0x1800072e6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x1800072ea  jz      short loc_180007361
0x1800072ec  mov     eax, [rsp+11D0h+var_1188]
0x1800072f0  mov     rdx, [rsp+11D0h+var_1158]
0x1800072f5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800072f9  sub     r8d, edx
0x1800072fc  mov     [rsp+11D0h+var_11A0], 1
0x180007304  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180007308  mov     rcx, r14
0x18000730b  call    wil_details_NtUpdateWnfStateData
0x180007310  cmp     eax, 0C0000001h
0x180007315  jnz     short loc_18000733F
0x180007317  inc     r12
0x18000731a  mov     bl, r15b
0x18000731d  jmp     short loc_18000736D
0x18000731f  mov     rcx, [rbp+10D0h+var_1048]
0x180007326  xor     r15d, r15d
0x180007329  test    rcx, rcx
0x18000732c  jz      short loc_18000733A
0x18000732e  mov     rax, [rcx]
0x180007331  mov     rax, [rax+18h]
0x180007335  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000733a  mov     bl, r15b
0x18000733d  jmp     short loc_1800072E6
0x18000733f  test    eax, eax
0x180007341  jz      short loc_180007361
0x180007343  mov     rdx, [rsp+11D0h+var_1158]
0x180007348  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000734c  sub     r8d, edx
0x18000734f  mov     [rsp+11D0h+var_11A0], r15d
0x180007354  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180007359  mov     rcx, r14
0x18000735c  call    wil_details_NtUpdateWnfStateData
0x180007361  add     r14, 8
0x180007365  mov     rax, [rbp+10D0h+var_1130]
0x180007369  mov     [rbp+10D0h+var_1128], rax
0x18000736d  mov     rsi, [rbp+10D0h+lpMem]
0x180007371  mov     [rbp+10D0h+lpMem], r15
0x180007375  test    rsi, rsi
0x180007378  jz      short loc_18000738E
0x18000737a  call    cs:__imp_GetProcessHeap
0x180007380  mov     rcx, rax; hHeap
0x180007383  mov     r8, rsi; lpMem
0x180007386  xor     edx, edx; dwFlags
0x180007388  call    cs:__imp_HeapFree
0x18000738e  test    bl, bl
0x180007390  jnz     short loc_1800073C4
0x180007392  cmp     r14, r13
0x180007395  jnb     short loc_1800073C4
0x180007397  cmp     r12, 32h ; '2'
0x18000739b  jb      loc_180007066
0x1800073a1  jmp     short loc_1800073C4
0x1800073a3  mov     rbx, [rbp+10D0h+lpMem]
0x1800073a7  mov     [rbp+10D0h+lpMem], r15
0x1800073ab  test    rbx, rbx
0x1800073ae  jz      short loc_1800073C4
0x1800073b0  call    cs:__imp_GetProcessHeap
0x1800073b6  mov     rcx, rax; hHeap
0x1800073b9  mov     r8, rbx; lpMem
0x1800073bc  xor     edx, edx; dwFlags
0x1800073be  call    cs:__imp_HeapFree
0x1800073c4  mov     rcx, [rbp+10D0h+var_40]
0x1800073cb  xor     rcx, rsp; StackCookie
0x1800073ce  call    __security_check_cookie
0x1800073d3  mov     rbx, [rsp+11D0h+arg_8]
0x1800073db  add     rsp, 11A0h
0x1800073e2  pop     r15
0x1800073e4  pop     r14
0x1800073e6  pop     r13
0x1800073e8  pop     r12
0x1800073ea  pop     rdi
0x1800073eb  pop     rsi
0x1800073ec  pop     rbp
0x1800073ed  retn
0x1800073ee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
