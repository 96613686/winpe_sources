# RoutingMgr::CreateChangeAppletIdGroupPolicyEvent(ulong *)

- ea: `0x18002fa10`
- end: `0x18002fc9a`
- name: `?CreateChangeAppletIdGroupPolicyEvent@RoutingMgr@@AEAAJPEAK@Z`
- size: `650`
- prototype: `__int64 __fastcall(RoutingMgr *__hidden this, unsigned int *)`
- caller_count: `3`
- callee_count: `4`
- tags: `authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180032c80`
- `0x18003304c`
- `0x1800332e8`

## callees

- `0x180003324`
- `0x1800049a0`
- `0x18000d4ec`
- `0x18002fa10`

## import_xrefs

- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18002fa5b`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18002fa66`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18002fa5b`
- `api-ms-win-crt-private-l1-1-0!_o_rand` at `0x18002fa66`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002faac`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x18002faac`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002fab8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002fb2c`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002fab8`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x18002fb2c`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002fc03`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18002fc03`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc31`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fad2`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb15`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fb3c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002fc31`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fae5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fb4f`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fae5`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x18002fb4f`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002faf4`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x18002faf4`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002fb0b`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x18002fb0b`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fadd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fc21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fc6c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fadd`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fc21`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x18002fc6c`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002fb47`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002fc57`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002fb47`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18002fc57`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x18002fb70`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x18002fb70`

## string_xrefs

- `0x18002fbc6`: `RoutingMgr::CreateChangeAppletIdGroupPolicyEvent`

## pseudocode

```c
__int64 __fastcall RoutingMgr::CreateChangeAppletIdGroupPolicyEvent(RoutingMgr *this, unsigned int *a2)
{
  int v4; // edi
  unsigned int v5; // edi
  __int64 **v6; // rax
  __int64 *i; // rcx
  int v8; // ebx
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  signed int v11; // eax
  int v12; // ecx
  int v13; // ebx
  int v14; // r8d
  int v15; // r9d
  HANDLE v16; // rax
  void *v17; // rcx
  signed int v18; // eax
  void *v20; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE hObject; // [rsp+48h] [rbp-B8h] BYREF
  WCHAR *v22; // [rsp+50h] [rbp-B0h] BYREF
  const char *v23; // [rsp+58h] [rbp-A8h] BYREF
  const char *v24; // [rsp+60h] [rbp-A0h] BYREF
  _SECURITY_ATTRIBUTES EventAttributes; // [rsp+68h] [rbp-98h] BYREF
  WCHAR Name[264]; // [rsp+80h] [rbp-80h] BYREF

  memset(&EventAttributes, 0, sizeof(EventAttributes));
  hObject = 0;
  v20 = 0;
LABEL_2:
  v4 = rand() << 16;
  v5 = rand() + v4;
  v6 = (__int64 **)*((_QWORD *)this + 43);
  for ( i = *v6; i != (__int64 *)v6; i = (__int64 *)*i )
  {
    if ( *((_DWORD *)i + 41) == v5 )
      goto LABEL_2;
  }
  v8 = StringCchPrintfW(Name, 0x104u, L"Session\\0\\NFC_HCE_ChangeAppletIdGroupPolicy_%d", v5);
  if ( v8 >= 0 )
  {
    v8 = CoImpersonateClient();
    if ( v8 < 0 )
    {
LABEL_8:
      CoRevertToSelf();
      goto LABEL_24;
    }
    if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    {
      LastError = GetLastError();
      CloseHandle(hObject);
      SetLastError(LastError);
    }
    hObject = 0;
    CurrentThread = GetCurrentThread();
    if ( !OpenThreadToken(CurrentThread, 8u, 1, &hObject) )
    {
      v11 = GetLastError();
      v8 = v11;
      if ( v11 > 0 )
        v8 = (unsigned __int16)v11 | 0x80070000;
      goto LABEL_8;
    }
    CoRevertToSelf();
    v20 = 0;
    v13 = BuildSecurityDescriptorForSharingAccess(hObject, 0, 0x100000, &v20);
    if ( v13 >= 0 )
    {
      EventAttributes.lpSecurityDescriptor = v20;
      EventAttributes.nLength = 24;
      EventAttributes.bInheritHandle = 1;
      if ( (unsigned int)dword_18012F048 > 5 )
      {
        v22 = Name;
        v23 = "Creating event";
        v24 = "RoutingMgr::CreateChangeAppletIdGroupPolicyEvent";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v12,
          (unsigned int)&word_18011C86E,
          v14,
          v15,
          (__int64)&v24,
          (__int64)&v23,
          (__int64)&v22);
      }
      v16 = CreateEventW(&EventAttributes, 0, 0, Name);
      v17 = (void *)*((_QWORD *)this + 45);
      *((_QWORD *)this + 45) = v16;
      if ( (unsigned __int64)v17 + 1 > 1 )
        CloseHandle(v17);
      if ( *((_QWORD *)this + 45) )
      {
        v8 = 0;
        *a2 = v5;
      }
      else
      {
        v18 = GetLastError();
        v8 = v18;
        if ( v18 > 0 )
          v8 = (unsigned __int16)v18 | 0x80070000;
      }
    }
    else
    {
      v8 = v13 | 0x10000000;
    }
  }
LABEL_24:
  if ( v20 )
    FreeTransientObjectSecurityDescriptor(v20);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return (unsigned int)v8;
}

```

