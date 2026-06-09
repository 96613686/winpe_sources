# StorageService::CreateStorageCardDirectory(_STORAGE_DEVICE_TYPE,ulong,ushort const *,ulong,_SECURITY_ATTRIBUTES *,_ACL *,int)

- ea: `0x180020450`
- end: `0x1800206cd`
- name: `?CreateStorageCardDirectory@StorageService@@IEAAJW4_STORAGE_DEVICE_TYPE@@KPEBGKPEAU_SECURITY_ATTRIBUTES@@PEAU_ACL@@H@Z`
- size: `637`
- prototype: `__int64 __fastcall(StorageService *, int, unsigned int, __int64, int, struct _SECURITY_ATTRIBUTES *, struct _ACL *, int)`
- caller_count: `3`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, service_task, broker_com_uri`

## callers

- `0x180027858`
- `0x180027b2c`
- `0x18002a3f8`

## callees

- `0x180002184`
- `0x180002248`
- `0x18000d030`
- `0x180012c9c`
- `0x18001fc18`
- `0x180020450`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002052d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020562`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002052d`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180020562`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002050d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002059b`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002050d`
- `api-ms-win-core-file-l1-1-0!GetFileAttributesW` at `0x18002059b`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180020558`
- `api-ms-win-core-file-l1-1-0!CreateDirectoryW` at `0x180020558`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800205c3`
- `api-ms-win-core-file-l1-1-0!SetFileAttributesW` at `0x1800205c3`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180020523`
- `api-ms-win-core-file-l1-1-0!DeleteFileW` at `0x180020523`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800204d4`
- `api-ms-win-core-path-l1-1-0!PathCchAppend` at `0x1800204d4`
- `RPCRT4!RpcRevertToSelf` at `0x180020637`
- `RPCRT4!RpcRevertToSelf` at `0x180020637`
- `RPCRT4!RpcImpersonateClient` at `0x1800204f2`
- `RPCRT4!RpcImpersonateClient` at `0x1800204f2`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall StorageService::CreateStorageCardDirectory(
        StorageService *a1,
        int a2,
        unsigned int a3,
        __int64 a4,
        int a5,
        struct _SECURITY_ATTRIBUTES *a6,
        struct _ACL *a7,
        int a8)
{
  int v11; // ebx
  const WCHAR *v12; // r11
  int v13; // r14d
  DWORD FileAttributesW; // eax
  DWORD v15; // edi
  signed int LastError; // eax
  signed int v17; // edx
  int v18; // ecx
  int v19; // r8d
  int v20; // r9d
  int v21; // ecx
  int v22; // r8d
  int v23; // r9d
  signed int v25; // [rsp+50h] [rbp-B0h] BYREF
  int v26; // [rsp+54h] [rbp-ACh] BYREF
  int v27; // [rsp+58h] [rbp-A8h] BYREF
  LPSECURITY_ATTRIBUTES lpSecurityAttributes; // [rsp+60h] [rbp-A0h] BYREF
  WCHAR *v29; // [rsp+68h] [rbp-98h] BYREF
  WCHAR pszPath[264]; // [rsp+70h] [rbp-90h] BYREF

  lpSecurityAttributes = a6;
  v11 = StringCchCopyW(pszPath, 0x104u, (const wchar_t *)(*((_QWORD *)a1 + a2 + 5) + 4LL + 1112LL * a3));
  if ( v11 < 0 )
    return (unsigned int)v11;
  v11 = PathCchAppend(pszPath, 0x104u, v12);
  if ( v11 < 0 )
    return (unsigned int)v11;
  v13 = 0;
  if ( a8 )
  {
    v11 = RpcImpersonateClient(0);
    if ( v11 < 0 )
      return (unsigned int)v11;
    v13 = 1;
  }
  FileAttributesW = GetFileAttributesW(pszPath);
  v15 = FileAttributesW;
  if ( FileAttributesW != -1 && (FileAttributesW & 0x10) == 0 )
  {
    if ( !DeleteFileW(pszPath) )
    {
      LastError = GetLastError();
      v11 = LastError;
      if ( LastError > 0 )
        v11 = (unsigned __int16)LastError | 0x80070000;
      goto LABEL_22;
    }
    v15 = -1;
  }
  if ( CreateDirectoryW(pszPath, lpSecurityAttributes) )
  {
LABEL_17:
    if ( v15 != -1
      && (a5 | 0x10) != (v15 & 0xFFFFFFDF)
      && !SetFileAttributesW(pszPath, a5 | 0x10)
      && (unsigned int)dword_1800BF000 > 5 )
    {
      v27 = v11;
      v29 = pszPath;
      v26 = a5 | 0x10;
      v25 = a3;
      LODWORD(lpSecurityAttributes) = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
        v21,
        (unsigned int)byte_1800A7713,
        v22,
        v23,
        (__int64)&lpSecurityAttributes,
        (__int64)&v25,
        (__int64)&v29,
        (__int64)&v26,
        (__int64)&v27);
    }
    goto LABEL_22;
  }
  v17 = GetLastError();
  if ( v17 != 183 )
  {
    if ( (unsigned int)dword_1800BF000 > 5 )
    {
      if ( v17 > 0 )
        v17 = (unsigned __int16)v17 | 0x80070000;
      v25 = v17;
      lpSecurityAttributes = (LPSECURITY_ATTRIBUTES)pszPath;
      v26 = a3;
      v27 = a2;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapperByVal<4>>(
        v18,
        (unsigned int)word_1800A7092,
        v19,
        v20,
        (__int64)&v27,
        (__int64)&v26,
        (__int64)&lpSecurityAttributes,
        (__int64)&v25);
    }
    v11 = 0;
    goto LABEL_22;
  }
  if ( !a7 || (v11 = StorageService::ApplyFolderDacl(a1, pszPath, a7), v11 >= 0) )
  {
    v11 = 0;
    v15 = GetFileAttributesW(pszPath);
    goto LABEL_17;
  }
