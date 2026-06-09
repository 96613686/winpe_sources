# CEtwLogCollectorsNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180007ca0`
- end: `0x180008077`
- name: `?GetChildNodeNames@CEtwLogCollectorsNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `983`
- prototype: `__int64 __fastcall(CEtwLogCollectorsNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x1800073e0`
- `0x1800075ec`
- `0x180007ca0`
- `0x1800090b4`
- `0x18000dbb0`
- `0x18000e054`
- `0x180010ed4`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f8d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007fcb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008030`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000803e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007f8d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180007fcb`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008030`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000803e`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007d58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007e95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007d58`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007e95`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007db3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000800f`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007db3`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000800f`
- `OLEAUT32!__imp_SysAllocString` at `0x180007d79`
- `OLEAUT32!__imp_SysAllocString` at `0x180007eba`
- `OLEAUT32!__imp_SysAllocString` at `0x180007d79`
- `OLEAUT32!__imp_SysAllocString` at `0x180007eba`
- `OLEAUT32!__imp_SysFreeString` at `0x180007da4`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ee3`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f79`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fff`
- `OLEAUT32!__imp_SysFreeString` at `0x180007da4`
- `OLEAUT32!__imp_SysFreeString` at `0x180007ee3`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f79`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fb7`
- `OLEAUT32!__imp_SysFreeString` at `0x180007fff`

## pseudocode

```c
__int64 __fastcall CEtwLogCollectorsNode::GetChildNodeNames(__int64 this, unsigned int *a2, unsigned __int16 ***a3)
{
  int v3; // esi
  BSTR *v5; // r13
  BSTR *v6; // r15
  unsigned __int16 ***v7; // r12
  CEtwLogCollectorsNode *v8; // r9
  int v9; // ecx
  int v10; // ecx
  int RegisteredCollectorNames; // ebx
  __int64 v12; // rbx
  unsigned __int16 **v13; // rax
  unsigned __int16 **v14; // rsi
  __int64 v15; // rdi
  BSTR v16; // rax
  __int64 j; // rbx
  __int64 v18; // rbx
  unsigned __int16 **v19; // rax
  BSTR v20; // rax
  __int64 i; // rbx
  int v22; // eax
  int k; // edi
  unsigned int v24; // esi
  int m; // edi
  unsigned __int16 **v26; // rdi
  unsigned int v27; // r12d
  __int64 n; // rsi
  __int128 v30; // [rsp+30h] [rbp-50h] BYREF
  __int64 v31; // [rsp+40h] [rbp-40h]
  BSTR *v32; // [rsp+48h] [rbp-38h] BYREF
  __int64 v33; // [rsp+50h] [rbp-30h]
  OLECHAR *psz; // [rsp+58h] [rbp-28h]
  const unsigned __int16 *v35; // [rsp+60h] [rbp-20h]
  const wchar_t *v36; // [rsp+68h] [rbp-18h]
  const unsigned __int16 *v37; // [rsp+70h] [rbp-10h]
  const wchar_t *v38; // [rsp+78h] [rbp-8h]
  unsigned __int16 *v39; // [rsp+C8h] [rbp+48h] BYREF
  unsigned __int16 ***v40; // [rsp+D0h] [rbp+50h]
  int v41; // [rsp+D8h] [rbp+58h] BYREF

  v40 = a3;
  v3 = 0;
  v5 = 0;
  v6 = 0;
  v30 = 0u;
  v32 = 0;
  v7 = a3;
  v33 = 0;
  v8 = (CEtwLogCollectorsNode *)this;
  if ( !a2 || !a3 )
    goto LABEL_38;
  *a2 = 0;
  *a3 = 0;
  v9 = *(_DWORD *)(this + 44) - 2;
  if ( !v9 )
  {
    RegisteredCollectorNames = CEtwLogCollector::GetRegisteredCollectorNames(&v30, 2147942487LL, a3, v8);
    if ( RegisteredCollectorNames >= 0 )
      RegisteredCollectorNames = ConstructBSTRArray(v7, a2, (__int64)&v30);
    v5 = (BSTR *)v30;
    goto LABEL_18;
  }
  v10 = v9 - 1;
  if ( !v10 )
  {
    v18 = 40;
    psz = L"TraceStatus";
    v35 = L"TraceLogFileMode";
    v36 = L"TraceControl";
    v37 = L"LogFileSizeLimitMB";
    v38 = L"Providers";
    v19 = (unsigned __int16 **)CoTaskMemAlloc(0x28u);
    v14 = v19;
    if ( !v19 )
      goto LABEL_17;
    v15 = 0;
    do
    {
      *(_BYTE *)v19 = 0;
      v19 = (unsigned __int16 **)((char *)v19 + 1);
      --v18;
    }
    while ( v18 );
    while ( 1 )
    {
      v20 = SysAllocString((&psz)[v15]);
      v14[v15] = v20;
      if ( !v20 )
        break;
      v15 = (unsigned int)(v15 + 1);
      if ( (unsigned int)v15 >= 5 )
      {
LABEL_13:
        *v7 = v14;
        RegisteredCollectorNames = 0;
        *a2 = v15;
        goto LABEL_18;
      }
    }
    for ( i = 0; (unsigned int)i < (unsigned int)v15; i = (unsigned int)(i + 1) )
      SysFreeString(v14[i]);
LABEL_16:
    CoTaskMemFree(v14);
LABEL_17:
    RegisteredCollectorNames = -2147024882;
LABEL_18:
    v3 = DWORD2(v30);
    goto LABEL_39;
  }
  this = (unsigned int)(v10 - 5);
  if ( (_DWORD)this )
  {
    if ( (_DWORD)this != 1 )
    {
      *a2 = 0;
      *a3 = 0;
      RegisteredCollectorNames = -2046820335;
      goto LABEL_39;
    }
    v12 = 24;
    psz = (OLECHAR *)L"Keywords";
    v35 = L"TraceLevel";
    v36 = L"State";
    v13 = (unsigned __int16 **)CoTaskMemAlloc(0x18u);
    v14 = v13;
    if ( !v13 )
      goto LABEL_17;
    v15 = 0;
    do
    {
      *(_BYTE *)v13 = 0;
      v13 = (unsigned __int16 **)((char *)v13 + 1);
      --v12;
    }
    while ( v12 );
    while ( 1 )
    {
      v16 = SysAllocString((&psz)[v15]);
      v14[v15] = v16;
      if ( !v16 )
        break;
      v15 = (unsigned int)(v15 + 1);
      if ( (unsigned int)v15 >= 3 )
        goto LABEL_13;
    }
    for ( j = 0; (unsigned int)j < (unsigned int)v15; j = (unsigned int)(j + 1) )
      SysFreeString(v14[j]);
    goto LABEL_16;
  }
  this = *((_QWORD *)v8 + 3);
  if ( this )
  {
    v39 = 0;
    RegisteredCollectorNames = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 **))(*(_QWORD *)this + 88LL))(
                                 this,
                                 3,
                                 &v39);
    if ( RegisteredCollectorNames >= 0 )
    {
      v31 = 0;
      v30 = 0;
      RegisteredCollectorNames = CEtwLogCollector::Open((CEtwLogCollector *)&v30, v39);
      if ( RegisteredCollectorNames >= 0 )
      {
        RegisteredCollectorNames = CRegUtils::EnumChildKeys(&v30, &v32);
        if ( RegisteredCollectorNames >= 0 )
          RegisteredCollectorNames = ConstructBSTRArray(v7, a2, (__int64)&v32);
        CFileDownload_DMChannel::~CFileDownload_DMChannel((HKEY *)&v30);
        v6 = v32;
      }
      else
      {
        CFileDownload_DMChannel::~CFileDownload_DMChannel((HKEY *)&v30);
      }
    }
  }
  else
  {
LABEL_38:
    RegisteredCollectorNames = -2147024809;
  }
