# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140006c1c`
- end: `0x140006ff4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1400060fc`

## callees

- `0x1400016f0`
- `0x140005bf8`
- `0x140005ffc`
- `0x140006c1c`
- `0x1400075f4`
- `0x140008aec`
- `0x140009310`
- `0x14000b840`
- `0x14000c010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006cfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140006cfc`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d13`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140006d13`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006f7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006fb0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006f7a`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x140006fb0`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006f88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006fbe`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006f88`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x140006fbe`

## string_xrefs

- `0x140006cf5`: `ntdll.dll`

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
0x140006c1c  mov     [rsp-8+arg_8], rbx
0x140006c21  push    rbp
0x140006c22  push    rsi
0x140006c23  push    rdi
0x140006c24  push    r12
0x140006c26  push    r13
0x140006c28  push    r14
0x140006c2a  push    r15
0x140006c2c  lea     rbp, [rsp-10A0h]
0x140006c34  mov     eax, 11A0h
0x140006c39  call    _alloca_probe
0x140006c3e  sub     rsp, rax
0x140006c41  mov     rax, cs:__security_cookie
0x140006c48  xor     rax, rsp
0x140006c4b  mov     [rbp+10D0h+var_40], rax
0x140006c52  mov     rdi, r8
0x140006c55  mov     r14, rcx
0x140006c58  lea     r13, [rcx+rdx*8]
0x140006c5c  xor     r15d, r15d
0x140006c5f  mov     r12d, r15d
0x140006c62  mov     [rbp+10D0h+var_1128], r15
0x140006c66  mov     cl, [rdi+8]
0x140006c69  movzx   edx, word ptr [rdi+6]
0x140006c6d  movzx   eax, word ptr [rdi]
0x140006c70  mov     [rsp+11D0h+var_1170], ax
0x140006c75  movzx   eax, word ptr [rdi+2]
0x140006c79  mov     [rsp+11D0h+var_116E], ax
0x140006c7e  mov     al, [rdi+4]
0x140006c81  mov     [rsp+11D0h+var_116C], al
0x140006c85  mov     [rsp+11D0h+var_116A], dx
0x140006c8a  mov     [rsp+11D0h+var_1168], cl
0x140006c8e  test    dx, dx
0x140006c91  jz      short loc_140006CB0
0x140006c93  mov     eax, edx
0x140006c95  cmp     cl, 1
0x140006c98  jnz     short loc_140006CA0
0x140006c9a  add     rax, 2
0x140006c9e  jmp     short loc_140006CA9
0x140006ca0  cmp     cl, 2
0x140006ca3  jnz     short loc_140006CA9
0x140006ca5  add     rax, 4
0x140006ca9  mov     [rsp+11D0h+var_1160], rax
0x140006cae  jmp     short loc_140006CB5
0x140006cb0  mov     [rsp+11D0h+var_1160], r15
0x140006cb5  mov     [rsp+11D0h+var_1158], r15
0x140006cba  xorps   xmm0, xmm0
0x140006cbd  movdqa  [rbp+10D0h+var_1150], xmm0
0x140006cc2  mov     [rbp+10D0h+lpMem], r15
0x140006cc6  mov     [rbp+10D0h+var_1138], 0
0x140006ccc  mov     [rbp+10D0h+var_1136], r15b
0x140006cd0  mov     [rsp+11D0h+var_1188], r15d
0x140006cd5  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x140006cdd  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140006ce4  test    rax, rax
0x140006ce7  jnz     short loc_140006D2C
0x140006ce9  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006cf0  test    rax, rax
0x140006cf3  jnz     short loc_140006D09
0x140006cf5  lea     rcx, ModuleName; "ntdll.dll"
0x140006cfc  call    cs:__imp_GetModuleHandleW
0x140006d02  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140006d09  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140006d10  mov     rcx, rax; hModule
0x140006d13  call    cs:__imp_GetProcAddress
0x140006d19  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140006d20  test    rax, rax
0x140006d23  jnz     short loc_140006D2C
0x140006d25  mov     ebx, 0C0000139h
0x140006d2a  jmp     short loc_140006D56
0x140006d2c  lea     rcx, [rsp+11D0h+var_1190]
0x140006d31  mov     [rsp+11D0h+var_11A8], rcx
0x140006d36  lea     rcx, [rbp+10D0h+var_1040]
0x140006d3d  mov     [rsp+11D0h+var_11B0], rcx
0x140006d42  lea     r9, [rsp+11D0h+var_1188]
0x140006d47  xor     r8d, r8d
0x140006d4a  xor     edx, edx
0x140006d4c  mov     rcx, r14
0x140006d4f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006d54  mov     ebx, eax
0x140006d56  mov     ecx, ebx; this
0x140006d58  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x140006d5d  test    ebx, ebx
0x140006d5f  jz      short loc_140006D6F
0x140006d61  mov     eax, r15d
0x140006d64  mov     dword ptr [rsp+11D0h+var_1190], eax
0x140006d68  mov     [rsp+11D0h+var_1188], r15d
0x140006d6d  jmp     short loc_140006D73
0x140006d6f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x140006d73  mov     r8d, eax; unsigned __int64
0x140006d76  mov     r9d, 1000h; unsigned __int64
0x140006d7c  lea     rdx, [rbp+10D0h+var_1040]; void *
0x140006d83  lea     rcx, [rsp+11D0h+var_1170]; this
0x140006d88  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140006d8d  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x140006d91  jnz     loc_140006FA3
0x140006d97  mov     [rbp+10D0h+var_1130], r15
0x140006d9b  lea     rax, ??_7?$__func@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@$$A6A_NPEAX131I@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x140006da2  mov     [rbp+10D0h+var_10B0], rax
0x140006da6  lea     rax, [rbp+10D0h+var_1130]
0x140006daa  mov     [rbp+10D0h+var_10A8], rax
0x140006dae  lea     rax, [rbp+10D0h+var_1128]
0x140006db2  mov     [rbp+10D0h+var_10A0], rax
0x140006db6  lea     rax, [rsp+11D0h+var_1170]
0x140006dbb  mov     [rbp+10D0h+var_1098], rax
0x140006dbf  lea     rax, [rbp+10D0h+var_10B0]
0x140006dc3  mov     [rbp+10D0h+var_1048], rax
0x140006dca  lea     rax, [rbp+10D0h+var_10B8]
0x140006dce  mov     [rbp+10D0h+var_10C0], rax
0x140006dd2  mov     rax, [rdi+18h]
0x140006dd6  add     rax, 0Ah
0x140006dda  mov     [rsp+11D0h+var_1190], rax
0x140006ddf  movzx   eax, word ptr [rdi+2]
0x140006de3  mov     [rbp+10D0h+var_1120], ax
0x140006de7  mov     al, [rdi+4]
0x140006dea  mov     [rbp+10D0h+var_111E], al
0x140006ded  mov     [rbp+10D0h+var_111C], r15d
0x140006df1  mov     [rbp+10D0h+var_1118], r15w
0x140006df6  xorps   xmm0, xmm0
0x140006df9  movdqu  [rbp+10D0h+var_1110], xmm0
0x140006dfe  movzx   eax, word ptr [rdi+6]
0x140006e02  mov     [rbp+10D0h+var_1100], ax
0x140006e06  mov     al, [rdi+8]
0x140006e09  mov     [rbp+10D0h+var_10FE], al
0x140006e0c  mov     [rbp+10D0h+var_10FC], r15d
0x140006e10  mov     [rbp+10D0h+var_10F8], r15w
0x140006e15  movdqu  [rbp+10D0h+var_10F0], xmm0
0x140006e1a  jmp     loc_140006EB2
0x140006e1f  mov     ebx, r15d
0x140006e22  mov     esi, [rbp+10D0h+var_111C]
0x140006e25  test    esi, esi
0x140006e27  jz      loc_140006EB2
0x140006e2d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x140006e31  mov     r8, [rdi+20h]; unsigned __int8 *
0x140006e35  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140006e3a  lea     rcx, [rbp+10D0h+var_1100]; this
0x140006e3e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140006e43  test    al, al
0x140006e45  jz      short loc_140006EAF
0x140006e47  mov     eax, [rbp+10D0h+var_10FC]
0x140006e4a  mov     [rsp+11D0h+var_1180], eax
0x140006e4e  movzx   eax, [rbp+10D0h+var_10F8]
0x140006e52  mov     [rbp+10D0h+var_10E0], rax
0x140006e56  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x140006e5a  mov     [rbp+10D0h+var_10D8], rax
0x140006e5e  movzx   eax, [rbp+10D0h+var_1118]
0x140006e62  mov     [rbp+10D0h+var_10D0], rax
0x140006e66  mov     [rbp+10D0h+var_10C8], r15
0x140006e6a  mov     rcx, [rbp+10D0h+var_1048]; this
0x140006e71  test    rcx, rcx
0x140006e74  jz      loc_140006FEE
0x140006e7a  mov     rax, [rcx]
0x140006e7d  lea     rdx, [rsp+11D0h+var_1180]
0x140006e82  mov     [rsp+11D0h+var_11A8], rdx
0x140006e87  lea     rdx, [rbp+10D0h+var_10E0]
0x140006e8b  mov     [rsp+11D0h+var_11B0], rdx
0x140006e90  lea     r9, [rbp+10D0h+var_10D8]
0x140006e94  lea     r8, [rbp+10D0h+var_10D0]
0x140006e98  lea     rdx, [rbp+10D0h+var_10C8]
0x140006e9c  mov     rax, [rax+20h]
0x140006ea0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ea5  test    al, al
0x140006ea7  jz      short loc_140006F1F
0x140006ea9  inc     ebx
0x140006eab  cmp     ebx, esi
0x140006ead  jb      short loc_140006E31
0x140006eaf  xor     r15d, r15d
0x140006eb2  mov     r8, [rdi+20h]; unsigned __int8 *
0x140006eb6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x140006ebb  lea     rcx, [rbp+10D0h+var_1120]; this
0x140006ebf  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140006ec4  test    al, al
0x140006ec6  jnz     loc_140006E1F
0x140006ecc  mov     rcx, [rbp+10D0h+var_1048]
0x140006ed3  test    rcx, rcx
0x140006ed6  jz      short loc_140006EE4
0x140006ed8  mov     rax, [rcx]
0x140006edb  mov     rax, [rax+18h]
0x140006edf  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006ee4  mov     bl, 1
0x140006ee6  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x140006eea  jz      short loc_140006F61
0x140006eec  mov     eax, [rsp+11D0h+var_1188]
0x140006ef0  mov     rdx, [rsp+11D0h+var_1158]
0x140006ef5  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x140006ef9  sub     r8d, edx
0x140006efc  mov     [rsp+11D0h+var_11A0], 1
0x140006f04  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x140006f08  mov     rcx, r14
0x140006f0b  call    wil_details_NtUpdateWnfStateData
0x140006f10  cmp     eax, 0C0000001h
0x140006f15  jnz     short loc_140006F3F
0x140006f17  inc     r12
0x140006f1a  mov     bl, r15b
0x140006f1d  jmp     short loc_140006F6D
0x140006f1f  mov     rcx, [rbp+10D0h+var_1048]
0x140006f26  xor     r15d, r15d
0x140006f29  test    rcx, rcx
0x140006f2c  jz      short loc_140006F3A
0x140006f2e  mov     rax, [rcx]
0x140006f31  mov     rax, [rax+18h]
0x140006f35  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140006f3a  mov     bl, r15b
0x140006f3d  jmp     short loc_140006EE6
0x140006f3f  test    eax, eax
0x140006f41  jz      short loc_140006F61
0x140006f43  mov     rdx, [rsp+11D0h+var_1158]
0x140006f48  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x140006f4c  sub     r8d, edx
0x140006f4f  mov     [rsp+11D0h+var_11A0], r15d
0x140006f54  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x140006f59  mov     rcx, r14
0x140006f5c  call    wil_details_NtUpdateWnfStateData
0x140006f61  add     r14, 8
0x140006f65  mov     rax, [rbp+10D0h+var_1130]
0x140006f69  mov     [rbp+10D0h+var_1128], rax
0x140006f6d  mov     rsi, [rbp+10D0h+lpMem]
0x140006f71  mov     [rbp+10D0h+lpMem], r15
0x140006f75  test    rsi, rsi
0x140006f78  jz      short loc_140006F8E
0x140006f7a  call    cs:__imp_GetProcessHeap
0x140006f80  mov     rcx, rax; hHeap
0x140006f83  mov     r8, rsi; lpMem
0x140006f86  xor     edx, edx; dwFlags
0x140006f88  call    cs:__imp_HeapFree
0x140006f8e  test    bl, bl
0x140006f90  jnz     short loc_140006FC4
0x140006f92  cmp     r14, r13
0x140006f95  jnb     short loc_140006FC4
0x140006f97  cmp     r12, 32h ; '2'
0x140006f9b  jb      loc_140006C66
0x140006fa1  jmp     short loc_140006FC4
0x140006fa3  mov     rbx, [rbp+10D0h+lpMem]
0x140006fa7  mov     [rbp+10D0h+lpMem], r15
0x140006fab  test    rbx, rbx
0x140006fae  jz      short loc_140006FC4
0x140006fb0  call    cs:__imp_GetProcessHeap
0x140006fb6  mov     rcx, rax; hHeap
0x140006fb9  mov     r8, rbx; lpMem
0x140006fbc  xor     edx, edx; dwFlags
0x140006fbe  call    cs:__imp_HeapFree
0x140006fc4  mov     rcx, [rbp+10D0h+var_40]
0x140006fcb  xor     rcx, rsp; StackCookie
0x140006fce  call    __security_check_cookie
0x140006fd3  mov     rbx, [rsp+11D0h+arg_8]
0x140006fdb  add     rsp, 11A0h
0x140006fe2  pop     r15
0x140006fe4  pop     r14
0x140006fe6  pop     r13
0x140006fe8  pop     r12
0x140006fea  pop     rdi
0x140006feb  pop     rsi
0x140006fec  pop     rbp
0x140006fed  retn
0x140006fee  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
