# CRuntimeBroker::ReadBrokerAumid(_RTL_RUN_ONCE *,void *,void * *)

- ea: `0x140007a90`
- end: `0x140007c60`
- name: `?ReadBrokerAumid@CRuntimeBroker@@SAHPEAT_RTL_RUN_ONCE@@PEAXPEAPEAX@Z`
- size: `464`
- prototype: `BOOL __stdcall(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140007a90`
- `0x140008c80`

## import_xrefs

- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140007c23`
- `api-ms-win-eventing-provider-l1-1-0!EventWriteTransfer` at `0x140007c23`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140007b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsCreateString` at `0x140007b2d`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140007b0b`
- `api-ms-win-core-winrt-string-l1-1-0!WindowsDeleteString` at `0x140007b0b`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x140007ac5`
- `api-ms-win-appmodel-runtime-l1-1-1!GetApplicationUserModelIdFromToken` at `0x140007ac5`

## pseudocode

```c
__int64 __fastcall CRuntimeBroker::ReadBrokerAumid(PINIT_ONCE InitOnce, PVOID Parameter, PVOID *Context)
{
  LONG ApplicationUserModelIdFromToken; // eax
  int String; // ecx
  unsigned __int64 v5; // rbx
  UINT32 applicationUserModelIdLength; // [rsp+30h] [rbp-178h] BYREF
  _DWORD v8[3]; // [rsp+34h] [rbp-174h] BYREF
  EVENT_DESCRIPTOR EventDescriptor; // [rsp+40h] [rbp-168h] BYREF
  struct _EVENT_DATA_DESCRIPTOR UserData; // [rsp+50h] [rbp-158h] BYREF
  int *v11; // [rsp+60h] [rbp-148h]
  int v12; // [rsp+68h] [rbp-140h]
  int v13; // [rsp+6Ch] [rbp-13Ch]
  _DWORD *v14; // [rsp+70h] [rbp-138h]
  __int64 v15; // [rsp+78h] [rbp-130h]
  WCHAR applicationUserModelId[136]; // [rsp+80h] [rbp-128h] BYREF

  applicationUserModelIdLength = 130;
  ApplicationUserModelIdFromToken = GetApplicationUserModelIdFromToken(
                                      (HANDLE)0xFFFFFFFFFFFFFFFCLL,
                                      &applicationUserModelIdLength,
                                      applicationUserModelId);
  String = ApplicationUserModelIdFromToken;
  if ( ApplicationUserModelIdFromToken )
  {
    if ( ApplicationUserModelIdFromToken == 15703 )
      return 1;
    if ( ApplicationUserModelIdFromToken > 0 )
      String = (unsigned __int16)ApplicationUserModelIdFromToken | 0x80070000;
  }
  else
  {
    v5 = -1;
    do
      ++v5;
    while ( applicationUserModelId[v5] );
    if ( v5 > 0xFFFFFFFF )
    {
      String = -2147024362;
    }
    else
    {
      WindowsDeleteString(CRuntimeBroker::s_brokerAumid);
      CRuntimeBroker::s_brokerAumid = 0;
      String = WindowsCreateString(applicationUserModelId, v5, &CRuntimeBroker::s_brokerAumid);
    }
  }
  if ( String >= 0 )
    return 1;
  if ( (unsigned int)dword_140018008 > 2 )
  {
    v8[0] = String;
    v14 = v8;
    *(_DWORD *)&EventDescriptor.Level = 2;
    UserData.Ptr = (ULONGLONG)off_140018010;
    v15 = 4;
    *(_DWORD *)&EventDescriptor.Id = 184549376;
    EventDescriptor.Keyword = 0;
    UserData.Size = (unsigned __int16)*off_140018010;
    v11 = &dword_1400142B4;
    UserData.Reserved = 2;
    v12 = 34;
    v13 = 1;
    v8[1] = (unsigned int)&TraceLoggingMetadataEnd - (unsigned int)&TraceLoggingMetadata;
    EventWriteTransfer(RegHandle, &EventDescriptor, 0, 0, 3u, &UserData);
  }
  return 0;
}

```

## disassembly

