# FindClientCertificate(void *)

- ea: `0x1800c9888`
- end: `0x1800c9bff`
- name: `?FindClientCertificate@@YA?AV?$unique_ptr@$$CBU_CERT_CONTEXT@@UCertContextDeleter@@@std@@PEAX@Z`
- size: `887`
- prototype: ``
- caller_count: `1`
- callee_count: `11`
- tags: `broker_com_uri`

## callers

- `0x1800c9c08`

## callees

- `0x180003604`
- `0x180007b9c`
- `0x180007e10`
- `0x180011314`
- `0x180035564`
- `0x1800c9198`
- `0x1800c9888`
- `0x1800cd264`
- `0x1800cd2a0`
- `0x1800cd2dc`
- `0x1800cd300`

## import_xrefs

- `CRYPT32!CertDuplicateCertificateContext` at `0x1800c9b2f`
- `CRYPT32!CertDuplicateCertificateContext` at `0x1800c9b2f`
- `CRYPT32!CertFindChainInStore` at `0x1800c9aa7`
- `CRYPT32!CertFindChainInStore` at `0x1800c9aa7`
- `CRYPT32!CertOpenSystemStoreW` at `0x1800c99fd`
- `CRYPT32!CertOpenSystemStoreW` at `0x1800c99fd`
- `WINHTTP!WinHttpQueryOption` at `0x1800c9992`
- `WINHTTP!WinHttpQueryOption` at `0x1800c9992`

## pseudocode

