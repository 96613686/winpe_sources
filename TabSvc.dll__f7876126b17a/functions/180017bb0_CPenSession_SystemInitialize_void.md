# CPenSession::SystemInitialize(void)

- ea: `0x180017bb0`
- end: `0x180017dd2`
- name: `?SystemInitialize@CPenSession@@QEAAHXZ`
- size: `546`
- prototype: `__int64 __fastcall(CPenSession *__hidden this)`
- caller_count: `2`
- callee_count: `5`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001506c`
- `0x1800169d0`

## callees

- `0x1800010f8`
- `0x180002940`
- `0x180015630`
- `0x180017bb0`
- `0x18002b404`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d70`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017c7c`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017cf6`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180017d70`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017d13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017d89`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017c9d`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017d13`
- `api-ms-win-core-heap-l2-1-0!LocalFree` at `0x180017d89`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017c44`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017cc4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017d3a`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017c44`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017cc4`
- `api-ms-win-security-sddl-l1-1-0!ConvertStringSecurityDescriptorToSecurityDescriptorW` at `0x180017d3a`

## string_xrefs

- `0x180017be5`: `PENSERVICE_CPenSession::SystemInitialize`
- `0x180017da5`: `PENSERVICE_CPenSession::SystemInitialize`

## pseudocode

```c
_BOOL8 __fastcall CPenSession::SystemInitialize(CPenSession *this)
{
  signed int v2; // ebx
  __int64 v3; // rcx
  __int64 v4; // r8
  void *EventInSession; // rax
  signed int LastError; // eax
  __int64 v7; // r8
  void *v8; // rax
  signed int v9; // eax
  __int64 v10; // r8
  void *v11; // rax
  signed int v12; // eax
  int v14; // [rsp+20h] [rbp-18h]
  PSECURITY_DESCRIPTOR SecurityDescriptor; // [rsp+60h] [rbp+28h] BYREF

  v2 = 0;
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      13,
      (unsigned int)WPP_c659a2668e88300a995919efad269855_Traceguids,
      (unsigned int)"PENSERVICE_CPenSession::SystemInitialize",
      *((_DWORD *)this + 1));
  if ( (unsigned int)dword_1800411A8 > 5 && (unsigned __int8)tlgKeywordOn(&dword_1800411A8, 0x4000000) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(
      v3,
      (int)&byte_18003B11F);
  if ( !*((_QWORD *)this + 4) )
  {
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:SYG:SYD:(A;;0x1F0003;;;SY)",
            1u,
            &SecurityDescriptor,
            0) )
      goto LABEL_9;
    EventInSession = CreateEventInSession(
                       *((_DWORD *)this + 1),
                       L"{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-request2",
                       v4,
                       0,
                       v14,
                       SecurityDescriptor);
    *((_QWORD *)this + 4) = EventInSession;
    if ( !EventInSession )
    {
      LastError = GetLastError();
      v2 = LastError;
      if ( LastError > 0 )
        v2 = (unsigned __int16)LastError | 0x80070000;
      if ( v2 < 0 )
        goto LABEL_29;
    }
    LocalFree(SecurityDescriptor);
  }
  if ( !*((_QWORD *)this + 7) )
  {
    SecurityDescriptor = 0;
    if ( !ConvertStringSecurityDescriptorToSecurityDescriptorW(
            L"O:SYG:SYD:(A;;0x1F0003;;;SY)",
            1u,
            &SecurityDescriptor,
            0) )
      goto LABEL_9;
    v8 = CreateEventInSession(
           *((_DWORD *)this + 1),
           L"{773F1B9A-35B9-4E95-83A0-A210F2DE3B37}-sdl",
           v7,
           0,
           v14,
           SecurityDescriptor);
    *((_QWORD *)this + 7) = v8;
    if ( v8 )
    {
      v2 = 0;
    }
    else
    {
      v9 = GetLastError();
      v2 = v9;
      if ( v9 > 0 )
        v2 = (unsigned __int16)v9 | 0x80070000;
      if ( v2 < 0 )
        goto LABEL_29;
    }
    LocalFree(SecurityDescriptor);
  }
  if ( !*((_QWORD *)this + 5) )
  {
    SecurityDescriptor = 0;
    if ( ConvertStringSecurityDescriptorToSecurityDescriptorW(
           L"O:SYG:SYD:(A;;0x1F0003;;;SY)",
           1u,
           &SecurityDescriptor,
           0) )
    {
      v11 = CreateEventInSession(
              *((_DWORD *)this + 1),
              L"{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-request3",
              v10,
              0,
              v14,
              SecurityDescriptor);
      *((_QWORD *)this + 5) = v11;
      if ( v11 )
      {
        v2 = 0;
      }
      else
      {
        v12 = GetLastError();
        v2 = v12;
        if ( v12 > 0 )
          v2 = (unsigned __int16)v12 | 0x80070000;
      }
      goto LABEL_29;
    }
LABEL_9:
    v2 = -2147467259;
LABEL_29:
    LocalFree(SecurityDescriptor);
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_sd(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      14,
      (unsigned int)WPP_c659a2668e88300a995919efad269855_Traceguids,
      (unsigned int)"PENSERVICE_CPenSession::SystemInitialize",
      v2);
  return v2 >= 0;
}

```

