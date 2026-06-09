# CFileDownloadManager::RefreshServerKnowledge(ClientPartnershipDescriptor const &)

- ea: `0x18004a894`
- end: `0x18004af3e`
- name: `?RefreshServerKnowledge@CFileDownloadManager@@AEAAJAEBVClientPartnershipDescriptor@@@Z`
- size: `1706`
- prototype: `__int64 __fastcall(CFileDownloadManager *__hidden this, const struct ClientPartnershipDescriptor *)`
- caller_count: `1`
- callee_count: `18`
- tags: `service_task, broker_com_uri`

## callers

- `0x18004996c`

## callees

- `0x180002ab0`
- `0x180003604`
- `0x18000444c`
- `0x180007e10`
- `0x180008b8c`
- `0x180009188`
- `0x18000a694`
- `0x180010ee0`
- `0x180011314`
- `0x18001133c`
- `0x1800151d8`
- `0x1800155b8`
- `0x1800155e0`
- `0x1800158d4`
- `0x18003ddb0`
- `0x18004a894`
- `0x18004d408`
- `0x18013e010`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004aad5`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18004aad5`
- `WinSync!__imp_CreateSyncServiceInstance` at `0x18004abc3`
- `WinSync!__imp_CreateSyncServiceInstance` at `0x18004abc3`

## pseudocode

