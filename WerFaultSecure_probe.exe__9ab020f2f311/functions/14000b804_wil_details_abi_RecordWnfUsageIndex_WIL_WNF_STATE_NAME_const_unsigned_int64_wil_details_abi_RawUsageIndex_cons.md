# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x14000b804`
- end: `0x14000bbdc`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `984`
- prototype: `void __fastcall(wil::details_abi *__hidden this, const struct __WIL__WNF_STATE_NAME *, unsigned __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x14000af58`

## callees

- `0x1400023d0`
- `0x140006008`
- `0x14000aab4`
- `0x14000ae58`
- `0x14000b804`
- `0x14000c3cc`
- `0x14000e4e8`
- `0x1400112a0`
- `0x140012010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b8fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetProcAddress` at `0x14000b8fb`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b8e4`
- `api-ms-win-core-libraryloader-l1-2-0!GetModuleHandleW` at `0x14000b8e4`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bb62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bb98`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bb62`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x14000bb98`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bb70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bba6`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bb70`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x14000bba6`

## string_xrefs

- `0x14000b8dd`: `ntdll.dll`

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
  wil::details::in1diag4 *v58; // [rsp+188h] [rbp+88h]
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
    v58 = (wil::details::in1diag4 *)v57;
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
            wil::details::in1diag4::_FailFastImmediate_Unexpected(0);
          v27 = &v52;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag4 *, _QWORD *, __int64 *, __int64 *))(*(_QWORD *)v58 + 32LL))(
                  v58,
                  v55,
                  &v54,
                  &v53) )
          {
            if ( v58 )
              (*(void (__fastcall **)(wil::details::in1diag4 *))(*(_QWORD *)v58 + 24LL))(v58);
            v20 = 0;
            goto LABEL_30;
          }
          if ( ++v16 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v58 )
      (*(void (__fastcall **)(wil::details::in1diag4 *))(*(_QWORD *)v58 + 24LL))(v58);
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
0x14000b804  mov     [rsp-8+arg_8], rbx
0x14000b809  push    rbp
0x14000b80a  push    rsi
0x14000b80b  push    rdi
0x14000b80c  push    r12
0x14000b80e  push    r13
0x14000b810  push    r14
0x14000b812  push    r15
0x14000b814  lea     rbp, [rsp-10A0h]
0x14000b81c  mov     eax, 11A0h
0x14000b821  call    _alloca_probe
0x14000b826  sub     rsp, rax
0x14000b829  mov     rax, cs:__security_cookie
0x14000b830  xor     rax, rsp
0x14000b833  mov     [rbp+10D0h+var_40], rax
0x14000b83a  mov     rdi, r8
0x14000b83d  mov     r14, rcx
0x14000b840  lea     r13, [rcx+rdx*8]
0x14000b844  xor     r15d, r15d
0x14000b847  mov     r12d, r15d
0x14000b84a  mov     [rbp+10D0h+var_1128], r15
0x14000b84e  mov     cl, [rdi+8]
0x14000b851  movzx   edx, word ptr [rdi+6]
0x14000b855  movzx   eax, word ptr [rdi]
0x14000b858  mov     [rsp+11D0h+var_1170], ax
0x14000b85d  movzx   eax, word ptr [rdi+2]
0x14000b861  mov     [rsp+11D0h+var_116E], ax
0x14000b866  mov     al, [rdi+4]
0x14000b869  mov     [rsp+11D0h+var_116C], al
0x14000b86d  mov     [rsp+11D0h+var_116A], dx
0x14000b872  mov     [rsp+11D0h+var_1168], cl
0x14000b876  test    dx, dx
0x14000b879  jz      short loc_14000B898
0x14000b87b  mov     eax, edx
0x14000b87d  cmp     cl, 1
0x14000b880  jnz     short loc_14000B888
0x14000b882  add     rax, 2
0x14000b886  jmp     short loc_14000B891
0x14000b888  cmp     cl, 2
0x14000b88b  jnz     short loc_14000B891
0x14000b88d  add     rax, 4
0x14000b891  mov     [rsp+11D0h+var_1160], rax
0x14000b896  jmp     short loc_14000B89D
0x14000b898  mov     [rsp+11D0h+var_1160], r15
0x14000b89d  mov     [rsp+11D0h+var_1158], r15
0x14000b8a2  xorps   xmm0, xmm0
0x14000b8a5  movdqa  [rbp+10D0h+var_1150], xmm0
0x14000b8aa  mov     [rbp+10D0h+lpMem], r15
0x14000b8ae  mov     [rbp+10D0h+var_1138], 0
0x14000b8b4  mov     [rbp+10D0h+var_1136], r15b
0x14000b8b8  mov     [rsp+11D0h+var_1188], r15d
0x14000b8bd  mov     dword ptr [rsp+11D0h+var_1190], 1000h
0x14000b8c5  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x14000b8cc  test    rax, rax
0x14000b8cf  jnz     short loc_14000B914
0x14000b8d1  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b8d8  test    rax, rax
0x14000b8db  jnz     short loc_14000B8F1
0x14000b8dd  lea     rcx, aNtdllDll_1; "ntdll.dll"
0x14000b8e4  call    cs:__imp_GetModuleHandleW
0x14000b8ea  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x14000b8f1  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x14000b8f8  mov     rcx, rax; hModule
0x14000b8fb  call    cs:__imp_GetProcAddress
0x14000b901  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x14000b908  test    rax, rax
0x14000b90b  jnz     short loc_14000B914
0x14000b90d  mov     ebx, 0C0000139h
0x14000b912  jmp     short loc_14000B93E
0x14000b914  lea     rcx, [rsp+11D0h+var_1190]
0x14000b919  mov     [rsp+11D0h+var_11A8], rcx
0x14000b91e  lea     rcx, [rbp+10D0h+var_1040]
0x14000b925  mov     [rsp+11D0h+var_11B0], rcx
0x14000b92a  lea     r9, [rsp+11D0h+var_1188]
0x14000b92f  xor     r8d, r8d
0x14000b932  xor     edx, edx
0x14000b934  mov     rcx, r14
0x14000b937  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000b93c  mov     ebx, eax
0x14000b93e  mov     ecx, ebx; this
0x14000b940  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x14000b945  test    ebx, ebx
0x14000b947  jz      short loc_14000B957
0x14000b949  mov     eax, r15d
0x14000b94c  mov     dword ptr [rsp+11D0h+var_1190], eax
0x14000b950  mov     [rsp+11D0h+var_1188], r15d
0x14000b955  jmp     short loc_14000B95B
0x14000b957  mov     eax, dword ptr [rsp+11D0h+var_1190]
0x14000b95b  mov     r8d, eax; unsigned __int64
0x14000b95e  mov     r9d, 1000h; unsigned __int64
0x14000b964  lea     rdx, [rbp+10D0h+var_1040]; void *
0x14000b96b  lea     rcx, [rsp+11D0h+var_1170]; this
0x14000b970  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x14000b975  cmp     byte ptr [rbp+10D0h+var_1138+1], r15b
0x14000b979  jnz     loc_14000BB8B
0x14000b97f  mov     [rbp+10D0h+var_1130], r15
0x14000b983  lea     rax, ??_7?$__func@V_lambda_8db0ce862824541f40dfb767113f1e28_@@$$A6A_NPEAX_K01I@Z@__function@wistd@@6B@; const wistd::__function::__func<_lambda_8db0ce862824541f40dfb767113f1e28_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x14000b98a  mov     [rbp+10D0h+var_10B0], rax
0x14000b98e  lea     rax, [rbp+10D0h+var_1130]
0x14000b992  mov     [rbp+10D0h+var_10A8], rax
0x14000b996  lea     rax, [rbp+10D0h+var_1128]
0x14000b99a  mov     [rbp+10D0h+var_10A0], rax
0x14000b99e  lea     rax, [rsp+11D0h+var_1170]
0x14000b9a3  mov     [rbp+10D0h+var_1098], rax
0x14000b9a7  lea     rax, [rbp+10D0h+var_10B0]
0x14000b9ab  mov     [rbp+10D0h+var_1048], rax
0x14000b9b2  lea     rax, [rbp+10D0h+var_10B8]
0x14000b9b6  mov     [rbp+10D0h+var_10C0], rax
0x14000b9ba  mov     rax, [rdi+18h]
0x14000b9be  add     rax, 0Ah
0x14000b9c2  mov     [rsp+11D0h+var_1190], rax
0x14000b9c7  movzx   eax, word ptr [rdi+2]
0x14000b9cb  mov     [rbp+10D0h+var_1120], ax
0x14000b9cf  mov     al, [rdi+4]
0x14000b9d2  mov     [rbp+10D0h+var_111E], al
0x14000b9d5  mov     [rbp+10D0h+var_111C], r15d
0x14000b9d9  mov     [rbp+10D0h+var_1118], r15w
0x14000b9de  xorps   xmm0, xmm0
0x14000b9e1  movdqu  [rbp+10D0h+var_1110], xmm0
0x14000b9e6  movzx   eax, word ptr [rdi+6]
0x14000b9ea  mov     [rbp+10D0h+var_1100], ax
0x14000b9ee  mov     al, [rdi+8]
0x14000b9f1  mov     [rbp+10D0h+var_10FE], al
0x14000b9f4  mov     [rbp+10D0h+var_10FC], r15d
0x14000b9f8  mov     [rbp+10D0h+var_10F8], r15w
0x14000b9fd  movdqu  [rbp+10D0h+var_10F0], xmm0
0x14000ba02  jmp     loc_14000BA9A
0x14000ba07  mov     ebx, r15d
0x14000ba0a  mov     esi, [rbp+10D0h+var_111C]
0x14000ba0d  test    esi, esi
0x14000ba0f  jz      loc_14000BA9A
0x14000ba15  mov     r15, qword ptr [rbp+10D0h+var_1110+8]
0x14000ba19  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000ba1d  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000ba22  lea     rcx, [rbp+10D0h+var_1100]; this
0x14000ba26  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000ba2b  test    al, al
0x14000ba2d  jz      short loc_14000BA97
0x14000ba2f  mov     eax, [rbp+10D0h+var_10FC]
0x14000ba32  mov     [rsp+11D0h+var_1180], eax
0x14000ba36  movzx   eax, [rbp+10D0h+var_10F8]
0x14000ba3a  mov     [rbp+10D0h+var_10E0], rax
0x14000ba3e  mov     rax, qword ptr [rbp+10D0h+var_10F0+8]
0x14000ba42  mov     [rbp+10D0h+var_10D8], rax
0x14000ba46  movzx   eax, [rbp+10D0h+var_1118]
0x14000ba4a  mov     [rbp+10D0h+var_10D0], rax
0x14000ba4e  mov     [rbp+10D0h+var_10C8], r15
0x14000ba52  mov     rcx, [rbp+10D0h+var_1048]; this
0x14000ba59  test    rcx, rcx
0x14000ba5c  jz      loc_14000BBD6
0x14000ba62  mov     rax, [rcx]
0x14000ba65  lea     rdx, [rsp+11D0h+var_1180]
0x14000ba6a  mov     [rsp+11D0h+var_11A8], rdx
0x14000ba6f  lea     rdx, [rbp+10D0h+var_10E0]
0x14000ba73  mov     [rsp+11D0h+var_11B0], rdx
0x14000ba78  lea     r9, [rbp+10D0h+var_10D8]
0x14000ba7c  lea     r8, [rbp+10D0h+var_10D0]
0x14000ba80  lea     rdx, [rbp+10D0h+var_10C8]
0x14000ba84  mov     rax, [rax+20h]
0x14000ba88  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000ba8d  test    al, al
0x14000ba8f  jz      short loc_14000BB07
0x14000ba91  inc     ebx
0x14000ba93  cmp     ebx, esi
0x14000ba95  jb      short loc_14000BA19
0x14000ba97  xor     r15d, r15d
0x14000ba9a  mov     r8, [rdi+20h]; unsigned __int8 *
0x14000ba9e  lea     rdx, [rsp+11D0h+var_1190]; unsigned __int8 **
0x14000baa3  lea     rcx, [rbp+10D0h+var_1120]; this
0x14000baa7  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x14000baac  test    al, al
0x14000baae  jnz     loc_14000BA07
0x14000bab4  mov     rcx, [rbp+10D0h+var_1048]
0x14000babb  test    rcx, rcx
0x14000babe  jz      short loc_14000BACC
0x14000bac0  mov     rax, [rcx]
0x14000bac3  mov     rax, [rax+18h]
0x14000bac7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bacc  mov     bl, 1
0x14000bace  cmp     byte ptr [rbp+10D0h+var_1138], r15b
0x14000bad2  jz      short loc_14000BB49
0x14000bad4  mov     eax, [rsp+11D0h+var_1188]
0x14000bad8  mov     rdx, [rsp+11D0h+var_1158]
0x14000badd  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000bae1  sub     r8d, edx
0x14000bae4  mov     [rsp+11D0h+var_11A0], 1
0x14000baec  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x14000baf0  mov     rcx, r14
0x14000baf3  call    wil_details_NtUpdateWnfStateData
0x14000baf8  cmp     eax, 0C0000001h
0x14000bafd  jnz     short loc_14000BB27
0x14000baff  inc     r12
0x14000bb02  mov     bl, r15b
0x14000bb05  jmp     short loc_14000BB55
0x14000bb07  mov     rcx, [rbp+10D0h+var_1048]
0x14000bb0e  xor     r15d, r15d
0x14000bb11  test    rcx, rcx
0x14000bb14  jz      short loc_14000BB22
0x14000bb16  mov     rax, [rcx]
0x14000bb19  mov     rax, [rax+18h]
0x14000bb1d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000bb22  mov     bl, r15b
0x14000bb25  jmp     short loc_14000BACE
0x14000bb27  test    eax, eax
0x14000bb29  jz      short loc_14000BB49
0x14000bb2b  mov     rdx, [rsp+11D0h+var_1158]
0x14000bb30  mov     r8d, dword ptr [rbp+10D0h+var_1150]
0x14000bb34  sub     r8d, edx
0x14000bb37  mov     [rsp+11D0h+var_11A0], r15d
0x14000bb3c  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x14000bb41  mov     rcx, r14
0x14000bb44  call    wil_details_NtUpdateWnfStateData
0x14000bb49  add     r14, 8
0x14000bb4d  mov     rax, [rbp+10D0h+var_1130]
0x14000bb51  mov     [rbp+10D0h+var_1128], rax
0x14000bb55  mov     rsi, [rbp+10D0h+lpMem]
0x14000bb59  mov     [rbp+10D0h+lpMem], r15
0x14000bb5d  test    rsi, rsi
0x14000bb60  jz      short loc_14000BB76
0x14000bb62  call    cs:__imp_GetProcessHeap
0x14000bb68  mov     rcx, rax; hHeap
0x14000bb6b  mov     r8, rsi; lpMem
0x14000bb6e  xor     edx, edx; dwFlags
0x14000bb70  call    cs:__imp_HeapFree
0x14000bb76  test    bl, bl
0x14000bb78  jnz     short loc_14000BBAC
0x14000bb7a  cmp     r14, r13
0x14000bb7d  jnb     short loc_14000BBAC
0x14000bb7f  cmp     r12, 32h ; '2'
0x14000bb83  jb      loc_14000B84E
0x14000bb89  jmp     short loc_14000BBAC
0x14000bb8b  mov     rbx, [rbp+10D0h+lpMem]
0x14000bb8f  mov     [rbp+10D0h+lpMem], r15
0x14000bb93  test    rbx, rbx
0x14000bb96  jz      short loc_14000BBAC
0x14000bb98  call    cs:__imp_GetProcessHeap
0x14000bb9e  mov     rcx, rax; hHeap
0x14000bba1  mov     r8, rbx; lpMem
0x14000bba4  xor     edx, edx; dwFlags
0x14000bba6  call    cs:__imp_HeapFree
0x14000bbac  mov     rcx, [rbp+10D0h+var_40]
0x14000bbb3  xor     rcx, rsp; StackCookie
0x14000bbb6  call    __security_check_cookie
0x14000bbbb  mov     rbx, [rsp+11D0h+arg_8]
0x14000bbc3  add     rsp, 11A0h
0x14000bbca  pop     r15
0x14000bbcc  pop     r14
0x14000bbce  pop     r13
0x14000bbd0  pop     r12
0x14000bbd2  pop     rdi
0x14000bbd3  pop     rsi
0x14000bbd4  pop     rbp
0x14000bbd5  retn
0x14000bbd6  call    ?_FailFastImmediate_Unexpected@in1diag4@details@wil@@YAXXZ; wil::details::in1diag4::_FailFastImmediate_Unexpected(void)
```
