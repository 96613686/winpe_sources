# CBrowserBrokerInstance::GetFavoritesHTMLLastUpdatedFileTime(_FILETIME *)

- ea: `0x180009860`
- end: `0x180009be7`
- name: `?GetFavoritesHTMLLastUpdatedFileTime@CBrowserBrokerInstance@@UEAAJPEAU_FILETIME@@@Z`
- size: `903`
- prototype: `int(CBrowserBrokerInstance *__hidden this, struct _FILETIME *)`
- caller_count: `0`
- callee_count: `7`
- tags: `file_ops, reparse_path, registry_config, service_task, installer_update, broker_com_uri`

## callees

- `0x180002ce0`
- `0x180006c90`
- `0x180006cc4`
- `0x180009860`
- `0x18000e428`
- `0x18001bd78`
- `0x18002d010`

## import_xrefs

- `iertutil!CreateUri` at `0x1800098d3`
- `iertutil!CreateUri` at `0x1800098d3`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009987`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180009987`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000996f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ba1`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18000996f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009992`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x1800099e8`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009a66`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009af5`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009b4a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180009ba1`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000994b`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18000994b`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180009965`
- `api-ms-win-core-file-l1-1-0!GetFileTime` at `0x180009965`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180009b97`
- `api-ms-win-core-timezone-l1-1-0!SystemTimeToFileTime` at `0x180009b97`
- `WININET!HttpSendRequestW` at `0x180009b1a`
- `WININET!HttpSendRequestW` at `0x180009b1a`
- `WININET!InternetCloseHandle` at `0x180009b5e`
- `WININET!InternetCloseHandle` at `0x180009b67`
- `WININET!InternetCloseHandle` at `0x180009b7b`
- `WININET!InternetCloseHandle` at `0x180009b5e`
- `WININET!InternetCloseHandle` at `0x180009b67`
- `WININET!InternetCloseHandle` at `0x180009b7b`
- `WININET!HttpOpenRequestW` at `0x180009ae7`
- `WININET!HttpOpenRequestW` at `0x180009ae7`
- `WININET!InternetConnectW` at `0x180009a58`
- `WININET!InternetConnectW` at `0x180009a58`
- `WININET!HttpQueryInfoW` at `0x180009b40`
- `WININET!HttpQueryInfoW` at `0x180009b40`
- `WININET!InternetOpenW` at `0x1800099d5`
- `WININET!InternetOpenW` at `0x1800099d5`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b72`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b86`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b72`
- `OLEAUT32!__imp_SysFreeString` at `0x180009b86`

## pseudocode

```c
// Hidden C++ exception states: #wind=4
__int64 __fastcall CBrowserBrokerInstance::GetFavoritesHTMLLastUpdatedFileTime(
        CBrowserBrokerInstance *this,
        struct _FILETIME *a2)
{
  int PIC; // ebx
  HANDLE FileW; // rax
  void *v5; // rsi
  signed int v6; // eax
  signed int v7; // eax
  void *v8; // r15
  signed int LastError; // eax
  INTERNET_PORT v10; // si
  void *v11; // r14
  signed int v12; // eax
  DWORD v13; // eax
  void *v14; // rsi
  signed int v15; // eax
  signed int v16; // eax
  signed int v17; // eax
  unsigned int v19; // [rsp+40h] [rbp-49h] BYREF
  IUri *ppURI; // [rsp+48h] [rbp-41h] BYREF
  LPCWSTR pwzURI; // [rsp+50h] [rbp-39h] BYREF
  DWORD dwBufferLength; // [rsp+58h] [rbp-31h] BYREF
  LPCWSTR lpszObjectName; // [rsp+60h] [rbp-29h] BYREF
  LPCWSTR lpszServerName; // [rsp+68h] [rbp-21h] BYREF
  LPCWSTR lpszAcceptTypes[2]; // [rsp+70h] [rbp-19h] BYREF
  SYSTEMTIME Buffer; // [rsp+80h] [rbp-9h] BYREF

