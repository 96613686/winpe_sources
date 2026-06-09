# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180006b98`
- end: `0x180006f65`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x1800062cc`

## callees

- `0x180005d94`
- `0x1800061dc`
- `0x180006b98`
- `0x1800078dc`
- `0x180009474`
- `0x18000a7b8`
- `0x180013840`
- `0x1800138d0`
- `0x180014010`

## import_xrefs

- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ef9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f2f`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006ef9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180006f2f`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eeb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f21`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006eeb`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180006f21`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c77`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180006c77`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c8e`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180006c8e`

## string_xrefs

- `0x180006c70`: `ntdll.dll`

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
  int v18; // r9d
  char v19; // bl
  int updated; // eax
  int v21; // r9d
  void *v22; // rsi
  HANDLE ProcessHeap; // rax
  void *v24; // rbx
  HANDLE v25; // rax
  __int64 *v26; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v27; // [rsp+40h] [rbp-C0h] BYREF
  _DWORD v28[6]; // [rsp+48h] [rbp-B8h] BYREF
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v7, 0, 0, v28);
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
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v7, v34, (int)v35 - (int)v34, v18, (_DWORD)v26, v28[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v7, v34, v35 - v34, v21, (_DWORD)v26, 0, 0);
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
0x180006b98  mov     [rsp-8+arg_8], rbx
0x180006b9d  push    rbp
0x180006b9e  push    rsi
0x180006b9f  push    rdi
0x180006ba0  push    r12
0x180006ba2  push    r13
0x180006ba4  push    r14
0x180006ba6  push    r15
0x180006ba8  lea     rbp, [rsp-10A0h]
0x180006bb0  mov     eax, 11A0h
0x180006bb5  call    _alloca_probe
0x180006bba  sub     rsp, rax
0x180006bbd  mov     rax, cs:__security_cookie
0x180006bc4  xor     rax, rsp
0x180006bc7  mov     [rbp+10D0h+var_40], rax
0x180006bce  xor     r13d, r13d
0x180006bd1  lea     r12, [rcx+rdx*8]
0x180006bd5  mov     r15d, r13d
0x180006bd8  mov     [rbp+10D0h+var_1128], r13
0x180006bdc  mov     rdi, r8
0x180006bdf  mov     r14, rcx
0x180006be2  movzx   eax, word ptr [rdi]
0x180006be5  movzx   edx, word ptr [rdi+6]
0x180006be9  mov     cl, [rdi+8]
0x180006bec  mov     [rsp+11D0h+var_1170], ax
0x180006bf1  movzx   eax, word ptr [rdi+2]
0x180006bf5  mov     [rsp+11D0h+var_116E], ax
0x180006bfa  mov     al, [rdi+4]
0x180006bfd  mov     [rsp+11D0h+var_116C], al
0x180006c01  mov     [rsp+11D0h+var_116A], dx
0x180006c06  mov     [rsp+11D0h+var_1168], cl
0x180006c0a  test    dx, dx
0x180006c0d  jz      short loc_180006C2C
0x180006c0f  mov     eax, edx
0x180006c11  cmp     cl, 1
0x180006c14  jnz     short loc_180006C1C
0x180006c16  add     rax, 2
0x180006c1a  jmp     short loc_180006C25
0x180006c1c  cmp     cl, 2
0x180006c1f  jnz     short loc_180006C25
0x180006c21  add     rax, 4
0x180006c25  mov     [rsp+11D0h+var_1160], rax
0x180006c2a  jmp     short loc_180006C31
0x180006c2c  mov     [rsp+11D0h+var_1160], r13
0x180006c31  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180006c38  xorps   xmm0, xmm0
0x180006c3b  mov     [rsp+11D0h+var_1158], r13
0x180006c40  movdqa  [rbp+10D0h+var_1150], xmm0
0x180006c45  mov     [rbp+10D0h+lpMem], r13
0x180006c49  mov     [rbp+10D0h+var_1138], r13w
0x180006c4e  mov     [rbp+10D0h+var_1136], r13b
0x180006c52  mov     [rsp+11D0h+var_1188], r13d
0x180006c57  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180006c5f  test    rax, rax
0x180006c62  jnz     short loc_180006CA7
0x180006c64  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006c6b  test    rax, rax
0x180006c6e  jnz     short loc_180006C84
0x180006c70  lea     rcx, ModuleName; "ntdll.dll"
0x180006c77  call    cs:__imp_GetModuleHandleW
0x180006c7d  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006c84  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180006c8b  mov     rcx, rax; hModule
0x180006c8e  call    cs:__imp_GetProcAddress
0x180006c94  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180006c9b  test    rax, rax
0x180006c9e  jnz     short loc_180006CA7
0x180006ca0  mov     ebx, 0C0000139h
0x180006ca5  jmp     short loc_180006CD1
0x180006ca7  lea     rcx, [rsp+11D0h+var_1190]
0x180006cac  xor     r8d, r8d
0x180006caf  mov     [rsp+11D0h+var_11A8], rcx
0x180006cb4  lea     r9, [rsp+11D0h+var_1188]
0x180006cb9  lea     rcx, [rbp+10D0h+var_1040]
0x180006cc0  xor     edx, edx
0x180006cc2  mov     [rsp+11D0h+var_11B0], rcx
0x180006cc7  mov     rcx, r14
0x180006cca  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006ccf  mov     ebx, eax
0x180006cd1  mov     ecx, ebx; this
0x180006cd3  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180006cd8  test    ebx, ebx
0x180006cda  jz      short loc_180006CEA
0x180006cdc  mov     eax, r13d
0x180006cdf  mov     [rsp+11D0h+var_1188], r13d
0x180006ce4  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180006ce8  jmp     short loc_180006CEE
0x180006cea  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180006cee  mov     r8d, eax; unsigned __int64
0x180006cf1  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180006cf8  mov     r9d, 1000h; unsigned __int64
0x180006cfe  lea     rcx, [rsp+11D0h+var_1170]; this
0x180006d03  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180006d08  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180006d0c  jnz     loc_180006F14
0x180006d12  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180006d19  mov     [rbp+10D0h+var_1130], r13
0x180006d1d  mov     [rbp+10D0h+var_10B8], rax
0x180006d21  xorps   xmm0, xmm0
0x180006d24  lea     rax, [rbp+10D0h+var_1130]
0x180006d28  mov     [rbp+10D0h+var_111C], r13d
0x180006d2c  mov     [rbp+10D0h+var_10B0], rax
0x180006d30  lea     rax, [rbp+10D0h+var_1128]
0x180006d34  mov     [rbp+10D0h+var_10A8], rax
0x180006d38  lea     rax, [rsp+11D0h+var_1170]
0x180006d3d  mov     [rbp+10D0h+var_10A0], rax
0x180006d41  lea     rax, [rbp+10D0h+var_10B8]
0x180006d45  mov     [rbp+10D0h+var_1050], rax
0x180006d4c  mov     rax, [rdi+18h]
0x180006d50  add     rax, 0Ah
0x180006d54  mov     [rbp+10D0h+var_1118], r13w
0x180006d59  mov     [rsp+11D0h+var_1190], rax
0x180006d5e  movzx   eax, word ptr [rdi+2]
0x180006d62  mov     [rbp+10D0h+var_1120], ax
0x180006d66  mov     al, [rdi+4]
0x180006d69  mov     [rbp+10D0h+var_111E], al
0x180006d6c  movzx   eax, word ptr [rdi+6]
0x180006d70  mov     [rbp+10D0h+var_1100], ax
0x180006d74  mov     al, [rdi+8]
0x180006d77  mov     [rbp+10D0h+var_10FE], al
0x180006d7a  movdqu  [rbp+10D0h+var_1110], xmm0
0x180006d7f  mov     [rbp+10D0h+var_10FC], r13d
0x180006d83  mov     [rbp+10D0h+var_10F8], r13w
0x180006d88  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180006d8d  jmp     loc_180006E26
0x180006d92  mov     ebx, r13d
0x180006d95  cmp     [rbp+10D0h+var_111C], r13d
0x180006d99  jbe     loc_180006E26
0x180006d9f  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006da3  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180006da8  lea     rcx, [rbp+10D0h+var_1100]; this
0x180006dac  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006db1  test    al, al
0x180006db3  jz      short loc_180006E26
0x180006db5  mov     eax, [rbp+10D0h+var_10FC]
0x180006db8  mov     rcx, [rbp+10D0h+var_1050]; this
0x180006dbf  mov     [rsp+11D0h+var_1180], eax
0x180006dc3  movzx   eax, [rbp+10D0h+var_10F8]
0x180006dc7  mov     [rbp+10D0h+var_10E0], rax
0x180006dcb  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180006dcf  mov     [rbp+10D0h+var_10D8], rax
0x180006dd3  movzx   eax, [rbp+10D0h+var_1118]
0x180006dd7  mov     [rbp+10D0h+var_10D0], rax
0x180006ddb  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x180006ddf  mov     [rbp+10D0h+var_10C8], rax
0x180006de3  test    rcx, rcx
0x180006de6  jz      loc_180006F5F
0x180006dec  mov     rax, [rcx]
0x180006def  lea     rdx, [rsp+11D0h+var_1180]
0x180006df4  mov     [rsp+11D0h+var_11A8], rdx
0x180006df9  lea     r9, [rbp+10D0h+var_10D8]
0x180006dfd  lea     rdx, [rbp+10D0h+var_10E0]
0x180006e01  mov     [rsp+11D0h+var_11B0], rdx
0x180006e06  lea     r8, [rbp+10D0h+var_10D0]
0x180006e0a  mov     rax, [rax+20h]
0x180006e0e  lea     rdx, [rbp+10D0h+var_10C8]
0x180006e12  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e17  test    al, al
0x180006e19  jz      short loc_180006E93
0x180006e1b  inc     ebx
0x180006e1d  cmp     ebx, [rbp+10D0h+var_111C]
0x180006e20  jb      loc_180006D9F
0x180006e26  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006e2a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180006e2f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180006e33  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006e38  test    al, al
0x180006e3a  jnz     loc_180006D92
0x180006e40  mov     rcx, [rbp+10D0h+var_1050]
0x180006e47  test    rcx, rcx
0x180006e4a  jz      short loc_180006E58
0x180006e4c  mov     rax, [rcx]
0x180006e4f  mov     rax, [rax+18h]
0x180006e53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e58  mov     bl, 1
0x180006e5a  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x180006e5e  jz      short loc_180006ED2
0x180006e60  mov     rdx, [rsp+11D0h+var_1158]
0x180006e65  mov     rcx, r14
0x180006e68  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006e6c  mov     eax, [rsp+11D0h+var_1188]
0x180006e70  sub     r8d, edx
0x180006e73  mov     [rsp+11D0h+var_11A0], 1
0x180006e7b  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180006e7f  call    wil_details_NtUpdateWnfStateData
0x180006e84  cmp     eax, 0C0000001h
0x180006e89  jnz     short loc_180006EB0
0x180006e8b  inc     r15
0x180006e8e  mov     bl, r13b
0x180006e91  jmp     short loc_180006EDE
0x180006e93  mov     rcx, [rbp+10D0h+var_1050]
0x180006e9a  test    rcx, rcx
0x180006e9d  jz      short loc_180006EAB
0x180006e9f  mov     rax, [rcx]
0x180006ea2  mov     rax, [rax+18h]
0x180006ea6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006eab  mov     bl, r13b
0x180006eae  jmp     short loc_180006E5A
0x180006eb0  test    eax, eax
0x180006eb2  jz      short loc_180006ED2
0x180006eb4  mov     rdx, [rsp+11D0h+var_1158]
0x180006eb9  mov     rcx, r14
0x180006ebc  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006ec0  sub     r8d, edx
0x180006ec3  mov     [rsp+11D0h+var_11A0], r13d
0x180006ec8  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x180006ecd  call    wil_details_NtUpdateWnfStateData
0x180006ed2  mov     rax, [rbp+10D0h+var_1130]
0x180006ed6  add     r14, 8
0x180006eda  mov     [rbp+10D0h+var_1128], rax
0x180006ede  mov     rsi, [rbp+10D0h+lpMem]
0x180006ee2  mov     [rbp+10D0h+lpMem], r13
0x180006ee6  test    rsi, rsi
0x180006ee9  jz      short loc_180006EFF
0x180006eeb  call    cs:__imp_GetProcessHeap
0x180006ef1  mov     r8, rsi; lpMem
0x180006ef4  xor     edx, edx; dwFlags
0x180006ef6  mov     rcx, rax; hHeap
0x180006ef9  call    cs:__imp_HeapFree
0x180006eff  test    bl, bl
0x180006f01  jnz     short loc_180006F35
0x180006f03  cmp     r14, r12
0x180006f06  jnb     short loc_180006F35
0x180006f08  cmp     r15, 32h ; '2'
0x180006f0c  jb      loc_180006BE2
0x180006f12  jmp     short loc_180006F35
0x180006f14  mov     rbx, [rbp+10D0h+lpMem]
0x180006f18  mov     [rbp+10D0h+lpMem], r13
0x180006f1c  test    rbx, rbx
0x180006f1f  jz      short loc_180006F35
0x180006f21  call    cs:__imp_GetProcessHeap
0x180006f27  mov     r8, rbx; lpMem
0x180006f2a  xor     edx, edx; dwFlags
0x180006f2c  mov     rcx, rax; hHeap
0x180006f2f  call    cs:__imp_HeapFree
0x180006f35  mov     rcx, [rbp+10D0h+var_40]
0x180006f3c  xor     rcx, rsp; StackCookie
0x180006f3f  call    __security_check_cookie
0x180006f44  mov     rbx, [rsp+11D0h+arg_8]
0x180006f4c  add     rsp, 11A0h
0x180006f53  pop     r15
0x180006f55  pop     r14
0x180006f57  pop     r13
0x180006f59  pop     r12
0x180006f5b  pop     rdi
0x180006f5c  pop     rsi
0x180006f5d  pop     rbp
0x180006f5e  retn
0x180006f5f  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
