# BipStorageOpenRootKey(_UNICODE_STRING *,void * *)

- ea: `0x180083c0c`
- end: `0x180083e8d`
- name: `?BipStorageOpenRootKey@@YAJPEAU_UNICODE_STRING@@PEAPEAX@Z`
- size: `641`
- prototype: `__int64 __fastcall(struct _UNICODE_STRING *, void **)`
- caller_count: `1`
- callee_count: `6`
- tags: `file_ops, reparse_path, authz_impersonation, loader_planting, broker_com_uri`

## callers

- `0x1800639b0`

## callees

- `0x180024558`
- `0x18002b060`
- `0x180053100`
- `0x180083b1c`
- `0x180083c0c`
- `0x1800946a0`

## import_xrefs

- `ntdll!NtLoadKeyEx` at `0x180083cde`
- `ntdll!NtLoadKeyEx` at `0x180083d39`
- `ntdll!NtLoadKeyEx` at `0x180083cde`
- `ntdll!NtLoadKeyEx` at `0x180083d39`
- `ntdll!NtDeleteFile` at `0x180083cf6`
- `ntdll!NtDeleteFile` at `0x180083cf6`
- `ntdll!RtlFreeUnicodeString` at `0x180083e66`
- `ntdll!RtlFreeUnicodeString` at `0x180083e66`
- `ntdll!RtlInitUnicodeString` at `0x180083d73`
- `ntdll!RtlInitUnicodeString` at `0x180083d73`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180083d52`
- `api-ms-win-core-sysinfo-l1-1-0!GetSystemTimeAsFileTime` at `0x180083d52`

## pseudocode

```c
__int64 __fastcall BipStorageOpenRootKey(struct _UNICODE_STRING *a1, void **a2)
{
  NTSTATUS HiveMountPath; // ebx
  __int64 v4; // r8
  NTSTATUS v5; // eax
  int v6; // r8d
  __int64 v8; // [rsp+20h] [rbp-E0h]
  HANDLE *p_KeyHandle; // [rsp+30h] [rbp-D0h]
  __int64 v10; // [rsp+38h] [rbp-C8h]
  struct _FILETIME SystemTimeAsFileTime; // [rsp+40h] [rbp-C0h] BYREF
  HANDLE KeyHandle; // [rsp+48h] [rbp-B8h] BYREF
  struct _FILETIME v13; // [rsp+50h] [rbp-B0h] BYREF
  int v14; // [rsp+58h] [rbp-A8h] BYREF
  struct _FILETIME v15; // [rsp+60h] [rbp-A0h] BYREF
  struct _UNICODE_STRING UnicodeString; // [rsp+68h] [rbp-98h] BYREF
  struct _OBJECT_ATTRIBUTES SourceFile; // [rsp+78h] [rbp-88h] BYREF
  struct _OBJECT_ATTRIBUTES TargetKey; // [rsp+A8h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+D8h] [rbp-28h] BYREF
  _BYTE v20[32]; // [rsp+F0h] [rbp-10h] BYREF
  struct _FILETIME *v21; // [rsp+110h] [rbp+10h]
  __int64 v22; // [rsp+118h] [rbp+18h]
  int *v23; // [rsp+120h] [rbp+20h]
  __int64 v24; // [rsp+128h] [rbp+28h]
  struct _FILETIME *v25; // [rsp+130h] [rbp+30h]
  __int64 v26; // [rsp+138h] [rbp+38h]

  SourceFile.ObjectName = a1;
  *(_QWORD *)&SourceFile.Length = 48;
  KeyHandle = 0;
  SystemTimeAsFileTime = 0;
  memset(&TargetKey, 0, sizeof(TargetKey));
  SourceFile.RootDirectory = 0;
  *(_QWORD *)&SourceFile.Attributes = 64;
  UnicodeString = 0;
  DestinationString = 0;
  *(_OWORD *)&SourceFile.SecurityDescriptor = 0;
  HiveMountPath = BipStorageGetHiveMountPath(&UnicodeString);
  if ( HiveMountPath >= 0 )
  {
    v10 = 0;
    TargetKey.ObjectName = &UnicodeString;
    TargetKey.Length = 48;
    p_KeyHandle = &KeyHandle;
    HIDWORD(v8) = 0;
    TargetKey.RootDirectory = 0;
    TargetKey.Attributes = 64;
    *(_OWORD *)&TargetKey.SecurityDescriptor = 0;
    v5 = NtLoadKeyEx(&TargetKey, &SourceFile, 0x10u, 0);
    HiveMountPath = v5;
    if ( v5 == -1073741492 )
    {
      HiveMountPath = NtDeleteFile(&SourceFile);
      if ( HiveMountPath < 0 )
      {
        v4 = 30;
        goto LABEL_14;
      }
      v10 = 0;
      p_KeyHandle = &KeyHandle;
      HIDWORD(v8) = 0;
      HiveMountPath = NtLoadKeyEx(&TargetKey, &SourceFile, 0x10u, 0);
      if ( HiveMountPath < 0 )
      {
        v4 = 40;
        goto LABEL_14;
      }
      GetSystemTimeAsFileTime(&SystemTimeAsFileTime);
      v13 = SystemTimeAsFileTime;
      RtlInitUnicodeString(&DestinationString, L"RecoveredFromCorruptedHive");
      HiveMountPath = BipWriteRegUlong64(KeyHandle, &DestinationString);
      if ( HiveMountPath < 0 )
      {
        v4 = 50;
        goto LABEL_14;
      }
    }
    else if ( v5 < 0 )
    {
      v4 = 20;
      goto LABEL_14;
    }
    v4 = 0;
    HiveMountPath = 0;
    *a2 = KeyHandle;
    KeyHandle = 0;
    if ( !SystemTimeAsFileTime.dwHighDateTime && !SystemTimeAsFileTime.dwLowDateTime )
      goto LABEL_17;
    goto LABEL_14;
  }
  v4 = 10;
LABEL_14:
  if ( (unsigned int)dword_1800C3098 > 2 && (unsigned __int8)tlgKeywordOn(&dword_1800C3098, 0x200000000000LL, v4) )
  {
    v15 = SystemTimeAsFileTime;
    v14 = v6;
    v25 = &v15;
    v13.dwLowDateTime = HiveMountPath;
    v23 = &v14;
    v26 = 8;
    v21 = &v13;
    LODWORD(v8) = 5;
    v24 = 4;
    v22 = 4;
    tlgWriteTransfer_EventWriteTransfer(&dword_1800C3098, word_1800B4ECA, 0, 0, v8, v20, p_KeyHandle, v10);
  }
LABEL_17:
  RtlFreeUnicodeString(&UnicodeString);
  return (unsigned int)HiveMountPath;
}

