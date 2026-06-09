# MpSavePreventPagingFileAbuseConfig

- ea: `0x140074f80`
- end: `0x140075105`
- name: `MpSavePreventPagingFileAbuseConfig`
- size: `389`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x14005be60`

## callees

- `0x1400051bc`
- `0x1400118d0`
- `0x140074f80`

## import_xrefs

- `ntoskrnl!ZwSetValueKey` at `0x140075077`
- `ntoskrnl!ZwSetValueKey` at `0x140075077`
- `ntoskrnl!ZwOpenKey` at `0x140075026`
- `ntoskrnl!ZwOpenKey` at `0x140075026`
- `ntoskrnl!RtlInitUnicodeString` at `0x140074fe7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140075049`
- `ntoskrnl!RtlInitUnicodeString` at `0x140074fe7`
- `ntoskrnl!RtlInitUnicodeString` at `0x140075049`
- `ntoskrnl!ZwClose` at `0x1400750d9`
- `ntoskrnl!ZwClose` at `0x1400750d9`

## pseudocode

```c
NTSTATUS MpSavePreventPagingFileAbuseConfig()
{
  NTSTATUS result; // eax
  NTSTATUS v1; // ebx
  void *KeyHandle; // [rsp+30h] [rbp-9h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-1h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+68h] [rbp+2Fh] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+78h] [rbp+3Fh] BYREF

  KeyHandle = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  ValueName = 0;
  if ( !*(_QWORD *)(MpData + 584) )
    return -1073741811;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(MpData + 584));
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 576;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = ZwOpenKey(&KeyHandle, 2u, &ObjectAttributes);
  if ( result >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"PreventPagingFileAbuse");
    v1 = ZwSetValueKey(KeyHandle, &ValueName, 0, 4u, &dword_140026A20, 4u);
    if ( v1 < 0
      && WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
      && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0 )
    {
      _mm_lfence();
      WPP_SF_qD(
        WPP_GLOBAL_Control->AttachedDevice,
        54,
        WPP_b960013237753183ac7a6d55d666ce86_Traceguids,
        KeGetCurrentThread(),
        v1);
    }
    if ( KeyHandle )
      ZwClose(KeyHandle);
    return v1;
  }
  else
  {
    _mm_lfence();
  }
  return result;
}

```

## disassembly

```asm
0x140074f80  mov     [rsp-8+arg_0], rbx
0x140074f85  push    rbp
0x140074f86  lea     rbp, [rsp-57h]
0x140074f8b  sub     rsp, 90h
0x140074f92  mov     rax, cs:__security_cookie
0x140074f99  xor     rax, rsp
0x140074f9c  mov     [rbp+57h+var_8], rax
0x140074fa0  mov     rdx, cs:MpData
0x140074fa7  xorps   xmm0, xmm0
0x140074faa  mov     [rbp+57h+KeyHandle], 0
0x140074fb2  mov     dword ptr [rbp+57h+ObjectAttributes+4], 0
0x140074fb9  mov     dword ptr [rbp+57h+ObjectAttributes+1Ch], 0
0x140074fc0  movups  xmmword ptr [rbp+57h+ValueName.Length], xmm0
0x140074fc4  cmp     qword ptr [rdx+248h], 0
0x140074fcc  jnz     short loc_140074FD8
0x140074fce  mov     eax, 0C000000Dh
0x140074fd3  jmp     loc_1400750E7
0x140074fd8  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm0
0x140074fdc  mov     rdx, [rdx+248h]; SourceString
0x140074fe3  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140074fe7  call    cs:__imp_RtlInitUnicodeString
0x140074fee  nop     dword ptr [rax+rax+00h]
0x140074ff3  lea     rax, [rbp+57h+DestinationString]
0x140074ff7  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x140074ffe  xorps   xmm0, xmm0
0x140075001  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x140075005  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140075009  mov     [rbp+57h+ObjectAttributes.RootDirectory], 0
0x140075011  mov     edx, 2; DesiredAccess
0x140075016  mov     [rbp+57h+ObjectAttributes.Attributes], 240h
0x14007501d  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140075021  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x140075026  call    cs:__imp_ZwOpenKey
0x14007502d  nop     dword ptr [rax+rax+00h]
0x140075032  test    eax, eax
0x140075034  jns     short loc_14007503E
0x140075036  lfence
0x140075039  jmp     loc_1400750E7
0x14007503e  lea     rdx, aPreventpagingf; "PreventPagingFileAbuse"
0x140075045  lea     rcx, [rbp+57h+ValueName]; DestinationString
0x140075049  call    cs:__imp_RtlInitUnicodeString
0x140075050  nop     dword ptr [rax+rax+00h]
0x140075055  mov     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x140075059  lea     rax, dword_140026A20
0x140075060  mov     r9d, 4; Type
0x140075066  lea     rdx, [rbp+57h+ValueName]; ValueName
0x14007506a  mov     [rsp+90h+DataSize], r9d; DataSize
0x14007506f  xor     r8d, r8d; TitleIndex
0x140075072  mov     [rsp+90h+Data], rax; Data
0x140075077  call    cs:__imp_ZwSetValueKey
0x14007507e  nop     dword ptr [rax+rax+00h]
0x140075083  mov     ebx, eax
0x140075085  test    eax, eax
0x140075087  jns     short loc_1400750D0
0x140075089  mov     rcx, cs:WPP_GLOBAL_Control
0x140075090  lea     rax, WPP_GLOBAL_Control
0x140075097  cmp     rcx, rax
0x14007509a  jz      short loc_1400750D0
0x14007509c  mov     ecx, [rcx+2Ch]
0x14007509f  test    cl, 1
0x1400750a2  jz      short loc_1400750D0
0x1400750a4  lfence
0x1400750a7  mov     r9, gs:188h
0x1400750b0  lea     r8, WPP_b960013237753183ac7a6d55d666ce86_Traceguids
0x1400750b7  mov     rcx, cs:WPP_GLOBAL_Control
0x1400750be  mov     edx, 36h ; '6'
0x1400750c3  mov     dword ptr [rsp+90h+Data], ebx
0x1400750c7  mov     rcx, [rcx+18h]
0x1400750cb  call    WPP_SF_qD
0x1400750d0  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x1400750d4  test    rcx, rcx
0x1400750d7  jz      short loc_1400750E5
0x1400750d9  call    cs:__imp_ZwClose
0x1400750e0  nop     dword ptr [rax+rax+00h]
0x1400750e5  mov     eax, ebx
0x1400750e7  mov     rcx, [rbp+57h+var_8]
0x1400750eb  xor     rcx, rsp; StackCookie
0x1400750ee  call    __security_check_cookie
0x1400750f3  mov     rbx, [rsp+90h+arg_0]
0x1400750fb  add     rsp, 90h
0x140075102  pop     rbp
0x140075103  retn
```
