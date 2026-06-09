# CreateEventInSession(ulong,ushort *,ulong,int,int,void *)

- ea: `0x180002940`
- end: `0x180002adc`
- name: `?CreateEventInSession@@YAPEAXKPEAGKHHPEAX@Z`
- size: `412`
- prototype: `void *__fastcall(unsigned int, PCWSTR SourceString, __int64, int, int, void *)`
- caller_count: `3`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, broker_com_uri`

## callers

- `0x1800169d0`
- `0x180017bb0`
- `0x1800282a0`

## callees

- `0x180002940`
- `0x180002af0`
- `0x18002b3a8`
- `0x18002e484`
- `0x18002e5f0`

## import_xrefs

- `ntdll!RtlInitUnicodeString` at `0x1800029b8`
- `ntdll!RtlInitUnicodeString` at `0x1800029b8`
- `ntdll!NtClose` at `0x180002a4c`
- `ntdll!NtClose` at `0x180002a4c`
- `ntdll!NtCreateEvent` at `0x180002a0a`
- `ntdll!NtCreateEvent` at `0x180002a0a`

## string_xrefs

- `0x180002975`: `PENSERVICE_CreateEventInSession`
- `0x180002a2a`: `PENSERVICE_CreateEventInSession`
- `0x180002a72`: `PENSERVICE_CreateEventInSession`
- `0x180002aaf`: `PENSERVICE_CreateEventInSession`

## pseudocode

```c
void *__fastcall CreateEventInSession(unsigned int a1, PCWSTR SourceString, __int64 a3, int a4, int a5, void *a6)
{
  void *v9; // rbx
  unsigned int v10; // r8d
  NTSTATUS v11; // eax
  int v12; // r8d
  void *result; // rax
  void *EventHandle; // [rsp+30h] [rbp-88h] BYREF
  _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-80h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-70h] BYREF

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      16,
      WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
      "PENSERVICE_CreateEventInSession");
  EventHandle = 0;
  v9 = _OpenSessionDirectory(a1);
  if ( v9 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    ObjectAttributes.SecurityDescriptor = a6;
    *(_QWORD *)&ObjectAttributes.Attributes = 0;
    ObjectAttributes.RootDirectory = v9;
    ObjectAttributes.SecurityQualityOfService = 0;
    v11 = NtCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, (EVENT_TYPE)(a4 == 0), 0);
    if ( v11 < 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
        WPP_SF_sSd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          17,
          v12,
          (unsigned int)"PENSERVICE_CreateEventInSession",
          (__int64)SourceString,
          v11);
      EventHandle = 0;
    }
    NtClose(v9);
  }
  result = EventHandle;
  if ( !EventHandle )
  {
    if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
      WPP_SF_s(
        *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
        18,
        WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
        "PENSERVICE_CreateEventInSession");
    result = OpenEventInSession(a1, SourceString, v10);
    EventHandle = result;
  }
  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      19,
      WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
      "PENSERVICE_CreateEventInSession");
    return EventHandle;
  }
  return result;
}

