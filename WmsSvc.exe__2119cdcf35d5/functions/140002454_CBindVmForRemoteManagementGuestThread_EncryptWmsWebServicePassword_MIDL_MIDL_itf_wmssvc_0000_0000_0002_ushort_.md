# CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword(__MIDL___MIDL_itf_wmssvc_0000_0000_0002,ushort const *,ushort * *)

- ea: `0x140002454`
- end: `0x140002a06`
- name: `?EncryptWmsWebServicePassword@CBindVmForRemoteManagementGuestThread@@AEAAJW4__MIDL___MIDL_itf_wmssvc_0000_0000_0002@@PEBGPEAPEAG@Z`
- size: `1458`
- prototype: `__int64 __fastcall(__int64, __int64, const WCHAR *, unsigned __int16 **)`
- caller_count: `1`
- callee_count: `10`
- tags: `file_ops, service_task`

## callers

- `0x14000308c`

## callees

- `0x1400016b8`
- `0x1400016c4`
- `0x140002454`
- `0x14005bc30`
- `0x14005bc68`
- `0x14005bfec`
- `0x14005c408`
- `0x140062fb8`
- `0x1400631e8`
- `0x14007e010`

## import_xrefs

- `ADVAPI32!CryptAcquireContextW` at `0x1400024f1`
- `ADVAPI32!CryptAcquireContextW` at `0x1400024f1`
- `ADVAPI32!CryptImportKey` at `0x14000268c`
- `ADVAPI32!CryptImportKey` at `0x14000268c`
- `ADVAPI32!CryptEncrypt` at `0x140002701`
- `ADVAPI32!CryptEncrypt` at `0x140002957`
- `ADVAPI32!CryptEncrypt` at `0x140002701`
- `ADVAPI32!CryptEncrypt` at `0x140002957`
- `ADVAPI32!CryptDestroyKey` at `0x1400025a3`
- `ADVAPI32!CryptDestroyKey` at `0x1400025a3`
- `ADVAPI32!CryptReleaseContext` at `0x1400025b4`
- `ADVAPI32!CryptReleaseContext` at `0x1400025b4`
- `KERNEL32!GetLastError` at `0x1400024ff`
- `KERNEL32!GetLastError` at `0x140002696`
- `KERNEL32!GetLastError` at `0x14000270b`
- `KERNEL32!GetLastError` at `0x140002961`
- `KERNEL32!GetLastError` at `0x1400024ff`
- `KERNEL32!GetLastError` at `0x140002696`
- `KERNEL32!GetLastError` at `0x14000270b`
- `KERNEL32!GetLastError` at `0x140002961`
- `KERNEL32!IsDebuggerPresent` at `0x14000255a`
- `KERNEL32!IsDebuggerPresent` at `0x140002762`
- `KERNEL32!IsDebuggerPresent` at `0x1400027ce`
- `KERNEL32!IsDebuggerPresent` at `0x140002894`
- `KERNEL32!IsDebuggerPresent` at `0x1400029b8`
- `KERNEL32!IsDebuggerPresent` at `0x14000255a`
- `KERNEL32!IsDebuggerPresent` at `0x140002762`
- `KERNEL32!IsDebuggerPresent` at `0x1400027ce`
- `KERNEL32!IsDebuggerPresent` at `0x140002894`
- `KERNEL32!IsDebuggerPresent` at `0x1400029b8`
- `msvcrt!memcpy_s` at `0x14000291c`
- `msvcrt!memcpy_s` at `0x14000291c`
- `OLEAUT32!__imp_SysFreeString` at `0x1400025be`
- `OLEAUT32!__imp_SysFreeString` at `0x1400025ee`
- `OLEAUT32!__imp_SysFreeString` at `0x1400025be`
- `OLEAUT32!__imp_SysFreeString` at `0x1400025ee`
- `OLEAUT32!__imp_SysStringLen` at `0x1400025cd`
- `OLEAUT32!__imp_SysStringLen` at `0x1400025cd`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400026ba`
- `OLEAUT32!__imp_SysStringByteLen` at `0x1400026ba`

## string_xrefs

- `0x14000252f`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140002735`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x1400027b4`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140002871`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x14000298b`: `termsrv\wms\src\devices\wmssvc\bindvmforremotemanagementguestthread.cpp`
- `0x140002528`: `CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword`
- `0x14000272e`: `CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword`
- `0x1400027a8`: `CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword`
- `0x140002866`: `CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword`
- `0x140002984`: `CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword`
- `0x1400026c6`: `CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword - Calling CryptEncrypt to get buffer size, cbEncrypted=%lu, cbUnencryptedWmsControlPassword=%lu \n`
- `0x140002791`: `cbEncrypted >= cbUnencryptedWmsWebServicePassword`
- `0x1400027d6`: `cbEncrypted >= cbUnencryptedWmsWebServicePassword`
- `0x14000283a`: `CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword - Calling CryptEncrypt to encrypt data, cbEncrypted=%lu\n`
- `0x140002926`: `CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword - Calling CryptEncrypt to encrypt data, cbEncrypted=%lu, cbUnencryptedWmsWebServicePassword=%lu \n`

## pseudocode

```c
__int64 __fastcall CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        unsigned __int16 **a4)
{
  __int64 *v4; // rcx
  BYTE *v5; // r14
  unsigned __int16 *v8; // r15
  BYTE *v9; // r13
  __int64 v10; // rax
  __int64 (__fastcall *v11)(__int64 *, __int64, BSTR *, BSTR *); // rax
  signed int v12; // ebx
  signed int LastError; // eax
  unsigned int v14; // r12d
  __int64 v15; // r9
  OLECHAR *v16; // rcx
  __int64 v17; // rax
  __int64 v19; // r8
  signed int v20; // eax
  signed int v21; // eax
  BYTE *v22; // rax
  signed int v23; // eax
  DWORD dwBufLen[2]; // [rsp+30h] [rbp-49h]
  BYTE *pbData; // [rsp+40h] [rbp-39h] BYREF
  rsize_t SourceSize; // [rsp+48h] [rbp-31h] BYREF
  unsigned __int16 *v27; // [rsp+50h] [rbp-29h]
  DWORD dwDataLen; // [rsp+58h] [rbp-21h] BYREF
  BSTR pbstr; // [rsp+60h] [rbp-19h] BYREF
  HCRYPTKEY hKey; // [rsp+68h] [rbp-11h] BYREF
  unsigned __int16 *v31; // [rsp+70h] [rbp-9h] BYREF
  HCRYPTPROV phProv; // [rsp+78h] [rbp-1h] BYREF
  BSTR bstrString[10]; // [rsp+80h] [rbp+7h] BYREF
  DWORD pdwDataLen; // [rsp+E0h] [rbp+67h] BYREF

  v4 = *(__int64 **)(a1 + 336);
  v5 = 0;
  bstrString[0] = 0;
  pbstr = 0;
  phProv = 0;
  hKey = 0;
  LODWORD(SourceSize) = 0;
  v8 = 0;
  pdwDataLen = 0;
  v9 = 0;
  v10 = *v4;
  pbData = 0;
  dwDataLen = 0;
  v27 = 0;
  v11 = *(__int64 (__fastcall **)(__int64 *, __int64, BSTR *, BSTR *))(v10 + 224);
  v31 = 0;
  v12 = v11(v4, a2, bstrString, &pbstr);
  if ( v12 >= 0 )
  {
    if ( !CryptAcquireContextW(&phProv, 0, 0, 1u, 0xF0000040) )
    {
      LastError = GetLastError();
      v12 = LastError;
      if ( LastError > 0 )
        v12 = (unsigned __int16)LastError | 0x80070000;
      v14 = 251;
LABEL_6:
      if ( v12 >= 0 )
        v12 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        v14,
        L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword",
        L"CBRAEx",
        L"fSuccess",
        v12);
      if ( IsDebuggerPresent() )
      {
        v15 = v14;
LABEL_10:
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          v15,
          L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword",
          L"CBRAEx",
          L"fSuccess",
          v12);
LABEL_11:
        v8 = v27;
LABEL_12:
        v5 = pbData;
        goto LABEL_13;
      }
      v19 = v14;
      goto LABEL_24;
    }
    v12 = WmsBase64Decode(a3, &dwDataLen, &pbData);
    if ( v12 < 0 )
      goto LABEL_12;
    v5 = pbData;
    if ( !CryptImportKey(phProv, pbData, dwDataLen, 0, 0, &hKey) )
    {
      v20 = GetLastError();
      v12 = v20;
      if ( v20 > 0 )
        v12 = (unsigned __int16)v20 | 0x80070000;
      v14 = 257;
      goto LABEL_6;
    }
    LODWORD(SourceSize) = SysStringByteLen(pbstr) + 2;
    pdwDataLen = SourceSize;
    DEBUGMSG(
      L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword - Calling CryptEncrypt to get buffer size, cbE"
       "ncrypted=%lu, cbUnencryptedWmsControlPassword=%lu \n",
      (unsigned int)SourceSize,
      (unsigned int)SourceSize);
    if ( !CryptEncrypt(hKey, 0, 1, 0, 0, &pdwDataLen, 0) )
    {
      v21 = GetLastError();
      v12 = v21;
      if ( v21 > 0 )
        v12 = (unsigned __int16)v21 | 0x80070000;
      if ( v12 >= 0 )
        v12 = -2147467259;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        0x108u,
        L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword",
        L"CBRAEx",
        L"fSuccess",
        v12);
      if ( IsDebuggerPresent() )
      {
        v15 = 264;
        goto LABEL_10;
      }
      v19 = 264;
