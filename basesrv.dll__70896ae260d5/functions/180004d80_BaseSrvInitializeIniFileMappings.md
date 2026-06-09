# BaseSrvInitializeIniFileMappings

- ea: `0x180004d80`
- end: `0x1800051fd`
- name: `BaseSrvInitializeIniFileMappings`
- size: `1149`
- prototype: `NTSTATUS()`
- caller_count: `1`
- callee_count: `6`
- tags: `reparse_path, authz_impersonation, registry_config, loader_planting, broker_com_uri`

## callers

- `0x180002f50`

## callees

- `0x180004d80`
- `0x180005210`
- `0x1800056e0`
- `0x180005bc0`
- `0x18000caf0`
- `0x18000d730`

## import_xrefs

- `ntdll!RtlAllocateHeap` at `0x180004e31`
- `ntdll!RtlAllocateHeap` at `0x180004f72`
- `ntdll!RtlAllocateHeap` at `0x1800050f3`
- `ntdll!RtlAllocateHeap` at `0x180004e31`
- `ntdll!RtlAllocateHeap` at `0x180004f72`
- `ntdll!RtlAllocateHeap` at `0x1800050f3`
- `ntdll!NtOpenKey` at `0x180004e9e`
- `ntdll!NtOpenKey` at `0x1800050bd`
- `ntdll!NtOpenKey` at `0x180004e9e`
- `ntdll!NtOpenKey` at `0x1800050bd`
- `ntdll!NtQueryValueKey` at `0x180004ee8`
- `ntdll!NtQueryValueKey` at `0x180004ee8`
- `ntdll!NtClose` at `0x18000517d`
- `ntdll!NtClose` at `0x180005195`
- `ntdll!NtClose` at `0x1800051b5`
- `ntdll!NtClose` at `0x1800051d2`
- `ntdll!NtClose` at `0x18000517d`
- `ntdll!NtClose` at `0x180005195`
- `ntdll!NtClose` at `0x1800051b5`
- `ntdll!NtClose` at `0x1800051d2`
- `ntdll!RtlCopyUnicodeString` at `0x180004fa8`
- `ntdll!RtlCopyUnicodeString` at `0x18000512d`
- `ntdll!RtlCopyUnicodeString` at `0x180004fa8`
- `ntdll!RtlCopyUnicodeString` at `0x18000512d`
- `ntdll!NtEnumerateKey` at `0x180005057`
- `ntdll!NtEnumerateKey` at `0x180005057`
- `ntdll!RtlEqualUnicodeString` at `0x180005157`
- `ntdll!RtlEqualUnicodeString` at `0x180005157`
- `ntdll!RtlInitUnicodeString` at `0x180004df7`
- `ntdll!RtlInitUnicodeString` at `0x180004e0a`
- `ntdll!RtlInitUnicodeString` at `0x180004e5f`
- `ntdll!RtlInitUnicodeString` at `0x180004eb8`
- `ntdll!RtlInitUnicodeString` at `0x180004df7`
- `ntdll!RtlInitUnicodeString` at `0x180004e0a`
- `ntdll!RtlInitUnicodeString` at `0x180004e5f`
- `ntdll!RtlInitUnicodeString` at `0x180004eb8`

## string_xrefs

- `0x180004e4d`: `\REGISTRY\MACHINE\SOFTWARE\Microsoft\Windows NT\CurrentVersion\IniFileMapping`

## pseudocode

