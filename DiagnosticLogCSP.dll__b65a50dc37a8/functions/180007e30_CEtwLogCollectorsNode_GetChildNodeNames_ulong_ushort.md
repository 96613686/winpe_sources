# CEtwLogCollectorsNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180007e30`
- end: `0x180008262`
- name: `?GetChildNodeNames@CEtwLogCollectorsNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1074`
- prototype: `__int64 __fastcall(CEtwLogCollectorsNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `9`
- tags: `service_task, broker_com_uri`

## callees

- `0x180001090`
- `0x180007530`
- `0x18000774c`
- `0x180007e30`
- `0x1800092f8`
- `0x18000e278`
- `0x18000e744`
- `0x180011770`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000814d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008197`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000820e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008222`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000814d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008197`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000820e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180008222`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000803d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180007ee8`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x18000803d`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081e7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180007f55`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800081e7`
- `OLEAUT32!__imp_SysAllocString` at `0x180007f0f`
- `OLEAUT32!__imp_SysAllocString` at `0x180008068`
- `OLEAUT32!__imp_SysAllocString` at `0x180007f0f`
- `OLEAUT32!__imp_SysAllocString` at `0x180008068`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f40`
- `OLEAUT32!__imp_SysFreeString` at `0x180008097`
- `OLEAUT32!__imp_SysFreeString` at `0x180008133`
- `OLEAUT32!__imp_SysFreeString` at `0x18000817d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081d1`
- `OLEAUT32!__imp_SysFreeString` at `0x180007f40`
- `OLEAUT32!__imp_SysFreeString` at `0x180008097`
- `OLEAUT32!__imp_SysFreeString` at `0x180008133`
- `OLEAUT32!__imp_SysFreeString` at `0x18000817d`
- `OLEAUT32!__imp_SysFreeString` at `0x1800081d1`

## pseudocode

