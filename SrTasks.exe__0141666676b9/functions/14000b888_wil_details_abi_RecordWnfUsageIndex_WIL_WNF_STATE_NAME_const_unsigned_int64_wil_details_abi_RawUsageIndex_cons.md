# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x14000b888`
- end: `0x14000bc55`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14000afc8`

## callees

- `0x14000ac28`
- `0x14000aed8`
- `0x14000b888`
- `0x14000c24c`
- `0x14000cdac`
- `0x14000d07c`
- `0x140010980`
- `0x140010a10`
- `0x140011010`

## import_xrefs

- `KERNEL32!GetModuleHandleW` at `0x14000b967`
- `KERNEL32!GetModuleHandleW` at `0x14000b967`
- `KERNEL32!HeapFree` at `0x14000bbe9`
- `KERNEL32!HeapFree` at `0x14000bc1f`
- `KERNEL32!HeapFree` at `0x14000bbe9`
- `KERNEL32!HeapFree` at `0x14000bc1f`
- `KERNEL32!GetProcessHeap` at `0x14000bbdb`
- `KERNEL32!GetProcessHeap` at `0x14000bc11`
- `KERNEL32!GetProcessHeap` at `0x14000bbdb`
- `KERNEL32!GetProcessHeap` at `0x14000bc11`
- `KERNEL32!GetProcAddress` at `0x14000b97e`
- `KERNEL32!GetProcAddress` at `0x14000b97e`

## string_xrefs

- `0x14000b960`: `ntdll.dll`

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
0x14000b888  mov     [rsp-8+arg_8], rbx
0x14000b88d  push    rbp
0x14000b88e  push    rsi
0x14000b88f  push    rdi
0x14000b890  push    r12
0x14000b892  push    r13
0x14000b894  push    r14
0x14000b896  push    r15
0x14000b898  lea     rbp, [rsp-10A0h]
0x14000b8a0  mov     eax, 11A0h
0x14000b8a5  call    _alloca_probe
0x14000b8aa  sub     rsp, rax
0x14000b8ad  mov     rax, cs:__security_cookie
0x14000b8b4  xor     rax, rsp
0x14000b8b7  mov     [rbp+10D0h+var_40], rax
0x14000b8be  xor     r13d, r13d
0x14000b8c1  lea     r12, [rcx+rdx*8]
0x14000b8c5  mov     r15d, r13d
0x14000b8c8  mov     [rbp+10D0h+var_1128], r13
0x14000b8cc  mov     rdi, r8
0x14000b8cf  mov     r14, rcx
0x14000b8d2  movzx   eax, word ptr [rdi]
0x14000b8d5  movzx   edx, word ptr [rdi+6]
0x14000b8d9  mov     cl, [rdi+8]
0x14000b8dc  mov     [rsp+11D0h+var_1170], ax
0x14000b8e1  movzx   eax, word ptr [rdi+2]
0x14000b8e5  mov     [rsp+11D0h+var_116E], ax
0x14000b8ea  mov     al, [rdi+4]
0x14000b8ed  mov     [rsp+11D0h+var_116C], al
0x14000b8f1  mov     [rsp+11D0h+var_116A], dx
0x14000b8f6  mov     [rsp+11D0h+var_1168], cl
0x14000b8fa  test    dx, dx
0x14000b8fd  jz      short loc_14000B91C
0x14000b8ff  mov     eax, edx
0x14000b901  cmp     cl, 1
0x14000b904  jnz     short loc_14000B90C
0x14000b906  add     rax, 2
0x14000b90a  jmp     short loc_14000B915
0x14000b90c  cmp     cl, 2
0x14000b90f  jnz     short loc_14000B915
0x14000b911  add     rax, 4
0x14000b915  mov     [rsp+11D0h+var_1160], rax
0x14000b91a  jmp     short loc_14000B921
0x14000b91c  mov     [rsp+11D0h+var_1160], r13
0x14000b921  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000b928  xorps   xmm0, xmm0
0x14000b92b  mov     [rsp+11D0h+var_1158], r13
0x14000b930  movdqa  [rbp+10D0h+var_1150], xmm0
0x14000b935  mov     [rbp+10D0h+lpMem], r13
0x14000b939  mov     [rbp+10D0h+var_1138], r13w
0x14000b93e  mov     [rbp+10D0h+var_1136], r13b
0x14000b942  mov     [rsp+11D0h+var_1188], r13d
0x14000b947  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14000b94f  test    rax, rax
0x14000b952  jnz     short loc_14000B997
0x14000b954  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b95b  test    rax, rax
0x14000b95e  jnz     short loc_14000B974
0x14000b960  lea     rcx, ModuleName; "ntdll.dll"
0x14000b967  call    cs:__imp_GetModuleHandleW
0x14000b96d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b974  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000b97b  mov     rcx, rax; hModule
0x14000b97e  call    cs:__imp_GetProcAddress
0x14000b984  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000b98b  test    rax, rax
0x14000b98e  jnz     short loc_14000B997
0x14000b990  mov     ebx, 0C0000139h
0x14000b995  jmp     short loc_14000B9C1
0x14000b997  lea     rcx, [rsp+11D0h+var_1190]
0x14000b99c  xor     r8d, r8d
0x14000b99f  mov     [rsp+11D0h+var_11A8], rcx
0x14000b9a4  lea     r9, [rsp+11D0h+var_1188]
0x14000b9a9  lea     rcx, [rbp+10D0h+var_1040]
0x14000b9b0  xor     edx, edx
0x14000b9b2  mov     [rsp+11D0h+var_11B0], rcx
0x14000b9b7  mov     rcx, r14
0x14000b9ba  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b9bf  mov     ebx, eax
0x14000b9c1  mov     ecx, ebx; this
0x14000b9c3  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000b9c8  test    ebx, ebx
0x14000b9ca  jz      short loc_14000B9DA
0x14000b9cc  mov     eax, r13d
0x14000b9cf  mov     [rsp+11D0h+var_1188], r13d
0x14000b9d4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x14000b9d8  jmp     short loc_14000B9DE
0x14000b9da  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x14000b9de  mov     r8d, eax; unsigned __int64
0x14000b9e1  lea     rdx, [rbp+10D0h+var_1040]; void *
0x14000b9e8  mov     r9d, 1000h; unsigned __int64
0x14000b9ee  lea     rcx, [rsp+11D0h+var_1170]; this
0x14000b9f3  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x14000b9f8  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x14000b9fc  jnz     loc_14000BC04
0x14000ba02  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x14000ba09  mov     [rbp+10D0h+var_1130], r13
0x14000ba0d  mov     [rbp+10D0h+var_10B8], rax
0x14000ba11  xorps   xmm0, xmm0
0x14000ba14  lea     rax, [rbp+10D0h+var_1130]
0x14000ba18  mov     [rbp+10D0h+var_111C], r13d
0x14000ba1c  mov     [rbp+10D0h+var_10B0], rax
0x14000ba20  lea     rax, [rbp+10D0h+var_1128]
0x14000ba24  mov     [rbp+10D0h+var_10A8], rax
0x14000ba28  lea     rax, [rsp+11D0h+var_1170]
0x14000ba2d  mov     [rbp+10D0h+var_10A0], rax
0x14000ba31  lea     rax, [rbp+10D0h+var_10B8]
0x14000ba35  mov     [rbp+10D0h+var_1050], rax
0x14000ba3c  mov     rax, [rdi+18h]
0x14000ba40  add     rax, 0Ah
0x14000ba44  mov     [rbp+10D0h+var_1118], r13w
0x14000ba49  mov     [rsp+11D0h+var_1190], rax
0x14000ba4e  movzx   eax, word ptr [rdi+2]
0x14000ba52  mov     [rbp+10D0h+var_1120], ax
0x14000ba56  mov     al, [rdi+4]
0x14000ba59  mov     [rbp+10D0h+var_111E], al
0x14000ba5c  movzx   eax, word ptr [rdi+6]
0x14000ba60  mov     [rbp+10D0h+var_1100], ax
0x14000ba64  mov     al, [rdi+8]
0x14000ba67  mov     [rbp+10D0h+var_10FE], al
0x14000ba6a  movdqu  [rbp+10D0h+var_1110], xmm0
0x14000ba6f  mov     [rbp+10D0h+var_10FC], r13d
0x14000ba73  mov     [rbp+10D0h+var_10F8], r13w
0x14000ba78  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14000ba7d  jmp     loc_14000BB16
0x14000ba82  mov     ebx, r13d
0x14000ba85  cmp     [rbp+10D0h+var_111C], r13d
0x14000ba89  jbe     loc_14000BB16
0x14000ba8f  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000ba93  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000ba98  lea     rcx, [rbp+10D0h+var_1100]; this
0x14000ba9c  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000baa1  test    al, al
0x14000baa3  jz      short loc_14000BB16
0x14000baa5  mov     eax, [rbp+10D0h+var_10FC]
0x14000baa8  mov     rcx, [rbp+10D0h+var_1050]; this
0x14000baaf  mov     [rsp+11D0h+var_1180], eax
0x14000bab3  movzx   eax, [rbp+10D0h+var_10F8]
0x14000bab7  mov     [rbp+10D0h+var_10E0], rax
0x14000babb  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000babf  mov     [rbp+10D0h+var_10D8], rax
0x14000bac3  movzx   eax, [rbp+10D0h+var_1118]
0x14000bac7  mov     [rbp+10D0h+var_10D0], rax
0x14000bacb  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x14000bacf  mov     [rbp+10D0h+var_10C8], rax
0x14000bad3  test    rcx, rcx
0x14000bad6  jz      loc_14000BC4F
0x14000badc  mov     rax, [rcx]
0x14000badf  lea     rdx, [rsp+11D0h+var_1180]
0x14000bae4  mov     [rsp+11D0h+var_11A8], rdx
0x14000bae9  lea     r9, [rbp+10D0h+var_10D8]
0x14000baed  lea     rdx, [rbp+10D0h+var_10E0]
0x14000baf1  mov     [rsp+11D0h+var_11B0], rdx
0x14000baf6  lea     r8, [rbp+10D0h+var_10D0]
0x14000bafa  mov     rax, [rax+20h]
0x14000bafe  lea     rdx, [rbp+10D0h+var_10C8]
0x14000bb02  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb07  test    al, al
0x14000bb09  jz      short loc_14000BB83
0x14000bb0b  inc     ebx
0x14000bb0d  cmp     ebx, [rbp+10D0h+var_111C]
0x14000bb10  jb      loc_14000BA8F
0x14000bb16  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000bb1a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000bb1f  lea     rcx, [rbp+10D0h+var_1120]; this
0x14000bb23  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000bb28  test    al, al
0x14000bb2a  jnz     loc_14000BA82
0x14000bb30  mov     rcx, [rbp+10D0h+var_1050]
0x14000bb37  test    rcx, rcx
0x14000bb3a  jz      short loc_14000BB48
0x14000bb3c  mov     rax, [rcx]
0x14000bb3f  mov     rax, [rax+18h]
0x14000bb43  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb48  mov     bl, 1
0x14000bb4a  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x14000bb4e  jz      short loc_14000BBC2
0x14000bb50  mov     rdx, [rsp+11D0h+var_1158]
0x14000bb55  mov     rcx, r14
0x14000bb58  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000bb5c  mov     eax, [rsp+11D0h+var_1188]
0x14000bb60  sub     r8d, edx
0x14000bb63  mov     [rsp+11D0h+var_11A0], 1
0x14000bb6b  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14000bb6f  call    wil_details_NtUpdateWnfStateData
0x14000bb74  cmp     eax, 0C0000001h
0x14000bb79  jnz     short loc_14000BBA0
0x14000bb7b  inc     r15
0x14000bb7e  mov     bl, r13b
0x14000bb81  jmp     short loc_14000BBCE
0x14000bb83  mov     rcx, [rbp+10D0h+var_1050]
0x14000bb8a  test    rcx, rcx
0x14000bb8d  jz      short loc_14000BB9B
0x14000bb8f  mov     rax, [rcx]
0x14000bb92  mov     rax, [rax+18h]
0x14000bb96  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb9b  mov     bl, r13b
0x14000bb9e  jmp     short loc_14000BB4A
0x14000bba0  test    eax, eax
0x14000bba2  jz      short loc_14000BBC2
0x14000bba4  mov     rdx, [rsp+11D0h+var_1158]
0x14000bba9  mov     rcx, r14
0x14000bbac  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000bbb0  sub     r8d, edx
0x14000bbb3  mov     [rsp+11D0h+var_11A0], r13d
0x14000bbb8  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x14000bbbd  call    wil_details_NtUpdateWnfStateData
0x14000bbc2  mov     rax, [rbp+10D0h+var_1130]
0x14000bbc6  add     r14, 8
0x14000bbca  mov     [rbp+10D0h+var_1128], rax
0x14000bbce  mov     rsi, [rbp+10D0h+lpMem]
0x14000bbd2  mov     [rbp+10D0h+lpMem], r13
0x14000bbd6  test    rsi, rsi
0x14000bbd9  jz      short loc_14000BBEF
0x14000bbdb  call    cs:__imp_GetProcessHeap
0x14000bbe1  mov     r8, rsi; lpMem
0x14000bbe4  xor     edx, edx; dwFlags
0x14000bbe6  mov     rcx, rax; hHeap
0x14000bbe9  call    cs:__imp_HeapFree
0x14000bbef  test    bl, bl
0x14000bbf1  jnz     short loc_14000BC25
0x14000bbf3  cmp     r14, r12
0x14000bbf6  jnb     short loc_14000BC25
0x14000bbf8  cmp     r15, 32h ; '2'
0x14000bbfc  jb      loc_14000B8D2
0x14000bc02  jmp     short loc_14000BC25
0x14000bc04  mov     rbx, [rbp+10D0h+lpMem]
0x14000bc08  mov     [rbp+10D0h+lpMem], r13
0x14000bc0c  test    rbx, rbx
0x14000bc0f  jz      short loc_14000BC25
0x14000bc11  call    cs:__imp_GetProcessHeap
0x14000bc17  mov     r8, rbx; lpMem
0x14000bc1a  xor     edx, edx; dwFlags
0x14000bc1c  mov     rcx, rax; hHeap
0x14000bc1f  call    cs:__imp_HeapFree
0x14000bc25  mov     rcx, [rbp+10D0h+var_40]
0x14000bc2c  xor     rcx, rsp; StackCookie
0x14000bc2f  call    __security_check_cookie
0x14000bc34  mov     rbx, [rsp+11D0h+arg_8]
0x14000bc3c  add     rsp, 11A0h
0x14000bc43  pop     r15
0x14000bc45  pop     r14
0x14000bc47  pop     r13
0x14000bc49  pop     r12
0x14000bc4b  pop     rdi
0x14000bc4c  pop     rsi
0x14000bc4d  pop     rbp
0x14000bc4e  retn
0x14000bc4f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
