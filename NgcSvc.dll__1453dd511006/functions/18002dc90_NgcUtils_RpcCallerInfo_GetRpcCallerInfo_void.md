# NgcUtils::RpcCallerInfo::GetRpcCallerInfo(void)

- ea: `0x18002dc90`
- end: `0x18002e0ca`
- name: `?GetRpcCallerInfo@RpcCallerInfo@NgcUtils@@AEAAJXZ`
- size: `1082`
- prototype: `__int64 __fastcall(NgcUtils::RpcCallerInfo *__hidden this)`
- caller_count: `2`
- callee_count: `10`
- tags: `authz_impersonation, broker_com_uri`

## callers

- `0x18002dc0c`
- `0x18003dad0`

## callees

- `0x180028d18`
- `0x18002dc90`
- `0x1800334f0`
- `0x180038764`
- `0x180045500`
- `0x180045d60`
- `0x18005cee0`
- `0x18005dd80`
- `0x18007612c`
- `0x18008d1ec`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dcea`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dd1c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002dee9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002df7c`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002dda9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002de86`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002df76`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002dda9`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002de86`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x18002df76`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002debe`
- `api-ms-win-security-base-l1-1-0!GetTokenInformation` at `0x18002debe`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002dcdc`
- `RPCRT4!I_RpcBindingInqLocalClientPID` at `0x18002dcdc`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002ddb3`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002dfb3`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002ddb3`
- `RPCRT4!RpcRevertToSelfEx` at `0x18002dfb3`
- `RPCRT4!RpcImpersonateClient` at `0x18002dcc4`
- `RPCRT4!RpcImpersonateClient` at `0x18002dcc4`

## pseudocode

