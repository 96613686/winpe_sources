# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180008ed8`
- end: `0x1800092b2`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `986`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180008408`

## callees

- `0x180007c48`
- `0x180008318`
- `0x180008ed8`
- `0x180009938`
- `0x18000b3b8`
- `0x18000e560`
- `0x18000f5f0`
- `0x18000f680`
- `0x180011010`

## import_xrefs

- `KERNEL32!GetProcessHeap` at `0x180009235`
- `KERNEL32!GetProcessHeap` at `0x18000926d`
- `KERNEL32!GetProcessHeap` at `0x180009235`
- `KERNEL32!GetProcessHeap` at `0x18000926d`
- `KERNEL32!HeapFree` at `0x180009243`
- `KERNEL32!HeapFree` at `0x18000927b`
- `KERNEL32!HeapFree` at `0x180009243`
- `KERNEL32!HeapFree` at `0x18000927b`
- `KERNEL32!GetModuleHandleW` at `0x180008fb7`
- `KERNEL32!GetModuleHandleW` at `0x180008fb7`
- `KERNEL32!GetProcAddress` at `0x180008fce`
- `KERNEL32!GetProcAddress` at `0x180008fce`

## string_xrefs

- `0x180008fb0`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
void __fastcall wil::details_abi::RecordWnfUsageIndex(
        wil::details_abi *this,
        const struct __WIL__WNF_STATE_NAME *a2,
        __int64 a3,
        const struct wil::details_abi::RawUsageIndex *a4)
{
  wil::details_abi *v5; // r14
  wil::details_abi *v6; // r12
  unsigned __int64 v7; // r15
  char v8; // cl
  unsigned int v9; // edx
  __int64 v10; // rax
  FARPROC ProcAddress; // rax
  HMODULE ModuleHandleW; // rax
  int v13; // edx
  unsigned int v14; // edi
  unsigned int v15; // eax
  int v16; // edi
  __int64 v17; // r9
  char v18; // di
  int updated; // eax
  __int64 v20; // r9
  void *v21; // rsi
  HANDLE ProcessHeap; // rax
  void *v23; // rbx
  HANDLE v24; // rax
  __int64 *v25; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v26; // [rsp+40h] [rbp-C0h] BYREF
  int v27[6]; // [rsp+48h] [rbp-B8h] BYREF
  _WORD v28[2]; // [rsp+60h] [rbp-A0h] BYREF
  char v29; // [rsp+64h] [rbp-9Ch]
  __int16 v30; // [rsp+66h] [rbp-9Ah]
  char v31; // [rsp+68h] [rbp-98h]
  __int64 v32; // [rsp+70h] [rbp-90h]
  __int64 v33; // [rsp+78h] [rbp-88h]
  __int128 v34; // [rsp+80h] [rbp-80h]
  LPVOID lpMem; // [rsp+90h] [rbp-70h]
  __int16 v36; // [rsp+98h] [rbp-68h]
  char v37; // [rsp+9Ah] [rbp-66h]
  __int64 v38; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v39; // [rsp+A8h] [rbp-58h] BYREF
  __int16 v40; // [rsp+B0h] [rbp-50h] BYREF
  char v41; // [rsp+B2h] [rbp-4Eh]
  unsigned int v42; // [rsp+B4h] [rbp-4Ch]
  unsigned __int16 v43; // [rsp+B8h] [rbp-48h]
  __int128 v44; // [rsp+C0h] [rbp-40h]
  __int16 v45; // [rsp+D0h] [rbp-30h] BYREF
  char v46; // [rsp+D2h] [rbp-2Eh]
  int v47; // [rsp+D4h] [rbp-2Ch]
  unsigned __int16 v48; // [rsp+D8h] [rbp-28h]
  __int128 v49; // [rsp+E0h] [rbp-20h]
  __int64 v50; // [rsp+F0h] [rbp-10h] BYREF
  __int64 v51; // [rsp+F8h] [rbp-8h] BYREF
  __int64 v52; // [rsp+100h] [rbp+0h] BYREF
  _QWORD v53[2]; // [rsp+108h] [rbp+8h] BYREF
  char v54; // [rsp+118h] [rbp+18h] BYREF
  _QWORD v55[13]; // [rsp+120h] [rbp+20h] BYREF
  wil::details::in1diag3 *v56; // [rsp+188h] [rbp+88h]
  _BYTE v57[4096]; // [rsp+190h] [rbp+90h] BYREF

  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v39 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v28[0] = *(_WORD *)a3;
    v28[1] = *(_WORD *)(a3 + 2);
    v29 = *(_BYTE *)(a3 + 4);
    v30 = v9;
    v31 = v8;
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
      v32 = v10;
    }
    else
    {
      v32 = 0;
    }
    v33 = 0;
    v34 = 0;
    lpMem = 0;
    v36 = 0;
    v37 = 0;
    v27[0] = 0;
    LODWORD(v26) = 4096;
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
      v25 = (__int64 *)v57;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v27);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v26) = 0;
      v27[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v26;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v28, v57, v15, 0x1000u);
    if ( HIBYTE(v36) )
      break;
    v38 = 0;
    v55[0] = &wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,unsigned int)>::`vftable';
    v55[1] = &v38;
    v55[2] = &v39;
    v55[3] = v28;
    v56 = (wil::details::in1diag3 *)v55;
    v53[1] = &v54;
    v26 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v40 = *(_WORD *)(a3 + 2);
    v41 = *(_BYTE *)(a3 + 4);
    v42 = 0;
    v43 = 0;
    v44 = 0;
    v45 = *(_WORD *)(a3 + 6);
    v46 = *(_BYTE *)(a3 + 8);
    v47 = 0;
    v48 = 0;
    v49 = 0;
