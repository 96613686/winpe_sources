# HCI_CleanupHidStateHack(HCI_INTERFACE *,unsigned __int64 *)

- ea: `0x140052f74`
- end: `0x14005310d`
- name: `?HCI_CleanupHidStateHack@@YAXPEAUHCI_INTERFACE@@PEA_K@Z`
- size: `409`
- prototype: `void __fastcall(struct HCI_INTERFACE *, unsigned __int64 *)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, service_task, broker_com_uri`

## callers

- `0x14005d3a0`

## callees

- `0x140020330`
- `0x140020414`
- `0x140052f74`
- `0x140067e8c`
- `0x140165540`

## import_xrefs

- `ntoskrnl!ZwOpenKey` at `0x1400530b4`
- `ntoskrnl!ZwOpenKey` at `0x1400530b4`
- `ntoskrnl!ZwDeleteKey` at `0x1400530c9`
- `ntoskrnl!ZwDeleteKey` at `0x1400530c9`
- `ntoskrnl!ZwClose` at `0x1400530df`
- `ntoskrnl!ZwClose` at `0x1400530df`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005306d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14005306d`

## string_xrefs

- `0x140052fa8`: `\Registry\Machine\System\CurrentControlSet\Services\HIDBTH\Parameters\Devices\`

## pseudocode

```c
void __fastcall HCI_CleanupHidStateHack(struct HCI_INTERFACE *a1, unsigned __int64 *a2)
{
  __int64 v3; // r11
  __int64 v4; // [rsp+20h] [rbp-E0h]
  void *KeyHandle; // [rsp+30h] [rbp-D0h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+38h] [rbp-C8h] BYREF
  _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+48h] [rbp-B8h] BYREF
  unsigned __int16 v8[20]; // [rsp+78h] [rbp-88h] BYREF
  WCHAR SourceString[104]; // [rsp+A0h] [rbp-60h] BYREF

  KeyHandle = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  DestinationString = 0;
  if ( (int)RtlStringCbCopyW(
              SourceString,
              0xD0u,
              L"\\Registry\\Machine\\System\\CurrentControlSet\\Services\\HIDBTH\\Parameters\\Devices\\") >= 0
    && (int)RtlStringCbPrintfW(v8, 0x1Au, L"%04x%08x", *(unsigned __int16 *)(v3 + 296), *(_DWORD *)(v3 + 292)) >= 0
    && RtlStringCbCatW(SourceString, 0xD0u, v8) >= 0 )
  {
    LODWORD(v4) = *(_DWORD *)a2;
    if ( (int)RtlStringCbPrintfW(v8, 0x1Au, L"%04x%08x", *((unsigned __int16 *)a2 + 2), v4) >= 0
      && RtlStringCbCatW(SourceString, 0xD0u, v8) >= 0 )
    {
      RtlInitUnicodeString(&DestinationString, SourceString);
      ObjectAttributes.Length = 48;
      ObjectAttributes.ObjectName = &DestinationString;
      ObjectAttributes.RootDirectory = 0;
      ObjectAttributes.Attributes = 576;
      *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
      if ( ZwOpenKey(&KeyHandle, 0xF003Fu, &ObjectAttributes) >= 0 )
        ZwDeleteKey(KeyHandle);
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
}

```

## disassembly

```asm
0x140052f74  mov     [rsp-8+arg_10], rbx
0x140052f79  mov     [rsp-8+arg_18], rdi
0x140052f7e  push    rbp
0x140052f7f  lea     rbp, [rsp-80h]
0x140052f84  sub     rsp, 180h
0x140052f8b  mov     rax, cs:__security_cookie
0x140052f92  xor     rax, rsp
0x140052f95  mov     [rbp+80h+var_10], rax
0x140052f99  xorps   xmm0, xmm0
0x140052f9c  mov     [rsp+180h+KeyHandle], 0
0x140052fa5  mov     rbx, rdx
0x140052fa8  lea     r8, aRegistryMachin_3; "\\Registry\\Machine\\System\\CurrentCon"...
0x140052faf  mov     r11, rcx
0x140052fb2  mov     edi, 0D0h
0x140052fb7  mov     edx, edi; unsigned __int64
0x140052fb9  lea     rcx, [rbp+80h+SourceString]; unsigned __int16 *
0x140052fbd  movups  xmmword ptr [rsp+180h+ObjectAttributes.Length], xmm0
0x140052fc2  movups  xmmword ptr [rsp+180h+ObjectAttributes.ObjectName], xmm0
0x140052fc7  movups  xmmword ptr [rsp+180h+ObjectAttributes.SecurityDescriptor], xmm0
0x140052fcc  movups  xmmword ptr [rsp+180h+DestinationString.Length], xmm0
0x140052fd1  call    ?RtlStringCbCopyW@@YAJPEAG_KPEBG@Z; RtlStringCbCopyW(ushort *,unsigned __int64,ushort const *)
0x140052fd6  test    eax, eax
0x140052fd8  js      loc_1400530D5
0x140052fde  mov     eax, [r11+124h]
0x140052fe5  lea     r8, a04x08x; "%04x%08x"
0x140052fec  movzx   r9d, word ptr [r11+128h]
0x140052ff4  lea     rcx, [rsp+180h+var_108]; unsigned __int16 *
0x140052ff9  mov     edx, 1Ah; unsigned __int64
0x140052ffe  mov     [rsp+180h+var_160], eax
0x140053002  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140053007  test    eax, eax
0x140053009  js      loc_1400530D5
0x14005300f  lea     r8, [rsp+180h+var_108]; unsigned __int16 *
0x140053014  mov     edx, edi; unsigned __int64
0x140053016  lea     rcx, [rbp+80h+SourceString]; unsigned __int16 *
0x14005301a  call    ?RtlStringCbCatW@@YAJPEAG_KPEBG@Z; RtlStringCbCatW(ushort *,unsigned __int64,ushort const *)
0x14005301f  test    eax, eax
0x140053021  js      loc_1400530D5
0x140053027  mov     eax, [rbx]
0x140053029  lea     r8, a04x08x; "%04x%08x"
0x140053030  movzx   r9d, word ptr [rbx+4]
0x140053035  lea     rcx, [rsp+180h+var_108]; unsigned __int16 *
0x14005303a  mov     edx, 1Ah; unsigned __int64
0x14005303f  mov     [rsp+180h+var_160], eax
0x140053043  call    ?RtlStringCbPrintfW@@YAJPEAG_KPEBGZZ; RtlStringCbPrintfW(ushort *,unsigned __int64,ushort const *,...)
0x140053048  test    eax, eax
0x14005304a  js      loc_1400530D5
0x140053050  lea     r8, [rsp+180h+var_108]; unsigned __int16 *
0x140053055  mov     edx, edi; unsigned __int64
0x140053057  lea     rcx, [rbp+80h+SourceString]; unsigned __int16 *
0x14005305b  call    ?RtlStringCbCatW@@YAJPEAG_KPEBG@Z; RtlStringCbCatW(ushort *,unsigned __int64,ushort const *)
0x140053060  test    eax, eax
0x140053062  js      short loc_1400530D5
0x140053064  lea     rdx, [rbp+80h+SourceString]; SourceString
0x140053068  lea     rcx, [rsp+180h+DestinationString]; DestinationString
0x14005306d  call    cs:__imp_RtlInitUnicodeString
0x140053074  nop     dword ptr [rax+rax+00h]
0x140053079  lea     rax, [rsp+180h+DestinationString]
0x14005307e  mov     [rsp+180h+ObjectAttributes.Length], 30h ; '0'
0x140053086  xorps   xmm0, xmm0
0x140053089  mov     [rsp+180h+ObjectAttributes.ObjectName], rax
0x14005308e  lea     r8, [rsp+180h+ObjectAttributes]; ObjectAttributes
0x140053093  mov     [rsp+180h+ObjectAttributes.RootDirectory], 0
0x14005309c  mov     edx, 0F003Fh; DesiredAccess
0x1400530a1  mov     [rsp+180h+ObjectAttributes.Attributes], 240h
0x1400530a9  lea     rcx, [rsp+180h+KeyHandle]; KeyHandle
0x1400530ae  movdqu  xmmword ptr [rsp+180h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400530b4  call    cs:__imp_ZwOpenKey
0x1400530bb  nop     dword ptr [rax+rax+00h]
0x1400530c0  test    eax, eax
0x1400530c2  js      short loc_1400530D5
0x1400530c4  mov     rcx, [rsp+180h+KeyHandle]; KeyHandle
0x1400530c9  call    cs:__imp_ZwDeleteKey
0x1400530d0  nop     dword ptr [rax+rax+00h]
0x1400530d5  mov     rcx, [rsp+180h+KeyHandle]; Handle
0x1400530da  test    rcx, rcx
0x1400530dd  jz      short loc_1400530EB
0x1400530df  call    cs:__imp_ZwClose
0x1400530e6  nop     dword ptr [rax+rax+00h]
0x1400530eb  mov     rcx, [rbp+80h+var_10]
0x1400530ef  xor     rcx, rsp; StackCookie
0x1400530f2  call    __security_check_cookie
0x1400530f7  lea     r11, [rsp+180h+var_s0]
0x1400530ff  mov     rbx, [r11+20h]
0x140053103  mov     rdi, [r11+28h]
0x140053107  mov     rsp, r11
0x14005310a  pop     rbp
0x14005310b  retn
```