```c
__int64 __fastcall CEtwLogCollectorsNode::GetChildNodeNames(
        CEtwLogCollectorsNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  int v3; // esi
  BSTR *v5; // r13
  BSTR *v6; // r15
  unsigned __int16 ***v7; // r12
  CEtwLogCollectorsNode *v8; // r9
  unsigned int v9; // edx
  int v10; // ecx
  int v11; // ecx
  int RegisteredCollectorNames; // ebx
  __int64 v13; // rbx
  unsigned __int16 **v14; // rax
  unsigned __int16 **v15; // rsi
  __int64 v16; // rdi
  BSTR v17; // rax
  __int64 j; // rbx
  __int64 v19; // rbx
  unsigned __int16 **v20; // rax
  BSTR v21; // rax
  __int64 i; // rbx
  int v23; // eax
  int k; // edi
  unsigned int v25; // esi
  int m; // edi
  unsigned __int16 **v27; // rdi
  unsigned int v28; // r12d
  __int64 n; // rsi
  __int128 v31; // [rsp+30h] [rbp-50h] BYREF
  __int64 v32; // [rsp+40h] [rbp-40h]
  BSTR *v33; // [rsp+48h] [rbp-38h] BYREF
  __int64 v34; // [rsp+50h] [rbp-30h]
  OLECHAR *psz; // [rsp+58h] [rbp-28h]
  const unsigned __int16 *v36; // [rsp+60h] [rbp-20h]
  const wchar_t *v37; // [rsp+68h] [rbp-18h]
  const unsigned __int16 *v38; // [rsp+70h] [rbp-10h]
  const wchar_t *v39; // [rsp+78h] [rbp-8h]
  unsigned __int16 *v40; // [rsp+C8h] [rbp+48h] BYREF
  unsigned __int16 ***v41; // [rsp+D0h] [rbp+50h]
  int v42; // [rsp+D8h] [rbp+58h] BYREF

  v41 = a3;
  v3 = 0;
  v5 = 0;
  v6 = 0;
  v31 = 0u;
  v33 = 0;
  v7 = a3;
  v34 = 0;
  v8 = this;
  v9 = -2147024809;
  if ( !a2 || !a3 )
    goto LABEL_38;
  *a2 = 0;
  *a3 = 0;
  v10 = *((_DWORD *)this + 11) - 2;
  if ( !v10 )
  {
    RegisteredCollectorNames = CEtwLogCollector::GetRegisteredCollectorNames(&v31, 2147942487LL, a3, v8);
    if ( RegisteredCollectorNames >= 0 )
      RegisteredCollectorNames = ConstructBSTRArray(v7, a2, &v31);
    v5 = (BSTR *)v31;
    goto LABEL_18;
  }
  v11 = v10 - 1;
  if ( !v11 )
  {
    v19 = 40;
    psz = L"TraceStatus";
    v36 = L"TraceLogFileMode";
    v37 = L"TraceControl";
    v38 = L"LogFileSizeLimitMB";
    v39 = L"Providers";
    v20 = (unsigned __int16 **)CoTaskMemAlloc(0x28u);
    v15 = v20;
    if ( !v20 )
      goto LABEL_17;
    v16 = 0;
    do
    {
      *(_BYTE *)v20 = 0;
      v20 = (unsigned __int16 **)((char *)v20 + 1);
      --v19;
    }
    while ( v19 );
    while ( 1 )
    {
      v21 = SysAllocString((&psz)[v16]);
      v15[v16] = v21;
      if ( !v21 )
        break;
      v16 = (unsigned int)(v16 + 1);
      if ( (unsigned int)v16 >= 5 )
      {
LABEL_13:
        *v7 = v15;
        RegisteredCollectorNames = 0;
        *a2 = v16;
        goto LABEL_18;
      }
    }
    for ( i = 0; (unsigned int)i < (unsigned int)v16; i = (unsigned int)(i + 1) )
      SysFreeString(v15[i]);
LABEL_16:
    CoTaskMemFree(v15);
LABEL_17:
    RegisteredCollectorNames = -2147024882;
LABEL_18:
    v3 = DWORD2(v31);
    goto LABEL_39;
  }
  LODWORD(this) = v11 - 5;
  if ( (_DWORD)this )
  {
    if ( (_DWORD)this != 1 )
    {
      *a2 = 0;
      *a3 = 0;
      RegisteredCollectorNames = -2046820335;
      goto LABEL_39;
    }
    v13 = 24;
    psz = (OLECHAR *)L"Keywords";
    v36 = L"TraceLevel";
    v37 = L"State";
    v14 = (unsigned __int16 **)CoTaskMemAlloc(0x18u);
    v15 = v14;
    if ( !v14 )
      goto LABEL_17;
    v16 = 0;
    do
    {
      *(_BYTE *)v14 = 0;
      v14 = (unsigned __int16 **)((char *)v14 + 1);
      --v13;
    }
    while ( v13 );
    while ( 1 )
    {
      v17 = SysAllocString((&psz)[v16]);
      v15[v16] = v17;
      if ( !v17 )
        break;
      v16 = (unsigned int)(v16 + 1);
      if ( (unsigned int)v16 >= 3 )
        goto LABEL_13;
    }
    for ( j = 0; (unsigned int)j < (unsigned int)v16; j = (unsigned int)(j + 1) )
      SysFreeString(v15[j]);
    goto LABEL_16;
  }
  this = (CEtwLogCollectorsNode *)*((_QWORD *)v8 + 3);
  if ( this )
  {
    v40 = 0;
    RegisteredCollectorNames = (*(__int64 (__fastcall **)(CEtwLogCollectorsNode *, __int64, unsigned __int16 **))(*(_QWORD *)this + 88LL))(
                                 this,
                                 3,
                                 &v40);
    if ( RegisteredCollectorNames >= 0 )
    {
      v32 = 0;
      v31 = 0;
      RegisteredCollectorNames = CEtwLogCollector::Open((CEtwLogCollector *)&v31, v40);
      if ( RegisteredCollectorNames >= 0 )
      {
        RegisteredCollectorNames = CRegUtils::EnumChildKeys(&v31, &v33);
        if ( RegisteredCollectorNames >= 0 )
          RegisteredCollectorNames = ConstructBSTRArray(v7, a2, &v33);
        CFileDownload_DMChannel::~CFileDownload_DMChannel((CFileDownload_DMChannel *)&v31);
        v6 = v33;
      }
      else
      {
        CFileDownload_DMChannel::~CFileDownload_DMChannel((CFileDownload_DMChannel *)&v31);
      }
    }
  }
  else
  {
LABEL_38:
    RegisteredCollectorNames = -2147024809;
  }
LABEL_39:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    LODWORD(v40) = RegisteredCollectorNames;
    if ( a2 )
      v23 = *a2;
    else
      v23 = -1;
    v42 = v23;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)byte_18004097B,
      (_DWORD)a3,
      (_DWORD)v8,
      (__int64)&v42,
      (__int64)&v40);
  }
  for ( k = 0; k < (unsigned int)v3; ++k )
  {
    if ( k < 0 || k >= v3 )
    {
      ATL::_AtlRaiseException(0xC000008C, v9);
      __debugbreak();
    }
    SysFreeString(v5[k]);
  }
  if ( v5 )
    free(v5);
  v25 = v34;
  for ( m = 0; m < v25; ++m )
  {
    if ( m < 0 || m >= (int)v34 )
    {
      ATL::_AtlRaiseException(0xC000008C, v9);
      JUMPOUT(0x180008261LL);
    }
    SysFreeString(v6[m]);
  }
  if ( v6 )
    free(v6);
  if ( (int)(RegisteredCollectorNames + 0x80000000) >= 0 && RegisteredCollectorNames != -2147024809 )
  {
    v27 = *v7;
    if ( *v7 )
    {
      v28 = *a2;
      for ( n = 0; (unsigned int)n < v28; n = (unsigned int)(n + 1) )
        SysFreeString(v27[n]);
      CoTaskMemFree(v27);
      v7 = v41;
    }
    *v7 = 0;
    *a2 = 0;
  }
  return (unsigned int)RegisteredCollectorNames;
}

```

