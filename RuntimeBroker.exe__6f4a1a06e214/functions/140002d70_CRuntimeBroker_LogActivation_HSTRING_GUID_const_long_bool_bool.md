# CRuntimeBroker::LogActivation(HSTRING__ *,_GUID const &,long,bool,bool)

- ea: `0x140002d70`
- end: `0x140003528`
- name: `?LogActivation@CRuntimeBroker@@SAXPEAUHSTRING__@@AEBU_GUID@@J_N2@Z`
- size: `1976`
- prototype: `void __fastcall(HSTRING, const struct _GUID *, int, bool, bool)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x140002260`
- `0x140002590`

## callees

- `0x140002d70`
- `0x140008c80`
- `0x140010010`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140002dd0`
- `api-ms-win-core-synch-l1-2-0!InitOnceExecuteOnce` at `0x140002dd0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fe9`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002f7b`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140002fe9`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002f8e`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x140002f8e`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002f23`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400030c1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400032d0`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140002f23`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400030c1`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x1400032d0`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400034ed`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x140002f86`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x1400034ed`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140002fd3`
- `api-ms-win-core-psapi-l1-1-0!QueryFullProcessImageNameW` at `0x140002fd3`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140002f34`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x140002f34`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140002e00`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x140002e00`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140002f50`
- `api-ms-win-core-com-l1-1-0!CoGetCallContext` at `0x140002f50`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140002de3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140003116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140003338`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140002de3`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140003116`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsGetStringRawBuffer` at `0x140003338`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x140002e41`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x140002e41`

## pseudocode

```c
void __fastcall CRuntimeBroker::LogActivation(HSTRING a1, const struct _GUID *a2, int a3, char a4)
{
  PCWSTR StringRawBuffer; // r14
  HRESULT v6; // eax
  signed int v7; // ecx
  bool v8; // bl
  LONG ApplicationUserModelIdFromToken; // eax
  WCHAR *v10; // rdi
  signed int v11; // ecx
  void *v12; // r15
  HANDLE v13; // rsi
  __int64 (__fastcall *v14)(void *, __int64, HANDLE *); // r12
  DWORD LastError; // ebx
  WCHAR *v16; // rbx
  signed int v17; // eax
  const wchar_t *v18; // rsi
  PCWSTR v19; // rax
  __int64 v20; // rcx
  const size_t *v21; // r8
  __int64 v22; // rdx
  bool v23; // zf
  int v24; // edx
  __int64 v25; // rax
  int v26; // eax
  __int64 v27; // rax
  int v28; // eax
  __int64 v29; // rax
  int v30; // ecx
  const wchar_t *v31; // rsi
  PCWSTR v32; // rax
  __int64 v33; // rcx
  const size_t *v34; // r8
  __int64 v35; // rdx
  int v36; // edx
  __int64 v37; // rax
  int v38; // eax
  __int64 v39; // rax
  int v40; // ecx
  void *v41; // rcx
  UINT32 applicationUserModelIdLength; // [rsp+38h] [rbp-D0h] BYREF
  DWORD dwSize; // [rsp+3Ch] [rbp-CCh] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-C8h] BYREF
  __int64 v45; // [rsp+50h] [rbp-B8h]
  HANDLE hObject; // [rsp+58h] [rbp-B0h] BYREF
  void *ppInterface; // [rsp+60h] [rbp-A8h] BYREF
  HSTRING string; // [rsp+68h] [rbp-A0h]
  const struct _GUID *v49; // [rsp+70h] [rbp-98h]
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+78h] [rbp-90h] BYREF
  __int16 *v51; // [rsp+88h] [rbp-80h]
  int v52; // [rsp+90h] [rbp-78h]
  int v53; // [rsp+94h] [rbp-74h]
  UINT32 *p_applicationUserModelIdLength; // [rsp+98h] [rbp-70h]
  __int64 v55; // [rsp+A0h] [rbp-68h]
  struct _EVENT_DATA_DESCRIPTOR v56; // [rsp+A8h] [rbp-60h] BYREF
  char *v57; // [rsp+B8h] [rbp-50h]
  int v58; // [rsp+C0h] [rbp-48h]
  int v59; // [rsp+C4h] [rbp-44h]
  const size_t *v60; // [rsp+C8h] [rbp-40h]
  int v61; // [rsp+D0h] [rbp-38h]
  int v62; // [rsp+D4h] [rbp-34h]
  const struct _GUID *v63; // [rsp+D8h] [rbp-30h]
  __int64 v64; // [rsp+E0h] [rbp-28h]
  DWORD *p_dwSize; // [rsp+E8h] [rbp-20h]
  __int64 v66; // [rsp+F0h] [rbp-18h]
  const wchar_t *v67; // [rsp+F8h] [rbp-10h]
  int v68; // [rsp+100h] [rbp-8h]
  int v69; // [rsp+104h] [rbp-4h]
  WCHAR *v70; // [rsp+108h] [rbp+0h]
  int v71; // [rsp+110h] [rbp+8h]
  int v72; // [rsp+114h] [rbp+Ch]
  WCHAR *v73; // [rsp+118h] [rbp+10h]
  int v74; // [rsp+120h] [rbp+18h]
  int v75; // [rsp+124h] [rbp+1Ch]
  PCWSTR v76; // [rsp+128h] [rbp+20h]
  int v77; // [rsp+130h] [rbp+28h]
  int v78; // [rsp+134h] [rbp+2Ch]
  WCHAR applicationUserModelId[136]; // [rsp+138h] [rbp+30h] BYREF
  WCHAR ExeName[264]; // [rsp+248h] [rbp+140h] BYREF

  LODWORD(v45) = a3;
  v49 = a2;
  string = a1;
  if ( !InitOnceExecuteOnce(
          &`CRuntimeBroker::GetBrokerAumid'::`2'::brokerAumidInitOnce,
          CRuntimeBroker::ReadBrokerAumid,
          0,
          0)
    || (StringRawBuffer = WindowsGetStringRawBuffer(CRuntimeBroker::s_brokerAumid, 0)) == 0 )
  {
    StringRawBuffer = L"ERROR";
  }
  v6 = CoImpersonateClient();
  v7 = v6;
  if ( v6 < 0 )
  {
    v8 = 0;
LABEL_13:
    if ( (unsigned int)dword_140018008 > 2 )
    {
      applicationUserModelIdLength = v7;
      p_applicationUserModelIdLength = &applicationUserModelIdLength;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_140018010;
      v55 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_140018010;
      v51 = (__int16 *)byte_14001430D;
      UserData.Reserved = 2;
      v52 = 34;
      v53 = 1;
      dwSize = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v10 = L"ERROR";
    goto LABEL_16;
  }
  applicationUserModelIdLength = 130;
  v8 = v6 >= 0;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      (HANDLE)0xFFFFFFFFFFFFFFFBLL,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  v7 = ApplicationUserModelIdFromToken;
  if ( ApplicationUserModelIdFromToken )
  {
    if ( ApplicationUserModelIdFromToken != 15703 )
    {
      if ( ApplicationUserModelIdFromToken > 0 )
        v7 = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
      v10 = 0;
      if ( v7 >= 0 )
        goto LABEL_16;
      goto LABEL_13;
    }
    v10 = (WCHAR *)&Format;
  }
  else
  {
    v10 = applicationUserModelId;
  }
LABEL_16:
  if ( v8 )
    CoRevertToSelf();
  ppInterface = 0;
  hObject = 0;
  v11 = CoGetCallContext(&GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541, &ppInterface);
  if ( v11 < 0 )
    goto LABEL_27;
  v12 = ppInterface;
  v13 = hObject;
  v14 = *(__int64 (__fastcall **)(void *, __int64, HANDLE *))(*(_QWORD *)ppInterface + 24LL);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
  {
    LastError = GetLastError();
    CloseHandle(v13);
    SetLastError(LastError);
  }
  hObject = 0;
  v11 = v14(v12, 4096, &hObject);
  if ( v11 < 0 )
    goto LABEL_27;
  dwSize = 260;
  if ( QueryFullProcessImageNameW(hObject, 0, ExeName, &dwSize) )
  {
    v16 = ExeName;
    goto LABEL_30;
  }
  v17 = GetLastError();
  v11 = v17;
  if ( v17 > 0 )
    v11 = (unsigned __int16)v17 | 0x80070000;
  v16 = 0;
  if ( v11 < 0 )
  {
LABEL_27:
    if ( (unsigned int)dword_140018008 > 2 )
    {
      dwSize = v11;
      p_applicationUserModelIdLength = &dwSize;
      *(_DWORD *)&EventDescriptor.Level = 2;
      UserData.Ptr = (ULONGLONG)off_140018010;
      v55 = 4;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      UserData.Size = (unsigned __int16)*off_140018010;
      v51 = word_1400142E2;
      UserData.Reserved = 2;
      v52 = 31;
      v53 = 1;
      applicationUserModelIdLength = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
    }
    v16 = L"ERROR";
  }
LABEL_30:
  if ( byte_140018608 )
  {
    if ( (unsigned int)dword_140018008 > 4 )
    {
      v18 = L"ActivateInstance";
      if ( !a4 )
        v18 = L"GetActivationFactory";
      dwSize = v45;
      v19 = WindowsGetStringRawBuffer(string, 0);
      v20 = -1;
      v21 = (const size_t *)v19;
      if ( StringRawBuffer )
      {
        v22 = -1;
        do
          v23 = StringRawBuffer[++v22] == 0;
        while ( !v23 );
        v24 = 2 * v22 + 2;
      }
      else
      {
        StringRawBuffer = (PCWSTR)&Format;
        v24 = 2;
      }
      v76 = StringRawBuffer;
      v77 = v24;
      v78 = 0;
      if ( v16 )
      {
        v25 = -1;
        do
          v23 = v16[++v25] == 0;
        while ( !v23 );
        v26 = 2 * v25 + 2;
      }
      else
      {
        v16 = (WCHAR *)&Format;
        v26 = 2;
      }
      v73 = v16;
      v74 = v26;
      v75 = 0;
      if ( v10 )
      {
        v27 = -1;
        do
          v23 = v10[++v27] == 0;
        while ( !v23 );
        v28 = 2 * v27 + 2;
      }
      else
      {
        v10 = (WCHAR *)&Format;
        v28 = 2;
      }
      v71 = v28;
      v29 = -1;
      v70 = v10;
      v72 = 0;
      do
        v23 = v18[++v29] == 0;
      while ( !v23 );
      v67 = v18;
      v68 = 2 * v29 + 2;
      p_dwSize = &dwSize;
      v63 = v49;
      v69 = 0;
      v66 = 4;
      v64 = 16;
      if ( v21 )
      {
        do
          v23 = *((_WORD *)v21 + ++v20) == 0;
        while ( !v23 );
        v30 = 2 * v20 + 2;
      }
      else
      {
        v21 = &Format;
        v30 = 2;
      }
      *(_DWORD *)&EventDescriptor.Level = 4;
      v56.Ptr = (ULONGLONG)off_140018010;
      v61 = v30;
      v60 = v21;
      v62 = 0;
      *(_DWORD *)&EventDescriptor.Id = 184549376;
      EventDescriptor.Keyword = 0;
      v56.Size = (unsigned __int16)*off_140018010;
      v57 = byte_14001433B;
      v56.Reserved = 2;
      v58 = 170;
      v59 = 1;
      applicationUserModelIdLength = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
      EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 9u, &v56);
    }
  }
  else if ( (unsigned int)dword_140018008 > 4
         && (qword_140018018 & 0x200000000000LL) != 0
         && (qword_140018020 & 0x200000000000LL) == qword_140018020 )
  {
    v31 = L"ActivateInstance";
    if ( !a4 )
      v31 = L"GetActivationFactory";
    dwSize = v45;
    v32 = WindowsGetStringRawBuffer(string, 0);
    v33 = -1;
    v34 = (const size_t *)v32;
    if ( v16 )
    {
      v35 = -1;
      do
        v23 = v16[++v35] == 0;
      while ( !v23 );
      v36 = 2 * v35 + 2;
    }
    else
    {
      v16 = (WCHAR *)&Format;
      v36 = 2;
    }
    v73 = v16;
    v74 = v36;
    v75 = 0;
    if ( v10 )
    {
      v37 = -1;
      do
        v23 = v10[++v37] == 0;
      while ( !v23 );
      v38 = 2 * v37 + 2;
    }
    else
    {
      v10 = (WCHAR *)&Format;
      v38 = 2;
    }
    v71 = v38;
    v39 = -1;
    v70 = v10;
    v72 = 0;
    do
      v23 = v31[++v39] == 0;
    while ( !v23 );
    v67 = v31;
    v68 = 2 * v39 + 2;
    p_dwSize = &dwSize;
    v63 = v49;
    v69 = 0;
    v66 = 4;
    v64 = 16;
    if ( v34 )
    {
      do
        v23 = *((_WORD *)v34 + ++v33) == 0;
      while ( !v23 );
      v40 = 2 * v33 + 2;
    }
    else
    {
      v34 = &Format;
      v40 = 2;
    }
    *(_DWORD *)&EventDescriptor.Level = 4;
    v56.Ptr = (ULONGLONG)off_140018010;
    v61 = v40;
    v60 = v34;
    v62 = 0;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0x200000000000LL;
    v56.Size = (unsigned __int16)*off_140018010;
    v57 = byte_1400143F1;
    v56.Reserved = 2;
    v58 = 143;
    v59 = 1;
    applicationUserModelIdLength = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 8u, &v56);
  }
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  v41 = ppInterface;
  if ( ppInterface )
  {
    ppInterface = 0;
    (*(void (__fastcall **)(void *))(*(_QWORD *)v41 + 16LL))(v41);
  }
}

