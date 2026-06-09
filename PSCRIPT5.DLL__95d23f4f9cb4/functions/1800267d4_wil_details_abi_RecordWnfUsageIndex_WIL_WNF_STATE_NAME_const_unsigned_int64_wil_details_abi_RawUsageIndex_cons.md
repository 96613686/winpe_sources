# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x1800267d4`
- end: `0x180026ba4`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `976`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180025ebc`

## callees

- `0x180001ee0`
- `0x180025a58`
- `0x180025dbc`
- `0x1800267d4`
- `0x1800271f8`
- `0x180027dac`
- `0x1800287dc`
- `0x18005c3b0`
- `0x18005d010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x1800268b4`
- `KERNEL32!GetModuleHandleW` at `0x1800268b4`
- `KERNEL32!GetProcessHeap` at `0x180026b2a`
- `KERNEL32!GetProcessHeap` at `0x180026b60`
- `KERNEL32!GetProcessHeap` at `0x180026b2a`
- `KERNEL32!GetProcessHeap` at `0x180026b60`
- `KERNEL32!HeapFree` at `0x180026b38`
- `KERNEL32!HeapFree` at `0x180026b6e`
- `KERNEL32!HeapFree` at `0x180026b38`
- `KERNEL32!HeapFree` at `0x180026b6e`
- `KERNEL32!GetProcAddress` at `0x1800268cb`
- `KERNEL32!GetProcAddress` at `0x1800268cb`

## string_xrefs

- `0x1800268ad`: `ntdll.dll`

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
  __int64 v20; // r9
  char v21; // bl
  int updated; // eax
  __int64 v23; // r9
  void *v24; // rsi
  HANDLE ProcessHeap; // rax
  void *v26; // rbx
  HANDLE v27; // rax
  __int64 *v28; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v29; // [rsp+40h] [rbp-C0h] BYREF
  int v30[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v7, 0, 0, v30);
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v7, v36, (int)v37 - (int)v36, v20, (int)v28, v30[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v7, v36, v37 - v36, v23, (int)v28, 0, 0);
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
0x1800267d4  mov     [rsp-8+arg_8], rbx
0x1800267d9  push    rbp
0x1800267da  push    rsi
0x1800267db  push    rdi
0x1800267dc  push    r12
0x1800267de  push    r13
0x1800267e0  push    r14
0x1800267e2  push    r15
0x1800267e4  lea     rbp, [rsp-10A0h]
0x1800267ec  mov     eax, 11A0h
0x1800267f1  call    _alloca_probe
0x1800267f6  sub     rsp, rax
0x1800267f9  mov     rax, cs:__security_cookie
0x180026800  xor     rax, rsp
0x180026803  mov     [rbp+10D0h+var_40], rax
0x18002680a  xor     r15d, r15d
0x18002680d  lea     r13, [rcx+rdx*8]
0x180026811  mov     r12d, r15d
0x180026814  mov     [rbp+10D0h+var_1128], r15
0x180026818  mov     rdi, r8
0x18002681b  mov     r14, rcx
0x18002681e  movzx   eax, word ptr [rdi]
0x180026821  movzx   edx, word ptr [rdi+6]
0x180026825  mov     cl, [rdi+8]
0x180026828  mov     [rsp+11D0h+var_1170], ax
0x18002682d  movzx   eax, word ptr [rdi+2]
0x180026831  mov     [rsp+11D0h+var_116E], ax
0x180026836  mov     al, [rdi+4]
0x180026839  mov     [rsp+11D0h+var_116C], al
0x18002683d  mov     [rsp+11D0h+var_116A], dx
0x180026842  mov     [rsp+11D0h+var_1168], cl
0x180026846  test    dx, dx
0x180026849  jz      short loc_180026868
0x18002684b  mov     eax, edx
0x18002684d  cmp     cl, 1
0x180026850  jnz     short loc_180026858
0x180026852  add     rax, 2
0x180026856  jmp     short loc_180026861
0x180026858  cmp     cl, 2
0x18002685b  jnz     short loc_180026861
0x18002685d  add     rax, 4
0x180026861  mov     [rsp+11D0h+var_1160], rax
0x180026866  jmp     short loc_18002686D
0x180026868  mov     [rsp+11D0h+var_1160], r15
0x18002686d  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180026874  xorps   xmm0, xmm0
0x180026877  mov     [rsp+11D0h+var_1158], r15
0x18002687c  movdqa  [rbp+10D0h+var_1150], xmm0
0x180026881  mov     [rbp+10D0h+lpMem], r15
0x180026885  mov     [rbp+10D0h+var_1138], 0
0x18002688b  mov     [rbp+10D0h+var_1136], r15b
0x18002688f  mov     [rsp+11D0h+var_1188], r15d
0x180026894  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x18002689c  test    rax, rax
0x18002689f  jnz     short loc_1800268E4
0x1800268a1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800268a8  test    rax, rax
0x1800268ab  jnz     short loc_1800268C1
0x1800268ad  lea     rcx, aNtdllDll; "ntdll.dll"
0x1800268b4  call    cs:__imp_GetModuleHandleW
0x1800268ba  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800268c1  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x1800268c8  mov     rcx, rax; hModule
0x1800268cb  call    cs:__imp_GetProcAddress
0x1800268d1  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x1800268d8  test    rax, rax
0x1800268db  jnz     short loc_1800268E4
0x1800268dd  mov     ebx, 0C0000139h
0x1800268e2  jmp     short loc_18002690E
0x1800268e4  lea     rcx, [rsp+11D0h+var_1190]
0x1800268e9  xor     r8d, r8d
0x1800268ec  mov     [rsp+11D0h+var_11A8], rcx
0x1800268f1  lea     r9, [rsp+11D0h+var_1188]
0x1800268f6  lea     rcx, [rbp+10D0h+var_1040]
0x1800268fd  xor     edx, edx
0x1800268ff  mov     [rsp+11D0h+var_11B0], rcx
0x180026904  mov     rcx, r14
0x180026907  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002690c  mov     ebx, eax
0x18002690e  mov     ecx, ebx; this
0x180026910  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180026915  test    ebx, ebx
0x180026917  jz      short loc_180026927
0x180026919  mov     eax, r15d
0x18002691c  mov     [rsp+11D0h+var_1188], r15d
0x180026921  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180026925  jmp     short loc_18002692B
0x180026927  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18002692b  mov     r8d, eax; unsigned __int64
0x18002692e  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180026935  mov     r9d, 1000h; unsigned __int64
0x18002693b  lea     rcx, [rsp+11D0h+var_1170]; this
0x180026940  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180026945  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180026949  jnz     loc_180026B53
0x18002694f  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180026956  mov     [rbp+10D0h+var_1130], r15
0x18002695a  mov     [rbp+10D0h+var_10B8], rax
0x18002695e  xorps   xmm0, xmm0
0x180026961  lea     rax, [rbp+10D0h+var_1130]
0x180026965  mov     [rbp+10D0h+var_111C], r15d
0x180026969  mov     [rbp+10D0h+var_10B0], rax
0x18002696d  lea     rax, [rbp+10D0h+var_1128]
0x180026971  mov     [rbp+10D0h+var_10A8], rax
0x180026975  lea     rax, [rsp+11D0h+var_1170]
0x18002697a  mov     [rbp+10D0h+var_10A0], rax
0x18002697e  lea     rax, [rbp+10D0h+var_10B8]
0x180026982  mov     [rbp+10D0h+var_1050], rax
0x180026989  mov     rax, [rdi+18h]
0x18002698d  add     rax, 0Ah
0x180026991  mov     [rbp+10D0h+var_1118], r15w
0x180026996  mov     [rsp+11D0h+var_1190], rax
0x18002699b  movzx   eax, word ptr [rdi+2]
0x18002699f  mov     [rbp+10D0h+var_1120], ax
0x1800269a3  mov     al, [rdi+4]
0x1800269a6  mov     [rbp+10D0h+var_111E], al
0x1800269a9  movzx   eax, word ptr [rdi+6]
0x1800269ad  mov     [rbp+10D0h+var_1100], ax
0x1800269b1  mov     al, [rdi+8]
0x1800269b4  mov     [rbp+10D0h+var_10FE], al
0x1800269b7  movdqu  [rbp+10D0h+var_1110], xmm0
0x1800269bc  mov     [rbp+10D0h+var_10FC], r15d
0x1800269c0  mov     [rbp+10D0h+var_10F8], r15w
0x1800269c5  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800269ca  jmp     loc_180026A62
0x1800269cf  mov     esi, [rbp+10D0h+var_111C]
0x1800269d2  mov     ebx, r15d
0x1800269d5  test    esi, esi
0x1800269d7  jz      loc_180026A62
0x1800269dd  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x1800269e1  mov     r8, [rdi+20h]; unsigned __int8 *
0x1800269e5  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800269ea  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800269ee  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800269f3  test    al, al
0x1800269f5  jz      short loc_180026A5F
0x1800269f7  mov     eax, [rbp+10D0h+var_10FC]
0x1800269fa  mov     rcx, [rbp+10D0h+var_1050]; this
0x180026a01  mov     [rsp+11D0h+var_1180], eax
0x180026a05  movzx   eax, [rbp+10D0h+var_10F8]
0x180026a09  mov     [rbp+10D0h+var_10E0], rax
0x180026a0d  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180026a11  mov     [rbp+10D0h+var_10D8], rax
0x180026a15  movzx   eax, [rbp+10D0h+var_1118]
0x180026a19  mov     [rbp+10D0h+var_10D0], rax
0x180026a1d  mov     [rbp+10D0h+var_10C8], r15
0x180026a21  test    rcx, rcx
0x180026a24  jz      loc_180026B9E
0x180026a2a  mov     rax, [rcx]
0x180026a2d  lea     rdx, [rsp+11D0h+var_1180]
0x180026a32  mov     [rsp+11D0h+var_11A8], rdx
0x180026a37  lea     r9, [rbp+10D0h+var_10D8]
0x180026a3b  lea     rdx, [rbp+10D0h+var_10E0]
0x180026a3f  mov     [rsp+11D0h+var_11B0], rdx
0x180026a44  lea     r8, [rbp+10D0h+var_10D0]
0x180026a48  mov     rax, [rax+20h]
0x180026a4c  lea     rdx, [rbp+10D0h+var_10C8]
0x180026a50  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a55  test    al, al
0x180026a57  jz      short loc_180026ACF
0x180026a59  inc     ebx
0x180026a5b  cmp     ebx, esi
0x180026a5d  jb      short loc_1800269E1
0x180026a5f  xor     r15d, r15d
0x180026a62  mov     r8, [rdi+20h]; unsigned __int8 *
0x180026a66  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180026a6b  lea     rcx, [rbp+10D0h+var_1120]; this
0x180026a6f  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180026a74  test    al, al
0x180026a76  jnz     loc_1800269CF
0x180026a7c  mov     rcx, [rbp+10D0h+var_1050]
0x180026a83  test    rcx, rcx
0x180026a86  jz      short loc_180026A94
0x180026a88  mov     rax, [rcx]
0x180026a8b  mov     rax, [rax+18h]
0x180026a8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026a94  mov     bl, 1
0x180026a96  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180026a9a  jz      short loc_180026B11
0x180026a9c  mov     rdx, [rsp+11D0h+var_1158]
0x180026aa1  mov     rcx, r14
0x180026aa4  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180026aa8  mov     eax, [rsp+11D0h+var_1188]
0x180026aac  sub     r8d, edx
0x180026aaf  mov     [rsp+11D0h+var_11A0], 1
0x180026ab7  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180026abb  call    wil_details_NtUpdateWnfStateData
0x180026ac0  cmp     eax, 0C0000001h
0x180026ac5  jnz     short loc_180026AEF
0x180026ac7  inc     r12
0x180026aca  mov     bl, r15b
0x180026acd  jmp     short loc_180026B1D
0x180026acf  mov     rcx, [rbp+10D0h+var_1050]
0x180026ad6  xor     r15d, r15d
0x180026ad9  test    rcx, rcx
0x180026adc  jz      short loc_180026AEA
0x180026ade  mov     rax, [rcx]
0x180026ae1  mov     rax, [rax+18h]
0x180026ae5  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180026aea  mov     bl, r15b
0x180026aed  jmp     short loc_180026A96
0x180026aef  test    eax, eax
0x180026af1  jz      short loc_180026B11
0x180026af3  mov     rdx, [rsp+11D0h+var_1158]
0x180026af8  mov     rcx, r14
0x180026afb  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180026aff  sub     r8d, edx
0x180026b02  mov     [rsp+11D0h+var_11A0], r15d
0x180026b07  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180026b0c  call    wil_details_NtUpdateWnfStateData
0x180026b11  mov     rax, [rbp+10D0h+var_1130]
0x180026b15  add     r14, 8
0x180026b19  mov     [rbp+10D0h+var_1128], rax
0x180026b1d  mov     rsi, [rbp+10D0h+lpMem]
0x180026b21  mov     [rbp+10D0h+lpMem], r15
0x180026b25  test    rsi, rsi
0x180026b28  jz      short loc_180026B3E
0x180026b2a  call    cs:__imp_GetProcessHeap
0x180026b30  mov     r8, rsi; lpMem
0x180026b33  xor     edx, edx; dwFlags
0x180026b35  mov     rcx, rax; hHeap
0x180026b38  call    cs:__imp_HeapFree
0x180026b3e  test    bl, bl
0x180026b40  jnz     short loc_180026B74
0x180026b42  cmp     r14, r13
0x180026b45  jnb     short loc_180026B74
0x180026b47  cmp     r12, 32h ; '2'
0x180026b4b  jb      loc_18002681E
0x180026b51  jmp     short loc_180026B74
0x180026b53  mov     rbx, [rbp+10D0h+lpMem]
0x180026b57  mov     [rbp+10D0h+lpMem], r15
0x180026b5b  test    rbx, rbx
0x180026b5e  jz      short loc_180026B74
0x180026b60  call    cs:__imp_GetProcessHeap
0x180026b66  mov     r8, rbx; lpMem
0x180026b69  xor     edx, edx; dwFlags
0x180026b6b  mov     rcx, rax; hHeap
0x180026b6e  call    cs:__imp_HeapFree
0x180026b74  mov     rcx, [rbp+10D0h+var_40]
0x180026b7b  xor     rcx, rsp; StackCookie
0x180026b7e  call    __security_check_cookie
0x180026b83  mov     rbx, [rsp+11D0h+arg_8]
0x180026b8b  add     rsp, 11A0h
0x180026b92  pop     r15
0x180026b94  pop     r14
0x180026b96  pop     r13
0x180026b98  pop     r12
0x180026b9a  pop     rdi
0x180026b9b  pop     rsi
0x180026b9c  pop     rbp
0x180026b9d  retn
0x180026b9e  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
