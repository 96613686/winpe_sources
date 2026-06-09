# CloudFilePolicy::CleanupItem(void *,TraceLoggingActivity<&_tlgProvider_t const * const StorageServiceProvider,70368744177664,5,_TlgReflectorTag_Param0IsHProvider> *)

- ea: `0x18002ede0`
- end: `0x18002f182`
- name: `?CleanupItem@CloudFilePolicy@@UEAAJPEAXPEAV?$TraceLoggingActivity@$1?StorageServiceProvider@@3QEBU_tlgProvider_t@@EB$0EAAAAAAAAAAA@$04U_TlgReflectorTag_Param0IsHProvider@@@@@Z`
- size: `930`
- prototype: `__int64 __fastcall(__int64, void *, __int64)`
- caller_count: `0`
- callee_count: `10`
- tags: `file_ops, authz_impersonation, registry_config, loader_planting, service_task, broker_com_uri`

## callees

- `0x180001148`
- `0x18000318c`
- `0x18000d030`
- `0x18000ddb0`
- `0x180012734`
- `0x180019d4c`
- `0x18001c130`
- `0x18001dcf4`
- `0x18001fcac`
- `0x18002ede0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002eea0`
- `api-ms-win-core-synch-l1-1-0!ResetEvent` at `0x18002eea0`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ee87`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002ee87`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f029`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002f029`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002f01f`
- `api-ms-win-core-io-l1-1-0!GetOverlappedResult` at `0x18002f01f`
- `ntdll!RtlInitializeCorrelationVector` at `0x18002ef5d`
- `ntdll!RtlInitializeCorrelationVector` at `0x18002ef5d`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18002f049`
- `api-ms-win-core-shlwapi-legacy-l1-1-0!PathFindExtensionW` at `0x18002f049`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002eef5`
- `api-ms-win-core-file-l1-1-0!CreateFileW` at `0x18002eef5`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002effb`
- `api-ms-win-core-synch-l1-2-1!WaitForMultipleObjects` at `0x18002effb`
- `RPCRT4!RpcRevertToSelf` at `0x18002ee67`
- `RPCRT4!RpcRevertToSelf` at `0x18002ef1d`
- `RPCRT4!RpcRevertToSelf` at `0x18002f12b`
- `RPCRT4!RpcRevertToSelf` at `0x18002ee67`
- `RPCRT4!RpcRevertToSelf` at `0x18002ef1d`
- `RPCRT4!RpcRevertToSelf` at `0x18002f12b`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002ef4a`
- `api-ms-win-core-com-l1-1-0!CoCreateGuid` at `0x18002ef4a`
- `cldapi!CfDehydratePlaceholderEx` at `0x18002efa7`
- `cldapi!CfDehydratePlaceholderEx` at `0x18002efa7`
- `cldapi!CfSetCorrelationVector` at `0x18002ef6c`
- `cldapi!CfSetCorrelationVector` at `0x18002ef6c`

## string_xrefs

- `0x18002ee48`: `onecore\drivers\storage\storsvc\service\storagepolicy.cpp`

## pseudocode

```c
// Hidden C++ exception states: #wind=18
__int64 __fastcall CloudFilePolicy::CleanupItem(__int64 a1, void *a2, __int64 a3)
{
  DWORD v5; // r15d
  unsigned int v6; // edi
  char v7; // al
  struct _SECURITY_ATTRIBUTES *EventW; // rax
  bool v9; // si
  const WCHAR *v10; // rax
  HANDLE FileW; // rax
  char v12; // al
  unsigned int v13; // eax
  DWORD v14; // eax
  signed int LastError; // eax
  const WCHAR *v16; // rax
  const WCHAR *v17; // r8
  int v18; // r9d
  const WCHAR *v19; // rax
  char v20; // al
  int dwCreationDisposition; // [rsp+20h] [rbp-E0h]
  _BYTE v23[8]; // [rsp+60h] [rbp-A0h] BYREF
  HANDLE hFile; // [rsp+68h] [rbp-98h] BYREF
  DWORD NumberOfBytesTransferred; // [rsp+70h] [rbp-90h] BYREF
  int v26; // [rsp+74h] [rbp-8Ch] BYREF
  DWORD v27; // [rsp+78h] [rbp-88h] BYREF
  unsigned int v28; // [rsp+7Ch] [rbp-84h] BYREF
  HANDLE Handles[2]; // [rsp+80h] [rbp-80h] BYREF
  __int64 v30; // [rsp+90h] [rbp-70h]
  __int64 v31; // [rsp+98h] [rbp-68h] BYREF
  const WCHAR *v32; // [rsp+A0h] [rbp-60h] BYREF
  __int64 v33; // [rsp+A8h] [rbp-58h] BYREF
  GUID pguid; // [rsp+B0h] [rbp-50h] BYREF
  char v35; // [rsp+C0h] [rbp-40h] BYREF
  char v36; // [rsp+C1h] [rbp-3Fh] BYREF
  wil::details::in1diag3 *retaddr; // [rsp+198h] [rbp+98h]

  v30 = a3;
  v5 = 0;
  NumberOfBytesTransferred = 0;
  hFile = 0;
  AutoRpcImpersonateClient(v23);
  if ( !std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 8) )
  {
    v6 = -2147024809;
    wil::details::in1diag3::Return_Hr(
      retaddr,
      (void *)0x38B,
      (unsigned int)"onecore\\drivers\\storage\\storsvc\\service\\storagepolicy.cpp",
      (const char *)0x80070057LL,
      dwCreationDisposition);
    v7 = v23[0];
    v23[0] = 0;
    if ( v7 )
      RpcRevertToSelf();
    goto LABEL_27;
  }
  if ( CloudFilePolicy::HEvent )
  {
    v9 = 1;
    ResetEvent(CloudFilePolicy::HEvent);
    EventW = CloudFilePolicy::HEvent;
  }
  else
  {
    EventW = (struct _SECURITY_ATTRIBUTES *)CreateEventW(0, 0, 0, 0);
    CloudFilePolicy::HEvent = EventW;
    v9 = EventW != 0;
  }
  CloudFilePolicy::Overlapped.Internal = 0;
  *(_OWORD *)&CloudFilePolicy::Overlapped.InternalHigh = 0;
  CloudFilePolicy::Overlapped.hEvent = EventW;
  v10 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 8);
  FileW = CreateFileW(v10, 0x80u, 1u, 0, 3u, (unsigned __int8)v9 << 30, 0);
  wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::reset(
    &hFile,
    FileW);
  if ( hFile == (HANDLE)-1LL )
  {
    v12 = v23[0];
    v23[0] = 0;
    if ( v12 )
      RpcRevertToSelf();
    v6 = -2147024809;
    goto LABEL_27;
  }
  memset_0(&v35, 0, 0x82u);
  pguid = 0;
  CoCreateGuid(&pguid);
  RtlInitializeCorrelationVector(&v35, 2, &pguid);
  CfSetCorrelationVector(hFile, &v35);
  v13 = CfDehydratePlaceholderEx(hFile, 0, 0x7FFFFFFFFFFFFFFFLL, 0);
  v6 = v13;
  if ( v9 && v13 == -2147023899 )
  {
    Handles[0] = CloudFilePolicy::HEvent;
    Handles[1] = a2;
    v5 = 10000;
    if ( (unsigned int)(*(_QWORD *)(a1 + 48) / 0x1388uLL) > 0x2710 )
      v5 = *(_QWORD *)(a1 + 48) / 0x1388uLL;
    v14 = WaitForMultipleObjects(2u, Handles, 0, v5);
    if ( v14 )
    {
      if ( v14 == 1 )
      {
        v6 = -2147023673;
      }
      else
      {
        if ( v14 != 258 )
        {
LABEL_18:
          LastError = GetLastError();
          v6 = LastError;
          if ( LastError > 0 )
            v6 = (unsigned __int16)LastError | 0x80070000;
          goto LABEL_20;
        }
        v6 = -2147023436;
      }
    }
    else
    {
      v6 = 0;
      if ( !GetOverlappedResult(hFile, &CloudFilePolicy::Overlapped, &NumberOfBytesTransferred, 0) )
        goto LABEL_18;
    }
  }