LABEL_24:
      dwBufLen[0] = v12;
      DEBUGMSGBOX(
        L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        v19,
        L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword",
        L"CBRAEx",
        L"fSuccess",
        *(_QWORD *)dwBufLen);
      goto LABEL_11;
    }
    if ( pdwDataLen < (unsigned int)SourceSize )
    {
      v12 = -2147418113;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        0x109u,
        L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword",
        L"CBRAEx",
        L"cbEncrypted >= cbUnencryptedWmsWebServicePassword",
        -2147418113);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          265,
          L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword",
          L"CBRAEx",
          L"cbEncrypted >= cbUnencryptedWmsWebServicePassword",
          -2147418113);
      }
      else
      {
        dwBufLen[0] = -2147418113;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          265,
          L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword",
          L"CBRAEx",
          L"cbEncrypted >= cbUnencryptedWmsWebServicePassword",
          *(_QWORD *)dwBufLen);
      }
      goto LABEL_12;
    }
    DEBUGMSG(
      L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword - Calling CryptEncrypt to encrypt data, cbEncrypted=%lu\n");
    v22 = (BYTE *)operator new(pdwDataLen);
    v9 = v22;
    if ( v22 )
    {
      memcpy_s(v22, pdwDataLen, pbstr, (unsigned int)SourceSize);
      DEBUGMSG(
        L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword - Calling CryptEncrypt to encrypt data, cbEn"
         "crypted=%lu, cbUnencryptedWmsWebServicePassword=%lu \n",
        pdwDataLen,
        (unsigned int)SourceSize);
      if ( !CryptEncrypt(hKey, 0, 1, 0, v9, (DWORD *)&SourceSize, pdwDataLen) )
      {
        v23 = GetLastError();
        v12 = v23;
        if ( v23 > 0 )
          v12 = (unsigned __int16)v23 | 0x80070000;
        if ( v12 >= 0 )
          v12 = -2147467259;
        LOGASSERTHR(
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          0x114u,
          L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword",
          L"CBRAEx",
          L"fSuccess",
          v12);
        if ( IsDebuggerPresent() )
        {
          v15 = 276;
          goto LABEL_10;
        }
        v19 = 276;
        goto LABEL_24;
      }
      v12 = WmsBase64Encode(pdwDataLen, v9, &v31, &dwDataLen);
      if ( v12 < 0 )
        v8 = v31;
      else
        *a4 = v31;
    }
    else
    {
      v12 = -2147024882;
      LOGASSERTHR(
        L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
        0x10Du,
        L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword",
        L"CPR",
        L"pbEncrypted",
        -2147024882);
      if ( IsDebuggerPresent() )
      {
        DEBUGMSGLEVEL(
          2u,
          L"%s(%d) - %s - Assertion failed:  %s (%s)  hr = 0x%08X\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          269,
          L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword",
          L"CPR",
          L"pbEncrypted",
          -2147024882);
      }
      else
      {
        dwBufLen[0] = -2147024882;
        DEBUGMSGBOX(
          L"Assertion failed:  %s(%d) - %s - %s (%s)  hr = 0x%08X\n\n",
          L"termsrv\\wms\\src\\devices\\wmssvc\\bindvmforremotemanagementguestthread.cpp",
          269,
          L"CBindVmForRemoteManagementGuestThread::EncryptWmsWebServicePassword",
          L"CPR",
          L"pbEncrypted",
          *(_QWORD *)dwBufLen);
      }
    }
  }
