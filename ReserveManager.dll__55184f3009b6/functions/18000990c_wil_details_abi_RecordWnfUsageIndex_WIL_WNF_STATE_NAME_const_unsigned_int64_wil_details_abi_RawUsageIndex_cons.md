# wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)

- ea: `0x18000990c`
- end: `0x180009ced`
- name: `?RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@12@@Z`
- size: `993`
- prototype: `void __fastcall(wil::details_abi *this, const struct __WIL__WNF_STATE_NAME *, __int64, const struct wil::details_abi::RawUsageIndex *)`
- caller_count: `1`
- callee_count: `9`
- tags: `loader_planting, installer_update`

## callers

- `0x180008d40`

## callees

- `0x180003870`
- `0x18000871c`
- `0x180008be4`
- `0x18000990c`
- `0x18000a430`
- `0x18000bf6c`
- `0x18000d0b0`
- `0x180031b80`
- `0x180033010`

## import_xrefs

- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800099ee`
- `api-ms-win-core-libraryloader-l1-1-0!GetModuleHandleW` at `0x1800099ee`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009a05`
- `api-ms-win-core-libraryloader-l1-1-0!GetProcAddress` at `0x180009a05`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ca9`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009c73`
- `api-ms-win-core-heap-l1-1-0!GetProcessHeap` at `0x180009ca9`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009cb7`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009c81`
- `api-ms-win-core-heap-l1-1-0!HeapFree` at `0x180009cb7`

## string_xrefs

- `0x1800099e7`: `ntdll.dll`

## pseudocode