  v19 = 0;
  PIC = BrokerAuthenticateAttachedCallerGetPIC(1, &v19);
  if ( PIC >= 0 )
  {
    pwzURI = 0;
    PIC = GetProcessedConfiguredFavoritesUrl((LPWSTR *)&pwzURI);
    if ( PIC >= 0 )
    {
      ppURI = 0;
      PIC = CreateUri(pwzURI, 0x3002B84u, 0, &ppURI);
      if ( PIC >= 0 )
      {
        v19 = 0;
        PIC = ((__int64 (__fastcall *)(IUri *, unsigned int *))ppURI->lpVtbl->GetScheme)(ppURI, &v19);
        if ( PIC >= 0 )
        {
          if ( v19 == 2 || v19 == 11 )
          {
            Buffer = 0;
            v8 = InternetOpenW(L"FavoritesEnterpriseClient", 0, 0, 0, 0);
            if ( v8 )
              goto LABEL_20;
            LastError = GetLastError();
            PIC = LastError;
            if ( LastError > 0 )
              PIC = (unsigned __int16)LastError | 0x80070000;
            if ( PIC >= 0 )
            {
LABEL_20:
              v10 = 443;
              if ( v19 != 11 )
                v10 = 80;
              lpszServerName = 0;
              PIC = ((__int64 (__fastcall *)(IUri *, LPCWSTR *))ppURI->lpVtbl->GetHost)(ppURI, &lpszServerName);
              if ( PIC >= 0 )
              {
                v11 = InternetConnectW(v8, lpszServerName, v10, 0, 0, 3u, 0, 0);
                if ( v11 )
                  goto LABEL_27;
                v12 = GetLastError();
                PIC = v12;
                if ( v12 > 0 )
                  PIC = (unsigned __int16)v12 | 0x80070000;
                if ( PIC >= 0 )
                {
LABEL_27:
                  lpszObjectName = 0;
                  PIC = ((__int64 (__fastcall *)(IUri *, LPCWSTR *))ppURI->lpVtbl->GetPath)(ppURI, &lpszObjectName);
                  if ( PIC >= 0 )
                  {
                    lpszAcceptTypes[0] = L"text/*";
                    lpszAcceptTypes[1] = 0;
                    v13 = 0;
                    if ( v19 == 11 )
                      v13 = 0x800000;
                    v14 = HttpOpenRequestW(v11, L"HEAD", lpszObjectName, 0, 0, lpszAcceptTypes, v13, 0);
                    if ( v14 )
                      goto LABEL_49;
                    v15 = GetLastError();
                    PIC = v15;
                    if ( v15 > 0 )
                      PIC = (unsigned __int16)v15 | 0x80070000;
                    if ( PIC >= 0 )
                    {
LABEL_49:
                      if ( !HttpSendRequestW(v14, 0, 0, 0, 0)
                        || (dwBufferLength = 16, !HttpQueryInfoW(v14, 0x4000000Bu, &Buffer, &dwBufferLength, 0)) )
                      {
                        v16 = GetLastError();
                        PIC = v16;
                        if ( v16 > 0 )
                          PIC = (unsigned __int16)v16 | 0x80070000;
                      }
                      InternetCloseHandle(v14);
                    }
                  }
                  InternetCloseHandle(v11);
                  SysFreeString((BSTR)lpszObjectName);
                }
              }
              InternetCloseHandle(v8);
              SysFreeString((BSTR)lpszServerName);
              if ( PIC >= 0 && !SystemTimeToFileTime(&Buffer, a2) )
              {
                v17 = GetLastError();
                PIC = v17;
                if ( v17 > 0 )
                  PIC = (unsigned __int16)v17 | 0x80070000;
              }
            }
          }
          else if ( v19 == 9 )
          {
            FileW = CreateFileW(pwzURI, 0x80000000, 3u, 0, 3u, 0x80u, 0);
            v5 = FileW;
            if ( FileW == (HANDLE)-1LL )
            {
              v7 = GetLastError();
              PIC = v7;
              if ( v7 > 0 )
                PIC = (unsigned __int16)v7 | 0x80070000;
            }
            else
            {
              if ( !GetFileTime(FileW, 0, 0, a2) )
              {
                v6 = GetLastError();
                PIC = v6;
                if ( v6 > 0 )
                  PIC = (unsigned __int16)v6 | 0x80070000;
              }
              CloseHandle(v5);
            }
          }
          else
          {
            PIC = -2147467259;
          }
        }
      }
      ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>((__int64 *)&ppURI);
    }
    CCoTaskMemPtr<unsigned short>::~CCoTaskMemPtr<unsigned short>((void **)&pwzURI);
  }
  return (unsigned int)PIC;
}

