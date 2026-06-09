# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000632c`
- end: `0x1800066f9`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180005878`

## callees

- `0x180005398`
- `0x180005788`
- `0x18000632c`
- `0x180006e0c`
- `0x180007c4c`
- `0x180009aa0`
- `0x18000c560`
- `0x18000c5f0`
- `0x18000d010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006422`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006422`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000640b`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x18000640b`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000668d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066c3`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000668d`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800066c3`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000667f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066b5`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000667f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800066b5`

## string_xrefs

- `0x180006404`: `ntdll.dll`

## pseudocode

```c
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v4; // r12
  unsigned __int64 v5; // r15
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
  int v17; // ebx
  __int64 v18; // r9
  char v19; // bl
  int updated; // eax
  __int64 v21; // r9
  void *v22; // rsi
  HANDLE ProcessHeap; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  __int64 *v26; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v27; // [rsp+40h] [rbp-C0h] BYREF
  int v28[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v29[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v30; // [rsp+64h] [rbp-9Ch]
  __int16 v31; // [rsp+66h] [rbp-9Ah]
  char v32; // [rsp+68h] [rbp-98h]
  __int64 v33; // [rsp+70h] [rbp-90h]
  __int64 v34; // [rsp+78h] [rbp-88h]
  __int128 v35; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v37; // [rsp+98h] [rbp-68h]
  char v38; // [rsp+9Ah] [rbp-66h]
  __int64 v39; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v40; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v41; // [rsp+B0h] [rbp-50h] BYREF
  char v42; // [rsp+B2h] [rbp-4Eh]
  unsigned int v43; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v44; // [rsp+B8h] [rbp-48h]
  __int128 v45; // [rsp+C0h] [rbp-40h]
  __int16 v46; // [rsp+D0h] [rbp-30h] BYREF
  char v47; // [rsp+D2h] [rbp-2Eh]
  int v48; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v49; // [rsp+D8h] [rbp-28h]
  __int128 v50; // [rsp+E0h] [rbp-20h]
  __int64 v51; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v52; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v53; // [rsp+100h] [rbp+0h] BYREF
  __int64 v54; // [rsp+108h] [rbp+8h] BYREF
  _QWORD v55[13]; // [rsp+118h] [rbp+18h] BYREF
  wil::details::in1diag3 *v56; // [rsp+180h] [rbp+80h]
  _BYTE v57[4096]; // [rsp+190h] [rbp+90h] BYREF

  v4 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v5 = 0;
  v40 = 0;
  v7 = this;
  while ( 1 )
  {
    v8 = *(unsigned __int16 *)(a3 + 6);
    v9 = *(_BYTE *)(a3 + 8);
    v29[0] = *(_WORD *)a3;
    v29[1] = *(_WORD *)(a3 + 2);
    v30 = *(_BYTE *)(a3 + 4);
    v31 = v8;
    v32 = v9;
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
      v33 = v10;
    }
    else
    {
      v33 = 0;
    }
    ProcAddress = (FARPROC)g_wil_details_pfnNtQueryWnfStateData;
    v34 = 0;
    v35 = 0;
    lpMem = 0;
    v37 = 0;
    v38 = 0;
    v28[0] = 0;
    LODWORD(v27) = 4096;
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
      v26 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v7, 0, 0, v28);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      v28[0] = 0;
      LODWORD(v27) = 0;
    }
    else
    {
      v15 = (unsigned int)v27;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v29, v57, v15, 0x1000u);
    if ( HIBYTE(v37) )
      break;
    v39 = 0;
    v55[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v43 = 0;
    v55[1] = &v39;
    v55[2] = &v40;
    v55[3] = v29;
    v56 = (wil::details::in1diag3 *)v55;
    v16 = *(_QWORD *)(a3 + 24);
    v44 = 0;
    v27 = (unsigned __int8 *)(v16 + 10);
    v41 = *(_WORD *)(a3 + 2);
    v42 = *(_BYTE *)(a3 + 4);
    v46 = *(_WORD *)(a3 + 6);
    v47 = *(_BYTE *)(a3 + 8);
    v45 = 0;
    v48 = 0;
    v49 = 0;
    v50 = 0;
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v41,
              &v27,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v17 = 0;
      if ( v43 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v46,
                  &v27,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v28[2] = v48;
          v51 = v49;
          v52 = *((_QWORD *)&v50 + 1);
          v53 = v44;
          v54 = *((_QWORD *)&v45 + 1);
          if ( !v56 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v26 = &v51;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  &v54,
                  &v53,
                  &v52) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
            v19 = 0;
            goto LABEL_29;
          }
          if ( ++v17 >= v43 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
    v19 = 1;
LABEL_29:
    if ( !(_BYTE)v37 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((__int64)v7, v34, (int)v35 - (int)v34, v18, (int)v26, v28[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v7, v34, v35 - v34, v21, (int)v26, 0, 0);
LABEL_37:
      v7 = (wil::details_abi *)((char *)v7 + 8);
      v40 = v39;
      goto LABEL_38;
    }
    ++v5;
    v19 = 0;
LABEL_38:
    v22 = lpMem;
    lpMem = 0;
    if ( v22 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v22);
    }
    if ( v19 || v7 >= v4 || v5 >= 0x32 )
      return;
  }
  v24 = lpMem;
  lpMem = 0;
  if ( v24 )
  {
    v25 = GetProcessHeap();
    HeapFree(v25, 0, v24);
  }
}