```

## disassembly

```asm
0x180002940  push    rbx
0x180002942  push    rbp
0x180002943  push    rsi
0x180002944  push    rdi
0x180002945  push    r14
0x180002947  push    r15
0x180002949  sub     rsp, 88h
0x180002950  mov     esi, r9d
0x180002953  mov     rbp, rdx
0x180002956  mov     edi, ecx
0x180002958  mov     rcx, cs:WPP_GLOBAL_Control
0x18000295f  lea     r14, WPP_GLOBAL_Control
0x180002966  cmp     rcx, r14
0x180002969  jz      short loc_18000298D
0x18000296b  test    byte ptr [rcx+1Ch], 10h
0x18000296f  jz      short loc_18000298D
0x180002971  mov     rcx, [rcx+10h]
0x180002975  lea     r9, aPenserviceCrea; "PENSERVICE_CreateEventInSession"
0x18000297c  mov     edx, 10h
0x180002981  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x180002988  call    WPP_SF_s
0x18000298d  xor     r15d, r15d
0x180002990  mov     ecx, edi; unsigned int
0x180002992  mov     [rsp+0B8h+EventHandle], r15
0x180002997  call    ?_OpenSessionDirectory@@YAPEAXK@Z; _OpenSessionDirectory(ulong)
0x18000299c  mov     rbx, rax
0x18000299f  test    rax, rax
0x1800029a2  jz      loc_180002A52
0x1800029a8  xorps   xmm0, xmm0
0x1800029ab  lea     rcx, [rsp+0B8h+DestinationString]; DestinationString
0x1800029b0  mov     rdx, rbp; SourceString
0x1800029b3  movups  xmmword ptr [rsp+0B8h+DestinationString.Length], xmm0
0x1800029b8  call    cs:__imp_RtlInitUnicodeString
0x1800029be  lea     rax, [rsp+0B8h+DestinationString]
0x1800029c3  mov     qword ptr [rsp+0B8h+ObjectAttributes.Length], 30h ; '0'
0x1800029cc  mov     [rsp+0B8h+ObjectAttributes.ObjectName], rax
0x1800029d1  lea     r8, [rsp+0B8h+ObjectAttributes]; ObjectAttributes
0x1800029d6  mov     rax, [rsp+0B8h+arg_28]
0x1800029de  lea     rcx, [rsp+0B8h+EventHandle]; EventHandle
0x1800029e3  mov     r9d, r15d
0x1800029e6  mov     [rsp+0B8h+ObjectAttributes.SecurityDescriptor], rax
0x1800029eb  test    esi, esi
0x1800029ed  mov     qword ptr [rsp+0B8h+ObjectAttributes.Attributes], r15
0x1800029f2  mov     edx, 1F0003h; DesiredAccess
0x1800029f7  mov     [rsp+0B8h+ObjectAttributes.RootDirectory], rbx
0x1800029fc  setz    r9b; EventType
0x180002a00  mov     [rsp+0B8h+ObjectAttributes.SecurityQualityOfService], r15
0x180002a05  mov     [rsp+0B8h+InitialState], r15b; InitialState
0x180002a0a  call    cs:__imp_NtCreateEvent
0x180002a10  test    eax, eax
0x180002a12  jns     short loc_180002A49
0x180002a14  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a1b  cmp     rcx, r14
0x180002a1e  jz      short loc_180002A44
0x180002a20  test    byte ptr [rcx+1Ch], 4
0x180002a24  jz      short loc_180002A44
0x180002a26  mov     rcx, [rcx+10h]
0x180002a2a  lea     r9, aPenserviceCrea; "PENSERVICE_CreateEventInSession"
0x180002a31  mov     [rsp+0B8h+var_90], eax
0x180002a35  mov     edx, 11h
0x180002a3a  mov     qword ptr [rsp+0B8h+InitialState], rbp
0x180002a3f  call    WPP_SF_sSd
0x180002a44  mov     [rsp+0B8h+EventHandle], r15
0x180002a49  mov     rcx, rbx; Handle
0x180002a4c  call    cs:__imp_NtClose
0x180002a52  mov     rax, [rsp+0B8h+EventHandle]
0x180002a57  test    rax, rax
0x180002a5a  jnz     short loc_180002A99
0x180002a5c  mov     rcx, cs:WPP_GLOBAL_Control
0x180002a63  cmp     rcx, r14
0x180002a66  jz      short loc_180002A8A
0x180002a68  test    byte ptr [rcx+1Ch], 4
0x180002a6c  jz      short loc_180002A8A
0x180002a6e  mov     rcx, [rcx+10h]
0x180002a72  lea     r9, aPenserviceCrea; "PENSERVICE_CreateEventInSession"
0x180002a79  mov     edx, 12h
0x180002a7e  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x180002a85  call    WPP_SF_s
0x180002a8a  mov     rdx, rbp; SourceString
0x180002a8d  mov     ecx, edi; unsigned int
0x180002a8f  call    ?OpenEventInSession@@YAPEAXKPEAGK@Z; OpenEventInSession(ulong,ushort *,ulong)
0x180002a94  mov     [rsp+0B8h+EventHandle], rax
0x180002a99  mov     rcx, cs:WPP_GLOBAL_Control
0x180002aa0  cmp     rcx, r14
0x180002aa3  jz      short loc_180002ACC
0x180002aa5  test    byte ptr [rcx+1Ch], 10h
0x180002aa9  jz      short loc_180002ACC
0x180002aab  mov     rcx, [rcx+10h]
0x180002aaf  lea     r9, aPenserviceCrea; "PENSERVICE_CreateEventInSession"
0x180002ab6  mov     edx, 13h
0x180002abb  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x180002ac2  call    WPP_SF_s
0x180002ac7  mov     rax, [rsp+0B8h+EventHandle]
0x180002acc  add     rsp, 88h
0x180002ad3  pop     r15
0x180002ad5  pop     r14
0x180002ad7  pop     rdi
0x180002ad8  pop     rsi
0x180002ad9  pop     rbp
0x180002ada  pop     rbx
0x180002adb  retn
```
