# KdcWaitForSamService(void)

- ea: `0x180038094`
- end: `0x18003823e`
- name: `?KdcWaitForSamService@@YAEXZ`
- size: `426`
- prototype: `unsigned __int8(void)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, loader_planting, service_task, installer_update, broker_com_uri`

## callers

- `0x18003a5fc`

## callees

- `0x1800101c4`
- `0x180038094`
- `0x18003b5d8`
- `0x1800402c4`
- `0x18004046c`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180038199`
- `api-ms-win-core-synch-l1-1-0!WaitForSingleObject` at `0x180038199`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038203`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x180038203`
- `ntdll!RtlInitUnicodeString` at `0x1800380cc`
- `ntdll!RtlInitUnicodeString` at `0x1800380cc`
- `ntdll!NtOpenEvent` at `0x180038107`
- `ntdll!NtOpenEvent` at `0x180038148`
- `ntdll!NtOpenEvent` at `0x180038107`
- `ntdll!NtOpenEvent` at `0x180038148`
- `ntdll!NtClose` at `0x1800381e7`
- `ntdll!NtClose` at `0x180038224`
- `ntdll!NtClose` at `0x1800381e7`
- `ntdll!NtClose` at `0x180038224`
- `ntdll!NtCreateEvent` at `0x18003812a`
- `ntdll!NtCreateEvent` at `0x18003812a`

## string_xrefs

- `0x1800380b1`: `\SAM_SERVICE_STARTED`

## pseudocode

```c
unsigned __int8 KdcWaitForSamService(void)
{
  NTSTATUS v0; // eax
  NTSTATUS v1; // eax
  DWORD v2; // edi
  DWORD LastError; // eax
  __int64 v5; // rdx
  __int64 v6; // r8
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+80h] [rbp+10h] BYREF

  EventHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\SAM_SERVICE_STARTED");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v0 = NtOpenEvent(&EventHandle, 0x100002u, &ObjectAttributes);
  if ( v0 >= 0 )
    goto LABEL_25;
  if ( v0 != -1073741772 )
    goto LABEL_7;
  v1 = NtCreateEvent(&EventHandle, 0x100002u, &ObjectAttributes, NotificationEvent, 0);
  if ( v1 == 0x40000000 || v1 == -1073741771 )
    v1 = NtOpenEvent(&EventHandle, 0x100002u, &ObjectAttributes);
  if ( v1 >= 0 )
  {
LABEL_25:
    while ( 1 )
    {
      v2 = WaitForSingleObject(EventHandle, 0x1388u);
      if ( v2 != 258 )
        break;
      if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 2) != 0 )
        WPP_SF_(*((_QWORD *)WPP_GLOBAL_Control + 2), 15, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids);
      if ( !UpdateStatus(2u) )
        goto LABEL_21;
    }
    if ( !v2 )
    {
      NtClose(EventHandle);
      return 1;
    }
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
    {
      LastError = GetLastError();
      WPP_SF_ll(*((_QWORD *)WPP_GLOBAL_Control + 2), v5, v6, LastError, v2);
    }
LABEL_21:
    NtClose(EventHandle);
  }
  else
  {
LABEL_7:
    if ( WPP_GLOBAL_Control != (CSecurityData *)&WPP_GLOBAL_Control && (*((_BYTE *)WPP_GLOBAL_Control + 28) & 1) != 0 )
      WPP_SF_L(*((_QWORD *)WPP_GLOBAL_Control + 2), 14);
  }
  return 0;
}

