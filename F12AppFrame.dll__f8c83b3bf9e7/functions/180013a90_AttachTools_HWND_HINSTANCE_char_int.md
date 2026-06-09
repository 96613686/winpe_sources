# AttachTools(HWND__ *,HINSTANCE__ *,char *,int)

- ea: `0x180013a90`
- end: `0x180013dbc`
- name: `?AttachTools@@YAXPEAUHWND__@@PEAUHINSTANCE__@@PEADH@Z`
- size: `812`
- prototype: `void __fastcall(HWND, HINSTANCE, char *)`
- caller_count: `0`
- callee_count: `13`
- tags: `registry_config, broker_com_uri`

## callees

- `0x18000193c`
- `0x180002b60`
- `0x180002d44`
- `0x180002dd4`
- `0x1800030dc`
- `0x180003420`
- `0x180003880`
- `0x1800124e4`
- `0x180013a90`
- `0x180014740`
- `0x1800152b0`
- `0x180030808`
- `0x180035010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180013c36`
- `api-ms-win-crt-private-l1-1-0!_o__wtoi` at `0x180013c36`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180013c4c`
- `api-ms-win-crt-private-l1-1-0!_o_wcstol` at `0x180013c4c`
- `KERNEL32!LocalFree` at `0x180013bdd`
- `KERNEL32!LocalFree` at `0x180013bdd`
- `ole32!CoInitializeEx` at `0x180013c5c`
- `ole32!CoInitializeEx` at `0x180013c5c`
- `SHELL32!CommandLineToArgvW` at `0x180013b4c`
- `SHELL32!CommandLineToArgvW` at `0x180013b4c`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x180013ce5`
- `iertutil!__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z` at `0x180013ce5`

## pseudocode

```c
void __fastcall AttachTools(HWND a1, HINSTANCE a2, char *a3)
{
  BPT *v4; // r15
  LPCWSTR v5; // rdi
  LPWSTR *v6; // rbx
  int i; // r14d
  _QWORD *v8; // rdx
  DWORD v9; // edi
  HWND v10; // r14
  void *v11; // rbx
  __int64 v12; // rdx
  char v13; // [rsp+20h] [rbp-39h] BYREF
  int pNumArgs; // [rsp+28h] [rbp-31h] BYREF
  HRESULT v15; // [rsp+2Ch] [rbp-2Dh] BYREF
  BPT *v16; // [rsp+30h] [rbp-29h] BYREF
  __int128 v17; // [rsp+38h] [rbp-21h] BYREF
  __int64 v18; // [rsp+48h] [rbp-11h]
  LPCWSTR lpCmdLine; // [rsp+50h] [rbp-9h] BYREF
  __int64 v20; // [rsp+58h] [rbp-1h] BYREF
  HRESULT *v21; // [rsp+60h] [rbp+7h]
  char *v22; // [rsp+68h] [rbp+Fh]
  char v23; // [rsp+70h] [rbp+17h]

  pNumArgs = 0;
  v17 = 0;
  v18 = 0;
  v16 = (BPT *)(((__int64 (__fastcall *)(void ***, HINSTANCE))ATL::g_strmgr[3])(&ATL::g_strmgr, a2) + 24);
  if ( (unsigned __int64)(a3 - 1) > 0xFFFE )
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator=(&v16, a3);
  else
    ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::LoadStringW(&v16, (unsigned __int16)a3);
  v4 = v16;
  lpCmdLine = (LPCWSTR)(((__int64 (__fastcall *)(void ***))ATL::g_strmgr[3])(&ATL::g_strmgr) + 24);
  if ( !(unsigned __int8)ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CheckImplicitLoad(
                           &lpCmdLine,
                           v4) )
    ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::operator=(
      &lpCmdLine,
      v4);
  v5 = lpCmdLine;
  v6 = CommandLineToArgvW(lpCmdLine, &pNumArgs);
  v21 = (HRESULT *)v6;
  if ( v6 )
  {
    for ( i = 0; i < pNumArgs; ++i )
    {
      ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
        &v20,
        v6[i]);
      if ( *((_QWORD *)&v17 + 1) == v18 )
      {
        std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::_Emplace_reallocate<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>> const &>(
          &v17,
          *((_QWORD *)&v17 + 1),
          &v20);
      }
      else
      {
        ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>(
          *((_QWORD *)&v17 + 1),
          &v20);
        *((_QWORD *)&v17 + 1) += 8LL;
      }
      v8 = (_QWORD *)(v20 - 24);
      if ( _InterlockedDecrement((volatile signed __int32 *)(v20 - 24 + 16)) <= 0 )
        (*(void (__fastcall **)(_QWORD))(*(_QWORD *)*v8 + 8LL))(*v8);
    }
    LocalFree(v6);
    if ( _InterlockedDecrement((volatile signed __int32 *)v5 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 - 3) + 8LL))(*((_QWORD *)v5 - 3));
    if ( _InterlockedDecrement((volatile signed __int32 *)v4 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 - 3) + 8LL))(*((_QWORD *)v4 - 3));
    if ( pNumArgs == 2 )
    {
      v9 = _o__wtoi(*(_QWORD *)v17);
      v10 = (HWND)wcstol(*(const wchar_t **)(v17 + 8), 0, 16);
      v15 = CoInitializeEx(0, 2u);
      v13 = 0;
      v21 = &v15;
      v22 = &v13;
      v23 = 1;
      v11 = operator new(0x18u);
      *(_OWORD *)v11 = 0;
      *((_DWORD *)v11 + 2) = 1;
      *((_DWORD *)v11 + 3) = 1;
      *(_QWORD *)v11 = &std::_Ref_count_resource<long *,_lambda_dd8769f8f4d11b2a01f6b470159a26eb_>::`vftable';
      *((_QWORD *)v11 + 2) = &v15;
      v21 = &v15;
      v22 = (char *)v11;
      if ( !v15 )
      {
        v16 = 0;
        if ( !(unsigned int)F12::GetDocumentFromHwnd(v10) )
        {
          LOBYTE(v12) = 1;
          if ( (unsigned int)IEConfiguration_SetBool(536870925, v12) )
          {
            if ( v16 )
              (*(void (__fastcall **)(BPT *))(*(_QWORD *)v16 + 16LL))(v16);
            goto LABEL_28;
          }
          InjectTools(v9, &v16);
        }
        if ( v16 )
          (*(void (__fastcall **)(BPT *))(*(_QWORD *)v16 + 16LL))(v16);
      }
