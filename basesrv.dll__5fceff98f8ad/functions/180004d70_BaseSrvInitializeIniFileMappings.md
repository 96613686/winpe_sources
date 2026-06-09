# BaseSrvInitializeIniFileMappings

- ea: `0x180004d70`
- end: `0x1800051f5`
- name: `BaseSrvInitializeIniFileMappings`
- size: `1157`
- prototype: `__int64(void)`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002f10`

## callees

- `0x180004d70`
- `0x180005200`
- `0x180005b60`
- `0x180005c10`
- `0x18000ced4`
- `0x18000db40`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180004e28`
- `ntdll!RtlAllocateHeap` at `0x180004f6a`
- `ntdll!RtlAllocateHeap` at `0x1800050eb`
- `ntdll!RtlAllocateHeap` at `0x180004e28`
- `ntdll!RtlAllocateHeap` at `0x180004f6a`
- `ntdll!RtlAllocateHeap` at `0x1800050eb`
- `ntdll!NtOpenKey` at `0x180004e95`
- `ntdll!NtOpenKey` at `0x1800050b5`
- `ntdll!NtOpenKey` at `0x180004e95`
- `ntdll!NtOpenKey` at `0x1800050b5`
- `ntdll!NtQueryValueKey` at `0x180004ee0`
- `ntdll!NtQueryValueKey` at `0x180004ee0`
- `ntdll!NtClose` at `0x180005175`
- `ntdll!NtClose` at `0x18000518d`
- `ntdll!NtClose` at `0x1800051ad`
- `ntdll!NtClose` at `0x1800051ca`
- `ntdll!NtClose` at `0x180005175`
- `ntdll!NtClose` at `0x18000518d`
- `ntdll!NtClose` at `0x1800051ad`
- `ntdll!NtClose` at `0x1800051ca`
- `ntdll!RtlCopyUnicodeString` at `0x180004fa0`
- `ntdll!RtlCopyUnicodeString` at `0x180005125`
- `ntdll!RtlCopyUnicodeString` at `0x180004fa0`
- `ntdll!RtlCopyUnicodeString` at `0x180005125`
- `ntdll!NtEnumerateKey` at `0x18000504f`
- `ntdll!NtEnumerateKey` at `0x18000504f`
- `ntdll!RtlEqualUnicodeString` at `0x18000514f`
- `ntdll!RtlEqualUnicodeString` at `0x18000514f`
- `ntdll!RtlInitUnicodeString` at `0x180004ded`
- `ntdll!RtlInitUnicodeString` at `0x180004e00`
- `ntdll!RtlInitUnicodeString` at `0x180004e56`
- `ntdll!RtlInitUnicodeString` at `0x180004eaf`
- `ntdll!RtlInitUnicodeString` at `0x180004ded`
- `ntdll!RtlInitUnicodeString` at `0x180004e00`
- `ntdll!RtlInitUnicodeString` at `0x180004e56`
- `ntdll!RtlInitUnicodeString` at `0x180004eaf`

## string_xrefs

