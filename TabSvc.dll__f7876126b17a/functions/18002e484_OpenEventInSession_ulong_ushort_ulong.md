# OpenEventInSession(ulong,ushort *,ulong)

- ea: `0x18002e484`
- end: `0x18002e5e7`
- name: `?OpenEventInSession@@YAPEAXKPEAGK@Z`
- size: `355`
- prototype: `void *__fastcall(unsigned int, PCWSTR SourceString, unsigned int)`
- caller_count: `1`
- callee_count: `4`
- tags: `reparse_path, loader_planting, service_task`

## callers

- `0x180002940`

## callees

- `0x180002af0`
- `0x18002b3a8`
- `0x18002e484`
- `0x18002e5f0`

## import_xrefs

- `ntdll!NtOpenEvent` at `0x18002e52b`
- `ntdll!NtOpenEvent` at `0x18002e52b`
- `ntdll!RtlInitUnicodeString` at `0x18002e4f4`
- `ntdll!RtlInitUnicodeString` at `0x18002e4f4`
- `ntdll!NtClose` at `0x18002e570`
- `ntdll!NtClose` at `0x18002e570`

## string_xrefs

- `0x18002e4b3`: `PENSERVICE_OpenEventInSession`
- `0x18002e54b`: `PENSERVICE_OpenEventInSession`
- `0x18002e593`: `PENSERVICE_OpenEventInSession`
- `0x18002e5c1`: `PENSERVICE_OpenEventInSession`

## pseudocode

```c
void *__fastcall OpenEventInSession(unsigned int a1, PCWSTR SourceString)
{
  void *v4; // rbx
  NTSTATUS v5; // eax
  int v6; // r8d
  struct _GUID *v7; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-48h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-38h] BYREF
  void *EventHandle; // [rsp+B8h] [rbp+40h] BYREF

  if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      20,
      WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
      "PENSERVICE_OpenEventInSession");
  EventHandle = 0;
  v4 = _OpenSessionDirectory(a1);
  if ( v4 )
  {
    DestinationString = 0;
    RtlInitUnicodeString(&DestinationString, SourceString);
    *(_QWORD *)&ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &DestinationString;
    memset(&ObjectAttributes.Attributes, 0, 24);
    ObjectAttributes.RootDirectory = v4;
    v5 = NtOpenEvent(&EventHandle, 0x1F0003u, &ObjectAttributes);
    if ( v5 < 0 )
    {
      if ( WPP_GLOBAL_Control != (struct _GUID *)&WPP_GLOBAL_Control && (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
        WPP_SF_sSd(
          *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
          21,
          v6,
          (unsigned int)"PENSERVICE_OpenEventInSession",
          (__int64)SourceString,
          v5);
      EventHandle = 0;
    }
    NtClose(v4);
  }
  if ( EventHandle )
    goto LABEL_15;
  v7 = WPP_GLOBAL_Control;
  if ( WPP_GLOBAL_Control == (struct _GUID *)&WPP_GLOBAL_Control )
    return EventHandle;
  if ( (WPP_GLOBAL_Control[1].Data4[4] & 4) != 0 )
  {
    WPP_SF_s(
      *(_QWORD *)&WPP_GLOBAL_Control[1].Data1,
      22,
      WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
      "PENSERVICE_OpenEventInSession");
LABEL_15:
    v7 = WPP_GLOBAL_Control;
  }
  if ( v7 != (struct _GUID *)&WPP_GLOBAL_Control && (v7[1].Data4[4] & 0x10) != 0 )
    WPP_SF_s(
      *(_QWORD *)&v7[1].Data1,
      23,
      WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids,
      "PENSERVICE_OpenEventInSession");
  return EventHandle;
}

```

## disassembly