```

## disassembly

```asm
0x180083c0c  mov     [rsp-8+arg_10], rbx
0x180083c11  push    rbp
0x180083c12  push    rsi
0x180083c13  push    rdi
0x180083c14  lea     rbp, [rsp-50h]
0x180083c19  sub     rsp, 150h
0x180083c20  mov     rax, cs:__security_cookie
0x180083c27  xor     rax, rsp
0x180083c2a  mov     [rbp+60h+var_20], rax
0x180083c2e  xorps   xmm0, xmm0
0x180083c31  mov     [rbp+60h+SourceFile.ObjectName], rcx
0x180083c35  xor     esi, esi
0x180083c37  mov     qword ptr [rsp+160h+SourceFile.Length], 30h ; '0'
0x180083c40  xorps   xmm1, xmm1
0x180083c43  mov     [rsp+160h+KeyHandle], rsi
0x180083c48  lea     rcx, [rsp+160h+UnicodeString]; struct _UNICODE_STRING *
0x180083c4d  mov     qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime], rsi
0x180083c52  movups  xmmword ptr [rbp+60h+TargetKey.Length], xmm0
0x180083c56  mov     [rbp+60h+SourceFile.RootDirectory], rsi
0x180083c5a  mov     rdi, rdx
0x180083c5d  movups  xmmword ptr [rbp+60h+TargetKey.ObjectName], xmm0
0x180083c61  mov     qword ptr [rbp+60h+SourceFile.Attributes], 40h ; '@'
0x180083c69  movups  xmmword ptr [rbp+60h+TargetKey.SecurityDescriptor], xmm0
0x180083c6d  movups  xmmword ptr [rsp+160h+UnicodeString.Length], xmm0
0x180083c72  movups  xmmword ptr [rbp+60h+DestinationString.Length], xmm1
0x180083c76  movdqu  xmmword ptr [rbp+60h+SourceFile.SecurityDescriptor], xmm0
0x180083c7b  call    ?BipStorageGetHiveMountPath@@YAJPEAU_UNICODE_STRING@@@Z; BipStorageGetHiveMountPath(_UNICODE_STRING *)
0x180083c80  mov     ebx, eax
0x180083c82  test    eax, eax
0x180083c84  jns     short loc_180083C8F
0x180083c86  lea     r8d, [rsi+0Ah]
0x180083c8a  jmp     loc_180083DC8
0x180083c8f  mov     [rsp+160h+var_128], rsi
0x180083c94  lea     rax, [rsp+160h+UnicodeString]
0x180083c99  xor     r9d, r9d; TrustClassKey
0x180083c9c  mov     [rbp+60h+TargetKey.ObjectName], rax
0x180083ca0  lea     rax, [rsp+160h+KeyHandle]
0x180083ca5  mov     [rbp+60h+TargetKey.Length], 30h ; '0'
0x180083cac  mov     [rsp+160h+var_130], rax
0x180083cb1  lea     rdx, [rsp+160h+SourceFile]; SourceFile
0x180083cb6  xorps   xmm0, xmm0
0x180083cb9  mov     dword ptr [rsp+160h+var_138], 0F003Fh
0x180083cc1  lea     r8d, [r9+10h]; Flags
0x180083cc5  mov     [rsp+160h+var_140], rsi
0x180083cca  lea     rcx, [rbp+60h+TargetKey]; TargetKey
0x180083cce  mov     [rbp+60h+TargetKey.RootDirectory], rsi
0x180083cd2  mov     [rbp+60h+TargetKey.Attributes], 40h ; '@'
0x180083cd9  movdqu  xmmword ptr [rbp+60h+TargetKey.SecurityDescriptor], xmm0
0x180083cde  call    cs:__imp_NtLoadKeyEx
0x180083ce4  mov     ebx, eax
0x180083ce6  cmp     eax, 0C000014Ch
0x180083ceb  jnz     loc_180083D9A
0x180083cf1  lea     rcx, [rsp+160h+SourceFile]; ObjectAttributes
0x180083cf6  call    cs:__imp_NtDeleteFile
0x180083cfc  mov     ebx, eax
0x180083cfe  test    eax, eax
0x180083d00  jns     short loc_180083D0D
0x180083d02  mov     r8d, 1Eh
0x180083d08  jmp     loc_180083DC8
0x180083d0d  mov     [rsp+160h+var_128], rsi
0x180083d12  lea     rax, [rsp+160h+KeyHandle]
0x180083d17  mov     [rsp+160h+var_130], rax
0x180083d1c  lea     rdx, [rsp+160h+SourceFile]; SourceFile
0x180083d21  xor     r9d, r9d; TrustClassKey
0x180083d24  mov     dword ptr [rsp+160h+var_138], 0F003Fh
0x180083d2c  lea     rcx, [rbp+60h+TargetKey]; TargetKey
0x180083d30  mov     [rsp+160h+var_140], rsi
0x180083d35  lea     r8d, [r9+10h]; Flags
0x180083d39  call    cs:__imp_NtLoadKeyEx
0x180083d3f  mov     ebx, eax
0x180083d41  test    eax, eax
0x180083d43  jns     short loc_180083D4D
0x180083d45  mov     r8d, 28h ; '('
0x180083d4b  jmp     short loc_180083DC8
0x180083d4d  lea     rcx, [rsp+160h+SystemTimeAsFileTime]; lpSystemTimeAsFileTime
0x180083d52  call    cs:__imp_GetSystemTimeAsFileTime
0x180083d58  mov     eax, [rsp+160h+SystemTimeAsFileTime.dwHighDateTime]
0x180083d5c  lea     rdx, aRecoveredfromc; "RecoveredFromCorruptedHive"
0x180083d63  mov     dword ptr [rsp+160h+var_110+4], eax
0x180083d67  lea     rcx, [rbp+60h+DestinationString]; DestinationString
0x180083d6b  mov     eax, [rsp+160h+SystemTimeAsFileTime.dwLowDateTime]
0x180083d6f  mov     dword ptr [rsp+160h+var_110], eax
0x180083d73  call    cs:__imp_RtlInitUnicodeString
0x180083d79  mov     r8, [rsp+160h+var_110]
0x180083d7e  lea     rdx, [rbp+60h+DestinationString]; ValueName
0x180083d82  mov     rcx, [rsp+160h+KeyHandle]; KeyHandle
0x180083d87  call    BipWriteRegUlong64
0x180083d8c  mov     ebx, eax
0x180083d8e  test    eax, eax
0x180083d90  jns     short loc_180083DA6
0x180083d92  mov     r8d, 32h ; '2'
0x180083d98  jmp     short loc_180083DC8
0x180083d9a  test    eax, eax
0x180083d9c  jns     short loc_180083DA6
0x180083d9e  mov     r8d, 14h
0x180083da4  jmp     short loc_180083DC8
0x180083da6  mov     r8d, esi
0x180083da9  mov     rax, [rsp+160h+KeyHandle]
0x180083dae  mov     ebx, esi
0x180083db0  mov     [rdi], rax
0x180083db3  mov     [rsp+160h+KeyHandle], rsi
0x180083db8  cmp     [rsp+160h+SystemTimeAsFileTime.dwHighDateTime], esi
0x180083dbc  jnz     short loc_180083DC8
0x180083dbe  cmp     [rsp+160h+SystemTimeAsFileTime.dwLowDateTime], esi
0x180083dc2  jz      loc_180083E61
0x180083dc8  mov     eax, cs:dword_1800C3098
0x180083dce  cmp     eax, 2
0x180083dd1  jbe     loc_180083E61
0x180083dd7  mov     rdx, 200000000000h
0x180083de1  lea     rcx, dword_1800C3098
0x180083de8  call    _tlgKeywordOn
0x180083ded  test    al, al
0x180083def  jz      short loc_180083E61
0x180083df1  mov     rax, qword ptr [rsp+160h+SystemTimeAsFileTime.dwLowDateTime]
0x180083df6  lea     rdx, word_1800B4ECA
0x180083dfd  mov     [rsp+160h+var_100], rax
0x180083e02  lea     rcx, dword_1800C3098
0x180083e09  lea     rax, [rsp+160h+var_100]
0x180083e0e  mov     [rsp+160h+var_108], r8d
0x180083e13  mov     [rbp+60h+var_30], rax
0x180083e17  xor     r9d, r9d
0x180083e1a  lea     rax, [rsp+160h+var_108]
0x180083e1f  mov     dword ptr [rsp+160h+var_110], ebx
0x180083e23  mov     [rbp+60h+var_40], rax
0x180083e27  xor     r8d, r8d
0x180083e2a  lea     rax, [rsp+160h+var_110]
0x180083e2f  mov     [rbp+60h+var_28], 8
0x180083e37  mov     [rbp+60h+var_50], rax
0x180083e3b  lea     rax, [rbp+60h+var_70]
0x180083e3f  mov     [rsp+160h+var_138], rax
0x180083e44  mov     dword ptr [rsp+160h+var_140], 5
0x180083e4c  mov     [rbp+60h+var_38], 4
0x180083e54  mov     [rbp+60h+var_48], 4
0x180083e5c  call    _tlgWriteTransfer_EventWriteTransfer
0x180083e61  lea     rcx, [rsp+160h+UnicodeString]; UnicodeString
0x180083e66  call    cs:__imp_RtlFreeUnicodeString
0x180083e6c  mov     eax, ebx
0x180083e6e  mov     rcx, [rbp+60h+var_20]
0x180083e72  xor     rcx, rsp; StackCookie
0x180083e75  call    __security_check_cookie
0x180083e7a  mov     rbx, [rsp+160h+arg_10]
0x180083e82  add     rsp, 150h
0x180083e89  pop     rdi
0x180083e8a  pop     rsi
0x180083e8b  pop     rbp
0x180083e8c  retn
```