```c
// Hidden C++ exception states: #wind=1
__int64 __fastcall NgcUtils::RpcCallerInfo::GetRpcCallerInfo(NgcUtils::RpcCallerInfo *this)
{
  void *v2; // rbx
  int v3; // edi
  signed int LastError; // eax
  int UserSidFromToken; // edi
  RPC_STATUS v6; // ebx
  signed int v8; // eax
  bool *v9; // rdx
  int IsAppContainer; // ebx
  _BYTE v11[4]; // [rsp+30h] [rbp-49h] BYREF
  DWORD v12; // [rsp+34h] [rbp-45h] BYREF
  void *v13; // [rsp+38h] [rbp-41h] BYREF
  DWORD ReturnLength; // [rsp+40h] [rbp-39h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+68h] [rbp-11h] BYREF
  __int16 *v17; // [rsp+78h] [rbp-1h]
  int v18; // [rsp+80h] [rbp+7h]
  int v19; // [rsp+84h] [rbp+Bh]
  DWORD *v20; // [rsp+88h] [rbp+Fh]
  __int64 v21; // [rsp+90h] [rbp+17h]

  v2 = (void *)*((_QWORD *)this + 6);
  v13 = v2;
  v3 = RpcImpersonateClient(v2);
  if ( v3 )
  {
    if ( (unsigned int)dword_180122070 > 2 && (unsigned __int8)tlgKeywordOn(&dword_180122070, 0) )
    {
      v12 = v3;
      _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
        (__int64)&dword_180122070,
        (unsigned __int8 *)byte_18010833B,
        0,
        0,
        (__int64)&v12);
    }
    if ( v3 > 0 )
      v3 = (unsigned __int16)v3 | 0x80070000;
    win32_exception::win32_exception((win32_exception *)&EventDescriptor, v3);
    throw (hresult_exception *)&EventDescriptor;
  }
  if ( I_RpcBindingInqLocalClientPID(*((RPC_BINDING_HANDLE *)this + 6), (unsigned int *)this + 15) )
  {
    LastError = GetLastError();
    UserSidFromToken = LastError;
    if ( LastError > 0 )
      UserSidFromToken = (unsigned __int16)LastError | 0x80070000;
    if ( (unsigned int)dword_180122070 > 2 )
    {
      v12 = GetLastError();
      v20 = &v12;
      v21 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180122078;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      UserData.Reserved = 2;
      v17 = (__int16 *)byte_180108311;
      v18 = 41;
      v19 = 1;
      LODWORD(v13) = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    goto LABEL_7;
  }
  ReturnLength = 4;
  if ( !GetTokenInformation((HANDLE)0xFFFFFFFFFFFFFFFBLL, TokenSessionId, (char *)this + 56, 4u, &ReturnLength) )
  {
    if ( (unsigned int)dword_180122070 > 2 )
    {
      LODWORD(v13) = GetLastError();
      v20 = (DWORD *)&v13;
      v21 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      *(_DWORD *)&EventDescriptor.Level = 2;
      EventDescriptor.Keyword = 0;
      UserData.Ptr = (ULONGLONG)off_180122078;
      UserData.Size = *(unsigned __int16 *)off_180122078;
      UserData.Reserved = 2;
      v17 = (__int16 *)&unk_1801082A8;
      v18 = 31;
      v19 = 1;
      v12 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v8 = GetLastError();
    UserSidFromToken = v8;
    if ( v8 > 0 )
      UserSidFromToken = (unsigned __int16)v8 | 0x80070000;
LABEL_7:
    v6 = RpcRevertToSelfEx(v2);
    if ( v6 )
    {
      if ( (unsigned int)dword_180122070 > 1
        && (qword_180122080 & 0x200000000000LL) != 0
        && (qword_180122088 & 0x200000000000LL) == qword_180122088 )
      {
LABEL_11:
        v20 = (DWORD *)&v13;
        *(_DWORD *)&EventDescriptor.Level = 1;
        LODWORD(v13) = v6;
        v21 = 4;
        *(_DWORD *)&EventDescriptor.Id = 184549376;
        EventDescriptor.Keyword = 0x200000000000LL;
        UserData.Ptr = (ULONGLONG)off_180122078;
        UserData.Size = *(unsigned __int16 *)off_180122078;
        UserData.Reserved = 2;
        v17 = word_180108372;
        v18 = 29;
        v19 = 1;
        v12 = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
        EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
      }
LABEL_12:
      __fastfail(v6);
    }
    return (unsigned int)UserSidFromToken;
  }
  UserSidFromToken = NgcUtils::GetUserSidFromToken((HANDLE)0xFFFFFFFFFFFFFFFALL, (const void **)this + 3);
  if ( UserSidFromToken < 0 )
  {
    v6 = RpcRevertToSelfEx(v2);
    if ( v6 )
    {
      if ( (unsigned int)dword_180122070 > 1
        && (qword_180122080 & 0x200000000000LL) != 0
        && (qword_180122088 & 0x200000000000LL) == qword_180122088 )
      {
        goto LABEL_11;
      }
      goto LABEL_12;
    }
    return (unsigned int)UserSidFromToken;
  }
  v11[0] = 0;
  IsAppContainer = NgcUtils::CallerIsAppContainer((NgcUtils *)v11, v9);
  if ( IsAppContainer >= 0 && v11[0] )
    IsAppContainer = NgcUtils::GetCallerAppContainerSid(this);
  NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator((NgcUtils::RpcCallerImpersonator *)&v13);
  return (unsigned int)IsAppContainer;
}

```

## disassembly