```

## disassembly

```asm
0x140002d70  mov     r11, rsp
0x140002d73  push    rbp
0x140002d74  push    r14
0x140002d76  lea     rbp, [r11-388h]
0x140002d7d  sub     rsp, 478h
0x140002d84  mov     rax, cs:__security_cookie
0x140002d8b  xor     rax, rsp
0x140002d8e  mov     [rbp+380h+var_30], rax
0x140002d95  mov     [r11+10h], rbx
0x140002d99  mov     [r11+18h], rsi
0x140002d9d  mov     [r11-18h], r12
0x140002da1  mov     [r11-20h], r13
0x140002da5  movzx   r13d, r9b
0x140002da9  mov     dword ptr [rsp+480h+var_438], r8d
0x140002dae  xor     r9d, r9d; Context
0x140002db1  mov     [rsp+480h+var_418], rdx
0x140002db6  xor     r8d, r8d; Parameter
0x140002db9  mov     [rsp+480h+string], rcx
0x140002dbe  lea     rdx, ?ReadBrokerAumid@CRuntimeBroker@@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z; InitFn
0x140002dc5  lea     rcx, ?brokerAumidInitOnce@?1??GetBrokerAumid@CRuntimeBroker@@SAPEBGXZ@4T_RTL_RUN_ONCE@@A; InitOnce
0x140002dcc  mov     [r11-28h], r15
0x140002dd0  call    cs:__imp_InitOnceExecuteOnce
0x140002dd6  test    eax, eax
0x140002dd8  jz      short loc_140002DF1
0x140002dda  mov     rcx, cs:?s_brokerAumid@CRuntimeBroker@@2VHString@Wrappers@WRL@Microsoft@@A; string
0x140002de1  xor     edx, edx; length
0x140002de3  call    cs:__imp_WindowsGetStringRawBuffer
0x140002de9  mov     r14, rax
0x140002dec  test    rax, rax
0x140002def  jnz     short loc_140002DF8
0x140002df1  lea     r14, aError; "ERROR"
0x140002df8  mov     [rsp+480h+arg_18], rdi
0x140002e00  call    cs:__imp_CoImpersonateClient
0x140002e06  xor     r15d, r15d
0x140002e09  lea     rsi, _TraceLoggingMetadataEnd
0x140002e10  lea     r12, _TraceLoggingMetadata
0x140002e17  mov     ecx, eax
0x140002e19  test    eax, eax
0x140002e1b  jns     short loc_140002E21
0x140002e1d  xor     bl, bl
0x140002e1f  jmp     short loc_140002E81
0x140002e21  mov     ebx, eax
0x140002e23  mov     [rsp+480h+applicationUserModelIdLength], 82h
0x140002e2b  shr     ebx, 1Fh
0x140002e2e  lea     r8, [rbp+380h+applicationUserModelId]; applicationUserModelId
0x140002e32  lea     rdx, [rsp+480h+applicationUserModelIdLength]; applicationUserModelIdLength
0x140002e37  mov     rcx, 0FFFFFFFFFFFFFFFBh; token
0x140002e3e  xor     bl, 1
0x140002e41  call    cs:__imp_GetApplicationUserModelIdFromToken
0x140002e47  mov     ecx, eax
0x140002e49  test    eax, eax
0x140002e4b  jnz     short loc_140002E56
0x140002e4d  lea     rdi, [rbp+380h+applicationUserModelId]
0x140002e51  jmp     loc_140002F30
0x140002e56  cmp     eax, 3D57h
0x140002e5b  jnz     short loc_140002E69
0x140002e5d  lea     rdi, Format
0x140002e64  jmp     loc_140002F30
0x140002e69  test    eax, eax
0x140002e6b  jle     short loc_140002E76
0x140002e6d  movzx   ecx, ax
0x140002e70  or      ecx, 80070000h
0x140002e76  mov     rdi, r15
0x140002e79  test    ecx, ecx
0x140002e7b  jns     loc_140002F30
0x140002e81  mov     eax, cs:dword_140018008
0x140002e87  cmp     eax, 2
0x140002e8a  jbe     loc_140002F29
0x140002e90  mov     [rsp+480h+applicationUserModelIdLength], ecx
0x140002e94  lea     rax, [rsp+480h+applicationUserModelIdLength]
0x140002e99  mov     [rbp+380h+var_3F0], rax
0x140002e9d  lea     rdx, [rsp+480h+EventDescriptor]; EventDescriptor
0x140002ea2  movzx   eax, cs:word_140014303
0x140002ea9  xor     r9d, r9d; RelatedActivityId
0x140002eac  mov     dword ptr [rsp+480h+EventDescriptor.Level], eax
0x140002eb0  xor     r8d, r8d; ActivityId
0x140002eb3  mov     rax, cs:off_140018010
0x140002eba  mov     [rsp+480h+var_410.Ptr], rax
0x140002ebf  mov     [rbp+380h+var_3E8], 4
0x140002ec7  mov     dword ptr [rsp+480h+EventDescriptor.Id], 0B000000h
0x140002ecf  mov     [rsp+480h+EventDescriptor.Keyword], r15
0x140002ed4  movzx   eax, word ptr [rax]
0x140002ed7  mov     [rsp+480h+var_410.Size], eax
0x140002edb  lea     rax, byte_14001430D
0x140002ee2  mov     [rbp+380h+var_400], rax
0x140002ee6  mov     rax, rsi
0x140002ee9  sub     eax, r12d
0x140002eec  mov     dword ptr [rsp+480h+var_410.0Ch], 2
0x140002ef4  mov     [rbp+380h+var_3F8], 22h ; '"'
0x140002efb  mov     [rbp+380h+var_3F4], 1
0x140002f02  mov     [rsp+480h+dwSize], eax
0x140002f06  mov     eax, [rsp+480h+dwSize]
0x140002f0a  mov     rcx, cs:RegHandle; RegHandle
0x140002f11  lea     rax, [rsp+480h+var_410]
0x140002f16  mov     [rsp+480h+UserData], rax; UserData
0x140002f1b  mov     [rsp+480h+UserDataCount], 3; UserDataCount
0x140002f23  call    cs:__imp_EventWriteTransfer
0x140002f29  lea     rdi, aError; "ERROR"
0x140002f30  test    bl, bl
0x140002f32  jz      short loc_140002F3A
0x140002f34  call    cs:__imp_CoRevertToSelf
0x140002f3a  lea     rdx, [rsp+480h+ppInterface]; ppInterface
0x140002f3f  mov     [rsp+480h+ppInterface], r15
0x140002f44  lea     rcx, _GUID_68c6a1b9_de39_42c3_8d28_bf40a5126541; riid
0x140002f4b  mov     [rsp+480h+hObject], r15
0x140002f50  call    cs:__imp_CoGetCallContext
0x140002f56  mov     ecx, eax
0x140002f58  test    eax, eax
0x140002f5a  js      loc_14000301F
0x140002f60  mov     r15, [rsp+480h+ppInterface]
0x140002f65  mov     rsi, [rsp+480h+hObject]
0x140002f6a  mov     rax, [r15]
0x140002f6d  mov     r12, [rax+18h]
0x140002f71  lea     rax, [rsi-1]
0x140002f75  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x140002f79  ja      short loc_140002F94
0x140002f7b  call    cs:__imp_GetLastError
0x140002f81  mov     rcx, rsi; hObject
0x140002f84  mov     ebx, eax
0x140002f86  call    cs:__imp_CloseHandle
0x140002f8c  mov     ecx, ebx; dwErrCode
0x140002f8e  call    cs:__imp_SetLastError
0x140002f94  lea     r8, [rsp+480h+hObject]
0x140002f99  mov     [rsp+480h+hObject], 0
0x140002fa2  mov     edx, 1000h
0x140002fa7  mov     rcx, r15
0x140002faa  mov     rax, r12
0x140002fad  call    _guard_dispatch_icall$thunk$10345483385596137414
0x140002fb2  mov     ecx, eax
0x140002fb4  test    eax, eax
0x140002fb6  js      short loc_14000300E
0x140002fb8  mov     rcx, [rsp+480h+hObject]; hProcess
0x140002fbd  lea     r9, [rsp+480h+dwSize]; lpdwSize
0x140002fc2  lea     r8, [rbp+380h+ExeName]; lpExeName
0x140002fc9  mov     [rsp+480h+dwSize], 104h
0x140002fd1  xor     edx, edx; dwFlags
0x140002fd3  call    cs:__imp_QueryFullProcessImageNameW
0x140002fd9  test    eax, eax
0x140002fdb  jz      short loc_140002FE9
0x140002fdd  lea     rbx, [rbp+380h+ExeName]
0x140002fe4  jmp     loc_1400030CE
0x140002fe9  call    cs:__imp_GetLastError
0x140002fef  mov     ecx, eax
0x140002ff1  test    eax, eax
0x140002ff3  jle     short loc_140002FFE
0x140002ff5  movzx   ecx, ax
0x140002ff8  or      ecx, 80070000h
0x140002ffe  xor     r15d, r15d
0x140003001  mov     ebx, r15d
0x140003004  test    ecx, ecx
0x140003006  jns     loc_1400030CE
0x14000300c  jmp     short loc_140003011
0x14000300e  xor     r15d, r15d
0x140003011  lea     r12, _TraceLoggingMetadata
0x140003018  lea     rsi, _TraceLoggingMetadataEnd
0x14000301f  mov     eax, cs:dword_140018008
0x140003025  cmp     eax, 2
0x140003028  jbe     loc_1400030C7
0x14000302e  mov     [rsp+480h+dwSize], ecx
0x140003032  lea     rax, [rsp+480h+dwSize]
0x140003037  mov     [rbp+380h+var_3F0], rax
0x14000303b  lea     rdx, [rsp+480h+EventDescriptor]; EventDescriptor
0x140003040  movzx   eax, cs:word_1400142D8
0x140003047  xor     r9d, r9d; RelatedActivityId
0x14000304a  mov     dword ptr [rsp+480h+EventDescriptor.Level], eax
0x14000304e  xor     r8d, r8d; ActivityId
0x140003051  mov     rax, cs:off_140018010
0x140003058  mov     [rsp+480h+var_410.Ptr], rax
0x14000305d  mov     [rbp+380h+var_3E8], 4
0x140003065  mov     dword ptr [rsp+480h+EventDescriptor.Id], 0B000000h
0x14000306d  mov     [rsp+480h+EventDescriptor.Keyword], r15
0x140003072  movzx   eax, word ptr [rax]
0x140003075  mov     [rsp+480h+var_410.Size], eax
0x140003079  lea     rax, word_1400142E2
0x140003080  mov     [rbp+380h+var_400], rax
0x140003084  mov     rax, rsi
0x140003087  sub     eax, r12d
0x14000308a  mov     dword ptr [rsp+480h+var_410.0Ch], 2
0x140003092  mov     [rbp+380h+var_3F8], 1Fh
0x140003099  mov     [rbp+380h+var_3F4], 1
0x1400030a0  mov     [rsp+480h+applicationUserModelIdLength], eax
0x1400030a4  mov     eax, [rsp+480h+applicationUserModelIdLength]
0x1400030a8  mov     rcx, cs:RegHandle; RegHandle
0x1400030af  lea     rax, [rsp+480h+var_410]
0x1400030b4  mov     [rsp+480h+UserData], rax; UserData
0x1400030b9  mov     [rsp+480h+UserDataCount], 3; UserDataCount
0x1400030c1  call    cs:__imp_EventWriteTransfer
0x1400030c7  lea     rbx, aError; "ERROR"
0x1400030ce  cmp     cs:byte_140018608, 0
0x1400030d5  mov     r12, [rsp+470h]
0x1400030dd  mov     eax, cs:dword_140018008
0x1400030e3  jz      loc_1400032DB
0x1400030e9  cmp     eax, 4
0x1400030ec  jbe     loc_1400034B3
0x1400030f2  mov     rcx, [rsp+480h+string]; string
0x1400030f7  lea     rax, aGetactivationf; "GetActivationFactory"
0x1400030fe  test    r13b, r13b
0x140003101  lea     rsi, aActivateinstan; "ActivateInstance"
0x140003108  cmovz   rsi, rax
0x14000310c  mov     eax, dword ptr [rsp+480h+var_438]
0x140003110  xor     edx, edx; length
0x140003112  mov     [rsp+480h+dwSize], eax
0x140003116  call    cs:__imp_WindowsGetStringRawBuffer
0x14000311c  mov     rcx, 0FFFFFFFFFFFFFFFFh
0x140003123  mov     r8, rax
0x140003126  test    r14, r14
0x140003129  jz      short loc_140003146
0x14000312b  mov     rdx, rcx
0x14000312e  xchg    ax, ax
0x140003130  cmp     word ptr [r14+rdx*2+2], 0
0x140003137  lea     rdx, [rdx+1]
0x14000313b  jnz     short loc_140003130
0x14000313d  lea     edx, ds:2[rdx*2]
0x140003144  jmp     short loc_140003152
0x140003146  lea     r14, Format
0x14000314d  mov     edx, 2
0x140003152  mov     [rbp+380h+var_360], r14
0x140003156  xor     r14d, r14d
0x140003159  mov     [rbp+380h+var_358], edx
0x14000315c  mov     [rbp+380h+var_354], r14d
0x140003160  test    rbx, rbx
0x140003163  jz      short loc_140003185
0x140003165  mov     rax, rcx
0x140003168  nop     dword ptr [rax+rax+00000000h]
0x140003170  cmp     [rbx+rax*2+2], r14w
0x140003176  lea     rax, [rax+1]
0x14000317a  jnz     short loc_140003170
0x14000317c  lea     eax, ds:2[rax*2]
0x140003183  jmp     short loc_140003191
0x140003185  lea     rbx, Format
0x14000318c  mov     eax, 2
0x140003191  mov     [rbp+380h+var_370], rbx
0x140003195  mov     [rbp+380h+var_368], eax
0x140003198  mov     [rbp+380h+var_364], r14d
0x14000319c  test    rdi, rdi
0x14000319f  jz      short loc_1400031B9
0x1400031a1  mov     rax, rcx
0x1400031a4  cmp     [rdi+rax*2+2], r14w
0x1400031aa  lea     rax, [rax+1]
0x1400031ae  jnz     short loc_1400031A4
0x1400031b0  lea     eax, ds:2[rax*2]
0x1400031b7  jmp     short loc_1400031C5
0x1400031b9  lea     rdi, Format
0x1400031c0  mov     eax, 2
0x1400031c5  mov     [rbp+380h+var_378], eax
0x1400031c8  mov     rax, rcx
0x1400031cb  mov     [rbp+380h+var_380], rdi
0x1400031cf  mov     [rbp+380h+var_374], r14d
0x1400031d3  cmp     [rsi+rax*2+2], r14w
0x1400031d9  lea     rax, [rax+1]
0x1400031dd  jnz     short loc_1400031D3
0x1400031df  mov     [rbp+380h+var_390], rsi
0x1400031e3  lea     eax, ds:2[rax*2]
0x1400031ea  mov     [rbp+380h+var_388], eax
0x1400031ed  lea     rax, [rsp+480h+dwSize]
0x1400031f2  mov     [rbp+380h+var_3A0], rax
0x1400031f6  mov     rax, [rsp+480h+var_418]
0x1400031fb  mov     [rbp+380h+var_3B0], rax
0x1400031ff  mov     [rbp+380h+var_384], r14d
0x140003203  mov     [rbp+380h+var_398], 4
0x14000320b  mov     [rbp+380h+var_3A8], 10h
0x140003213  test    r8, r8
0x140003216  jz      short loc_140003235
0x140003218  nop     dword ptr [rax+rax+00000000h]
0x140003220  cmp     [r8+rcx*2+2], r14w
0x140003226  lea     rcx, [rcx+1]
0x14000322a  jnz     short loc_140003220
0x14000322c  lea     ecx, ds:2[rcx*2]
0x140003233  jmp     short loc_140003241
0x140003235  lea     r8, Format
0x14000323c  mov     ecx, 2
0x140003241  movzx   eax, cs:word_140014331
0x140003248  mov     dword ptr [rsp+480h+EventDescriptor.Level], eax
0x14000324c  mov     rax, cs:off_140018010
0x140003253  mov     [rbp+380h+var_3E0.Ptr], rax
0x140003257  mov     [rbp+380h+var_3B8], ecx
0x14000325a  lea     rcx, _TraceLoggingMetadata
0x140003261  mov     [rbp+380h+var_3C0], r8
0x140003265  mov     [rbp+380h+var_3B4], r14d
0x140003269  mov     dword ptr [rsp+480h+EventDescriptor.Id], 0B000000h
0x140003271  mov     [rsp+480h+EventDescriptor.Keyword], r14
0x140003276  movzx   eax, word ptr [rax]
0x140003279  mov     [rbp+380h+var_3E0.Size], eax
0x14000327c  lea     rax, byte_14001433B
0x140003283  mov     [rbp+380h+var_3D0], rax
0x140003287  lea     rax, _TraceLoggingMetadataEnd
0x14000328e  sub     eax, ecx
0x140003290  mov     dword ptr [rbp+380h+var_3E0.0Ch], 2
0x140003297  mov     [rbp+380h+var_3C8], 0AAh
0x14000329e  mov     [rbp+380h+var_3C4], 1
0x1400032a5  mov     [rsp+480h+applicationUserModelIdLength], eax
0x1400032a9  mov     eax, [rsp+480h+applicationUserModelIdLength]
0x1400032ad  lea     rax, [rbp+380h+var_3E0]
0x1400032b1  mov     [rsp+480h+UserData], rax; UserData
0x1400032b6  mov     [rsp+480h+UserDataCount], 9; UserDataCount
0x1400032be  mov     rcx, cs:RegHandle; RegHandle
0x1400032c5  lea     rdx, [rsp+480h+EventDescriptor]; EventDescriptor
0x1400032ca  xor     r9d, r9d; RelatedActivityId
0x1400032cd  xor     r8d, r8d; ActivityId
0x1400032d0  call    cs:__imp_EventWriteTransfer
  ... truncated ...
```