```

## disassembly

```asm
0x18000632c  mov     [rsp-8+arg_8], rbx
0x180006331  push    rbp
0x180006332  push    rsi
0x180006333  push    rdi
0x180006334  push    r12
0x180006336  push    r13
0x180006338  push    r14
0x18000633a  push    r15
0x18000633c  lea     rbp, [rsp-10A0h]
0x180006344  mov     eax, 11A0h
0x180006349  call    _alloca_probe
0x18000634e  sub     rsp, rax
0x180006351  mov     rax, cs:__security_cookie
0x180006358  xor     rax, rsp
0x18000635b  mov     [rbp+10D0h+var_40], rax
0x180006362  xor     r13d, r13d
0x180006365  lea     r12, [rcx+rdx*8]
0x180006369  mov     r15d, r13d
0x18000636c  mov     [rbp+10D0h+var_1128], r13
0x180006370  mov     rdi, r8
0x180006373  mov     r14, rcx
0x180006376  movzx   eax, word ptr [rdi]
0x180006379  movzx   edx, word ptr [rdi+6]
0x18000637d  mov     cl, [rdi+8]
0x180006380  mov     [rsp+11D0h+var_1170], ax
0x180006385  movzx   eax, word ptr [rdi+2]
0x180006389  mov     [rsp+11D0h+var_116E], ax
0x18000638e  mov     al, [rdi+4]
0x180006391  mov     [rsp+11D0h+var_116C], al
0x180006395  mov     [rsp+11D0h+var_116A], dx
0x18000639a  mov     [rsp+11D0h+var_1168], cl
0x18000639e  test    dx, dx
0x1800063a1  jz      short loc_1800063C0
0x1800063a3  mov     eax, edx
0x1800063a5  cmp     cl, 1
0x1800063a8  jnz     short loc_1800063B0
0x1800063aa  add     rax, 2
0x1800063ae  jmp     short loc_1800063B9
0x1800063b0  cmp     cl, 2
0x1800063b3  jnz     short loc_1800063B9
0x1800063b5  add     rax, 4
0x1800063b9  mov     [rsp+11D0h+var_1160], rax
0x1800063be  jmp     short loc_1800063C5
0x1800063c0  mov     [rsp+11D0h+var_1160], r13
0x1800063c5  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800063cc  xorps   xmm0, xmm0
0x1800063cf  mov     [rsp+11D0h+var_1158], r13
0x1800063d4  movdqa  [rbp+10D0h+var_1150], xmm0
0x1800063d9  mov     [rbp+10D0h+lpMem], r13
0x1800063dd  mov     [rbp+10D0h+var_1138], r13w
0x1800063e2  mov     [rbp+10D0h+var_1136], r13b
0x1800063e6  mov     [rsp+11D0h+var_1188], r13d
0x1800063eb  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x1800063f3  test    rax, rax
0x1800063f6  jnz     short loc_18000643B
0x1800063f8  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800063ff  test    rax, rax
0x180006402  jnz     short loc_180006418
0x180006404  lea     rcx, ModuleName; "ntdll.dll"
0x18000640b  call    cs:__imp_GetModuleHandleW
0x180006411  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006418  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18000641f  mov     rcx, rax; hModule
0x180006422  call    cs:__imp_GetProcAddress
0x180006428  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18000642f  test    rax, rax
0x180006432  jnz     short loc_18000643B
0x180006434  mov     ebx, 0C0000139h
0x180006439  jmp     short loc_180006465
0x18000643b  lea     rcx, [rsp+11D0h+var_1190]
0x180006440  xor     r8d, r8d
0x180006443  mov     [rsp+11D0h+var_11A8], rcx
0x180006448  lea     r9, [rsp+11D0h+var_1188]
0x18000644d  lea     rcx, [rbp+10D0h+var_1040]
0x180006454  xor     edx, edx
0x180006456  mov     [rsp+11D0h+var_11B0], rcx
0x18000645b  mov     rcx, r14
0x18000645e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006463  mov     ebx, eax
0x180006465  mov     ecx, ebx; this
0x180006467  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x18000646c  test    ebx, ebx
0x18000646e  jz      short loc_18000647E
0x180006470  mov     eax, r13d
0x180006473  mov     [rsp+11D0h+var_1188], r13d
0x180006478  mov     dword ptr [rsp+11D0h+var_1190], eax
0x18000647c  jmp     short loc_180006482
0x18000647e  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180006482  mov     r8d, eax; unsigned __int64
0x180006485  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000648c  mov     r9d, 1000h; unsigned __int64
0x180006492  lea     rcx, [rsp+11D0h+var_1170]; this
0x180006497  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x18000649c  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x1800064a0  jnz     loc_1800066A8
0x1800064a6  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x1800064ad  mov     [rbp+10D0h+var_1130], r13
0x1800064b1  mov     [rbp+10D0h+var_10B8], rax
0x1800064b5  xorps   xmm0, xmm0
0x1800064b8  lea     rax, [rbp+10D0h+var_1130]
0x1800064bc  mov     [rbp+10D0h+var_111C], r13d
0x1800064c0  mov     [rbp+10D0h+var_10B0], rax
0x1800064c4  lea     rax, [rbp+10D0h+var_1128]
0x1800064c8  mov     [rbp+10D0h+var_10A8], rax
0x1800064cc  lea     rax, [rsp+11D0h+var_1170]
0x1800064d1  mov     [rbp+10D0h+var_10A0], rax
0x1800064d5  lea     rax, [rbp+10D0h+var_10B8]
0x1800064d9  mov     [rbp+10D0h+var_1050], rax
0x1800064e0  mov     rax, [rdi+18h]
0x1800064e4  add     rax, 0Ah
0x1800064e8  mov     [rbp+10D0h+var_1118], r13w
0x1800064ed  mov     [rsp+11D0h+var_1190], rax
0x1800064f2  movzx   eax, word ptr [rdi+2]
0x1800064f6  mov     [rbp+10D0h+var_1120], ax
0x1800064fa  mov     al, [rdi+4]
0x1800064fd  mov     [rbp+10D0h+var_111E], al
0x180006500  movzx   eax, word ptr [rdi+6]
0x180006504  mov     [rbp+10D0h+var_1100], ax
0x180006508  mov     al, [rdi+8]
0x18000650b  mov     [rbp+10D0h+var_10FE], al
0x18000650e  movdqu  [rbp+10D0h+var_1110], xmm0
0x180006513  mov     [rbp+10D0h+var_10FC], r13d
0x180006517  mov     [rbp+10D0h+var_10F8], r13w
0x18000651c  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180006521  jmp     loc_1800065BA
0x180006526  mov     ebx, r13d
0x180006529  cmp     [rbp+10D0h+var_111C], r13d
0x18000652d  jbe     loc_1800065BA
0x180006533  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006537  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000653c  lea     rcx, [rbp+10D0h+var_1100]; this
0x180006540  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006545  test    al, al
0x180006547  jz      short loc_1800065BA
0x180006549  mov     eax, [rbp+10D0h+var_10FC]
0x18000654c  mov     rcx, [rbp+10D0h+var_1050]; this
0x180006553  mov     [rsp+11D0h+var_1180], eax
0x180006557  movzx   eax, [rbp+10D0h+var_10F8]
0x18000655b  mov     [rbp+10D0h+var_10E0], rax
0x18000655f  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180006563  mov     [rbp+10D0h+var_10D8], rax
0x180006567  movzx   eax, [rbp+10D0h+var_1118]
0x18000656b  mov     [rbp+10D0h+var_10D0], rax
0x18000656f  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x180006573  mov     [rbp+10D0h+var_10C8], rax
0x180006577  test    rcx, rcx
0x18000657a  jz      loc_1800066F3
0x180006580  mov     rax, [rcx]
0x180006583  lea     rdx, [rsp+11D0h+var_1180]
0x180006588  mov     [rsp+11D0h+var_11A8], rdx
0x18000658d  lea     r9, [rbp+10D0h+var_10D8]
0x180006591  lea     rdx, [rbp+10D0h+var_10E0]
0x180006595  mov     [rsp+11D0h+var_11B0], rdx
0x18000659a  lea     r8, [rbp+10D0h+var_10D0]
0x18000659e  mov     rax, [rax+20h]
0x1800065a2  lea     rdx, [rbp+10D0h+var_10C8]
0x1800065a6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ab  test    al, al
0x1800065ad  jz      short loc_180006627
0x1800065af  inc     ebx
0x1800065b1  cmp     ebx, [rbp+10D0h+var_111C]
0x1800065b4  jb      loc_180006533
0x1800065ba  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800065be  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800065c3  lea     rcx, [rbp+10D0h+var_1120]; this
0x1800065c7  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800065cc  test    al, al
0x1800065ce  jnz     loc_180006526
0x1800065d4  mov     rcx, [rbp+10D0h+var_1050]
0x1800065db  test    rcx, rcx
0x1800065de  jz      short loc_1800065EC
0x1800065e0  mov     rax, [rcx]
0x1800065e3  mov     rax, [rax+18h]
0x1800065e7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800065ec  mov     bl, 1
0x1800065ee  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x1800065f2  jz      short loc_180006666
0x1800065f4  mov     rdx, [rsp+11D0h+var_1158]
0x1800065f9  mov     rcx, r14
0x1800065fc  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006600  mov     eax, [rsp+11D0h+var_1188]
0x180006604  sub     r8d, edx
0x180006607  mov     [rsp+11D0h+var_11A0], 1
0x18000660f  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180006613  call    wil_details_NtUpdateWnfStateData
0x180006618  cmp     eax, 0C0000001h
0x18000661d  jnz     short loc_180006644
0x18000661f  inc     r15
0x180006622  mov     bl, r13b
0x180006625  jmp     short loc_180006672
0x180006627  mov     rcx, [rbp+10D0h+var_1050]
0x18000662e  test    rcx, rcx
0x180006631  jz      short loc_18000663F
0x180006633  mov     rax, [rcx]
0x180006636  mov     rax, [rax+18h]
0x18000663a  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000663f  mov     bl, r13b
0x180006642  jmp     short loc_1800065EE
0x180006644  test    eax, eax
0x180006646  jz      short loc_180006666
0x180006648  mov     rdx, [rsp+11D0h+var_1158]
0x18000664d  mov     rcx, r14
0x180006650  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006654  sub     r8d, edx
0x180006657  mov     [rsp+11D0h+var_11A0], r13d
0x18000665c  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x180006661  call    wil_details_NtUpdateWnfStateData
0x180006666  mov     rax, [rbp+10D0h+var_1130]
0x18000666a  add     r14, 8
0x18000666e  mov     [rbp+10D0h+var_1128], rax
0x180006672  mov     rsi, [rbp+10D0h+lpMem]
0x180006676  mov     [rbp+10D0h+lpMem], r13
0x18000667a  test    rsi, rsi
0x18000667d  jz      short loc_180006693
0x18000667f  call    cs:__imp_GetProcessHeap
0x180006685  mov     r8, rsi; lpMem
0x180006688  xor     edx, edx; dwFlags
0x18000668a  mov     rcx, rax; hHeap
0x18000668d  call    cs:__imp_HeapFree
0x180006693  test    bl, bl
0x180006695  jnz     short loc_1800066C9
0x180006697  cmp     r14, r12
0x18000669a  jnb     short loc_1800066C9
0x18000669c  cmp     r15, 32h ; '2'
0x1800066a0  jb      loc_180006376
0x1800066a6  jmp     short loc_1800066C9
0x1800066a8  mov     rbx, [rbp+10D0h+lpMem]
0x1800066ac  mov     [rbp+10D0h+lpMem], r13
0x1800066b0  test    rbx, rbx
0x1800066b3  jz      short loc_1800066C9
0x1800066b5  call    cs:__imp_GetProcessHeap
0x1800066bb  mov     r8, rbx; lpMem
0x1800066be  xor     edx, edx; dwFlags
0x1800066c0  mov     rcx, rax; hHeap
0x1800066c3  call    cs:__imp_HeapFree
0x1800066c9  mov     rcx, [rbp+10D0h+var_40]
0x1800066d0  xor     rcx, rsp; StackCookie
0x1800066d3  call    __security_check_cookie
0x1800066d8  mov     rbx, [rsp+11D0h+arg_8]
0x1800066e0  add     rsp, 11A0h
0x1800066e7  pop     r15
0x1800066e9  pop     r14
0x1800066eb  pop     r13
0x1800066ed  pop     r12
0x1800066ef  pop     rdi
0x1800066f0  pop     rsi
0x1800066f1  pop     rbp
0x1800066f2  retn
0x1800066f3  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