```

## disassembly

```asm
0x180038094  mov     [rsp-8+arg_8], rbx
0x180038099  mov     [rsp-8+arg_10], rdi
0x18003809e  push    rbp
0x18003809f  mov     rbp, rsp
0x1800380a2  sub     rsp, 70h
0x1800380a6  xorps   xmm0, xmm0
0x1800380a9  mov     [rbp+EventHandle], 0
0x1800380b1  lea     rdx, aSamServiceStar; "\\SAM_SERVICE_STARTED"
0x1800380b8  lea     rcx, [rbp+DestinationString]; DestinationString
0x1800380bc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1800380c0  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x1800380c4  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x1800380c8  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x1800380cc  call    cs:__imp_RtlInitUnicodeString
0x1800380d2  lea     rax, [rbp+DestinationString]
0x1800380d6  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x1800380dd  xorps   xmm0, xmm0
0x1800380e0  mov     [rbp+ObjectAttributes.ObjectName], rax
0x1800380e4  mov     ebx, 100002h
0x1800380e9  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x1800380f1  mov     edx, ebx; DesiredAccess
0x1800380f3  mov     [rbp+ObjectAttributes.Attributes], 0
0x1800380fa  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1800380fe  lea     rcx, [rbp+EventHandle]; EventHandle
0x180038102  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x180038107  call    cs:__imp_NtOpenEvent
0x18003810d  test    eax, eax
0x18003810f  jns     short loc_180038189
0x180038111  cmp     eax, 0C0000034h
0x180038116  jnz     short loc_180038152
0x180038118  xor     r9d, r9d; EventType
0x18003811b  mov     [rsp+70h+InitialState], 0; InitialState
0x180038120  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180038124  mov     edx, ebx; DesiredAccess
0x180038126  lea     rcx, [rbp+EventHandle]; EventHandle
0x18003812a  call    cs:__imp_NtCreateEvent
0x180038130  cmp     eax, 40000000h
0x180038135  jz      short loc_18003813E
0x180038137  cmp     eax, 0C0000035h
0x18003813c  jnz     short loc_18003814E
0x18003813e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x180038142  mov     edx, ebx; DesiredAccess
0x180038144  lea     rcx, [rbp+EventHandle]; EventHandle
0x180038148  call    cs:__imp_NtOpenEvent
0x18003814e  test    eax, eax
0x180038150  jns     short loc_180038189
0x180038152  mov     rcx, cs:WPP_GLOBAL_Control
0x180038159  lea     rbx, WPP_GLOBAL_Control
0x180038160  cmp     rcx, rbx
0x180038163  jz      loc_18003822A
0x180038169  test    byte ptr [rcx+1Ch], 1
0x18003816d  jz      loc_18003822A
0x180038173  mov     rcx, [rcx+10h]
0x180038177  mov     edx, 0Eh
0x18003817c  mov     r9d, eax
0x18003817f  call    WPP_SF_L
0x180038184  jmp     loc_18003822A
0x180038189  lea     rbx, WPP_GLOBAL_Control
0x180038190  mov     rcx, [rbp+EventHandle]; hHandle
0x180038194  mov     edx, 1388h; dwMilliseconds
0x180038199  call    cs:__imp_WaitForSingleObject
0x18003819f  mov     edi, eax
0x1800381a1  cmp     eax, 102h
0x1800381a6  jnz     short loc_1800381DF
0x1800381a8  mov     rcx, cs:WPP_GLOBAL_Control
0x1800381af  cmp     rcx, rbx
0x1800381b2  jz      short loc_1800381CF
0x1800381b4  test    byte ptr [rcx+1Ch], 2
0x1800381b8  jz      short loc_1800381CF
0x1800381ba  mov     rcx, [rcx+10h]
0x1800381be  lea     r8, WPP_4faeb9b481d0381be4025487491ed0d4_Traceguids
0x1800381c5  mov     edx, 0Fh
0x1800381ca  call    WPP_SF_
0x1800381cf  mov     ecx, 2; unsigned int
0x1800381d4  call    ?UpdateStatus@@YAEK@Z; UpdateStatus(ulong)
0x1800381d9  test    al, al
0x1800381db  jnz     short loc_180038190
0x1800381dd  jmp     short loc_180038220
0x1800381df  test    edi, edi
0x1800381e1  jnz     short loc_1800381F1
0x1800381e3  mov     rcx, [rbp+EventHandle]; Handle
0x1800381e7  call    cs:__imp_NtClose
0x1800381ed  mov     al, 1
0x1800381ef  jmp     short loc_18003822C
0x1800381f1  mov     rax, cs:WPP_GLOBAL_Control
0x1800381f8  cmp     rax, rbx
0x1800381fb  jz      short loc_180038220
0x1800381fd  test    byte ptr [rax+1Ch], 1
0x180038201  jz      short loc_180038220
0x180038203  call    cs:__imp_GetLastError
0x180038209  mov     rcx, cs:WPP_GLOBAL_Control
0x180038210  mov     r9d, eax
0x180038213  mov     dword ptr [rsp+70h+InitialState], edi
0x180038217  mov     rcx, [rcx+10h]
0x18003821b  call    WPP_SF_ll
0x180038220  mov     rcx, [rbp+EventHandle]; Handle
0x180038224  call    cs:__imp_NtClose
0x18003822a  xor     al, al
0x18003822c  lea     r11, [rsp+70h+var_s0]
0x180038231  mov     rbx, [r11+18h]
0x180038235  mov     rdi, [r11+20h]
0x180038239  mov     rsp, r11
0x18003823c  pop     rbp
0x18003823d  retn
```
