# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180006bcc`
- end: `0x180006f99`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `973`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180006118`

## callees

- `0x180005c38`
- `0x180006028`
- `0x180006bcc`
- `0x18000758c`
- `0x1800082c4`
- `0x180008bc0`
- `0x180016280`
- `0x180016310`
- `0x180017010`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180006f2d`
- `KERNEL32!HeapFree` at `0x180006f63`
- `KERNEL32!HeapFree` at `0x180006f2d`
- `KERNEL32!HeapFree` at `0x180006f63`
- `KERNEL32!GetProcessHeap` at `0x180006f1f`
- `KERNEL32!GetProcessHeap` at `0x180006f55`
- `KERNEL32!GetProcessHeap` at `0x180006f1f`
- `KERNEL32!GetProcessHeap` at `0x180006f55`
- `KERNEL32!GetModuleHandleW` at `0x180006cab`
- `KERNEL32!GetModuleHandleW` at `0x180006cab`
- `KERNEL32!GetProcAddress` at `0x180006cc2`
- `KERNEL32!GetProcAddress` at `0x180006cc2`

## string_xrefs

- `0x180006ca4`: `ntdll.dll`

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
0x180006bcc  mov     [rsp-8+arg_8], rbx
0x180006bd1  push    rbp
0x180006bd2  push    rsi
0x180006bd3  push    rdi
0x180006bd4  push    r12
0x180006bd6  push    r13
0x180006bd8  push    r14
0x180006bda  push    r15
0x180006bdc  lea     rbp, [rsp-10A0h]
0x180006be4  mov     eax, 11A0h
0x180006be9  call    _alloca_probe
0x180006bee  sub     rsp, rax
0x180006bf1  mov     rax, cs:__security_cookie
0x180006bf8  xor     rax, rsp
0x180006bfb  mov     [rbp+10D0h+var_40], rax
0x180006c02  xor     r13d, r13d
0x180006c05  lea     r12, [rcx+rdx*8]
0x180006c09  mov     r15d, r13d
0x180006c0c  mov     [rbp+10D0h+var_1128], r13
0x180006c10  mov     rdi, r8
0x180006c13  mov     r14, rcx
0x180006c16  movzx   eax, word ptr [rdi]
0x180006c19  movzx   edx, word ptr [rdi+6]
0x180006c1d  mov     cl, [rdi+8]
0x180006c20  mov     [rsp+11D0h+var_1170], ax
0x180006c25  movzx   eax, word ptr [rdi+2]
0x180006c29  mov     [rsp+11D0h+var_116E], ax
0x180006c2e  mov     al, [rdi+4]
0x180006c31  mov     [rsp+11D0h+var_116C], al
0x180006c35  mov     [rsp+11D0h+var_116A], dx
0x180006c3a  mov     [rsp+11D0h+var_1168], cl
0x180006c3e  test    dx, dx
0x180006c41  jz      short loc_180006C60
0x180006c43  mov     eax, edx
0x180006c45  cmp     cl, 1
0x180006c48  jnz     short loc_180006C50
0x180006c4a  add     rax, 2
0x180006c4e  jmp     short loc_180006C59
0x180006c50  cmp     cl, 2
0x180006c53  jnz     short loc_180006C59
0x180006c55  add     rax, 4
0x180006c59  mov     [rsp+11D0h+var_1160], rax
0x180006c5e  jmp     short loc_180006C65
0x180006c60  mov     [rsp+11D0h+var_1160], r13
0x180006c65  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180006c6c  xorps   xmm0, xmm0
0x180006c6f  mov     [rsp+11D0h+var_1158], r13
0x180006c74  movdqa  [rbp+10D0h+var_1150], xmm0
0x180006c79  mov     [rbp+10D0h+lpMem], r13
0x180006c7d  mov     [rbp+10D0h+var_1138], r13w
0x180006c82  mov     [rbp+10D0h+var_1136], r13b
0x180006c86  mov     [rsp+11D0h+var_1188], r13d
0x180006c8b  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180006c93  test    rax, rax
0x180006c96  jnz     short loc_180006CDB
0x180006c98  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006c9f  test    rax, rax
0x180006ca2  jnz     short loc_180006CB8
0x180006ca4  lea     rcx, ModuleName; "ntdll.dll"
0x180006cab  call    cs:__imp_GetModuleHandleW
0x180006cb1  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180006cb8  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180006cbf  mov     rcx, rax; hModule
0x180006cc2  call    cs:__imp_GetProcAddress
0x180006cc8  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180006ccf  test    rax, rax
0x180006cd2  jnz     short loc_180006CDB
0x180006cd4  mov     ebx, 0C0000139h
0x180006cd9  jmp     short loc_180006D05
0x180006cdb  lea     rcx, [rsp+11D0h+var_1190]
0x180006ce0  xor     r8d, r8d
0x180006ce3  mov     [rsp+11D0h+var_11A8], rcx
0x180006ce8  lea     r9, [rsp+11D0h+var_1188]
0x180006ced  lea     rcx, [rbp+10D0h+var_1040]
0x180006cf4  xor     edx, edx
0x180006cf6  mov     [rsp+11D0h+var_11B0], rcx
0x180006cfb  mov     rcx, r14
0x180006cfe  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006d03  mov     ebx, eax
0x180006d05  mov     ecx, ebx; this
0x180006d07  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180006d0c  test    ebx, ebx
0x180006d0e  jz      short loc_180006D1E
0x180006d10  mov     eax, r13d
0x180006d13  mov     [rsp+11D0h+var_1188], r13d
0x180006d18  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180006d1c  jmp     short loc_180006D22
0x180006d1e  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180006d22  mov     r8d, eax; unsigned __int64
0x180006d25  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180006d2c  mov     r9d, 1000h; unsigned __int64
0x180006d32  lea     rcx, [rsp+11D0h+var_1170]; this
0x180006d37  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180006d3c  cmp     byte ptr [rbp+10D0h+var_1138+1], r13b
0x180006d40  jnz     loc_180006F48
0x180006d46  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180006d4d  mov     [rbp+10D0h+var_1130], r13
0x180006d51  mov     [rbp+10D0h+var_10B8], rax
0x180006d55  xorps   xmm0, xmm0
0x180006d58  lea     rax, [rbp+10D0h+var_1130]
0x180006d5c  mov     [rbp+10D0h+var_111C], r13d
0x180006d60  mov     [rbp+10D0h+var_10B0], rax
0x180006d64  lea     rax, [rbp+10D0h+var_1128]
0x180006d68  mov     [rbp+10D0h+var_10A8], rax
0x180006d6c  lea     rax, [rsp+11D0h+var_1170]
0x180006d71  mov     [rbp+10D0h+var_10A0], rax
0x180006d75  lea     rax, [rbp+10D0h+var_10B8]
0x180006d79  mov     [rbp+10D0h+var_1050], rax
0x180006d80  mov     rax, [rdi+18h]
0x180006d84  add     rax, 0Ah
0x180006d88  mov     [rbp+10D0h+var_1118], r13w
0x180006d8d  mov     [rsp+11D0h+var_1190], rax
0x180006d92  movzx   eax, word ptr [rdi+2]
0x180006d96  mov     [rbp+10D0h+var_1120], ax
0x180006d9a  mov     al, [rdi+4]
0x180006d9d  mov     [rbp+10D0h+var_111E], al
0x180006da0  movzx   eax, word ptr [rdi+6]
0x180006da4  mov     [rbp+10D0h+var_1100], ax
0x180006da8  mov     al, [rdi+8]
0x180006dab  mov     [rbp+10D0h+var_10FE], al
0x180006dae  movdqu  [rbp+10D0h+var_1110], xmm0
0x180006db3  mov     [rbp+10D0h+var_10FC], r13d
0x180006db7  mov     [rbp+10D0h+var_10F8], r13w
0x180006dbc  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180006dc1  jmp     loc_180006E5A
0x180006dc6  mov     ebx, r13d
0x180006dc9  cmp     [rbp+10D0h+var_111C], r13d
0x180006dcd  jbe     loc_180006E5A
0x180006dd3  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006dd7  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180006ddc  lea     rcx, [rbp+10D0h+var_1100]; this
0x180006de0  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006de5  test    al, al
0x180006de7  jz      short loc_180006E5A
0x180006de9  mov     eax, [rbp+10D0h+var_10FC]
0x180006dec  mov     rcx, [rbp+10D0h+var_1050]; this
0x180006df3  mov     [rsp+11D0h+var_1180], eax
0x180006df7  movzx   eax, [rbp+10D0h+var_10F8]
0x180006dfb  mov     [rbp+10D0h+var_10E0], rax
0x180006dff  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180006e03  mov     [rbp+10D0h+var_10D8], rax
0x180006e07  movzx   eax, [rbp+10D0h+var_1118]
0x180006e0b  mov     [rbp+10D0h+var_10D0], rax
0x180006e0f  mov     rax, qword ptr [rbp+10D0h+var_1110+8]
0x180006e13  mov     [rbp+10D0h+var_10C8], rax
0x180006e17  test    rcx, rcx
0x180006e1a  jz      loc_180006F93
0x180006e20  mov     rax, [rcx]
0x180006e23  lea     rdx, [rsp+11D0h+var_1180]
0x180006e28  mov     [rsp+11D0h+var_11A8], rdx
0x180006e2d  lea     r9, [rbp+10D0h+var_10D8]
0x180006e31  lea     rdx, [rbp+10D0h+var_10E0]
0x180006e35  mov     [rsp+11D0h+var_11B0], rdx
0x180006e3a  lea     r8, [rbp+10D0h+var_10D0]
0x180006e3e  mov     rax, [rax+20h]
0x180006e42  lea     rdx, [rbp+10D0h+var_10C8]
0x180006e46  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e4b  test    al, al
0x180006e4d  jz      short loc_180006EC7
0x180006e4f  inc     ebx
0x180006e51  cmp     ebx, [rbp+10D0h+var_111C]
0x180006e54  jb      loc_180006DD3
0x180006e5a  mov     r8, [rdi+20h]; unsigned __int8 *
0x180006e5e  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180006e63  lea     rcx, [rbp+10D0h+var_1120]; this
0x180006e67  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180006e6c  test    al, al
0x180006e6e  jnz     loc_180006DC6
0x180006e74  mov     rcx, [rbp+10D0h+var_1050]
0x180006e7b  test    rcx, rcx
0x180006e7e  jz      short loc_180006E8C
0x180006e80  mov     rax, [rcx]
0x180006e83  mov     rax, [rax+18h]
0x180006e87  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006e8c  mov     bl, 1
0x180006e8e  cmp     byte ptr [rbp+10D0h+var_1138], r13b
0x180006e92  jz      short loc_180006F06
0x180006e94  mov     rdx, [rsp+11D0h+var_1158]
0x180006e99  mov     rcx, r14
0x180006e9c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006ea0  mov     eax, [rsp+11D0h+var_1188]
0x180006ea4  sub     r8d, edx
0x180006ea7  mov     [rsp+11D0h+var_11A0], 1
0x180006eaf  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180006eb3  call    wil_details_NtUpdateWnfStateData
0x180006eb8  cmp     eax, 0C0000001h
0x180006ebd  jnz     short loc_180006EE4
0x180006ebf  inc     r15
0x180006ec2  mov     bl, r13b
0x180006ec5  jmp     short loc_180006F12
0x180006ec7  mov     rcx, [rbp+10D0h+var_1050]
0x180006ece  test    rcx, rcx
0x180006ed1  jz      short loc_180006EDF
0x180006ed3  mov     rax, [rcx]
0x180006ed6  mov     rax, [rax+18h]
0x180006eda  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180006edf  mov     bl, r13b
0x180006ee2  jmp     short loc_180006E8E
0x180006ee4  test    eax, eax
0x180006ee6  jz      short loc_180006F06
0x180006ee8  mov     rdx, [rsp+11D0h+var_1158]
0x180006eed  mov     rcx, r14
0x180006ef0  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180006ef4  sub     r8d, edx
0x180006ef7  mov     [rsp+11D0h+var_11A0], r13d
0x180006efc  mov     dword ptr [rsp+11D0h+var_11A8], r13d
0x180006f01  call    wil_details_NtUpdateWnfStateData
0x180006f06  mov     rax, [rbp+10D0h+var_1130]
0x180006f0a  add     r14, 8
0x180006f0e  mov     [rbp+10D0h+var_1128], rax
0x180006f12  mov     rsi, [rbp+10D0h+lpMem]
0x180006f16  mov     [rbp+10D0h+lpMem], r13
0x180006f1a  test    rsi, rsi
0x180006f1d  jz      short loc_180006F33
0x180006f1f  call    cs:__imp_GetProcessHeap
0x180006f25  mov     r8, rsi; lpMem
0x180006f28  xor     edx, edx; dwFlags
0x180006f2a  mov     rcx, rax; hHeap
0x180006f2d  call    cs:__imp_HeapFree
0x180006f33  test    bl, bl
0x180006f35  jnz     short loc_180006F69
0x180006f37  cmp     r14, r12
0x180006f3a  jnb     short loc_180006F69
0x180006f3c  cmp     r15, 32h ; '2'
0x180006f40  jb      loc_180006C16
0x180006f46  jmp     short loc_180006F69
0x180006f48  mov     rbx, [rbp+10D0h+lpMem]
0x180006f4c  mov     [rbp+10D0h+lpMem], r13
0x180006f50  test    rbx, rbx
0x180006f53  jz      short loc_180006F69
0x180006f55  call    cs:__imp_GetProcessHeap
0x180006f5b  mov     r8, rbx; lpMem
0x180006f5e  xor     edx, edx; dwFlags
0x180006f60  mov     rcx, rax; hHeap
0x180006f63  call    cs:__imp_HeapFree
0x180006f69  mov     rcx, [rbp+10D0h+var_40]
0x180006f70  xor     rcx, rsp; StackCookie
0x180006f73  call    __security_check_cookie
0x180006f78  mov     rbx, [rsp+11D0h+arg_8]
0x180006f80  add     rsp, 11A0h
0x180006f87  pop     r15
0x180006f89  pop     r14
0x180006f8b  pop     r13
0x180006f8d  pop     r12
0x180006f8f  pop     rdi
0x180006f90  pop     rsi
0x180006f91  pop     rbp
0x180006f92  retn
0x180006f93  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
