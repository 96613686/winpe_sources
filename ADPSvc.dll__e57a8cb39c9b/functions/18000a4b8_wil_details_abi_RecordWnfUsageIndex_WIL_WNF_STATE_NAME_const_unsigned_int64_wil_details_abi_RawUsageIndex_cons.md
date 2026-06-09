# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000a4b8`
- end: `0x18000a890`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180009a08`

## callees

- `0x180002250`
- `0x18000770c`
- `0x1800095a8`
- `0x180009908`
- `0x18000a4b8`
- `0x18000abb0`
- `0x18000bad0`
- `0x1800c6e30`
- `0x1800ca010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a598`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000a598`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a5af`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18000a5af`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a816`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a84c`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a816`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000a84c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a824`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a85a`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a824`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000a85a`

## string_xrefs

- `0x18000a591`: `ntdll.dll`

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
  __int64 v19; // r9
  char v20; // bl
  int updated; // eax
  __int64 v22; // r9
  void *v23; // rsi
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 *v27; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v29);
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v35, (int)v36 - (int)v35, v19, (int)v27, v29[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v35, v36 - v35, v22, (int)v27, 0, 0);
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
0x18000a4b8  mov     [rsp-8+arg_8], rbx
0x18000a4bd  push    rbp
0x18000a4be  push    rsi
0x18000a4bf  push    rdi
0x18000a4c0  push    r12
0x18000a4c2  push    r13
0x18000a4c4  push    r14
0x18000a4c6  push    r15
0x18000a4c8  lea     rbp, [rsp-10A0h]
0x18000a4d0  mov     eax, 11A0h
0x18000a4d5  call    _alloca_probe
0x18000a4da  sub     rsp, rax
0x18000a4dd  mov     rax, cs:__security_cookie
0x18000a4e4  xor     rax, rsp
0x18000a4e7  mov     [rbp+10D0h+var_40], rax
0x18000a4ee  mov     rdi, r8
0x18000a4f1  mov     r14, rcx
0x18000a4f4  lea     r13, [rcx+rdx*8]
0x18000a4f8  xor     r15d, r15d
0x18000a4fb  mov     r12d, r15d
0x18000a4fe  mov     [rbp+10D0h+var_1128], r15
0x18000a502  mov     cl, [rdi+8]
0x18000a505  movzx   edx, word ptr [rdi+6]
0x18000a509  movzx   eax, word ptr [rdi]
0x18000a50c  mov     [rsp+11D0h+var_1170], ax
0x18000a511  movzx   eax, word ptr [rdi+2]
0x18000a515  mov     [rsp+11D0h+var_116E], ax
0x18000a51a  mov     al, [rdi+4]
0x18000a51d  mov     [rsp+11D0h+var_116C], al
0x18000a521  mov     [rsp+11D0h+var_116A], dx
0x18000a526  mov     [rsp+11D0h+var_1168], cl
0x18000a52a  test    dx, dx
0x18000a52d  jz      short loc_18000A54C
0x18000a52f  mov     eax, edx
0x18000a531  cmp     cl, 1
0x18000a534  jnz     short loc_18000A53C
0x18000a536  add     rax, 2
0x18000a53a  jmp     short loc_18000A545
0x18000a53c  cmp     cl, 2
0x18000a53f  jnz     short loc_18000A545
0x18000a541  add     rax, 4
0x18000a545  mov     [rsp+11D0h+var_1160], rax
0x18000a54a  jmp     short loc_18000A551
0x18000a54c  mov     [rsp+11D0h+var_1160], r15
0x18000a551  mov     [rsp+11D0h+var_1158], r15
0x18000a556  xorps   xmm0, xmm0
0x18000a559  movdqa  [rbp+10D0h+var_1150], xmm0
0x18000a55e  mov     [rbp+10D0h+lpMem], r15
0x18000a562  mov     [rbp+10D0h+var_1138], 0
0x18000a568  mov     [rbp+10D0h+var_1136], r15b
0x18000a56c  mov     [rsp+11D0h+var_1188], r15d
0x18000a571  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18000a579  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x18000a580  test    rax, rax
0x18000a583  jnz     short loc_18000A5C8
0x18000a585  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a58c  test    rax, rax
0x18000a58f  jnz     short loc_18000A5A5
0x18000a591  lea     rcx, ModuleName; "ntdll.dll"
0x18000a598  call    cs:__imp_GetModuleHandleW
0x18000a59e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18000a5a5  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000a5ac  mov     rcx, rax; hModule
0x18000a5af  call    cs:__imp_GetProcAddress
0x18000a5b5  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000a5bc  test    rax, rax
0x18000a5bf  jnz     short loc_18000A5C8
0x18000a5c1  mov     ebx, 0C0000139h
0x18000a5c6  jmp     short loc_18000A5F2
0x18000a5c8  lea     rcx, [rsp+11D0h+var_1190]
0x18000a5cd  mov     [rsp+11D0h+var_11A8], rcx
0x18000a5d2  lea     rcx, [rbp+10D0h+var_1040]
0x18000a5d9  mov     [rsp+11D0h+var_11B0], rcx
0x18000a5de  lea     r9, [rsp+11D0h+var_1188]
0x18000a5e3  xor     r8d, r8d
0x18000a5e6  xor     edx, edx
0x18000a5e8  mov     rcx, r14
0x18000a5eb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a5f0  mov     ebx, eax
0x18000a5f2  mov     ecx, ebx; this
0x18000a5f4  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000a5f9  test    ebx, ebx
0x18000a5fb  jz      short loc_18000A60B
0x18000a5fd  mov     eax, r15d
0x18000a600  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000a604  mov     [rsp+11D0h+var_1188], r15d
0x18000a609  jmp     short loc_18000A60F
0x18000a60b  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000a60f  mov     r8d, eax; unsigned __int64
0x18000a612  mov     r9d, 1000h; unsigned __int64
0x18000a618  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000a61f  lea     rcx, [rsp+11D0h+var_1170]; this
0x18000a624  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000a629  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x18000a62d  jnz     loc_18000A83F
0x18000a633  mov     [rbp+10D0h+var_1130], r15
0x18000a637  lea     rax, ??_7?$__func@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@$$A6A_NPEAX131I@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000a63e  mov     [rbp+10D0h+var_10B0], rax
0x18000a642  lea     rax, [rbp+10D0h+var_1130]
0x18000a646  mov     [rbp+10D0h+var_10A8], rax
0x18000a64a  lea     rax, [rbp+10D0h+var_1128]
0x18000a64e  mov     [rbp+10D0h+var_10A0], rax
0x18000a652  lea     rax, [rsp+11D0h+var_1170]
0x18000a657  mov     [rbp+10D0h+var_1098], rax
0x18000a65b  lea     rax, [rbp+10D0h+var_10B0]
0x18000a65f  mov     [rbp+10D0h+var_1048], rax
0x18000a666  lea     rax, [rbp+10D0h+var_10B8]
0x18000a66a  mov     [rbp+10D0h+var_10C0], rax
0x18000a66e  mov     rax, [rdi+18h]
0x18000a672  add     rax, 0Ah
0x18000a676  mov     [rsp+11D0h+var_1190], rax
0x18000a67b  movzx   eax, word ptr [rdi+2]
0x18000a67f  mov     [rbp+10D0h+var_1120], ax
0x18000a683  mov     al, [rdi+4]
0x18000a686  mov     [rbp+10D0h+var_111E], al
0x18000a689  mov     [rbp+10D0h+var_111C], r15d
0x18000a68d  mov     [rbp+10D0h+var_1118], r15w
0x18000a692  xorps   xmm0, xmm0
0x18000a695  movdqu  [rbp+10D0h+var_1110], xmm0
0x18000a69a  movzx   eax, word ptr [rdi+6]
0x18000a69e  mov     [rbp+10D0h+var_1100], ax
0x18000a6a2  mov     al, [rdi+8]
0x18000a6a5  mov     [rbp+10D0h+var_10FE], al
0x18000a6a8  mov     [rbp+10D0h+var_10FC], r15d
0x18000a6ac  mov     [rbp+10D0h+var_10F8], r15w
0x18000a6b1  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18000a6b6  jmp     loc_18000A74E
0x18000a6bb  mov     ebx, r15d
0x18000a6be  mov     esi, [rbp+10D0h+var_111C]
0x18000a6c1  test    esi, esi
0x18000a6c3  jz      loc_18000A74E
0x18000a6c9  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x18000a6cd  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000a6d1  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000a6d6  lea     rcx, [rbp+10D0h+var_1100]; this
0x18000a6da  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000a6df  test    al, al
0x18000a6e1  jz      short loc_18000A74B
0x18000a6e3  mov     eax, [rbp+10D0h+var_10FC]
0x18000a6e6  mov     [rsp+11D0h+var_1180], eax
0x18000a6ea  movzx   eax, [rbp+10D0h+var_10F8]
0x18000a6ee  mov     [rbp+10D0h+var_10E0], rax
0x18000a6f2  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x18000a6f6  mov     [rbp+10D0h+var_10D8], rax
0x18000a6fa  movzx   eax, [rbp+10D0h+var_1118]
0x18000a6fe  mov     [rbp+10D0h+var_10D0], rax
0x18000a702  mov     [rbp+10D0h+var_10C8], r15
0x18000a706  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000a70d  test    rcx, rcx
0x18000a710  jz      loc_18000A88A
0x18000a716  mov     rax, [rcx]
0x18000a719  lea     rdx, [rsp+11D0h+var_1180]
0x18000a71e  mov     [rsp+11D0h+var_11A8], rdx
0x18000a723  lea     rdx, [rbp+10D0h+var_10E0]
0x18000a727  mov     [rsp+11D0h+var_11B0], rdx
0x18000a72c  lea     r9, [rbp+10D0h+var_10D8]
0x18000a730  lea     r8, [rbp+10D0h+var_10D0]
0x18000a734  lea     rdx, [rbp+10D0h+var_10C8]
0x18000a738  mov     rax, [rax+20h]
0x18000a73c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a741  test    al, al
0x18000a743  jz      short loc_18000A7BB
0x18000a745  inc     ebx
0x18000a747  cmp     ebx, esi
0x18000a749  jb      short loc_18000A6CD
0x18000a74b  xor     r15d, r15d
0x18000a74e  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000a752  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000a757  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000a75b  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x18000a760  test    al, al
0x18000a762  jnz     loc_18000A6BB
0x18000a768  mov     rcx, [rbp+10D0h+var_1048]
0x18000a76f  test    rcx, rcx
0x18000a772  jz      short loc_18000A780
0x18000a774  mov     rax, [rcx]
0x18000a777  mov     rax, [rax+18h]
0x18000a77b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a780  mov     bl, 1
0x18000a782  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000a786  jz      short loc_18000A7FD
0x18000a788  mov     eax, [rsp+11D0h+var_1188]
0x18000a78c  mov     rdx, [rsp+11D0h+var_1158]
0x18000a791  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000a795  sub     r8d, edx
0x18000a798  mov     [rsp+11D0h+var_11A0], 1
0x18000a7a0  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000a7a4  mov     rcx, r14
0x18000a7a7  call    wil_details_NtUpdateWnfStateData
0x18000a7ac  cmp     eax, 0C0000001h
0x18000a7b1  jnz     short loc_18000A7DB
0x18000a7b3  inc     r12
0x18000a7b6  mov     bl, r15b
0x18000a7b9  jmp     short loc_18000A809
0x18000a7bb  mov     rcx, [rbp+10D0h+var_1048]
0x18000a7c2  xor     r15d, r15d
0x18000a7c5  test    rcx, rcx
0x18000a7c8  jz      short loc_18000A7D6
0x18000a7ca  mov     rax, [rcx]
0x18000a7cd  mov     rax, [rax+18h]
0x18000a7d1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a7d6  mov     bl, r15b
0x18000a7d9  jmp     short loc_18000A782
0x18000a7db  test    eax, eax
0x18000a7dd  jz      short loc_18000A7FD
0x18000a7df  mov     rdx, [rsp+11D0h+var_1158]
0x18000a7e4  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000a7e8  sub     r8d, edx
0x18000a7eb  mov     [rsp+11D0h+var_11A0], r15d
0x18000a7f0  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000a7f5  mov     rcx, r14
0x18000a7f8  call    wil_details_NtUpdateWnfStateData
0x18000a7fd  add     r14, 8
0x18000a801  mov     rax, [rbp+10D0h+var_1130]
0x18000a805  mov     [rbp+10D0h+var_1128], rax
0x18000a809  mov     rsi, [rbp+10D0h+lpMem]
0x18000a80d  mov     [rbp+10D0h+lpMem], r15
0x18000a811  test    rsi, rsi
0x18000a814  jz      short loc_18000A82A
0x18000a816  call    cs:__imp_GetProcessHeap
0x18000a81c  mov     rcx, rax; hHeap
0x18000a81f  mov     r8, rsi; lpMem
0x18000a822  xor     edx, edx; dwFlags
0x18000a824  call    cs:__imp_HeapFree
0x18000a82a  test    bl, bl
0x18000a82c  jnz     short loc_18000A860
0x18000a82e  cmp     r14, r13
0x18000a831  jnb     short loc_18000A860
0x18000a833  cmp     r12, 32h ; '2'
0x18000a837  jb      loc_18000A502
0x18000a83d  jmp     short loc_18000A860
0x18000a83f  mov     rbx, [rbp+10D0h+lpMem]
0x18000a843  mov     [rbp+10D0h+lpMem], r15
0x18000a847  test    rbx, rbx
0x18000a84a  jz      short loc_18000A860
0x18000a84c  call    cs:__imp_GetProcessHeap
0x18000a852  mov     rcx, rax; hHeap
0x18000a855  mov     r8, rbx; lpMem
0x18000a858  xor     edx, edx; dwFlags
0x18000a85a  call    cs:__imp_HeapFree
0x18000a860  mov     rcx, [rbp+10D0h+var_40]
0x18000a867  xor     rcx, rsp; StackCookie
0x18000a86a  call    __security_check_cookie
0x18000a86f  mov     rbx, [rsp+11D0h+arg_8]
0x18000a877  add     rsp, 11A0h
0x18000a87e  pop     r15
0x18000a880  pop     r14
0x18000a882  pop     r13
0x18000a884  pop     r12
0x18000a886  pop     rdi
0x18000a887  pop     rsi
0x18000a888  pop     rbp
0x18000a889  retn
0x18000a88a  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