```c
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
  int v19; // r9d
  char v20; // bl
  int updated; // eax
  int v22; // r9d
  void *v23; // rsi
  HANDLE ProcessHeap; // rax
  void *v25; // rbx
  HANDLE v26; // rax
  __int64 *v27; // [rsp+20h] [rbp-E0h]
  __int16 v28; // [rsp+40h] [rbp-C0h] BYREF
  char v29; // [rsp+42h] [rbp-BEh]
  unsigned int v30; // [rsp+44h] [rbp-BCh]
  unsigned __int16 v31; // [rsp+48h] [rbp-B8h]
  __int128 v32; // [rsp+50h] [rbp-B0h]
  __int16 v33; // [rsp+60h] [rbp-A0h] BYREF
  char v34; // [rsp+62h] [rbp-9Eh]
  int v35; // [rsp+64h] [rbp-9Ch]
  unsigned __int16 v36; // [rsp+68h] [rbp-98h]
  __int128 v37; // [rsp+70h] [rbp-90h]
  __int64 v38; // [rsp+80h] [rbp-80h]
  char *v39; // [rsp+88h] [rbp-78h]
  char v40; // [rsp+90h] [rbp-70h] BYREF
  _QWORD v41[13]; // [rsp+98h] [rbp-68h] BYREF
  wil::details::in1diag3 *v42; // [rsp+100h] [rbp+0h]
  __int64 v43; // [rsp+108h] [rbp+8h] BYREF
  __int64 v44; // [rsp+110h] [rbp+10h] BYREF
  unsigned __int8 *v45; // [rsp+118h] [rbp+18h] BYREF
  _DWORD v46[4]; // [rsp+120h] [rbp+20h] BYREF
  _WORD v47[2]; // [rsp+130h] [rbp+30h] BYREF
  char v48; // [rsp+134h] [rbp+34h]
  __int16 v49; // [rsp+136h] [rbp+36h]
  char v50; // [rsp+138h] [rbp+38h]
  __int64 v51; // [rsp+140h] [rbp+40h]
  __int64 v52; // [rsp+148h] [rbp+48h]
  __int128 v53; // [rsp+150h] [rbp+50h]
  LPVOID lpMem; // [rsp+160h] [rbp+60h]
  __int16 v55; // [rsp+168h] [rbp+68h]
  char v56; // [rsp+16Ah] [rbp+6Ah]
  __int64 v57; // [rsp+170h] [rbp+70h] BYREF
  __int64 v58; // [rsp+178h] [rbp+78h] BYREF
  __int64 v59; // [rsp+180h] [rbp+80h] BYREF
  __int64 v60; // [rsp+188h] [rbp+88h] BYREF
  _BYTE v61[4096]; // [rsp+190h] [rbp+90h] BYREF

  v38 = -2;
  v5 = this;
  v6 = (wil::details_abi *)((char *)this + 8 * (_QWORD)a2);
  v7 = 0;
  v58 = 0;
  while ( 1 )
  {
    v8 = *(_BYTE *)(a3 + 8);
    v9 = *(unsigned __int16 *)(a3 + 6);
    v47[0] = *(_WORD *)a3;
    v47[1] = *(_WORD *)(a3 + 2);
    v48 = *(_BYTE *)(a3 + 4);
    v49 = v9;
    v50 = v8;
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
      v51 = v10;
    }
    else
    {
      v51 = 0;
    }
    v52 = 0;
    v53 = 0;
    lpMem = 0;
    v55 = 0;
    v56 = 0;
    v46[0] = 0;
    LODWORD(v45) = 4096;
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
      v27 = (__int64 *)v61;
      v14 = ((__int64 (__fastcall *)(wil::details_abi *, _QWORD, _QWORD, _DWORD *))ProcAddress)(v5, 0, 0, v46);
    }
    else
    {
      v14 = -1073741511;
    }
    wil::details::NtStatusToHr((wil::details *)v14, v13);
    if ( v14 )
    {
      v15 = 0;
      LODWORD(v45) = 0;
      v46[0] = 0;
    }
    else
    {
      v15 = (unsigned int)v45;
    }
    wil::details_abi::RawUsageIndex::SetBuffer((wil::details_abi::RawUsageIndex *)v47, v61, v15, 0x1000u);
    if ( HIBYTE(v55) )
      break;
    v57 = 0;
    v41[0] = wistd::__function::Z::$$A6A_NPEAX131I::Z::__func<`wil::details_abi::RecordWnfUsageIndex'::`4'::_lambda_1_,AXPEBU__WIL__WNF_STATE_NAME,unsigned __int64,wil::details_abi::RawUsageIndex const &>::`vftable';
    v41[1] = &v57;
    v41[2] = &v58;
    v41[3] = v47;
    v42 = (wil::details::in1diag3 *)v41;
    v39 = &v40;
    v45 = (unsigned __int8 *)(*(_QWORD *)(a3 + 24) + 10LL);
    v28 = *(_WORD *)(a3 + 2);
    v29 = *(_BYTE *)(a3 + 4);
    v30 = 0;
    v31 = 0;
    v32 = 0;
    v33 = *(_WORD *)(a3 + 6);
    v34 = *(_BYTE *)(a3 + 8);
    v35 = 0;
    v36 = 0;
    v37 = 0;
LABEL_26:
    while ( wil::details_abi::UsageIndexProperty::Read(
              (wil::details_abi::UsageIndexProperty *)&v28,
              &v45,
              *(unsigned __int8 **)(a3 + 32)) )
    {
      v16 = 0;
      v17 = v30;
      if ( v30 )
      {
        v18 = *((_QWORD *)&v32 + 1);
        while ( wil::details_abi::UsageIndexProperty::Read(
                  (wil::details_abi::UsageIndexProperty *)&v33,
                  &v45,
                  *(unsigned __int8 **)(a3 + 32)) )
        {
          v46[2] = v35;
          v59 = v36;
          v43 = *((_QWORD *)&v37 + 1);
          v60 = v31;
          v44 = v18;
          if ( !v42 )
            wil::details::in1diag3::_FailFastImmediate_Unexpected(0);
          v27 = &v59;
          if ( !(*(unsigned __int8 (__fastcall **)(wil::details::in1diag3 *, __int64 *, __int64 *, __int64 *))(*(_QWORD *)v42 + 32LL))(
                  v42,
                  &v44,
                  &v60,
                  &v43) )
          {
            if ( v42 )
              (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v42 + 24LL))(v42);
            v20 = 0;
            goto LABEL_30;
          }
          if ( ++v16 >= v17 )
            goto LABEL_26;
        }
      }
    }
    if ( v42 )
      (*(void (__fastcall **)(wil::details::in1diag3 *))(*(_QWORD *)v42 + 24LL))(v42);
    v20 = 1;
LABEL_30:
    if ( !(_BYTE)v55 )
      goto LABEL_38;
    updated = wil_details_NtUpdateWnfStateData((_DWORD)v5, v52, (int)v53 - (int)v52, v19, (_DWORD)v27, v46[0], 1);
    if ( updated != -1073741823 )
    {
      if ( updated )
        wil_details_NtUpdateWnfStateData((_DWORD)v5, v52, v53 - v52, v22, (_DWORD)v27, 0, 0);
LABEL_38:
      v5 = (wil::details_abi *)((char *)v5 + 8);
      v58 = v57;
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
0x18000990c  push    rbp
0x18000990e  push    rsi
0x18000990f  push    rdi
0x180009910  push    r12
0x180009912  push    r13
0x180009914  push    r14
0x180009916  push    r15
0x180009918  lea     rbp, [rsp-10A0h]
0x180009920  mov     eax, 11A0h
0x180009925  call    _alloca_probe
0x18000992a  sub     rsp, rax
0x18000992d  mov     [rbp+10D0h+var_1150], 0FFFFFFFFFFFFFFFEh
0x180009935  mov     [rsp+11D0h+arg_8], rbx
0x18000993d  mov     rax, cs:__security_cookie
0x180009944  xor     rax, rsp
0x180009947  mov     [rbp+10D0h+var_40], rax
0x18000994e  mov     rdi, r8
0x180009951  mov     r14, rcx
0x180009954  lea     r13, [rcx+rdx*8]
0x180009958  xor     r15d, r15d
0x18000995b  mov     r12d, r15d
0x18000995e  mov     [rbp+10D0h+var_1058], r15
0x180009962  mov     cl, [rdi+8]
0x180009965  movzx   edx, word ptr [rdi+6]
0x180009969  movzx   eax, word ptr [rdi]
0x18000996c  mov     [rbp+10D0h+var_10A0], ax
0x180009970  movzx   eax, word ptr [rdi+2]
0x180009974  mov     [rbp+10D0h+var_109E], ax
0x180009978  mov     al, [rdi+4]
0x18000997b  mov     [rbp+10D0h+var_109C], al
0x18000997e  mov     [rbp+10D0h+var_109A], dx
0x180009982  mov     [rbp+10D0h+var_1098], cl
0x180009985  test    dx, dx
0x180009988  jz      short loc_1800099A6
0x18000998a  mov     eax, edx
0x18000998c  cmp     cl, 1
0x18000998f  jnz     short loc_180009997
0x180009991  add     rax, 2
0x180009995  jmp     short loc_1800099A0
0x180009997  cmp     cl, 2
0x18000999a  jnz     short loc_1800099A0
0x18000999c  add     rax, 4
0x1800099a0  mov     [rbp+10D0h+var_1090], rax
0x1800099a4  jmp     short loc_1800099AA
0x1800099a6  mov     [rbp+10D0h+var_1090], r15
0x1800099aa  mov     [rbp+10D0h+var_1088], r15
0x1800099ae  xorps   xmm0, xmm0
0x1800099b1  movdqa  [rbp+10D0h+var_1080], xmm0
0x1800099b6  mov     [rbp+10D0h+lpMem], r15
0x1800099ba  mov     [rbp+10D0h+var_1068], 0
0x1800099c0  mov     [rbp+10D0h+var_1066], r15b
0x1800099c4  mov     [rbp+10D0h+var_10B0], r15d
0x1800099c8  mov     dword ptr [rbp+10D0h+var_10B8], 1000h
0x1800099cf  mov     rax, cs:g_wil_details_pfnNtQueryWnfStateData
0x1800099d6  test    rax, rax
0x1800099d9  jnz     short loc_180009A1E
0x1800099db  mov     rax, cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800099e2  test    rax, rax
0x1800099e5  jnz     short loc_1800099FB
0x1800099e7  lea     rcx, aNtdllDll_0; "ntdll.dll"
0x1800099ee  call    cs:__imp_GetModuleHandleW
0x1800099f4  mov     cs:?wil_details_ntdllModuleHandle@?1??wil_details_GetNtDllModuleHandle@@YAPEAUHINSTANCE__@@XZ@4PEAU2@EA, rax; HINSTANCE__ * `wil_details_GetNtDllModuleHandle(void)'::`2'::wil_details_ntdllModuleHandle
0x1800099fb  lea     rdx, aNtquerywnfstat; "NtQueryWnfStateData"
0x180009a02  mov     rcx, rax; hModule
0x180009a05  call    cs:__imp_GetProcAddress
0x180009a0b  mov     cs:g_wil_details_pfnNtQueryWnfStateData, rax
0x180009a12  test    rax, rax
0x180009a15  jnz     short loc_180009A1E
0x180009a17  mov     ebx, 0C0000139h
0x180009a1c  jmp     short loc_180009A46
0x180009a1e  lea     rcx, [rbp+10D0h+var_10B8]
0x180009a22  mov     [rsp+11D0h+var_11A8], rcx
0x180009a27  lea     rcx, [rbp+10D0h+var_1040]
0x180009a2e  mov     [rsp+11D0h+var_11B0], rcx
0x180009a33  lea     r9, [rbp+10D0h+var_10B0]
0x180009a37  xor     r8d, r8d
0x180009a3a  xor     edx, edx
0x180009a3c  mov     rcx, r14
0x180009a3f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a44  mov     ebx, eax
0x180009a46  mov     ecx, ebx; this
0x180009a48  call    ?NtStatusToHr@details@wil@@YAJJ@Z; wil::details::NtStatusToHr(long)
0x180009a4d  test    ebx, ebx
0x180009a4f  jz      short loc_180009A5D
0x180009a51  mov     eax, r15d
0x180009a54  mov     dword ptr [rbp+10D0h+var_10B8], eax
0x180009a57  mov     [rbp+10D0h+var_10B0], r15d
0x180009a5b  jmp     short loc_180009A60
0x180009a5d  mov     eax, dword ptr [rbp+10D0h+var_10B8]
0x180009a60  mov     r8d, eax; unsigned __int64
0x180009a63  mov     r9d, 1000h; unsigned __int64
0x180009a69  lea     rdx, [rbp+10D0h+var_1040]; void *
0x180009a70  lea     rcx, [rbp+10D0h+var_10A0]; this
0x180009a74  call    ?SetBuffer@RawUsageIndex@details_abi@wil@@QEAAXPEAX_K1@Z; wil::details_abi::RawUsageIndex::SetBuffer(void *,unsigned __int64,unsigned __int64)
0x180009a79  cmp     byte ptr [rbp+10D0h+var_1068+1], r15b
0x180009a7d  jnz     loc_180009C9C
0x180009a83  mov     [rbp+10D0h+var_1060], r15
0x180009a87  lea     rax, ??_7?$__func@V_lambda_1_@?3??RecordWnfUsageIndex@details_abi@wil@@YAXPEBU__WIL__WNF_STATE_NAME@@_KAEBVRawUsageIndex@34@@Z@$$A6A_NPEAX131I@Z@__function@wistd@@6B@; const wistd::__function::__func<`wil::details_abi::RecordWnfUsageIndex(__WIL__WNF_STATE_NAME const *,unsigned __int64,wil::details_abi::RawUsageIndex const &)'::`4'::_lambda_1_,bool (void *,unsigned __int64,void *,unsigned __int64,uint)>::`vftable'
0x180009a8e  mov     [rbp+10D0h+var_1138], rax
0x180009a92  lea     rax, [rbp+10D0h+var_1060]
0x180009a96  mov     [rbp+10D0h+var_1130], rax
0x180009a9a  lea     rax, [rbp+10D0h+var_1058]
0x180009a9e  mov     [rbp+10D0h+var_1128], rax
0x180009aa2  lea     rax, [rbp+10D0h+var_10A0]
0x180009aa6  mov     [rbp+10D0h+var_1120], rax
0x180009aaa  lea     rax, [rbp+10D0h+var_1138]
0x180009aae  mov     [rbp+10D0h+var_10D0], rax
0x180009ab2  lea     rax, [rbp+10D0h+var_1140]
0x180009ab6  mov     [rbp+10D0h+var_1148], rax
0x180009aba  mov     rax, [rdi+18h]
0x180009abe  add     rax, 0Ah
0x180009ac2  mov     [rbp+10D0h+var_10B8], rax
0x180009ac6  movzx   eax, word ptr [rdi+2]
0x180009aca  mov     [rsp+11D0h+var_1190], ax
0x180009acf  mov     al, [rdi+4]
0x180009ad2  mov     [rsp+11D0h+var_118E], al
0x180009ad6  mov     [rsp+11D0h+var_118C], r15d
0x180009adb  mov     [rsp+11D0h+var_1188], r15w
0x180009ae1  xorps   xmm0, xmm0
0x180009ae4  movdqu  [rsp+11D0h+var_1180], xmm0
0x180009aea  movzx   eax, word ptr [rdi+6]
0x180009aee  mov     [rsp+11D0h+var_1170], ax
0x180009af3  mov     al, [rdi+8]
0x180009af6  mov     [rsp+11D0h+var_116E], al
0x180009afa  mov     [rsp+11D0h+var_116C], r15d
0x180009aff  mov     [rsp+11D0h+var_1168], r15w
0x180009b05  movdqu  [rsp+11D0h+var_1160], xmm0
0x180009b0b  jmp     loc_180009BB4
0x180009b10  mov     ebx, r15d
0x180009b13  mov     esi, [rsp+11D0h+var_118C]
0x180009b17  test    esi, esi
0x180009b19  jz      loc_180009BB4
0x180009b1f  mov     r15, qword ptr [rsp+11D0h+var_1180+8]
0x180009b24  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009b28  lea     rdx, [rbp+10D0h+var_10B8]; unsigned __int8 **
0x180009b2c  lea     rcx, [rsp+11D0h+var_1170]; this
0x180009b31  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009b36  test    al, al
0x180009b38  jz      short loc_180009BB1
0x180009b3a  mov     eax, [rsp+11D0h+var_116C]
0x180009b3e  mov     [rbp+10D0h+var_10A8], eax
0x180009b41  movzx   eax, [rsp+11D0h+var_1168]
0x180009b46  mov     [rbp+10D0h+var_1050], rax
0x180009b4d  mov     rax, qword ptr [rsp+11D0h+var_1160+8]
0x180009b52  mov     [rbp+10D0h+var_10C8], rax
0x180009b56  movzx   eax, [rsp+11D0h+var_1188]
0x180009b5b  mov     [rbp+10D0h+var_1048], rax
0x180009b62  mov     [rbp+10D0h+var_10C0], r15
0x180009b66  mov     rcx, [rbp+10D0h+var_10D0]; this
0x180009b6a  test    rcx, rcx
0x180009b6d  jz      loc_180009CE7
0x180009b73  mov     rax, [rcx]
0x180009b76  lea     rdx, [rbp+10D0h+var_10A8]
0x180009b7a  mov     [rsp+11D0h+var_11A8], rdx
0x180009b7f  lea     rdx, [rbp+10D0h+var_1050]
0x180009b86  mov     [rsp+11D0h+var_11B0], rdx
0x180009b8b  lea     r9, [rbp+10D0h+var_10C8]
0x180009b8f  lea     r8, [rbp+10D0h+var_1048]
0x180009b96  lea     rdx, [rbp+10D0h+var_10C0]
0x180009b9a  mov     rax, [rax+20h]
0x180009b9e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ba3  test    al, al
0x180009ba5  jz      short loc_180009C1C
0x180009ba7  inc     ebx
0x180009ba9  cmp     ebx, esi
0x180009bab  jb      loc_180009B24
0x180009bb1  xor     r15d, r15d
0x180009bb4  mov     r8, [rdi+20h]; unsigned __int8 *
0x180009bb8  lea     rdx, [rbp+10D0h+var_10B8]; unsigned __int8 **
0x180009bbc  lea     rcx, [rsp+11D0h+var_1190]; this
0x180009bc1  call    ?Read@UsageIndexProperty@details_abi@wil@@QEAA_NAEAPEAEPEAE@Z; wil::details_abi::UsageIndexProperty::Read(uchar * &,uchar *)
0x180009bc6  test    al, al
0x180009bc8  jnz     loc_180009B10
0x180009bce  mov     rcx, [rbp+10D0h+var_10D0]
0x180009bd2  test    rcx, rcx
0x180009bd5  jz      short loc_180009BE3
0x180009bd7  mov     rax, [rcx]
0x180009bda  mov     rax, [rax+18h]
0x180009bde  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009be3  mov     bl, 1
0x180009be5  cmp     byte ptr [rbp+10D0h+var_1068], r15b
0x180009be9  jz      short loc_180009C5A
0x180009beb  mov     eax, [rbp+10D0h+var_10B0]
0x180009bee  mov     rdx, [rbp+10D0h+var_1088]
0x180009bf2  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x180009bf6  sub     r8d, edx
0x180009bf9  mov     [rsp+11D0h+var_11A0], 1
0x180009c01  mov     dword ptr [rsp+11D0h+var_11A8], eax
0x180009c05  mov     rcx, r14
0x180009c08  call    wil_details_NtUpdateWnfStateData
0x180009c0d  cmp     eax, 0C0000001h
0x180009c12  jnz     short loc_180009C39
0x180009c14  inc     r12
0x180009c17  mov     bl, r15b
0x180009c1a  jmp     short loc_180009C66
0x180009c1c  mov     rcx, [rbp+10D0h+var_10D0]
0x180009c20  xor     r15d, r15d
0x180009c23  test    rcx, rcx
0x180009c26  jz      short loc_180009C34
0x180009c28  mov     rax, [rcx]
0x180009c2b  mov     rax, [rax+18h]
0x180009c2f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009c34  mov     bl, r15b
0x180009c37  jmp     short loc_180009BE5
0x180009c39  test    eax, eax
0x180009c3b  jz      short loc_180009C5A
0x180009c3d  mov     rdx, [rbp+10D0h+var_1088]
0x180009c41  mov     r8d, dword ptr [rbp+10D0h+var_1080]
0x180009c45  sub     r8d, edx
0x180009c48  mov     [rsp+11D0h+var_11A0], r15d
0x180009c4d  mov     dword ptr [rsp+11D0h+var_11A8], r15d
0x180009c52  mov     rcx, r14
0x180009c55  call    wil_details_NtUpdateWnfStateData
0x180009c5a  add     r14, 8
0x180009c5e  mov     rax, [rbp+10D0h+var_1060]
0x180009c62  mov     [rbp+10D0h+var_1058], rax
0x180009c66  mov     rsi, [rbp+10D0h+lpMem]
0x180009c6a  mov     [rbp+10D0h+lpMem], r15
0x180009c6e  test    rsi, rsi
0x180009c71  jz      short loc_180009C87
0x180009c73  call    cs:__imp_GetProcessHeap
0x180009c79  mov     rcx, rax; hHeap
0x180009c7c  mov     r8, rsi; lpMem
0x180009c7f  xor     edx, edx; dwFlags
0x180009c81  call    cs:__imp_HeapFree
0x180009c87  test    bl, bl
0x180009c89  jnz     short loc_180009CBD
0x180009c8b  cmp     r14, r13
0x180009c8e  jnb     short loc_180009CBD
0x180009c90  cmp     r12, 32h ; '2'
0x180009c94  jb      loc_180009962
0x180009c9a  jmp     short loc_180009CBD
0x180009c9c  mov     rbx, [rbp+10D0h+lpMem]
0x180009ca0  mov     [rbp+10D0h+lpMem], r15
0x180009ca4  test    rbx, rbx
0x180009ca7  jz      short loc_180009CBD
0x180009ca9  call    cs:__imp_GetProcessHeap
0x180009caf  mov     rcx, rax; hHeap
0x180009cb2  mov     r8, rbx; lpMem
0x180009cb5  xor     edx, edx; dwFlags
0x180009cb7  call    cs:__imp_HeapFree
0x180009cbd  mov     rcx, [rbp+10D0h+var_40]
0x180009cc4  xor     rcx, rsp; StackCookie
0x180009cc7  call    __security_check_cookie
0x180009ccc  mov     rbx, [rsp+11D0h+arg_8]
0x180009cd4  add     rsp, 11A0h
0x180009cdb  pop     r15
0x180009cdd  pop     r14
0x180009cdf  pop     r13
0x180009ce1  pop     r12
0x180009ce3  pop     rdi
0x180009ce4  pop     rsi
0x180009ce5  pop     rbp
0x180009ce6  retn
0x180009ce7  call    ?_FailFastImmediate_Unexpected@in1diag3@details@wil@@YAXXZ; wil::details::in1diag3::_FailFastImmediate_Unexpected(void)
```