LABEL_22:
  if ( v13 )
    RpcRevertToSelf();
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x180020450  push    rbp
0x180020452  push    rbx
0x180020453  push    rsi
0x180020454  push    rdi
0x180020455  push    r12
0x180020457  push    r13
0x180020459  push    r14
0x18002045b  push    r15
0x18002045d  lea     rbp, [rsp-198h]
0x180020465  sub     rsp, 298h
0x18002046c  mov     rax, cs:__security_cookie
0x180020473  xor     rax, rsp
0x180020476  mov     [rbp+1D0h+var_50], rax
0x18002047d  mov     rax, [rbp+1D0h+arg_28]
0x180020484  mov     r13, rcx
0x180020487  mov     rsi, [rbp+1D0h+arg_30]
0x18002048e  mov     edi, 104h
0x180020493  mov     r12d, r8d
0x180020496  mov     r11, r9
0x180020499  movsxd  r15, edx
0x18002049c  mov     edx, edi; unsigned __int64
0x18002049e  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x1800204a3  imul    r8, r12, 458h
0x1800204aa  mov     rax, [rcx+r15*8+28h]
0x1800204af  lea     rcx, [rsp+2D0h+pszPath]; wchar_t *
0x1800204b4  add     rax, 4
0x1800204b8  add     r8, rax; wchar_t *
0x1800204bb  call    ?StringCchCopyW@@YAJPEA_W_KPEB_W@Z; StringCchCopyW(wchar_t *,unsigned __int64,wchar_t const *)
0x1800204c0  mov     ebx, eax
0x1800204c2  test    eax, eax
0x1800204c4  js      loc_18002063D
0x1800204ca  mov     r8, r11; pszMore
0x1800204cd  lea     rcx, [rsp+2D0h+pszPath]; pszPath
0x1800204d2  mov     edx, edi; cchPath
0x1800204d4  call    cs:__imp_PathCchAppend
0x1800204da  mov     ebx, eax
0x1800204dc  test    eax, eax
0x1800204de  js      loc_18002063D
0x1800204e4  xor     r14d, r14d
0x1800204e7  cmp     [rbp+1D0h+arg_38], r14d
0x1800204ee  jz      short loc_180020508
0x1800204f0  xor     ecx, ecx; BindingHandle
0x1800204f2  call    cs:__imp_RpcImpersonateClient
0x1800204f8  mov     ebx, eax
0x1800204fa  test    eax, eax
0x1800204fc  js      loc_18002063D
0x180020502  mov     r14d, 1
0x180020508  lea     rcx, [rsp+2D0h+pszPath]; lpFileName
0x18002050d  call    cs:__imp_GetFileAttributesW
0x180020513  mov     edi, eax
0x180020515  cmp     eax, 0FFFFFFFFh
0x180020518  jz      short loc_18002054E
0x18002051a  test    al, 10h
0x18002051c  jnz     short loc_18002054E
0x18002051e  lea     rcx, [rsp+2D0h+pszPath]; lpFileName
0x180020523  call    cs:__imp_DeleteFileW
0x180020529  test    eax, eax
0x18002052b  jnz     short loc_18002054B
0x18002052d  call    cs:__imp_GetLastError
0x180020533  mov     ebx, eax
0x180020535  test    eax, eax
0x180020537  jle     loc_180020632
0x18002053d  movzx   ebx, ax
0x180020540  or      ebx, 80070000h
0x180020546  jmp     loc_180020632
0x18002054b  or      edi, 0FFFFFFFFh
0x18002054e  mov     rdx, [rsp+2D0h+lpSecurityAttributes]; lpSecurityAttributes
0x180020553  lea     rcx, [rsp+2D0h+pszPath]; lpPathName
0x180020558  call    cs:__imp_CreateDirectoryW
0x18002055e  test    eax, eax
0x180020560  jnz     short loc_1800205A3
0x180020562  call    cs:__imp_GetLastError
0x180020568  mov     edx, eax
0x18002056a  cmp     eax, 0B7h
0x18002056f  jnz     loc_180020662
0x180020575  test    rsi, rsi
0x180020578  jz      short loc_180020594
0x18002057a  mov     r8, rsi; struct _ACL *
0x18002057d  lea     rdx, [rsp+2D0h+pszPath]; unsigned __int16 *
0x180020582  mov     rcx, r13; this
0x180020585  call    ?ApplyFolderDacl@StorageService@@AEAAJPEAGPEAU_ACL@@@Z; StorageService::ApplyFolderDacl(ushort *,_ACL *)
0x18002058a  mov     ebx, eax
0x18002058c  test    eax, eax
0x18002058e  js      loc_180020632
0x180020594  xor     ebx, ebx
0x180020596  lea     rcx, [rsp+2D0h+pszPath]; lpFileName
0x18002059b  call    cs:__imp_GetFileAttributesW
0x1800205a1  mov     edi, eax
0x1800205a3  cmp     edi, 0FFFFFFFFh
0x1800205a6  jz      loc_180020632
0x1800205ac  mov     esi, [rbp+1D0h+arg_20]
0x1800205b2  and     edi, 0FFFFFFDFh
0x1800205b5  or      esi, 10h
0x1800205b8  cmp     esi, edi
0x1800205ba  jz      short loc_180020632
0x1800205bc  mov     edx, esi; dwFileAttributes
0x1800205be  lea     rcx, [rsp+2D0h+pszPath]; lpFileName
0x1800205c3  call    cs:__imp_SetFileAttributesW
0x1800205c9  test    eax, eax
0x1800205cb  jnz     short loc_180020632
0x1800205cd  mov     eax, cs:dword_1800BF000
0x1800205d3  cmp     eax, 5
0x1800205d6  jbe     short loc_180020632
0x1800205d8  lea     rax, [rsp+2D0h+pszPath]
0x1800205dd  mov     [rsp+2D0h+var_278], ebx
0x1800205e1  mov     [rsp+2D0h+var_268], rax
0x1800205e6  lea     rdx, byte_1800A7713
0x1800205ed  lea     rax, [rsp+2D0h+var_278]
0x1800205f2  mov     [rsp+2D0h+var_27C], esi
0x1800205f6  mov     [rsp+2D0h+var_290], rax
0x1800205fb  lea     rax, [rsp+2D0h+var_27C]
0x180020600  mov     [rsp+2D0h+var_298], rax
0x180020605  lea     rax, [rsp+2D0h+var_268]
0x18002060a  mov     [rsp+2D0h+var_2A0], rax
0x18002060f  lea     rax, [rsp+2D0h+var_280]
0x180020614  mov     [rsp+2D0h+var_2A8], rax
0x180020619  lea     rax, [rsp+2D0h+lpSecurityAttributes]
0x18002061e  mov     [rsp+2D0h+var_2B0], rax
0x180020623  mov     [rsp+2D0h+var_280], r12d
0x180020628  mov     dword ptr [rsp+2D0h+lpSecurityAttributes], r15d
0x18002062d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U1@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@33@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x180020632  test    r14d, r14d
0x180020635  jz      short loc_18002063D
0x180020637  call    cs:__imp_RpcRevertToSelf
0x18002063d  mov     eax, ebx
0x18002063f  mov     rcx, [rbp+1D0h+var_50]
0x180020646  xor     rcx, rsp; StackCookie
0x180020649  call    __security_check_cookie
0x18002064e  add     rsp, 298h
0x180020655  pop     r15
0x180020657  pop     r14
0x180020659  pop     r13
0x18002065b  pop     r12
0x18002065d  pop     rdi
0x18002065e  pop     rsi
0x18002065f  pop     rbx
0x180020660  pop     rbp
0x180020661  retn
0x180020662  mov     eax, cs:dword_1800BF000
0x180020668  cmp     eax, 5
0x18002066b  jbe     short loc_1800206C6
0x18002066d  test    edx, edx
0x18002066f  jle     short loc_18002067A
0x180020671  movzx   edx, dx
0x180020674  or      edx, 80070000h
0x18002067a  lea     rax, [rsp+2D0h+pszPath]
0x18002067f  mov     [rsp+2D0h+var_280], edx
0x180020683  mov     [rsp+2D0h+lpSecurityAttributes], rax
0x180020688  lea     rdx, word_1800A7092
0x18002068f  lea     rax, [rsp+2D0h+var_280]
0x180020694  mov     [rsp+2D0h+var_27C], r12d
0x180020699  mov     [rsp+2D0h+var_298], rax
0x18002069e  lea     rax, [rsp+2D0h+lpSecurityAttributes]
0x1800206a3  mov     [rsp+2D0h+var_2A0], rax
0x1800206a8  lea     rax, [rsp+2D0h+var_27C]
0x1800206ad  mov     [rsp+2D0h+var_2A8], rax
0x1800206b2  lea     rax, [rsp+2D0h+var_278]
0x1800206b7  mov     [rsp+2D0h+var_2B0], rax
0x1800206bc  mov     [rsp+2D0h+var_278], r15d
0x1800206c1  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@U?$_tlgWrapSz@G@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3AEBU?$_tlgWrapSz@G@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapperByVal<4> const &)
0x1800206c6  xor     ebx, ebx
0x1800206c8  jmp     loc_180020632
```