LABEL_28:
      if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 2, 0xFFFFFFFF) == 1 )
      {
        (**(void (__fastcall ***)(void *))v11)(v11);
        if ( _InterlockedExchangeAdd((volatile signed __int32 *)v11 + 3, 0xFFFFFFFF) == 1 )
          (*(void (__fastcall **)(void *))(*(_QWORD *)v11 + 8LL))(v11);
      }
    }
  }
  else
  {
    if ( _InterlockedDecrement((volatile signed __int32 *)v5 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v5 - 3) + 8LL))(*((_QWORD *)v5 - 3));
    if ( _InterlockedDecrement((volatile signed __int32 *)v4 - 2) <= 0 )
      (*(void (__fastcall **)(_QWORD))(**((_QWORD **)v4 - 3) + 8LL))(*((_QWORD *)v4 - 3));
  }
  std::vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>::~vector<ATL::CStringT<unsigned short,ATL::StrTraitATL<unsigned short,ATL::ChTraitsCRT<unsigned short>>>>(&v17);
}

```

## disassembly

```asm
0x180013a90  push    rbp
0x180013a92  push    rbx
0x180013a93  push    rsi
0x180013a94  push    rdi
0x180013a95  push    r14
0x180013a97  push    r15
0x180013a99  lea     rbp, [rsp-2Fh]
0x180013a9e  sub     rsp, 88h
0x180013aa5  mov     rbx, r8
0x180013aa8  mov     [rbp+57h+pNumArgs], 0
0x180013aaf  xorps   xmm0, xmm0
0x180013ab2  movdqu  [rbp+57h+var_78], xmm0
0x180013ab7  mov     [rbp+57h+var_68], 0
0x180013abf  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180013ac6  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180013acd  mov     rax, [rax+18h]
0x180013ad1  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013ad6  add     rax, 18h
0x180013ada  mov     [rbp+57h+var_80], rax
0x180013ade  lea     rax, [rbx-1]
0x180013ae2  lea     rcx, [rbp+57h+var_80]
0x180013ae6  cmp     rax, 0FFFEh
0x180013aec  ja      short loc_180013AF8
0x180013aee  movzx   edx, bx
0x180013af1  call    ?LoadStringW@?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAHI@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::LoadStringW(uint)
0x180013af6  jmp     short loc_180013B01
0x180013af8  mov     rdx, rbx
0x180013afb  call    ??4?$CStringT@DV?$StrTraitATL@DV?$ChTraitsCRT@D@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<char,ATL::StrTraitATL<char,ATL::ChTraitsCRT<char>>>::operator=(char const *)
0x180013b00  nop
0x180013b01  mov     r15, [rbp+57h+var_80]
0x180013b05  mov     rax, cs:?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180013b0c  lea     rcx, ?g_strmgr@ATL@@3VCAtlStringMgr@1@A; ATL::CAtlStringMgr ATL::g_strmgr
0x180013b13  mov     rax, [rax+18h]
0x180013b17  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013b1c  add     rax, 18h
0x180013b20  mov     [rbp+57h+lpCmdLine], rax
0x180013b24  mov     rdx, r15
0x180013b27  lea     rcx, [rbp+57h+lpCmdLine]
0x180013b2b  call    ?CheckImplicitLoad@?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@AEAA_NPEBX@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CheckImplicitLoad(void const *)
0x180013b30  test    al, al
0x180013b32  jnz     short loc_180013B41
0x180013b34  mov     rdx, r15
0x180013b37  lea     rcx, [rbp+57h+lpCmdLine]
0x180013b3b  call    ??4?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAAAEAV01@PEBD@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::operator=(char const *)
0x180013b40  nop
0x180013b41  lea     rdx, [rbp+57h+pNumArgs]; pNumArgs
0x180013b45  mov     rdi, [rbp+57h+lpCmdLine]
0x180013b49  mov     rcx, rdi; lpCmdLine
0x180013b4c  call    cs:__imp_CommandLineToArgvW
0x180013b52  mov     rbx, rax
0x180013b55  mov     [rbp+57h+var_50], rax
0x180013b59  test    rax, rax
0x180013b5c  jz      loc_180013D5E
0x180013b62  xor     r14d, r14d
0x180013b65  or      esi, 0FFFFFFFFh
0x180013b68  cmp     [rbp+57h+pNumArgs], r14d
0x180013b6c  jle     short loc_180013BDA
0x180013b6e  movsxd  rdx, r14d
0x180013b71  mov     rdx, [rbx+rdx*8]
0x180013b75  lea     rcx, [rbp+57h+var_58]
0x180013b79  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@PEBG@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ushort const *)
0x180013b7e  nop
0x180013b7f  mov     rax, qword ptr [rbp+57h+var_78+8]
0x180013b83  cmp     rax, [rbp+57h+var_68]
0x180013b87  jz      short loc_180013B9C
0x180013b89  lea     rdx, [rbp+57h+var_58]
0x180013b8d  mov     rcx, rax
0x180013b90  call    ??0?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAA@AEBV01@@Z; ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180013b95  add     qword ptr [rbp+57h+var_78+8], 8
0x180013b9a  jmp     short loc_180013BAD
0x180013b9c  lea     r8, [rbp+57h+var_58]
0x180013ba0  mov     rdx, rax
0x180013ba3  lea     rcx, [rbp+57h+var_78]
0x180013ba7  call    ??$_Emplace_reallocate@AEBV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@AEAAPEAV?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@QEAV23@AEBV23@@Z; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::_Emplace_reallocate<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &>(ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> * const,ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>> const &)
0x180013bac  nop
0x180013bad  mov     rdx, [rbp+57h+var_58]
0x180013bb1  add     rdx, 0FFFFFFFFFFFFFFE8h
0x180013bb5  mov     eax, esi
0x180013bb7  lock xadd [rdx+10h], eax
0x180013bbc  add     eax, esi
0x180013bbe  test    eax, eax
0x180013bc0  jg      short loc_180013BD1
0x180013bc2  mov     rcx, [rdx]
0x180013bc5  mov     rax, [rcx]
0x180013bc8  mov     rax, [rax+8]
0x180013bcc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013bd1  inc     r14d
0x180013bd4  cmp     r14d, [rbp+57h+pNumArgs]
0x180013bd8  jl      short loc_180013B6E
0x180013bda  mov     rcx, rbx; hMem
0x180013bdd  call    cs:__imp_LocalFree
0x180013be3  nop
0x180013be4  lea     rdx, [rdi-18h]
0x180013be8  mov     eax, esi
0x180013bea  lock xadd [rdx+10h], eax
0x180013bef  add     eax, esi
0x180013bf1  test    eax, eax
0x180013bf3  jg      short loc_180013C05
0x180013bf5  mov     rcx, [rdx]
0x180013bf8  mov     rax, [rcx]
0x180013bfb  mov     rax, [rax+8]
0x180013bff  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c04  nop
0x180013c05  lea     rdx, [r15-18h]
0x180013c09  mov     eax, esi
0x180013c0b  lock xadd [rdx+10h], eax
0x180013c10  add     eax, esi
0x180013c12  test    eax, eax
0x180013c14  jg      short loc_180013C25
0x180013c16  mov     rcx, [rdx]
0x180013c19  mov     rax, [rcx]
0x180013c1c  mov     rax, [rax+8]
0x180013c20  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013c25  cmp     [rbp+57h+pNumArgs], 2
0x180013c29  jnz     loc_180013DA3
0x180013c2f  mov     rcx, qword ptr [rbp+57h+var_78]
0x180013c33  mov     rcx, [rcx]
0x180013c36  call    cs:__imp__o__wtoi
0x180013c3c  mov     edi, eax
0x180013c3e  xor     edx, edx; EndPtr
0x180013c40  lea     r8d, [rdx+10h]; Radix
0x180013c44  mov     rcx, qword ptr [rbp+57h+var_78]
0x180013c48  mov     rcx, [rcx+8]; String
0x180013c4c  call    cs:__imp_wcstol
0x180013c52  movsxd  r14, eax
0x180013c55  mov     edx, 2; dwCoInit
0x180013c5a  xor     ecx, ecx; pvReserved
0x180013c5c  call    cs:__imp_CoInitializeEx
0x180013c62  mov     [rbp+57h+var_84], eax
0x180013c65  mov     [rbp+57h+var_90], 0
0x180013c69  lea     rax, [rbp+57h+var_84]
0x180013c6d  mov     [rbp+57h+var_50], rax
0x180013c71  lea     rax, [rbp+57h+var_90]
0x180013c75  mov     [rbp+57h+var_48], rax
0x180013c79  mov     [rbp+57h+var_40], 1
0x180013c7d  mov     ecx, 18h; Size
0x180013c82  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x180013c87  mov     rbx, rax
0x180013c8a  mov     [rbp+57h+var_50], rax
0x180013c8e  xorps   xmm0, xmm0
0x180013c91  movups  xmmword ptr [rax], xmm0
0x180013c94  mov     dword ptr [rax+8], 1
0x180013c9b  mov     dword ptr [rax+0Ch], 1
0x180013ca2  lea     rax, ??_7?$_Ref_count_resource@PEAJV_lambda_dd8769f8f4d11b2a01f6b470159a26eb_@@@std@@6B@; const std::_Ref_count_resource<long *,_lambda_dd8769f8f4d11b2a01f6b470159a26eb_>::`vftable'
0x180013ca9  mov     [rbx], rax
0x180013cac  lea     rax, [rbp+57h+var_84]
0x180013cb0  mov     [rbx+10h], rax
0x180013cb4  lea     rax, [rbp+57h+var_84]
0x180013cb8  mov     [rbp+57h+var_50], rax
0x180013cbc  mov     [rbp+57h+var_48], rbx
0x180013cc0  cmp     [rbp+57h+var_84], 0
0x180013cc4  jnz     short loc_180013D29
0x180013cc6  mov     rcx, r14; hWnd
0x180013cc9  mov     [rbp+57h+var_80], 0
0x180013cd1  lea     rdx, [rbp+57h+var_80]
0x180013cd5  call    ?GetDocumentFromHwnd@F12@@YAJQEAUHWND__@@AEAV?$CComPtr@UIDispatch@@@ATL@@@Z; F12::GetDocumentFromHwnd(HWND__ * const,ATL::CComPtr<IDispatch> &)
0x180013cda  test    eax, eax
0x180013cdc  jnz     short loc_180013CFB
0x180013cde  mov     dl, 1
0x180013ce0  mov     ecx, 2000000Dh
0x180013ce5  call    cs:__imp_?IEConfiguration_SetBool@@YAJW4IEConfigurationID@@_N@Z; IEConfiguration_SetBool(IEConfigurationID,bool)
0x180013ceb  test    eax, eax
0x180013ced  jnz     short loc_180013D13
0x180013cef  lea     rdx, [rbp+57h+var_80]
0x180013cf3  mov     ecx, edi; dwProcessId
0x180013cf5  call    ?InjectTools@@YAHKAEAV?$CComPtr@UIDispatch@@@ATL@@@Z; InjectTools(ulong,ATL::CComPtr<IDispatch> &)
0x180013cfa  nop
0x180013cfb  mov     rcx, [rbp+57h+var_80]
0x180013cff  test    rcx, rcx
0x180013d02  jz      short loc_180013D11
0x180013d04  mov     rax, [rcx]
0x180013d07  mov     rax, [rax+10h]
0x180013d0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d10  nop
0x180013d11  jmp     short loc_180013D29
0x180013d13  mov     rcx, [rbp+57h+var_80]
0x180013d17  test    rcx, rcx
0x180013d1a  jz      short loc_180013D29
0x180013d1c  mov     rax, [rcx]
0x180013d1f  mov     rax, [rax+10h]
0x180013d23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d28  nop
0x180013d29  mov     eax, esi
0x180013d2b  lock xadd [rbx+8], eax
0x180013d30  add     eax, esi
0x180013d32  jnz     short loc_180013DA3
0x180013d34  mov     rax, [rbx]
0x180013d37  mov     rcx, rbx
0x180013d3a  mov     rax, [rax]
0x180013d3d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d42  mov     eax, esi
0x180013d44  lock xadd [rbx+0Ch], eax
0x180013d49  add     eax, esi
0x180013d4b  jnz     short loc_180013DA3
0x180013d4d  mov     rax, [rbx]
0x180013d50  mov     rcx, rbx
0x180013d53  mov     rax, [rax+8]
0x180013d57  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d5c  jmp     short loc_180013DA3
0x180013d5e  lea     rdx, [rdi-18h]
0x180013d62  or      esi, 0FFFFFFFFh
0x180013d65  mov     eax, esi
0x180013d67  lock xadd [rdx+10h], eax
0x180013d6c  add     eax, esi
0x180013d6e  test    eax, eax
0x180013d70  jg      short loc_180013D82
0x180013d72  mov     rcx, [rdx]
0x180013d75  mov     rax, [rcx]
0x180013d78  mov     rax, [rax+8]
0x180013d7c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013d81  nop
0x180013d82  lea     rdx, [r15-18h]
0x180013d86  mov     eax, esi
0x180013d88  lock xadd [rdx+10h], eax
0x180013d8d  add     eax, esi
0x180013d8f  test    eax, eax
0x180013d91  jg      short loc_180013DA3
0x180013d93  mov     rcx, [rdx]
0x180013d96  mov     rax, [rcx]
0x180013d99  mov     rax, [rax+8]
0x180013d9d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180013da2  nop
0x180013da3  lea     rcx, [rbp+57h+var_78]
0x180013da7  call    ??1?$vector@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@V?$allocator@V?$CStringT@GV?$StrTraitATL@GV?$ChTraitsCRT@G@ATL@@@ATL@@@ATL@@@std@@@std@@QEAA@XZ; std::vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>::~vector<ATL::CStringT<ushort,ATL::StrTraitATL<ushort,ATL::ChTraitsCRT<ushort>>>>(void)
0x180013dac  add     rsp, 88h
0x180013db3  pop     r15
0x180013db5  pop     r14
0x180013db7  pop     rdi
0x180013db8  pop     rsi
0x180013db9  pop     rbx
0x180013dba  pop     rbp
0x180013dbb  retn
```