```c
// Hidden C++ exception states: #wind=5
_QWORD *__fastcall FindClientCertificate(_QWORD *a1, void *a2)
{
  _QWORD *v3; // rsi
  _BYTE *v4; // rax
  char v5; // al
  PCCERT_CHAIN_CONTEXT ChainInStore; // rax
  int v7; // edx
  __int64 v8; // rax
  __int64 v9; // rax
  const CERT_CONTEXT *v10; // rcx
  PCCERT_CONTEXT v11; // rax
  int v13; // [rsp+30h] [rbp-C8h] BYREF
  int v14; // [rsp+34h] [rbp-C4h]
  char v15; // [rsp+38h] [rbp-C0h]
  const char *v16; // [rsp+40h] [rbp-B8h]
  __int64 v17; // [rsp+48h] [rbp-B0h]
  DWORD dwBufferLength; // [rsp+50h] [rbp-A8h] BYREF
  int v19; // [rsp+54h] [rbp-A4h]
  int pExceptionObject; // [rsp+58h] [rbp-A0h] BYREF
  int LastFailureAsHRESULT; // [rsp+5Ch] [rbp-9Ch] BYREF
  int v22; // [rsp+60h] [rbp-98h] BYREF
  int v23; // [rsp+64h] [rbp-94h] BYREF
  __int64 Buffer; // [rsp+68h] [rbp-90h] BYREF
  __int64 v25; // [rsp+70h] [rbp-88h] BYREF
  HCERTSTORE hCertStore; // [rsp+78h] [rbp-80h] BYREF
  __int64 v27; // [rsp+80h] [rbp-78h] BYREF
  int v28; // [rsp+88h] [rbp-70h] BYREF
  __int64 v29; // [rsp+90h] [rbp-68h] BYREF
  __int64 v30; // [rsp+98h] [rbp-60h] BYREF
  __int128 pvFindPara; // [rsp+A0h] [rbp-58h] BYREF
  __int128 v32; // [rsp+B0h] [rbp-48h]
  __int128 v33; // [rsp+C0h] [rbp-38h]
  __int64 v34; // [rsp+D0h] [rbp-28h]
  const ATL::CAtlException *v35; // [rsp+D8h] [rbp-20h] BYREF
  __int64 v37; // [rsp+110h] [rbp+18h] BYREF
  HCERTSTORE v38; // [rsp+118h] [rbp+20h] BYREF

  v3 = a1;
  v19 = 1;
  v4 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control != &WPP_GLOBAL_Control )
  {
    if ( (*((_BYTE *)WPP_GLOBAL_Control + 68) & 2) == 0 )
    {
LABEL_8:
      v5 = 0;
      goto LABEL_9;
    }
    if ( *((_BYTE *)WPP_GLOBAL_Control + 65) >= 6u )
    {
      WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 7), 31, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids);
      v4 = WPP_GLOBAL_Control;
    }
  }
  if ( (v4[68] & 2) == 0 || v4[65] < 6u )
    goto LABEL_8;
  v5 = 1;
LABEL_9:
  v13 = 0;
  v14 = 1034;
  v15 = v5;
  v16 = "FindClientCertificate";
  v17 = 0;
  ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(v3);
  v19 = 1;
  try
  {
    hCertStore = 0;
    ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(&v25);
    v27 = 0;
    Buffer = 0;
    pvFindPara = 0;
    v32 = 0;
    v33 = 0;
    v34 = 0;
    dwBufferLength = 8;
    if ( !WinHttpQueryOption(a2, 0x5Eu, &Buffer, &dwBufferLength) )
    {
      HIWORD(v14) = 1050;
      pExceptionObject = EcsGetLastFailureAsHRESULT();
      throw (long *)&pExceptionObject;
    }
    v13 = 0;
    LOWORD(v14) = 1050;
    v37 = Buffer;
    EcsUniqueHandle<void *,GlobalMemoryDeleter,0>::reset(&v27, &v37);
    v38 = CertOpenSystemStoreW(0, L"MY");
    EcsUniqueHandle<void *,CertStoreDeleter<0>,0>::reset(&hCertStore, &v38);
    if ( !hCertStore )
    {
      HIWORD(v14) = 1057;
      LastFailureAsHRESULT = EcsGetLastFailureAsHRESULT();
      throw (long *)&LastFailureAsHRESULT;
    }
    v13 = 0;
    LOWORD(v14) = 1057;
    LODWORD(pvFindPara) = 56;
    DWORD2(v32) = *(_DWORD *)(Buffer + 8);
    *(_QWORD *)&v33 = *(_QWORD *)Buffer;
    ChainInStore = CertFindChainInStore(hCertStore, 1u, 0x8004u, 1u, &pvFindPara, 0);
    std::unique_ptr<_CERT_CHAIN_CONTEXT const,CertChainContextDeleter>::reset(&v25, ChainInStore);
    if ( !v25 )
    {
      HIWORD(v14) = 1071;
      v22 = EcsGetLastFailureAsHRESULT();
      throw (long *)&v22;
    }
    v7 = 0;
    v13 = 0;
    LOWORD(v14) = 1071;
    if ( *(_DWORD *)(v25 + 12) )
    {
      v8 = **(_QWORD **)(v25 + 16);
      if ( v8 )
      {
        if ( *(_DWORD *)(v8 + 12) )
        {
          v9 = *(_QWORD *)(v8 + 16);
          if ( *(_QWORD *)v9 )
          {
            v10 = *(const CERT_CONTEXT **)(*(_QWORD *)v9 + 8LL);
            if ( v10 )
            {
              v11 = CertDuplicateCertificateContext(v10);
              std::unique_ptr<_CERT_CONTEXT const,CertContextDeleter>::reset(v3, v11);
              v7 = v13;
            }
          }
        }
      }
    }
    v13 = v7;
    if ( !*v3 )
    {
      v13 = -2147418113;
      HIWORD(v14) = 1082;
      v23 = -2147418113;
      throw (long *)&v23;
    }
    v13 = 0;
    LOWORD(v14) = 1082;
    v29 = 0;
    EcsUniqueHandle<void *,GlobalMemoryDeleter,0>::reset(&v27, &v29);
    std::unique_ptr<_CERT_CHAIN_CONTEXT const,CertChainContextDeleter>::~unique_ptr<_CERT_CHAIN_CONTEXT const,CertChainContextDeleter>(&v25);
    v30 = 0;
    EcsUniqueHandle<void *,CertStoreDeleter<0>,0>::reset(&hCertStore, &v30);
  }
  catch ( long v28 )
  {
    v13 = v28;
    v3 = a1;
  }
  catch ( std::bad_alloc )
  {
    HIWORD(v14) = 1084;
    v13 = -2147024882;
    v3 = a1;
  }
  catch ( std::exception )
  {
    HIWORD(v14) = 1084;
    v13 = -2147418113;
    v3 = a1;
  }
  catch ( const ATL::CAtlException *v35 )
  {
    HIWORD(v14) = 1084;
    v13 = *(_DWORD *)v35;
    v3 = a1;
  }
  v19 = 0;
  CEcsFunctionTracer::~CEcsFunctionTracer((CEcsFunctionTracer *)&v13);
  return v3;
}

```

