# StartDisableCredentialGuardWatcher

- ea: `0x1400065bc`
- end: `0x1400066b6`
- name: `StartDisableCredentialGuardWatcher`
- size: `250`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000685c`

## callees

- `0x1400065bc`

## import_xrefs

- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000667f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006689`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006675`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x14000667f`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x140006689`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000669c`
- `api-ms-win-core-handle-l1-1-0!CloseHandle` at `0x14000669c`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140006667`
- `api-ms-win-core-processthreads-l1-1-0!CreateThread` at `0x140006667`
- `ntdll!NtCreateEvent` at `0x14000663b`
- `ntdll!NtCreateEvent` at `0x14000663b`
- `ntdll!RtlInitUnicodeString` at `0x1400065fa`
- `ntdll!RtlInitUnicodeString` at `0x1400065fa`

## pseudocode

```c
__int64 __fastcall StartDisableCredentialGuardWatcher(_QWORD *a1)
{
  int LastError; // ebx
  HANDLE Thread; // rax
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+88h] [rbp+18h] BYREF

  EventHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  RtlInitUnicodeString(&DestinationString, L"\\LSA_ISO_DISABLE_CREDENTIAL_GUARD");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  LastError = NtCreateEvent(&EventHandle, 0x1F0003u, &ObjectAttributes, NotificationEvent, 0);
  if ( LastError >= 0 )
  {
    Thread = CreateThread(0, 0, DisableCredentialGuardWatcher, EventHandle, 0, 0);
    *a1 = Thread;
    if ( !Thread )
    {
      if ( (int)GetLastError() > 0 )
        LastError = (unsigned __int16)GetLastError() | 0xC0070000;
      else
        LastError = GetLastError();
      CloseHandle(EventHandle);
    }
  }
  return (unsigned int)LastError;
}

```

## disassembly

```asm
0x1400065bc  mov     [rsp-8+arg_0], rbx
0x1400065c1  mov     [rsp-8+arg_10], rdi
0x1400065c6  push    rbp
0x1400065c7  mov     rbp, rsp
0x1400065ca  sub     rsp, 70h
0x1400065ce  xorps   xmm1, xmm1
0x1400065d1  mov     [rbp+EventHandle], 0
0x1400065d9  mov     rdi, rcx
0x1400065dc  lea     rdx, aLsaIsoDisableC; "\\LSA_ISO_DISABLE_CREDENTIAL_GUARD"
0x1400065e3  xorps   xmm0, xmm0
0x1400065e6  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400065ea  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400065ee  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x1400065f2  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x1400065f6  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x1400065fa  call    cs:__imp_RtlInitUnicodeString
0x140006600  lea     rax, [rbp+DestinationString]
0x140006604  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000660b  xorps   xmm0, xmm0
0x14000660e  mov     [rbp+ObjectAttributes.ObjectName], rax
0x140006612  xor     r9d, r9d; EventType
0x140006615  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x14000661d  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140006621  mov     [rbp+ObjectAttributes.Attributes], 0
0x140006628  mov     edx, 1F0003h; DesiredAccess
0x14000662d  mov     [rsp+70h+InitialState], 0; InitialState
0x140006632  lea     rcx, [rbp+EventHandle]; EventHandle
0x140006636  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000663b  call    cs:__imp_NtCreateEvent
0x140006641  mov     ebx, eax
0x140006643  test    eax, eax
0x140006645  js      short loc_1400066A2
0x140006647  mov     r9, [rbp+EventHandle]; lpParameter
0x14000664b  lea     r8, ?DisableCredentialGuardWatcher@@YAKPEAX@Z; lpStartAddress
0x140006652  mov     [rsp+70h+lpThreadId], 0; lpThreadId
0x14000665b  xor     edx, edx; dwStackSize
0x14000665d  xor     ecx, ecx; lpThreadAttributes
0x14000665f  mov     dword ptr [rsp+70h+InitialState], 0; dwCreationFlags
0x140006667  call    cs:__imp_CreateThread
0x14000666d  mov     [rdi], rax
0x140006670  test    rax, rax
0x140006673  jnz     short loc_1400066A2
0x140006675  call    cs:__imp_GetLastError
0x14000667b  test    eax, eax
0x14000667d  jg      short loc_140006689
0x14000667f  call    cs:__imp_GetLastError
0x140006685  mov     ebx, eax
0x140006687  jmp     short loc_140006698
0x140006689  call    cs:__imp_GetLastError
0x14000668f  movzx   ebx, ax
0x140006692  or      ebx, 0C0070000h
0x140006698  mov     rcx, [rbp+EventHandle]; hObject
0x14000669c  call    cs:__imp_CloseHandle
0x1400066a2  lea     r11, [rsp+70h+var_s0]
0x1400066a7  mov     eax, ebx
0x1400066a9  mov     rbx, [r11+10h]
0x1400066ad  mov     rdi, [r11+20h]
0x1400066b1  mov     rsp, r11
0x1400066b4  pop     rbp
0x1400066b5  retn
```
