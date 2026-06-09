# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180008e0c`
- end: `0x1800091e4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800084f0`

## callees

- `0x1800016b0`
- `0x180008088`
- `0x1800083f0`
- `0x180008e0c`
- `0x1800097e4`
- `0x18000aafc`
- `0x18000b110`
- `0x18000bba0`
- `0x18000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f03`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008f03`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008eec`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008eec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009178`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091ae`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009178`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800091ae`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000916a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091a0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000916a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800091a0`

## string_xrefs

- `0x180008ee5`: `ntdll.dll`

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
0x180008e0c  mov     [rsp-8+arg_8], rbx
0x180008e11  push    rbp
0x180008e12  push    rsi
0x180008e13  push    rdi
0x180008e14  push    r12
0x180008e16  push    r13
0x180008e18  push    r14
0x180008e1a  push    r15
0x180008e1c  lea     rbp, [rsp-10A0h]
0x180008e24  mov     eax, 11A0h
0x180008e29  call    _alloca_probe
0x180008e2e  sub     rsp, rax
0x180008e31  mov     rax, cs:__security_cookie
0x180008e38  xor     rax, rsp
0x180008e3b  mov     [rbp+10D0h+var_40], rax
0x180008e42  mov     rdi, r8
0x180008e45  mov     r14, rcx
0x180008e48  lea     r13, [rcx+rdx*8]
0x180008e4c  xor     r15d, r15d
0x180008e4f  mov     r12d, r15d
0x180008e52  mov     [rbp+10D0h+var_1128], r15
0x180008e56  mov     cl, [rdi+8]
0x180008e59  movzx   edx, word ptr [rdi+6]
0x180008e5d  movzx   eax, word ptr [rdi]
0x180008e60  mov     [rsp+11D0h+var_1170], ax
0x180008e65  movzx   eax, word ptr [rdi+2]
0x180008e69  mov     [rsp+11D0h+var_116E], ax
0x180008e6e  mov     al, [rdi+4]
0x180008e71  mov     [rsp+11D0h+var_116C], al
0x180008e75  mov     [rsp+11D0h+var_116A], dx
0x180008e7a  mov     [rsp+11D0h+var_1168], cl
0x180008e7e  test    dx, dx
0x180008e81  jz      short loc_180008EA0
0x180008e83  mov     eax, edx
0x180008e85  cmp     cl, 1
0x180008e88  jnz     short loc_180008E90
0x180008e8a  add     rax, 2
0x180008e8e  jmp     short loc_180008E99
0x180008e90  cmp     cl, 2
0x180008e93  jnz     short loc_180008E99
0x180008e95  add     rax, 4
0x180008e99  mov     [rsp+11D0h+var_1160], rax
0x180008e9e  jmp     short loc_180008EA5
0x180008ea0  mov     [rsp+11D0h+var_1160], r15
0x180008ea5  mov     [rsp+11D0h+var_1158], r15
0x180008eaa  xorps   xmm0, xmm0
0x180008ead  movdqa  [rbp+10D0h+var_1150], xmm0
0x180008eb2  mov     [rbp+10D0h+lpMem], r15
0x180008eb6  mov     [rbp+10D0h+var_1138], 0
0x180008ebc  mov     [rbp+10D0h+var_1136], r15b
0x180008ec0  mov     [rsp+11D0h+var_1188], r15d
0x180008ec5  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180008ecd  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008ed4  test    rax, rax
0x180008ed7  jnz     short loc_180008F1C
0x180008ed9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008ee0  test    rax, rax
0x180008ee3  jnz     short loc_180008EF9
0x180008ee5  lea     rcx, ModuleName; "ntdll.dll"
0x180008eec  call    cs:__imp_GetModuleHandleW
0x180008ef2  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008ef9  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008f00  mov     rcx, rax; hModule
0x180008f03  call    cs:__imp_GetProcAddress
0x180008f09  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008f10  test    rax, rax
0x180008f13  jnz     short loc_180008F1C
0x180008f15  mov     ebx, 0C0000139h
0x180008f1a  jmp     short loc_180008F46
0x180008f1c  lea     rcx, [rsp+11D0h+var_1190]
0x180008f21  mov     [rsp+11D0h+var_11A8], rcx
0x180008f26  lea     rcx, [rbp+10D0h+var_1040]
0x180008f2d  mov     [rsp+11D0h+var_11B0], rcx
0x180008f32  lea     r9, [rsp+11D0h+var_1188]
0x180008f37  xor     r8d, r8d
0x180008f3a  xor     edx, edx
0x180008f3c  mov     rcx, r14
0x180008f3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f44  mov     ebx, eax
0x180008f46  mov     ecx, ebx; this
0x180008f48  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180008f4d  test    ebx, ebx
0x180008f4f  jz      short loc_180008F5F
0x180008f51  mov     eax, r15d
0x180008f54  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180008f58  mov     [rsp+11D0h+var_1188], r15d
0x180008f5d  jmp     short loc_180008F63
0x180008f5f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180008f63  mov     r8d, eax; unsigned __int64
0x180008f66  mov     r9d, 1000h; unsigned __int64
0x180008f6c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180008f73  lea     rcx, [rsp+11D0h+var_1170]; this
0x180008f78  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180008f7d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180008f81  jnz     loc_180009193
0x180008f87  mov     [rbp+10D0h+var_1130], r15
0x180008f8b  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180008f92  mov     [rbp+10D0h+var_10B0], rax
0x180008f96  lea     rax, [rbp+10D0h+var_1130]
0x180008f9a  mov     [rbp+10D0h+var_10A8], rax
0x180008f9e  lea     rax, [rbp+10D0h+var_1128]
0x180008fa2  mov     [rbp+10D0h+var_10A0], rax
0x180008fa6  lea     rax, [rsp+11D0h+var_1170]
0x180008fab  mov     [rbp+10D0h+var_1098], rax
0x180008faf  lea     rax, [rbp+10D0h+var_10B0]
0x180008fb3  mov     [rbp+10D0h+var_1048], rax
0x180008fba  lea     rax, [rbp+10D0h+var_10B8]
0x180008fbe  mov     [rbp+10D0h+var_10C0], rax
0x180008fc2  mov     rax, [rdi+18h]
0x180008fc6  add     rax, 0Ah
0x180008fca  mov     [rsp+11D0h+var_1190], rax
0x180008fcf  movzx   eax, word ptr [rdi+2]
0x180008fd3  mov     [rbp+10D0h+var_1120], ax
0x180008fd7  mov     al, [rdi+4]
0x180008fda  mov     [rbp+10D0h+var_111E], al
0x180008fdd  mov     [rbp+10D0h+var_111C], r15d
0x180008fe1  mov     [rbp+10D0h+var_1118], r15w
0x180008fe6  xorps   xmm0, xmm0
0x180008fe9  movdqu  [rbp+10D0h+var_1110], xmm0
0x180008fee  movzx   eax, word ptr [rdi+6]
0x180008ff2  mov     [rbp+10D0h+var_1100], ax
0x180008ff6  mov     al, [rdi+8]
0x180008ff9  mov     [rbp+10D0h+var_10FE], al
0x180008ffc  mov     [rbp+10D0h+var_10FC], r15d
0x180009000  mov     [rbp+10D0h+var_10F8], r15w
0x180009005  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000900a  jmp     loc_1800090A2
0x18000900f  mov     ebx, r15d
0x180009012  mov     esi, [rbp+10D0h+var_111C]
0x180009015  test    esi, esi
0x180009017  jz      loc_1800090A2
0x18000901d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180009021  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009025  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000902a  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000902e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009033  test    al, al
0x180009035  jz      short loc_18000909F
0x180009037  mov     eax, [rbp+10D0h+var_10FC]
0x18000903a  mov     [rsp+11D0h+var_1180], eax
0x18000903e  movzx   eax, [rbp+10D0h+var_10F8]
0x180009042  mov     [rbp+10D0h+var_10E0], rax
0x180009046  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000904a  mov     [rbp+10D0h+var_10D8], rax
0x18000904e  movzx   eax, [rbp+10D0h+var_1118]
0x180009052  mov     [rbp+10D0h+var_10D0], rax
0x180009056  mov     [rbp+10D0h+var_10C8], r15
0x18000905a  mov     rcx, [rbp+10D0h+var_1048]; this
0x180009061  test    rcx, rcx
0x180009064  jz      loc_1800091DE
0x18000906a  mov     rax, [rcx]
0x18000906d  lea     rdx, [rsp+11D0h+var_1180]
0x180009072  mov     [rsp+11D0h+var_11A8], rdx
0x180009077  lea     rdx, [rbp+10D0h+var_10E0]
0x18000907b  mov     [rsp+11D0h+var_11B0], rdx
0x180009080  lea     r9, [rbp+10D0h+var_10D8]
0x180009084  lea     r8, [rbp+10D0h+var_10D0]
0x180009088  lea     rdx, [rbp+10D0h+var_10C8]
0x18000908c  mov     rax, [rax+20h]
0x180009090  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009095  test    al, al
0x180009097  jz      short loc_18000910F
0x180009099  inc     ebx
0x18000909b  cmp     ebx, esi
0x18000909d  jb      short loc_180009021
0x18000909f  xor     r15d, r15d
0x1800090a2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800090a6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800090ab  lea     rcx, [rbp+10D0h+var_1120]; this
0x1800090af  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800090b4  test    al, al
0x1800090b6  jnz     loc_18000900F
0x1800090bc  mov     rcx, [rbp+10D0h+var_1048]
0x1800090c3  test    rcx, rcx
0x1800090c6  jz      short loc_1800090D4
0x1800090c8  mov     rax, [rcx]
0x1800090cb  mov     rax, [rax+18h]
0x1800090cf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800090d4  mov     bl, 1
0x1800090d6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x1800090da  jz      short loc_180009151
0x1800090dc  mov     eax, [rsp+11D0h+var_1188]
0x1800090e0  mov     rdx, [rsp+11D0h+var_1158]
0x1800090e5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800090e9  sub     r8d, edx
0x1800090ec  mov     [rsp+11D0h+var_11A0], 1
0x1800090f4  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800090f8  mov     rcx, r14
0x1800090fb  call    wil_details_NtUpdateWnfStateData
0x180009100  cmp     eax, 0C0000001h
0x180009105  jnz     short loc_18000912F
0x180009107  inc     r12
0x18000910a  mov     bl, r15b
0x18000910d  jmp     short loc_18000915D
0x18000910f  mov     rcx, [rbp+10D0h+var_1048]
0x180009116  xor     r15d, r15d
0x180009119  test    rcx, rcx
0x18000911c  jz      short loc_18000912A
0x18000911e  mov     rax, [rcx]
0x180009121  mov     rax, [rax+18h]
0x180009125  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000912a  mov     bl, r15b
0x18000912d  jmp     short loc_1800090D6
0x18000912f  test    eax, eax
0x180009131  jz      short loc_180009151
0x180009133  mov     rdx, [rsp+11D0h+var_1158]
0x180009138  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000913c  sub     r8d, edx
0x18000913f  mov     [rsp+11D0h+var_11A0], r15d
0x180009144  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180009149  mov     rcx, r14
0x18000914c  call    wil_details_NtUpdateWnfStateData
0x180009151  add     r14, 8
0x180009155  mov     rax, [rbp+10D0h+var_1130]
0x180009159  mov     [rbp+10D0h+var_1128], rax
0x18000915d  mov     rsi, [rbp+10D0h+lpMem]
0x180009161  mov     [rbp+10D0h+lpMem], r15
0x180009165  test    rsi, rsi
0x180009168  jz      short loc_18000917E
0x18000916a  call    cs:__imp_GetProcessHeap
0x180009170  mov     rcx, rax; hHeap
0x180009173  mov     r8, rsi; lpMem
0x180009176  xor     edx, edx; dwFlags
0x180009178  call    cs:__imp_HeapFree
0x18000917e  test    bl, bl
0x180009180  jnz     short loc_1800091B4
0x180009182  cmp     r14, r13
0x180009185  jnb     short loc_1800091B4
0x180009187  cmp     r12, 32h ; '2'
0x18000918b  jb      loc_180008E56
0x180009191  jmp     short loc_1800091B4
0x180009193  mov     rbx, [rbp+10D0h+lpMem]
0x180009197  mov     [rbp+10D0h+lpMem], r15
0x18000919b  test    rbx, rbx
0x18000919e  jz      short loc_1800091B4
0x1800091a0  call    cs:__imp_GetProcessHeap
0x1800091a6  mov     rcx, rax; hHeap
0x1800091a9  mov     r8, rbx; lpMem
0x1800091ac  xor     edx, edx; dwFlags
0x1800091ae  call    cs:__imp_HeapFree
0x1800091b4  mov     rcx, [rbp+10D0h+var_40]
0x1800091bb  xor     rcx, rsp; StackCookie
0x1800091be  call    __security_check_cookie
0x1800091c3  mov     rbx, [rsp+11D0h+arg_8]
0x1800091cb  add     rsp, 11A0h
0x1800091d2  pop     r15
0x1800091d4  pop     r14
0x1800091d6  pop     r13
0x1800091d8  pop     r12
0x1800091da  pop     rdi
0x1800091db  pop     rsi
0x1800091dc  pop     rbp
0x1800091dd  retn
0x1800091de  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
