# SignalLsaIsoReady

- ea: `0x1400064a0`
- end: `0x1400065b6`
- name: `SignalLsaIsoReady`
- size: `278`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `2`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x14000685c`

## callees

- `0x1400010bc`
- `0x1400064a0`

## import_xrefs

- `IUMBASE!IsSecureProcess` at `0x1400064d8`
- `IUMBASE!IsSecureProcess` at `0x1400064d8`
- `ntdll!NtSetEvent` at `0x140006561`
- `ntdll!NtSetEvent` at `0x140006561`
- `ntdll!NtClose` at `0x1400065a0`
- `ntdll!NtClose` at `0x1400065a0`
- `ntdll!RtlInitUnicodeString` at `0x1400064f4`
- `ntdll!RtlInitUnicodeString` at `0x1400064f4`
- `ntdll!NtOpenEvent` at `0x14000652d`
- `ntdll!NtOpenEvent` at `0x14000652d`

## string_xrefs

- `0x1400064de`: `\LSA_ISO_READY`
- `0x1400064cf`: `\LSA_ISO_READY_LAUNCHED_AFTER_BOOT`
- `0x1400064e9`: `\LSA_ISO_READY_D`

## pseudocode

```c
__int64 __fastcall SignalLsaIsoReady(int a1)
{
  const WCHAR *v1; // rdx
  int v2; // eax
  NTSTATUS v3; // ebx
  int v4; // r8d
  int v5; // r9d
  int *v7; // rdx
  _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-40h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+40h] [rbp-30h] BYREF
  NTSTATUS v10; // [rsp+80h] [rbp+10h] BYREF
  void *EventHandle; // [rsp+88h] [rbp+18h] BYREF

  EventHandle = 0;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  if ( a1 )
  {
    v1 = L"\\LSA_ISO_READY_LAUNCHED_AFTER_BOOT";
  }
  else
  {
    v2 = IsSecureProcess();
    v1 = L"\\LSA_ISO_READY";
    if ( !v2 )
      v1 = L"\\LSA_ISO_READY_D";
  }
  RtlInitUnicodeString(&DestinationString, v1);
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v3 = NtOpenEvent(&EventHandle, 2u, &ObjectAttributes);
  if ( v3 == -1073741772 )
    return 3221225701LL;
  if ( v3 >= 0 )
  {
    v3 = NtSetEvent(EventHandle, 0);
    if ( v3 < 0 && (unsigned int)dword_140052018 > 2 )
    {
      v7 = (int *)byte_14004C84D;
      goto LABEL_13;
    }
  }
  else if ( (unsigned int)dword_140052018 > 2 )
  {
    v7 = &dword_14004C9CC;
LABEL_13:
    v10 = v3;
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(
      (unsigned int)&dword_140052018,
      (_DWORD)v7,
      v4,
      v5,
      (__int64)&v10);
  }
  if ( EventHandle )
    NtClose(EventHandle);
  return (unsigned int)v3;
}

```

## disassembly

```asm
0x1400064a0  mov     [rsp-8+arg_10], rbx
0x1400064a5  push    rbp
0x1400064a6  mov     rbp, rsp
0x1400064a9  sub     rsp, 70h
0x1400064ad  mov     [rbp+EventHandle], 0
0x1400064b5  xorps   xmm1, xmm1
0x1400064b8  xorps   xmm0, xmm0
0x1400064bb  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x1400064bf  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm1
0x1400064c3  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm1
0x1400064c7  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm1
0x1400064cb  test    ecx, ecx
0x1400064cd  jz      short loc_1400064D8
0x1400064cf  lea     rdx, aLsaIsoReadyLau; "\\LSA_ISO_READY_LAUNCHED_AFTER_BOOT"
0x1400064d6  jmp     short loc_1400064F0
0x1400064d8  call    cs:__imp_IsSecureProcess
0x1400064de  lea     rdx, aLsaIsoReady; "\\LSA_ISO_READY"
0x1400064e5  test    eax, eax
0x1400064e7  jnz     short loc_1400064F0
0x1400064e9  lea     rdx, SourceString; "\\LSA_ISO_READY_D"
0x1400064f0  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400064f4  call    cs:__imp_RtlInitUnicodeString
0x1400064fa  lea     rax, [rbp+DestinationString]
0x1400064fe  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x140006505  xorps   xmm0, xmm0
0x140006508  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000650c  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x140006510  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x140006518  mov     edx, 2; DesiredAccess
0x14000651d  mov     [rbp+ObjectAttributes.Attributes], 0
0x140006524  lea     rcx, [rbp+EventHandle]; EventHandle
0x140006528  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000652d  call    cs:__imp_NtOpenEvent
0x140006533  mov     ebx, eax
0x140006535  cmp     eax, 0C0000034h
0x14000653a  jnz     short loc_140006543
0x14000653c  mov     eax, 0C00000E5h
0x140006541  jmp     short loc_1400065A8
0x140006543  test    ebx, ebx
0x140006545  jns     short loc_14000655B
0x140006547  mov     eax, cs:dword_140052018
0x14000654d  cmp     eax, 2
0x140006550  jbe     short loc_140006597
0x140006552  lea     rdx, dword_14004C9CC
0x140006559  jmp     short loc_14000657F
0x14000655b  mov     rcx, [rbp+EventHandle]; EventHandle
0x14000655f  xor     edx, edx; PreviousState
0x140006561  call    cs:__imp_NtSetEvent
0x140006567  mov     ebx, eax
0x140006569  test    eax, eax
0x14000656b  jns     short loc_140006597
0x14000656d  mov     eax, cs:dword_140052018
0x140006573  cmp     eax, 2
0x140006576  jbe     short loc_140006597
0x140006578  lea     rdx, byte_14004C84D
0x14000657f  lea     rax, [rbp+arg_0]
0x140006583  mov     [rsp+70h+var_50], rax
0x140006588  lea     rcx, dword_140052018
0x14000658f  mov     [rbp+arg_0], ebx
0x140006592  call    ??$Write@U?$_tlgWrapperByVal@$03@@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &)
0x140006597  mov     rcx, [rbp+EventHandle]; Handle
0x14000659b  test    rcx, rcx
0x14000659e  jz      short loc_1400065A6
0x1400065a0  call    cs:__imp_NtClose
0x1400065a6  mov     eax, ebx
0x1400065a8  mov     rbx, [rsp+70h+arg_10]
0x1400065b0  add     rsp, 70h
0x1400065b4  pop     rbp
0x1400065b5  retn
```
