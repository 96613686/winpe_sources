# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x140008e4c`
- end: `0x140009224`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x140008334`

## callees

- `0x1400016a0`
- `0x140007bb8`
- `0x140008234`
- `0x140008e4c`
- `0x140009d6c`
- `0x14000b51c`
- `0x14000c700`
- `0x140010d80`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008f2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x140008f2c`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008f43`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x140008f43`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400091b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400091ee`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400091b8`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1400091ee`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400091aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400091e0`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400091aa`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1400091e0`

## string_xrefs

- `0x140008f25`: `ntdll.dll`

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
0x140008e4c  mov     [rsp-8+arg_8], rbx
0x140008e51  push    rbp
0x140008e52  push    rsi
0x140008e53  push    rdi
0x140008e54  push    r12
0x140008e56  push    r13
0x140008e58  push    r14
0x140008e5a  push    r15
0x140008e5c  lea     rbp, [rsp-10A0h]
0x140008e64  mov     eax, 11A0h
0x140008e69  call    _alloca_probe
0x140008e6e  sub     rsp, rax
0x140008e71  mov     rax, cs:__security_cookie
0x140008e78  xor     rax, rsp
0x140008e7b  mov     [rbp+10D0h+var_40], rax
0x140008e82  mov     rdi, r8
0x140008e85  mov     r14, rcx
0x140008e88  lea     r13, [rcx+rdx*8]
0x140008e8c  xor     r15d, r15d
0x140008e8f  mov     r12d, r15d
0x140008e92  mov     [rbp+10D0h+var_1128], r15
0x140008e96  mov     cl, [rdi+8]
0x140008e99  movzx   edx, word ptr [rdi+6]
0x140008e9d  movzx   eax, word ptr [rdi]
0x140008ea0  mov     [rsp+11D0h+var_1170], ax
0x140008ea5  movzx   eax, word ptr [rdi+2]
0x140008ea9  mov     [rsp+11D0h+var_116E], ax
0x140008eae  mov     al, [rdi+4]
0x140008eb1  mov     [rsp+11D0h+var_116C], al
0x140008eb5  mov     [rsp+11D0h+var_116A], dx
0x140008eba  mov     [rsp+11D0h+var_1168], cl
0x140008ebe  test    dx, dx
0x140008ec1  jz      short loc_140008EE0
0x140008ec3  mov     eax, edx
0x140008ec5  cmp     cl, 1
0x140008ec8  jnz     short loc_140008ED0
0x140008eca  add     rax, 2
0x140008ece  jmp     short loc_140008ED9
0x140008ed0  cmp     cl, 2
0x140008ed3  jnz     short loc_140008ED9
0x140008ed5  add     rax, 4
0x140008ed9  mov     [rsp+11D0h+var_1160], rax
0x140008ede  jmp     short loc_140008EE5
0x140008ee0  mov     [rsp+11D0h+var_1160], r15
0x140008ee5  mov     [rsp+11D0h+var_1158], r15
0x140008eea  xorps   xmm0, xmm0
0x140008eed  movdqa  [rbp+10D0h+var_1150], xmm0
0x140008ef2  mov     [rbp+10D0h+lpMem], r15
0x140008ef6  mov     [rbp+10D0h+var_1138], 0
0x140008efc  mov     [rbp+10D0h+var_1136], r15b
0x140008f00  mov     [rsp+11D0h+var_1188], r15d
0x140008f05  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x140008f0d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x140008f14  test    rax, rax
0x140008f17  jnz     short loc_140008F5C
0x140008f19  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008f20  test    rax, rax
0x140008f23  jnz     short loc_140008F39
0x140008f25  lea     rcx, ModuleName; "ntdll.dll"
0x140008f2c  call    cs:__imp_GetModuleHandleW
0x140008f32  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x140008f39  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x140008f40  mov     rcx, rax; hModule
0x140008f43  call    cs:__imp_GetProcAddress
0x140008f49  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x140008f50  test    rax, rax
0x140008f53  jnz     short loc_140008F5C
0x140008f55  mov     ebx, 0C0000139h
0x140008f5a  jmp     short loc_140008F86
0x140008f5c  lea     rcx, [rsp+11D0h+var_1190]
0x140008f61  mov     [rsp+11D0h+var_11A8], rcx
0x140008f66  lea     rcx, [rbp+10D0h+var_1040]
0x140008f6d  mov     [rsp+11D0h+var_11B0], rcx
0x140008f72  lea     r9, [rsp+11D0h+var_1188]
0x140008f77  xor     r8d, r8d
0x140008f7a  xor     edx, edx
0x140008f7c  mov     rcx, r14
0x140008f7f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140008f84  mov     ebx, eax
0x140008f86  mov     ecx, ebx; this
0x140008f88  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x140008f8d  test    ebx, ebx
0x140008f8f  jz      short loc_140008F9F
0x140008f91  mov     eax, r15d
0x140008f94  mov     dword ptr [rsp+11D0h+var_1190], eax
0x140008f98  mov     [rsp+11D0h+var_1188], r15d
0x140008f9d  jmp     short loc_140008FA3
0x140008f9f  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x140008fa3  mov     r8d, eax; unsigned __int64
0x140008fa6  mov     r9d, 1000h; unsigned __int64
0x140008fac  lea     rdx, [rbp+10D0h+var_1040]; void *
0x140008fb3  lea     rcx, [rsp+11D0h+var_1170]; this
0x140008fb8  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x140008fbd  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x140008fc1  jnz     loc_1400091D3
0x140008fc7  mov     [rbp+10D0h+var_1130], r15
0x140008fcb  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x140008fd2  mov     [rbp+10D0h+var_10B0], rax
0x140008fd6  lea     rax, [rbp+10D0h+var_1130]
0x140008fda  mov     [rbp+10D0h+var_10A8], rax
0x140008fde  lea     rax, [rbp+10D0h+var_1128]
0x140008fe2  mov     [rbp+10D0h+var_10A0], rax
0x140008fe6  lea     rax, [rsp+11D0h+var_1170]
0x140008feb  mov     [rbp+10D0h+var_1098], rax
0x140008fef  lea     rax, [rbp+10D0h+var_10B0]
0x140008ff3  mov     [rbp+10D0h+var_1048], rax
0x140008ffa  lea     rax, [rbp+10D0h+var_10B8]
0x140008ffe  mov     [rbp+10D0h+var_10C0], rax
0x140009002  mov     rax, [rdi+18h]
0x140009006  add     rax, 0Ah
0x14000900a  mov     [rsp+11D0h+var_1190], rax
0x14000900f  movzx   eax, word ptr [rdi+2]
0x140009013  mov     [rbp+10D0h+var_1120], ax
0x140009017  mov     al, [rdi+4]
0x14000901a  mov     [rbp+10D0h+var_111E], al
0x14000901d  mov     [rbp+10D0h+var_111C], r15d
0x140009021  mov     [rbp+10D0h+var_1118], r15w
0x140009026  xorps   xmm0, xmm0
0x140009029  movdqu  [rbp+10D0h+var_1110], xmm0
0x14000902e  movzx   eax, word ptr [rdi+6]
0x140009032  mov     [rbp+10D0h+var_1100], ax
0x140009036  mov     al, [rdi+8]
0x140009039  mov     [rbp+10D0h+var_10FE], al
0x14000903c  mov     [rbp+10D0h+var_10FC], r15d
0x140009040  mov     [rbp+10D0h+var_10F8], r15w
0x140009045  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14000904a  jmp     loc_1400090E2
0x14000904f  mov     ebx, r15d
0x140009052  mov     esi, [rbp+10D0h+var_111C]
0x140009055  test    esi, esi
0x140009057  jz      loc_1400090E2
0x14000905d  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x140009061  mov     r8, [rdi+20h]; unsigned __int8 *
0x140009065  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000906a  lea     rcx, [rbp+10D0h+var_1100]; this
0x14000906e  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x140009073  test    al, al
0x140009075  jz      short loc_1400090DF
0x140009077  mov     eax, [rbp+10D0h+var_10FC]
0x14000907a  mov     [rsp+11D0h+var_1180], eax
0x14000907e  movzx   eax, [rbp+10D0h+var_10F8]
0x140009082  mov     [rbp+10D0h+var_10E0], rax
0x140009086  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000908a  mov     [rbp+10D0h+var_10D8], rax
0x14000908e  movzx   eax, [rbp+10D0h+var_1118]
0x140009092  mov     [rbp+10D0h+var_10D0], rax
0x140009096  mov     [rbp+10D0h+var_10C8], r15
0x14000909a  mov     rcx, [rbp+10D0h+var_1048]; this
0x1400090a1  test    rcx, rcx
0x1400090a4  jz      loc_14000921E
0x1400090aa  mov     rax, [rcx]
0x1400090ad  lea     rdx, [rsp+11D0h+var_1180]
0x1400090b2  mov     [rsp+11D0h+var_11A8], rdx
0x1400090b7  lea     rdx, [rbp+10D0h+var_10E0]
0x1400090bb  mov     [rsp+11D0h+var_11B0], rdx
0x1400090c0  lea     r9, [rbp+10D0h+var_10D8]
0x1400090c4  lea     r8, [rbp+10D0h+var_10D0]
0x1400090c8  lea     rdx, [rbp+10D0h+var_10C8]
0x1400090cc  mov     rax, [rax+20h]
0x1400090d0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400090d5  test    al, al
0x1400090d7  jz      short loc_14000914F
0x1400090d9  inc     ebx
0x1400090db  cmp     ebx, esi
0x1400090dd  jb      short loc_140009061
0x1400090df  xor     r15d, r15d
0x1400090e2  mov     r8, [rdi+20h]; unsigned __int8 *
0x1400090e6  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1400090eb  lea     rcx, [rbp+10D0h+var_1120]; this
0x1400090ef  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1400090f4  test    al, al
0x1400090f6  jnz     loc_14000904F
0x1400090fc  mov     rcx, [rbp+10D0h+var_1048]
0x140009103  test    rcx, rcx
0x140009106  jz      short loc_140009114
0x140009108  mov     rax, [rcx]
0x14000910b  mov     rax, [rax+18h]
0x14000910f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140009114  mov     bl, 1
0x140009116  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x14000911a  jz      short loc_140009191
0x14000911c  mov     eax, [rsp+11D0h+var_1188]
0x140009120  mov     rdx, [rsp+11D0h+var_1158]
0x140009125  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x140009129  sub     r8d, edx
0x14000912c  mov     [rsp+11D0h+var_11A0], 1
0x140009134  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x140009138  mov     rcx, r14
0x14000913b  call    wil_details_NtUpdateWnfStateData
0x140009140  cmp     eax, 0C0000001h
0x140009145  jnz     short loc_14000916F
0x140009147  inc     r12
0x14000914a  mov     bl, r15b
0x14000914d  jmp     short loc_14000919D
0x14000914f  mov     rcx, [rbp+10D0h+var_1048]
0x140009156  xor     r15d, r15d
0x140009159  test    rcx, rcx
0x14000915c  jz      short loc_14000916A
0x14000915e  mov     rax, [rcx]
0x140009161  mov     rax, [rax+18h]
0x140009165  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000916a  mov     bl, r15b
0x14000916d  jmp     short loc_140009116
0x14000916f  test    eax, eax
0x140009171  jz      short loc_140009191
0x140009173  mov     rdx, [rsp+11D0h+var_1158]
0x140009178  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000917c  sub     r8d, edx
0x14000917f  mov     [rsp+11D0h+var_11A0], r15d
0x140009184  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x140009189  mov     rcx, r14
0x14000918c  call    wil_details_NtUpdateWnfStateData
0x140009191  add     r14, 8
0x140009195  mov     rax, [rbp+10D0h+var_1130]
0x140009199  mov     [rbp+10D0h+var_1128], rax
0x14000919d  mov     rsi, [rbp+10D0h+lpMem]
0x1400091a1  mov     [rbp+10D0h+lpMem], r15
0x1400091a5  test    rsi, rsi
0x1400091a8  jz      short loc_1400091BE
0x1400091aa  call    cs:__imp_GetProcessHeap
0x1400091b0  mov     rcx, rax; hHeap
0x1400091b3  mov     r8, rsi; lpMem
0x1400091b6  xor     edx, edx; dwFlags
0x1400091b8  call    cs:__imp_HeapFree
0x1400091be  test    bl, bl
0x1400091c0  jnz     short loc_1400091F4
0x1400091c2  cmp     r14, r13
0x1400091c5  jnb     short loc_1400091F4
0x1400091c7  cmp     r12, 32h ; '2'
0x1400091cb  jb      loc_140008E96
0x1400091d1  jmp     short loc_1400091F4
0x1400091d3  mov     rbx, [rbp+10D0h+lpMem]
0x1400091d7  mov     [rbp+10D0h+lpMem], r15
0x1400091db  test    rbx, rbx
0x1400091de  jz      short loc_1400091F4
0x1400091e0  call    cs:__imp_GetProcessHeap
0x1400091e6  mov     rcx, rax; hHeap
0x1400091e9  mov     r8, rbx; lpMem
0x1400091ec  xor     edx, edx; dwFlags
0x1400091ee  call    cs:__imp_HeapFree
0x1400091f4  mov     rcx, [rbp+10D0h+var_40]
0x1400091fb  xor     rcx, rsp; StackCookie
0x1400091fe  call    __security_check_cookie
0x140009203  mov     rbx, [rsp+11D0h+arg_8]
0x14000920b  add     rsp, 11A0h
0x140009212  pop     r15
0x140009214  pop     r14
0x140009216  pop     r13
0x140009218  pop     r12
0x14000921a  pop     rdi
0x14000921b  pop     rsi
0x14000921c  pop     rbp
0x14000921d  retn
0x14000921e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
