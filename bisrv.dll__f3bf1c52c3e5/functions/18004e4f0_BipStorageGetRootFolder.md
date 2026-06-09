# BipStorageGetRootFolder

- ea: `0x18004e4f0`
- end: `0x18004e609`
- name: `BipStorageGetRootFolder`
- size: `281`
- prototype: `void __fastcall(unsigned __int16 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x1800797e0`

## callees

- `0x180026f8c`
- `0x18002dae4`
- `0x18004e4f0`

## import_xrefs

- `ntdll!NtOpenKey` at `0x18004e574`
- `ntdll!NtOpenKey` at `0x18004e574`
- `ntdll!RtlFreeUnicodeString` at `0x18004e5ee`
- `ntdll!RtlFreeUnicodeString` at `0x18004e5ee`
- `ntdll!RtlInitUnicodeString` at `0x18004e53b`
- `ntdll!RtlInitUnicodeString` at `0x18004e589`
- `ntdll!RtlInitUnicodeString` at `0x18004e53b`
- `ntdll!RtlInitUnicodeString` at `0x18004e589`
- `ntdll!NtClose` at `0x18004e5cc`
- `ntdll!NtClose` at `0x18004e5cc`

## string_xrefs

- `0x18004e513`: `\Registry\Machine\Software\Microsoft\Windows NT\CurrentVersion\BackgroundModel`
- `0x18004e5d6`: `\SystemRoot\System32\Config`

## pseudocode

```c
void __fastcall BipStorageGetRootFolder(unsigned __int16 *a1)
{
  bool v2; // bl
  struct _UNICODE_STRING UnicodeString; // [rsp+20h] [rbp-60h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-50h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+40h] [rbp-40h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+20h] BYREF

  KeyHandle = (void *)-1LL;
  DestinationString = 0;
  v2 = 0;
  ValueName = 0;
  memset(&ObjectAttributes, 0, sizeof(ObjectAttributes));
  UnicodeString = 0;
  RtlInitUnicodeString(
    &DestinationString,
    L"\\Registry\\Machine\\Software\\Microsoft\\Windows NT\\CurrentVersion\\BackgroundModel");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &DestinationString;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  if ( NtOpenKey(&KeyHandle, 0x20019u, &ObjectAttributes) >= 0 )
  {
    RtlInitUnicodeString(&ValueName, L"StorageRoot");
    if ( (int)BipReadRegUnicodeString(KeyHandle, &ValueName, &UnicodeString) >= 0 )
      v2 = (int)RtlStringCchCopyW(a1, 0x100u, UnicodeString.Buffer) >= 0;
  }
  if ( KeyHandle != (void *)-1LL )
    NtClose(KeyHandle);
  if ( !v2 )
    RtlStringCchCopyW(a1, 0x100u, L"\\SystemRoot\\System32\\Config");
  RtlFreeUnicodeString(&UnicodeString);
}

```

## disassembly

```asm
0x18004e4f0  mov     [rsp-8+arg_0], rbx
0x18004e4f5  mov     [rsp-8+arg_8], rdi
0x18004e4fa  push    rbp
0x18004e4fb  mov     rbp, rsp
0x18004e4fe  sub     rsp, 80h
0x18004e505  xorps   xmm0, xmm0
0x18004e508  mov     [rbp+KeyHandle], 0FFFFFFFFFFFFFFFFh
0x18004e510  mov     rdi, rcx
0x18004e513  lea     rdx, aRegistryMachin; "\\Registry\\Machine\\Software\\Microsof"...
0x18004e51a  xorps   xmm1, xmm1
0x18004e51d  lea     rcx, [rbp+DestinationString]; DestinationString
0x18004e521  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x18004e525  xor     bl, bl
0x18004e527  movups  xmmword ptr [rbp+ValueName.Length], xmm1
0x18004e52b  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x18004e52f  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x18004e533  movups  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004e537  movups  xmmword ptr [rbp+UnicodeString.Length], xmm0
0x18004e53b  call    cs:__imp_RtlInitUnicodeString
0x18004e541  lea     rax, [rbp+DestinationString]
0x18004e545  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x18004e54c  xorps   xmm0, xmm0
0x18004e54f  mov     [rbp+ObjectAttributes.ObjectName], rax
0x18004e553  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x18004e557  mov     [rbp+ObjectAttributes.RootDirectory], 0
0x18004e55f  mov     edx, 20019h; DesiredAccess
0x18004e564  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x18004e56b  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x18004e56f  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x18004e574  call    cs:__imp_NtOpenKey
0x18004e57a  test    eax, eax
0x18004e57c  js      short loc_18004E5C2
0x18004e57e  lea     rdx, aStorageroot; "StorageRoot"
0x18004e585  lea     rcx, [rbp+ValueName]; DestinationString
0x18004e589  call    cs:__imp_RtlInitUnicodeString
0x18004e58f  mov     rcx, [rbp+KeyHandle]; KeyHandle
0x18004e593  lea     r8, [rbp+UnicodeString]; DestinationString
0x18004e597  lea     rdx, [rbp+ValueName]; ValueName
0x18004e59b  call    BipReadRegUnicodeString
0x18004e5a0  test    eax, eax
0x18004e5a2  js      short loc_18004E5C2
0x18004e5a4  mov     r8, [rbp+UnicodeString.Buffer]; unsigned __int16 *
0x18004e5a8  mov     edx, 100h; unsigned __int64
0x18004e5ad  mov     rcx, rdi; unsigned __int16 *
0x18004e5b0  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004e5b5  test    eax, eax
0x18004e5b7  movzx   ebx, bl
0x18004e5ba  mov     ecx, 1
0x18004e5bf  cmovns  ebx, ecx
0x18004e5c2  mov     rcx, [rbp+KeyHandle]; Handle
0x18004e5c6  cmp     rcx, 0FFFFFFFFFFFFFFFFh
0x18004e5ca  jz      short loc_18004E5D2
0x18004e5cc  call    cs:__imp_NtClose
0x18004e5d2  test    bl, bl
0x18004e5d4  jnz     short loc_18004E5EA
0x18004e5d6  lea     r8, aSystemrootSyst; "\\SystemRoot\\System32\\Config"
0x18004e5dd  mov     edx, 100h; unsigned __int64
0x18004e5e2  mov     rcx, rdi; unsigned __int16 *
0x18004e5e5  call    ?RtlStringCchCopyW@@YAJPEAG_KPEBG@Z; RtlStringCchCopyW(ushort *,unsigned __int64,ushort const *)
0x18004e5ea  lea     rcx, [rbp+UnicodeString]; UnicodeString
0x18004e5ee  call    cs:__imp_RtlFreeUnicodeString
0x18004e5f4  lea     r11, [rsp+80h+var_s0]
0x18004e5fc  mov     rbx, [r11+10h]
0x18004e600  mov     rdi, [r11+18h]
0x18004e604  mov     rsp, r11
0x18004e607  pop     rbp
0x18004e608  retn
```