```c
// Hidden C++ exception states: #wind=16
__int64 __fastcall CFileDownloadManager::RefreshServerKnowledge(
        CFileDownloadManager *this,
        const struct ClientPartnershipDescriptor *a2)
{
  const struct ClientPartnershipDescriptor *v2; // r15
  _BYTE *v4; // rax
  char v5; // al
  __int64 v6; // rax
  __int64 (__fastcall *v7)(__int64, __int64, _QWORD); // r10
  __int64 v8; // r11
  int v9; // eax
  HRESULT v10; // eax
  __int64 v11; // rax
  __int64 v12; // r11
  __int64 v13; // r9
  __int64 v14; // r8
  int v15; // eax
  int v16; // eax
  int v17; // eax
  struct IUnknown *v18; // rdx
  __int64 v19; // rax
  __int64 v20; // r8
  void (__fastcall *v21)(__int64, __int64); // r9
  int v23; // [rsp+40h] [rbp-198h] BYREF
  int v24; // [rsp+44h] [rbp-194h]
  char v25; // [rsp+48h] [rbp-190h]
  const char *v26; // [rsp+50h] [rbp-188h]
  __int64 v27; // [rsp+58h] [rbp-180h]
  struct IEcsProtocolClient *v28; // [rsp+60h] [rbp-178h] BYREF
  const struct ClientPartnershipDescriptor *v29; // [rsp+68h] [rbp-170h]
  int v30; // [rsp+70h] [rbp-168h]
  CFileDownloadManager *v31; // [rsp+78h] [rbp-160h]
  struct IUnknown *v32; // [rsp+80h] [rbp-158h] BYREF
  __int64 v33; // [rsp+88h] [rbp-150h] BYREF
  int pExceptionObject; // [rsp+90h] [rbp-148h] BYREF
  HRESULT v35; // [rsp+94h] [rbp-144h] BYREF
  int v36; // [rsp+98h] [rbp-140h] BYREF
  int v37; // [rsp+9Ch] [rbp-13Ch] BYREF
  int v38; // [rsp+A0h] [rbp-138h] BYREF
  int v39; // [rsp+A4h] [rbp-134h] BYREF
  int v40; // [rsp+A8h] [rbp-130h] BYREF
  __int64 v41; // [rsp+B0h] [rbp-128h] BYREF
  void **v42; // [rsp+B8h] [rbp-120h] BYREF
  struct IUnknown *v43; // [rsp+C0h] [rbp-118h] BYREF
  __int64 v44; // [rsp+C8h] [rbp-110h] BYREF
  int v45; // [rsp+D0h] [rbp-108h] BYREF
  int v46; // [rsp+D4h] [rbp-104h] BYREF
  _QWORD v47[2]; // [rsp+D8h] [rbp-100h] BYREF
  const ATL::CAtlException *v48; // [rsp+E8h] [rbp-F0h] BYREF
  const ATL::CAtlException *v49; // [rsp+F0h] [rbp-E8h] BYREF
  _BYTE v50[16]; // [rsp+F8h] [rbp-E0h] BYREF
  GUID v51[2]; // [rsp+108h] [rbp-D0h] BYREF
  GUID pguid; // [rsp+128h] [rbp-B0h] BYREF
  __int128 v53; // [rsp+138h] [rbp-A0h] BYREF

  v2 = a2;
  v31 = this;
  v29 = a2;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) == 0 )
    {
LABEL_8:
      v5 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 25, WPP_9fffca09c132345368abadf44793045b_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 8) == 0 || v4[65] < 6u )
    goto LABEL_8;
  v5 = 1;
LABEL_9:
  v23 = 0;
  v24 = 501;
  v25 = v5;
  v26 = "CFileDownloadManager::RefreshServerKnowledge";
  v27 = 0;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 4u )
  {
    WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 26, WPP_9fffca09c132345368abadf44793045b_Traceguids);
  }
  v33 = 0;
  v32 = 0;
  v28 = 0;
  v43 = 0;
  v42 = &CEcsCredentialFactory::`vftable';
  memset(v51, 0, 28);
  v53 = 0;
  pguid = 0;
  v41 = 0;
  v44 = 0;
  v36 = 0;
  v37 = 0;
  v30 = 0;
  try
  {
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)this + 16);
    v47[1] = v50;
    std::shared_ptr<CSyncStateManager>::shared_ptr<CSyncStateManager>(v50);
    v6 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v2 + 136);
    v9 = v7(v8, v6, 0);
    v23 = v9;
    if ( v9 < 0 )
    {
      HIWORD(v24) = 527;
      pExceptionObject = v9;
      throw (long *)&pExceptionObject;
    }
    LOWORD(v24) = 527;
    CEcsCredentialFactory::CreateCredential(
      (CEcsCredentialFactory *)&v42,
      *((struct IUserCredentialProvider **)this + 12),
      &v43);
    if ( v43 )
      (*(void (__fastcall **)(struct IEcsProtocolClient *))(*(_QWORD *)v28 + 120LL))(v28);
    v10 = CoCreateGuid(&pguid);
    v23 = v10;
    if ( v10 < 0 )
    {
      HIWORD(v24) = 537;
      v35 = v10;
      throw (long *)&v35;
    }
    LOWORD(v24) = 537;
    std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v2 + 104);
    v11 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v2 + 200);
    LOBYTE(v13) = 1;
    (*(void (__fastcall **)(__int64, GUID *, __int64, __int64, __int64, __int128 *))(*(_QWORD *)v12 + 40LL))(
      v12,
      &pguid,
      v11,
      v13,
      v14,
      &v53);
    v30 = 1;
    (*(void (__fastcall **)(struct IEcsProtocolClient *, int *, int *, __int64 *, __int64 *))(*(_QWORD *)v28 + 56LL))(
      v28,
      &v37,
      &v36,
      &v41,
      &v44);
    wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(v47, v41);
    v15 = CreateSyncServiceInstance(&GUID_8ed97ec6_e77c_452e_9866_3747bc305db5, &v33);
    v23 = v15;
    if ( v15 < 0 )
    {
      HIWORD(v24) = 554;
      v38 = v15;
      throw (long *)&v38;
    }
    LOWORD(v24) = 554;
    *(_QWORD *)&v51[0].Data1 = 28;
    *(_WORD *)v51[0].Data4 = 16;
    *(_DWORD *)&v51[0].Data4[4] = 0;
    LOWORD(v51[1].Data1) = 24;
    *(_DWORD *)&v51[1].Data2 = 0;
    *(_WORD *)v51[1].Data4 = 1;
    v16 = (*(__int64 (__fastcall **)(__int64, GUID *))(*(_QWORD *)v33 + 24LL))(v33, v51);
    v23 = v16;
    if ( v16 < 0 )
    {
      HIWORD(v24) = 556;
      v39 = v16;
      throw (long *)&v39;
    }
    LOWORD(v24) = 556;
    v17 = (*(__int64 (__fastcall **)(__int64, __int64, _QWORD, _QWORD, struct IUnknown **))(*(_QWORD *)v33 + 64LL))(
            v33,
            v41,
            (unsigned int)v44,
            0,
            &v32);
    v23 = v17;
    if ( v17 < 0 )
    {
      HIWORD(v24) = 561;
      v40 = v17;
      throw (long *)&v40;
    }
    LOWORD(v24) = 561;
    v18 = v32;
    v32 = 0;
    if ( *((struct IUnknown **)this + 43) != v18 )
      ATL::AtlComPtrAssign((struct IUnknown **)this + 43, v18);
    std::wstring::operator=((char *)this + 360, (char *)v2 + 200);
    std::unique_ptr<unsigned short [0]>::~unique_ptr<unsigned short [0]>(v47);
  }
  catch ( long v45 )
  {
    v23 = v45;
    v2 = v29;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v24) = 566;
    v23 = -2147024882;
    v2 = v29;
  }
  catch ( std::exception )
  {
    HIWORD(v24) = 566;
    v23 = -2147418113;
    v2 = v29;
  }
  catch ( const ATL::CAtlException *v48 )
  {
    HIWORD(v24) = 566;
    v23 = *(_DWORD *)v48;
    v2 = v29;
  }
  LODWORD(v29) = v23;
  v23 = 0;
  if ( (int)v29 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 2u )
  {
    WPP_SF_d(*((_QWORD *)WPP_GLOBAL_Control + 7), 27, WPP_9fffca09c132345368abadf44793045b_Traceguids, 0);
  }
  try
  {
    v19 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr((char *)v2 + 104);
    v21(v20, v19);
  }
  catch ( long v46 )
  {
    v23 = v46;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v24) = 596;
    v23 = -2147024882;
  }
  catch ( std::exception )
  {
    HIWORD(v24) = 596;
    v23 = -2147418113;
  }
  catch ( const ATL::CAtlException *v49 )
  {
    HIWORD(v24) = 596;
    v23 = *(_DWORD *)v49;
  }
  if ( v23 < 0
    && WPP_GLOBAL_Control != &WPP_GLOBAL_Control
    && (*((_BYTE *)WPP_GLOBAL_Control + 68) & 8) != 0
    && *((_BYTE *)WPP_GLOBAL_Control + 65) >= 3u )
  {
    WPP_SF_d(
      *((_QWORD *)WPP_GLOBAL_Control + 7),
      28,
      WPP_9fffca09c132345368abadf44793045b_Traceguids,
      (unsigned int)v23);
  }
  v42 = &IEcsCredentialFactory::`vftable';
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v43);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v28);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v32);
  ATL::CComPtrBase<IUnknown>::~CComPtrBase<IUnknown>(&v33);
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v23);
  return (unsigned int)v29;
}

```