```asm
0x140007a90  sub     rsp, 1A8h
0x140007a97  mov     rax, cs:__security_cookie
0x140007a9e  xor     rax, rsp
0x140007aa1  mov     [rsp+1A8h+var_18], rax
0x140007aa9  lea     r8, [rsp+1A8h+applicationUserModelId]; applicationUserModelId
0x140007ab1  mov     [rsp+1A8h+applicationUserModelIdLength], 82h
0x140007ab9  lea     rdx, [rsp+1A8h+applicationUserModelIdLength]; applicationUserModelIdLength
0x140007abe  mov     rcx, 0FFFFFFFFFFFFFFFCh; token
0x140007ac5  call    cs:__imp_GetApplicationUserModelIdFromToken
0x140007acb  mov     ecx, eax
0x140007acd  test    eax, eax
0x140007acf  jnz     short loc_140007B4E
0x140007ad1  mov     [rsp+1A8h+var_8], rbx
0x140007ad9  lea     rax, [rsp+1A8h+applicationUserModelId]
0x140007ae1  mov     rbx, 0FFFFFFFFFFFFFFFFh
0x140007ae8  nop     dword ptr [rax+rax+00000000h]
0x140007af0  inc     rbx
0x140007af3  cmp     word ptr [rax+rbx*2], 0
0x140007af8  jnz     short loc_140007AF0
0x140007afa  mov     eax, 0FFFFFFFFh
0x140007aff  cmp     rbx, rax
0x140007b02  ja      short loc_140007B3F
0x140007b04  mov     rcx, cs:?s_brokerAumid@CRuntimeBroker@@2VHString@Wrappers@WRL@Microsoft@@A; string
0x140007b0b  call    cs:__imp_WindowsDeleteString
0x140007b11  mov     edx, ebx; length
0x140007b13  mov     cs:?s_brokerAumid@CRuntimeBroker@@2VHString@Wrappers@WRL@Microsoft@@A, 0; Microsoft::WRL::Wrappers::HString CRuntimeBroker::s_brokerAumid
0x140007b1e  lea     r8, ?s_brokerAumid@CRuntimeBroker@@2VHString@Wrappers@WRL@Microsoft@@A; string
0x140007b25  lea     rcx, [rsp+1A8h+applicationUserModelId]; sourceString
0x140007b2d  call    cs:__imp_WindowsCreateString
0x140007b33  mov     rbx, [rsp+1A8h+var_8]
0x140007b3b  mov     ecx, eax
0x140007b3d  jmp     short loc_140007B66
0x140007b3f  mov     rbx, [rsp+1A8h+var_8]
0x140007b47  mov     ecx, 80070216h
0x140007b4c  jmp     short loc_140007B66
0x140007b4e  cmp     eax, 3D57h
0x140007b53  jz      loc_140007C43
0x140007b59  test    eax, eax
0x140007b5b  jle     short loc_140007B66
0x140007b5d  movzx   ecx, ax
0x140007b60  or      ecx, 80070000h
0x140007b66  test    ecx, ecx
0x140007b68  jns     loc_140007C43
0x140007b6e  mov     eax, cs:dword_140018008
0x140007b74  cmp     eax, 2
0x140007b77  jbe     loc_140007C29
0x140007b7d  mov     [rsp+1A8h+var_174], ecx
0x140007b81  lea     rax, [rsp+1A8h+var_174]
0x140007b86  mov     [rsp+1A8h+var_138], rax
0x140007b8b  lea     rcx, _TraceLoggingMetadata
0x140007b92  movzx   eax, cs:word_1400142AA
0x140007b99  lea     rdx, [rsp+1A8h+EventDescriptor]; EventDescriptor
0x140007b9e  mov     dword ptr [rsp+1A8h+EventDescriptor.Level], eax
0x140007ba2  xor     r9d, r9d; RelatedActivityId
0x140007ba5  mov     rax, cs:off_140018010
0x140007bac  xor     r8d, r8d; ActivityId
0x140007baf  mov     [rsp+1A8h+var_158.Ptr], rax
0x140007bb4  mov     [rsp+1A8h+var_130], 4
0x140007bbd  mov     dword ptr [rsp+1A8h+EventDescriptor.Id], 0B000000h
0x140007bc5  mov     [rsp+1A8h+EventDescriptor.Keyword], 0
0x140007bce  movzx   eax, word ptr [rax]
0x140007bd1  mov     [rsp+1A8h+var_158.Size], eax
0x140007bd5  lea     rax, dword_1400142B4
0x140007bdc  mov     [rsp+1A8h+var_148], rax
0x140007be1  lea     rax, _TraceLoggingMetadataEnd
0x140007be8  sub     eax, ecx
0x140007bea  mov     dword ptr [rsp+1A8h+var_158.0Ch], 2
0x140007bf2  mov     [rsp+1A8h+var_140], 22h ; '"'
0x140007bfa  mov     [rsp+1A8h+var_13C], 1
0x140007c02  mov     [rsp+1A8h+var_170], eax
0x140007c06  mov     eax, [rsp+1A8h+var_170]
0x140007c0a  mov     rcx, cs:RegHandle; RegHandle
0x140007c11  lea     rax, [rsp+1A8h+var_158]
0x140007c16  mov     [rsp+1A8h+UserData], rax; UserData
0x140007c1b  mov     [rsp+1A8h+UserDataCount], 3; UserDataCount
0x140007c23  call    cs:__imp_EventWriteTransfer
0x140007c29  xor     eax, eax
0x140007c2b  mov     rcx, [rsp+1A8h+var_18]
0x140007c33  xor     rcx, rsp; StackCookie
0x140007c36  call    __security_check_cookie
0x140007c3b  add     rsp, 1A8h
0x140007c42  retn
0x140007c43  mov     eax, 1
0x140007c48  mov     rcx, [rsp+1A8h+var_18]
0x140007c50  xor     rcx, rsp; StackCookie
0x140007c53  call    __security_check_cookie
0x140007c58  add     rsp, 1A8h
0x140007c5f  retn
```