- `0x180004e44`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\IniFileMapping`

## pseudocode

```c
int BaseSrvInitializeIniFileMappings()
{
  __int64 v0; // rbx
  PVOID Heap; // rax
  int result; // eax
  NTSTATUS v3; // eax
  __int64 v4; // rdi
  __int64 *v5; // rax
  __int64 *i; // rdi
  char *v7; // rax
  __int64 v8; // rcx
  __int64 v9; // rbx
  int v10; // eax
  ULONG v11; // edi
  _QWORD *v12; // r14
  NTSTATUS v13; // eax
  int v14; // ebx
  char *v15; // rax
  __int64 v16; // rsi
  ULONG ResultLength; // [rsp+30h] [rbp-D0h] BYREF
  HANDLE Handle; // [rsp+38h] [rbp-C8h] BYREF
  void *KeyHandle; // [rsp+40h] [rbp-C0h] BYREF
  UNICODE_STRING SourceString; // [rsp+48h] [rbp-B8h] BYREF
  UNICODE_STRING v21; // [rsp+58h] [rbp-A8h] BYREF
  __int64 v22; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+70h] [rbp-90h] BYREF
  struct _UNICODE_STRING v24; // [rsp+A0h] [rbp-60h] BYREF
  struct _UNICODE_STRING ValueName; // [rsp+B0h] [rbp-50h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+C0h] [rbp-40h] BYREF
  _BYTE KeyValueInformation[12]; // [rsp+D0h] [rbp-30h] BYREF
  wchar_t v28; // [rsp+DCh] [rbp-24h] BYREF
  char v29; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v30; // [rsp+4CEh] [rbp+3CEh]

  v0 = BaseSrvpStaticServerData;
  KeyHandle = 0;
  v22 = 0;
  v24 = 0;
  ResultLength = 0;
  memset(&ObjectAttributes, 0, 44);
  Handle = 0;
  ValueName = 0;
  v21 = 0;
  DestinationString = 0;
  SourceString = 0;
  RtlInitUnicodeString(&DestinationString, L"win.ini");
  RtlInitUnicodeString(&SourceString, 0);
  Heap = RtlAllocateHeap(BaseSrvSharedHeap, (BaseSrvSharedTag + 0x40000) | 8, 0x20u);
  BaseSrvIniFileMapping = (__int64)Heap;
  if ( !Heap )
    return -1073741801;
  *(_QWORD *)(v0 + 368) = Heap;
  RtlInitUnicodeString(&v24, L"\\REGISTRY\\MACHINE\\SOFTWARE\\Microsoft\\Windows NT\\CurrentVersion\\IniFileMapping");
  ObjectAttributes.Length = 48;
  ObjectAttributes.ObjectName = &v24;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.Attributes = 64;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  result = NtOpenKey(&KeyHandle, 0x80000000, &ObjectAttributes);
  if ( result < 0 )
    return result;
  RtlInitUnicodeString(&ValueName, 0);
  v3 = NtQueryValueKey(KeyHandle, &ValueName, KeyValuePartialInformation, KeyValueInformation, 0x400u, &ResultLength);
  v30 = 0;
  if ( v3 >= 0 )
  {
    result = BaseSrvSaveFileNameMapping(&SourceString, (_QWORD *)(BaseSrvIniFileMapping + 8));
    if ( result < 0 )
      return result;
    v4 = *(_QWORD *)(BaseSrvIniFileMapping + 8);
    if ( SourceString.Length )
    {
      v5 = *(__int64 **)(v4 + 24);
      for ( i = (__int64 *)(v4 + 24); v5; v5 = (__int64 *)*v5 )
        i = v5;
    }
    else
    {
      i = (__int64 *)(v4 + 32);
    }
    v7 = (char *)RtlAllocateHeap(BaseSrvSharedHeap, (BaseSrvSharedTag + 0x40000) | 8, SourceString.MaximumLength + 40LL);
    v9 = (__int64)v7;
    if ( !v7 )
      return -1073741801;
    if ( SourceString.Length )
    {
      *((_QWORD *)v7 + 2) = v7 + 40;
      *((_WORD *)v7 + 5) = SourceString.MaximumLength;
      RtlCopyUnicodeString((PUNICODE_STRING)(v7 + 8), &SourceString);
    }
    *i = v9;
    v10 = BaseSrvSaveVarNameMapping(v8, v9, &SourceString, &v28, &v22);
    if ( v10 >= 0 )
    {
      *(_DWORD *)(v22 + 24) |= 0x30000000u;
    }
    else if ( v10 == -1073741801 )
    {
      return -1073741801;
    }
  }
  v11 = 0;
  v12 = (_QWORD *)BaseSrvIniFileMapping;
  *(_QWORD *)BaseSrvIniFileMapping = 0;
  while ( 1 )
  {
    v13 = NtEnumerateKey(KeyHandle, v11, KeyBasicInformation, KeyValueInformation, 0x400u, &ResultLength);
    v14 = v13;
    if ( v13 < 0 )
      break;
    ObjectAttributes.Length = 48;
    v21.Buffer = (PWSTR)&v29;
    v21.Length = v28;
    v21.MaximumLength = v28;
    ObjectAttributes.RootDirectory = KeyHandle;
    ObjectAttributes.ObjectName = &v21;
    ObjectAttributes.Attributes = 64;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v14 = NtOpenKey(&Handle, 0x80000000, &ObjectAttributes);
    if ( v14 < 0 )
      goto LABEL_32;
    v15 = (char *)RtlAllocateHeap(BaseSrvSharedHeap, (BaseSrvSharedTag + 0x40000) | 8, v21.MaximumLength + 40LL);
    v16 = (__int64)v15;
    if ( !v15 )
    {
      v14 = -1073741801;
      NtClose(Handle);
      goto LABEL_32;
    }
    if ( v21.Length )
    {
      *((_QWORD *)v15 + 2) = v15 + 40;
      *((_WORD *)v15 + 5) = v21.MaximumLength;
      RtlCopyUnicodeString((PUNICODE_STRING)(v15 + 8), &v21);
    }
    v14 = BaseSrvSaveIniFileMapping(v16, Handle);
    if ( v14 < 0 )
    {
      NtClose(Handle);
      BaseSrvFreeFileMapping((PVOID)v16);
      goto LABEL_32;
    }
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)(v16 + 8), &DestinationString, 1u) )
      *(_QWORD *)(BaseSrvIniFileMapping + 16) = v16;
    *v12 = v16;
    v12 = (_QWORD *)v16;
    NtClose(Handle);
    ++v11;
  }
  if ( v13 == -2147483622 )
    v14 = 0;