## disassembly

```asm
0x18004a894  mov     [rsp+arg_10], rbx
0x18004a899  mov     [rsp+arg_18], rsi
0x18004a89e  push    rdi
0x18004a89f  push    r12
0x18004a8a1  push    r13
0x18004a8a3  push    r14
0x18004a8a5  push    r15
0x18004a8a7  sub     rsp, 1B0h
0x18004a8ae  mov     rax, cs:__security_cookie
0x18004a8b5  xor     rax, rsp
0x18004a8b8  mov     [rsp+1D8h+var_38], rax
0x18004a8c0  mov     r15, rdx
0x18004a8c3  mov     r14, rcx
0x18004a8c6  mov     [rsp+1D8h+var_160], rcx
0x18004a8cb  mov     [rsp+1D8h+var_170], rdx
0x18004a8d0  lea     rdi, WPP_GLOBAL_Control
0x18004a8d7  mov     rax, cs:WPP_GLOBAL_Control
0x18004a8de  cmp     rax, rdi
0x18004a8e1  jz      short loc_18004A90B
0x18004a8e3  test    byte ptr [rax+44h], 8
0x18004a8e7  jz      short loc_18004A924
0x18004a8e9  cmp     byte ptr [rax+41h], 6
0x18004a8ed  jb      short loc_18004A90B
0x18004a8ef  mov     edx, 19h
0x18004a8f4  lea     r8, WPP_9fffca09c132345368abadf44793045b_Traceguids
0x18004a8fb  mov     rcx, [rax+38h]
0x18004a8ff  call    WPP_SF_
0x18004a904  mov     rax, cs:WPP_GLOBAL_Control
0x18004a90b  test    byte ptr [rax+44h], 8
0x18004a90f  jz      short loc_18004A924
0x18004a911  cmp     byte ptr [rax+41h], 6
0x18004a915  jb      short loc_18004A924
0x18004a917  mov     r12d, 1
0x18004a91d  mov     al, r12b
0x18004a920  xor     ebx, ebx
0x18004a922  jmp     short loc_18004A92C
0x18004a924  xor     ebx, ebx
0x18004a926  mov     al, bl
0x18004a928  lea     r12d, [rbx+1]
0x18004a92c  mov     [rsp+1D8h+var_198], ebx
0x18004a930  mov     [rsp+1D8h+var_194], 1F5h
0x18004a938  mov     [rsp+1D8h+var_190], al
0x18004a93c  lea     rax, aCfiledownloadm; "CFileDownloadManager::RefreshServerKnow"...
0x18004a943  mov     [rsp+1D8h+var_188], rax
0x18004a948  mov     [rsp+1D8h+var_180], rbx
0x18004a94d  mov     rcx, cs:WPP_GLOBAL_Control
0x18004a954  cmp     rcx, rdi
0x18004a957  jz      short loc_18004A97A
0x18004a959  test    byte ptr [rcx+44h], 8
0x18004a95d  jz      short loc_18004A97A
0x18004a95f  cmp     byte ptr [rcx+41h], 4
0x18004a963  jb      short loc_18004A97A
0x18004a965  mov     edx, 1Ah
0x18004a96a  lea     r8, WPP_9fffca09c132345368abadf44793045b_Traceguids
0x18004a971  mov     rcx, [rcx+38h]
0x18004a975  call    WPP_SF_
0x18004a97a  mov     [rsp+1D8h+var_150], rbx
0x18004a982  mov     [rsp+1D8h+var_158], rbx
0x18004a98a  mov     [rsp+1D8h+var_178], rbx
0x18004a98f  mov     [rsp+1D8h+var_118], rbx
0x18004a997  lea     rsi, ??_7IEcsCredentialFactory@@6B@; const IEcsCredentialFactory::`vftable'
0x18004a99e  mov     [rsp+1D8h+var_120], rsi
0x18004a9a6  lea     rax, ??_7CEcsCredentialFactory@@6B@; const CEcsCredentialFactory::`vftable'
0x18004a9ad  mov     [rsp+1D8h+var_120], rax
0x18004a9b5  xorps   xmm0, xmm0
0x18004a9b8  movups  [rsp+1D8h+var_D0], xmm0
0x18004a9c0  movups  [rsp+1D8h+var_D0+0Ch], xmm0
0x18004a9c8  movups  [rsp+1D8h+var_A0], xmm0
0x18004a9d0  xorps   xmm1, xmm1
0x18004a9d3  movups  xmmword ptr [rsp+1D8h+pguid.Data1], xmm1
0x18004a9db  mov     [rsp+1D8h+var_128], rbx
0x18004a9e3  mov     [rsp+1D8h+var_110], rbx
0x18004a9eb  mov     [rsp+1D8h+var_140], ebx
0x18004a9f2  mov     [rsp+1D8h+var_13C], ebx
0x18004a9f9  mov     [rsp+1D8h+var_168], ebx
0x18004a9fd  mov     r11, [r14+40h]
0x18004aa01  mov     rax, [r11]
0x18004aa04  mov     r10, [rax]
0x18004aa07  lea     rcx, [r14+10h]
0x18004aa0b  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004aa10  mov     rdx, rax
0x18004aa13  lea     rax, [rsp+1D8h+var_E0]
0x18004aa1b  mov     [rsp+1D8h+var_F8], rax
0x18004aa23  lea     rcx, [rsp+1D8h+var_E0]
0x18004aa2b  call    ??0?$shared_ptr@VCSyncStateManager@@@std@@QEAA@$$T@Z; std::shared_ptr<CSyncStateManager>::shared_ptr<CSyncStateManager>(std::nullptr_t)
0x18004aa30  mov     r9, rax
0x18004aa33  lea     rcx, [r15+88h]
0x18004aa3a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004aa3f  nop
0x18004aa40  lea     rcx, [rsp+1D8h+var_178]
0x18004aa45  mov     [rsp+1D8h+var_1B0], rcx
0x18004aa4a  mov     [rsp+1D8h+var_1B8], rdx
0x18004aa4f  xor     r8d, r8d
0x18004aa52  mov     rdx, rax
0x18004aa55  mov     rcx, r11
0x18004aa58  mov     rax, r10
0x18004aa5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aa60  mov     [rsp+1D8h+var_198], eax
0x18004aa64  mov     [rsp+1D8h+var_198], eax
0x18004aa68  mov     ecx, 20Fh
0x18004aa6d  test    eax, eax
0x18004aa6f  jns     short loc_18004AA91
0x18004aa71  mov     word ptr [rsp+1D8h+var_194+2], cx
0x18004aa76  mov     [rsp+1D8h+pExceptionObject], eax
0x18004aa7d  lea     rdx, _TI1J; pThrowInfo
0x18004aa84  lea     rcx, [rsp+1D8h+pExceptionObject]; pExceptionObject
0x18004aa8c  call    _CxxThrowException_0
0x18004aa91  mov     word ptr [rsp+1D8h+var_194], cx
0x18004aa96  lea     r8, [rsp+1D8h+var_118]; struct IUnknown **
0x18004aa9e  mov     rdx, [r14+60h]; struct IUserCredentialProvider *
0x18004aaa2  lea     rcx, [rsp+1D8h+var_120]; this
0x18004aaaa  call    ?CreateCredential@CEcsCredentialFactory@@UEAAXPEAVIUserCredentialProvider@@PEAPEAUIUnknown@@@Z; CEcsCredentialFactory::CreateCredential(IUserCredentialProvider *,IUnknown * *)
0x18004aaaf  mov     rdx, [rsp+1D8h+var_118]
0x18004aab7  test    rdx, rdx
0x18004aaba  jz      short loc_18004AACD
0x18004aabc  mov     rcx, [rsp+1D8h+var_178]
0x18004aac1  mov     rax, [rcx]
0x18004aac4  mov     rax, [rax+78h]
0x18004aac8  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004aacd  lea     rcx, [rsp+1D8h+pguid]; pguid
0x18004aad5  call    cs:__imp_CoCreateGuid
0x18004aadb  mov     [rsp+1D8h+var_198], eax
0x18004aadf  mov     [rsp+1D8h+var_198], eax
0x18004aae3  mov     ecx, 219h
0x18004aae8  test    eax, eax
0x18004aaea  jns     short loc_18004AB0C
0x18004aaec  mov     word ptr [rsp+1D8h+var_194+2], cx
0x18004aaf1  mov     [rsp+1D8h+var_144], eax
0x18004aaf8  lea     rdx, _TI1J; pThrowInfo
0x18004aaff  lea     rcx, [rsp+1D8h+var_144]; pExceptionObject
0x18004ab07  call    _CxxThrowException_0
0x18004ab0c  mov     word ptr [rsp+1D8h+var_194], cx
0x18004ab11  mov     r11, [rsp+1D8h+var_178]
0x18004ab16  lea     rcx, [r15+68h]
0x18004ab1a  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ab1f  mov     r8, rax
0x18004ab22  lea     r13, [r15+0C8h]
0x18004ab29  mov     rcx, r13
0x18004ab2c  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ab31  mov     rdx, [r11]
0x18004ab34  mov     r10, [rdx+28h]
0x18004ab38  lea     rcx, [rsp+1D8h+var_A0]
0x18004ab40  mov     [rsp+1D8h+var_1B0], rcx
0x18004ab45  mov     [rsp+1D8h+var_1B8], r8
0x18004ab4a  mov     r9b, r12b
0x18004ab4d  mov     r8, rax
0x18004ab50  lea     rdx, [rsp+1D8h+pguid]
0x18004ab58  mov     rcx, r11
0x18004ab5b  mov     rax, r10
0x18004ab5e  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab63  mov     [rsp+1D8h+var_168], r12d
0x18004ab68  mov     rcx, [rsp+1D8h+var_178]
0x18004ab6d  mov     rax, [rcx]
0x18004ab70  lea     rdx, [rsp+1D8h+var_110]
0x18004ab78  mov     [rsp+1D8h+var_1B8], rdx
0x18004ab7d  lea     r9, [rsp+1D8h+var_128]
0x18004ab85  lea     r8, [rsp+1D8h+var_140]
0x18004ab8d  lea     rdx, [rsp+1D8h+var_13C]
0x18004ab95  mov     rax, [rax+38h]
0x18004ab99  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ab9e  mov     rdx, [rsp+1D8h+var_128]
0x18004aba6  lea     rcx, [rsp+1D8h+var_100]
0x18004abae  call    ??$?0$00X@?$unique_ptr@XUprocess_heap_deleter@wil@@@wistd@@QEAA@PEAX@Z; wistd::unique_ptr<void,wil::process_heap_deleter>::unique_ptr<void,wil::process_heap_deleter>(void *)
0x18004abb3  nop
0x18004abb4  lea     rdx, [rsp+1D8h+var_150]
0x18004abbc  lea     rcx, _GUID_8ed97ec6_e77c_452e_9866_3747bc305db5
0x18004abc3  call    cs:__imp_CreateSyncServiceInstance
0x18004abc9  mov     [rsp+1D8h+var_198], eax
0x18004abcd  mov     [rsp+1D8h+var_198], eax
0x18004abd1  mov     ecx, 22Ah
0x18004abd6  test    eax, eax
0x18004abd8  jns     short loc_18004ABFA
0x18004abda  mov     word ptr [rsp+1D8h+var_194+2], cx
0x18004abdf  mov     [rsp+1D8h+var_138], eax
0x18004abe6  lea     rdx, _TI1J; pThrowInfo
0x18004abed  lea     rcx, [rsp+1D8h+var_138]; pExceptionObject
0x18004abf5  call    _CxxThrowException_0
0x18004abfa  mov     word ptr [rsp+1D8h+var_194], cx
0x18004abff  mov     qword ptr [rsp+1D8h+var_D0], 1Ch
0x18004ac0b  mov     eax, 10h
0x18004ac10  mov     word ptr [rsp+1D8h+var_D0+8], ax
0x18004ac18  mov     dword ptr [rsp+1D8h+var_D0+0Ch], ebx
0x18004ac1f  mov     eax, 18h
0x18004ac24  mov     [rsp+1D8h+var_C0], ax
0x18004ac2c  mov     [rsp+1D8h+var_BC], ebx
0x18004ac33  mov     [rsp+1D8h+var_B8], r12w
0x18004ac3c  mov     rcx, [rsp+1D8h+var_150]
0x18004ac44  mov     rax, [rcx]
0x18004ac47  lea     rdx, [rsp+1D8h+var_D0]
0x18004ac4f  mov     rax, [rax+18h]
0x18004ac53  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ac58  mov     [rsp+1D8h+var_198], eax
0x18004ac5c  mov     [rsp+1D8h+var_198], eax
0x18004ac60  mov     ecx, 22Ch
0x18004ac65  test    eax, eax
0x18004ac67  jns     short loc_18004AC89
0x18004ac69  mov     word ptr [rsp+1D8h+var_194+2], cx
0x18004ac6e  mov     [rsp+1D8h+var_134], eax
0x18004ac75  lea     rdx, _TI1J; pThrowInfo
0x18004ac7c  lea     rcx, [rsp+1D8h+var_134]; pExceptionObject
0x18004ac84  call    _CxxThrowException_0
0x18004ac89  mov     word ptr [rsp+1D8h+var_194], cx
0x18004ac8e  mov     rcx, [rsp+1D8h+var_150]
0x18004ac96  mov     rax, [rcx]
0x18004ac99  lea     rdx, [rsp+1D8h+var_158]
0x18004aca1  mov     [rsp+1D8h+var_1B8], rdx
0x18004aca6  xor     r9d, r9d
0x18004aca9  mov     r8d, dword ptr [rsp+1D8h+var_110]
0x18004acb1  mov     rdx, [rsp+1D8h+var_128]
0x18004acb9  mov     rax, [rax+40h]
0x18004acbd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004acc2  mov     [rsp+1D8h+var_198], eax
0x18004acc6  mov     [rsp+1D8h+var_198], eax
0x18004acca  mov     ecx, 231h
0x18004accf  test    eax, eax
0x18004acd1  jns     short loc_18004ACF3
0x18004acd3  mov     word ptr [rsp+1D8h+var_194+2], cx
0x18004acd8  mov     [rsp+1D8h+var_130], eax
0x18004acdf  lea     rdx, _TI1J; pThrowInfo
0x18004ace6  lea     rcx, [rsp+1D8h+var_130]; pExceptionObject
0x18004acee  call    _CxxThrowException_0
0x18004acf3  mov     word ptr [rsp+1D8h+var_194], cx
0x18004acf8  mov     rdx, [rsp+1D8h+var_158]; struct IUnknown *
0x18004ad00  mov     [rsp+1D8h+var_158], rbx
0x18004ad08  lea     rcx, [r14+158h]; struct IUnknown **
0x18004ad0f  cmp     [rcx], rdx
0x18004ad12  jz      short loc_18004AD19
0x18004ad14  call    ?AtlComPtrAssign@ATL@@YAPEAUIUnknown@@PEAPEAU2@PEAU2@@Z; ATL::AtlComPtrAssign(IUnknown * *,IUnknown *)
0x18004ad19  lea     rcx, [r14+168h]
0x18004ad20  mov     rdx, r13
0x18004ad23  call    ??4?$basic_string@GU?$char_traits@G@std@@V?$allocator@G@2@@std@@QEAAAEAV01@AEBV01@@Z; std::wstring::operator=(std::wstring const &)
0x18004ad28  nop
0x18004ad29  lea     rcx, [rsp+1D8h+var_100]
0x18004ad31  call    ??1?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@std@@@std@@QEAA@XZ; std::unique_ptr<ushort [0]>::~unique_ptr<ushort [0]>(void)
0x18004ad36  nop
0x18004ad37  jmp     short loc_18004AD59
0x18004ad39  jmp     short loc_18004AD3F
0x18004ad3b  jmp     short loc_18004AD3F
0x18004ad3d  jmp     short $+2
0x18004ad3f  mov     r14, [rsp+1D8h+var_160]
0x18004ad44  mov     r15, [rsp+1D8h+var_170]
0x18004ad49  lea     rsi, ??_7IEcsCredentialFactory@@6B@; const IEcsCredentialFactory::`vftable'
0x18004ad50  xor     ebx, ebx
0x18004ad52  lea     rdi, WPP_GLOBAL_Control
0x18004ad59  mov     eax, [rsp+1D8h+var_198]
0x18004ad5d  mov     dword ptr [rsp+1D8h+var_170], eax
0x18004ad61  mov     edx, ebx
0x18004ad63  mov     [rsp+1D8h+var_198], ebx
0x18004ad67  test    eax, eax
0x18004ad69  jns     loc_18004AE4E
0x18004ad6f  mov     rcx, cs:WPP_GLOBAL_Control
0x18004ad76  cmp     rcx, rdi
0x18004ad79  jz      short loc_18004ADA3
0x18004ad7b  test    byte ptr [rcx+44h], 8
0x18004ad7f  jz      short loc_18004ADA3
0x18004ad81  cmp     byte ptr [rcx+41h], 2
0x18004ad85  jb      short loc_18004ADA3
0x18004ad87  mov     edx, 1Bh
0x18004ad8c  xor     r9d, r9d
0x18004ad8f  lea     r8, WPP_9fffca09c132345368abadf44793045b_Traceguids
0x18004ad96  mov     rcx, [rcx+38h]
0x18004ad9a  call    WPP_SF_d
0x18004ad9f  mov     edx, [rsp+1D8h+var_198]
0x18004ada3  cmp     [rsp+1D8h+var_178], rbx
0x18004ada8  jz      loc_18004AE4E
0x18004adae  cmp     edx, 80C80300h
0x18004adb4  jz      short loc_18004ADC2
0x18004adb6  cmp     edx, 80C8032Dh
0x18004adbc  jnz     loc_18004AE4E
0x18004adc2  lea     rcx, [rsp+1D8h+var_88]; this
0x18004adca  call    ??0AuthenticationInfo@@QEAA@XZ; AuthenticationInfo::AuthenticationInfo(void)
0x18004adcf  nop
0x18004add0  lea     rdx, [rsp+1D8h+var_88]; struct AuthenticationInfo *
0x18004add8  mov     rcx, [rsp+1D8h+var_178]; struct IEcsProtocolClient *
0x18004addd  call    ?GetAuthenticationInfo@CFileDownloadTask@@SAXPEAUIEcsProtocolClient@@AEAUAuthenticationInfo@@@Z; CFileDownloadTask::GetAuthenticationInfo(IEcsProtocolClient *,AuthenticationInfo &)
0x18004ade2  mov     r11, [r14+60h]
0x18004ade6  mov     r10, [r11]
0x18004ade9  lea     rcx, [rsp+1D8h+var_68]
0x18004adf1  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004adf6  mov     rdx, rax
0x18004adf9  lea     rcx, [rsp+1D8h+var_88]
0x18004ae01  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18004ae06  mov     r8, rax
0x18004ae09  mov     [rsp+1D8h+var_1B8], rdx
0x18004ae0e  mov     r9d, [rsp+1D8h+var_44]
0x18004ae16  mov     edx, [rsp+1D8h+var_48]
0x18004ae1d  mov     rcx, r11
0x18004ae20  mov     rax, [r10+8]
0x18004ae24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae29  mov     rcx, [r14+60h]
0x18004ae2d  mov     rax, [rcx]
0x18004ae30  mov     edx, [rsp+1D8h+var_48]
0x18004ae37  mov     rax, [rax+30h]
0x18004ae3b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18004ae40  nop
0x18004ae41  lea     rcx, [rsp+1D8h+var_88]; this
0x18004ae49  call    ??1DiscoverSyncShareResponseType@@QEAA@XZ; DiscoverSyncShareResponseType::~DiscoverSyncShareResponseType(void)
0x18004ae4e  cmp     [rsp+1D8h+var_168], ebx
0x18004ae52  jz      short loc_18004AEC6
0x18004ae54  mov     r8, [rsp+1D8h+var_178]
  ... truncated ...
```
