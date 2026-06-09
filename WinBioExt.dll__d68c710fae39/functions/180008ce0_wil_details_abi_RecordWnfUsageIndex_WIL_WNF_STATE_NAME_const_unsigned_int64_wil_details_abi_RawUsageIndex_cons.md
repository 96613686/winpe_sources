# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x180008ce0`
- end: `0x1800090b8`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180008428`

## callees

- `0x180001610`
- `0x180005b4c`
- `0x180008064`
- `0x180008328`
- `0x180008ce0`
- `0x18000926c`
- `0x180009d94`
- `0x180009f50`
- `0x18000b010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x180008dc0`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008dd7`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x180008dd7`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000903e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009074`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x18000903e`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009074`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000904c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009082`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x18000904c`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009082`

## string_xrefs

- `0x180008db9`: `ntdll.dll`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
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
  __int64 v19; // r9
  char v20; // bl
  int updated; // eax
  __int64 v22; // r9
  void *v23; // rsi
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 *v27; // [rsp+20h] [rbp-E0h]
  unsigned __int8 *v28; // [rsp+40h] [rbp-C0h] BYREF
  int v29[6]; // [rsp+48h] [rbp-B8h] BYREF
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
    ModuleHandleW = (HMODULE)`wil_details_GetNtDllModuleHandle'::`2'::wil_details_ntdllModuleHandle;
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
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, int *))ProcAddress)(v5, 0, 0, v29);
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
    updated = wil_details_NtUpdateWnfStateData((__int64)v5, v35, (int)v36 - (int)v35, v19, (int)v27, v29[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((__int64)v5, v35, v36 - v35, v22, (int)v27, 0, 0);
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
0x180008ce0  mov     [rsp-8+arg_8], rbx
0x180008ce5  push    rbp
0x180008ce6  push    rsi
0x180008ce7  push    rdi
0x180008ce8  push    r12
0x180008cea  push    r13
0x180008cec  push    r14
0x180008cee  push    r15
0x180008cf0  lea     rbp, [rsp-10A0h]
0x180008cf8  mov     eax, 11A0h
0x180008cfd  call    _alloca_probe
0x180008d02  sub     rsp, rax
0x180008d05  mov     rax, cs:__security_cookie
0x180008d0c  xor     rax, rsp
0x180008d0f  mov     [rbp+10D0h+var_40], rax
0x180008d16  mov     rdi, r8
0x180008d19  mov     r14, rcx
0x180008d1c  lea     r13, [rcx+rdx*8]
0x180008d20  xor     r15d, r15d
0x180008d23  mov     r12d, r15d
0x180008d26  mov     [rbp+10D0h+var_1128], r15
0x180008d2a  mov     cl, [rdi+8]
0x180008d2d  movzx   edx, word ptr [rdi+6]
0x180008d31  movzx   eax, word ptr [rdi]
0x180008d34  mov     [rsp+11D0h+var_1170], ax
0x180008d39  movzx   eax, word ptr [rdi+2]
0x180008d3d  mov     [rsp+11D0h+var_116E], ax
0x180008d42  mov     al, [rdi+4]
0x180008d45  mov     [rsp+11D0h+var_116C], al
0x180008d49  mov     [rsp+11D0h+var_116A], dx
0x180008d4e  mov     [rsp+11D0h+var_1168], cl
0x180008d52  test    dx, dx
0x180008d55  jz      short loc_180008D74
0x180008d57  mov     eax, edx
0x180008d59  cmp     cl, 1
0x180008d5c  jnz     short loc_180008D64
0x180008d5e  add     rax, 2
0x180008d62  jmp     short loc_180008D6D
0x180008d64  cmp     cl, 2
0x180008d67  jnz     short loc_180008D6D
0x180008d69  add     rax, 4
0x180008d6d  mov     [rsp+11D0h+var_1160], rax
0x180008d72  jmp     short loc_180008D79
0x180008d74  mov     [rsp+11D0h+var_1160], r15
0x180008d79  mov     [rsp+11D0h+var_1158], r15
0x180008d7e  xorps   xmm0, xmm0
0x180008d81  movdqa  [rbp+10D0h+var_1150], xmm0
0x180008d86  mov     [rbp+10D0h+lpMem], r15
0x180008d8a  mov     [rbp+10D0h+var_1138], 0
0x180008d90  mov     [rbp+10D0h+var_1136], r15b
0x180008d94  mov     [rsp+11D0h+var_1188], r15d
0x180008d99  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x180008da1  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x180008da8  test    rax, rax
0x180008dab  jnz     short loc_180008DF0
0x180008dad  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008db4  test    rax, rax
0x180008db7  jnz     short loc_180008DCD
0x180008db9  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x180008dc0  call    cs:__imp_GetModuleHandleW
0x180008dc6  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x180008dcd  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180008dd4  mov     rcx, rax; hModule
0x180008dd7  call    cs:__imp_GetProcAddress
0x180008ddd  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180008de4  test    rax, rax
0x180008de7  jnz     short loc_180008DF0
0x180008de9  mov     ebx, 0C0000139h
0x180008dee  jmp     short loc_180008E1A
0x180008df0  lea     rcx, [rsp+11D0h+var_1190]
0x180008df5  mov     [rsp+11D0h+var_11A8], rcx
0x180008dfa  lea     rcx, [rbp+10D0h+var_1040]
0x180008e01  mov     [rsp+11D0h+var_11B0], rcx
0x180008e06  lea     r9, [rsp+11D0h+var_1188]
0x180008e0b  xor     r8d, r8d
0x180008e0e  xor     edx, edx
0x180008e10  mov     rcx, r14
0x180008e13  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008e18  mov     ebx, eax
0x180008e1a  mov     ecx, ebx; this
0x180008e1c  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180008e21  test    ebx, ebx
0x180008e23  jz      short loc_180008E33
0x180008e25  mov     eax, r15d
0x180008e28  mov     dword ptr [rsp+11D0h+var_1190], eax
0x180008e2c  mov     [rsp+11D0h+var_1188], r15d
0x180008e31  jmp     short loc_180008E37
0x180008e33  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x180008e37  mov     r8d, eax; unsigned __int64
0x180008e3a  mov     r9d, 1000h; unsigned __int64
0x180008e40  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180008e47  lea     rcx, [rsp+11D0h+var_1170]; this
0x180008e4c  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180008e51  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x180008e55  jnz     loc_180009067
0x180008e5b  mov     [rbp+10D0h+var_1130], r15
0x180008e5f  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180008e66  mov     [rbp+10D0h+var_10B0], rax
0x180008e6a  lea     rax, [rbp+10D0h+var_1130]
0x180008e6e  mov     [rbp+10D0h+var_10A8], rax
0x180008e72  lea     rax, [rbp+10D0h+var_1128]
0x180008e76  mov     [rbp+10D0h+var_10A0], rax
0x180008e7a  lea     rax, [rsp+11D0h+var_1170]
0x180008e7f  mov     [rbp+10D0h+var_1098], rax
0x180008e83  lea     rax, [rbp+10D0h+var_10B0]
0x180008e87  mov     [rbp+10D0h+var_1048], rax
0x180008e8e  lea     rax, [rbp+10D0h+var_10B8]
0x180008e92  mov     [rbp+10D0h+var_10C0], rax
0x180008e96  mov     rax, [rdi+18h]
0x180008e9a  add     rax, 0Ah
0x180008e9e  mov     [rsp+11D0h+var_1190], rax
0x180008ea3  movzx   eax, word ptr [rdi+2]
0x180008ea7  mov     [rbp+10D0h+var_1120], ax
0x180008eab  mov     al, [rdi+4]
0x180008eae  mov     [rbp+10D0h+var_111E], al
0x180008eb1  mov     [rbp+10D0h+var_111C], r15d
0x180008eb5  mov     [rbp+10D0h+var_1118], r15w
0x180008eba  xorps   xmm0, xmm0
0x180008ebd  movdqu  [rbp+10D0h+var_1110], xmm0
0x180008ec2  movzx   eax, word ptr [rdi+6]
0x180008ec6  mov     [rbp+10D0h+var_1100], ax
0x180008eca  mov     al, [rdi+8]
0x180008ecd  mov     [rbp+10D0h+var_10FE], al
0x180008ed0  mov     [rbp+10D0h+var_10FC], r15d
0x180008ed4  mov     [rbp+10D0h+var_10F8], r15w
0x180008ed9  movdqu  [rbp+10D0h+var_10F0], xmm0
0x180008ede  jmp     loc_180008F76
0x180008ee3  mov     ebx, r15d
0x180008ee6  mov     esi, [rbp+10D0h+var_111C]
0x180008ee9  test    esi, esi
0x180008eeb  jz      loc_180008F76
0x180008ef1  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x180008ef5  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008ef9  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180008efe  lea     rcx, [rbp+10D0h+var_1100]; this
0x180008f02  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008f07  test    al, al
0x180008f09  jz      short loc_180008F73
0x180008f0b  mov     eax, [rbp+10D0h+var_10FC]
0x180008f0e  mov     [rsp+11D0h+var_1180], eax
0x180008f12  movzx   eax, [rbp+10D0h+var_10F8]
0x180008f16  mov     [rbp+10D0h+var_10E0], rax
0x180008f1a  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x180008f1e  mov     [rbp+10D0h+var_10D8], rax
0x180008f22  movzx   eax, [rbp+10D0h+var_1118]
0x180008f26  mov     [rbp+10D0h+var_10D0], rax
0x180008f2a  mov     [rbp+10D0h+var_10C8], r15
0x180008f2e  mov     rcx, [rbp+10D0h+var_1048]; this
0x180008f35  test    rcx, rcx
0x180008f38  jz      loc_1800090B2
0x180008f3e  mov     rax, [rcx]
0x180008f41  lea     rdx, [rsp+11D0h+var_1180]
0x180008f46  mov     [rsp+11D0h+var_11A8], rdx
0x180008f4b  lea     rdx, [rbp+10D0h+var_10E0]
0x180008f4f  mov     [rsp+11D0h+var_11B0], rdx
0x180008f54  lea     r9, [rbp+10D0h+var_10D8]
0x180008f58  lea     r8, [rbp+10D0h+var_10D0]
0x180008f5c  lea     rdx, [rbp+10D0h+var_10C8]
0x180008f60  mov     rax, [rax+20h]
0x180008f64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008f69  test    al, al
0x180008f6b  jz      short loc_180008FE3
0x180008f6d  inc     ebx
0x180008f6f  cmp     ebx, esi
0x180008f71  jb      short loc_180008EF5
0x180008f73  xor     r15d, r15d
0x180008f76  mov     r8, [rdi+20h]; unsigned __int8 *
0x180008f7a  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x180008f7f  lea     rcx, [rbp+10D0h+var_1120]; this
0x180008f83  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180008f88  test    al, al
0x180008f8a  jnz     loc_180008EE3
0x180008f90  mov     rcx, [rbp+10D0h+var_1048]
0x180008f97  test    rcx, rcx
0x180008f9a  jz      short loc_180008FA8
0x180008f9c  mov     rax, [rcx]
0x180008f9f  mov     rax, [rax+18h]
0x180008fa3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008fa8  mov     bl, 1
0x180008faa  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x180008fae  jz      short loc_180009025
0x180008fb0  mov     eax, [rsp+11D0h+var_1188]
0x180008fb4  mov     rdx, [rsp+11D0h+var_1158]
0x180008fb9  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180008fbd  sub     r8d, edx
0x180008fc0  mov     [rsp+11D0h+var_11A0], 1
0x180008fc8  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180008fcc  mov     rcx, r14
0x180008fcf  call    wil_details_NtUpdateWnfStateData
0x180008fd4  cmp     eax, 0C0000001h
0x180008fd9  jnz     short loc_180009003
0x180008fdb  inc     r12
0x180008fde  mov     bl, r15b
0x180008fe1  jmp     short loc_180009031
0x180008fe3  mov     rcx, [rbp+10D0h+var_1048]
0x180008fea  xor     r15d, r15d
0x180008fed  test    rcx, rcx
0x180008ff0  jz      short loc_180008FFE
0x180008ff2  mov     rax, [rcx]
0x180008ff5  mov     rax, [rax+18h]
0x180008ff9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ffe  mov     bl, r15b
0x180009001  jmp     short loc_180008FAA
0x180009003  test    eax, eax
0x180009005  jz      short loc_180009025
0x180009007  mov     rdx, [rsp+11D0h+var_1158]
0x18000900c  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x180009010  sub     r8d, edx
0x180009013  mov     [rsp+11D0h+var_11A0], r15d
0x180009018  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x18000901d  mov     rcx, r14
0x180009020  call    wil_details_NtUpdateWnfStateData
0x180009025  add     r14, 8
0x180009029  mov     rax, [rbp+10D0h+var_1130]
0x18000902d  mov     [rbp+10D0h+var_1128], rax
0x180009031  mov     rsi, [rbp+10D0h+lpMem]
0x180009035  mov     [rbp+10D0h+lpMem], r15
0x180009039  test    rsi, rsi
0x18000903c  jz      short loc_180009052
0x18000903e  call    cs:__imp_GetProcessHeap
0x180009044  mov     rcx, rax; hHeap
0x180009047  mov     r8, rsi; lpMem
0x18000904a  xor     edx, edx; dwFlags
0x18000904c  call    cs:__imp_HeapFree
0x180009052  test    bl, bl
0x180009054  jnz     short loc_180009088
0x180009056  cmp     r14, r13
0x180009059  jnb     short loc_180009088
0x18000905b  cmp     r12, 32h ; '2'
0x18000905f  jb      loc_180008D2A
0x180009065  jmp     short loc_180009088
0x180009067  mov     rbx, [rbp+10D0h+lpMem]
0x18000906b  mov     [rbp+10D0h+lpMem], r15
0x18000906f  test    rbx, rbx
0x180009072  jz      short loc_180009088
0x180009074  call    cs:__imp_GetProcessHeap
0x18000907a  mov     rcx, rax; hHeap
0x18000907d  mov     r8, rbx; lpMem
0x180009080  xor     edx, edx; dwFlags
0x180009082  call    cs:__imp_HeapFree
0x180009088  mov     rcx, [rbp+10D0h+var_40]
0x18000908f  xor     rcx, rsp; StackCookie
0x180009092  call    __security_check_cookie
0x180009097  mov     rbx, [rsp+11D0h+arg_8]
0x18000909f  add     rsp, 11A0h
0x1800090a6  pop     r15
0x1800090a8  pop     r14
0x1800090aa  pop     r13
0x1800090ac  pop     r12
0x1800090ae  pop     rdi
0x1800090af  pop     rsi
0x1800090b0  pop     rbp
0x1800090b1  retn
0x1800090b2  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