```c
NTSTATUS BaseSrvInitializeIniFileMappings()
{
  __int64 v0; // rbx
  PVOID Heap; // rax
  NTSTATUS result; // eax
  NTSTATUS v3; // eax
  __int64 v4; // rbx
  _QWORD *v5; // rax
  _QWORD *i; // rbx
  char *v7; // rax
  __int64 v8; // rcx
  char *v9; // rdi
  int v10; // eax
  ULONG v11; // edi
  _QWORD *v12; // r14
  NTSTATUS v13; // eax
  NTSTATUS v14; // ebx
  char *v15; // rax
  char *v16; // rsi
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
  USHORT v28; // [rsp+DCh] [rbp-24h] BYREF
  char v29; // [rsp+E0h] [rbp-20h] BYREF
  __int16 v30; // [rsp+4CEh] [rbp+3CEh]

  v0 = BaseSrvpStaticServerData;
  KeyHandle = 0;
  v22 = 0;
  v24 = 0;
  *(&ObjectAttributes.Length + 1) = 0;
  *(&ObjectAttributes.Attributes + 1) = 0;
  ResultLength = 0;
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
    result = BaseSrvSaveFileNameMapping(&SourceString);
    if ( result < 0 )
      return result;
    v4 = *(_QWORD *)(BaseSrvIniFileMapping + 8);
    if ( SourceString.Length )
    {
      v5 = *(_QWORD **)(v4 + 24);
      for ( i = (_QWORD *)(v4 + 24); v5; v5 = (_QWORD *)*v5 )
        i = v5;
    }
    else
    {
      i = (_QWORD *)(v4 + 32);
    }
    v7 = (char *)RtlAllocateHeap(BaseSrvSharedHeap, (BaseSrvSharedTag + 0x40000) | 8, SourceString.MaximumLength + 40LL);
    v9 = v7;
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
    v16 = v15;
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
      BaseSrvFreeFileMapping(v16);
      goto LABEL_32;
    }
    if ( RtlEqualUnicodeString((PCUNICODE_STRING)(v16 + 8), &DestinationString, 1u) )
      *(_QWORD *)(BaseSrvIniFileMapping + 16) = v16;
    *v12 = v16;
    v12 = v16;
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
0x180004d80  mov     [rsp-8+arg_18], rbx
0x180004d85  push    rbp
0x180004d86  push    rdi
0x180004d87  push    r12
0x180004d89  lea     rbp, [rsp-3E0h]
0x180004d91  sub     rsp, 4E0h
0x180004d98  mov     rax, cs:__security_cookie
0x180004d9f  xor     rax, rsp
0x180004da2  mov     [rbp+3F0h+var_20], rax
0x180004da9  mov     rbx, cs:BaseSrvpStaticServerData
0x180004db0  lea     rdx, aWinIni; "win.ini"
0x180004db7  xor     r12d, r12d
0x180004dba  lea     rcx, [rbp+3F0h+DestinationString]; DestinationString
0x180004dbe  xorps   xmm0, xmm0
0x180004dc1  mov     [rsp+4F0h+KeyHandle], r12
0x180004dc6  xorps   xmm1, xmm1
0x180004dc9  mov     [rsp+4F0h+var_488], r12
0x180004dce  movups  xmmword ptr [rbp+3F0h+var_450.Length], xmm0
0x180004dd2  mov     dword ptr [rsp+4F0h+ObjectAttributes+4], r12d
0x180004dd7  mov     dword ptr [rbp+3F0h+ObjectAttributes+1Ch], r12d
0x180004ddb  mov     [rsp+4F0h+var_4C0], r12d
0x180004de0  mov     [rsp+4F0h+Handle], r12
0x180004de5  movups  xmmword ptr [rbp+3F0h+ValueName.Length], xmm0
0x180004de9  movups  xmmword ptr [rsp+4F0h+var_498.Length], xmm1
0x180004dee  movups  xmmword ptr [rbp+3F0h+DestinationString.Length], xmm0
0x180004df2  movups  xmmword ptr [rsp+4F0h+SourceString.Length], xmm1
0x180004df7  call    cs:__imp_RtlInitUnicodeString
0x180004dfe  nop     dword ptr [rax+rax+00h]
0x180004e03  xor     edx, edx; SourceString
0x180004e05  lea     rcx, [rsp+4F0h+SourceString]; DestinationString
0x180004e0a  call    cs:__imp_RtlInitUnicodeString
0x180004e11  nop     dword ptr [rax+rax+00h]
0x180004e16  mov     edx, cs:BaseSrvSharedTag
0x180004e1c  lea     r8d, [r12+20h]; Size
0x180004e21  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180004e28  add     edx, 40000h
0x180004e2e  or      edx, 8; Flags
0x180004e31  call    cs:__imp_RtlAllocateHeap
0x180004e38  nop     dword ptr [rax+rax+00h]
0x180004e3d  mov     cs:BaseSrvIniFileMapping, rax
0x180004e44  test    rax, rax
0x180004e47  jz      loc_180004FDD
0x180004e4d  lea     rdx, aRegistryMachin_0; "\\REGISTRY\\MACHINE\\SOFTWARE\\Microsof"...
0x180004e54  mov     [rbx+170h], rax
0x180004e5b  lea     rcx, [rbp+3F0h+var_450]; DestinationString
0x180004e5f  call    cs:__imp_RtlInitUnicodeString
0x180004e66  nop     dword ptr [rax+rax+00h]
0x180004e6b  lea     rax, [rbp+3F0h+var_450]
0x180004e6f  mov     [rsp+4F0h+ObjectAttributes.Length], 30h ; '0'
0x180004e77  xorps   xmm0, xmm0
0x180004e7a  mov     [rbp+3F0h+ObjectAttributes.ObjectName], rax
0x180004e7e  lea     r8, [rsp+4F0h+ObjectAttributes]; ObjectAttributes
0x180004e83  mov     [rsp+4F0h+ObjectAttributes.RootDirectory], r12
0x180004e88  mov     edx, 80000000h; DesiredAccess
0x180004e8d  mov     [rbp+3F0h+ObjectAttributes.Attributes], 40h ; '@'
0x180004e94  lea     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x180004e99  movdqu  xmmword ptr [rbp+3F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x180004e9e  call    cs:__imp_NtOpenKey
0x180004ea5  nop     dword ptr [rax+rax+00h]
0x180004eaa  test    eax, eax
0x180004eac  js      loc_180004FE2
0x180004eb2  xor     edx, edx; SourceString
0x180004eb4  lea     rcx, [rbp+3F0h+ValueName]; DestinationString
0x180004eb8  call    cs:__imp_RtlInitUnicodeString
0x180004ebf  nop     dword ptr [rax+rax+00h]
0x180004ec4  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x180004ec9  lea     rax, [rsp+4F0h+var_4C0]
0x180004ece  mov     [rsp+4F0h+ResultLength], rax; ResultLength
0x180004ed3  lea     r9, [rbp+3F0h+KeyValueInformation]; KeyValueInformation
0x180004ed7  lea     r8d, [r12+2]; KeyValueInformationClass
0x180004edc  mov     [rsp+4F0h+Length], 400h; Length
0x180004ee4  lea     rdx, [rbp+3F0h+ValueName]; ValueName
0x180004ee8  call    cs:__imp_NtQueryValueKey
0x180004eef  nop     dword ptr [rax+rax+00h]
0x180004ef4  mov     [rbp+3F0h+var_22], r12w
0x180004efc  test    eax, eax
0x180004efe  js      loc_180005012
0x180004f04  mov     rdx, cs:BaseSrvIniFileMapping
0x180004f0b  lea     rcx, [rsp+4F0h+SourceString]; SourceString
0x180004f10  add     rdx, 8
0x180004f14  call    BaseSrvSaveFileNameMapping
0x180004f19  test    eax, eax
0x180004f1b  js      loc_180004FE2
0x180004f21  mov     rax, cs:BaseSrvIniFileMapping
0x180004f28  mov     rbx, [rax+8]
0x180004f2c  cmp     [rsp+4F0h+SourceString.Length], r12w
0x180004f32  jz      short loc_180004F4E
0x180004f34  mov     rax, [rbx+18h]
0x180004f38  add     rbx, 18h
0x180004f3c  test    rax, rax
0x180004f3f  jz      short loc_180004F52
0x180004f41  mov     rbx, rax
0x180004f44  mov     rax, [rax]
0x180004f47  test    rax, rax
0x180004f4a  jnz     short loc_180004F41
0x180004f4c  jmp     short loc_180004F52
0x180004f4e  add     rbx, 20h ; ' '
0x180004f52  mov     edx, cs:BaseSrvSharedTag
0x180004f58  movzx   r8d, [rsp+4F0h+SourceString.MaximumLength]
0x180004f5e  add     edx, 40000h
0x180004f64  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x180004f6b  or      edx, 8; Flags
0x180004f6e  add     r8, 28h ; '('; Size
0x180004f72  call    cs:__imp_RtlAllocateHeap
0x180004f79  nop     dword ptr [rax+rax+00h]
0x180004f7e  mov     rdi, rax
0x180004f81  test    rax, rax
0x180004f84  jz      short loc_180004FDD
0x180004f86  cmp     [rsp+4F0h+SourceString.Length], r12w
0x180004f8c  jz      short loc_180004FB4
0x180004f8e  lea     rcx, [rax+28h]
0x180004f92  mov     [rax+10h], rcx
0x180004f96  lea     rdx, [rsp+4F0h+SourceString]; SourceString
0x180004f9b  movzx   ecx, [rsp+4F0h+SourceString.MaximumLength]
0x180004fa0  mov     [rax+0Ah], cx
0x180004fa4  lea     rcx, [rax+8]; DestinationString
0x180004fa8  call    cs:__imp_RtlCopyUnicodeString
0x180004faf  nop     dword ptr [rax+rax+00h]
0x180004fb4  lea     rax, [rsp+4F0h+var_488]
0x180004fb9  mov     [rbx], rdi
0x180004fbc  lea     r9, [rbp+3F0h+var_414]
0x180004fc0  mov     qword ptr [rsp+4F0h+Length], rax
0x180004fc5  lea     r8, [rsp+4F0h+SourceString]
0x180004fca  mov     rdx, rdi
0x180004fcd  call    BaseSrvSaveVarNameMapping
0x180004fd2  test    eax, eax
0x180004fd4  jns     short loc_180005006
0x180004fd6  cmp     eax, 0C0000017h
0x180004fdb  jnz     short loc_180005012
0x180004fdd  mov     eax, 0C0000017h
0x180004fe2  mov     rcx, [rbp+3F0h+var_20]
0x180004fe9  xor     rcx, rsp; StackCookie
0x180004fec  call    __security_check_cookie
0x180004ff1  mov     rbx, [rsp+4F0h+arg_18]
0x180004ff9  add     rsp, 4E0h
0x180005000  pop     r12
0x180005002  pop     rdi
0x180005003  pop     rbp
0x180005004  retn
0x180005006  mov     rax, [rsp+4F0h+var_488]
0x18000500b  or      dword ptr [rax+18h], 30000000h
0x180005012  mov     [rsp+4F0h+arg_8], r14
0x18000501a  mov     edi, r12d
0x18000501d  mov     r14, cs:BaseSrvIniFileMapping
0x180005024  mov     [rsp+4F0h+arg_0], rsi
0x18000502c  mov     [rsp+4F0h+arg_10], r15
0x180005034  mov     [r14], r12
0x180005037  mov     rcx, [rsp+4F0h+KeyHandle]; KeyHandle
0x18000503c  lea     rax, [rsp+4F0h+var_4C0]
0x180005041  mov     [rsp+4F0h+ResultLength], rax; ResultLength
0x180005046  lea     r9, [rbp+3F0h+KeyValueInformation]; KeyInformation
0x18000504a  xor     r8d, r8d; KeyInformationClass
0x18000504d  mov     [rsp+4F0h+Length], 400h; Length
0x180005055  mov     edx, edi; Index
0x180005057  call    cs:__imp_NtEnumerateKey
0x18000505e  nop     dword ptr [rax+rax+00h]
0x180005063  mov     ebx, eax
0x180005065  test    eax, eax
0x180005067  js      loc_1800051C3
0x18000506d  lea     rax, [rbp+3F0h+var_410]
0x180005071  mov     [rsp+4F0h+ObjectAttributes.Length], 30h ; '0'
0x180005079  mov     [rsp+4F0h+var_498.Buffer], rax
0x18000507e  lea     r8, [rsp+4F0h+ObjectAttributes]; ObjectAttributes
0x180005083  movzx   eax, [rbp+3F0h+var_414]
0x180005087  lea     rcx, [rsp+4F0h+Handle]; KeyHandle
0x18000508c  mov     [rsp+4F0h+var_498.Length], ax
0x180005091  xorps   xmm0, xmm0
0x180005094  mov     [rsp+4F0h+var_498.MaximumLength], ax
0x180005099  mov     edx, 80000000h; DesiredAccess
0x18000509e  mov     rax, [rsp+4F0h+KeyHandle]
0x1800050a3  mov     [rsp+4F0h+ObjectAttributes.RootDirectory], rax
0x1800050a8  lea     rax, [rsp+4F0h+var_498]
0x1800050ad  mov     [rbp+3F0h+ObjectAttributes.ObjectName], rax
0x1800050b1  mov     [rbp+3F0h+ObjectAttributes.Attributes], 40h ; '@'
0x1800050b8  movdqu  xmmword ptr [rbp+3F0h+ObjectAttributes.SecurityDescriptor], xmm0
0x1800050bd  call    cs:__imp_NtOpenKey
0x1800050c4  nop     dword ptr [rax+rax+00h]
0x1800050c9  mov     ebx, eax
0x1800050cb  test    eax, eax
0x1800050cd  js      loc_1800051CD
0x1800050d3  mov     edx, cs:BaseSrvSharedTag
0x1800050d9  movzx   r8d, [rsp+4F0h+var_498.MaximumLength]
0x1800050df  add     edx, 40000h
0x1800050e5  mov     rcx, cs:BaseSrvSharedHeap; HeapHandle
0x1800050ec  or      edx, 8; Flags
0x1800050ef  add     r8, 28h ; '('; Size
0x1800050f3  call    cs:__imp_RtlAllocateHeap
0x1800050fa  nop     dword ptr [rax+rax+00h]
0x1800050ff  mov     rsi, rax
0x180005102  test    rax, rax
0x180005105  jz      loc_1800051AB
0x18000510b  cmp     [rsp+4F0h+var_498.Length], r12w
0x180005111  jz      short loc_180005139
0x180005113  lea     rcx, [rax+28h]
0x180005117  mov     [rax+10h], rcx
0x18000511b  lea     rdx, [rsp+4F0h+var_498]; SourceString
0x180005120  movzx   ecx, [rsp+4F0h+var_498.MaximumLength]
0x180005125  mov     [rax+0Ah], cx
0x180005129  lea     rcx, [rax+8]; DestinationString
0x18000512d  call    cs:__imp_RtlCopyUnicodeString
0x180005134  nop     dword ptr [rax+rax+00h]
0x180005139  mov     rdx, [rsp+4F0h+Handle]
0x18000513e  mov     rcx, rsi
0x180005141  call    BaseSrvSaveIniFileMapping
0x180005146  mov     ebx, eax
0x180005148  test    eax, eax
0x18000514a  js      short loc_180005190
0x18000514c  mov     r8b, 1; CaseInsensitive
0x18000514f  lea     rdx, [rbp+3F0h+DestinationString]; String2
0x180005153  lea     rcx, [rsi+8]; String1
0x180005157  call    cs:__imp_RtlEqualUnicodeString
0x18000515e  nop     dword ptr [rax+rax+00h]
0x180005163  test    al, al
0x180005165  jz      short loc_180005172
0x180005167  mov     rax, cs:BaseSrvIniFileMapping
0x18000516e  mov     [rax+10h], rsi
0x180005172  mov     [r14], rsi
0x180005175  mov     r14, rsi
0x180005178  mov     rcx, [rsp+4F0h+Handle]; Handle
0x18000517d  call    cs:__imp_NtClose
0x180005184  nop     dword ptr [rax+rax+00h]
0x180005189  inc     edi
0x18000518b  jmp     loc_180005037
0x180005190  mov     rcx, [rsp+4F0h+Handle]; Handle
0x180005195  call    cs:__imp_NtClose
0x18000519c  nop     dword ptr [rax+rax+00h]
0x1800051a1  mov     rcx, rsi; P
0x1800051a4  call    BaseSrvFreeFileMapping
0x1800051a9  jmp     short loc_1800051CD
0x1800051ab  mov     rcx, [rsp+4F0h+Handle]; Handle
0x1800051b0  mov     ebx, 0C0000017h
0x1800051b5  call    cs:__imp_NtClose
0x1800051bc  nop     dword ptr [rax+rax+00h]
0x1800051c1  jmp     short loc_1800051CD
0x1800051c3  cmp     eax, 8000001Ah
0x1800051c8  jnz     short loc_1800051CD
0x1800051ca  mov     ebx, r12d
0x1800051cd  mov     rcx, [rsp+4F0h+KeyHandle]; Handle
0x1800051d2  call    cs:__imp_NtClose
0x1800051d9  nop     dword ptr [rax+rax+00h]
0x1800051de  mov     r15, [rsp+4F0h+arg_10]
0x1800051e6  mov     eax, ebx
0x1800051e8  mov     r14, [rsp+4F0h+arg_8]
0x1800051f0  mov     rsi, [rsp+4F0h+arg_0]
0x1800051f8  jmp     loc_180004FE2
```
