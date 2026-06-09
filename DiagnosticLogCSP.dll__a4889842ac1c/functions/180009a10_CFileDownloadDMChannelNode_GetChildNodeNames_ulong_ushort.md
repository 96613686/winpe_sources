# CFileDownloadDMChannelNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180009a10`
- end: `0x18000a001`
- name: `?GetChildNodeNames@CFileDownloadDMChannelNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1521`
- prototype: `__int64 __fastcall(CFileDownloadDMChannelNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x18000108c`
- `0x180001b60`
- `0x18000262c`
- `0x180006518`
- `0x1800073e0`
- `0x1800075ec`
- `0x1800090b4`
- `0x18000967c`
- `0x180009a10`
- `0x18000dbb0`
- `0x18000f170`
- `0x180010ed4`
- `0x18001107c`
- `0x1800116a4`
- `0x180011dd0`
- `0x180037010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009e5d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009ea0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009ee1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009ef3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f7e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f90`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009e5d`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009ea0`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009ee1`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009ef3`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f62`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f70`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f7e`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x180009f90`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180009d46`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180009d46`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009c1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009b5a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009c1b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f40`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009c7b`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f40`
- `OLEAUT32!__imp_SysAllocString` at `0x180009bb8`
- `OLEAUT32!__imp_SysAllocString` at `0x180009c3a`
- `OLEAUT32!__imp_SysAllocString` at `0x180009bb8`
- `OLEAUT32!__imp_SysAllocString` at `0x180009c3a`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c6c`
- `OLEAUT32!__imp_SysFreeString` at `0x180009e48`
- `OLEAUT32!__imp_SysFreeString` at `0x180009e8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180009ecd`
- `OLEAUT32!__imp_SysFreeString` at `0x180009f30`
- `OLEAUT32!__imp_SysFreeString` at `0x180009c6c`
- `OLEAUT32!__imp_SysFreeString` at `0x180009e48`
- `OLEAUT32!__imp_SysFreeString` at `0x180009e8b`
- `OLEAUT32!__imp_SysFreeString` at `0x180009ecd`
- `OLEAUT32!__imp_SysFreeString` at `0x180009f30`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009d8f`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x180009d8f`

## string_xrefs

- `0x180009bfa`: `BlockIndexToRead`

## pseudocode