LABEL_32:
  NtClose(KeyHandle);
  return v14;
}

```

## disassembly

```asm
0x180004d70  mov     [rsp-8+arg_18], rbx
0x180004d75  push    rbp
0x180004d76  push    rdi
0x180004d77  push    r12
0x180004d79  lea     rbp, [rsp-3E0h]
0x180004d81  sub     rsp, 4E0h
0x180004d88  mov     rax, cs:__security_cookie
0x180004d8f  xor     rax, rsp
0x180004d92  mov     [rbp+3F0h+var_20], rax
0x180004d99  mov     rbx, cs:BaseSrvpStaticServerData
0x180004da0  lea     rdx, aWinIni; "win.ini"
0x180004da7  xorps   xmm0, xmm0
0x180004daa  lea     rcx, [rbp+3F0h+DestinationString]; DestinationString
0x180004dae  xor     r12d, r12d
0x180004db1  xorps   xmm1, xmm1
0x180004db4  movups  xmmword ptr [rbp+3F0h+ObjectAttributes.ObjectName], xmm0
0x180004db8  xor     eax, eax
0x180004dba  mov     [rsp+4F0h+KeyHandle], r12
0x180004dbf  movups  xmmword ptr [rbp+3F0h+ObjectAttributes+1Ch], xmm0
0x180004dc3  mov     [rsp+4F0h+var_488], r12
0x180004dc8  movups  xmmword ptr [rbp+3F0h+var_450.Length], xmm0
0x180004dcc  mov     [rsp+4F0h+var_4C0], r12d
0x180004dd1  movups  xmmword ptr [rsp+4F0h+ObjectAttributes.Length], xmm0
0x180004dd6  mov     [rsp+4F0h+Handle], r12
0x180004ddb  movups  xmmword ptr [rbp+3F0h+ValueName.Length], xmm0
0x180004ddf  movups  xmmword ptr [rsp+4F0h+var_498.Length], xmm1
0x180004de4  movups  xmmword ptr [rbp+3F0h+DestinationString.Length], xmm0
0x180004de8  movups  xmmword ptr [rsp+4F0h+SourceString.Length], xmm1
0x180004ded  call    cs:__imp_RtlInitUnicodeString
0x180004df4  nop     dword ptr [rax+rax+00h]
0x180004df9  xor     edx, edx; SourceString
0x180004dfb  lea     rcx, [rsp+4F0h+SourceString]; DestinationString
0x180004e00  call    cs:__imp_RtlInitUnicodeString
0x180004e07  nop     dword ptr [rax+rax+00h]
0x180004e0c  mov     edx, cs:BaseSrvSharedTag
0x180004e12  mov     r8d, 20h ; ' '; Size
0x180004e18  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180004e1f  add     edx, 40000h
0x180004e25  or      edx, 8; Flags
0x180004e28  call    cs:__imp_RtlAllocateHeap
0x180004e2f  nop     dword ptr [rax+rax+00h]
0x180004e34  mov     cs:BaseSrvIniFileMapping, rax
0x180004e3b  test    rax, rax
0x180004e3e  jz      loc_180004FD5
0x180004e44  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180004e4b  mov     [rbx+170h], rax
0x180004e52  lea     rcx, [rbp+3F0h+var_450]; DestinationString
0x180004e56  call    cs:__imp_RtlInitUnicodeString
0x180004e5d  nop     dword ptr [rax+rax+00h]
0x180004e62  lea     rax, [rbp+3F0h+var_450]
0x180004e66  mov     [rsp+4F0h+ObjectAttributes.Length], 30h ; '0'
0x180004e6e  xorps   xmm0, xmm0
0x180004e71  mov     [rbp+3F0h+ObjectAttributes.ObjectName], rax
0x180004e75  lea     r8, [rsp+4F0h+ObjectAttributes]; ObjectAttributes
0x180004e7a  mov     [rsp+4F0h+ObjectAttributes.RootDirectory], r12
0x180004e7f  mov     edx, 80000000h; DesiredAccess
0x180004e84  mov     [rbp+3F0h+ObjectAttributes.Attributes], 40h ; '@'
0x180004e8b  lea     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x180004e90  movdqu  xmmword ptr [rbp+3F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180004e95  call    cs:__imp_NtOpenKey
0x180004e9c  nop     dword ptr [rax+rax+00h]
0x180004ea1  test    eax, eax
0x180004ea3  js      loc_180004FDA
0x180004ea9  xor     edx, edx; SourceString
0x180004eab  lea     rcx, [rbp+3F0h+ValueName]; DestinationString
0x180004eaf  call    cs:__imp_RtlInitUnicodeString
0x180004eb6  nop     dword ptr [rax+rax+00h]
0x180004ebb  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x180004ec0  lea     rax, [rsp+4F0h+var_4C0]
0x180004ec5  mov     [rsp+4F0h+ResultLength], rax; ResultLength
0x180004eca  lea     r9, [rbp+3F0h+KeyValueInformation]; KeyValueInformation
0x180004ece  mov     r8d, 2; KeyValueInformationClass
0x180004ed4  mov     [rsp+4F0h+Length], 400h; Length
0x180004edc  lea     rdx, [rbp+3F0h+ValueName]; ValueName
0x180004ee0  call    cs:__imp_NtQueryValueKey
0x180004ee7  nop     dword ptr [rax+rax+00h]
0x180004eec  mov     [rbp+3F0h+var_22], r12w
0x180004ef4  test    eax, eax
0x180004ef6  js      loc_18000500A
0x180004efc  mov     rdx, cs:BaseSrvIniFileMapping
0x180004f03  lea     rcx, [rsp+4F0h+SourceString]; SourceString
0x180004f08  add     rdx, 8
0x180004f0c  call    BaseSrvSaveFileNameMapping
0x180004f11  test    eax, eax
0x180004f13  js      loc_180004FDA
0x180004f19  mov     rax, cs:BaseSrvIniFileMapping
0x180004f20  mov     rdi, [rax+8]
0x180004f24  cmp     [rsp+4F0h+SourceString.Length], r12w
0x180004f2a  jz      short loc_180004F46
0x180004f2c  mov     rax, [rdi+18h]
0x180004f30  add     rdi, 18h
0x180004f34  test    rax, rax
0x180004f37  jz      short loc_180004F4A
0x180004f39  mov     rdi, rax
0x180004f3c  mov     rax, [rax]
0x180004f3f  test    rax, rax
0x180004f42  jnz     short loc_180004F39
0x180004f44  jmp     short loc_180004F4A
0x180004f46  add     rdi, 20h ; ' '
0x180004f4a  mov     edx, cs:BaseSrvSharedTag
0x180004f50  movzx   r8d, [rsp+4F0h+SourceString.MaximumLength]
0x180004f56  add     edx, 40000h
0x180004f5c  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180004f63  or      edx, 8; Flags
0x180004f66  add     r8, 28h ; '('; Size
0x180004f6a  call    cs:__imp_RtlAllocateHeap
0x180004f71  nop     dword ptr [rax+rax+00h]
0x180004f76  mov     rbx, rax
0x180004f79  test    rax, rax
0x180004f7c  jz      short loc_180004FD5
0x180004f7e  cmp     [rsp+4F0h+SourceString.Length], r12w
0x180004f84  jz      short loc_180004FAC
0x180004f86  lea     rcx, [rax+28h]
0x180004f8a  mov     [rax+10h], rcx
0x180004f8e  lea     rdx, [rsp+4F0h+SourceString]; SourceString
0x180004f93  movzx   ecx, [rsp+4F0h+SourceString.MaximumLength]
0x180004f98  mov     [rax+0Ah], cx
0x180004f9c  lea     rcx, [rax+8]; DestinationString
0x180004fa0  call    cs:__imp_RtlCopyUnicodeString
0x180004fa7  nop     dword ptr [rax+rax+00h]
0x180004fac  lea     rax, [rsp+4F0h+var_488]
0x180004fb1  mov     [rdi], rbx
0x180004fb4  lea     r9, [rbp+3F0h+var_414]
0x180004fb8  mov     qword ptr [rsp+4F0h+Length], rax
0x180004fbd  lea     r8, [rsp+4F0h+SourceString]
0x180004fc2  mov     rdx, rbx
0x180004fc5  call    BaseSrvSaveVarNameMapping
0x180004fca  test    eax, eax
0x180004fcc  jns     short loc_180004FFE
0x180004fce  cmp     eax, 0C0000017h
0x180004fd3  jnz     short loc_18000500A
0x180004fd5  mov     eax, 0C0000017h
0x180004fda  mov     rcx, [rbp+3F0h+var_20]
0x180004fe1  xor     rcx, rsp; StackCookie
0x180004fe4  call    __security_check_cookie
0x180004fe9  mov     rbx, [rsp+4F0h+arg_18]
0x180004ff1  add     rsp, 4E0h
0x180004ff8  pop     r12
0x180004ffa  pop     rdi
0x180004ffb  pop     rbp
0x180004ffc  retn
0x180004ffe  mov     rax, [rsp+4F0h+var_488]
0x180005003  or      dword ptr [rax+18h], 30000000h
0x18000500a  mov     [rsp+4F0h+arg_8], r14
0x180005012  mov     edi, r12d
0x180005015  mov     r14, cs:BaseSrvIniFileMapping
0x18000501c  mov     [rsp+4F0h+arg_0], rsi
0x180005024  mov     [rsp+4F0h+arg_10], r15
0x18000502c  mov     [r14], r12
0x18000502f  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x180005034  lea     rax, [rsp+4F0h+var_4C0]
0x180005039  mov     [rsp+4F0h+ResultLength], rax; ResultLength
0x18000503e  lea     r9, [rbp+3F0h+KeyValueInformation]; KeyInformation
0x180005042  xor     r8d, r8d; KeyInformationClass
0x180005045  mov     [rsp+4F0h+Length], 400h; Length
0x18000504d  mov     edx, edi; Index
0x18000504f  call    cs:__imp_NtEnumerateKey
0x180005056  nop     dword ptr [rax+rax+00h]
0x18000505b  mov     ebx, eax
0x18000505d  test    eax, eax
0x18000505f  js      loc_1800051BB
0x180005065  lea     rax, [rbp+3F0h+var_410]
0x180005069  mov     [rsp+4F0h+ObjectAttributes.Length], 30h ; '0'
0x180005071  mov     [rsp+4F0h+var_498.Buffer], rax
0x180005076  lea     r8, [rsp+4F0h+ObjectAttributes]; ObjectAttributes
0x18000507b  movzx   eax, [rbp+3F0h+var_414]
0x18000507f  lea     rcx, [rsp+4F0h+Handle]; KeyHandle
0x180005084  mov     [rsp+4F0h+var_498.Length], ax
0x180005089  xorps   xmm0, xmm0
0x18000508c  mov     [rsp+4F0h+var_498.MaximumLength], ax
0x180005091  mov     edx, 80000000h; DesiredAccess
0x180005096  mov     rax, [rsp+4F0h+KeyHandle]
0x18000509b  mov     [rsp+4F0h+ObjectAttributes.RootDirectory], rax
0x1800050a0  lea     rax, [rsp+4F0h+var_498]
0x1800050a5  mov     [rbp+3F0h+ObjectAttributes.ObjectName], rax
0x1800050a9  mov     [rbp+3F0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800050b0  movdqu  xmmword ptr [rbp+3F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800050b5  call    cs:__imp_NtOpenKey
0x1800050bc  nop     dword ptr [rax+rax+00h]
0x1800050c1  mov     ebx, eax
0x1800050c3  test    eax, eax
0x1800050c5  js      loc_1800051C5
0x1800050cb  mov     edx, cs:BaseSrvSharedTag
0x1800050d1  movzx   r8d, [rsp+4F0h+var_498.MaximumLength]
0x1800050d7  add     edx, 40000h
0x1800050dd  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x1800050e4  or      edx, 8; Flags
0x1800050e7  add     r8, 28h ; '('; Size
0x1800050eb  call    cs:__imp_RtlAllocateHeap
0x1800050f2  nop     dword ptr [rax+rax+00h]
0x1800050f7  mov     rsi, rax
0x1800050fa  test    rax, rax
0x1800050fd  jz      loc_1800051A3
0x180005103  cmp     [rsp+4F0h+var_498.Length], r12w
0x180005109  jz      short loc_180005131
0x18000510b  lea     rcx, [rax+28h]
0x18000510f  mov     [rax+10h], rcx
0x180005113  lea     rdx, [rsp+4F0h+var_498]; SourceString
0x180005118  movzx   ecx, [rsp+4F0h+var_498.MaximumLength]
0x18000511d  mov     [rax+0Ah], cx
0x180005121  lea     rcx, [rax+8]; DestinationString
0x180005125  call    cs:__imp_RtlCopyUnicodeString
0x18000512c  nop     dword ptr [rax+rax+00h]
0x180005131  mov     rdx, [rsp+4F0h+Handle]
0x180005136  mov     rcx, rsi
0x180005139  call    BaseSrvSaveIniFileMapping
0x18000513e  mov     ebx, eax
0x180005140  test    eax, eax
0x180005142  js      short loc_180005188
0x180005144  mov     r8b, 1; CaseInsensitive
0x180005147  lea     rdx, [rbp+3F0h+DestinationString]; String2
0x18000514b  lea     rcx, [rsi+8]; String1
0x18000514f  call    cs:__imp_RtlEqualUnicodeString
0x180005156  nop     dword ptr [rax+rax+00h]
0x18000515b  test    al, al
0x18000515d  jz      short loc_18000516A
0x18000515f  mov     rax, cs:BaseSrvIniFileMapping
0x180005166  mov     [rax+10h], rsi
0x18000516a  mov     [r14], rsi
0x18000516d  mov     r14, rsi
0x180005170  mov     rcx, [rsp+4F0h+Handle]; Handle
0x180005175  call    cs:__imp_NtClose
0x18000517c  nop     dword ptr [rax+rax+00h]
0x180005181  inc     edi
0x180005183  jmp     loc_18000502F
0x180005188  mov     rcx, [rsp+4F0h+Handle]; Handle
0x18000518d  call    cs:__imp_NtClose
0x180005194  nop     dword ptr [rax+rax+00h]
0x180005199  mov     rcx, rsi; P
0x18000519c  call    BaseSrvFreeFileMapping
0x1800051a1  jmp     short loc_1800051C5
0x1800051a3  mov     rcx, [rsp+4F0h+Handle]; Handle
0x1800051a8  mov     ebx, 0C0000017h
0x1800051ad  call    cs:__imp_NtClose
0x1800051b4  nop     dword ptr [rax+rax+00h]
0x1800051b9  jmp     short loc_1800051C5
0x1800051bb  cmp     eax, 8000001Ah
0x1800051c0  jnz     short loc_1800051C5
0x1800051c2  mov     ebx, r12d
0x1800051c5  mov     rcx, [rsp+4F0h+KeyHandle]; Handle
0x1800051ca  call    cs:__imp_NtClose
0x1800051d1  nop     dword ptr [rax+rax+00h]
0x1800051d6  mov     r15, [rsp+4F0h+arg_10]
0x1800051de  mov     eax, ebx
0x1800051e0  mov     r14, [rsp+4F0h+arg_8]
0x1800051e8  mov     rsi, [rsp+4F0h+arg_0]
0x1800051f0  jmp     loc_180004FDA
```