LABEL_25:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v40,
              &v26,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      if ( v42 )
      {
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v45,
                  &v26,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v27[2] = v47;
          v50 = v48;
          v51 = *((_QWORD *)&v49 + 1);
          v52 = v43;
          v53[0] = *((_QWORD *)&v44 + 1);
          if ( !v56 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v25 = &v50;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v56 + 32LL))(
                  v56,
                  v53,
                  &v52,
                  &v51) )
          {
            if ( v56 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
            v18 = 0;
            goto LABEL_29;
          }
          if ( ++v16 >= v42 )
            goto LABEL_25;
        }
      }
    }
    if ( v56 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v56 + 24LL))(v56);
    v18 = 1;
LABEL_29:
    if ( !(_BYTE)v36 )
      goto LABEL_37;
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v33, (int)v34 - (int)v33, v17, (int)v25, v27[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v33, v34 - v33, v20, (int)v25, 0, 0);
LABEL_37:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v39 = v38;
      goto LABEL_38;
    }
    ++v7;
    v18 = 0;
LABEL_38:
    v21 = lpMem;
    lpMem = 0;
    if ( v21 )
    {
      ProcessHeap = GetProcessHeap();
      HeapFree(ProcessHeap, 0, v21);
    }
    if ( v18 || v5 >= v6 || v7 >= 0x32 )
      return;
  }
  v23 = lpMem;
  lpMem = 0;
  if ( v23 )
  {
    v24 = GetProcessHeap();
    HeapFree(v24, 0, v23);
  }
}