LABEL_13:
  if ( hKey )
    CryptDestroyKey(hKey);
  if ( phProv )
    CryptReleaseContext(phProv, 0);
  SysFreeString(bstrString[0]);
  if ( pbstr )
  {
    LODWORD(v17) = SysStringLen(pbstr);
    v16 = pbstr;
    v17 = (unsigned int)v17;
    if ( (_DWORD)v17 )
    {
      do
      {
        *(_BYTE *)v16 = 0;
        v16 = (OLECHAR *)((char *)v16 + 1);
        --v17;
      }
      while ( v17 );
      v16 = pbstr;
    }
    SysFreeString(v16);
    pbstr = 0;
  }
  operator delete(v5);
  operator delete(v9);
  operator delete(v8);
  return (unsigned int)v12;
}

```

## disassembly

```asm
0x140002454  push    rbp
0x140002456  push    rbx
0x140002457  push    rsi
0x140002458  push    rdi
0x140002459  push    r12
0x14000245b  push    r13
0x14000245d  push    r14
0x14000245f  push    r15
0x140002461  lea     rbp, [rsp-1Fh]
0x140002466  sub     rsp, 98h
0x14000246d  mov     rcx, [rcx+150h]
0x140002474  xor     r14d, r14d
0x140002477  mov     [rbp+57h+bstrString], 0
0x14000247f  mov     rsi, r9
0x140002482  mov     [rbp+57h+pbstr], 0
0x14000248a  lea     r9, [rbp+57h+pbstr]
0x14000248e  mov     [rbp+57h+phProv], 0
0x140002496  mov     rdi, r8
0x140002499  mov     [rbp+57h+hKey], 0
0x1400024a1  lea     r8, [rbp+57h+bstrString]
0x1400024a5  mov     dword ptr [rbp+57h+SourceSize], r14d
0x1400024a9  xor     r15d, r15d
0x1400024ac  mov     [rbp+57h+pdwDataLen], r14d
0x1400024b0  xor     r13d, r13d
0x1400024b3  mov     rax, [rcx]
0x1400024b6  mov     [rbp+57h+pbData], r14
0x1400024ba  mov     [rbp+57h+dwDataLen], r14d
0x1400024be  mov     [rbp+57h+var_80], r15
0x1400024c2  mov     rax, [rax+0E0h]
0x1400024c9  mov     [rbp+57h+var_60], r15
0x1400024cd  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1400024d2  mov     ebx, eax
0x1400024d4  test    eax, eax
0x1400024d6  js      loc_14000259A
0x1400024dc  lea     r9d, [r14+1]; dwProvType
0x1400024e0  mov     [rsp+0D0h+dwFlags], 0F0000040h; dwFlags
0x1400024e8  xor     r8d, r8d; szProvider
0x1400024eb  lea     rcx, [rbp+57h+phProv]; phProv
0x1400024ef  xor     edx, edx; szContainer
0x1400024f1  call    cs:__imp_CryptAcquireContextW
0x1400024f7  test    eax, eax
0x1400024f9  jnz     loc_140002652
0x1400024ff  call    cs:__imp_GetLastError
0x140002505  mov     ebx, eax
0x140002507  test    eax, eax
0x140002509  jle     short loc_140002514
0x14000250b  movzx   ebx, ax
0x14000250e  or      ebx, 80070000h
0x140002514  mov     r12d, 0FBh
0x14000251a  mov     eax, 80004005h
0x14000251f  lea     r14, aCbraex; "CBRAEx"
0x140002526  test    ebx, ebx
0x140002528  lea     rsi, aCbindvmforremo_3; "CBindVmForRemoteManagementGuestThread::"...
0x14000252f  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140002536  mov     r9, r14; unsigned __int16 *
0x140002539  cmovns  ebx, eax
0x14000253c  lea     r15, aFsuccess; "fSuccess"
0x140002543  mov     dword ptr [rsp+0D0h+phKey], ebx; int
0x140002547  mov     r8, rsi; unsigned __int16 *
0x14000254a  mov     edx, r12d; unsigned int
0x14000254d  mov     qword ptr [rsp+0D0h+dwFlags], r15; unsigned __int16 *
0x140002552  mov     rcx, rdi; unsigned __int16 *
0x140002555  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x14000255a  call    cs:__imp_IsDebuggerPresent
0x140002560  test    eax, eax
0x140002562  jz      loc_14000262A
0x140002568  mov     r9d, r12d
0x14000256b  mov     ecx, 2; unsigned __int8
0x140002570  mov     [rsp+0D0h+var_98], ebx
0x140002574  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x14000257b  mov     qword ptr [rsp+0D0h+dwBufLen], r15
0x140002580  mov     r8, rdi
0x140002583  mov     [rsp+0D0h+phKey], r14
0x140002588  mov     qword ptr [rsp+0D0h+dwFlags], rsi
0x14000258d  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x140002592  mov     r15, [rbp+57h+var_80]
0x140002596  mov     r14, [rbp+57h+pbData]
0x14000259a  mov     rcx, [rbp+57h+hKey]; hKey
0x14000259e  test    rcx, rcx
0x1400025a1  jz      short loc_1400025A9
0x1400025a3  call    cs:__imp_CryptDestroyKey
0x1400025a9  mov     rcx, [rbp+57h+phProv]; hProv
0x1400025ad  test    rcx, rcx
0x1400025b0  jz      short loc_1400025BA
0x1400025b2  xor     edx, edx; dwFlags
0x1400025b4  call    cs:__imp_CryptReleaseContext
0x1400025ba  mov     rcx, [rbp+57h+bstrString]; bstrString
0x1400025be  call    cs:__imp_SysFreeString
0x1400025c4  mov     rcx, [rbp+57h+pbstr]; pbstr
0x1400025c8  test    rcx, rcx
0x1400025cb  jz      short loc_1400025FC
0x1400025cd  call    cs:__imp_SysStringLen
0x1400025d3  mov     rcx, [rbp+57h+pbstr]
0x1400025d7  mov     eax, eax
0x1400025d9  test    rax, rax
0x1400025dc  jz      short loc_1400025EE
0x1400025de  mov     byte ptr [rcx], 0
0x1400025e1  inc     rcx
0x1400025e4  sub     rax, 1
0x1400025e8  jnz     short loc_1400025DE
0x1400025ea  mov     rcx, [rbp+57h+pbstr]; bstrString
0x1400025ee  call    cs:__imp_SysFreeString
0x1400025f4  mov     [rbp+57h+pbstr], 0
0x1400025fc  mov     rcx, r14; Block
0x1400025ff  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002604  mov     rcx, r13; Block
0x140002607  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14000260c  mov     rcx, r15; Block
0x14000260f  call    ??3@YAXPEAX@Z; operator delete(void *)
0x140002614  mov     eax, ebx
0x140002616  add     rsp, 98h
0x14000261d  pop     r15
0x14000261f  pop     r14
0x140002621  pop     r13
0x140002623  pop     r12
0x140002625  pop     rdi
0x140002626  pop     rsi
0x140002627  pop     rbx
0x140002628  pop     rbp
0x140002629  retn
0x14000262a  mov     r8d, r12d
0x14000262d  mov     [rsp+0D0h+dwBufLen], ebx
0x140002631  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x140002638  mov     [rsp+0D0h+phKey], r15
0x14000263d  mov     r9, rsi
0x140002640  mov     rdx, rdi
0x140002643  mov     qword ptr [rsp+0D0h+dwFlags], r14
0x140002648  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x14000264d  jmp     loc_140002592
0x140002652  lea     r8, [rbp+57h+pbData]; unsigned __int8 **
0x140002656  mov     rcx, rdi; pszString
0x140002659  lea     rdx, [rbp+57h+dwDataLen]; unsigned int *
0x14000265d  call    ?WmsBase64Decode@@YAJPEBGPEAKPEAPEAE@Z; WmsBase64Decode(ushort const *,ulong *,uchar * *)
0x140002662  mov     ebx, eax
0x140002664  test    eax, eax
0x140002666  js      loc_140002596
0x14000266c  mov     r14, [rbp+57h+pbData]
0x140002670  lea     rax, [rbp+57h+hKey]
0x140002674  mov     r8d, [rbp+57h+dwDataLen]; dwDataLen
0x140002678  mov     rdx, r14; pbData
0x14000267b  mov     rcx, [rbp+57h+phProv]; hProv
0x14000267f  xor     r9d, r9d; hPubKey
0x140002682  mov     [rsp+0D0h+phKey], rax; phKey
0x140002687  mov     [rsp+0D0h+dwFlags], r13d; dwFlags
0x14000268c  call    cs:__imp_CryptImportKey
0x140002692  test    eax, eax
0x140002694  jnz     short loc_1400026B6
0x140002696  call    cs:__imp_GetLastError
0x14000269c  mov     ebx, eax
0x14000269e  test    eax, eax
0x1400026a0  jle     short loc_1400026AB
0x1400026a2  movzx   ebx, ax
0x1400026a5  or      ebx, 80070000h
0x1400026ab  mov     r12d, 101h
0x1400026b1  jmp     loc_14000251A
0x1400026b6  mov     rcx, [rbp+57h+pbstr]; bstr
0x1400026ba  call    cs:__imp_SysStringByteLen
0x1400026c0  mov     r12d, 2
0x1400026c6  lea     rcx, aCbindvmforremo_8; "CBindVmForRemoteManagementGuestThread::"...
0x1400026cd  add     eax, r12d
0x1400026d0  mov     r8d, eax
0x1400026d3  mov     dword ptr [rbp+57h+SourceSize], eax
0x1400026d6  mov     edx, eax
0x1400026d8  mov     [rbp+57h+pdwDataLen], eax
0x1400026db  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x1400026e0  mov     rcx, [rbp+57h+hKey]; hKey
0x1400026e4  lea     rax, [rbp+57h+pdwDataLen]
0x1400026e8  mov     [rsp+0D0h+dwBufLen], r13d; dwBufLen
0x1400026ed  lea     r8d, [r12-1]; Final
0x1400026f2  mov     [rsp+0D0h+phKey], rax; pdwDataLen
0x1400026f7  xor     r9d, r9d; dwFlags
0x1400026fa  xor     edx, edx; hHash
0x1400026fc  mov     qword ptr [rsp+0D0h+dwFlags], r13; pbData
0x140002701  call    cs:__imp_CryptEncrypt
0x140002707  test    eax, eax
0x140002709  jnz     short loc_140002785
0x14000270b  call    cs:__imp_GetLastError
0x140002711  mov     ebx, eax
0x140002713  test    eax, eax
0x140002715  jle     short loc_140002720
0x140002717  movzx   ebx, ax
0x14000271a  or      ebx, 80070000h
0x140002720  mov     eax, 80004005h
0x140002725  lea     r14, aCbraex; "CBRAEx"
0x14000272c  test    ebx, ebx
0x14000272e  lea     rsi, aCbindvmforremo_3; "CBindVmForRemoteManagementGuestThread::"...
0x140002735  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x14000273c  mov     r9, r14; unsigned __int16 *
0x14000273f  cmovns  ebx, eax
0x140002742  lea     r15, aFsuccess; "fSuccess"
0x140002749  mov     dword ptr [rsp+0D0h+phKey], ebx; int
0x14000274d  mov     r8, rsi; unsigned __int16 *
0x140002750  mov     edx, 108h; unsigned int
0x140002755  mov     qword ptr [rsp+0D0h+dwFlags], r15; unsigned __int16 *
0x14000275a  mov     rcx, rdi; unsigned __int16 *
0x14000275d  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140002762  call    cs:__imp_IsDebuggerPresent
0x140002768  test    eax, eax
0x14000276a  jz      short loc_14000277A
0x14000276c  mov     r9d, 108h
0x140002772  mov     ecx, r12d
0x140002775  jmp     loc_140002570
0x14000277a  mov     r8d, 108h
0x140002780  jmp     loc_14000262D
0x140002785  mov     edx, [rbp+57h+pdwDataLen]
0x140002788  cmp     edx, dword ptr [rbp+57h+SourceSize]
0x14000278b  jnb     loc_14000283A
0x140002791  lea     rax, aCbencryptedCbu; "cbEncrypted >= cbUnencryptedWmsWebServi"...
0x140002798  mov     ebx, 8000FFFFh
0x14000279d  lea     r14, aCbraex; "CBRAEx"
0x1400027a4  mov     dword ptr [rsp+0D0h+phKey], ebx; int
0x1400027a8  lea     rsi, aCbindvmforremo_3; "CBindVmForRemoteManagementGuestThread::"...
0x1400027af  mov     qword ptr [rsp+0D0h+dwFlags], rax; unsigned __int16 *
0x1400027b4  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x1400027bb  mov     r9, r14; unsigned __int16 *
0x1400027be  mov     r8, rsi; unsigned __int16 *
0x1400027c1  mov     rcx, rdi; unsigned __int16 *
0x1400027c4  mov     edx, 109h; unsigned int
0x1400027c9  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x1400027ce  call    cs:__imp_IsDebuggerPresent
0x1400027d4  test    eax, eax
0x1400027d6  lea     rax, aCbencryptedCbu; "cbEncrypted >= cbUnencryptedWmsWebServi"...
0x1400027dd  jz      short loc_14000280F
0x1400027df  mov     [rsp+0D0h+var_98], ebx
0x1400027e3  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400027ea  mov     qword ptr [rsp+0D0h+dwBufLen], rax
0x1400027ef  mov     r9d, 109h
0x1400027f5  mov     [rsp+0D0h+phKey], r14
0x1400027fa  mov     r8, rdi
0x1400027fd  mov     ecx, r12d; unsigned __int8
0x140002800  mov     qword ptr [rsp+0D0h+dwFlags], rsi
0x140002805  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x14000280a  jmp     loc_140002596
0x14000280f  mov     [rsp+0D0h+dwBufLen], ebx
0x140002813  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x14000281a  mov     [rsp+0D0h+phKey], rax
0x14000281f  mov     r9, rsi
0x140002822  mov     r8d, 109h
0x140002828  mov     qword ptr [rsp+0D0h+dwFlags], r14
0x14000282d  mov     rdx, rdi
0x140002830  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140002835  jmp     loc_140002596
0x14000283a  lea     rcx, aCbindvmforremo_12; "CBindVmForRemoteManagementGuestThread::"...
0x140002841  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002846  mov     ecx, [rbp+57h+pdwDataLen]; Size
0x140002849  call    ??2@YAPEAX_K@Z; operator new(unsigned __int64)
0x14000284e  mov     r13, rax
0x140002851  test    rax, rax
0x140002854  jnz     loc_14000290E
0x14000285a  lea     rax, aPbencrypted; "pbEncrypted"
0x140002861  mov     ebx, 8007000Eh
0x140002866  lea     rsi, aCbindvmforremo_3; "CBindVmForRemoteManagementGuestThread::"...
0x14000286d  mov     dword ptr [rsp+0D0h+phKey], ebx; int
0x140002871  lea     rdi, aTermsrvWmsSrcD_0; "termsrv\\wms\\src\\devices\\wmssvc\\bin"...
0x140002878  mov     qword ptr [rsp+0D0h+dwFlags], rax; unsigned __int16 *
0x14000287d  mov     r8, rsi; unsigned __int16 *
0x140002880  lea     r9, aCpr; "CPR"
0x140002887  mov     rcx, rdi; unsigned __int16 *
0x14000288a  mov     edx, 10Dh; unsigned int
0x14000288f  call    ?LOGASSERTHR@@YAXPEBGK000J@Z; LOGASSERTHR(ushort const *,ulong,ushort const *,ushort const *,ushort const *,long)
0x140002894  call    cs:__imp_IsDebuggerPresent
0x14000289a  test    eax, eax
0x14000289c  lea     rax, aPbencrypted; "pbEncrypted"
0x1400028a3  jz      short loc_1400028DC
0x1400028a5  mov     [rsp+0D0h+var_98], ebx
0x1400028a9  lea     rdx, aSDSAssertionFa_0; "%s(%d) - %s - Assertion failed:  %s (%s"...
0x1400028b0  mov     qword ptr [rsp+0D0h+dwBufLen], rax
0x1400028b5  mov     r9d, 10Dh
0x1400028bb  lea     rax, aCpr; "CPR"
0x1400028c2  mov     r8, rdi
0x1400028c5  mov     [rsp+0D0h+phKey], rax
0x1400028ca  mov     ecx, r12d; unsigned __int8
0x1400028cd  mov     qword ptr [rsp+0D0h+dwFlags], rsi
0x1400028d2  call    ?DEBUGMSGLEVEL@@YAXEPEBGZZ; DEBUGMSGLEVEL(uchar,ushort const *,...)
0x1400028d7  jmp     loc_14000259A
0x1400028dc  mov     [rsp+0D0h+dwBufLen], ebx
0x1400028e0  lea     rcx, aAssertionFaile; "Assertion failed:  %s(%d) - %s - %s (%s"...
0x1400028e7  mov     [rsp+0D0h+phKey], rax
0x1400028ec  mov     r9, rsi
0x1400028ef  lea     rax, aCpr; "CPR"
0x1400028f6  mov     r8d, 10Dh
0x1400028fc  mov     rdx, rdi
0x1400028ff  mov     qword ptr [rsp+0D0h+dwFlags], rax
0x140002904  call    ?DEBUGMSGBOX@@YAHPEBGZZ; DEBUGMSGBOX(ushort const *,...)
0x140002909  jmp     loc_14000259A
0x14000290e  mov     r9d, dword ptr [rbp+57h+SourceSize]; SourceSize
0x140002912  mov     rcx, r13; Destination
0x140002915  mov     edx, [rbp+57h+pdwDataLen]; DestinationSize
0x140002918  mov     r8, [rbp+57h+pbstr]; Source
0x14000291c  call    cs:__imp_memcpy_s
0x140002922  mov     r8d, dword ptr [rbp+57h+SourceSize]
0x140002926  lea     rcx, aCbindvmforremo_14; "CBindVmForRemoteManagementGuestThread::"...
0x14000292d  mov     edx, [rbp+57h+pdwDataLen]
0x140002930  call    ?DEBUGMSG@@YAXPEBGZZ; DEBUGMSG(ushort const *,...)
0x140002935  mov     eax, [rbp+57h+pdwDataLen]
0x140002938  xor     r9d, r9d; dwFlags
0x14000293b  mov     rcx, [rbp+57h+hKey]; hKey
0x14000293f  xor     edx, edx; hHash
0x140002941  mov     [rsp+0D0h+dwBufLen], eax; dwBufLen
0x140002945  lea     rax, [rbp+57h+SourceSize]
  ... truncated ...
```
