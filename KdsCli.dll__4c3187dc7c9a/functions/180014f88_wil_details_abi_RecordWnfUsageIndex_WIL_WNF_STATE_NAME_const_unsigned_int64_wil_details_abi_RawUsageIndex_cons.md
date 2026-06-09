# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180014f88`
- end: `0x180015355`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180014694`

## callees

- `0x180001630`
- `0x1800142f8`
- `0x1800145a8`
- `0x180014f88`
- `0x180015948`
- `0x1800165b8`
- `0x180016a80`
- `0x18001a640`
- `0x18001b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015067`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180015067`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001507e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x18001507e`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800152e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001531f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x1800152e9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18001531f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800152db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015311`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x1800152db`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180015311`

## string_xrefs

- `0x180015060`: `ntdll.dll`

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
0x180014f88  mov     [rsp-8+arg_8], rbx
0x180014f8d  push    rbp
0x180014f8e  push    rsi
0x180014f8f  push    rdi
0x180014f90  push    r12
0x180014f92  push    r13
0x180014f94  push    r14
0x180014f96  push    r15
0x180014f98  lea     rbp, [rsp-10A0h]
0x180014fa0  mov     eax, 11A0h
0x180014fa5  call    _alloca_probe
0x180014faa  sub     rsp, rax
0x180014fad  mov     rax, cs:__security_cookie
0x180014fb4  xor     rax, rsp
0x180014fb7  mov     [rbp+10D0h+var_40], rax
0x180014fbe  xor     r13d, r13d
0x180014fc1  lea     r12, [rcx+rdx*8]
0x180014fc5  mov     r15d, r13d
0x180014fc8  mov     [rbp+10D0h+var_1128], r13
0x180014fcc  mov     rdi, r8
0x180014fcf  mov     r14, rcx
0x180014fd2  movzx   eax, word ptr [rdi]
0x180014fd5  movzx   edx, word ptr [rdi+6]
0x180014fd9  mov     cl, [rdi+8]
0x180014fdc  mov     [rsp+11D0h+var_1170], ax
0x180014fe1  movzx   eax, word ptr [rdi+2]
0x180014fe5  mov     [rsp+11D0h+var_116E], ax
0x180014fea  mov     al, [rdi+4]
0x180014fed  mov     [rsp+11D0h+var_116C], al
0x180014ff1  mov     [rsp+11D0h+var_116A], dx
0x180014ff6  mov     [rsp+11D0h+var_1168], cl
0x180014ffa  test    dx, dx
0x180014ffd  jz      short loc_18001501C
0x180014fff  mov     eax, edx
0x180015001  cmp     cl, 1
0x180015004  jnz     short loc_18001500C
0x180015006  add     rax, 2
0x18001500a  jmp     short loc_180015015
0x18001500c  cmp     cl, 2
0x18001500f  jnz     short loc_180015015
0x180015011  add     rax, 4
0x180015015  mov     [rsp+11D0h+var_1160], rax
0x18001501a  jmp     short loc_180015021
0x18001501c  mov     [rsp+11D0h+var_1160], r13
0x180015021  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180015028  xorps   xmm0, xmm0
0x18001502b  mov     [rsp+11D0h+var_1158], r13
0x180015030  movdqa  [rbp+10D0h+var_1150], xmm0
0x180015035  mov     [rbp+10D0h+lpMem], r13
0x180015039  mov     [rbp+10D0h+var_1138], r13w
0x18001503e  mov     [rbp+10D0h+var_1136], r13b
0x180015042  mov     [rsp+11D0h+var_1188], r13d
0x180015047  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18001504f  test    rax, rax
0x180015052  jnz     short loc_180015097
0x180015054  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x18001505b  test    rax, rax
0x18001505e  jnz     short loc_180015074
0x180015060  lea     rcx, ModuleName; "ntdll.dll"
0x180015067  call    cs:__imp_GetModuleHandleW
0x18001506d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180015074  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x18001507b  mov     rcx, rax; hModule
0x18001507e  call    cs:__imp_GetProcAddress
0x180015084  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x18001508b  test    rax, rax
0x18001508e  jnz     short loc_180015097
0x180015090  mov     ebx, 0C0000139h
0x180015095  jmp     short loc_1800150C1
0x180015097  lea     rcx, [rsp+11D0h+var_1190]
0x18001509c  xor     r8d, r8d
0x18001509f  mov     [rsp+11D0h+var_11A8], rcx
0x1800150a4  lea     r9, [rsp+11D0h+var_1188]
0x1800150a9  lea     rcx, [rbp+10D0h+var_1040]
0x1800150b0  xor     edx, edx
0x1800150b2  mov     [rsp+11D0h+var_11B0], rcx
0x1800150b7  mov     rcx, r14
0x1800150ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800150bf  mov     ebx, eax
0x1800150c1  mov     ecx, ebx; this
0x1800150c3  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x1800150c8  test    ebx, ebx
0x1800150ca  jz      short loc_1800150DA
0x1800150cc  mov     eax, r13d
0x1800150cf  mov     [rsp+11D0h+var_1188], r13d
0x1800150d4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x1800150d8  jmp     short loc_1800150DE
0x1800150da  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x1800150de  mov     r8d, eax; unsigned __int64
0x1800150e1  lea     rdx, [rbp+10D0h+var_1040]; void *
0x1800150e8  mov     r9d, 1000h; unsigned __int64
0x1800150ee  lea     rcx, [rsp+11D0h+var_1170]; this
0x1800150f3  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x1800150f8  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x1800150fc  jnz     loc_180015304
0x180015102  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180015109  mov     [rbp+10D0h+var_1130], r13
0x18001510d  mov     [rbp+10D0h+var_10B8], rax
0x180015111  xorps   xmm0, xmm0
0x180015114  lea     rax, [rbp+10D0h+var_1130]
0x180015118  mov     [rbp+10D0h+var_111C], r13d
0x18001511c  mov     [rbp+10D0h+var_10B0], rax
0x180015120  lea     rax, [rbp+10D0h+var_1128]
0x180015124  mov     [rbp+10D0h+var_10A8], rax
0x180015128  lea     rax, [rsp+11D0h+var_1170]
0x18001512d  mov     [rbp+10D0h+var_10A0], rax
0x180015131  lea     rax, [rbp+10D0h+var_10B8]
0x180015135  mov     [rbp+10D0h+var_1050], rax
0x18001513c  mov     rax, [rdi+18h]
0x180015140  add     rax, 0Ah
0x180015144  mov     [rbp+10D0h+var_1118], r13w
0x180015149  mov     [rsp+11D0h+var_1190], rax
0x18001514e  movzx   eax, word ptr [rdi+2]
0x180015152  mov     [rbp+10D0h+var_1120], ax
0x180015156  mov     al, [rdi+4]
0x180015159  mov     [rbp+10D0h+var_111E], al
0x18001515c  movzx   eax, word ptr [rdi+6]
0x180015160  mov     [rbp+10D0h+var_1100], ax
0x180015164  mov     al, [rdi+8]
0x180015167  mov     [rbp+10D0h+var_10FE], al
0x18001516a  movdqu  [rbp+10D0h+var_1110], xmm0
0x18001516f  mov     [rbp+10D0h+var_10FC], r13d
0x180015173  mov     [rbp+10D0h+var_10F8], r13w
0x180015178  movdqu  [rbp+10D0h+var_10F0], xmm0
0x18001517d  jmp     loc_180015216
0x180015182  mov     ebx, r13d
0x180015185  cmp     [rbp+10D0h+var_111C], r13d
0x180015189  jbe     loc_180015216
0x18001518f  mov     r8, [rdi+20h]; unsigned __int8 *
0x180015193  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180015198  lea     rcx, [rbp+10D0h+var_1100]; this
0x18001519c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800151a1  test    al, al
0x1800151a3  jz      short loc_180015216
0x1800151a5  mov     eax, [rbp+10D0h+var_10FC]
0x1800151a8  mov     rcx, [rbp+10D0h+var_1050]; this
0x1800151af  mov     [rsp+11D0h+var_1180], eax
0x1800151b3  movzx   eax, [rbp+10D0h+var_10F8]
0x1800151b7  mov     [rbp+10D0h+var_10E0], rax
0x1800151bb  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x1800151bf  mov     [rbp+10D0h+var_10D8], rax
0x1800151c3  movzx   eax, [rbp+10D0h+var_1118]
0x1800151c7  mov     [rbp+10D0h+var_10D0], rax
0x1800151cb  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x1800151cf  mov     [rbp+10D0h+var_10C8], rax
0x1800151d3  test    rcx, rcx
0x1800151d6  jz      loc_18001534F
0x1800151dc  mov     rax, [rcx]
0x1800151df  lea     rdx, [rsp+11D0h+var_1180]
0x1800151e4  mov     [rsp+11D0h+var_11A8], rdx
0x1800151e9  lea     r9, [rbp+10D0h+var_10D8]
0x1800151ed  lea     rdx, [rbp+10D0h+var_10E0]
0x1800151f1  mov     [rsp+11D0h+var_11B0], rdx
0x1800151f6  lea     r8, [rbp+10D0h+var_10D0]
0x1800151fa  mov     rax, [rax+20h]
0x1800151fe  lea     rdx, [rbp+10D0h+var_10C8]
0x180015202  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015207  test    al, al
0x180015209  jz      short loc_180015283
0x18001520b  inc     ebx
0x18001520d  cmp     ebx, [rbp+10D0h+var_111C]
0x180015210  jb      loc_18001518F
0x180015216  mov     r8, [rdi+20h]; unsigned __int8 *
0x18001521a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x18001521f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180015223  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180015228  test    al, al
0x18001522a  jnz     loc_180015182
0x180015230  mov     rcx, [rbp+10D0h+var_1050]
0x180015237  test    rcx, rcx
0x18001523a  jz      short loc_180015248
0x18001523c  mov     rax, [rcx]
0x18001523f  mov     rax, [rax+18h]
0x180015243  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180015248  mov     bl, 1
0x18001524a  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x18001524e  jz      short loc_1800152C2
0x180015250  mov     rdx, [rsp+11D0h+var_1158]
0x180015255  mov     rcx, r14
0x180015258  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x18001525c  mov     eax, [rsp+11D0h+var_1188]
0x180015260  sub     r8d, edx
0x180015263  mov     [rsp+11D0h+var_11A0], 1
0x18001526b  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x18001526f  call    wil_details_NtUpdateWnfStateData
0x180015274  cmp     eax, 0C0000001h
0x180015279  jnz     short loc_1800152A0
0x18001527b  inc     r15
0x18001527e  mov     bl, r13b
0x180015281  jmp     short loc_1800152CE
0x180015283  mov     rcx, [rbp+10D0h+var_1050]
0x18001528a  test    rcx, rcx
0x18001528d  jz      short loc_18001529B
0x18001528f  mov     rax, [rcx]
0x180015292  mov     rax, [rax+18h]
0x180015296  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18001529b  mov     bl, r13b
0x18001529e  jmp     short loc_18001524A
0x1800152a0  test    eax, eax
0x1800152a2  jz      short loc_1800152C2
0x1800152a4  mov     rdx, [rsp+11D0h+var_1158]
0x1800152a9  mov     rcx, r14
0x1800152ac  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800152b0  sub     r8d, edx
0x1800152b3  mov     [rsp+11D0h+var_11A0], r13d
0x1800152b8  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x1800152bd  call    wil_details_NtUpdateWnfStateData
0x1800152c2  mov     rax, [rbp+10D0h+var_1130]
0x1800152c6  add     r14, 8
0x1800152ca  mov     [rbp+10D0h+var_1128], rax
0x1800152ce  mov     rsi, [rbp+10D0h+lpMem]
0x1800152d2  mov     [rbp+10D0h+lpMem], r13
0x1800152d6  test    rsi, rsi
0x1800152d9  jz      short loc_1800152EF
0x1800152db  call    cs:__imp_GetProcessHeap
0x1800152e1  mov     r8, rsi; lpMem
0x1800152e4  xor     edx, edx; dwFlags
0x1800152e6  mov     rcx, rax; hHeap
0x1800152e9  call    cs:__imp_HeapFree
0x1800152ef  test    bl, bl
0x1800152f1  jnz     short loc_180015325
0x1800152f3  cmp     r14, r12
0x1800152f6  jnb     short loc_180015325
0x1800152f8  cmp     r15, 32h ; '2'
0x1800152fc  jb      loc_180014FD2
0x180015302  jmp     short loc_180015325
0x180015304  mov     rbx, [rbp+10D0h+lpMem]
0x180015308  mov     [rbp+10D0h+lpMem], r13
0x18001530c  test    rbx, rbx
0x18001530f  jz      short loc_180015325
0x180015311  call    cs:__imp_GetProcessHeap
0x180015317  mov     r8, rbx; lpMem
0x18001531a  xor     edx, edx; dwFlags
0x18001531c  mov     rcx, rax; hHeap
0x18001531f  call    cs:__imp_HeapFree
0x180015325  mov     rcx, [rbp+10D0h+var_40]
0x18001532c  xor     rcx, rsp; StackCookie
0x18001532f  call    __security_check_cookie
0x180015334  mov     rbx, [rsp+11D0h+arg_8]
0x18001533c  add     rsp, 11A0h
0x180015343  pop     r15
0x180015345  pop     r14
0x180015347  pop     r13
0x180015349  pop     r12
0x18001534b  pop     rdi
0x18001534c  pop     rsi
0x18001534d  pop     rbp
0x18001534e  retn
0x18001534f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