## disassembly

```asm
0x180007e30  mov     [rsp-38h+arg_0], rbx
0x180007e35  mov     [rsp-38h+arg_10], r8
0x180007e3a  push    rbp
0x180007e3b  push    rsi
0x180007e3c  push    rdi
0x180007e3d  push    r12
0x180007e3f  push    r13
0x180007e41  push    r14
0x180007e43  push    r15
0x180007e45  mov     rbp, rsp
0x180007e48  sub     rsp, 80h
0x180007e4f  xor     esi, esi
0x180007e51  mov     r14, rdx
0x180007e54  xor     r13d, r13d
0x180007e57  mov     qword ptr [rbp+var_50+8], rsi
0x180007e5b  xor     r15d, r15d
0x180007e5e  mov     qword ptr [rbp+var_50], r13
0x180007e62  mov     [rbp+var_38], r15
0x180007e66  mov     r12, r8
0x180007e69  mov     [rbp+var_30], rsi
0x180007e6d  mov     r9, rcx
0x180007e70  mov     edx, 80070057h
0x180007e75  test    r14, r14
0x180007e78  jz      loc_1800080D7
0x180007e7e  test    r8, r8
0x180007e81  jz      loc_1800080D7
0x180007e87  mov     [r14], esi
0x180007e8a  mov     [r8], rsi
0x180007e8d  mov     ecx, [rcx+2Ch]
0x180007e90  sub     ecx, 2
0x180007e93  jz      loc_1800080AE
0x180007e99  sub     ecx, 1
0x180007e9c  jz      loc_180007FFF
0x180007ea2  sub     ecx, 5
0x180007ea5  jz      loc_180007F6E
0x180007eab  cmp     ecx, 1
0x180007eae  jz      short loc_180007EC0
0x180007eb0  mov     [r14], esi
0x180007eb3  mov     [r8], rsi
0x180007eb6  mov     ebx, 86000011h
0x180007ebb  jmp     loc_1800080D9
0x180007ec0  lea     rax, aKeywords; "Keywords"
0x180007ec7  mov     ebx, 18h
0x180007ecc  mov     [rbp+psz], rax
0x180007ed0  mov     ecx, ebx; cb
0x180007ed2  lea     rax, aTracelevel; "TraceLevel"
0x180007ed9  mov     [rbp+var_20], rax
0x180007edd  lea     rax, aState; "State"
0x180007ee4  mov     [rbp+var_18], rax
0x180007ee8  call    cs:__imp_CoTaskMemAlloc
0x180007eef  nop     dword ptr [rax+rax+00h]
0x180007ef4  mov     rsi, rax
0x180007ef7  test    rax, rax
0x180007efa  jz      short loc_180007F61
0x180007efc  xor     edi, edi
0x180007efe  mov     [rax], dil
0x180007f01  inc     rax
0x180007f04  sub     rbx, 1
0x180007f08  jnz     short loc_180007EFE
0x180007f0a  mov     rcx, [rbp+rdi*8+psz]; psz
0x180007f0f  call    cs:__imp_SysAllocString
0x180007f16  nop     dword ptr [rax+rax+00h]
0x180007f1b  mov     [rsi+rdi*8], rax
0x180007f1f  test    rax, rax
0x180007f22  jz      short loc_180007F36
0x180007f24  inc     edi
0x180007f26  cmp     edi, 3
0x180007f29  jb      short loc_180007F0A
0x180007f2b  mov     [r12], rsi
0x180007f2f  xor     ebx, ebx
0x180007f31  mov     [r14], edi
0x180007f34  jmp     short loc_180007F66
0x180007f36  xor     ebx, ebx
0x180007f38  test    edi, edi
0x180007f3a  jz      short loc_180007F52
0x180007f3c  mov     rcx, [rsi+rbx*8]; bstrString
0x180007f40  call    cs:__imp_SysFreeString
0x180007f47  nop     dword ptr [rax+rax+00h]
0x180007f4c  inc     ebx
0x180007f4e  cmp     ebx, edi
0x180007f50  jb      short loc_180007F3C
0x180007f52  mov     rcx, rsi; pv
0x180007f55  call    cs:__imp_CoTaskMemFree
0x180007f5c  nop     dword ptr [rax+rax+00h]
0x180007f61  mov     ebx, 8007000Eh
0x180007f66  mov     esi, dword ptr [rbp+var_50+8]
0x180007f69  jmp     loc_1800080D9
0x180007f6e  mov     rcx, [r9+18h]
0x180007f72  test    rcx, rcx
0x180007f75  jz      loc_1800080D7
0x180007f7b  mov     [rbp+arg_8], rsi
0x180007f7f  lea     r8, [rbp+arg_8]
0x180007f83  mov     rax, [rcx]
0x180007f86  mov     edx, 3
0x180007f8b  mov     rax, [rax+58h]
0x180007f8f  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007f94  mov     ebx, eax
0x180007f96  test    eax, eax
0x180007f98  js      loc_1800080D9
0x180007f9e  mov     rdx, [rbp+arg_8]; unsigned __int16 *
0x180007fa2  lea     rcx, [rbp+var_50]; this
0x180007fa6  xorps   xmm0, xmm0
0x180007fa9  mov     [rbp+var_40], rsi
0x180007fad  movdqu  [rbp+var_50], xmm0
0x180007fb2  call    ?Open@CEtwLogCollector@@QEAAJPEBG@Z; CEtwLogCollector::Open(ushort const *)
0x180007fb7  lea     rcx, [rbp+var_50]; this
0x180007fbb  mov     ebx, eax
0x180007fbd  test    eax, eax
0x180007fbf  jns     short loc_180007FCB
0x180007fc1  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180007fc6  jmp     loc_1800080D9
0x180007fcb  lea     rdx, [rbp+var_38]
0x180007fcf  call    ?EnumChildKeys@CRegUtils@@SAJAEAVCRegKey@ATL@@PEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@3@@Z; CRegUtils::EnumChildKeys(ATL::CRegKey &,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x180007fd4  mov     ebx, eax
0x180007fd6  test    eax, eax
0x180007fd8  jns     short loc_180007FEC
0x180007fda  lea     rcx, [rbp+var_50]; this
0x180007fde  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180007fe3  mov     r15, [rbp+var_38]
0x180007fe7  jmp     loc_1800080D9
0x180007fec  lea     r8, [rbp+var_38]
0x180007ff0  mov     rdx, r14
0x180007ff3  mov     rcx, r12
0x180007ff6  call    ?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)
0x180007ffb  mov     ebx, eax
0x180007ffd  jmp     short loc_180007FDA
0x180007fff  lea     rax, aTracestatus; "TraceStatus"
0x180008006  mov     ebx, 28h ; '('
0x18000800b  mov     [rbp+psz], rax
0x18000800f  mov     ecx, ebx; cb
0x180008011  lea     rax, aTracelogfilemo; "TraceLogFileMode"
0x180008018  mov     [rbp+var_20], rax
0x18000801c  lea     rax, aTracecontrol; "TraceControl"
0x180008023  mov     [rbp+var_18], rax
0x180008027  lea     rax, aLogfilesizelim; "LogFileSizeLimitMB"
0x18000802e  mov     [rbp+var_10], rax
0x180008032  lea     rax, aProviders; "Providers"
0x180008039  mov     [rbp+var_8], rax
0x18000803d  call    cs:__imp_CoTaskMemAlloc
0x180008044  nop     dword ptr [rax+rax+00h]
0x180008049  mov     rsi, rax
0x18000804c  test    rax, rax
0x18000804f  jz      loc_180007F61
0x180008055  xor     edi, edi
0x180008057  mov     [rax], dil
0x18000805a  inc     rax
0x18000805d  sub     rbx, 1
0x180008061  jnz     short loc_180008057
0x180008063  mov     rcx, [rbp+rdi*8+psz]; psz
0x180008068  call    cs:__imp_SysAllocString
0x18000806f  nop     dword ptr [rax+rax+00h]
0x180008074  mov     [rsi+rdi*8], rax
0x180008078  test    rax, rax
0x18000807b  jz      short loc_180008089
0x18000807d  inc     edi
0x18000807f  cmp     edi, 5
0x180008082  jb      short loc_180008063
0x180008084  jmp     loc_180007F2B
0x180008089  xor     ebx, ebx
0x18000808b  test    edi, edi
0x18000808d  jz      loc_180007F52
0x180008093  mov     rcx, [rsi+rbx*8]; bstrString
0x180008097  call    cs:__imp_SysFreeString
0x18000809e  nop     dword ptr [rax+rax+00h]
0x1800080a3  inc     ebx
0x1800080a5  cmp     ebx, edi
0x1800080a7  jb      short loc_180008093
0x1800080a9  jmp     loc_180007F52
0x1800080ae  lea     rcx, [rbp+var_50]
0x1800080b2  call    ?GetRegisteredCollectorNames@CEtwLogCollector@@SAJPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; CEtwLogCollector::GetRegisteredCollectorNames(ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x1800080b7  mov     ebx, eax
0x1800080b9  test    eax, eax
0x1800080bb  js      short loc_1800080CE
0x1800080bd  lea     r8, [rbp+var_50]
0x1800080c1  mov     rdx, r14
0x1800080c4  mov     rcx, r12
0x1800080c7  call    ?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)
0x1800080cc  mov     ebx, eax
0x1800080ce  mov     r13, qword ptr [rbp+var_50]
0x1800080d2  jmp     loc_180007F66
0x1800080d7  mov     ebx, edx
0x1800080d9  mov     eax, cs:dword_18004AE90
0x1800080df  cmp     eax, 5
0x1800080e2  jbe     short loc_180008115
0x1800080e4  mov     dword ptr [rbp+arg_8], ebx
0x1800080e7  test    r14, r14
0x1800080ea  jz      short loc_1800080F1
0x1800080ec  mov     eax, [r14]
0x1800080ef  jmp     short loc_1800080F4
0x1800080f1  or      eax, 0FFFFFFFFh
0x1800080f4  mov     [rbp+arg_18], eax
0x1800080f7  lea     rdx, byte_18004097B
0x1800080fe  lea     rax, [rbp+arg_8]
0x180008102  mov     [rsp+80h+var_58], rax
0x180008107  lea     rax, [rbp+arg_18]
0x18000810b  mov     [rsp+80h+var_60], rax
0x180008110  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180008115  xor     edi, edi
0x180008117  test    esi, esi
0x180008119  jz      short loc_180008145
0x18000811b  test    edi, edi
0x18000811d  js      loc_18000824C
0x180008123  cmp     edi, esi
0x180008125  jge     loc_18000824C
0x18000812b  movsxd  rcx, edi
0x18000812e  mov     rcx, [r13+rcx*8+0]; bstrString
0x180008133  call    cs:__imp_SysFreeString
0x18000813a  nop     dword ptr [rax+rax+00h]
0x18000813f  inc     edi
0x180008141  cmp     edi, esi
0x180008143  jb      short loc_18000811B
0x180008145  test    r13, r13
0x180008148  jz      short loc_18000815C
0x18000814a  mov     rcx, r13; Block
0x18000814d  call    cs:__imp_free
0x180008154  nop     dword ptr [rax+rax+00h]
0x180008159  xor     r13d, r13d
0x18000815c  mov     esi, dword ptr [rbp+var_30]
0x18000815f  xor     edi, edi
0x180008161  test    esi, esi
0x180008163  jz      short loc_18000818F
0x180008165  test    edi, edi
0x180008167  js      loc_180008257
0x18000816d  cmp     edi, dword ptr [rbp+var_30]
0x180008170  jge     loc_180008257
0x180008176  movsxd  rcx, edi
0x180008179  mov     rcx, [r15+rcx*8]; bstrString
0x18000817d  call    cs:__imp_SysFreeString
0x180008184  nop     dword ptr [rax+rax+00h]
0x180008189  inc     edi
0x18000818b  cmp     edi, esi
0x18000818d  jb      short loc_180008165
0x18000818f  test    r15, r15
0x180008192  jz      short loc_1800081A6
0x180008194  mov     rcx, r15; Block
0x180008197  call    cs:__imp_free
0x18000819e  nop     dword ptr [rax+rax+00h]
0x1800081a3  xor     r15d, r15d
0x1800081a6  mov     ecx, 80000000h
0x1800081ab  lea     eax, [rbx+rcx]
0x1800081ae  test    ecx, eax
0x1800081b0  jnz     short loc_180008206
0x1800081b2  cmp     ebx, 80070057h
0x1800081b8  jz      short loc_180008206
0x1800081ba  mov     rdi, [r12]
0x1800081be  test    rdi, rdi
0x1800081c1  jz      short loc_1800081F7
0x1800081c3  mov     r12d, [r14]
0x1800081c6  xor     esi, esi
0x1800081c8  test    r12d, r12d
0x1800081cb  jz      short loc_1800081E4
0x1800081cd  mov     rcx, [rdi+rsi*8]; bstrString
0x1800081d1  call    cs:__imp_SysFreeString
0x1800081d8  nop     dword ptr [rax+rax+00h]
0x1800081dd  inc     esi
0x1800081df  cmp     esi, r12d
0x1800081e2  jb      short loc_1800081CD
0x1800081e4  mov     rcx, rdi; pv
0x1800081e7  call    cs:__imp_CoTaskMemFree
0x1800081ee  nop     dword ptr [rax+rax+00h]
0x1800081f3  mov     r12, [rbp+arg_10]
0x1800081f7  mov     qword ptr [r12], 0
0x1800081ff  mov     dword ptr [r14], 0
0x180008206  test    r15, r15
0x180008209  jz      short loc_18000821A
0x18000820b  mov     rcx, r15; Block
0x18000820e  call    cs:__imp_free
0x180008215  nop     dword ptr [rax+rax+00h]
0x18000821a  test    r13, r13
0x18000821d  jz      short loc_18000822E
0x18000821f  mov     rcx, r13; Block
0x180008222  call    cs:__imp_free
0x180008229  nop     dword ptr [rax+rax+00h]
0x18000822e  mov     eax, ebx
0x180008230  mov     rbx, [rsp+80h+arg_0]
0x180008238  add     rsp, 80h
0x18000823f  pop     r15
0x180008241  pop     r14
0x180008243  pop     r13
0x180008245  pop     r12
0x180008247  pop     rdi
0x180008248  pop     rsi
0x180008249  pop     rbp
0x18000824a  retn
0x18000824c  mov     ecx, 0C000008Ch; unsigned int
0x180008251  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
0x180008256  int     3; Trap to Debugger
0x180008257  mov     ecx, 0C000008Ch; unsigned int
0x18000825c  call    ?_AtlRaiseException@ATL@@YAXKK@Z; ATL::_AtlRaiseException(ulong,ulong)
```
