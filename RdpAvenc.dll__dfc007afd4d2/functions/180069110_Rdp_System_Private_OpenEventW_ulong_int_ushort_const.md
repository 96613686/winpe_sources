# Rdp::System::Private::OpenEventW(ulong,int,ushort const *)

- ea: `0x180069110`
- end: `0x1800691a8`
- name: `?OpenEventW@Private@System@Rdp@@YAPEAXKHPEBG@Z`
- size: `152`
- prototype: `void *(Rdp::System::Private *__hidden this, unsigned int, int, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x18001737c`

## callees

- `0x180069110`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069146`
- `api-ms-win-core-errorhandling-l1-1-0!SetLastError` at `0x180069146`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18006913e`
- `ntdll!RtlNtStatusToDosErrorNoTeb` at `0x18006913e`
- `ntdll!NtOpenEvent` at `0x180069190`
- `ntdll!NtOpenEvent` at `0x180069190`
- `ntdll!RtlInitUnicodeString` at `0x180069157`
- `ntdll!RtlInitUnicodeString` at `0x180069157`

## pseudocode

```c
void *__fastcall Rdp::System::Private::OpenEventW(
        Rdp::System::Private *this,
        __int64 a2,
        const WCHAR *a3,
        const unsigned __int16 *a4)
{
  NTSTATUS v4; // ecx
  DWORD v5; // eax
  NTSTATUS v7; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+80h] [rbp+20h] BYREF

  EventHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( !a3 )
  {
    v4 = -1073741811;
LABEL_3:
    v5 = RtlNtStatusToDosErrorNoTeb(v4);
    SetLastError(v5);
    return 0;
  }
  RtlInitUnicodeString(&DestinationString, a3);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v7 = NtOpenEvent(&EventHandle, 0x100002u, &ObjectAttributes);
  if ( v7 < 0 )
  {
    v4 = v7;
    goto LABEL_3;
  }
  return EventHandle;
}

```

## disassembly

```asm
0x180069110  push    rbp
0x180069112  mov     rbp, rsp
0x180069115  sub     rsp, 60h
0x180069119  mov     [rbp+EventHandle], 0
0x180069121  xorps   xmm0, xmm0
0x180069124  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x180069128  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18006912c  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180069130  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x180069134  test    r8, r8
0x180069137  jnz     short loc_180069150
0x180069139  mov     ecx, 0C000000Dh; Status
0x18006913e  call    cs:__imp_RtlNtStatusToDosErrorNoTeb
0x180069144  mov     ecx, eax; dwErrCode
0x180069146  call    cs:__imp_SetLastError
0x18006914c  xor     eax, eax
0x18006914e  jmp     short loc_1800691A2
0x180069150  mov     rdx, r8; SourceString
0x180069153  lea     rcx, [rbp+DestinationString]; DestinationString
0x180069157  call    cs:__imp_RtlInitUnicodeString
0x18006915d  lea     rax, [rbp+DestinationString]
0x180069161  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x180069168  xorps   xmm0, xmm0
0x18006916b  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18006916f  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180069173  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18006917b  mov     edx, 100002h; DesiredAccess
0x180069180  mov     [rbp+ObjectAttributes.Attributes], 0
0x180069187  lea     rcx, [rbp+EventHandle]; EventHandle
0x18006918b  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180069190  call    cs:__imp_NtOpenEvent
0x180069196  test    eax, eax
0x180069198  jns     short loc_18006919E
0x18006919a  mov     ecx, eax
0x18006919c  jmp     short loc_18006913E
0x18006919e  mov     rax, [rbp+EventHandle]
0x1800691a2  add     rsp, 60h
0x1800691a6  pop     rbp
0x1800691a7  retn
```
