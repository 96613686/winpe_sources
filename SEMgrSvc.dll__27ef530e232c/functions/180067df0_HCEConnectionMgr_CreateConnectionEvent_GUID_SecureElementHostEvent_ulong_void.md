# HCEConnectionMgr::CreateConnectionEvent(_GUID *,SecureElementHostEvent,ulong,void * *)

- ea: `0x180067df0`
- end: `0x180068085`
- name: `?CreateConnectionEvent@HCEConnectionMgr@@EEAAJPEAU_GUID@@W4SecureElementHostEvent@@KPEAPEAX@Z`
- size: `661`
- prototype: ``
- caller_count: `0`
- callee_count: `4`
- tags: `authz_impersonation, loader_planting, broker_com_uri`

## callees

- `0x180003324`
- `0x1800049a0`
- `0x18000d4ec`
- `0x180067df0`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180067ecb`
- `api-ms-win-core-com-l1-1-0!CoImpersonateClient` at `0x180067ecb`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180067ed7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180067f4a`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180067ed7`
- `api-ms-win-core-com-l1-1-0!CoRevertToSelf` at `0x180067f4a`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006800e`
- `api-ms-win-core-synch-l1-1-0!CreateEventW` at `0x18006800e`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068019`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067ef0`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f33`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180067f59`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180068019`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067f03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067f6c`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067f03`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180067f6c`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180067f11`
- `api-ms-win-core-processthreads-l1-1-0!GetCurrentThread` at `0x180067f11`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180067f29`
- `api-ms-win-core-processthreads-l1-1-0!OpenThreadToken` at `0x180067f29`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067efb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068053`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180067efb`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x180068053`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180067f64`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18006803f`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x180067f64`
- `api-ms-win-security-accesshlpr-l1-1-0!FreeTransientObjectSecurityDescriptor` at `0x18006803f`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x180067f8a`
- `api-ms-win-security-accesshlpr-l1-1-0!BuildSecurityDescriptorForSharingAccess` at `0x180067f8a`

## string_xrefs

- `0x180067fd6`: `HCEConnectionMgr::CreateConnectionEvent`

## pseudocode

```c
__int64 __fastcall HCEConnectionMgr::CreateConnectionEvent(__int64 a1, int *a2, unsigned int a3, int a4, _QWORD *a5)
{
  int v5; // ecx
  __int64 v7; // r9
  int v8; // r8d
  int v9; // r10d
  int v10; // r11d
  int v11; // ebx
  int v12; // edi
  int v13; // esi
  int v14; // r14d
  int v15; // ebx
  DWORD LastError; // ebx
  HANDLE CurrentThread; // rax
  signed int v18; // eax
  int v19; // ecx
  int v20; // ebx
  int v21; // r8d
  int v22; // r9d
  HANDLE v23; // rax
  signed int v24; // eax
  int v26; // [rsp+28h] [rbp-D8h]
  int v27; // [rsp+68h] [rbp-98h]
  int v28; // [rsp+78h] [rbp-88h]
  void *v29; // [rsp+80h] [rbp-80h] BYREF
  HANDLE hObject; // [rsp+88h] [rbp-78h] BYREF
  WCHAR *v31; // [rsp+90h] [rbp-70h] BYREF
  const char *v32; // [rsp+98h] [rbp-68h] BYREF
  const char *v33; // [rsp+A0h] [rbp-60h] BYREF
  struct _SECURITY_ATTRIBUTES EventAttributes; // [rsp+A8h] [rbp-58h] BYREF
  WCHAR Name[264]; // [rsp+C0h] [rbp-40h] BYREF

  v5 = *((unsigned __int8 *)a2 + 14);
  hObject = 0;
  v7 = a3;
  v8 = *((unsigned __int8 *)a2 + 12);
  v9 = *((unsigned __int8 *)a2 + 11);
  v10 = *((unsigned __int8 *)a2 + 10);
  v11 = *((unsigned __int8 *)a2 + 9);
  v12 = *((unsigned __int8 *)a2 + 8);
  v13 = *((unsigned __int16 *)a2 + 3);
  v14 = *((unsigned __int16 *)a2 + 2);
  v29 = 0;
  v28 = *((unsigned __int8 *)a2 + 15);
  v27 = *((unsigned __int8 *)a2 + 13);
  v26 = *a2;
  memset(&EventAttributes, 0, sizeof(EventAttributes));
  v15 = StringCchPrintfW(
          Name,
          0x104u,
          L"Session\\0\\NFC_HCE_%d_%d_%08X-%04hX-%04hX-%02X%02X-%02X%02X%02X%02X%02X%02X",
          v7,
          a4,
          v26,
          v14,
          v13,
          v12,
          v11,
          v10,
          v9,
          v8,
          v27,
          v5,
          v28);
  if ( v15 >= 0 )
  {
    v15 = CoImpersonateClient();
    if ( v15 < 0 )
    {
LABEL_3:
      CoRevertToSelf();
      goto LABEL_17;
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
      v18 = GetLastError();
      v15 = v18;
      if ( v18 > 0 )
        v15 = (unsigned __int16)v18 | 0x80070000;
      goto LABEL_3;
    }
    CoRevertToSelf();
    v29 = 0;
    v20 = BuildSecurityDescriptorForSharingAccess(hObject, 0, 0x100000, &v29);
    if ( v20 >= 0 )
    {
      EventAttributes.lpSecurityDescriptor = v29;
      EventAttributes.nLength = 24;
      EventAttributes.bInheritHandle = 1;
      if ( (unsigned int)dword_18012F048 > 5 )
      {
        v31 = Name;
        v32 = "Creating event.";
        v33 = "HCEConnectionMgr::CreateConnectionEvent";
        _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<unsigned short>>(
          v19,
          (unsigned int)word_18011CFF2,
          v21,
          v22,
          (__int64)&v33,
          (__int64)&v32,
          (__int64)&v31);
      }
      v23 = CreateEventW(&EventAttributes, 0, 0, Name);
      if ( v23 )
      {
        v15 = 0;
        *a5 = v23;
      }
      else
      {
        v24 = GetLastError();
        v15 = v24;
        if ( v24 > 0 )
          v15 = (unsigned __int16)v24 | 0x80070000;
      }
    }
    else
    {
      v15 = v20 | 0x10000000;
    }
  }
LABEL_17:
  if ( v29 )
    FreeTransientObjectSecurityDescriptor(v29);
  if ( (char *)hObject - 1 <= (char *)0xFFFFFFFFFFFFFFFDLL )
    CloseHandle(hObject);
  return (unsigned int)v15;
}