```c
__int64 __fastcall CFileDownloadDMChannelNode::GetChildNodeNames(
        __int64 this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  HKEY v3; // rsi
  unsigned __int64 v4; // rdi
  int v6; // r14d
  unsigned __int16 *v7; // r13
  int v8; // r15d
  CFileDownloadDMChannelNode *v9; // r9
  int v10; // ecx
  int v11; // ebx
  int BlockCount; // eax
  void *v13; // rax
  int j; // edi
  BSTR v15; // rax
  CFileDownloadDMChannelNode *v16; // r8
  __int64 v17; // rbx
  _BYTE *v18; // rax
  _QWORD *v19; // rsi
  BSTR v20; // rax
  __int64 i; // rbx
  int RegisteredCollectorNames; // eax
  int v23; // ebx
  int RegisteredChannels; // eax
  int v25; // ebx
  char IsStateSeparationEnabled; // al
  const WCHAR *v27; // rcx
  int v28; // eax
  int v29; // eax
  int v30; // ebx
  int v31; // eax
  int k; // edi
  int m; // edi
  int v34; // esi
  int v35; // edi
  BSTR *n; // r15
  CFileDownloadDMChannelNode *v37; // rax
  BSTR *v38; // rsi
  unsigned int v39; // r14d
  __int64 ii; // rdi
  HKEY v42; // [rsp+30h] [rbp-79h]
  int v43; // [rsp+38h] [rbp-71h] BYREF
  CFileDownloadDMChannelNode *v44; // [rsp+40h] [rbp-69h]
  unsigned __int16 *v45; // [rsp+48h] [rbp-61h] BYREF
  __int64 v46; // [rsp+50h] [rbp-59h]
  HKEY hKey[2]; // [rsp+58h] [rbp-51h] BYREF
  __int128 v48; // [rsp+68h] [rbp-41h]
  void *v49[2]; // [rsp+78h] [rbp-31h] BYREF
  void *Block; // [rsp+88h] [rbp-21h]
  void *v51; // [rsp+90h] [rbp-19h] BYREF
  __int64 v52; // [rsp+98h] [rbp-11h]
  OLECHAR psz[4]; // [rsp+A0h] [rbp-9h] BYREF
  const wchar_t *v54; // [rsp+A8h] [rbp-1h]
  const unsigned __int16 *v55; // [rsp+B0h] [rbp+7h]
  const wchar_t *v56; // [rsp+B8h] [rbp+Fh]
  const wchar_t *v57; // [rsp+C0h] [rbp+17h]

  v3 = 0;
  v44 = (CFileDownloadDMChannelNode *)a3;
  v4 = 0;
  v42 = 0;
  hKey[0] = 0;
  v6 = 0;
  Block = 0;
  v7 = 0;
  hKey[1] = 0;
  v8 = 0;
  v45 = 0;
  v46 = 0;
  v9 = (CFileDownloadDMChannelNode *)this;
  v51 = 0;
  v52 = 0;
  v49[0] = 0;
  v49[1] = 0;
  if ( !a2 || !a3 )
  {
LABEL_60:
    v11 = -2147024809;
    goto LABEL_61;
  }
  *a2 = 0;
  *a3 = 0;
  v10 = *(_DWORD *)(this + 44) - 21;
  if ( v10 )
  {
    this = (unsigned int)(v10 - 1);
    if ( !(_DWORD)this )
    {
      v17 = 40;
      *(_QWORD *)psz = L"BlockSizeKB";
      v54 = L"BlockCount";
      v55 = L"BlockIndexToRead";
      v56 = L"BlockData";
      v57 = L"DataBlocks";
      v18 = CoTaskMemAlloc(0x28u);
      v19 = v18;
      if ( v18 )
      {
        do
        {
          *v18++ = 0;
          --v17;
        }
        while ( v17 );
        while ( 1 )
        {
          v20 = SysAllocString(*(const OLECHAR **)&psz[4 * v4]);
          v19[v4] = v20;
          if ( !v20 )
            break;
          v4 = (unsigned int)(v4 + 1);
          if ( (unsigned int)v4 >= 5 )
          {
            this = (__int64)v44;
            v11 = 0;
            *(_QWORD *)v44 = v19;
            *a2 = v4;
            goto LABEL_19;
          }
        }
        for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
          SysFreeString((BSTR)v19[i]);
        CoTaskMemFree(v19);
      }
      v11 = -2147024882;
LABEL_19:
      v3 = 0;
      goto LABEL_61;
    }
    if ( (_DWORD)this != 5 )
    {
      *a2 = 0;
      *a3 = 0;
      v11 = -2046820335;
      goto LABEL_61;
    }
    this = *((_QWORD *)v9 + 3);
    if ( this )
    {
      v45 = 0;
      v11 = (*(__int64 (__fastcall **)(__int64, __int64, unsigned __int16 **))(*(_QWORD *)this + 88LL))(this, 3, &v45);
      if ( v11 < 0 )
        goto LABEL_61;
      *(_OWORD *)hKey = 0;
      v48 = 0;
      v11 = CFileDownload_DMChannel::Initialize((CFileDownload_DMChannel *)hKey, v45, (int)a3, (int)v9);
      if ( v11 < 0 )
        goto LABEL_10;
      v43 = 0;
      BlockCount = CFileDownload_DMChannel::GetBlockCount((CFileDownload_DMChannel *)hKey, &v43);
      v11 = BlockCount;
      if ( BlockCount >= 0 )
      {
        LODWORD(v3) = v43;
      }
      else
      {
        if ( BlockCount != -2147019873 && BlockCount != -2147024894 )
        {
LABEL_10:
          CFileDownload_DMChannel::~CFileDownload_DMChannel(hKey);
          goto LABEL_61;
        }
        v11 = 0;
      }
      v13 = CoTaskMemAlloc(8LL * (int)v3);
      *(_QWORD *)v44 = v13;
      if ( v13 )
      {
        memset_0(v13, 0, 8LL * (int)v3);
        for ( j = 0; j < (int)v3; ++j )
        {
          v11 = StringCchPrintfW(psz, 0x10u, L"%d", (unsigned int)j);
          if ( v11 < 0 )
            break;
          v15 = SysAllocString(psz);
          v16 = v44;
          *(_QWORD *)(*(_QWORD *)v44 + 8LL * j) = v15;
          if ( !*(_QWORD *)v16 )
            goto LABEL_17;
          ++*a2;
        }
      }
      else
      {
LABEL_17:
        v11 = -2147024882;
      }
      CFileDownload_DMChannel::~CFileDownload_DMChannel(hKey);
      goto LABEL_19;
    }
    goto LABEL_60;
  }
  RegisteredCollectorNames = CEtwLogCollector::GetRegisteredCollectorNames(hKey, 2147942487LL, a3, v9);
  v3 = hKey[0];
  v11 = RegisteredCollectorNames;
  v6 = (int)hKey[1];
  v42 = hKey[0];
  if ( RegisteredCollectorNames < 0 )
    goto LABEL_61;
  v23 = 0;
  if ( LODWORD(hKey[1]) )
  {
    do
    {
      if ( v23 < 0 || v23 >= v6 )
      {
        ATL::_AtlRaiseException(0xC000008C);
        __debugbreak();
      }
      if ( !(unsigned int)ATL::CSimpleArray<unsigned short *,ATL::CSimpleArrayEqualHelper<unsigned short *>>::Add(
                            v49,
                            v3 + 2 * v23) )
        goto LABEL_59;
    }
    while ( ++v23 < (unsigned int)v6 );
  }
  RegisteredChannels = CEventLogChannel::GetRegisteredChannels(&v45);
  v8 = v46;
  v11 = RegisteredChannels;
  v7 = v45;
  if ( RegisteredChannels < 0 )
    goto LABEL_61;
  v25 = 0;
  if ( (_DWORD)v46 )
  {
    while ( 1 )
    {
      if ( v25 < 0 || v25 >= v8 )
      {
        ATL::_AtlRaiseException(0xC000008C);
        __debugbreak();
      }
      if ( !(unsigned int)ATL::CSimpleArray<unsigned short *,ATL::CSimpleArrayEqualHelper<unsigned short *>>::Add(
                            v49,
                            &v7[4 * v25]) )
        break;
      if ( ++v25 >= (unsigned int)v8 )
        goto LABEL_46;
    }
LABEL_59:
    v11 = -2147418113;
    goto LABEL_61;
  }
LABEL_46:
  hKey[0] = 0;
  hKey[1] = 0;
  *(_QWORD *)&v48 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v27 = L"OSData\\SOFTWARE\\Microsoft\\DiagnosticLogCSP\\DeviceStateData";
  if ( !IsStateSeparationEnabled )
    v27 = L"SOFTWARE\\Microsoft\\DiagnosticLogCSP\\DeviceStateData";
  v11 = CRegUtils::OpenKey(v27, (struct ATL::CRegKey *)hKey);
  if ( v11 >= 0 )
  {
    v28 = CRegUtils::EnumChildKeys(hKey, &v51);
    v4 = (unsigned __int64)v51;
    v11 = v28;
    Block = v51;
  }
  this = (__int64)hKey[0];
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( v11 >= 0 )
  {
    v29 = v52;
    v30 = 0;
    if ( !(_DWORD)v52 )
    {
LABEL_58:
      v11 = ConstructBSTRArray(v44, a2, (__int64)v49);
      goto LABEL_61;
    }
    while ( 1 )
    {
      if ( v30 < 0 || v30 >= v29 )
      {
        ATL::_AtlRaiseException(0xC000008C);
        __debugbreak();
      }
      if ( !(unsigned int)ATL::CSimpleArray<unsigned short *,ATL::CSimpleArrayEqualHelper<unsigned short *>>::Add(
                            v49,
                            v4 + 8LL * v30) )
        goto LABEL_59;
      v29 = v52;
      if ( ++v30 >= (unsigned int)v52 )
        goto LABEL_58;
    }
  }
LABEL_61:
  if ( (unsigned int)dword_180048E90 > 5 )
  {
    v43 = v11;
    if ( a2 )
      v31 = *a2;
    else
      v31 = -1;
    LODWORD(v45) = v31;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      this,
      (__int64)&unk_18003ED78,
      (__int64)a3,
      (__int64)v9,
      (__int64)&v45,
      (__int64)&v43);
  }
  for ( k = 0; k < (unsigned int)v6; ++k )
  {
    if ( k < 0 || k >= v6 )
    {
      ATL::_AtlRaiseException(0xC000008C);
      JUMPOUT(0x18000A000LL);
    }
    SysFreeString(*((BSTR *)v3 + k));
  }
  if ( v3 )
  {
    free(v3);
    v42 = 0;
  }
  for ( m = 0; m < (unsigned int)v8; ++m )
  {
    if ( m < 0 || m >= v8 )
    {
      ATL::_AtlRaiseException(0xC000008C);
      __debugbreak();
    }
    SysFreeString(*(BSTR *)&v7[4 * m]);
  }
  if ( v7 )
    free(v7);
  v34 = v52;
  v35 = 0;
  for ( n = (BSTR *)Block; v35 < (unsigned int)v34; ++v35 )
  {
    if ( v35 < 0 || v35 >= v34 )
    {
      ATL::_AtlRaiseException(0xC000008C);
      __debugbreak();
    }
    SysFreeString(n[v35]);
  }
  if ( n )
    free(n);
  if ( v49[0] )
  {
    free(v49[0]);
    v49[0] = 0;
  }
  if ( (int)(v11 + 0x80000000) >= 0 && v11 != -2147024809 )
  {
    v37 = v44;
    v38 = *(BSTR **)v44;
    if ( *(_QWORD *)v44 )
    {
      v39 = *a2;
      for ( ii = 0; (unsigned int)ii < v39; ii = (unsigned int)(ii + 1) )
        SysFreeString(v38[ii]);
      CoTaskMemFree(v38);
      v37 = v44;
    }
    *(_QWORD *)v37 = 0;
    *a2 = 0;
  }
  if ( v49[0] )
    free(v49[0]);
  if ( v42 )
    free(v42);
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180009a10  mov     [rsp-8+arg_18], rbx
0x180009a15  push    rbp
0x180009a16  push    rsi
0x180009a17  push    rdi
0x180009a18  push    r12
0x180009a1a  push    r13
0x180009a1c  push    r14
0x180009a1e  push    r15
0x180009a20  lea     rbp, [rsp-27h]
0x180009a25  sub     rsp, 0D0h
0x180009a2c  mov     rax, cs:__security_cookie
0x180009a33  xor     rax, rsp
0x180009a36  mov     [rbp+57h+var_38], rax
0x180009a3a  xor     esi, esi
0x180009a3c  mov     [rbp+57h+var_C0], r8
0x180009a40  xor     edi, edi
0x180009a42  mov     [rbp+57h+var_D0], rsi
0x180009a46  mov     r12, rdx
0x180009a49  mov     [rbp+57h+hKey], rsi
0x180009a4d  xor     r14d, r14d
0x180009a50  mov     [rbp+57h+Block], rdi
0x180009a54  xor     r13d, r13d
0x180009a57  mov     [rbp+57h+hKey+8], r14
0x180009a5b  xor     r15d, r15d
0x180009a5e  mov     [rbp+57h+var_B8], r13
0x180009a62  mov     [rbp+57h+var_B0], r15
0x180009a66  mov     r9, rcx
0x180009a69  mov     [rbp+57h+var_70], rdi
0x180009a6d  mov     edx, 80070057h
0x180009a72  mov     [rbp+57h+var_68], rsi
0x180009a76  mov     [rbp+57h+var_88], rsi
0x180009a7a  mov     [rbp+57h+var_80], rsi
0x180009a7e  test    r12, r12
0x180009a81  jz      loc_180009DEA
0x180009a87  test    r8, r8
0x180009a8a  jz      loc_180009DEA
0x180009a90  mov     [r12], esi
0x180009a94  mov     [r8], rsi
0x180009a97  mov     ecx, [rcx+2Ch]
0x180009a9a  sub     ecx, 15h
0x180009a9d  jz      loc_180009C8B
0x180009aa3  sub     ecx, 1
0x180009aa6  jz      loc_180009BDD
0x180009aac  cmp     ecx, 5
0x180009aaf  jz      short loc_180009AC2
0x180009ab1  mov     [r12], esi
0x180009ab5  mov     [r8], rsi
0x180009ab8  mov     ebx, 86000011h
0x180009abd  jmp     loc_180009DEC
0x180009ac2  mov     rcx, [r9+18h]
0x180009ac6  test    rcx, rcx
0x180009ac9  jz      loc_180009DEA
0x180009acf  mov     [rbp+57h+var_B8], rsi
0x180009ad3  lea     r8, [rbp+57h+var_B8]
0x180009ad7  mov     rax, [rcx]
0x180009ada  mov     edx, 3
0x180009adf  mov     rax, [rax+58h]
0x180009ae3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009ae8  mov     ebx, eax
0x180009aea  test    eax, eax
0x180009aec  js      loc_180009DEC
0x180009af2  mov     rdx, [rbp+57h+var_B8]; unsigned __int16 *
0x180009af6  lea     rcx, [rbp+57h+hKey]; this
0x180009afa  xorps   xmm0, xmm0
0x180009afd  xorps   xmm1, xmm1
0x180009b00  movdqu  xmmword ptr [rbp+57h+hKey], xmm0
0x180009b05  movdqu  [rbp+57h+var_98], xmm1
0x180009b0a  call    ?Initialize@CFileDownload_DMChannel@@QEAAJPEBG@Z; CFileDownload_DMChannel::Initialize(ushort const *)
0x180009b0f  lea     rcx, [rbp+57h+hKey]; this
0x180009b13  mov     ebx, eax
0x180009b15  test    eax, eax
0x180009b17  jns     short loc_180009B23
0x180009b19  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180009b1e  jmp     loc_180009DEC
0x180009b23  lea     rdx, [rbp+57h+var_C8]; int *
0x180009b27  mov     [rbp+57h+var_C8], esi
0x180009b2a  call    ?GetBlockCount@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockCount(long &)
0x180009b2f  mov     ebx, eax
0x180009b31  test    eax, eax
0x180009b33  jns     short loc_180009B4D
0x180009b35  cmp     eax, 8007139Fh
0x180009b3a  jz      short loc_180009B49
0x180009b3c  cmp     eax, 80070002h
0x180009b41  jz      short loc_180009B49
0x180009b43  lea     rcx, [rbp+57h+hKey]
0x180009b47  jmp     short loc_180009B19
0x180009b49  xor     ebx, ebx
0x180009b4b  jmp     short loc_180009B50
0x180009b4d  mov     esi, [rbp+57h+var_C8]
0x180009b50  movsxd  rdi, esi
0x180009b53  shl     rdi, 3
0x180009b57  mov     rcx, rdi; cb
0x180009b5a  call    cs:__imp_CoTaskMemAlloc
0x180009b60  mov     rcx, [rbp+57h+var_C0]
0x180009b64  mov     [rcx], rax
0x180009b67  test    rax, rax
0x180009b6a  jnz     short loc_180009B83
0x180009b6c  mov     ebx, 8007000Eh
0x180009b71  lea     rcx, [rbp+57h+hKey]; this
0x180009b75  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180009b7a  mov     rsi, [rbp+57h+var_D0]
0x180009b7e  jmp     loc_180009DEC
0x180009b83  mov     r8, rdi; Size
0x180009b86  xor     edx, edx; Val
0x180009b88  mov     rcx, rax; void *
0x180009b8b  call    memset_0
0x180009b90  xor     edi, edi
0x180009b92  test    esi, esi
0x180009b94  jle     short loc_180009B71
0x180009b96  mov     r9d, edi
0x180009b99  lea     r8, aD; "%d"
0x180009ba0  mov     edx, 10h; unsigned __int64
0x180009ba5  lea     rcx, [rbp+57h+psz]; unsigned __int16 *
0x180009ba9  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009bae  mov     ebx, eax
0x180009bb0  test    eax, eax
0x180009bb2  js      short loc_180009B71
0x180009bb4  lea     rcx, [rbp+57h+psz]; psz
0x180009bb8  call    cs:__imp_SysAllocString
0x180009bbe  mov     r8, [rbp+57h+var_C0]
0x180009bc2  movsxd  rdx, edi
0x180009bc5  mov     rcx, [r8]
0x180009bc8  mov     [rcx+rdx*8], rax
0x180009bcc  cmp     [r8], r13
0x180009bcf  jz      short loc_180009B6C
0x180009bd1  inc     dword ptr [r12]
0x180009bd5  inc     edi
0x180009bd7  cmp     edi, esi
0x180009bd9  jl      short loc_180009B96
0x180009bdb  jmp     short loc_180009B71
0x180009bdd  lea     rax, aBlocksizekb; "BlockSizeKB"
0x180009be4  mov     ebx, 28h ; '('
0x180009be9  mov     qword ptr [rbp+57h+psz], rax
0x180009bed  mov     ecx, ebx; cb
0x180009bef  lea     rax, aBlockcount; "BlockCount"
0x180009bf6  mov     [rbp+57h+var_58], rax
0x180009bfa  lea     rax, aBlockindextore; "BlockIndexToRead"
0x180009c01  mov     [rbp+57h+var_50], rax
0x180009c05  lea     rax, aBlockdata; "BlockData"
0x180009c0c  mov     [rbp+57h+var_48], rax
0x180009c10  lea     rax, aDatablocks; "DataBlocks"
0x180009c17  mov     [rbp+57h+var_40], rax
0x180009c1b  call    cs:__imp_CoTaskMemAlloc
0x180009c21  mov     rsi, rax
0x180009c24  test    rax, rax
0x180009c27  jz      short loc_180009C81
0x180009c29  mov     [rax], dil
0x180009c2c  inc     rax
0x180009c2f  sub     rbx, 1
0x180009c33  jnz     short loc_180009C29
0x180009c35  mov     rcx, qword ptr [rbp+rdi*8+57h+psz]; psz
0x180009c3a  call    cs:__imp_SysAllocString
0x180009c40  mov     [rsi+rdi*8], rax
0x180009c44  test    rax, rax
0x180009c47  jz      short loc_180009C62
0x180009c49  inc     edi
0x180009c4b  cmp     edi, 5
0x180009c4e  jb      short loc_180009C35
0x180009c50  mov     rcx, [rbp+57h+var_C0]
0x180009c54  xor     ebx, ebx
0x180009c56  mov     [rcx], rsi
0x180009c59  mov     [r12], edi
0x180009c5d  jmp     loc_180009B7A
0x180009c62  xor     ebx, ebx
0x180009c64  test    edi, edi
0x180009c66  jz      short loc_180009C78
0x180009c68  mov     rcx, [rsi+rbx*8]; bstrString
0x180009c6c  call    cs:__imp_SysFreeString
0x180009c72  inc     ebx
0x180009c74  cmp     ebx, edi
0x180009c76  jb      short loc_180009C68
0x180009c78  mov     rcx, rsi; pv
0x180009c7b  call    cs:__imp_CoTaskMemFree
0x180009c81  mov     ebx, 8007000Eh
0x180009c86  jmp     loc_180009B7A
0x180009c8b  lea     rcx, [rbp+57h+hKey]
0x180009c8f  call    ?GetRegisteredCollectorNames@CEtwLogCollector@@SAJPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; CEtwLogCollector::GetRegisteredCollectorNames(ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x180009c94  mov     rsi, [rbp+57h+hKey]
0x180009c98  mov     ebx, eax
0x180009c9a  mov     r14d, dword ptr [rbp+57h+hKey+8]
0x180009c9e  mov     [rbp+57h+var_D0], rsi
0x180009ca2  test    eax, eax
0x180009ca4  js      loc_180009DEC
0x180009caa  xor     ebx, ebx
0x180009cac  test    r14d, r14d
0x180009caf  jz      short loc_180009CE1
0x180009cb1  test    ebx, ebx
0x180009cb3  js      loc_180009FD5
0x180009cb9  cmp     ebx, r14d
0x180009cbc  jge     loc_180009FD5
0x180009cc2  movsxd  rax, ebx
0x180009cc5  lea     rcx, [rbp+57h+var_88]
0x180009cc9  lea     rdx, [rsi+rax*8]
0x180009ccd  call    ?Add@?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@QEAAHAEBQEAG@Z; ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>>::Add(ushort * const &)
0x180009cd2  test    eax, eax
0x180009cd4  jz      loc_180009DE3
0x180009cda  inc     ebx
0x180009cdc  cmp     ebx, r14d
0x180009cdf  jb      short loc_180009CB1
0x180009ce1  lea     rcx, [rbp+57h+var_B8]
0x180009ce5  call    ?GetRegisteredChannels@CEventLogChannel@@SAJPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; CEventLogChannel::GetRegisteredChannels(ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x180009cea  mov     r15d, dword ptr [rbp+57h+var_B0]
0x180009cee  mov     ebx, eax
0x180009cf0  mov     r13, [rbp+57h+var_B8]
0x180009cf4  test    eax, eax
0x180009cf6  js      loc_180009DEC
0x180009cfc  xor     ebx, ebx
0x180009cfe  test    r15d, r15d
0x180009d01  jz      short loc_180009D3A
0x180009d03  test    ebx, ebx
0x180009d05  js      loc_180009FE0
0x180009d0b  cmp     ebx, r15d
0x180009d0e  jge     loc_180009FE0
0x180009d14  movsxd  rax, ebx
0x180009d17  lea     rcx, [rbp+57h+var_88]
0x180009d1b  lea     rdx, ds:0[rax*8]
0x180009d23  add     rdx, r13
0x180009d26  call    ?Add@?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@QEAAHAEBQEAG@Z; ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>>::Add(ushort * const &)
0x180009d2b  test    eax, eax
0x180009d2d  jz      loc_180009DE3
0x180009d33  inc     ebx
0x180009d35  cmp     ebx, r15d
0x180009d38  jb      short loc_180009D03
0x180009d3a  mov     [rbp+57h+hKey], rdi
0x180009d3e  mov     [rbp+57h+hKey+8], rdi
0x180009d42  mov     qword ptr [rbp+57h+var_98], rdi
0x180009d46  call    cs:__imp_RtlIsStateSeparationEnabled
0x180009d4c  test    al, al
0x180009d4e  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\DiagnosticLogCSP\\"...
0x180009d55  lea     rcx, aOsdataSoftware; "OSData\\SOFTWARE\\Microsoft\\Diagnostic"...
0x180009d5c  cmovz   rcx, rdx; lpSubKey
0x180009d60  lea     rdx, [rbp+57h+hKey]; struct ATL::CRegKey *
0x180009d64  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x180009d69  mov     ebx, eax
0x180009d6b  test    eax, eax
0x180009d6d  js      short loc_180009D86
0x180009d6f  lea     rdx, [rbp+57h+var_70]
0x180009d73  lea     rcx, [rbp+57h+hKey]
0x180009d77  call    ?EnumChildKeys@CRegUtils@@SAJAEAVCRegKey@ATL@@PEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@3@@Z; CRegUtils::EnumChildKeys(ATL::CRegKey &,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x180009d7c  mov     rdi, [rbp+57h+var_70]
0x180009d80  mov     ebx, eax
0x180009d82  mov     [rbp+57h+Block], rdi
0x180009d86  mov     rcx, [rbp+57h+hKey]; hKey
0x180009d8a  test    rcx, rcx
0x180009d8d  jz      short loc_180009D95
0x180009d8f  call    cs:__imp_RegCloseKey
0x180009d95  test    ebx, ebx
0x180009d97  js      short loc_180009DEC
0x180009d99  mov     eax, dword ptr [rbp+57h+var_68]
0x180009d9c  xor     ebx, ebx
0x180009d9e  test    eax, eax
0x180009da0  jz      short loc_180009DCF
0x180009da2  test    ebx, ebx
0x180009da4  js      loc_180009FEB
0x180009daa  cmp     ebx, eax
0x180009dac  jge     loc_180009FEB
0x180009db2  movsxd  rax, ebx
0x180009db5  lea     rcx, [rbp+57h+var_88]
0x180009db9  lea     rdx, [rdi+rax*8]
0x180009dbd  call    ?Add@?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@QEAAHAEBQEAG@Z; ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>>::Add(ushort * const &)
0x180009dc2  test    eax, eax
0x180009dc4  jz      short loc_180009DE3
0x180009dc6  mov     eax, dword ptr [rbp+57h+var_68]
0x180009dc9  inc     ebx
0x180009dcb  cmp     ebx, eax
0x180009dcd  jb      short loc_180009DA2
0x180009dcf  mov     rcx, [rbp+57h+var_C0]
0x180009dd3  lea     r8, [rbp+57h+var_88]
0x180009dd7  mov     rdx, r12
0x180009dda  call    ?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)
0x180009ddf  mov     ebx, eax
0x180009de1  jmp     short loc_180009DEC
0x180009de3  mov     ebx, 8000FFFFh
0x180009de8  jmp     short loc_180009DEC
0x180009dea  mov     ebx, edx
0x180009dec  mov     eax, cs:dword_180048E90
0x180009df2  cmp     eax, 5
0x180009df5  jbe     short loc_180009E29
0x180009df7  mov     [rbp+57h+var_C8], ebx
0x180009dfa  test    r12, r12
0x180009dfd  jz      short loc_180009E05
0x180009dff  mov     eax, [r12]
0x180009e03  jmp     short loc_180009E08
0x180009e05  or      eax, 0FFFFFFFFh
0x180009e08  mov     dword ptr [rbp+57h+var_B8], eax
0x180009e0b  lea     rdx, unk_18003ED78
0x180009e12  lea     rax, [rbp+57h+var_C8]
0x180009e16  mov     [rsp+100h+var_D8], rax
0x180009e1b  lea     rax, [rbp+57h+var_B8]
0x180009e1f  mov     [rsp+100h+var_E0], rax
0x180009e24  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180009e29  xor     edi, edi
0x180009e2b  test    r14d, r14d
0x180009e2e  jz      short loc_180009E55
0x180009e30  test    edi, edi
0x180009e32  js      loc_180009FF6
0x180009e38  cmp     edi, r14d
0x180009e3b  jge     loc_180009FF6
0x180009e41  movsxd  rcx, edi
0x180009e44  mov     rcx, [rsi+rcx*8]; bstrString
  ... truncated ...
```