```asm
0x18002e484  push    rbp
0x18002e486  push    rbx
0x18002e487  push    rdi
0x18002e488  push    r14
0x18002e48a  mov     rbp, rsp
0x18002e48d  sub     rsp, 78h
0x18002e491  mov     rdi, rdx
0x18002e494  mov     ebx, ecx
0x18002e496  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e49d  lea     r14, WPP_GLOBAL_Control
0x18002e4a4  cmp     rcx, r14
0x18002e4a7  jz      short loc_18002E4CB
0x18002e4a9  test    byte ptr [rcx+1Ch], 10h
0x18002e4ad  jz      short loc_18002E4CB
0x18002e4af  mov     rcx, [rcx+10h]
0x18002e4b3  lea     r9, aPenserviceOpen_0; "PENSERVICE_OpenEventInSession"
0x18002e4ba  mov     edx, 14h
0x18002e4bf  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x18002e4c6  call    WPP_SF_s
0x18002e4cb  mov     ecx, ebx; unsigned int
0x18002e4cd  mov     [rbp+EventHandle], 0
0x18002e4d5  call    ?_OpenSessionDirectory@@YAPEAXK@Z; _OpenSessionDirectory(ulong)
0x18002e4da  mov     rbx, rax
0x18002e4dd  test    rax, rax
0x18002e4e0  jz      loc_18002E576
0x18002e4e6  xorps   xmm0, xmm0
0x18002e4e9  lea     rcx, [rbp+DestinationString]; DestinationString
0x18002e4ed  mov     rdx, rdi; SourceString
0x18002e4f0  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18002e4f4  call    cs:__imp_RtlInitUnicodeString
0x18002e4fa  lea     rax, [rbp+DestinationString]
0x18002e4fe  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x18002e506  xorps   xmm0, xmm0
0x18002e509  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18002e50d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18002e511  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x18002e519  mov     edx, 1F0003h; DesiredAccess
0x18002e51e  mov     [rbp+ObjectAttributes.RootDirectory], rbx
0x18002e522  lea     rcx, [rbp+EventHandle]; EventHandle
0x18002e526  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18002e52b  call    cs:__imp_NtOpenEvent
0x18002e531  test    eax, eax
0x18002e533  jns     short loc_18002E56D
0x18002e535  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e53c  cmp     rcx, r14
0x18002e53f  jz      short loc_18002E565
0x18002e541  test    byte ptr [rcx+1Ch], 4
0x18002e545  jz      short loc_18002E565
0x18002e547  mov     rcx, [rcx+10h]
0x18002e54b  lea     r9, aPenserviceOpen_0; "PENSERVICE_OpenEventInSession"
0x18002e552  mov     [rsp+78h+var_50], eax
0x18002e556  mov     edx, 15h
0x18002e55b  mov     [rsp+78h+var_58], rdi
0x18002e560  call    WPP_SF_sSd
0x18002e565  mov     [rbp+EventHandle], 0
0x18002e56d  mov     rcx, rbx; Handle
0x18002e570  call    cs:__imp_NtClose
0x18002e576  cmp     [rbp+EventHandle], 0
0x18002e57b  jnz     short loc_18002E5AB
0x18002e57d  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e584  cmp     rcx, r14
0x18002e587  jz      short loc_18002E5D9
0x18002e589  test    byte ptr [rcx+1Ch], 4
0x18002e58d  jz      short loc_18002E5B2
0x18002e58f  mov     rcx, [rcx+10h]
0x18002e593  lea     r9, aPenserviceOpen_0; "PENSERVICE_OpenEventInSession"
0x18002e59a  mov     edx, 16h
0x18002e59f  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x18002e5a6  call    WPP_SF_s
0x18002e5ab  mov     rcx, cs:WPP_GLOBAL_Control
0x18002e5b2  cmp     rcx, r14
0x18002e5b5  jz      short loc_18002E5D9
0x18002e5b7  test    byte ptr [rcx+1Ch], 10h
0x18002e5bb  jz      short loc_18002E5D9
0x18002e5bd  mov     rcx, [rcx+10h]
0x18002e5c1  lea     r9, aPenserviceOpen_0; "PENSERVICE_OpenEventInSession"
0x18002e5c8  mov     edx, 17h
0x18002e5cd  lea     r8, WPP_5dcd8414c92c33ed143342dc983ec5b8_Traceguids
0x18002e5d4  call    WPP_SF_s
0x18002e5d9  mov     rax, [rbp+EventHandle]
0x18002e5dd  add     rsp, 78h
0x18002e5e1  pop     r14
0x18002e5e3  pop     rdi
0x18002e5e4  pop     rbx
0x18002e5e5  pop     rbp
0x18002e5e6  retn
```