LABEL_39:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    LODWORD(v39) = RegisteredCollectorNames;
    if ( a2 )
      v22 = *a2;
    else
      v22 = -1;
    v41 = v22;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      this,
      (__int64)byte_18003E97B,
      (__int64)a3,
      (__int64)v8,
      (__int64)&v41,
      (__int64)&v39);
  }
  for ( k = 0; k < (unsigned int)v3; ++k )
  {
    if ( k < 0 || k >= v3 )
    {
      ATL::_AtlRaiseException(0xC000008C);
      __debugbreak();
    }
    SysFreeString(v5[k]);
  }
  if ( v5 )
    free(v5);
  v24 = v33;
  for ( m = 0; m < v24; ++m )
  {
    if ( m < 0 || m >= (int)v33 )
    {
      ATL::_AtlRaiseException(0xC000008C);
      JUMPOUT(0x180008076LL);
    }
    SysFreeString(v6[m]);
  }
  if ( v6 )
    free(v6);
  if ( (int)(RegisteredCollectorNames + 0x80000000) >= 0 && RegisteredCollectorNames != -2147024809 )
  {
    v26 = *v7;
    if ( *v7 )
    {
      v27 = *a2;
      for ( n = 0; (unsigned int)n < v27; n = (unsigned int)(n + 1) )
        SysFreeString(v26[n]);
      CoTaskMemFree(v26);
      v7 = v40;
    }
    *v7 = 0;
    *a2 = 0;
  }
  return (unsigned int)RegisteredCollectorNames;
}

