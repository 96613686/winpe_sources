# EapCreateAggregatedEventNode

- ea: `0x180009848`
- end: `0x180009937`
- name: `EapCreateAggregatedEventNode`
- size: `239`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800095e0`
- `0x18000ad20`
- `0x18000aec4`

## callees

- `0x180009848`

## import_xrefs

- `ntdll!ZwClose` at `0x180009923`
- `ntdll!ZwClose` at `0x180009923`
- `ntdll!ZwCreateKey` at `0x1800098e1`
- `ntdll!ZwCreateKey` at `0x1800098e1`
- `ntdll!RtlFreeUnicodeString` at `0x180009914`
- `ntdll!RtlFreeUnicodeString` at `0x180009914`
- `ntdll!RtlStringFromGUID` at `0x180009889`
- `ntdll!RtlStringFromGUID` at `0x180009889`

## pseudocode

```c
__int64 __fastcall EapCreateAggregatedEventNode(void *a1, const GUID *a2, void **a3)
{
  NTSTATUS v5; // ebx
  void *KeyHandle; // [rsp+40h] [rbp-19h] BYREF
  struct _UNICODE_STRING GuidString; // [rsp+48h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-1h] BYREF
  ULONG Disposition; // [rsp+D8h] [rbp+7Fh] BYREF

  Disposition = 0;
  *(_QWORD *)&GuidString.Length = 0;
  KeyHandle = 0;
  GuidString.Buffer = 0;
  memset(&ObjectAttributes, 0, 44);
  v5 = RtlStringFromGUID(a2, &GuidString);
  if ( v5 >= 0 )
  {
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = &GuidString;
    ObjectAttributes.RootDirectory = a1;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v5 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
    if ( v5 >= 0 )
    {
      if ( Disposition == 1 )
      {
        *a3 = KeyHandle;
        KeyHandle = 0;
      }
      else
      {
        v5 = -1073741771;
      }
    }
  }
  if ( GuidString.Buffer )
    RtlFreeUnicodeString(&GuidString);
  if ( KeyHandle )
    ZwClose(KeyHandle);
  return (unsigned int)v5;
}

```

## disassembly

```asm
0x180009848  push    rbp
0x18000984a  push    rbx
0x18000984b  push    rsi
0x18000984c  push    rdi
0x18000984d  lea     rbp, [rsp-3Fh]
0x180009852  sub     rsp, 98h
0x180009859  xor     eax, eax
0x18000985b  xorps   xmm0, xmm0
0x18000985e  mov     r9, rdx
0x180009861  mov     [rbp+57h+arg_18], eax
0x180009864  mov     rsi, rcx
0x180009867  mov     qword ptr [rbp+57h+GuidString.Length], rax
0x18000986b  movups  xmmword ptr [rbp+57h+ObjectAttributes.ObjectName], xmm0
0x18000986f  mov     rcx, r9; Guid
0x180009872  mov     [rbp+57h+KeyHandle], rax
0x180009876  lea     rdx, [rbp+57h+GuidString]; GuidString
0x18000987a  mov     [rbp+57h+GuidString.Buffer], rax
0x18000987e  movups  xmmword ptr [rbp+57h+ObjectAttributes+1Ch], xmm0
0x180009882  mov     rdi, r8
0x180009885  movups  xmmword ptr [rbp+57h+ObjectAttributes.Length], xmm0
0x180009889  call    cs:__imp_RtlStringFromGUID
0x18000988f  mov     ebx, eax
0x180009891  test    eax, eax
0x180009893  js      short loc_180009909
0x180009895  lea     rax, [rbp+57h+GuidString]
0x180009899  mov     [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1800098a0  mov     [rbp+57h+ObjectAttributes.ObjectName], rax
0x1800098a4  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x1800098a8  lea     rax, [rbp+57h+arg_18]
0x1800098ac  mov     [rbp+57h+ObjectAttributes.RootDirectory], rsi
0x1800098b0  mov     [rsp+0B0h+Disposition], rax; Disposition
0x1800098b5  lea     rcx, [rbp+57h+KeyHandle]; KeyHandle
0x1800098b9  xorps   xmm0, xmm0
0x1800098bc  mov     [rsp+0B0h+CreateOptions], 0; CreateOptions
0x1800098c4  xor     r9d, r9d; TitleIndex
0x1800098c7  mov     [rsp+0B0h+Class], 0; Class
0x1800098d0  mov     edx, 0F003Fh; DesiredAccess
0x1800098d5  mov     [rbp+57h+ObjectAttributes.Attributes], 40h ; '@'
0x1800098dc  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800098e1  call    cs:__imp_ZwCreateKey
0x1800098e7  mov     ebx, eax
0x1800098e9  test    eax, eax
0x1800098eb  js      short loc_180009909
0x1800098ed  cmp     [rbp+57h+arg_18], 1
0x1800098f1  jz      short loc_1800098FA
0x1800098f3  mov     ebx, 0C0000035h
0x1800098f8  jmp     short loc_180009909
0x1800098fa  mov     rax, [rbp+57h+KeyHandle]
0x1800098fe  mov     [rdi], rax
0x180009901  mov     [rbp+57h+KeyHandle], 0
0x180009909  cmp     [rbp+57h+GuidString.Buffer], 0
0x18000990e  jz      short loc_18000991A
0x180009910  lea     rcx, [rbp+57h+GuidString]; UnicodeString
0x180009914  call    cs:__imp_RtlFreeUnicodeString
0x18000991a  mov     rcx, [rbp+57h+KeyHandle]; Handle
0x18000991e  test    rcx, rcx
0x180009921  jz      short loc_180009929
0x180009923  call    cs:__imp_ZwClose
0x180009929  mov     eax, ebx
0x18000992b  add     rsp, 98h
0x180009932  pop     rdi
0x180009933  pop     rsi
0x180009934  pop     rbx
0x180009935  pop     rbp
0x180009936  retn
```