LABEL_20:
  v16 = (const WCHAR *)std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 8);
  PathFindExtensionW(v16);
  if ( (unsigned int)dword_1800BF000 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800BF000, 0x400000000000LL) )
  {
    v31 = std::_String_val<std::_Simple_types<unsigned short>>::_Myptr(a1 + 8);
    v19 = &word_180092AF0;
    if ( v17 )
      v19 = v17;
    v32 = v19;
    v26 = CloudFilePolicy::DehydrationReason;
    v33 = *(_QWORD *)(a1 + 48);
    v27 = v5;
    v28 = v6;
    Handles[0] = &v36;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<unsigned short>,_tlgWrapSz<unsigned short>>(
      (unsigned int)&dword_1800BF000,
      (unsigned int)&unk_1800A7960,
      v30 + 8,
      v18,
      (__int64)Handles,
      (__int64)&v28,
      (__int64)&v27,
      (__int64)&v33,
      (__int64)&v26,
      (__int64)&v32,
      (__int64)&v31);
  }
  v20 = v23[0];
  v23[0] = 0;
  if ( v20 )
    RpcRevertToSelf();
LABEL_27:
  wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&int CloseHandle(void *)>>(&hFile);
  return v6;
}

```

## disassembly

```asm
0x18002ede0  push    rbp
0x18002ede2  push    rsi
0x18002ede3  push    rdi
0x18002ede4  push    r12
0x18002ede6  push    r13
0x18002ede8  push    r14
0x18002edea  push    r15
0x18002edec  lea     rbp, [rsp-60h]
0x18002edf1  sub     rsp, 160h
0x18002edf8  mov     rax, cs:__security_cookie
0x18002edff  xor     rax, rsp
0x18002ee02  mov     [rbp+90h+var_40], rax
0x18002ee06  mov     [rbp+90h+var_100], r8
0x18002ee0a  mov     r12, rdx
0x18002ee0d  mov     r13, rcx
0x18002ee10  xor     r15d, r15d
0x18002ee13  mov     [rsp+190h+NumberOfBytesTransferred], r15d
0x18002ee18  mov     [rsp+190h+hFile], r15
0x18002ee1d  lea     rcx, [rsp+190h+var_130]
0x18002ee22  call    ?AutoRpcImpersonateClient@@YA?AV?$unique_call@P6AJXZ$1?RpcRevertToSelf@@YAJXZ$00@wil@@XZ; AutoRpcImpersonateClient(void)
0x18002ee27  nop
0x18002ee28  lea     r14, [r13+8]
0x18002ee2c  mov     rcx, r14
0x18002ee2f  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002ee34  test    rax, rax
0x18002ee37  jnz     short loc_18002EE73
0x18002ee39  mov     rcx, [rbp+98h]; this
0x18002ee40  mov     edi, 80070057h
0x18002ee45  mov     r9d, edi; char *
0x18002ee48  lea     r8, aOnecoreDrivers_25; "onecore\\drivers\\storage\\storsvc\\ser"...
0x18002ee4f  mov     edx, 38Bh; void *
0x18002ee54  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x18002ee59  nop
0x18002ee5a  mov     al, [rsp+190h+var_130]
0x18002ee5e  mov     [rsp+190h+var_130], r15b
0x18002ee63  test    al, al
0x18002ee65  jz      short loc_18002EE6E
0x18002ee67  call    cs:__imp_RpcRevertToSelf
0x18002ee6d  nop
0x18002ee6e  jmp     loc_18002F132
0x18002ee73  mov     rcx, cs:?HEvent@CloudFilePolicy@@2PEAXEA; hEvent
0x18002ee7a  test    rcx, rcx
0x18002ee7d  jnz     short loc_18002EE9D
0x18002ee7f  xor     r9d, r9d; lpName
0x18002ee82  xor     r8d, r8d; bInitialState
0x18002ee85  xor     edx, edx; bManualReset
0x18002ee87  call    cs:__imp_CreateEventW
0x18002ee8d  mov     cs:?HEvent@CloudFilePolicy@@2PEAXEA, rax; void * CloudFilePolicy::HEvent
0x18002ee94  test    rax, rax
0x18002ee97  setnz   sil
0x18002ee9b  jmp     short loc_18002EEAD
0x18002ee9d  mov     sil, 1
0x18002eea0  call    cs:__imp_ResetEvent
0x18002eea6  mov     rax, cs:?HEvent@CloudFilePolicy@@2PEAXEA; void * CloudFilePolicy::HEvent
0x18002eead  mov     cs:?Overlapped@CloudFilePolicy@@2U_OVERLAPPED@@A.Internal, r15; _OVERLAPPED CloudFilePolicy::Overlapped ...
0x18002eeb4  xorps   xmm0, xmm0
0x18002eeb7  movdqu  xmmword ptr cs:?Overlapped@CloudFilePolicy@@2U_OVERLAPPED@@A.InternalHigh, xmm0; _OVERLAPPED CloudFilePolicy::Overlapped ...
0x18002eebf  mov     cs:?Overlapped@CloudFilePolicy@@2U_OVERLAPPED@@A.hEvent, rax; _OVERLAPPED CloudFilePolicy::Overlapped ...
0x18002eec6  mov     rcx, r14
0x18002eec9  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002eece  movzx   ecx, sil
0x18002eed2  shl     ecx, 1Eh
0x18002eed5  mov     [rsp+190h+hTemplateFile], r15; hTemplateFile
0x18002eeda  mov     [rsp+190h+dwFlagsAndAttributes], ecx; dwFlagsAndAttributes
0x18002eede  mov     [rsp+190h+dwCreationDisposition], 3; dwCreationDisposition
0x18002eee6  xor     r9d, r9d; lpSecurityAttributes
0x18002eee9  mov     edx, 80h; dwDesiredAccess
0x18002eeee  lea     r8d, [r9+1]; dwShareMode
0x18002eef2  mov     rcx, rax; lpFileName
0x18002eef5  call    cs:__imp_CreateFileW
0x18002eefb  mov     rdx, rax
0x18002eefe  lea     rcx, [rsp+190h+hFile]
0x18002ef03  call    ?reset@?$unique_storage@U?$handle_null_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAAXPEAX@Z; wil::details::unique_storage<wil::details::handle_null_resource_policy<int (*)(void *),&CloseHandle(void *)>>::reset(void *)
0x18002ef08  cmp     [rsp+190h+hFile], 0FFFFFFFFFFFFFFFFh
0x18002ef0e  jnz     short loc_18002EF2E
0x18002ef10  mov     al, [rsp+190h+var_130]
0x18002ef14  mov     [rsp+190h+var_130], r15b
0x18002ef19  test    al, al
0x18002ef1b  jz      short loc_18002EF24
0x18002ef1d  call    cs:__imp_RpcRevertToSelf
0x18002ef23  nop
0x18002ef24  mov     edi, 80070057h
0x18002ef29  jmp     loc_18002F132
0x18002ef2e  xor     edx, edx; Val
0x18002ef30  mov     r8d, 82h; Size
0x18002ef36  lea     rcx, [rbp+90h+var_D0]; void *
0x18002ef3a  call    memset_0
0x18002ef3f  xorps   xmm0, xmm0
0x18002ef42  movups  xmmword ptr [rbp+90h+pguid.Data1], xmm0
0x18002ef46  lea     rcx, [rbp+90h+pguid]; pguid
0x18002ef4a  call    cs:__imp_CoCreateGuid
0x18002ef50  lea     r8, [rbp+90h+pguid]
0x18002ef54  mov     edx, 2
0x18002ef59  lea     rcx, [rbp+90h+var_D0]
0x18002ef5d  call    cs:__imp_RtlInitializeCorrelationVector
0x18002ef63  lea     rdx, [rbp+90h+var_D0]
0x18002ef67  mov     rcx, [rsp+190h+hFile]
0x18002ef6c  call    cs:__imp_CfSetCorrelationVector
0x18002ef72  mov     ecx, cs:?DehydrationReason@CloudFilePolicy@@2W4CF_DEHYDRATE_REASON@@A; CF_DEHYDRATE_REASON CloudFilePolicy::DehydrationReason
0x18002ef78  xor     edx, edx
0x18002ef7a  mov     r8, 7FFFFFFFFFFFFFFFh
0x18002ef84  mov     al, sil
0x18002ef87  lea     r9, ?Overlapped@CloudFilePolicy@@2U_OVERLAPPED@@A; _OVERLAPPED CloudFilePolicy::Overlapped
0x18002ef8e  neg     al
0x18002ef90  sbb     rax, rax
0x18002ef93  and     rax, r9
0x18002ef96  mov     qword ptr [rsp+190h+dwFlagsAndAttributes], rax
0x18002ef9b  mov     [rsp+190h+dwCreationDisposition], ecx
0x18002ef9f  xor     r9d, r9d
0x18002efa2  mov     rcx, [rsp+190h+hFile]
0x18002efa7  call    cs:__imp_CfDehydratePlaceholderEx
0x18002efad  mov     edi, eax
0x18002efaf  test    sil, sil
0x18002efb2  jz      loc_18002F03E
0x18002efb8  cmp     eax, 800703E5h
0x18002efbd  jnz     short loc_18002F03E
0x18002efbf  mov     rax, cs:?HEvent@CloudFilePolicy@@2PEAXEA; void * CloudFilePolicy::HEvent
0x18002efc6  mov     [rbp+90h+Handles], rax
0x18002efca  mov     [rbp+90h+var_108], r12
0x18002efce  mov     rax, 346DC5D63886594Bh
0x18002efd8  mul     qword ptr [r13+30h]
0x18002efdc  shr     rdx, 0Ah
0x18002efe0  mov     r15d, 2710h
0x18002efe6  cmp     edx, r15d
0x18002efe9  cmova   r15d, edx
0x18002efed  mov     r9d, r15d; dwMilliseconds
0x18002eff0  xor     r8d, r8d; bWaitAll
0x18002eff3  lea     rdx, [rbp+90h+Handles]; lpHandles
0x18002eff7  lea     ecx, [r8+2]; nCount
0x18002effb  call    cs:__imp_WaitForMultipleObjects
0x18002f001  test    eax, eax
0x18002f003  jnz     loc_18002F15D
0x18002f009  xor     edi, edi
0x18002f00b  xor     r9d, r9d; bWait
0x18002f00e  lea     r8, [rsp+190h+NumberOfBytesTransferred]; lpNumberOfBytesTransferred
0x18002f013  lea     rdx, ?Overlapped@CloudFilePolicy@@2U_OVERLAPPED@@A; lpOverlapped
0x18002f01a  mov     rcx, [rsp+190h+hFile]; hFile
0x18002f01f  call    cs:__imp_GetOverlappedResult
0x18002f025  test    eax, eax
0x18002f027  jnz     short loc_18002F03E
0x18002f029  call    cs:__imp_GetLastError
0x18002f02f  test    eax, eax
0x18002f031  mov     edi, eax
0x18002f033  jle     short loc_18002F03E
0x18002f035  movzx   edi, ax
0x18002f038  or      edi, 80070000h
0x18002f03e  mov     rcx, r14
0x18002f041  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f046  mov     rcx, rax; pszPath
0x18002f049  call    cs:__imp_PathFindExtensionW
0x18002f04f  mov     r8, rax
0x18002f052  mov     edx, cs:dword_1800BF000
0x18002f058  cmp     edx, 5
0x18002f05b  jbe     loc_18002F11E
0x18002f061  mov     rdx, 400000000000h
0x18002f06b  lea     rcx, dword_1800BF000
0x18002f072  call    _tlgKeywordOn
0x18002f077  test    al, al
0x18002f079  jz      loc_18002F11E
0x18002f07f  mov     rcx, r14
0x18002f082  call    ?_Myptr@?$_String_val@U?$_Simple_types@G@std@@@std@@QEBAPEBGXZ; std::_String_val<std::_Simple_types<ushort>>::_Myptr(void)
0x18002f087  mov     [rbp+90h+var_F8], rax
0x18002f08b  lea     rax, word_180092AF0
0x18002f092  test    r8, r8
0x18002f095  cmovnz  rax, r8
0x18002f099  mov     [rbp+90h+var_F0], rax
0x18002f09d  mov     eax, cs:?DehydrationReason@CloudFilePolicy@@2W4CF_DEHYDRATE_REASON@@A; CF_DEHYDRATE_REASON CloudFilePolicy::DehydrationReason
0x18002f0a3  mov     [rsp+190h+var_11C], eax
0x18002f0a7  mov     rax, [r13+30h]
0x18002f0ab  mov     [rbp+90h+var_E8], rax
0x18002f0af  mov     [rsp+190h+var_118], r15d
0x18002f0b4  mov     [rsp+190h+var_114], edi
0x18002f0b8  lea     rax, [rbp+90h+var_CF]
0x18002f0bc  mov     [rbp+90h+Handles], rax
0x18002f0c0  mov     r8, [rbp+90h+var_100]
0x18002f0c4  add     r8, 8
0x18002f0c8  lea     rax, [rbp+90h+var_F8]
0x18002f0cc  mov     [rsp+190h+var_140], rax
0x18002f0d1  lea     rax, [rbp+90h+var_F0]
0x18002f0d5  mov     [rsp+190h+var_148], rax
0x18002f0da  lea     rax, [rsp+190h+var_11C]
0x18002f0df  mov     [rsp+190h+var_150], rax
0x18002f0e4  lea     rax, [rbp+90h+var_E8]
0x18002f0e8  mov     [rsp+190h+var_158], rax
0x18002f0ed  lea     rax, [rsp+190h+var_118]
0x18002f0f2  mov     [rsp+190h+hTemplateFile], rax
0x18002f0f7  lea     rax, [rsp+190h+var_114]
0x18002f0fc  mov     qword ptr [rsp+190h+dwFlagsAndAttributes], rax
0x18002f101  lea     rax, [rbp+90h+Handles]
0x18002f105  mov     qword ptr [rsp+190h+dwCreationDisposition], rax
0x18002f10a  lea     rdx, unk_1800A7960
0x18002f111  lea     rcx, dword_1800BF000
0x18002f118  call    ??$Write@U?$_tlgWrapSz@D@@U?$_tlgWrapperByVal@$03@@U2@U?$_tlgWrapperByVal@$07@@U2@U?$_tlgWrapSz@G@@U4@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@AEBU?$_tlgWrapperByVal@$03@@4AEBU?$_tlgWrapperByVal@$07@@4AEBU?$_tlgWrapSz@G@@6@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapperByVal<4>,_tlgWrapperByVal<4>,_tlgWrapperByVal<8>,_tlgWrapperByVal<4>,_tlgWrapSz<ushort>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<8> const &,_tlgWrapperByVal<4> const &,_tlgWrapSz<ushort> const &,_tlgWrapSz<ushort> const &)
0x18002f11d  nop
0x18002f11e  mov     al, [rsp+190h+var_130]
0x18002f122  mov     [rsp+190h+var_130], 0
0x18002f127  test    al, al
0x18002f129  jz      short loc_18002F132
0x18002f12b  call    cs:__imp_RpcRevertToSelf
0x18002f131  nop
0x18002f132  lea     rcx, [rsp+190h+hFile]
0x18002f137  call    ??1?$unique_storage@U?$handle_invalid_resource_policy@P6AHPEAX@Z$1?CloseHandle@@YAH0@Z@details@wil@@@details@wil@@QEAA@XZ; wil::details::unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>::~unique_storage<wil::details::handle_invalid_resource_policy<int (*)(void *),&CloseHandle(void *)>>(void)
0x18002f13c  mov     eax, edi
0x18002f13e  mov     rcx, [rbp+90h+var_40]
0x18002f142  xor     rcx, rsp; StackCookie
0x18002f145  call    __security_check_cookie
0x18002f14a  add     rsp, 160h
0x18002f151  pop     r15
0x18002f153  pop     r14
0x18002f155  pop     r13
0x18002f157  pop     r12
0x18002f159  pop     rdi
0x18002f15a  pop     rsi
0x18002f15b  pop     rbp
0x18002f15c  retn
0x18002f15d  cmp     eax, 1
0x18002f160  jnz     short loc_18002F16C
0x18002f162  mov     edi, 800704C7h
0x18002f167  jmp     loc_18002F03E
0x18002f16c  cmp     eax, 102h
0x18002f171  jnz     loc_18002F029
0x18002f177  mov     edi, 800705B4h
0x18002f17c  jmp     loc_18002F03E
```