```

## disassembly

```asm
0x180007ca0  mov     [rsp-38h+arg_0], rbx
0x180007ca5  mov     [rsp-38h+arg_10], r8
0x180007caa  push    rbp
0x180007cab  push    rsi
0x180007cac  push    rdi
0x180007cad  push    r12
0x180007caf  push    r13
0x180007cb1  push    r14
0x180007cb3  push    r15
0x180007cb5  mov     rbp, rsp
0x180007cb8  sub     rsp, 80h
0x180007cbf  xor     esi, esi
0x180007cc1  mov     r14, rdx
0x180007cc4  xor     r13d, r13d
0x180007cc7  mov     qword ptr [rbp+var_50+8], rsi
0x180007ccb  xor     r15d, r15d
0x180007cce  mov     qword ptr [rbp+var_50], r13
0x180007cd2  mov     [rbp+var_38], r15
0x180007cd6  mov     r12, r8
0x180007cd9  mov     [rbp+var_30], rsi
0x180007cdd  mov     r9, rcx
0x180007ce0  mov     edx, 80070057h
0x180007ce5  test    r14, r14
0x180007ce8  jz      loc_180007F1D
0x180007cee  test    r8, r8
0x180007cf1  jz      loc_180007F1D
0x180007cf7  mov     [r14], esi
0x180007cfa  mov     [r8], rsi
0x180007cfd  mov     ecx, [rcx+2Ch]
0x180007d00  sub     ecx, 2
0x180007d03  jz      loc_180007EF4
0x180007d09  sub     ecx, 1
0x180007d0c  jz      loc_180007E57
0x180007d12  sub     ecx, 5
0x180007d15  jz      loc_180007DC6
0x180007d1b  cmp     ecx, 1
0x180007d1e  jz      short loc_180007D30
0x180007d20  mov     [r14], esi
0x180007d23  mov     [r8], rsi
0x180007d26  mov     ebx, 86000011h
0x180007d2b  jmp     loc_180007F1F
0x180007d30  lea     rax, aKeywords; "Keywords"
0x180007d37  mov     ebx, 18h
0x180007d3c  mov     [rbp+psz], rax
0x180007d40  mov     ecx, ebx; cb
0x180007d42  lea     rax, aTracelevel; "TraceLevel"
0x180007d49  mov     [rbp+var_20], rax
0x180007d4d  lea     rax, aState; "State"
0x180007d54  mov     [rbp+var_18], rax
0x180007d58  call    cs:__imp_CoTaskMemAlloc
0x180007d5e  mov     rsi, rax
0x180007d61  test    rax, rax
0x180007d64  jz      short loc_180007DB9
0x180007d66  xor     edi, edi
0x180007d68  mov     [rax], dil
0x180007d6b  inc     rax
0x180007d6e  sub     rbx, 1
0x180007d72  jnz     short loc_180007D68
0x180007d74  mov     rcx, [rbp+rdi*8+psz]; psz
0x180007d79  call    cs:__imp_SysAllocString
0x180007d7f  mov     [rsi+rdi*8], rax
0x180007d83  test    rax, rax
0x180007d86  jz      short loc_180007D9A
0x180007d88  inc     edi
0x180007d8a  cmp     edi, 3
0x180007d8d  jb      short loc_180007D74
0x180007d8f  mov     [r12], rsi
0x180007d93  xor     ebx, ebx
0x180007d95  mov     [r14], edi
0x180007d98  jmp     short loc_180007DBE
0x180007d9a  xor     ebx, ebx
0x180007d9c  test    edi, edi
0x180007d9e  jz      short loc_180007DB0
0x180007da0  mov     rcx, [rsi+rbx*8]; bstrString
0x180007da4  call    cs:__imp_SysFreeString
0x180007daa  inc     ebx
0x180007dac  cmp     ebx, edi
0x180007dae  jb      short loc_180007DA0
0x180007db0  mov     rcx, rsi; pv
0x180007db3  call    cs:__imp_CoTaskMemFree
0x180007db9  mov     ebx, 8007000Eh
0x180007dbe  mov     esi, dword ptr [rbp+var_50+8]
0x180007dc1  jmp     loc_180007F1F
0x180007dc6  mov     rcx, [r9+18h]
0x180007dca  test    rcx, rcx
0x180007dcd  jz      loc_180007F1D
0x180007dd3  mov     [rbp+arg_8], rsi
0x180007dd7  lea     r8, [rbp+arg_8]
0x180007ddb  mov     rax, [rcx]
0x180007dde  mov     edx, 3
0x180007de3  mov     rax, [rax+58h]
0x180007de7  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dec  mov     ebx, eax
0x180007dee  test    eax, eax
0x180007df0  js      loc_180007F1F
0x180007df6  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x180007dfa  lea     rcx, [rbp+var_50]; this
0x180007dfe  xorps   xmm0, xmm0
0x180007e01  mov     [rbp+var_40], rsi
0x180007e05  movdqu  [rbp+var_50], xmm0
0x180007e0a  call    ?Open@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::Open(ushort const *)
0x180007e0f  lea     rcx, [rbp+var_50]; this
0x180007e13  mov     ebx, eax
0x180007e15  test    eax, eax
0x180007e17  jns     short loc_180007E23
0x180007e19  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180007e1e  jmp     loc_180007F1F
0x180007e23  lea     rdx, [rbp+var_38]
0x180007e27  call    ?EnumChildKeys@CRegUtils@@SAJAEAVCRegKey@ATL@@PEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@3@@Z; CRegUtils::EnumChildKeys(ATL::CRegKey &,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x180007e2c  mov     ebx, eax
0x180007e2e  test    eax, eax
0x180007e30  jns     short loc_180007E44
0x180007e32  lea     rcx, [rbp+var_50]; this
0x180007e36  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180007e3b  mov     r15, [rbp+var_38]
0x180007e3f  jmp     loc_180007F1F
0x180007e44  lea     r8, [rbp+var_38]
0x180007e48  mov     rdx, r14
0x180007e4b  mov     rcx, r12
0x180007e4e  call    ?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)
0x180007e53  mov     ebx, eax
0x180007e55  jmp     short loc_180007E32
0x180007e57  lea     rax, aTracestatus; "TraceStatus"
0x180007e5e  mov     ebx, 28h ; '('
0x180007e63  mov     [rbp+psz], rax
0x180007e67  mov     ecx, ebx; cb
0x180007e69  lea     rax, aTracelogfilemo; "TraceLogFileMode"
0x180007e70  mov     [rbp+var_20], rax
0x180007e74  lea     rax, aTracecontrol; "TraceControl"
0x180007e7b  mov     [rbp+var_18], rax
0x180007e7f  lea     rax, aLogfilesizelim; "LogFileSizeLimitMB"
0x180007e86  mov     [rbp+var_10], rax
0x180007e8a  lea     rax, aProviders; "Providers"
0x180007e91  mov     [rbp+var_8], rax
0x180007e95  call    cs:__imp_CoTaskMemAlloc
0x180007e9b  mov     rsi, rax
0x180007e9e  test    rax, rax
0x180007ea1  jz      loc_180007DB9
0x180007ea7  xor     edi, edi
0x180007ea9  mov     [rax], dil
0x180007eac  inc     rax
0x180007eaf  sub     rbx, 1
0x180007eb3  jnz     short loc_180007EA9
0x180007eb5  mov     rcx, [rbp+rdi*8+psz]; psz
0x180007eba  call    cs:__imp_SysAllocString
0x180007ec0  mov     [rsi+rdi*8], rax
0x180007ec4  test    rax, rax
0x180007ec7  jz      short loc_180007ED5
0x180007ec9  inc     edi
0x180007ecb  cmp     edi, 5
0x180007ece  jb      short loc_180007EB5
0x180007ed0  jmp     loc_180007D8F
0x180007ed5  xor     ebx, ebx
0x180007ed7  test    edi, edi
0x180007ed9  jz      loc_180007DB0
0x180007edf  mov     rcx, [rsi+rbx*8]; bstrString
0x180007ee3  call    cs:__imp_SysFreeString
0x180007ee9  inc     ebx
0x180007eeb  cmp     ebx, edi
0x180007eed  jb      short loc_180007EDF
0x180007eef  jmp     loc_180007DB0
0x180007ef4  lea     rcx, [rbp+var_50]
0x180007ef8  call    ?GetRegisteredCollectorNames@CEtwLogCollector@@SAJPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; CEtwLogCollector::GetRegisteredCollectorNames(ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x180007efd  mov     ebx, eax
0x180007eff  test    eax, eax
0x180007f01  js      short loc_180007F14
0x180007f03  lea     r8, [rbp+var_50]
0x180007f07  mov     rdx, r14
0x180007f0a  mov     rcx, r12
0x180007f0d  call    ?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)
0x180007f12  mov     ebx, eax
0x180007f14  mov     r13, qword ptr [rbp+var_50]
0x180007f18  jmp     loc_180007DBE
0x180007f1d  mov     ebx, edx
0x180007f1f  mov     eax, cs:dword_180048E90
0x180007f25  cmp     eax, 5
0x180007f28  jbe     short loc_180007F5B
0x180007f2a  mov     dword ptr [rbp+arg_8], ebx
0x180007f2d  test    r14, r14
0x180007f30  jz      short loc_180007F37
0x180007f32  mov     eax, [r14]
0x180007f35  jmp     short loc_180007F3A
0x180007f37  or      eax, 0FFFFFFFFh
0x180007f3a  mov     [rbp+arg_18], eax
0x180007f3d  lea     rdx, byte_18003E97B
0x180007f44  lea     rax, [rbp+arg_8]
0x180007f48  mov     [rsp+80h+var_58], rax
0x180007f4d  lea     rax, [rbp+arg_18]
0x180007f51  mov     [rsp+80h+var_60], rax
0x180007f56  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180007f5b  xor     edi, edi
0x180007f5d  test    esi, esi
0x180007f5f  jz      short loc_180007F85
0x180007f61  test    edi, edi
0x180007f63  js      loc_180008061
0x180007f69  cmp     edi, esi
0x180007f6b  jge     loc_180008061
0x180007f71  movsxd  rcx, edi
0x180007f74  mov     rcx, [r13+rcx*8+0]; bstrString
0x180007f79  call    cs:__imp_SysFreeString
0x180007f7f  inc     edi
0x180007f81  cmp     edi, esi
0x180007f83  jb      short loc_180007F61
0x180007f85  test    r13, r13
0x180007f88  jz      short loc_180007F96
0x180007f8a  mov     rcx, r13; Block
0x180007f8d  call    cs:__imp_free
0x180007f93  xor     r13d, r13d
0x180007f96  mov     esi, dword ptr [rbp+var_30]
0x180007f99  xor     edi, edi
0x180007f9b  test    esi, esi
0x180007f9d  jz      short loc_180007FC3
0x180007f9f  test    edi, edi
0x180007fa1  js      loc_18000806C
0x180007fa7  cmp     edi, dword ptr [rbp+var_30]
0x180007faa  jge     loc_18000806C
0x180007fb0  movsxd  rcx, edi
0x180007fb3  mov     rcx, [r15+rcx*8]; bstrString
0x180007fb7  call    cs:__imp_SysFreeString
0x180007fbd  inc     edi
0x180007fbf  cmp     edi, esi
0x180007fc1  jb      short loc_180007F9F
0x180007fc3  test    r15, r15
0x180007fc6  jz      short loc_180007FD4
0x180007fc8  mov     rcx, r15; Block
0x180007fcb  call    cs:__imp_free
0x180007fd1  xor     r15d, r15d
0x180007fd4  mov     ecx, 80000000h
0x180007fd9  lea     eax, [rbx+rcx]
0x180007fdc  test    ecx, eax
0x180007fde  jnz     short loc_180008028
0x180007fe0  cmp     ebx, 80070057h
0x180007fe6  jz      short loc_180008028
0x180007fe8  mov     rdi, [r12]
0x180007fec  test    rdi, rdi
0x180007fef  jz      short loc_180008019
0x180007ff1  mov     r12d, [r14]
0x180007ff4  xor     esi, esi
0x180007ff6  test    r12d, r12d
0x180007ff9  jz      short loc_18000800C
0x180007ffb  mov     rcx, [rdi+rsi*8]; bstrString
0x180007fff  call    cs:__imp_SysFreeString
0x180008005  inc     esi
0x180008007  cmp     esi, r12d
0x18000800a  jb      short loc_180007FFB
0x18000800c  mov     rcx, rdi; pv
0x18000800f  call    cs:__imp_CoTaskMemFree
0x180008015  mov     r12, [rbp+arg_10]
0x180008019  mov     qword ptr [r12], 0
0x180008021  mov     dword ptr [r14], 0
0x180008028  test    r15, r15
0x18000802b  jz      short loc_180008036
0x18000802d  mov     rcx, r15; Block
0x180008030  call    cs:__imp_free
0x180008036  test    r13, r13
0x180008039  jz      short loc_180008044
0x18000803b  mov     rcx, r13; Block
0x18000803e  call    cs:__imp_free
0x180008044  mov     eax, ebx
0x180008046  mov     rbx, [rsp+80h+arg_0]
0x18000804e  add     rsp, 80h
0x180008055  pop     r15
0x180008057  pop     r14
0x180008059  pop     r13
0x18000805b  pop     r12
0x18000805d  pop     rdi
0x18000805e  pop     rsi
0x18000805f  pop     rbp
0x180008060  retn
0x180008061  mov     ecx, 0C000008Ch; unsigned int
0x180008066  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x18000806b  int     3; Trap to Debugger
0x18000806c  mov     ecx, 0C000008Ch; unsigned int
0x180008071  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
