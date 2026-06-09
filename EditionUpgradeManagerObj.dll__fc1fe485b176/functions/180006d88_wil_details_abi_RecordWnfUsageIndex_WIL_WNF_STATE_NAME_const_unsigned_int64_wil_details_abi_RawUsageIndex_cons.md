# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180006d88`
- end: `0x180007158`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `976`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180006288`

## callees

- `0x180001ac0`
- `0x180005d88`
- `0x180006188`
- `0x180006d88`
- `0x180007748`
- `0x1800086ec`
- `0x180008d10`
- `0x1800228f0`
- `0x180023010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006e7f`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006e68`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006e68`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007122`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800070ec`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180007122`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800070de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007114`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800070de`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180007114`

## string_xrefs

- `0x180006e61`: `ntdll.dll`

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
0x180006d88  mov     [rsp-8+arg_8], rbx
0x180006d8d  push    rbp
0x180006d8e  push    rsi
0x180006d8f  push    rdi
0x180006d90  push    r12
0x180006d92  push    r13
0x180006d94  push    r14
0x180006d96  push    r15
0x180006d98  lea     rbp, [rsp-10A0h]
0x180006da0  mov     eax, 11A0h
0x180006da5  call    _alloca_probe
0x180006daa  sub     rsp, rax
0x180006dad  mov     rax, cs:__security_cookie
0x180006db4  xor     rax, rsp
0x180006db7  mov     [rbp+10D0h+var_40], rax
0x180006dbe  xor     r15d, r15d
0x180006dc1  lea     r13, [rcx+rdx*8]
0x180006dc5  mov     r12d, r15d
0x180006dc8  mov     [rbp+10D0h+var_1128], r15
0x180006dcc  mov     rdi, r8
0x180006dcf  mov     r14, rcx
0x180006dd2  movzx   eax, word ptr [rdi]
0x180006dd5  movzx   edx, word ptr [rdi+6]
0x180006dd9  mov     cl, [rdi+8]
0x180006ddc  mov     [rsp+11D0h+var_1170], ax
0x180006de1  movzx   eax, word ptr [rdi+2]
0x180006de5  mov     [rsp+11D0h+var_116E], ax
0x180006dea  mov     al, [rdi+4]
0x180006ded  mov     [rsp+11D0h+var_116C], al
0x180006df1  mov     [rsp+11D0h+var_116A], dx
0x180006df6  mov     [rsp+11D0h+var_1168], cl
0x180006dfa  test    dx, dx
0x180006dfd  jz      short loc_180006E1C
0x180006dff  mov     eax, edx
0x180006e01  cmp     cl, 1
0x180006e04  jnz     short loc_180006E0C
0x180006e06  add     rax, 2
0x180006e0a  jmp     short loc_180006E15
0x180006e0c  cmp     cl, 2
0x180006e0f  jnz     short loc_180006E15
0x180006e11  add     rax, 4
0x180006e15  mov     [rsp+11D0h+var_1160], rax
0x180006e1a  jmp     short loc_180006E21
0x180006e1c  mov     [rsp+11D0h+var_1160], r15
0x180006e21  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180006e28  xorps   xmm0, xmm0
0x180006e2b  mov     [rsp+11D0h+var_1158], r15
0x180006e30  movdqa  [rbp+10D0h+var_1150], xmm0
0x180006e35  mov     [rbp+10D0h+lpMem], r15
0x180006e39  mov     [rbp+10D0h+var_1138], 0
0x180006e3f  mov     [rbp+10D0h+var_1136], r15b
0x180006e43  mov     [rsp+11D0h+var_1188], r15d
0x180006e48  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180006e50  test    rax, rax
0x180006e53  jnz     short loc_180006E98
0x180006e55  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006e5c  test    rax, rax
0x180006e5f  jnz     short loc_180006E75
0x180006e61  lea     rcx, ModuleName; "ntdll.dll"
0x180006e68  call    cs:__imp_GetModuleHandleW
0x180006e6e  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006e75  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180006e7c  mov     rcx, rax; hModule
0x180006e7f  call    cs:__imp_GetProcAddress
0x180006e85  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180006e8c  test    rax, rax
0x180006e8f  jnz     short loc_180006E98
0x180006e91  mov     ebx, 0C0000139h
0x180006e96  jmp     short loc_180006EC2
0x180006e98  lea     rcx, [rsp+11D0h+var_1190]
0x180006e9d  xor     r8d, r8d
0x180006ea0  mov     [rsp+11D0h+var_11A8], rcx
0x180006ea5  lea     r9, [rsp+11D0h+var_1188]
0x180006eaa  lea     rcx, [rbp+10D0h+var_1040]
0x180006eb1  xor     edx, edx
0x180006eb3  mov     [rsp+11D0h+var_11B0], rcx
0x180006eb8  mov     rcx, r14
0x180006ebb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ec0  mov     ebx, eax
0x180006ec2  mov     ecx, ebx; this
0x180006ec4  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180006ec9  test    ebx, ebx
0x180006ecb  jz      short loc_180006EDB
0x180006ecd  mov     eax, r15d
0x180006ed0  mov     [rsp+11D0h+var_1188], r15d
0x180006ed5  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180006ed9  jmp     short loc_180006EDF
0x180006edb  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180006edf  mov     r8d, eax; unsigned __int64
0x180006ee2  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180006ee9  mov     r9d, 1000h; unsigned __int64
0x180006eef  lea     rcx, [rsp+11D0h+var_1170]; this
0x180006ef4  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180006ef9  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180006efd  jnz     loc_180007107
0x180006f03  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180006f0a  mov     [rbp+10D0h+var_1130], r15
0x180006f0e  mov     [rbp+10D0h+var_10B8], rax
0x180006f12  xorps   xmm0, xmm0
0x180006f15  lea     rax, [rbp+10D0h+var_1130]
0x180006f19  mov     [rbp+10D0h+var_111C], r15d
0x180006f1d  mov     [rbp+10D0h+var_10B0], rax
0x180006f21  lea     rax, [rbp+10D0h+var_1128]
0x180006f25  mov     [rbp+10D0h+var_10A8], rax
0x180006f29  lea     rax, [rsp+11D0h+var_1170]
0x180006f2e  mov     [rbp+10D0h+var_10A0], rax
0x180006f32  lea     rax, [rbp+10D0h+var_10B8]
0x180006f36  mov     [rbp+10D0h+var_1050], rax
0x180006f3d  mov     rax, [rdi+18h]
0x180006f41  add     rax, 0Ah
0x180006f45  mov     [rbp+10D0h+var_1118], r15w
0x180006f4a  mov     [rsp+11D0h+var_1190], rax
0x180006f4f  movzx   eax, word ptr [rdi+2]
0x180006f53  mov     [rbp+10D0h+var_1120], ax
0x180006f57  mov     al, [rdi+4]
0x180006f5a  mov     [rbp+10D0h+var_111E], al
0x180006f5d  movzx   eax, word ptr [rdi+6]
0x180006f61  mov     [rbp+10D0h+var_1100], ax
0x180006f65  mov     al, [rdi+8]
0x180006f68  mov     [rbp+10D0h+var_10FE], al
0x180006f6b  movdqu  [rbp+10D0h+var_1110], xmm0
0x180006f70  mov     [rbp+10D0h+var_10FC], r15d
0x180006f74  mov     [rbp+10D0h+var_10F8], r15w
0x180006f79  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180006f7e  jmp     loc_180007016
0x180006f83  mov     esi, [rbp+10D0h+var_111C]
0x180006f86  mov     ebx, r15d
0x180006f89  test    esi, esi
0x180006f8b  jz      loc_180007016
0x180006f91  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180006f95  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006f99  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180006f9e  lea     rcx, [rbp+10D0h+var_1100]; this
0x180006fa2  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006fa7  test    al, al
0x180006fa9  jz      short loc_180007013
0x180006fab  mov     eax, [rbp+10D0h+var_10FC]
0x180006fae  mov     rcx, [rbp+10D0h+var_1050]; this
0x180006fb5  mov     [rsp+11D0h+var_1180], eax
0x180006fb9  movzx   eax, [rbp+10D0h+var_10F8]
0x180006fbd  mov     [rbp+10D0h+var_10E0], rax
0x180006fc1  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180006fc5  mov     [rbp+10D0h+var_10D8], rax
0x180006fc9  movzx   eax, [rbp+10D0h+var_1118]
0x180006fcd  mov     [rbp+10D0h+var_10D0], rax
0x180006fd1  mov     [rbp+10D0h+var_10C8], r15
0x180006fd5  test    rcx, rcx
0x180006fd8  jz      loc_180007152
0x180006fde  mov     rax, [rcx]
0x180006fe1  lea     rdx, [rsp+11D0h+var_1180]
0x180006fe6  mov     [rsp+11D0h+var_11A8], rdx
0x180006feb  lea     r9, [rbp+10D0h+var_10D8]
0x180006fef  lea     rdx, [rbp+10D0h+var_10E0]
0x180006ff3  mov     [rsp+11D0h+var_11B0], rdx
0x180006ff8  lea     r8, [rbp+10D0h+var_10D0]
0x180006ffc  mov     rax, [rax+20h]
0x180007000  lea     rdx, [rbp+10D0h+var_10C8]
0x180007004  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007009  test    al, al
0x18000700b  jz      short loc_180007083
0x18000700d  inc     ebx
0x18000700f  cmp     ebx, esi
0x180007011  jb      short loc_180006F95
0x180007013  xor     r15d, r15d
0x180007016  mov     r8, [rdi+20h]; unsigned __int8 *
0x18000701a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18000701f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180007023  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180007028  test    al, al
0x18000702a  jnz     loc_180006F83
0x180007030  mov     rcx, [rbp+10D0h+var_1050]
0x180007037  test    rcx, rcx
0x18000703a  jz      short loc_180007048
0x18000703c  mov     rax, [rcx]
0x18000703f  mov     rax, [rax+18h]
0x180007043  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007048  mov     bl, 1
0x18000704a  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x18000704e  jz      short loc_1800070C5
0x180007050  mov     rdx, [rsp+11D0h+var_1158]
0x180007055  mov     rcx, r14
0x180007058  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18000705c  mov     eax, [rsp+11D0h+var_1188]
0x180007060  sub     r8d, edx
0x180007063  mov     [rsp+11D0h+var_11A0], 1
0x18000706b  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18000706f  call    wil_details_NtUpdateWnfStateData
0x180007074  cmp     eax, 0C0000001h
0x180007079  jnz     short loc_1800070A3
0x18000707b  inc     r12
0x18000707e  mov     bl, r15b
0x180007081  jmp     short loc_1800070D1
0x180007083  mov     rcx, [rbp+10D0h+var_1050]
0x18000708a  xor     r15d, r15d
0x18000708d  test    rcx, rcx
0x180007090  jz      short loc_18000709E
0x180007092  mov     rax, [rcx]
0x180007095  mov     rax, [rax+18h]
0x180007099  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000709e  mov     bl, r15b
0x1800070a1  jmp     short loc_18000704A
0x1800070a3  test    eax, eax
0x1800070a5  jz      short loc_1800070C5
0x1800070a7  mov     rdx, [rsp+11D0h+var_1158]
0x1800070ac  mov     rcx, r14
0x1800070af  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800070b3  sub     r8d, edx
0x1800070b6  mov     [rsp+11D0h+var_11A0], r15d
0x1800070bb  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x1800070c0  call    wil_details_NtUpdateWnfStateData
0x1800070c5  mov     rax, [rbp+10D0h+var_1130]
0x1800070c9  add     r14, 8
0x1800070cd  mov     [rbp+10D0h+var_1128], rax
0x1800070d1  mov     rsi, [rbp+10D0h+lpMem]
0x1800070d5  mov     [rbp+10D0h+lpMem], r15
0x1800070d9  test    rsi, rsi
0x1800070dc  jz      short loc_1800070F2
0x1800070de  call    cs:__imp_GetProcessHeap
0x1800070e4  mov     r8, rsi; lpMem
0x1800070e7  xor     edx, edx; dwFlags
0x1800070e9  mov     rcx, rax; hHeap
0x1800070ec  call    cs:__imp_HeapFree
0x1800070f2  test    bl, bl
0x1800070f4  jnz     short loc_180007128
0x1800070f6  cmp     r14, r13
0x1800070f9  jnb     short loc_180007128
0x1800070fb  cmp     r12, 32h ; '2'
0x1800070ff  jb      loc_180006DD2
0x180007105  jmp     short loc_180007128
0x180007107  mov     rbx, [rbp+10D0h+lpMem]
0x18000710b  mov     [rbp+10D0h+lpMem], r15
0x18000710f  test    rbx, rbx
0x180007112  jz      short loc_180007128
0x180007114  call    cs:__imp_GetProcessHeap
0x18000711a  mov     r8, rbx; lpMem
0x18000711d  xor     edx, edx; dwFlags
0x18000711f  mov     rcx, rax; hHeap
0x180007122  call    cs:__imp_HeapFree
0x180007128  mov     rcx, [rbp+10D0h+var_40]
0x18000712f  xor     rcx, rsp; StackCookie
0x180007132  call    __security_check_cookie
0x180007137  mov     rbx, [rsp+11D0h+arg_8]
0x18000713f  add     rsp, 11A0h
0x180007146  pop     r15
0x180007148  pop     r14
0x18000714a  pop     r13
0x18000714c  pop     r12
0x18000714e  pop     rdi
0x18000714f  pop     rsi
0x180007150  pop     rbp
0x180007151  retn
0x180007152  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
