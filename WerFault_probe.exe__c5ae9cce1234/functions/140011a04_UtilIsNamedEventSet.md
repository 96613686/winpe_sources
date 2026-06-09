# UtilIsNamedEventSet

- ea: `0x140011a04`
- end: `0x140011aaf`
- name: `UtilIsNamedEventSet`
- size: `171`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x140023a6c`

## callees

- `0x140011a04`

## import_xrefs

- `ntdll!NtQueryEvent` at `0x140011a7b`
- `ntdll!NtQueryEvent` at `0x140011a7b`
- `ntdll!NtOpenEvent` at `0x140011a52`
- `ntdll!NtOpenEvent` at `0x140011a52`
- `ntdll!NtClose` at `0x140011a87`
- `ntdll!NtClose` at `0x140011a87`

## pseudocode

```c
int __fastcall UtilIsNamedEventSet(struct _UNICODE_STRING *a1)
{
  NTSTATUS v1; // eax
  NTSTATUS v3; // ebx
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+30h] [rbp-30h] BYREF
  void *EventHandle; // [rsp+70h] [rbp+10h] BYREF
  __int64 EventInformation; // [rsp+78h] [rbp+18h] BYREF

  ObjectAttributes.ObjectName = a1;
  EventHandle = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  ObjectAttributes.RootDirectory = 0;
  memset(&ObjectAttributes.Attributes, 0, 24);
  EventInformation = 0;
  v1 = NtOpenEvent(&EventHandle, 1u, &ObjectAttributes);
  if ( v1 < 0 )
    return v1 | 0x10000000;
  v3 = NtQueryEvent(EventHandle, EventBasicInformation, &EventInformation, 8u, 0);
  NtClose(EventHandle);
  if ( v3 >= 0 )
    return HIDWORD(EventInformation) == 0;
  else
    return v3 | 0x10000000;
}

```

## disassembly

```asm
0x140011a04  mov     [rsp-8+arg_10], rbx
0x140011a09  push    rbp
0x140011a0a  mov     rbp, rsp
0x140011a0d  sub     rsp, 60h
0x140011a11  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x140011a15  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140011a19  xorps   xmm0, xmm0
0x140011a1c  mov     [rbp+EventHandle], 0
0x140011a24  lea     rcx, [rbp+EventHandle]; EventHandle
0x140011a28  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140011a30  mov     edx, 1; DesiredAccess
0x140011a35  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140011a3d  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140011a42  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x140011a4a  mov     [rbp+EventInformation], 0
0x140011a52  call    cs:__imp_NtOpenEvent
0x140011a58  test    eax, eax
0x140011a5a  jns     short loc_140011A62
0x140011a5c  bts     eax, 1Ch
0x140011a60  jmp     short loc_140011AA1
0x140011a62  mov     rcx, [rbp+EventHandle]; EventHandle
0x140011a66  lea     r8, [rbp+EventInformation]; EventInformation
0x140011a6a  mov     r9d, 8; EventInformationLength
0x140011a70  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x140011a79  xor     edx, edx; EventInformationClass
0x140011a7b  call    cs:__imp_NtQueryEvent
0x140011a81  mov     rcx, [rbp+EventHandle]; Handle
0x140011a85  mov     ebx, eax
0x140011a87  call    cs:__imp_NtClose
0x140011a8d  test    ebx, ebx
0x140011a8f  jns     short loc_140011A99
0x140011a91  bts     ebx, 1Ch
0x140011a95  mov     eax, ebx
0x140011a97  jmp     short loc_140011AA1
0x140011a99  xor     eax, eax
0x140011a9b  cmp     dword ptr [rbp+EventInformation+4], eax
0x140011a9e  setz    al
0x140011aa1  mov     rbx, [rsp+60h+arg_10]
0x140011aa9  add     rsp, 60h
0x140011aad  pop     rbp
0x140011aae  retn
```