```asm
0x18002dc90  push    rbp
0x18002dc92  push    rbx
0x18002dc93  push    rsi
0x18002dc94  push    rdi
0x18002dc95  push    r14
0x18002dc97  push    r15
0x18002dc99  lea     rbp, [rsp-2Fh]
0x18002dc9e  sub     rsp, 0A8h
0x18002dca5  mov     rax, cs:__security_cookie
0x18002dcac  xor     rax, rsp
0x18002dcaf  mov     [rbp+57h+var_38], rax
0x18002dcb3  mov     rsi, rcx
0x18002dcb6  xor     r15d, r15d
0x18002dcb9  mov     rbx, [rcx+30h]
0x18002dcbd  mov     [rbp+57h+var_98], rbx
0x18002dcc1  mov     rcx, rbx; BindingHandle
0x18002dcc4  call    cs:__imp_RpcImpersonateClient
0x18002dcca  mov     edi, eax
0x18002dccc  test    eax, eax
0x18002dcce  jnz     loc_18002E05F
0x18002dcd4  lea     rdx, [rsi+3Ch]; Pid
0x18002dcd8  mov     rcx, [rsi+30h]; Binding
0x18002dcdc  call    cs:__imp_I_RpcBindingInqLocalClientPID
0x18002dce2  test    eax, eax
0x18002dce4  jz      loc_18002DE98
0x18002dcea  call    cs:__imp_GetLastError
0x18002dcf0  mov     edi, eax
0x18002dcf2  test    eax, eax
0x18002dcf4  jle     short loc_18002DCFF
0x18002dcf6  movzx   edi, ax
0x18002dcf9  or      edi, 80070000h
0x18002dcff  mov     eax, cs:dword_180122070
0x18002dd05  lea     rsi, _TraceLoggingMetadataEnd
0x18002dd0c  lea     r14, _TraceLoggingMetadata
0x18002dd13  cmp     eax, 2
0x18002dd16  jbe     loc_18002DDB0
0x18002dd1c  call    cs:__imp_GetLastError
0x18002dd22  mov     [rbp+57h+var_9C], eax
0x18002dd25  lea     rax, [rbp+57h+var_9C]
0x18002dd29  mov     [rbp+57h+var_48], rax
0x18002dd2d  mov     [rbp+57h+var_40], 4
0x18002dd35  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18002dd3c  movzx   eax, cs:word_180108307
0x18002dd43  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18002dd46  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x18002dd4a  mov     rax, cs:off_180122078
0x18002dd51  mov     [rbp+57h+var_68.Ptr], rax
0x18002dd55  movzx   eax, word ptr [rax]
0x18002dd58  mov     [rbp+57h+var_68.Size], eax
0x18002dd5b  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x18002dd62  lea     rax, byte_180108311
0x18002dd69  mov     [rbp+57h+var_58], rax
0x18002dd6d  mov     [rbp+57h+var_50], 29h ; ')'
0x18002dd74  mov     [rbp+57h+var_4C], 1
0x18002dd7b  mov     rax, rsi
0x18002dd7e  sub     eax, r14d
0x18002dd81  mov     dword ptr [rbp+57h+var_98], eax
0x18002dd84  mov     eax, dword ptr [rbp+57h+var_98]
0x18002dd87  lea     rax, [rbp+57h+var_68]
0x18002dd8b  mov     [rsp+0D0h+UserData], rax; UserData
0x18002dd90  mov     [rsp+0D0h+UserDataCount], 3; UserDataCount
0x18002dd98  xor     r9d, r9d; RelatedActivityId
0x18002dd9b  xor     r8d, r8d; ActivityId
0x18002dd9e  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18002dda2  mov     rcx, cs:RegHandle; RegHandle
0x18002dda9  call    cs:__imp_EventWriteTransfer
0x18002ddaf  nop
0x18002ddb0  mov     rcx, rbx; BindingHandle
0x18002ddb3  call    cs:__imp_RpcRevertToSelfEx
0x18002ddb9  test    eax, eax
0x18002ddbb  mov     ebx, eax
0x18002ddbd  jz      loc_18002DE91
0x18002ddc3  mov     ecx, cs:dword_180122070
0x18002ddc9  cmp     ecx, 1
0x18002ddcc  jbe     loc_18002DE8C
0x18002ddd2  mov     r8, cs:qword_180122088
0x18002ddd9  mov     rdx, 200000000000h
0x18002dde3  mov     rcx, cs:qword_180122080
0x18002ddea  test    rdx, rcx
0x18002dded  jz      loc_18002DE8C
0x18002ddf3  mov     rax, r8
0x18002ddf6  and     rax, rdx
0x18002ddf9  cmp     rax, r8
0x18002ddfc  jnz     loc_18002DE8C
0x18002de02  lea     rax, [rbp+57h+var_98]
0x18002de06  mov     [rbp+57h+var_48], rax
0x18002de0a  movzx   eax, cs:word_180108368
0x18002de11  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18002de14  mov     rax, cs:off_180122078
0x18002de1b  mov     dword ptr [rbp+57h+var_98], ebx
0x18002de1e  mov     [rbp+57h+var_40], 4
0x18002de26  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18002de2d  mov     [rbp+57h+EventDescriptor.Keyword], rdx
0x18002de31  mov     [rbp+57h+var_68.Ptr], rax
0x18002de35  movzx   eax, word ptr [rax]
0x18002de38  mov     [rbp+57h+var_68.Size], eax
0x18002de3b  lea     rax, word_180108372
0x18002de42  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x18002de49  mov     [rbp+57h+var_58], rax
0x18002de4d  mov     [rbp+57h+var_50], 1Dh
0x18002de54  mov     [rbp+57h+var_4C], 1
0x18002de5b  sub     esi, r14d
0x18002de5e  mov     [rbp+57h+var_9C], esi
0x18002de61  mov     eax, [rbp+57h+var_9C]
0x18002de64  lea     rax, [rbp+57h+var_68]
0x18002de68  mov     [rsp+0D0h+UserData], rax; UserData
0x18002de6d  mov     [rsp+0D0h+UserDataCount], 3; UserDataCount
0x18002de75  xor     r9d, r9d; RelatedActivityId
0x18002de78  xor     r8d, r8d; ActivityId
0x18002de7b  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18002de7f  mov     rcx, cs:RegHandle; RegHandle
0x18002de86  call    cs:__imp_EventWriteTransfer
0x18002de8c  mov     rcx, rbx
0x18002de8f  int     29h; Win8: RtlFailFast(ecx)
0x18002de91  mov     eax, edi
0x18002de93  jmp     loc_18002E043
0x18002de98  mov     [rbp+57h+ReturnLength], 4
0x18002de9f  lea     r8, [rsi+38h]; TokenInformation
0x18002dea3  lea     rax, [rbp+57h+ReturnLength]
0x18002dea7  mov     qword ptr [rsp+0D0h+UserDataCount], rax; ReturnLength
0x18002deac  mov     edx, 0Ch; TokenInformationClass
0x18002deb1  mov     rcx, 0FFFFFFFFFFFFFFFBh; TokenHandle
0x18002deb8  mov     r9d, 4; TokenInformationLength
0x18002debe  call    cs:__imp_GetTokenInformation
0x18002dec4  test    eax, eax
0x18002dec6  jnz     loc_18002DF9A
0x18002decc  mov     eax, cs:dword_180122070
0x18002ded2  lea     rsi, _TraceLoggingMetadataEnd
0x18002ded9  lea     r14, _TraceLoggingMetadata
0x18002dee0  cmp     eax, 2
0x18002dee3  jbe     loc_18002DF7C
0x18002dee9  call    cs:__imp_GetLastError
0x18002deef  mov     dword ptr [rbp+57h+var_98], eax
0x18002def2  lea     rax, [rbp+57h+var_98]
0x18002def6  mov     [rbp+57h+var_48], rax
0x18002defa  mov     [rbp+57h+var_40], 4
0x18002df02  mov     dword ptr [rbp+57h+EventDescriptor.Id], 0B000000h
0x18002df09  movzx   eax, cs:word_18010829E
0x18002df10  mov     dword ptr [rbp+57h+EventDescriptor.Level], eax
0x18002df13  mov     [rbp+57h+EventDescriptor.Keyword], r15
0x18002df17  mov     rax, cs:off_180122078
0x18002df1e  mov     [rbp+57h+var_68.Ptr], rax
0x18002df22  movzx   eax, word ptr [rax]
0x18002df25  mov     [rbp+57h+var_68.Size], eax
0x18002df28  mov     dword ptr [rbp+57h+var_68.0Ch], 2
0x18002df2f  lea     rax, unk_1801082A8
0x18002df36  mov     [rbp+57h+var_58], rax
0x18002df3a  mov     [rbp+57h+var_50], 1Fh
0x18002df41  mov     [rbp+57h+var_4C], 1
0x18002df48  mov     rax, rsi
0x18002df4b  sub     eax, r14d
0x18002df4e  mov     [rbp+57h+var_9C], eax
0x18002df51  mov     eax, [rbp+57h+var_9C]
0x18002df54  lea     rax, [rbp+57h+var_68]
0x18002df58  mov     [rsp+0D0h+UserData], rax; UserData
0x18002df5d  mov     [rsp+0D0h+UserDataCount], 3; UserDataCount
0x18002df65  xor     r9d, r9d; RelatedActivityId
0x18002df68  xor     r8d, r8d; ActivityId
0x18002df6b  lea     rdx, [rbp+57h+EventDescriptor]; EventDescriptor
0x18002df6f  mov     rcx, cs:RegHandle; RegHandle
0x18002df76  call    cs:__imp_EventWriteTransfer
0x18002df7c  call    cs:__imp_GetLastError
0x18002df82  mov     edi, eax
0x18002df84  test    eax, eax
0x18002df86  jle     loc_18002DDB0
0x18002df8c  movzx   edi, ax
0x18002df8f  or      edi, 80070000h
0x18002df95  jmp     loc_18002DDB0
0x18002df9a  lea     rdx, [rsi+18h]
0x18002df9e  mov     rcx, 0FFFFFFFFFFFFFFFAh; TokenHandle
0x18002dfa5  call    NgcUtils__GetUserSidFromToken
0x18002dfaa  mov     edi, eax
0x18002dfac  test    eax, eax
0x18002dfae  jns     short loc_18002E015
0x18002dfb0  mov     rcx, rbx; BindingHandle
0x18002dfb3  call    cs:__imp_RpcRevertToSelfEx
0x18002dfb9  mov     ebx, eax
0x18002dfbb  test    eax, eax
0x18002dfbd  jz      loc_18002DE91
0x18002dfc3  mov     ecx, cs:dword_180122070
0x18002dfc9  cmp     ecx, 1
0x18002dfcc  jbe     loc_18002DE8C
0x18002dfd2  mov     r8, cs:qword_180122088
0x18002dfd9  mov     rcx, cs:qword_180122080
0x18002dfe0  mov     rdx, 200000000000h
0x18002dfea  test    rdx, rcx
0x18002dfed  jz      loc_18002DE8C
0x18002dff3  mov     rax, r8
0x18002dff6  and     rax, rdx
0x18002dff9  cmp     rax, r8
0x18002dffc  jnz     loc_18002DE8C
0x18002e002  lea     rsi, _TraceLoggingMetadataEnd
0x18002e009  lea     r14, _TraceLoggingMetadata
0x18002e010  jmp     loc_18002DE02
0x18002e015  mov     [rbp+57h+var_A0], 0
0x18002e019  lea     rcx, [rbp+57h+var_A0]; this
0x18002e01d  call    ?CallerIsAppContainer@NgcUtils@@YAJPEA_N@Z; NgcUtils::CallerIsAppContainer(bool *)
0x18002e022  mov     ebx, eax
0x18002e024  test    eax, eax
0x18002e026  js      short loc_18002E038
0x18002e028  cmp     [rbp+57h+var_A0], 0
0x18002e02c  jz      short loc_18002E038
0x18002e02e  mov     rcx, rsi
0x18002e031  call    ?GetCallerAppContainerSid@NgcUtils@@YAJPEAV?$vector@EV?$allocator@E@std@@@std@@@Z; NgcUtils::GetCallerAppContainerSid(std::vector<uchar> *)
0x18002e036  mov     ebx, eax
0x18002e038  lea     rcx, [rbp+57h+var_98]; this
0x18002e03c  call    ??1RpcCallerImpersonator@NgcUtils@@QEAA@XZ; NgcUtils::RpcCallerImpersonator::~RpcCallerImpersonator(void)
0x18002e041  mov     eax, ebx
0x18002e043  mov     rcx, [rbp+57h+var_38]
0x18002e047  xor     rcx, rsp; StackCookie
0x18002e04a  call    __security_check_cookie
0x18002e04f  add     rsp, 0A8h
0x18002e056  pop     r15
0x18002e058  pop     r14
0x18002e05a  pop     rdi
0x18002e05b  pop     rsi
0x18002e05c  pop     rbx
0x18002e05d  pop     rbp
0x18002e05e  retn
0x18002e05f  mov     eax, cs:dword_180122070
0x18002e065  cmp     eax, 2
0x18002e068  jbe     short loc_18002E0A1
0x18002e06a  xor     edx, edx
0x18002e06c  lea     rcx, dword_180122070
0x18002e073  call    _tlgKeywordOn
0x18002e078  test    al, al
0x18002e07a  jz      short loc_18002E0A1
0x18002e07c  mov     [rbp+57h+var_9C], edi
0x18002e07f  lea     rax, [rbp+57h+var_9C]
0x18002e083  mov     qword ptr [rsp+0D0h+UserDataCount], rax
0x18002e088  xor     r9d, r9d
0x18002e08b  xor     r8d, r8d
0x18002e08e  lea     rdx, byte_18010833B
0x18002e095  lea     rcx, dword_180122070
0x18002e09c  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x18002e0a1  test    edi, edi
0x18002e0a3  jle     short loc_18002E0AE
0x18002e0a5  movzx   edi, di
0x18002e0a8  or      edi, 80070000h
0x18002e0ae  mov     edx, edi; unsigned int
0x18002e0b0  lea     rcx, [rbp+57h+EventDescriptor]; this
0x18002e0b4  call    ??0win32_exception@@QEAA@K@Z; win32_exception::win32_exception(ulong)
0x18002e0b9  lea     rdx, _TI3?AVhresult_exception@@; pThrowInfo
0x18002e0c0  lea     rcx, [rbp+57h+EventDescriptor]; pExceptionObject
0x18002e0c4  call    _CxxThrowException_0
```
