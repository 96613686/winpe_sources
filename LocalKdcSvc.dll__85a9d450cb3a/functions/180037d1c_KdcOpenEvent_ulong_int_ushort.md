# KdcOpenEvent(ulong,int,ushort *)

- ea: `0x180037d1c`
- end: `0x180037dde`
- name: `?KdcOpenEvent@@YAPEAXKHPEAG@Z`
- size: `194`
- prototype: `void *(unsigned int, int, unsigned __int16 *)`
- caller_count: `2`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18003b478`
- `0x18006d260`

## callees

- `0x180037d1c`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d49`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180037d49`
- `ntdll!RtlInitUnicodeString` at `0x180037d5d`
- `ntdll!RtlInitUnicodeString` at `0x180037d5d`
- `ntdll!NtOpenEvent` at `0x180037dbb`
- `ntdll!NtOpenEvent` at `0x180037dbb`
- `ntdll!NtCreateEvent` at `0x180037d9d`
- `ntdll!NtCreateEvent` at `0x180037d9d`
- `ntdll!RtlNtStatusToDosError` at `0x180037dc7`
- `ntdll!RtlNtStatusToDosError` at `0x180037dc7`

## pseudocode

```c
void *__fastcall KdcOpenEvent(__int64 a1, __int64 a2, unsigned __int16 *a3)
{
  DWORD v3; // ecx
  int v5; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+90h] [rbp+20h] BYREF

  EventHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( !a3 )
  {
    v3 = 87;
LABEL_3:
    SetLastError(v3);
    return 0;
  }
  RtlInitUnicodeString(&DestinationString, a3);
  ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  ObjectAttributes.ObjectName = &DestinationString;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v5 = NtCreateEvent(&EventHandle, 2u, &ObjectAttributes, NotificationEvent, 0);
  if ( v5 < 0 )
  {
    if ( v5 != -1073741771 || (v5 = NtOpenEvent(&EventHandle, 2u, &ObjectAttributes), v5 < 0) )
    {
      v3 = RtlNtStatusToDosError(v5);
      goto LABEL_3;
    }
  }
  return EventHandle;
}

```

## disassembly

```asm
0x180037d1c  push    rbp
0x180037d1e  mov     rbp, rsp
0x180037d21  sub     rsp, 70h
0x180037d25  mov     [rbp+EventHandle], 0
0x180037d2d  xorps   xmm0, xmm0
0x180037d30  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180037d34  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x180037d38  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180037d3c  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180037d40  test    r8, r8
0x180037d43  jnz     short loc_180037D56
0x180037d45  lea     ecx, [r8+57h]; dwErrCode
0x180037d49  call    cs:__imp_SetLastError
0x180037d4f  xor     eax, eax
0x180037d51  jmp     loc_180037DD8
0x180037d56  mov     rdx, r8; SourceString
0x180037d59  lea     rcx, [rbp+DestinationString]; DestinationString
0x180037d5d  call    cs:__imp_RtlInitUnicodeString
0x180037d63  xor     r9d, r9d; EventType
0x180037d66  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180037d6d  lea     rax, [rbp+DestinationString]
0x180037d71  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x180037d79  xorps   xmm0, xmm0
0x180037d7c  mov     [rbp+ObjectAttributes.Attributes], 0
0x180037d83  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180037d87  mov     [rbp+ObjectAttributes.ObjectName], rax
0x180037d8b  lea     edx, [r9+2]; DesiredAccess
0x180037d8f  mov     [rsp+70h+InitialState], 0; InitialState
0x180037d94  lea     rcx, [rbp+EventHandle]; EventHandle
0x180037d98  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180037d9d  call    cs:__imp_NtCreateEvent
0x180037da3  test    eax, eax
0x180037da5  jns     short loc_180037DD4
0x180037da7  cmp     eax, 0C0000035h
0x180037dac  jnz     short loc_180037DC5
0x180037dae  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180037db2  mov     edx, 2; DesiredAccess
0x180037db7  lea     rcx, [rbp+EventHandle]; EventHandle
0x180037dbb  call    cs:__imp_NtOpenEvent
0x180037dc1  test    eax, eax
0x180037dc3  jns     short loc_180037DD4
0x180037dc5  mov     ecx, eax; Status
0x180037dc7  call    cs:__imp_RtlNtStatusToDosError
0x180037dcd  mov     ecx, eax
0x180037dcf  jmp     loc_180037D49
0x180037dd4  mov     rax, [rbp+EventHandle]
0x180037dd8  add     rsp, 70h
0x180037ddc  pop     rbp
0x180037ddd  retn
```