## disassembly

```asm
0x1800c9888  mov     [rsp+arg_8], rbx
0x1800c988d  mov     [rsp+arg_0], rcx
0x1800c9892  push    rsi
0x1800c9893  push    rdi
0x1800c9894  push    r14
0x1800c9896  sub     rsp, 0E0h
0x1800c989d  mov     r14, rdx
0x1800c98a0  mov     rsi, rcx
0x1800c98a3  mov     edi, 1
0x1800c98a8  mov     [rsp+0F8h+var_A4], edi
0x1800c98ac  lea     rcx, WPP_GLOBAL_Control
0x1800c98b3  mov     rax, cs:WPP_GLOBAL_Control
0x1800c98ba  cmp     rax, rcx
0x1800c98bd  jz      short loc_1800C98E5
0x1800c98bf  test    byte ptr [rax+44h], 2
0x1800c98c3  jz      short loc_1800C98F8
0x1800c98c5  cmp     byte ptr [rax+41h], 6
0x1800c98c9  jb      short loc_1800C98E5
0x1800c98cb  lea     edx, [rdi+1Eh]
0x1800c98ce  lea     r8, WPP_8b4d22724a6b38af4ccce8fe2dcddd63_Traceguids
0x1800c98d5  mov     rcx, [rax+38h]
0x1800c98d9  call    WPP_SF_
0x1800c98de  mov     rax, cs:WPP_GLOBAL_Control
0x1800c98e5  test    byte ptr [rax+44h], 2
0x1800c98e9  jz      short loc_1800C98F8
0x1800c98eb  cmp     byte ptr [rax+41h], 6
0x1800c98ef  jb      short loc_1800C98F8
0x1800c98f1  mov     al, dil
0x1800c98f4  xor     ebx, ebx
0x1800c98f6  jmp     short loc_1800C98FC
0x1800c98f8  xor     ebx, ebx
0x1800c98fa  mov     al, bl
0x1800c98fc  mov     [rsp+0F8h+var_C8], ebx
0x1800c9900  mov     [rsp+0F8h+var_C4], 40Ah
0x1800c9908  mov     [rsp+0F8h+var_C0], al
0x1800c990c  lea     rax, aFindclientcert; "FindClientCertificate"
0x1800c9913  mov     [rsp+0F8h+var_B8], rax
0x1800c9918  mov     [rsp+0F8h+var_B0], rbx
0x1800c991d  mov     rcx, rsi
0x1800c9920  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x1800c9925  nop
0x1800c9926  mov     [rsp+0F8h+var_A4], edi
0x1800c992a  mov     [rsp+0F8h+hCertStore], rbx
0x1800c992f  lea     rcx, [rsp+0F8h+var_88]
0x1800c9934  call    ??0?$CComPtrBase@UIFileInfoFromDisk@@@ATL@@IEAA@PEAUIFileInfoFromDisk@@@Z; ATL::CComPtrBase<IFileInfoFromDisk>::CComPtrBase<IFileInfoFromDisk>(IFileInfoFromDisk *)
0x1800c9939  nop
0x1800c993a  mov     [rsp+0F8h+var_78], rbx
0x1800c9942  mov     [rsp+0F8h+Buffer], rbx
0x1800c9947  mov     [rsp+0F8h+dwBufferLength], ebx
0x1800c994b  xorps   xmm0, xmm0
0x1800c994e  xor     eax, eax
0x1800c9950  movups  [rsp+0F8h+var_58], xmm0
0x1800c9958  movups  [rsp+0F8h+var_48], xmm0
0x1800c9960  movups  [rsp+0F8h+var_38], xmm0
0x1800c9968  mov     [rsp+0F8h+var_28], rax
0x1800c9970  mov     [rsp+0F8h+dwBufferLength], 8
0x1800c9978  mov     eax, [rsp+0F8h+var_C8]
0x1800c997c  mov     [rsp+0F8h+var_C8], eax
0x1800c9980  lea     r9, [rsp+0F8h+dwBufferLength]; lpdwBufferLength
0x1800c9985  lea     r8, [rsp+0F8h+Buffer]; lpBuffer
0x1800c998a  mov     edx, 5Eh ; '^'; dwOption
0x1800c998f  mov     rcx, r14; hInternet
0x1800c9992  call    cs:__imp_WinHttpQueryOption
0x1800c9998  test    eax, eax
0x1800c999a  jnz     short loc_1800C99C4
0x1800c999c  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800c99a1  mov     [rsp+0F8h+var_C8], eax
0x1800c99a5  mov     ecx, 41Ah
0x1800c99aa  mov     word ptr [rsp+0F8h+var_C4+2], cx
0x1800c99af  mov     [rsp+0F8h+pExceptionObject], eax
0x1800c99b3  lea     rdx, _TI1J; pThrowInfo
0x1800c99ba  lea     rcx, [rsp+0F8h+pExceptionObject]; pExceptionObject
0x1800c99bf  call    _CxxThrowException_0
0x1800c99c4  mov     [rsp+0F8h+var_C8], ebx
0x1800c99c8  mov     ecx, 41Ah
0x1800c99cd  mov     word ptr [rsp+0F8h+var_C4], cx
0x1800c99d2  mov     rax, [rsp+0F8h+Buffer]
0x1800c99d7  mov     [rsp+0F8h+arg_10], rax
0x1800c99df  lea     rdx, [rsp+0F8h+arg_10]
0x1800c99e7  lea     rcx, [rsp+0F8h+var_78]
0x1800c99ef  call    ?reset@?$EcsUniqueHandle@PEAXUGlobalMemoryDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,GlobalMemoryDeleter,0>::reset(void * const &)
0x1800c99f4  lea     rdx, szSubsystemProtocol; "MY"
0x1800c99fb  xor     ecx, ecx; hProv
0x1800c99fd  call    cs:__imp_CertOpenSystemStoreW
0x1800c9a03  mov     [rsp+0F8h+arg_18], rax
0x1800c9a0b  lea     rdx, [rsp+0F8h+arg_18]
0x1800c9a13  lea     rcx, [rsp+0F8h+hCertStore]
0x1800c9a18  call    ?reset@?$EcsUniqueHandle@PEAXU?$CertStoreDeleter@$0A@@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,CertStoreDeleter<0>,0>::reset(void * const &)
0x1800c9a1d  mov     eax, [rsp+0F8h+var_C8]
0x1800c9a21  mov     [rsp+0F8h+var_C8], eax
0x1800c9a25  mov     rcx, [rsp+0F8h+hCertStore]; hCertStore
0x1800c9a2a  test    rcx, rcx
0x1800c9a2d  jnz     short loc_1800C9A57
0x1800c9a2f  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800c9a34  mov     [rsp+0F8h+var_C8], eax
0x1800c9a38  mov     edx, 421h
0x1800c9a3d  mov     word ptr [rsp+0F8h+var_C4+2], dx
0x1800c9a42  mov     [rsp+0F8h+var_9C], eax
0x1800c9a46  lea     rdx, _TI1J; pThrowInfo
0x1800c9a4d  lea     rcx, [rsp+0F8h+var_9C]; pExceptionObject
0x1800c9a52  call    _CxxThrowException_0
0x1800c9a57  mov     [rsp+0F8h+var_C8], ebx
0x1800c9a5b  mov     edx, 421h
0x1800c9a60  mov     word ptr [rsp+0F8h+var_C4], dx
0x1800c9a65  mov     dword ptr [rsp+0F8h+var_58], 38h ; '8'
0x1800c9a70  mov     rdx, [rsp+0F8h+Buffer]
0x1800c9a75  mov     eax, [rdx+8]
0x1800c9a78  mov     dword ptr [rsp+0F8h+var_48+8], eax
0x1800c9a7f  mov     rax, [rdx]
0x1800c9a82  mov     qword ptr [rsp+0F8h+var_38], rax
0x1800c9a8a  mov     [rsp+0F8h+pPrevChainContext], rbx; pPrevChainContext
0x1800c9a8f  lea     rax, [rsp+0F8h+var_58]
0x1800c9a97  mov     [rsp+0F8h+pvFindPara], rax; pvFindPara
0x1800c9a9c  mov     r9d, edi; dwFindType
0x1800c9a9f  mov     r8d, 8004h; dwFindFlags
0x1800c9aa5  mov     edx, edi; dwCertEncodingType
0x1800c9aa7  call    cs:__imp_CertFindChainInStore
0x1800c9aad  mov     rdx, rax
0x1800c9ab0  lea     rcx, [rsp+0F8h+var_88]
0x1800c9ab5  call    ?reset@?$unique_ptr@$$CBU_CERT_CHAIN_CONTEXT@@UCertChainContextDeleter@@@std@@QEAAXPEBU_CERT_CHAIN_CONTEXT@@@Z; std::unique_ptr<_CERT_CHAIN_CONTEXT const,CertChainContextDeleter>::reset(_CERT_CHAIN_CONTEXT const *)
0x1800c9aba  mov     eax, [rsp+0F8h+var_C8]
0x1800c9abe  mov     [rsp+0F8h+var_C8], eax
0x1800c9ac2  mov     rax, [rsp+0F8h+var_88]
0x1800c9ac7  test    rax, rax
0x1800c9aca  jnz     short loc_1800C9AF4
0x1800c9acc  call    ?EcsGetLastFailureAsHRESULT@@YAJXZ; EcsGetLastFailureAsHRESULT(void)
0x1800c9ad1  mov     [rsp+0F8h+var_C8], eax
0x1800c9ad5  mov     ecx, 42Fh
0x1800c9ada  mov     word ptr [rsp+0F8h+var_C4+2], cx
0x1800c9adf  mov     [rsp+0F8h+var_98], eax
0x1800c9ae3  lea     rdx, _TI1J; pThrowInfo
0x1800c9aea  lea     rcx, [rsp+0F8h+var_98]; pExceptionObject
0x1800c9aef  call    _CxxThrowException_0
0x1800c9af4  mov     edx, ebx
0x1800c9af6  mov     [rsp+0F8h+var_C8], ebx
0x1800c9afa  mov     ecx, 42Fh
0x1800c9aff  mov     word ptr [rsp+0F8h+var_C4], cx
0x1800c9b04  cmp     [rax+0Ch], ebx
0x1800c9b07  jz      short loc_1800C9B44
0x1800c9b09  mov     rcx, [rax+10h]
0x1800c9b0d  mov     rax, [rcx]
0x1800c9b10  test    rax, rax
0x1800c9b13  jz      short loc_1800C9B44
0x1800c9b15  cmp     [rax+0Ch], ebx
0x1800c9b18  jz      short loc_1800C9B44
0x1800c9b1a  mov     rax, [rax+10h]
0x1800c9b1e  mov     rcx, [rax]
0x1800c9b21  test    rcx, rcx
0x1800c9b24  jz      short loc_1800C9B44
0x1800c9b26  mov     rcx, [rcx+8]; pCertContext
0x1800c9b2a  test    rcx, rcx
0x1800c9b2d  jz      short loc_1800C9B44
0x1800c9b2f  call    cs:__imp_CertDuplicateCertificateContext
0x1800c9b35  mov     rdx, rax
0x1800c9b38  mov     rcx, rsi
0x1800c9b3b  call    ?reset@?$unique_ptr@$$CBU_CERT_CONTEXT@@UCertContextDeleter@@@std@@QEAAXPEBU_CERT_CONTEXT@@@Z; std::unique_ptr<_CERT_CONTEXT const,CertContextDeleter>::reset(_CERT_CONTEXT const *)
0x1800c9b40  mov     edx, [rsp+0F8h+var_C8]
0x1800c9b44  mov     [rsp+0F8h+var_C8], edx
0x1800c9b48  mov     eax, 43Ah
0x1800c9b4d  cmp     [rsi], rbx
0x1800c9b50  jnz     short loc_1800C9B75
0x1800c9b52  mov     ecx, 8000FFFFh
0x1800c9b57  mov     [rsp+0F8h+var_C8], ecx
0x1800c9b5b  mov     word ptr [rsp+0F8h+var_C4+2], ax
0x1800c9b60  mov     [rsp+0F8h+var_94], ecx
0x1800c9b64  lea     rdx, _TI1J; pThrowInfo
0x1800c9b6b  lea     rcx, [rsp+0F8h+var_94]; pExceptionObject
0x1800c9b70  call    _CxxThrowException_0
0x1800c9b75  mov     [rsp+0F8h+var_C8], ebx
0x1800c9b79  mov     word ptr [rsp+0F8h+var_C4], ax
0x1800c9b7e  mov     [rsp+0F8h+var_68], rbx
0x1800c9b86  lea     rdx, [rsp+0F8h+var_68]
0x1800c9b8e  lea     rcx, [rsp+0F8h+var_78]
0x1800c9b96  call    ?reset@?$EcsUniqueHandle@PEAXUGlobalMemoryDeleter@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,GlobalMemoryDeleter,0>::reset(void * const &)
0x1800c9b9b  nop
0x1800c9b9c  lea     rcx, [rsp+0F8h+var_88]
0x1800c9ba1  call    ??1?$unique_ptr@$$CBU_CERT_CHAIN_CONTEXT@@UCertChainContextDeleter@@@std@@QEAA@XZ; std::unique_ptr<_CERT_CHAIN_CONTEXT const,CertChainContextDeleter>::~unique_ptr<_CERT_CHAIN_CONTEXT const,CertChainContextDeleter>(void)
0x1800c9ba6  nop
0x1800c9ba7  mov     [rsp+0F8h+var_60], rbx
0x1800c9baf  lea     rdx, [rsp+0F8h+var_60]
0x1800c9bb7  lea     rcx, [rsp+0F8h+hCertStore]
0x1800c9bbc  call    ?reset@?$EcsUniqueHandle@PEAXU?$CertStoreDeleter@$0A@@@$0A@@@QEAAXAEBQEAX@Z; EcsUniqueHandle<void *,CertStoreDeleter<0>,0>::reset(void * const &)
0x1800c9bc1  nop
0x1800c9bc2  jmp     short loc_1800C9BD7
0x1800c9bc4  jmp     short loc_1800C9BCA
0x1800c9bc6  jmp     short loc_1800C9BCA
0x1800c9bc8  jmp     short $+2
0x1800c9bca  mov     rsi, [rsp+0F8h+arg_0]
0x1800c9bd2  mov     edi, 1
0x1800c9bd7  and     edi, 0FFFFFFFEh
0x1800c9bda  mov     [rsp+0F8h+var_A4], edi
0x1800c9bde  lea     rcx, [rsp+0F8h+var_C8]; this
0x1800c9be3  call    ??1CEcsFunctionTracer@@QEAA@XZ; CEcsFunctionTracer::~CEcsFunctionTracer(void)
0x1800c9be8  mov     rax, rsi
0x1800c9beb  mov     rbx, [rsp+0F8h+arg_8]
0x1800c9bf3  add     rsp, 0E0h
0x1800c9bfa  pop     r14
0x1800c9bfc  pop     rdi
0x1800c9bfd  pop     rsi
0x1800c9bfe  retn
```
