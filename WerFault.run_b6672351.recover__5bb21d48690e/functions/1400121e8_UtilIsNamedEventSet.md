# UtilIsNamedEventSet

- ea: `0x1400121e8`
- end: `0x1400122a6`
- name: `UtilIsNamedEventSet`
- size: `190`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `reparse_path, loader_planting`

## callers

- `0x1400251c0`

## callees

- `0x1400121e8`

## import_xrefs

- `ntdll!NtQueryEvent` at `0x140012265`
- `ntdll!NtQueryEvent` at `0x140012265`
- `ntdll!NtOpenEvent` at `0x140012236`
- `ntdll!NtOpenEvent` at `0x140012236`
- `ntdll!NtClose` at `0x140012277`
- `ntdll!NtClose` at `0x140012277`

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
0x1400121e8  mov     [rsp-8+arg_10], rbx
0x1400121ed  push    rbp
0x1400121ee  mov     rbp, rsp
0x1400121f1  sub     rsp, 60h
0x1400121f5  mov     [rbp+ObjectAttributes.ObjectName], rcx
0x1400121f9  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x1400121fd  xorps   xmm0, xmm0
0x140012200  mov     [rbp+EventHandle], 0
0x140012208  lea     rcx, [rbp+EventHandle]; EventHandle
0x14001220c  mov     qword ptr [rbp+ObjectAttributes.Length], 30h ; '0'
0x140012214  mov     edx, 1; DesiredAccess
0x140012219  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140012221  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x140012226  mov     qword ptr [rbp+ObjectAttributes.Attributes], 0
0x14001222e  mov     [rbp+EventInformation], 0
0x140012236  call    cs:__imp_NtOpenEvent
0x14001223d  nop     dword ptr [rax+rax+00h]
0x140012242  test    eax, eax
0x140012244  jns     short loc_14001224C
0x140012246  bts     eax, 1Ch
0x14001224a  jmp     short loc_140012297
0x14001224c  mov     rcx, [rbp+EventHandle]; EventHandle
0x140012250  lea     r8, [rbp+EventInformation]; EventInformation
0x140012254  mov     r9d, 8; EventInformationLength
0x14001225a  mov     [rsp+60h+ReturnLength], 0; ReturnLength
0x140012263  xor     edx, edx; EventInformationClass
0x140012265  call    cs:__imp_NtQueryEvent
0x14001226c  nop     dword ptr [rax+rax+00h]
0x140012271  mov     rcx, [rbp+EventHandle]; Handle
0x140012275  mov     ebx, eax
0x140012277  call    cs:__imp_NtClose
0x14001227e  nop     dword ptr [rax+rax+00h]
0x140012283  test    ebx, ebx
0x140012285  jns     short loc_14001228F
0x140012287  bts     ebx, 1Ch
0x14001228b  mov     eax, ebx
0x14001228d  jmp     short loc_140012297
0x14001228f  xor     eax, eax
0x140012291  cmp     dword ptr [rbp+EventInformation+4], eax
0x140012294  setz    al
0x140012297  mov     rbx, [rsp+60h+arg_10]
0x14001229f  add     rsp, 60h
0x1400122a3  pop     rbp
0x1400122a4  retn
```