```

## disassembly

```asm
0x180009860  push    rbp
0x180009862  push    rbx
0x180009863  push    rsi
0x180009864  push    rdi
0x180009865  push    r12
0x180009867  push    r13
0x180009869  push    r14
0x18000986b  push    r15
0x18000986d  lea     rbp, [rsp-1Fh]
0x180009872  sub     rsp, 0A8h
0x180009879  mov     rax, cs:__security_cookie
0x180009880  xor     rax, rsp
0x180009883  mov     [rbp+57h+var_50], rax
0x180009887  mov     r12, rdx
0x18000988a  xor     r13d, r13d
0x18000988d  mov     [rbp+57h+var_A0], r13d
0x180009891  lea     rdx, [rbp+57h+var_A0]; unsigned int *
0x180009895  lea     ecx, [r13+1]; unsigned int
0x180009899  call    ?BrokerAuthenticateAttachedCallerGetPIC@@YAJKPEAK@Z; BrokerAuthenticateAttachedCallerGetPIC(ulong,ulong *)
0x18000989e  mov     ebx, eax
0x1800098a0  test    eax, eax
0x1800098a2  js      loc_180009BC5
0x1800098a8  mov     [rbp+57h+pwzURI], r13
0x1800098ac  lea     rcx, [rbp+57h+pwzURI]; ppwsz
0x1800098b0  call    ?GetProcessedConfiguredFavoritesUrl@@YAJPEAPEAG@Z; GetProcessedConfiguredFavoritesUrl(ushort * *)
0x1800098b5  mov     ebx, eax
0x1800098b7  test    eax, eax
0x1800098b9  js      loc_180009BBC
0x1800098bf  mov     [rbp+57h+ppURI], r13
0x1800098c3  lea     r9, [rbp+57h+ppURI]; ppURI
0x1800098c7  xor     r8d, r8d; dwReserved
0x1800098ca  mov     edx, 3002B84h; dwFlags
0x1800098cf  mov     rcx, [rbp+57h+pwzURI]; pwzURI
0x1800098d3  call    cs:__imp_CreateUri
0x1800098d9  mov     ebx, eax
0x1800098db  test    eax, eax
0x1800098dd  js      loc_180009BB2
0x1800098e3  mov     [rbp+57h+var_A0], r13d
0x1800098e7  mov     rcx, [rbp+57h+ppURI]
0x1800098eb  mov     rax, [rcx]
0x1800098ee  lea     rdx, [rbp+57h+var_A0]
0x1800098f2  mov     rax, [rax+0C0h]
0x1800098f9  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800098fe  mov     ebx, eax
0x180009900  test    eax, eax
0x180009902  js      loc_180009BB2
0x180009908  mov     eax, [rbp+57h+var_A0]
0x18000990b  cmp     eax, 2
0x18000990e  jz      loc_1800099BA
0x180009914  cmp     eax, 0Bh
0x180009917  jz      loc_1800099BA
0x18000991d  cmp     eax, 9
0x180009920  jnz     loc_1800099B0
0x180009926  mov     [rsp+0E0h+hTemplateFile], r13; hTemplateFile
0x18000992b  mov     [rsp+0E0h+dwFlagsAndAttributes], 80h; dwFlagsAndAttributes
0x180009933  mov     [rsp+0E0h+dwCreationDisposition], 3; dwCreationDisposition
0x18000993b  xor     r9d, r9d; lpSecurityAttributes
0x18000993e  mov     edx, 80000000h; dwDesiredAccess
0x180009943  lea     r8d, [r13+3]; dwShareMode
0x180009947  mov     rcx, [rbp+57h+pwzURI]; lpFileName
0x18000994b  call    cs:__imp_CreateFileW
0x180009951  mov     rsi, rax
0x180009954  cmp     rax, 0FFFFFFFFFFFFFFFFh
0x180009958  jz      short loc_180009992
0x18000995a  mov     r9, r12; lpLastWriteTime
0x18000995d  xor     r8d, r8d; lpLastAccessTime
0x180009960  xor     edx, edx; lpCreationTime
0x180009962  mov     rcx, rax; hFile
0x180009965  call    cs:__imp_GetFileTime
0x18000996b  test    eax, eax
0x18000996d  jnz     short loc_180009984
0x18000996f  call    cs:__imp_GetLastError
0x180009975  mov     ebx, eax
0x180009977  test    eax, eax
0x180009979  jle     short loc_180009984
0x18000997b  movzx   ebx, ax
0x18000997e  or      ebx, 80070000h
0x180009984  mov     rcx, rsi; hObject
0x180009987  call    cs:__imp_CloseHandle
0x18000998d  jmp     loc_180009BB2
0x180009992  call    cs:__imp_GetLastError
0x180009998  mov     ebx, eax
0x18000999a  test    eax, eax
0x18000999c  jle     loc_180009BB2
0x1800099a2  movzx   ebx, ax
0x1800099a5  or      ebx, 80070000h
0x1800099ab  jmp     loc_180009BB2
0x1800099b0  mov     ebx, 80004005h
0x1800099b5  jmp     loc_180009BB2
0x1800099ba  xorps   xmm0, xmm0
0x1800099bd  movups  [rbp+57h+Buffer], xmm0
0x1800099c1  mov     [rsp+0E0h+dwCreationDisposition], r13d; dwFlags
0x1800099c6  xor     r9d, r9d; lpszProxyBypass
0x1800099c9  xor     r8d, r8d; lpszProxy
0x1800099cc  xor     edx, edx; dwAccessType
0x1800099ce  lea     rcx, szAgent; "FavoritesEnterpriseClient"
0x1800099d5  call    cs:__imp_InternetOpenW
0x1800099db  mov     r15, rax
0x1800099de  mov     edi, 80070000h
0x1800099e3  test    rax, rax
0x1800099e6  jnz     short loc_180009A01
0x1800099e8  call    cs:__imp_GetLastError
0x1800099ee  mov     ebx, eax
0x1800099f0  test    eax, eax
0x1800099f2  jle     short loc_1800099F9
0x1800099f4  movzx   ebx, ax
0x1800099f7  or      ebx, edi
0x1800099f9  test    ebx, ebx
0x1800099fb  js      loc_180009BB2
0x180009a01  cmp     [rbp+57h+var_A0], 0Bh
0x180009a05  mov     esi, 1BBh
0x180009a0a  jz      short loc_180009A11
0x180009a0c  mov     esi, 50h ; 'P'
0x180009a11  mov     [rbp+57h+lpszServerName], r13
0x180009a15  mov     rcx, [rbp+57h+ppURI]
0x180009a19  mov     rax, [rcx]
0x180009a1c  lea     rdx, [rbp+57h+lpszServerName]
0x180009a20  mov     rax, [rax+68h]
0x180009a24  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a29  mov     ebx, eax
0x180009a2b  test    eax, eax
0x180009a2d  js      loc_180009B78
0x180009a33  mov     [rsp+0E0h+dwContext], r13; dwContext
0x180009a38  mov     dword ptr [rsp+0E0h+hTemplateFile], r13d; dwFlags
0x180009a3d  mov     [rsp+0E0h+dwFlagsAndAttributes], 3; dwService
0x180009a45  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpszPassword
0x180009a4a  xor     r9d, r9d; lpszUserName
0x180009a4d  movzx   r8d, si; nServerPort
0x180009a51  mov     rdx, [rbp+57h+lpszServerName]; lpszServerName
0x180009a55  mov     rcx, r15; hInternet
0x180009a58  call    cs:__imp_InternetConnectW
0x180009a5e  mov     r14, rax
0x180009a61  test    rax, rax
0x180009a64  jnz     short loc_180009A7F
0x180009a66  call    cs:__imp_GetLastError
0x180009a6c  mov     ebx, eax
0x180009a6e  test    eax, eax
0x180009a70  jle     short loc_180009A77
0x180009a72  movzx   ebx, ax
0x180009a75  or      ebx, edi
0x180009a77  test    ebx, ebx
0x180009a79  js      loc_180009B78
0x180009a7f  mov     [rbp+57h+lpszObjectName], r13
0x180009a83  mov     rcx, [rbp+57h+ppURI]
0x180009a87  mov     rax, [rcx]
0x180009a8a  lea     rdx, [rbp+57h+lpszObjectName]
0x180009a8e  mov     rax, [rax+78h]
0x180009a92  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180009a97  mov     ebx, eax
0x180009a99  test    eax, eax
0x180009a9b  js      loc_180009B64
0x180009aa1  lea     rax, aText; "text/*"
0x180009aa8  mov     [rbp+57h+lpszAcceptTypes], rax
0x180009aac  mov     [rbp+57h+var_68], r13
0x180009ab0  mov     eax, r13d
0x180009ab3  mov     ecx, 800000h
0x180009ab8  cmp     [rbp+57h+var_A0], 0Bh
0x180009abc  cmovz   eax, ecx
0x180009abf  mov     [rsp+0E0h+dwContext], r13; dwContext
0x180009ac4  mov     dword ptr [rsp+0E0h+hTemplateFile], eax; dwFlags
0x180009ac8  lea     rax, [rbp+57h+lpszAcceptTypes]
0x180009acc  mov     qword ptr [rsp+0E0h+dwFlagsAndAttributes], rax; lplpszAcceptTypes
0x180009ad1  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpszReferrer
0x180009ad6  xor     r9d, r9d; lpszVersion
0x180009ad9  mov     r8, [rbp+57h+lpszObjectName]; lpszObjectName
0x180009add  lea     rdx, szVerb; "HEAD"
0x180009ae4  mov     rcx, r14; hConnect
0x180009ae7  call    cs:__imp_HttpOpenRequestW
0x180009aed  mov     rsi, rax
0x180009af0  test    rax, rax
0x180009af3  jnz     short loc_180009B0A
0x180009af5  call    cs:__imp_GetLastError
0x180009afb  mov     ebx, eax
0x180009afd  test    eax, eax
0x180009aff  jle     short loc_180009B06
0x180009b01  movzx   ebx, ax
0x180009b04  or      ebx, edi
0x180009b06  test    ebx, ebx
0x180009b08  js      short loc_180009B64
0x180009b0a  mov     [rsp+0E0h+dwCreationDisposition], r13d; dwOptionalLength
0x180009b0f  xor     r9d, r9d; lpOptional
0x180009b12  xor     r8d, r8d; dwHeadersLength
0x180009b15  xor     edx, edx; lpszHeaders
0x180009b17  mov     rcx, rsi; hRequest
0x180009b1a  call    cs:__imp_HttpSendRequestW
0x180009b20  test    eax, eax
0x180009b22  jz      short loc_180009B4A
0x180009b24  mov     [rbp+57h+dwBufferLength], 10h
0x180009b2b  mov     qword ptr [rsp+0E0h+dwCreationDisposition], r13; lpdwIndex
0x180009b30  lea     r9, [rbp+57h+dwBufferLength]; lpdwBufferLength
0x180009b34  lea     r8, [rbp+57h+Buffer]; lpBuffer
0x180009b38  mov     edx, 4000000Bh; dwInfoLevel
0x180009b3d  mov     rcx, rsi; hRequest
0x180009b40  call    cs:__imp_HttpQueryInfoW
0x180009b46  test    eax, eax
0x180009b48  jnz     short loc_180009B5B
0x180009b4a  call    cs:__imp_GetLastError
0x180009b50  test    eax, eax
0x180009b52  mov     ebx, eax
0x180009b54  jle     short loc_180009B5B
0x180009b56  movzx   ebx, ax
0x180009b59  or      ebx, edi
0x180009b5b  mov     rcx, rsi; hInternet
0x180009b5e  call    cs:__imp_InternetCloseHandle
0x180009b64  mov     rcx, r14; hInternet
0x180009b67  call    cs:__imp_InternetCloseHandle
0x180009b6d  nop
0x180009b6e  mov     rcx, [rbp+57h+lpszObjectName]; bstrString
0x180009b72  call    cs:__imp_SysFreeString
0x180009b78  mov     rcx, r15; hInternet
0x180009b7b  call    cs:__imp_InternetCloseHandle
0x180009b81  nop
0x180009b82  mov     rcx, [rbp+57h+lpszServerName]; bstrString
0x180009b86  call    cs:__imp_SysFreeString
0x180009b8c  test    ebx, ebx
0x180009b8e  js      short loc_180009BB2
0x180009b90  mov     rdx, r12; lpFileTime
0x180009b93  lea     rcx, [rbp+57h+Buffer]; lpSystemTime
0x180009b97  call    cs:__imp_SystemTimeToFileTime
0x180009b9d  test    eax, eax
0x180009b9f  jnz     short loc_180009BB2
0x180009ba1  call    cs:__imp_GetLastError
0x180009ba7  mov     ebx, eax
0x180009ba9  test    eax, eax
0x180009bab  jle     short loc_180009BB2
0x180009bad  movzx   ebx, ax
0x180009bb0  or      ebx, edi
0x180009bb2  lea     rcx, [rbp+57h+ppURI]
0x180009bb6  call    ??1?$CComPtrBase@UIExtractIconW@@@ATL@@QEAA@XZ; ATL::CComPtrBase<IExtractIconW>::~CComPtrBase<IExtractIconW>(void)
0x180009bbb  nop
0x180009bbc  lea     rcx, [rbp+57h+pwzURI]
0x180009bc0  call    ??1?$CCoTaskMemPtr@G@@QEAA@XZ; CCoTaskMemPtr<ushort>::~CCoTaskMemPtr<ushort>(void)
0x180009bc5  mov     eax, ebx
0x180009bc7  mov     rcx, [rbp+57h+var_50]
0x180009bcb  xor     rcx, rsp; StackCookie
0x180009bce  call    __security_check_cookie
0x180009bd3  add     rsp, 0A8h
0x180009bda  pop     r15
0x180009bdc  pop     r14
0x180009bde  pop     r13
0x180009be0  pop     r12
0x180009be2  pop     rdi
0x180009be3  pop     rsi
0x180009be4  pop     rbx
0x180009be5  pop     rbp
0x180009be6  retn
```