```

## disassembly

```asm
0x180067df0  mov     [rsp-8+arg_0], rbx
0x180067df5  push    rbp
0x180067df6  push    rsi
0x180067df7  push    rdi
0x180067df8  push    r12
0x180067dfa  push    r13
0x180067dfc  push    r14
0x180067dfe  push    r15
0x180067e00  lea     rbp, [rsp-1E0h]
0x180067e08  sub     rsp, 2E0h
0x180067e0f  mov     rax, cs:__security_cookie
0x180067e16  xor     rax, rsp
0x180067e19  mov     [rbp+210h+var_40], rax
0x180067e20  movzx   ecx, byte ptr [rdx+0Eh]
0x180067e24  mov     r15, rdx
0x180067e27  mov     r13, [rbp+210h+arg_20]
0x180067e2e  xor     eax, eax
0x180067e30  mov     qword ptr [rbp+210h+EventAttributes.bInheritHandle], rax
0x180067e34  mov     r12d, r9d
0x180067e37  mov     [rbp+210h+hObject], rax
0x180067e3b  mov     r9d, r8d
0x180067e3e  movzx   r8d, byte ptr [r15+0Ch]
0x180067e43  xorps   xmm0, xmm0
0x180067e46  movzx   r10d, byte ptr [r15+0Bh]
0x180067e4b  movzx   r11d, byte ptr [r15+0Ah]
0x180067e50  movzx   ebx, byte ptr [r15+9]
0x180067e55  movzx   edi, byte ptr [r15+8]
0x180067e5a  movzx   esi, word ptr [r15+6]
0x180067e5f  movzx   r14d, word ptr [r15+4]
0x180067e64  mov     [rbp+210h+var_290], rax
0x180067e68  movzx   eax, byte ptr [rdx+0Fh]
0x180067e6c  movzx   edx, byte ptr [rdx+0Dh]
0x180067e70  mov     [rsp+310h+var_298], eax
0x180067e74  mov     eax, [r15]
0x180067e77  mov     [rsp+310h+var_2A0], ecx
0x180067e7b  lea     rcx, [rbp+210h+Name]; unsigned __int16 *
0x180067e7f  mov     [rsp+310h+var_2A8], edx
0x180067e83  mov     edx, 104h; unsigned __int64
0x180067e88  mov     [rsp+310h+var_2B0], r8d
0x180067e8d  lea     r8, aSession0NfcHce_0; "Session\\0\\NFC_HCE_%d_%d_%08X-%04hX-%0"...
0x180067e94  mov     [rsp+310h+var_2B8], r10d
0x180067e99  mov     [rsp+310h+var_2C0], r11d
0x180067e9e  mov     [rsp+310h+var_2C8], ebx
0x180067ea2  mov     [rsp+310h+var_2D0], edi
0x180067ea6  mov     [rsp+310h+var_2D8], esi
0x180067eaa  mov     dword ptr [rsp+310h+var_2E0], r14d
0x180067eaf  mov     dword ptr [rsp+310h+var_2E8], eax
0x180067eb3  mov     dword ptr [rsp+310h+var_2F0], r12d
0x180067eb8  movups  xmmword ptr [rbp+210h+EventAttributes.nLength], xmm0
0x180067ebc  call    ?StringCchPrintfW@@YAJPEAG_KPEBGZZ; StringCchPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x180067ec1  mov     ebx, eax
0x180067ec3  test    eax, eax
0x180067ec5  js      loc_180068036
0x180067ecb  call    cs:__imp_CoImpersonateClient
0x180067ed1  mov     ebx, eax
0x180067ed3  test    eax, eax
0x180067ed5  jns     short loc_180067EE2
0x180067ed7  call    cs:__imp_CoRevertToSelf
0x180067edd  jmp     loc_180068036
0x180067ee2  mov     rdi, [rbp+210h+hObject]
0x180067ee6  lea     rax, [rdi-1]
0x180067eea  cmp     rax, 0FFFFFFFFFFFFFFFDh
0x180067eee  ja      short loc_180067F09
0x180067ef0  call    cs:__imp_GetLastError
0x180067ef6  mov     rcx, rdi; hObject
0x180067ef9  mov     ebx, eax
0x180067efb  call    cs:__imp_CloseHandle
0x180067f01  mov     ecx, ebx; dwErrCode
0x180067f03  call    cs:__imp_SetLastError
0x180067f09  mov     [rbp+210h+hObject], 0
0x180067f11  call    cs:__imp_GetCurrentThread
0x180067f17  mov     esi, 1
0x180067f1c  lea     r9, [rbp+210h+hObject]; TokenHandle
0x180067f20  mov     r8d, esi; OpenAsSelf
0x180067f23  mov     rcx, rax; ThreadHandle
0x180067f26  lea     edx, [rsi+7]; DesiredAccess
0x180067f29  call    cs:__imp_OpenThreadToken
0x180067f2f  test    eax, eax
0x180067f31  jnz     short loc_180067F4A
0x180067f33  call    cs:__imp_GetLastError
0x180067f39  mov     ebx, eax
0x180067f3b  test    eax, eax
0x180067f3d  jle     short loc_180067ED7
0x180067f3f  movzx   ebx, ax
0x180067f42  or      ebx, 80070000h
0x180067f48  jmp     short loc_180067ED7
0x180067f4a  call    cs:__imp_CoRevertToSelf
0x180067f50  mov     rdi, [rbp+210h+var_290]
0x180067f54  test    rdi, rdi
0x180067f57  jz      short loc_180067F72
0x180067f59  call    cs:__imp_GetLastError
0x180067f5f  mov     rcx, rdi
0x180067f62  mov     ebx, eax
0x180067f64  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180067f6a  mov     ecx, ebx; dwErrCode
0x180067f6c  call    cs:__imp_SetLastError
0x180067f72  mov     rcx, [rbp+210h+hObject]
0x180067f76  lea     r9, [rbp+210h+var_290]
0x180067f7a  xor     edx, edx
0x180067f7c  mov     [rbp+210h+var_290], 0
0x180067f84  mov     r8d, 100000h
0x180067f8a  call    cs:__imp_BuildSecurityDescriptorForSharingAccess
0x180067f90  mov     ebx, eax
0x180067f92  test    eax, eax
0x180067f94  jns     short loc_180067F9F
0x180067f96  bts     ebx, 1Ch
0x180067f9a  jmp     loc_180068036
0x180067f9f  mov     rax, [rbp+210h+var_290]
0x180067fa3  mov     [rbp+210h+EventAttributes.lpSecurityDescriptor], rax
0x180067fa7  mov     eax, cs:dword_18012F048
0x180067fad  mov     [rbp+210h+EventAttributes.nLength], 18h
0x180067fb4  mov     [rbp+210h+EventAttributes.bInheritHandle], esi
0x180067fb7  cmp     eax, 5
0x180067fba  jbe     short loc_180068001
0x180067fbc  lea     rax, [rbp+210h+Name]
0x180067fc0  mov     [rbp+210h+var_280], rax
0x180067fc4  lea     rdx, word_18011CFF2
0x180067fcb  lea     rax, aCreatingEvent; "Creating event."
0x180067fd2  mov     [rbp+210h+var_278], rax
0x180067fd6  lea     rax, aHceconnectionm; "HCEConnectionMgr::CreateConnectionEvent"
0x180067fdd  mov     [rbp+210h+var_270], rax
0x180067fe1  lea     rax, [rbp+210h+var_280]
0x180067fe5  mov     [rsp+310h+var_2E0], rax
0x180067fea  lea     rax, [rbp+210h+var_278]
0x180067fee  mov     [rsp+310h+var_2E8], rax
0x180067ff3  lea     rax, [rbp+210h+var_270]
0x180067ff7  mov     [rsp+310h+var_2F0], rax
0x180067ffc  call    ??$Write@U?$_tlgWrapSz@D@@U1@U?$_tlgWrapSz@G@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapSz@D@@3AEBU?$_tlgWrapSz@G@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapSz<char>,_tlgWrapSz<char>,_tlgWrapSz<ushort>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapSz<char> const &,_tlgWrapSz<char> const &,_tlgWrapSz<ushort> const &)
0x180068001  lea     r9, [rbp+210h+Name]; lpName
0x180068005  xor     r8d, r8d; bInitialState
0x180068008  xor     edx, edx; bManualReset
0x18006800a  lea     rcx, [rbp+210h+EventAttributes]; lpEventAttributes
0x18006800e  call    cs:__imp_CreateEventW
0x180068014  test    rax, rax
0x180068017  jnz     short loc_180068030
0x180068019  call    cs:__imp_GetLastError
0x18006801f  mov     ebx, eax
0x180068021  test    eax, eax
0x180068023  jle     short loc_180068036
0x180068025  movzx   ebx, ax
0x180068028  or      ebx, 80070000h
0x18006802e  jmp     short loc_180068036
0x180068030  xor     ebx, ebx
0x180068032  mov     [r13+0], rax
0x180068036  mov     rcx, [rbp+210h+var_290]
0x18006803a  test    rcx, rcx
0x18006803d  jz      short loc_180068045
0x18006803f  call    cs:__imp_FreeTransientObjectSecurityDescriptor
0x180068045  mov     rcx, [rbp+210h+hObject]; hObject
0x180068049  lea     rdx, [rcx-1]
0x18006804d  cmp     rdx, 0FFFFFFFFFFFFFFFDh
0x180068051  ja      short loc_180068059
0x180068053  call    cs:__imp_CloseHandle
0x180068059  mov     eax, ebx
0x18006805b  mov     rcx, [rbp+210h+var_40]
0x180068062  xor     rcx, rsp; StackCookie
0x180068065  call    __security_check_cookie
0x18006806a  mov     rbx, [rsp+310h+arg_0]
0x180068072  add     rsp, 2E0h
0x180068079  pop     r15
0x18006807b  pop     r14
0x18006807d  pop     r13
0x18006807f  pop     r12
0x180068081  pop     rdi
0x180068082  pop     rsi
0x180068083  pop     rbp
0x180068084  retn
```
