# CFileDownloadDMChannelNode::GetChildNodeNames(ulong *,ushort * * *)

- ea: `0x180009ca0`
- end: `0x18000a310`
- name: `?GetChildNodeNames@CFileDownloadDMChannelNode@@UEAAJPEAKPEAPEAPEAG@Z`
- size: `1648`
- prototype: `__int64 __fastcall(CFileDownloadDMChannelNode *__hidden this, unsigned int *, unsigned __int16 ***)`
- caller_count: `0`
- callee_count: `16`
- tags: `registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001090`
- `0x180001b90`
- `0x18000265c`
- `0x180006498`
- `0x180007530`
- `0x18000774c`
- `0x1800092f8`
- `0x18000990c`
- `0x180009ca0`
- `0x18000e278`
- `0x18000f8cc`
- `0x180011770`
- `0x180011930`
- `0x180011fe0`
- `0x180012774`
- `0x180039010`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a123`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a172`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a1bf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a1d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a258`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a26c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a280`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a298`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a123`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a172`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a1bf`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a1d7`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a258`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a26c`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a280`
- `api-ms-win-crt-private-l1-1-0!_o_free` at `0x18000a298`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180009ffa`
- `ntdll!RtlIsStateSeparationEnabled` at `0x180009ffa`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009dea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009eb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009dea`
- `api-ms-win-core-com-l1-1-0!CoTaskMemAlloc` at `0x180009eb7`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a230`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180009f29`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18000a230`
- `OLEAUT32!__imp_SysAllocString` at `0x180009e4e`
- `OLEAUT32!__imp_SysAllocString` at `0x180009edc`
- `OLEAUT32!__imp_SysAllocString` at `0x180009e4e`
- `OLEAUT32!__imp_SysAllocString` at `0x180009edc`
- `OLEAUT32!__imp_SysFreeString` at `0x180009f14`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a108`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a157`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a1a5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a21a`
- `OLEAUT32!__imp_SysFreeString` at `0x180009f14`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a108`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a157`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a1a5`
- `OLEAUT32!__imp_SysFreeString` at `0x18000a21a`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a049`
- `api-ms-win-core-registry-l1-1-0!RegCloseKey` at `0x18000a049`

## string_xrefs

- `0x180009e96`: `BlockIndexToRead`

## pseudocode