## disassembly

```asm
0x180017bb0  push    rbp
0x180017bb2  push    rbx
0x180017bb3  push    rdi
0x180017bb4  push    r13
0x180017bb6  mov     rbp, rsp
0x180017bb9  sub     rsp, 38h
0x180017bbd  mov     rdi, rcx
0x180017bc0  xor     ebx, ebx
0x180017bc2  mov     rcx, cs:WPP_GLOBAL_Control
0x180017bc9  lea     r13, WPP_GLOBAL_Control
0x180017bd0  cmp     rcx, r13
0x180017bd3  jz      short loc_180017BFC
0x180017bd5  test    byte ptr [rcx+1Ch], 10h
0x180017bd9  jz      short loc_180017BFC
0x180017bdb  mov     eax, [rdi+4]
0x180017bde  lea     edx, [rbx+0Dh]
0x180017be1  mov     rcx, [rcx+10h]
0x180017be5  lea     r9, aPenserviceCpen_6; "PENSERVICE_CPenSession::SystemInitializ"...
0x180017bec  lea     r8, WPP_c659a2668e88300a995919efad269855_Traceguids
0x180017bf3  mov     [rsp+38h+var_18], eax; int
0x180017bf7  call    WPP_SF_sd
0x180017bfc  mov     eax, cs:dword_1800411A8
0x180017c02  cmp     eax, 5
0x180017c05  jbe     short loc_180017C28
0x180017c07  mov     edx, 4000000h
0x180017c0c  lea     rcx, dword_1800411A8
0x180017c13  call    _tlgKeywordOn
0x180017c18  test    al, al
0x180017c1a  jz      short loc_180017C28
0x180017c1c  lea     rdx, byte_18003B11F
0x180017c23  call    ??$Write@$$V@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EtwEventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EtwEventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *)
0x180017c28  cmp     [rdi+20h], rbx
0x180017c2c  jnz     short loc_180017CA3
0x180017c2e  xor     r9d, r9d; SecurityDescriptorSize
0x180017c31  mov     [rbp+SecurityDescriptor], rbx
0x180017c35  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180017c39  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;0x1F0003;;;SY)"
0x180017c40  lea     edx, [r9+1]; StringSDRevision
0x180017c44  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180017c4a  test    eax, eax
0x180017c4c  jnz     short loc_180017C58
0x180017c4e  mov     ebx, 80004005h
0x180017c53  jmp     loc_180017D85
0x180017c58  mov     rax, [rbp+SecurityDescriptor]
0x180017c5c  lea     rdx, aDffde2138cb446_0; "{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-"...
0x180017c63  mov     ecx, [rdi+4]; unsigned int
0x180017c66  xor     r9d, r9d; int
0x180017c69  mov     [rsp+38h+var_10], rax; void *
0x180017c6e  call    ?CreateEventInSession@@YAPEAXKPEAGKHHPEAX@Z; CreateEventInSession(ulong,ushort *,ulong,int,int,void *)
0x180017c73  mov     [rdi+20h], rax
0x180017c77  test    rax, rax
0x180017c7a  jnz     short loc_180017C99
0x180017c7c  call    cs:__imp_GetLastError
0x180017c82  mov     ebx, eax
0x180017c84  test    eax, eax
0x180017c86  jle     short loc_180017C91
0x180017c88  movzx   ebx, ax
0x180017c8b  or      ebx, 80070000h
0x180017c91  test    ebx, ebx
0x180017c93  js      loc_180017D85
0x180017c99  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180017c9d  call    cs:__imp_LocalFree
0x180017ca3  cmp     qword ptr [rdi+38h], 0
0x180017ca8  jnz     short loc_180017D19
0x180017caa  xor     r9d, r9d; SecurityDescriptorSize
0x180017cad  mov     [rbp+SecurityDescriptor], 0
0x180017cb5  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180017cb9  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;0x1F0003;;;SY)"
0x180017cc0  lea     edx, [r9+1]; StringSDRevision
0x180017cc4  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180017cca  test    eax, eax
0x180017ccc  jz      short loc_180017C4E
0x180017cce  mov     rax, [rbp+SecurityDescriptor]
0x180017cd2  lea     rdx, a773f1b9a35b94e; "{773F1B9A-35B9-4E95-83A0-A210F2DE3B37}-"...
0x180017cd9  mov     ecx, [rdi+4]; unsigned int
0x180017cdc  xor     r9d, r9d; int
0x180017cdf  mov     [rsp+38h+var_10], rax; void *
0x180017ce4  call    ?CreateEventInSession@@YAPEAXKPEAGKHHPEAX@Z; CreateEventInSession(ulong,ushort *,ulong,int,int,void *)
0x180017ce9  mov     [rdi+38h], rax
0x180017ced  test    rax, rax
0x180017cf0  jz      short loc_180017CF6
0x180017cf2  xor     ebx, ebx
0x180017cf4  jmp     short loc_180017D0F
0x180017cf6  call    cs:__imp_GetLastError
0x180017cfc  mov     ebx, eax
0x180017cfe  test    eax, eax
0x180017d00  jle     short loc_180017D0B
0x180017d02  movzx   ebx, ax
0x180017d05  or      ebx, 80070000h
0x180017d0b  test    ebx, ebx
0x180017d0d  js      short loc_180017D85
0x180017d0f  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180017d13  call    cs:__imp_LocalFree
0x180017d19  cmp     qword ptr [rdi+28h], 0
0x180017d1e  jnz     short loc_180017D8F
0x180017d20  xor     r9d, r9d; SecurityDescriptorSize
0x180017d23  mov     [rbp+SecurityDescriptor], 0
0x180017d2b  lea     r8, [rbp+SecurityDescriptor]; SecurityDescriptor
0x180017d2f  lea     rcx, StringSecurityDescriptor; "O:SYG:SYD:(A;;0x1F0003;;;SY)"
0x180017d36  lea     edx, [r9+1]; StringSDRevision
0x180017d3a  call    cs:__imp_ConvertStringSecurityDescriptorToSecurityDescriptorW
0x180017d40  test    eax, eax
0x180017d42  jz      loc_180017C4E
0x180017d48  mov     rax, [rbp+SecurityDescriptor]
0x180017d4c  lea     rdx, aDffde2138cb446_5; "{DFFDE213-8CB4-46a9-90EB-3DA843AF66F9}-"...
0x180017d53  mov     ecx, [rdi+4]; unsigned int
0x180017d56  xor     r9d, r9d; int
0x180017d59  mov     [rsp+38h+var_10], rax; void *
0x180017d5e  call    ?CreateEventInSession@@YAPEAXKPEAGKHHPEAX@Z; CreateEventInSession(ulong,ushort *,ulong,int,int,void *)
0x180017d63  mov     [rdi+28h], rax
0x180017d67  test    rax, rax
0x180017d6a  jz      short loc_180017D70
0x180017d6c  xor     ebx, ebx
0x180017d6e  jmp     short loc_180017D85
0x180017d70  call    cs:__imp_GetLastError
0x180017d76  mov     ebx, eax
0x180017d78  test    eax, eax
0x180017d7a  jle     short loc_180017D85
0x180017d7c  movzx   ebx, ax
0x180017d7f  or      ebx, 80070000h
0x180017d85  mov     rcx, [rbp+SecurityDescriptor]; hMem
0x180017d89  call    cs:__imp_LocalFree
0x180017d8f  mov     rcx, cs:WPP_GLOBAL_Control
0x180017d96  cmp     rcx, r13
0x180017d99  jz      short loc_180017DC1
0x180017d9b  test    byte ptr [rcx+1Ch], 10h
0x180017d9f  jz      short loc_180017DC1
0x180017da1  mov     rcx, [rcx+10h]
0x180017da5  lea     r9, aPenserviceCpen_6; "PENSERVICE_CPenSession::SystemInitializ"...
0x180017dac  mov     edx, 0Eh
0x180017db1  mov     [rsp+38h+var_18], ebx
0x180017db5  lea     r8, WPP_c659a2668e88300a995919efad269855_Traceguids
0x180017dbc  call    WPP_SF_sd
0x180017dc1  not     ebx
0x180017dc3  shr     ebx, 1Fh
0x180017dc6  mov     eax, ebx
0x180017dc8  add     rsp, 38h
0x180017dcc  pop     r13
0x180017dce  pop     rdi
0x180017dcf  pop     rbx
0x180017dd0  pop     rbp
0x180017dd1  retn
```