```

## disassembly

```asm
0x180008ed8  mov     [rsp-8+arg_8], rbx
0x180008edd  push    rbp
0x180008ede  push    rsi
0x180008edf  push    rdi
0x180008ee0  push    r12
0x180008ee2  push    r13
0x180008ee4  push    r14
0x180008ee6  push    r15
0x180008ee8  lea     rbp, [rsp-10A0h]
0x180008ef0  mov     eax, 11A0h
0x180008ef5  call    _alloca_probe
0x180008efa  sub     rsp, rax
0x180008efd  mov     rax, cs:__security_cookie
0x180008f04  xor     rax, rsp
0x180008f07  mov     [rbp+10D0h+var_40], rax
0x180008f0e  mov     rbx, r8
0x180008f11  mov     r14, rcx
0x180008f14  lea     r12, [rcx+rdx*8]
0x180008f18  xor     r13d, r13d
0x180008f1b  mov     r15d, r13d
0x180008f1e  mov     [rbp+10D0h+var_1128], r13
0x180008f22  mov     cl, [rbx+8]
0x180008f25  movzx   edx, word ptr [rbx+6]
0x180008f29  movzx   eax, word ptr [rbx]
0x180008f2c  mov     [rsp+11D0h+var_1170], ax
0x180008f31  movzx   eax, word ptr [rbx+2]
0x180008f35  mov     [rsp+11D0h+var_116E], ax
0x180008f3a  mov     al, [rbx+4]
0x180008f3d  mov     [rsp+11D0h+var_116C], al
0x180008f41  mov     [rsp+11D0h+var_116A], dx
0x180008f46  mov     [rsp+11D0h+var_1168], cl
0x180008f4a  test    dx, dx
0x180008f4d  jz      short loc_180008F6C
0x180008f4f  mov     eax, edx
0x180008f51  cmp     cl, 1
0x180008f54  jnz     short loc_180008F5C
0x180008f56  add     rax, 2
0x180008f5a  jmp     short loc_180008F65
0x180008f5c  cmp     cl, 2
0x180008f5f  jnz     short loc_180008F65
0x180008f61  add     rax, 4
0x180008f65  mov     [rsp+11D0h+var_1160], rax
0x180008f6a  jmp     short loc_180008F71
0x180008f6c  mov     [rsp+11D0h+var_1160], r13
0x180008f71  mov     [rsp+11D0h+var_1158], r13
0x180008f76  xorps   xmm0, xmm0
0x180008f79  movdqa  [rbp+10D0h+var_1150], xmm0
0x180008f7e  mov     [rbp+10D0h+lpMem], r13
0x180008f82  mov     [rbp+10D0h+var_1138], r13w
0x180008f87  mov     [rbp+10D0h+var_1136], r13b
0x180008f8b  mov     [rsp+11D0h+var_1188], r13d
0x180008f90  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180008f98  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008f9f  test    rax, rax
0x180008fa2  jnz     short loc_180008FE8
0x180008fa4  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008fab  test    rax, rax
0x180008fae  jnz     short loc_180008FC4
0x180008fb0  lea     rcx, ModuleName; "ntdll.dll"
0x180008fb7  call    cs:__imp_GetModuleHandleW
0x180008fbd  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008fc4  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008fcb  mov     rcx, rax; hModule
0x180008fce  call    cs:__imp_GetProcAddress
0x180008fd4  nop
0x180008fd5  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008fdc  test    rax, rax
0x180008fdf  jnz     short loc_180008FE8
0x180008fe1  mov     edi, 0C0000139h
0x180008fe6  jmp     short loc_180009012
0x180008fe8  lea     rcx, [rsp+11D0h+var_1190]
0x180008fed  mov     [rsp+11D0h+var_11A8], rcx
0x180008ff2  lea     rcx, [rbp+10D0h+var_1040]
0x180008ff9  mov     [rsp+11D0h+var_11B0], rcx
0x180008ffe  lea     r9, [rsp+11D0h+var_1188]
0x180009003  xor     r8d, r8d
0x180009006  xor     edx, edx
0x180009008  mov     rcx, r14
0x18000900b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009010  mov     edi, eax
0x180009012  mov     ecx, edi; this
0x180009014  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180009019  test    edi, edi
0x18000901b  jz      short loc_18000902B
0x18000901d  mov     eax, r13d
0x180009020  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180009024  mov     [rsp+11D0h+var_1188], r13d
0x180009029  jmp     short loc_18000902F
0x18000902b  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x18000902f  mov     r8d, eax; unsigned __int64
0x180009032  mov     r9d, 1000h; unsigned __int64
0x180009038  lea     rdx, [rbp+10D0h+var_1040]; void *
0x18000903f  lea     rcx, [rsp+11D0h+var_1170]; this
0x180009044  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180009049  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x18000904d  jnz     loc_180009260
0x180009053  mov     [rbp+10D0h+var_1130], r13
0x180009057  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x18000905e  mov     [rbp+10D0h+var_10B0], rax
0x180009062  lea     rax, [rbp+10D0h+var_1130]
0x180009066  mov     [rbp+10D0h+var_10A8], rax
0x18000906a  lea     rax, [rbp+10D0h+var_1128]
0x18000906e  mov     [rbp+10D0h+var_10A0], rax
0x180009072  lea     rax, [rsp+11D0h+var_1170]
0x180009077  mov     [rbp+10D0h+var_1098], rax
0x18000907b  lea     rax, [rbp+10D0h+var_10B0]
0x18000907f  mov     [rbp+10D0h+var_1048], rax
0x180009086  lea     rax, [rbp+10D0h+var_10B8]
0x18000908a  mov     [rbp+10D0h+var_10C0], rax
0x18000908e  mov     rax, [rbx+18h]
0x180009092  add     rax, 0Ah
0x180009096  mov     [rsp+11D0h+var_1190], rax
0x18000909b  movzx   eax, word ptr [rbx+2]
0x18000909f  mov     [rbp+10D0h+var_1120], ax
0x1800090a3  mov     al, [rbx+4]
0x1800090a6  mov     [rbp+10D0h+var_111E], al
0x1800090a9  mov     [rbp+10D0h+var_111C], r13d
0x1800090ad  mov     [rbp+10D0h+var_1118], r13w
0x1800090b2  xorps   xmm0, xmm0
0x1800090b5  movdqu  [rbp+10D0h+var_1110], xmm0
0x1800090ba  movzx   eax, word ptr [rbx+6]
0x1800090be  mov     [rbp+10D0h+var_1100], ax
0x1800090c2  mov     al, [rbx+8]
0x1800090c5  mov     [rbp+10D0h+var_10FE], al
0x1800090c8  mov     [rbp+10D0h+var_10FC], r13d
0x1800090cc  mov     [rbp+10D0h+var_10F8], r13w
0x1800090d1  movdqu  [rbp+10D0h+var_10F0], xmm0
0x1800090d6  jmp     loc_18000916F
0x1800090db  mov     edi, r13d
0x1800090de  cmp     [rbp+10D0h+var_111C], r13d
0x1800090e2  jbe     loc_18000916F
0x1800090e8  mov     r8, [rbx+20h]; unsigned __int8 *
0x1800090ec  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x1800090f1  lea     rcx, [rbp+10D0h+var_1100]; this
0x1800090f5  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x1800090fa  test    al, al
0x1800090fc  jz      short loc_18000916F
0x1800090fe  mov     eax, [rbp+10D0h+var_10FC]
0x180009101  mov     [rsp+11D0h+var_1180], eax
0x180009105  movzx   eax, [rbp+10D0h+var_10F8]
0x180009109  mov     [rbp+10D0h+var_10E0], rax
0x18000910d  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180009111  mov     [rbp+10D0h+var_10D8], rax
0x180009115  movzx   eax, [rbp+10D0h+var_1118]
0x180009119  mov     [rbp+10D0h+var_10D0], rax
0x18000911d  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x180009121  mov     [rbp+10D0h+var_10C8], rax
0x180009125  mov     rcx, [rbp+10D0h+var_1048]; this
0x18000912c  test    rcx, rcx
0x18000912f  jz      loc_1800092AC
0x180009135  mov     rax, [rcx]
0x180009138  lea     rdx, [rsp+11D0h+var_1180]
0x18000913d  mov     [rsp+11D0h+var_11A8], rdx
0x180009142  lea     rdx, [rbp+10D0h+var_10E0]
0x180009146  mov     [rsp+11D0h+var_11B0], rdx
0x18000914b  lea     r9, [rbp+10D0h+var_10D8]
0x18000914f  lea     r8, [rbp+10D0h+var_10D0]
0x180009153  lea     rdx, [rbp+10D0h+var_10C8]
0x180009157  mov     rax, [rax+20h]
0x18000915b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009160  test    al, al
0x180009162  jz      short loc_1800091DD
0x180009164  inc     edi
0x180009166  cmp     edi, [rbp+10D0h+var_111C]
0x180009169  jb      loc_1800090E8
0x18000916f  mov     r8, [rbx+20h]; unsigned __int8 *
0x180009173  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180009178  lea     rcx, [rbp+10D0h+var_1120]; this
0x18000917c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009181  test    al, al
0x180009183  jnz     loc_1800090DB
0x180009189  mov     rcx, [rbp+10D0h+var_1048]
0x180009190  test    rcx, rcx
0x180009193  jz      short loc_1800091A1
0x180009195  mov     rax, [rcx]
0x180009198  mov     rax, [rax+18h]
0x18000919c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091a1  mov     dil, 1
0x1800091a4  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x1800091a8  jz      short loc_18000921C
0x1800091aa  mov     eax, [rsp+11D0h+var_1188]
0x1800091ae  mov     rdx, [rsp+11D0h+var_1158]
0x1800091b3  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x1800091b7  sub     r8d, edx
0x1800091ba  mov     [rsp+11D0h+var_11A0], 1
0x1800091c2  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x1800091c6  mov     rcx, r14
0x1800091c9  call    wil_details_NtUpdateWnfStateData
0x1800091ce  cmp     eax, 0C0000001h
0x1800091d3  jnz     short loc_1800091FA
0x1800091d5  inc     r15
0x1800091d8  mov     dil, r13b
0x1800091db  jmp     short loc_180009228
0x1800091dd  mov     rcx, [rbp+10D0h+var_1048]
0x1800091e4  test    rcx, rcx
0x1800091e7  jz      short loc_1800091F5
0x1800091e9  mov     rax, [rcx]
0x1800091ec  mov     rax, [rax+18h]
0x1800091f0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800091f5  mov     dil, r13b
0x1800091f8  jmp     short loc_1800091A4
0x1800091fa  test    eax, eax
0x1800091fc  jz      short loc_18000921C
0x1800091fe  mov     rdx, [rsp+11D0h+var_1158]
0x180009203  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009207  sub     r8d, edx
0x18000920a  mov     [rsp+11D0h+var_11A0], r13d
0x18000920f  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x180009214  mov     rcx, r14
0x180009217  call    wil_details_NtUpdateWnfStateData
0x18000921c  add     r14, 8
0x180009220  mov     rax, [rbp+10D0h+var_1130]
0x180009224  mov     [rbp+10D0h+var_1128], rax
0x180009228  mov     rsi, [rbp+10D0h+lpMem]
0x18000922c  mov     [rbp+10D0h+lpMem], r13
0x180009230  test    rsi, rsi
0x180009233  jz      short loc_18000924A
0x180009235  call    cs:__imp_GetProcessHeap
0x18000923b  mov     rcx, rax; hHeap
0x18000923e  mov     r8, rsi; lpMem
0x180009241  xor     edx, edx; dwFlags
0x180009243  call    cs:__imp_HeapFree
0x180009249  nop
0x18000924a  test    dil, dil
0x18000924d  jnz     short loc_180009282
0x18000924f  cmp     r14, r12
0x180009252  jnb     short loc_180009282
0x180009254  cmp     r15, 32h ; '2'
0x180009258  jb      loc_180008F22
0x18000925e  jmp     short loc_180009282
0x180009260  mov     rbx, [rbp+10D0h+lpMem]
0x180009264  mov     [rbp+10D0h+lpMem], r13
0x180009268  test    rbx, rbx
0x18000926b  jz      short loc_180009282
0x18000926d  call    cs:__imp_GetProcessHeap
0x180009273  mov     rcx, rax; hHeap
0x180009276  mov     r8, rbx; lpMem
0x180009279  xor     edx, edx; dwFlags
0x18000927b  call    cs:__imp_HeapFree
0x180009281  nop
0x180009282  mov     rcx, [rbp+10D0h+var_40]
0x180009289  xor     rcx, rsp; StackCookie
0x18000928c  call    __security_check_cookie
0x180009291  mov     rbx, [rsp+11D0h+arg_8]
0x180009299  add     rsp, 11A0h
0x1800092a0  pop     r15
0x1800092a2  pop     r14
0x1800092a4  pop     r13
0x1800092a6  pop     r12
0x1800092a8  pop     rdi
0x1800092a9  pop     rsi
0x1800092aa  pop     rbp
0x1800092ab  retn
0x1800092ac  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