```c
__int64 __fastcall CFileDownloadDMChannelNode::GetChildNodeNames(
        CFileDownloadDMChannelNode *this,
        unsigned int *a2,
        unsigned __int16 ***a3)
{
  HKEY v3; // rsi
  unsigned __int64 v4; // rdi
  int v6; // r14d
  unsigned __int16 *v7; // r13
  int v8; // r15d
  CFileDownloadDMChannelNode *v9; // r9
  unsigned int v10; // edx
  int v11; // ecx
  int v12; // ebx
  int BlockCount; // eax
  unsigned __int16 **v14; // rax
  int j; // edi
  BSTR v16; // rax
  unsigned __int16 ***v17; // r8
  __int64 v18; // rbx
  unsigned __int16 **v19; // rax
  unsigned __int16 **v20; // rsi
  BSTR v21; // rax
  __int64 i; // rbx
  int RegisteredCollectorNames; // eax
  int v24; // ebx
  int RegisteredChannels; // eax
  int v26; // ebx
  char IsStateSeparationEnabled; // al
  const WCHAR *v28; // rcx
  int v29; // eax
  int v30; // eax
  int v31; // ebx
  int v32; // eax
  int k; // edi
  int m; // edi
  int v35; // esi
  int v36; // edi
  BSTR *n; // r15
  unsigned __int16 ***v38; // rax
  unsigned __int16 **v39; // rsi
  unsigned int v40; // r14d
  __int64 ii; // rdi
  HKEY v43; // [rsp+30h] [rbp-79h]
  int v44; // [rsp+38h] [rbp-71h] BYREF
  unsigned __int16 ***v45; // [rsp+40h] [rbp-69h]
  unsigned __int16 *v46; // [rsp+48h] [rbp-61h] BYREF
  __int64 v47; // [rsp+50h] [rbp-59h]
  HKEY hKey[2]; // [rsp+58h] [rbp-51h] BYREF
  __int128 v49; // [rsp+68h] [rbp-41h]
  void *v50[2]; // [rsp+78h] [rbp-31h] BYREF
  void *Block; // [rsp+88h] [rbp-21h]
  void *v52; // [rsp+90h] [rbp-19h] BYREF
  __int64 v53; // [rsp+98h] [rbp-11h]
  OLECHAR psz[4]; // [rsp+A0h] [rbp-9h] BYREF
  const wchar_t *v55; // [rsp+A8h] [rbp-1h]
  const unsigned __int16 *v56; // [rsp+B0h] [rbp+7h]
  const wchar_t *v57; // [rsp+B8h] [rbp+Fh]
  const wchar_t *v58; // [rsp+C0h] [rbp+17h]

  v3 = 0;
  v45 = a3;
  v4 = 0;
  v43 = 0;
  hKey[0] = 0;
  v6 = 0;
  Block = 0;
  v7 = 0;
  hKey[1] = 0;
  v8 = 0;
  v46 = 0;
  v47 = 0;
  v9 = this;
  v52 = 0;
  v10 = -2147024809;
  v53 = 0;
  v50[0] = 0;
  v50[1] = 0;
  if ( !a2 || !a3 )
  {
LABEL_60:
    v12 = -2147024809;
    goto LABEL_61;
  }
  *a2 = 0;
  *a3 = 0;
  v11 = *((_DWORD *)this + 11) - 21;
  if ( v11 )
  {
    LODWORD(this) = v11 - 1;
    if ( !(_DWORD)this )
    {
      v18 = 40;
      *(_QWORD *)psz = L"BlockSizeKB";
      v55 = L"BlockCount";
      v56 = L"BlockIndexToRead";
      v57 = L"BlockData";
      v58 = L"DataBlocks";
      v19 = (unsigned __int16 **)CoTaskMemAlloc(0x28u);
      v20 = v19;
      if ( v19 )
      {
        do
        {
          *(_BYTE *)v19 = 0;
          v19 = (unsigned __int16 **)((char *)v19 + 1);
          --v18;
        }
        while ( v18 );
        while ( 1 )
        {
          v21 = SysAllocString(*(const OLECHAR **)&psz[4 * v4]);
          v20[v4] = v21;
          if ( !v21 )
            break;
          v4 = (unsigned int)(v4 + 1);
          if ( (unsigned int)v4 >= 5 )
          {
            LODWORD(this) = (_DWORD)v45;
            v12 = 0;
            *v45 = v20;
            *a2 = v4;
            goto LABEL_19;
          }
        }
        for ( i = 0; (unsigned int)i < (unsigned int)v4; i = (unsigned int)(i + 1) )
          SysFreeString(v20[i]);
        CoTaskMemFree(v20);
      }
      v12 = -2147024882;
LABEL_19:
      v3 = 0;
      goto LABEL_61;
    }
    if ( (_DWORD)this != 5 )
    {
      *a2 = 0;
      *a3 = 0;
      v12 = -2046820335;
      goto LABEL_61;
    }
    this = (CFileDownloadDMChannelNode *)*((_QWORD *)v9 + 3);
    if ( this )
    {
      v46 = 0;
      v12 = (*(__int64 (__fastcall **)(CFileDownloadDMChannelNode *, __int64, unsigned __int16 **))(*(_QWORD *)this
                                                                                                  + 88LL))(
              this,
              3,
              &v46);
      if ( v12 < 0 )
        goto LABEL_61;
      *(_OWORD *)hKey = 0;
      v49 = 0;
      v12 = CFileDownload_DMChannel::Initialize((CFileDownload_DMChannel *)hKey, v46);
      if ( v12 < 0 )
        goto LABEL_10;
      v44 = 0;
      BlockCount = CFileDownload_DMChannel::GetBlockCount((CFileDownload_DMChannel *)hKey, (DWORD *)&v44);
      v12 = BlockCount;
      if ( BlockCount >= 0 )
      {
        LODWORD(v3) = v44;
      }
      else
      {
        if ( BlockCount != -2147019873 && BlockCount != -2147024894 )
        {
LABEL_10:
          CFileDownload_DMChannel::~CFileDownload_DMChannel((CFileDownload_DMChannel *)hKey);
          goto LABEL_61;
        }
        v12 = 0;
      }
      v14 = (unsigned __int16 **)CoTaskMemAlloc(8LL * (int)v3);
      *v45 = v14;
      if ( v14 )
      {
        memset_0(v14, 0, 8LL * (int)v3);
        for ( j = 0; j < (int)v3; ++j )
        {
          v12 = StringCchPrintfW(psz, 0x10u, L"%d", (unsigned int)j);
          if ( v12 < 0 )
            break;
          v16 = SysAllocString(psz);
          v17 = v45;
          (*v45)[j] = v16;
          if ( !*v17 )
            goto LABEL_17;
          ++*a2;
        }
      }
      else
      {
LABEL_17:
        v12 = -2147024882;
      }
      CFileDownload_DMChannel::~CFileDownload_DMChannel((CFileDownload_DMChannel *)hKey);
      goto LABEL_19;
    }
    goto LABEL_60;
  }
  RegisteredCollectorNames = CEtwLogCollector::GetRegisteredCollectorNames(hKey, 2147942487LL, a3, v9);
  v3 = hKey[0];
  v12 = RegisteredCollectorNames;
  v6 = (int)hKey[1];
  v43 = hKey[0];
  if ( RegisteredCollectorNames < 0 )
    goto LABEL_61;
  v24 = 0;
  if ( LODWORD(hKey[1]) )
  {
    do
    {
      if ( v24 < 0 || v24 >= v6 )
      {
        ATL::_AtlRaiseException(0xC000008C, v10);
        __debugbreak();
      }
      if ( !(unsigned int)ATL::CSimpleArray<unsigned short *,ATL::CSimpleArrayEqualHelper<unsigned short *>>::Add(
                            v50,
                            v3 + 2 * v24) )
        goto LABEL_59;
    }
    while ( ++v24 < (unsigned int)v6 );
  }
  RegisteredChannels = CEventLogChannel::GetRegisteredChannels(&v46);
  v8 = v47;
  v12 = RegisteredChannels;
  v7 = v46;
  if ( RegisteredChannels < 0 )
    goto LABEL_61;
  v26 = 0;
  if ( (_DWORD)v47 )
  {
    while ( 1 )
    {
      if ( v26 < 0 || v26 >= v8 )
      {
        ATL::_AtlRaiseException(0xC000008C, v10);
        __debugbreak();
      }
      if ( !(unsigned int)ATL::CSimpleArray<unsigned short *,ATL::CSimpleArrayEqualHelper<unsigned short *>>::Add(
                            v50,
                            &v7[4 * v26]) )
        break;
      if ( ++v26 >= (unsigned int)v8 )
        goto LABEL_46;
    }
LABEL_59:
    v12 = -2147418113;
    goto LABEL_61;
  }
LABEL_46:
  hKey[0] = 0;
  hKey[1] = 0;
  *(_QWORD *)&v49 = 0;
  IsStateSeparationEnabled = RtlIsStateSeparationEnabled();
  v28 = L"OSData\\SOFTWARE\\Microsoft\\DiagnosticLogCSP\\DeviceStateData";
  if ( !IsStateSeparationEnabled )
    v28 = L"SOFTWARE\\Microsoft\\DiagnosticLogCSP\\DeviceStateData";
  v12 = CRegUtils::OpenKey(v28, (struct ATL::CRegKey *)hKey);
  if ( v12 >= 0 )
  {
    v29 = CRegUtils::EnumChildKeys(hKey, &v52);
    v4 = (unsigned __int64)v52;
    v12 = v29;
    Block = v52;
  }
  LODWORD(this) = hKey[0];
  if ( hKey[0] )
    RegCloseKey(hKey[0]);
  if ( v12 >= 0 )
  {
    v30 = v53;
    v31 = 0;
    if ( !(_DWORD)v53 )
    {
LABEL_58:
      v12 = ConstructBSTRArray(v45, a2, v50);
      goto LABEL_61;
    }
    while ( 1 )
    {
      if ( v31 < 0 || v31 >= v30 )
      {
        ATL::_AtlRaiseException(0xC000008C, v10);
        __debugbreak();
      }
      if ( !(unsigned int)ATL::CSimpleArray<unsigned short *,ATL::CSimpleArrayEqualHelper<unsigned short *>>::Add(
                            v50,
                            v4 + 8LL * v31) )
        goto LABEL_59;
      v30 = v53;
      if ( ++v31 >= (unsigned int)v53 )
        goto LABEL_58;
    }
  }
LABEL_61:
  if ( (unsigned int)dword_18004AE90 > 5 )
  {
    v44 = v12;
    if ( a2 )
      v32 = *a2;
    else
      v32 = -1;
    LODWORD(v46) = v32;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (_DWORD)this,
      (unsigned int)&unk_180040D78,
      (_DWORD)a3,
      (_DWORD)v9,
      (__int64)&v46,
      (__int64)&v44);
  }
  for ( k = 0; k < (unsigned int)v6; ++k )
  {
    if ( k < 0 || k >= v6 )
    {
      ATL::_AtlRaiseException(0xC000008C, v10);
      JUMPOUT(0x18000A30FLL);
    }
    SysFreeString(*((BSTR *)v3 + k));
  }
  if ( v3 )
  {
    free(v3);
    v43 = 0;
  }
  for ( m = 0; m < (unsigned int)v8; ++m )
  {
    if ( m < 0 || m >= v8 )
    {
      ATL::_AtlRaiseException(0xC000008C, v10);
      __debugbreak();
    }
    SysFreeString(*(BSTR *)&v7[4 * m]);
  }
  if ( v7 )
    free(v7);
  v35 = v53;
  v36 = 0;
  for ( n = (BSTR *)Block; v36 < (unsigned int)v35; ++v36 )
  {
    if ( v36 < 0 || v36 >= v35 )
    {
      ATL::_AtlRaiseException(0xC000008C, v10);
      __debugbreak();
    }
    SysFreeString(n[v36]);
  }
  if ( n )
    free(n);
  if ( v50[0] )
  {
    free(v50[0]);
    v50[0] = 0;
  }
  if ( (int)(v12 + 0x80000000) >= 0 && v12 != -2147024809 )
  {
    v38 = v45;
    v39 = *v45;
    if ( *v45 )
    {
      v40 = *a2;
      for ( ii = 0; (unsigned int)ii < v40; ii = (unsigned int)(ii + 1) )
        SysFreeString(v39[ii]);
      CoTaskMemFree(v39);
      v38 = v45;
    }
    *v38 = 0;
    *a2 = 0;
  }
  if ( v50[0] )
    free(v50[0]);
  if ( v43 )
    free(v43);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x180009ca0  mov     [rsp-8+arg_18], rbx
0x180009ca5  push    rbp
0x180009ca6  push    rsi
0x180009ca7  push    rdi
0x180009ca8  push    r12
0x180009caa  push    r13
0x180009cac  push    r14
0x180009cae  push    r15
0x180009cb0  lea     rbp, [rsp-27h]
0x180009cb5  sub     rsp, 0D0h
0x180009cbc  mov     rax, cs:__security_cookie
0x180009cc3  xor     rax, rsp
0x180009cc6  mov     [rbp+57h+var_38], rax
0x180009cca  xor     esi, esi
0x180009ccc  mov     [rbp+57h+var_C0], r8
0x180009cd0  xor     edi, edi
0x180009cd2  mov     [rbp+57h+var_D0], rsi
0x180009cd6  mov     r12, rdx
0x180009cd9  mov     [rbp+57h+hKey], rsi
0x180009cdd  xor     r14d, r14d
0x180009ce0  mov     [rbp+57h+Block], rdi
0x180009ce4  xor     r13d, r13d
0x180009ce7  mov     [rbp+57h+hKey+8], r14
0x180009ceb  xor     r15d, r15d
0x180009cee  mov     [rbp+57h+var_B8], r13
0x180009cf2  mov     [rbp+57h+var_B0], r15
0x180009cf6  mov     r9, rcx
0x180009cf9  mov     [rbp+57h+var_70], rdi
0x180009cfd  mov     edx, 80070057h
0x180009d02  mov     [rbp+57h+var_68], rsi
0x180009d06  mov     [rbp+57h+var_88], rsi
0x180009d0a  mov     [rbp+57h+var_80], rsi
0x180009d0e  test    r12, r12
0x180009d11  jz      loc_18000A0AA
0x180009d17  test    r8, r8
0x180009d1a  jz      loc_18000A0AA
0x180009d20  mov     [r12], esi
0x180009d24  mov     [r8], rsi
0x180009d27  mov     ecx, [rcx+2Ch]
0x180009d2a  sub     ecx, 15h
0x180009d2d  jz      loc_180009F3F
0x180009d33  sub     ecx, 1
0x180009d36  jz      loc_180009E79
0x180009d3c  cmp     ecx, 5
0x180009d3f  jz      short loc_180009D52
0x180009d41  mov     [r12], esi
0x180009d45  mov     [r8], rsi
0x180009d48  mov     ebx, 86000011h
0x180009d4d  jmp     loc_18000A0AC
0x180009d52  mov     rcx, [r9+18h]
0x180009d56  test    rcx, rcx
0x180009d59  jz      loc_18000A0AA
0x180009d5f  mov     [rbp+57h+var_B8], rsi
0x180009d63  lea     r8, [rbp+57h+var_B8]
0x180009d67  mov     rax, [rcx]
0x180009d6a  mov     edx, 3
0x180009d6f  mov     rax, [rax+58h]
0x180009d73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009d78  mov     ebx, eax
0x180009d7a  test    eax, eax
0x180009d7c  js      loc_18000A0AC
0x180009d82  mov     rdx, [rbp+57h+var_B8]; unsigned __int16 *
0x180009d86  lea     rcx, [rbp+57h+hKey]; this
0x180009d8a  xorps   xmm0, xmm0
0x180009d8d  xorps   xmm1, xmm1
0x180009d90  movdqu  xmmword ptr [rbp+57h+hKey], xmm0
0x180009d95  movdqu  [rbp+57h+var_98], xmm1
0x180009d9a  call    ?Initialize@CFileDownload_DMChannel@@QEAAJPEBG@Z; CFileDownload_DMChannel::Initialize(ushort const *)
0x180009d9f  lea     rcx, [rbp+57h+hKey]; this
0x180009da3  mov     ebx, eax
0x180009da5  test    eax, eax
0x180009da7  jns     short loc_180009DB3
0x180009da9  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180009dae  jmp     loc_18000A0AC
0x180009db3  lea     rdx, [rbp+57h+var_C8]; int *
0x180009db7  mov     [rbp+57h+var_C8], esi
0x180009dba  call    ?GetBlockCount@CFileDownload_DMChannel@@QEAAJAEAJ@Z; CFileDownload_DMChannel::GetBlockCount(long &)
0x180009dbf  mov     ebx, eax
0x180009dc1  test    eax, eax
0x180009dc3  jns     short loc_180009DDD
0x180009dc5  cmp     eax, 8007139Fh
0x180009dca  jz      short loc_180009DD9
0x180009dcc  cmp     eax, 80070002h
0x180009dd1  jz      short loc_180009DD9
0x180009dd3  lea     rcx, [rbp+57h+hKey]
0x180009dd7  jmp     short loc_180009DA9
0x180009dd9  xor     ebx, ebx
0x180009ddb  jmp     short loc_180009DE0
0x180009ddd  mov     esi, [rbp+57h+var_C8]
0x180009de0  movsxd  rdi, esi
0x180009de3  shl     rdi, 3
0x180009de7  mov     rcx, rdi; cb
0x180009dea  call    cs:__imp_CoTaskMemAlloc
0x180009df1  nop     dword ptr [rax+rax+00h]
0x180009df6  mov     rcx, [rbp+57h+var_C0]
0x180009dfa  mov     [rcx], rax
0x180009dfd  test    rax, rax
0x180009e00  jnz     short loc_180009E19
0x180009e02  mov     ebx, 8007000Eh
0x180009e07  lea     rcx, [rbp+57h+hKey]; this
0x180009e0b  call    ??1CFileDownload_DMChannel@@QEAA@XZ; CFileDownload_DMChannel::~CFileDownload_DMChannel(void)
0x180009e10  mov     rsi, [rbp+57h+var_D0]
0x180009e14  jmp     loc_18000A0AC
0x180009e19  mov     r8, rdi; Size
0x180009e1c  xor     edx, edx; Val
0x180009e1e  mov     rcx, rax; void *
0x180009e21  call    memset_0
0x180009e26  xor     edi, edi
0x180009e28  test    esi, esi
0x180009e2a  jle     short loc_180009E07
0x180009e2c  mov     r9d, edi
0x180009e2f  lea     r8, aD; "%d"
0x180009e36  mov     edx, 10h; unsigned __int64
0x180009e3b  lea     rcx, [rbp+57h+psz]; unsigned __int16 *
0x180009e3f  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180009e44  mov     ebx, eax
0x180009e46  test    eax, eax
0x180009e48  js      short loc_180009E07
0x180009e4a  lea     rcx, [rbp+57h+psz]; psz
0x180009e4e  call    cs:__imp_SysAllocString
0x180009e55  nop     dword ptr [rax+rax+00h]
0x180009e5a  mov     r8, [rbp+57h+var_C0]
0x180009e5e  movsxd  rdx, edi
0x180009e61  mov     rcx, [r8]
0x180009e64  mov     [rcx+rdx*8], rax
0x180009e68  cmp     [r8], r13
0x180009e6b  jz      short loc_180009E02
0x180009e6d  inc     dword ptr [r12]
0x180009e71  inc     edi
0x180009e73  cmp     edi, esi
0x180009e75  jl      short loc_180009E2C
0x180009e77  jmp     short loc_180009E07
0x180009e79  lea     rax, aBlocksizekb; "BlockSizeKB"
0x180009e80  mov     ebx, 28h ; '('
0x180009e85  mov     qword ptr [rbp+57h+psz], rax
0x180009e89  mov     ecx, ebx; cb
0x180009e8b  lea     rax, aBlockcount; "BlockCount"
0x180009e92  mov     [rbp+57h+var_58], rax
0x180009e96  lea     rax, aBlockindextore; "BlockIndexToRead"
0x180009e9d  mov     [rbp+57h+var_50], rax
0x180009ea1  lea     rax, aBlockdata; "BlockData"
0x180009ea8  mov     [rbp+57h+var_48], rax
0x180009eac  lea     rax, aDatablocks; "DataBlocks"
0x180009eb3  mov     [rbp+57h+var_40], rax
0x180009eb7  call    cs:__imp_CoTaskMemAlloc
0x180009ebe  nop     dword ptr [rax+rax+00h]
0x180009ec3  mov     rsi, rax
0x180009ec6  test    rax, rax
0x180009ec9  jz      short loc_180009F35
0x180009ecb  mov     [rax], dil
0x180009ece  inc     rax
0x180009ed1  sub     rbx, 1
0x180009ed5  jnz     short loc_180009ECB
0x180009ed7  mov     rcx, qword ptr [rbp+rdi*8+57h+psz]; psz
0x180009edc  call    cs:__imp_SysAllocString
0x180009ee3  nop     dword ptr [rax+rax+00h]
0x180009ee8  mov     [rsi+rdi*8], rax
0x180009eec  test    rax, rax
0x180009eef  jz      short loc_180009F0A
0x180009ef1  inc     edi
0x180009ef3  cmp     edi, 5
0x180009ef6  jb      short loc_180009ED7
0x180009ef8  mov     rcx, [rbp+57h+var_C0]
0x180009efc  xor     ebx, ebx
0x180009efe  mov     [rcx], rsi
0x180009f01  mov     [r12], edi
0x180009f05  jmp     loc_180009E10
0x180009f0a  xor     ebx, ebx
0x180009f0c  test    edi, edi
0x180009f0e  jz      short loc_180009F26
0x180009f10  mov     rcx, [rsi+rbx*8]; bstrString
0x180009f14  call    cs:__imp_SysFreeString
0x180009f1b  nop     dword ptr [rax+rax+00h]
0x180009f20  inc     ebx
0x180009f22  cmp     ebx, edi
0x180009f24  jb      short loc_180009F10
0x180009f26  mov     rcx, rsi; pv
0x180009f29  call    cs:__imp_CoTaskMemFree
0x180009f30  nop     dword ptr [rax+rax+00h]
0x180009f35  mov     ebx, 8007000Eh
0x180009f3a  jmp     loc_180009E10
0x180009f3f  lea     rcx, [rbp+57h+hKey]
0x180009f43  call    ?GetRegisteredCollectorNames@CEtwLogCollector@@SAJPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; CEtwLogCollector::GetRegisteredCollectorNames(ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x180009f48  mov     rsi, [rbp+57h+hKey]
0x180009f4c  mov     ebx, eax
0x180009f4e  mov     r14d, dword ptr [rbp+57h+hKey+8]
0x180009f52  mov     [rbp+57h+var_D0], rsi
0x180009f56  test    eax, eax
0x180009f58  js      loc_18000A0AC
0x180009f5e  xor     ebx, ebx
0x180009f60  test    r14d, r14d
0x180009f63  jz      short loc_180009F95
0x180009f65  test    ebx, ebx
0x180009f67  js      loc_18000A2E4
0x180009f6d  cmp     ebx, r14d
0x180009f70  jge     loc_18000A2E4
0x180009f76  movsxd  rax, ebx
0x180009f79  lea     rcx, [rbp+57h+var_88]
0x180009f7d  lea     rdx, [rsi+rax*8]
0x180009f81  call    ?Add@?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@QEAAHAEBQEAG@Z; ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>>::Add(ushort * const &)
0x180009f86  test    eax, eax
0x180009f88  jz      loc_18000A0A3
0x180009f8e  inc     ebx
0x180009f90  cmp     ebx, r14d
0x180009f93  jb      short loc_180009F65
0x180009f95  lea     rcx, [rbp+57h+var_B8]
0x180009f99  call    ?GetRegisteredChannels@CEventLogChannel@@SAJPEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; CEventLogChannel::GetRegisteredChannels(ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x180009f9e  mov     r15d, dword ptr [rbp+57h+var_B0]
0x180009fa2  mov     ebx, eax
0x180009fa4  mov     r13, [rbp+57h+var_B8]
0x180009fa8  test    eax, eax
0x180009faa  js      loc_18000A0AC
0x180009fb0  xor     ebx, ebx
0x180009fb2  test    r15d, r15d
0x180009fb5  jz      short loc_180009FEE
0x180009fb7  test    ebx, ebx
0x180009fb9  js      loc_18000A2EF
0x180009fbf  cmp     ebx, r15d
0x180009fc2  jge     loc_18000A2EF
0x180009fc8  movsxd  rax, ebx
0x180009fcb  lea     rcx, [rbp+57h+var_88]
0x180009fcf  lea     rdx, ds:0[rax*8]
0x180009fd7  add     rdx, r13
0x180009fda  call    ?Add@?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@QEAAHAEBQEAG@Z; ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>>::Add(ushort * const &)
0x180009fdf  test    eax, eax
0x180009fe1  jz      loc_18000A0A3
0x180009fe7  inc     ebx
0x180009fe9  cmp     ebx, r15d
0x180009fec  jb      short loc_180009FB7
0x180009fee  mov     [rbp+57h+hKey], rdi
0x180009ff2  mov     [rbp+57h+hKey+8], rdi
0x180009ff6  mov     qword ptr [rbp+57h+var_98], rdi
0x180009ffa  call    cs:__imp_RtlIsStateSeparationEnabled
0x18000a001  nop     dword ptr [rax+rax+00h]
0x18000a006  test    al, al
0x18000a008  lea     rdx, aSoftwareMicros_4; "SOFTWARE\\Microsoft\\DiagnosticLogCSP\\"...
0x18000a00f  lea     rcx, aOsdataSoftware; "OSData\\SOFTWARE\\Microsoft\\Diagnostic"...
0x18000a016  cmovz   rcx, rdx; lpSubKey
0x18000a01a  lea     rdx, [rbp+57h+hKey]; struct ATL::CRegKey *
0x18000a01e  call    ?OpenKey@CRegUtils@@SAJPEBGAEAVCRegKey@ATL@@@Z; CRegUtils::OpenKey(ushort const *,ATL::CRegKey &)
0x18000a023  mov     ebx, eax
0x18000a025  test    eax, eax
0x18000a027  js      short loc_18000A040
0x18000a029  lea     rdx, [rbp+57h+var_70]
0x18000a02d  lea     rcx, [rbp+57h+hKey]
0x18000a031  call    ?EnumChildKeys@CRegUtils@@SAJAEAVCRegKey@ATL@@PEAV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@3@@Z; CRegUtils::EnumChildKeys(ATL::CRegKey &,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> *)
0x18000a036  mov     rdi, [rbp+57h+var_70]
0x18000a03a  mov     ebx, eax
0x18000a03c  mov     [rbp+57h+Block], rdi
0x18000a040  mov     rcx, [rbp+57h+hKey]; hKey
0x18000a044  test    rcx, rcx
0x18000a047  jz      short loc_18000A055
0x18000a049  call    cs:__imp_RegCloseKey
0x18000a050  nop     dword ptr [rax+rax+00h]
0x18000a055  test    ebx, ebx
0x18000a057  js      short loc_18000A0AC
0x18000a059  mov     eax, dword ptr [rbp+57h+var_68]
0x18000a05c  xor     ebx, ebx
0x18000a05e  test    eax, eax
0x18000a060  jz      short loc_18000A08F
0x18000a062  test    ebx, ebx
0x18000a064  js      loc_18000A2FA
0x18000a06a  cmp     ebx, eax
0x18000a06c  jge     loc_18000A2FA
0x18000a072  movsxd  rax, ebx
0x18000a075  lea     rcx, [rbp+57h+var_88]
0x18000a079  lea     rdx, [rdi+rax*8]
0x18000a07d  call    ?Add@?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@QEAAHAEBQEAG@Z; ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>>::Add(ushort * const &)
0x18000a082  test    eax, eax
0x18000a084  jz      short loc_18000A0A3
0x18000a086  mov     eax, dword ptr [rbp+57h+var_68]
0x18000a089  inc     ebx
0x18000a08b  cmp     ebx, eax
0x18000a08d  jb      short loc_18000A062
0x18000a08f  mov     rcx, [rbp+57h+var_C0]
0x18000a093  lea     r8, [rbp+57h+var_88]
0x18000a097  mov     rdx, r12
0x18000a09a  call    ?ConstructBSTRArray@@YAJPEAPEAPEAGPEAKAEBV?$CSimpleArray@PEAGV?$CSimpleArrayEqualHelper@PEAG@ATL@@@ATL@@@Z; ConstructBSTRArray(ushort * * *,ulong *,ATL::CSimpleArray<ushort *,ATL::CSimpleArrayEqualHelper<ushort *>> const &)
0x18000a09f  mov     ebx, eax
0x18000a0a1  jmp     short loc_18000A0AC
0x18000a0a3  mov     ebx, 8000FFFFh
0x18000a0a8  jmp     short loc_18000A0AC
0x18000a0aa  mov     ebx, edx
0x18000a0ac  mov     eax, cs:dword_18004AE90
0x18000a0b2  cmp     eax, 5
0x18000a0b5  jbe     short loc_18000A0E9
0x18000a0b7  mov     [rbp+57h+var_C8], ebx
0x18000a0ba  test    r12, r12
0x18000a0bd  jz      short loc_18000A0C5
0x18000a0bf  mov     eax, [r12]
0x18000a0c3  jmp     short loc_18000A0C8
0x18000a0c5  or      eax, 0FFFFFFFFh
0x18000a0c8  mov     dword ptr [rbp+57h+var_B8], eax
0x18000a0cb  lea     rdx, unk_180040D78
0x18000a0d2  lea     rax, [rbp+57h+var_C8]
0x18000a0d6  mov     [rsp+100h+var_D8], rax
0x18000a0db  lea     rax, [rbp+57h+var_B8]
0x18000a0df  mov     [rsp+100h+var_E0], rax
0x18000a0e4  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000a0e9  xor     edi, edi
  ... truncated ...
```