## disassembly

```asm
0x18002fa10  mov     [rsp-8+arg_10], rbx
0x18002fa15  push    rbp
0x18002fa16  push    rsi
0x18002fa17  push    rdi
0x18002fa18  push    r14
0x18002fa1a  push    r15
0x18002fa1c  lea     rbp, [rsp-1A0h]
0x18002fa24  sub     rsp, 2A0h
0x18002fa2b  mov     rax, cs:__security_cookie
0x18002fa32  xor     rax, rsp
0x18002fa35  mov     [rbp+1C0h+var_30], rax
0x18002fa3c  xor     eax, eax
0x18002fa3e  xorps   xmm0, xmm0
0x18002fa41  movups  xmmword ptr [rsp+2C0h+EventAttributes.nLength], xmm0
0x18002fa46  mov     qword ptr [rsp+2C0h+EventAttributes.bInheritHandle], rax
0x18002fa4b  mov     r15, rdx
0x18002fa4e  mov     [rsp+2C0h+hObject], rax
0x18002fa53  mov     r14, rcx
0x18002fa56  mov     [rsp+2C0h+var_280], rax
0x18002fa5b  call    cs:__imp_rand
0x18002fa61  mov     edi, eax
0x18002fa63  shl     edi, 10h
0x18002fa66  call    cs:__imp_rand
0x18002fa6c  add     edi, eax
0x18002fa6e  mov     rax, [r14+158h]
0x18002fa75  mov     rcx, [rax]
0x18002fa78  cmp     rcx, rax
0x18002fa7b  jz      short loc_18002FA8A
0x18002fa7d  cmp     [rcx+0A4h], edi
0x18002fa83  jz      short loc_18002FA5B
0x18002fa85  mov     rcx, [rcx]
0x18002fa88  jmp     short loc_18002FA78
0x18002fa8a  mov     r9d, edi
0x18002fa8d  lea     r8, aSession0NfcHce; "Session\\0\\NFC_HCE_ChangeAppletIdGroup"...
0x18002fa94  mov     edx, 104h; unsigned __int64
0x18002fa99  lea     rcx, [rbp+1C0h+Name]; unsigned __int16 *
0x18002fa9d  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x18002faa2  mov     ebx, eax
0x18002faa4  test    eax, eax
0x18002faa6  js      loc_18002FC4D
0x18002faac  call    cs:__imp_CoImpersonateClient
0x18002fab2  mov     ebx, eax
0x18002fab4  test    eax, eax
0x18002fab6  jns     short loc_18002FAC3
0x18002fab8  call    cs:__imp_CoRevertToSelf
0x18002fabe  jmp     loc_18002FC4D
0x18002fac3  mov     rsi, [rsp+2C0h+hObject]
0x18002fac8  lea     rax, [rsi-1]
0x18002facc  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x18002fad0  ja      short loc_18002FAEB
0x18002fad2  call    cs:__imp_GetLastError
0x18002fad8  mov     rcx, rsi; hObject
0x18002fadb  mov     ebx, eax
0x18002fadd  call    cs:__imp_CloseHandle
0x18002fae3  mov     ecx, ebx; dwErrCode
0x18002fae5  call    cs:__imp_SetLastError
0x18002faeb  mov     [rsp+2C0h+hObject], 0
0x18002faf4  call    cs:__imp_GetCurrentThread
0x18002fafa  mov     edx, 8; DesiredAccess
0x18002faff  lea     r9, [rsp+2C0h+hObject]; TokenHandle
0x18002fb04  mov     rcx, rax; ThreadHandle
0x18002fb07  lea     r8d, [rdx-7]; OpenAsSelf
0x18002fb0b  call    cs:__imp_OpenThreadToken
0x18002fb11  test    eax, eax
0x18002fb13  jnz     short loc_18002FB2C
0x18002fb15  call    cs:__imp_GetLastError
0x18002fb1b  mov     ebx, eax
0x18002fb1d  test    eax, eax
0x18002fb1f  jle     short loc_18002FAB8
0x18002fb21  movzx   ebx, ax
0x18002fb24  or      ebx, 80070000h
0x18002fb2a  jmp     short loc_18002FAB8
0x18002fb2c  call    cs:__imp_CoRevertToSelf
0x18002fb32  mov     rsi, [rsp+2C0h+var_280]
0x18002fb37  test    rsi, rsi
0x18002fb3a  jz      short loc_18002FB55
0x18002fb3c  call    cs:__imp_GetLastError
0x18002fb42  mov     rcx, rsi
0x18002fb45  mov     ebx, eax
0x18002fb47  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18002fb4d  mov     ecx, ebx; dwErrCode
0x18002fb4f  call    cs:__imp_SetLastError
0x18002fb55  mov     rcx, [rsp+2C0h+hObject]
0x18002fb5a  lea     r9, [rsp+2C0h+var_280]
0x18002fb5f  xor     edx, edx
0x18002fb61  mov     [rsp+2C0h+var_280], 0
0x18002fb6a  mov     r8d, 100000h
0x18002fb70  call    cs:__imp_BuildSecurityDescriptorForSharingAccess
0x18002fb76  mov     ebx, eax
0x18002fb78  test    eax, eax
0x18002fb7a  jns     short loc_18002FB85
0x18002fb7c  bts     ebx, 1Ch
0x18002fb80  jmp     loc_18002FC4D
0x18002fb85  mov     rax, [rsp+2C0h+var_280]
0x18002fb8a  mov     [rsp+2C0h+EventAttributes.lpSecurityDescriptor], rax
0x18002fb8f  mov     eax, cs:dword_18012F048
0x18002fb95  mov     [rsp+2C0h+EventAttributes.nLength], 18h
0x18002fb9d  mov     [rsp+2C0h+EventAttributes.bInheritHandle], 1
0x18002fba5  cmp     eax, 5
0x18002fba8  jbe     short loc_18002FBF5
0x18002fbaa  lea     rax, [rbp+1C0h+Name]
0x18002fbae  mov     [rsp+2C0h+var_270], rax
0x18002fbb3  lea     rdx, word_18011C86E
0x18002fbba  lea     rax, aCreatingEvent_0; "Creating event"
0x18002fbc1  mov     [rsp+2C0h+var_268], rax
0x18002fbc6  lea     rax, aRoutingmgrCrea; "RoutingMgr::CreateChangeAppletIdGroupPo"...
0x18002fbcd  mov     [rsp+2C0h+var_260], rax
0x18002fbd2  lea     rax, [rsp+2C0h+var_270]
0x18002fbd7  mov     [rsp+2C0h+var_290], rax
0x18002fbdc  lea     rax, [rsp+2C0h+var_268]
0x18002fbe1  mov     [rsp+2C0h+var_298], rax
0x18002fbe6  lea     rax, [rsp+2C0h+var_260]
0x18002fbeb  mov     [rsp+2C0h+var_2A0], rax
0x18002fbf0  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x18002fbf5  lea     r9, [rbp+1C0h+Name]; lpName
0x18002fbf9  xor     r8d, r8d; bInitialState
0x18002fbfc  xor     edx, edx; bManualReset
0x18002fbfe  lea     rcx, [rsp+2C0h+EventAttributes]; lpEventAttributes
0x18002fc03  call    cs:__imp_CreateEventW
0x18002fc09  mov     rcx, [r14+168h]; hObject
0x18002fc10  mov     [r14+168h], rax
0x18002fc17  lea     rax, [rcx+1]
0x18002fc1b  cmp     rax, 1
0x18002fc1f  jbe     short loc_18002FC27
0x18002fc21  call    cs:__imp_CloseHandle
0x18002fc27  cmp     qword ptr [r14+168h], 0
0x18002fc2f  jnz     short loc_18002FC48
0x18002fc31  call    cs:__imp_GetLastError
0x18002fc37  mov     ebx, eax
0x18002fc39  test    eax, eax
0x18002fc3b  jle     short loc_18002FC4D
0x18002fc3d  movzx   ebx, ax
0x18002fc40  or      ebx, 80070000h
0x18002fc46  jmp     short loc_18002FC4D
0x18002fc48  xor     ebx, ebx
0x18002fc4a  mov     [r15], edi
0x18002fc4d  mov     rcx, [rsp+2C0h+var_280]
0x18002fc52  test    rcx, rcx
0x18002fc55  jz      short loc_18002FC5D
0x18002fc57  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x18002fc5d  mov     rcx, [rsp+2C0h+hObject]; hObject
0x18002fc62  lea     rdx, [rcx-1]
0x18002fc66  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x18002fc6a  ja      short loc_18002FC72
0x18002fc6c  call    cs:__imp_CloseHandle
0x18002fc72  mov     eax, ebx
0x18002fc74  mov     rcx, [rbp+1C0h+var_30]
0x18002fc7b  xor     rcx, rsp; StackCookie
0x18002fc7e  call    __security_check_cookie
0x18002fc83  mov     rbx, [rsp+2C0h+arg_10]
0x18002fc8b  add     rsp, 2A0h
0x18002fc92  pop     r15
0x18002fc94  pop     r14
0x18002fc96  pop     rdi
0x18002fc97  pop     rsi
0x18002fc98  pop     rbp
0x18002fc99  retn
```
