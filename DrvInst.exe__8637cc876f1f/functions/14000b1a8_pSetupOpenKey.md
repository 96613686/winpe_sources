# pSetupOpenKey

- ea: `0x14000b1a8`
- end: `0x14000b283`
- name: `pSetupOpenKey`
- size: `219`
- prototype: ``
- caller_count: `1`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, loader_planting, installer_update, broker_com_uri`

## callers

- `0x14000b28c`

## callees

- `0x14000aedc`
- `0x14000b1a8`
- `0x14000b2a8`

## import_xrefs

- `ntdll!NtOpenKey` at `0x14000b246`
- `ntdll!NtOpenKey` at `0x14000b246`
- `ntdll!RtlInitUnicodeString` at `0x14000b20c`
- `ntdll!RtlInitUnicodeString` at `0x14000b20c`
- `ntdll!RtlNtStatusToDosError` at `0x14000b252`
- `ntdll!RtlNtStatusToDosError` at `0x14000b252`

## pseudocode

```c
__int64 __fastcall pSetupOpenKey(void *a1, const WCHAR *a2, __int64 a3, ACCESS_MASK a4, _QWORD *a5)
{
  void *v5; // rbx
  void *v8; // rsi
  ULONG v9; // edi
  ULONG v10; // eax
  int v11; // eax
  void *KeyHandle; // [rsp+20h] [rbp-58h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+28h] [rbp-50h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+38h] [rbp-40h] BYREF
  void *v16; // [rsp+B0h] [rbp+38h] BYREF

  KeyHandle = 0;
  v5 = 0;
  v16 = 0;
  v8 = a1;
  DestinationString = 0;
  memset(&ObjectAttributes, 0, 44);
  if ( (unsigned __int64)a1 + 0x80000000 <= 7 )
  {
    v10 = pSetupOpenPredefinedKey(a1, &v16);
    v5 = v16;
    v9 = v10;
    if ( v10 )
      goto LABEL_9;
  }
  else
  {
    v9 = 0;
  }
  RtlInitUnicodeString(&DestinationString, a2);
  ObjectAttributes.Length = 48;
  ObjectAttributes.Attributes = 64;
  ObjectAttributes.ObjectName = &DestinationString;
  if ( v5 )
    v8 = v5;
  ObjectAttributes.RootDirectory = v8;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  v11 = NtOpenKey(&KeyHandle, a4, &ObjectAttributes);
  if ( v11 >= 0 )
    *a5 = (int)KeyHandle;
  else
    v9 = RtlNtStatusToDosError(v11);
LABEL_9:
  if ( v5 )
    pSetupCloseKey(v5);
  return v9;
}

```

## disassembly

```asm
0x14000b1a8  push    rbp
0x14000b1aa  push    rbx
0x14000b1ab  push    rsi
0x14000b1ac  push    rdi
0x14000b1ad  push    r14
0x14000b1af  push    r15
0x14000b1b1  mov     rbp, rsp
0x14000b1b4  sub     rsp, 78h
0x14000b1b8  xor     eax, eax
0x14000b1ba  xorps   xmm0, xmm0
0x14000b1bd  mov     [rbp+KeyHandle], rax
0x14000b1c1  xor     ebx, ebx
0x14000b1c3  mov     eax, 80000000h
0x14000b1c8  mov     [rbp+arg_0], rbx
0x14000b1cc  add     rax, rcx
0x14000b1cf  mov     r14d, r9d
0x14000b1d2  mov     r15, rdx
0x14000b1d5  mov     rsi, rcx
0x14000b1d8  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000b1dc  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14000b1e0  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000b1e4  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000b1e8  cmp     rax, 7
0x14000b1ec  jbe     short loc_14000B1F2
0x14000b1ee  xor     edi, edi
0x14000b1f0  jmp     short loc_14000B205
0x14000b1f2  lea     rdx, [rbp+arg_0]
0x14000b1f6  call    pSetupOpenPredefinedKey
0x14000b1fb  mov     rbx, [rbp+arg_0]
0x14000b1ff  mov     edi, eax
0x14000b201  test    eax, eax
0x14000b203  jnz     short loc_14000B267
0x14000b205  mov     rdx, r15; SourceString
0x14000b208  lea     rcx, [rbp+DestinationString]; DestinationString
0x14000b20c  call    cs:__imp_RtlInitUnicodeString
0x14000b212  lea     rax, [rbp+DestinationString]
0x14000b216  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000b21d  xorps   xmm0, xmm0
0x14000b220  mov     [rbp+ObjectAttributes.Attributes], 40h ; '@'
0x14000b227  test    rbx, rbx
0x14000b22a  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000b22e  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000b232  mov     edx, r14d; DesiredAccess
0x14000b235  cmovnz  rsi, rbx
0x14000b239  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000b23d  mov     [rbp+ObjectAttributes.RootDirectory], rsi
0x14000b241  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000b246  call    cs:__imp_NtOpenKey
0x14000b24c  test    eax, eax
0x14000b24e  jns     short loc_14000B25C
0x14000b250  mov     ecx, eax; Status
0x14000b252  call    cs:__imp_RtlNtStatusToDosError
0x14000b258  mov     edi, eax
0x14000b25a  jmp     short loc_14000B267
0x14000b25c  mov     rax, [rbp+arg_20]
0x14000b260  movsxd  rcx, dword ptr [rbp+KeyHandle]
0x14000b264  mov     [rax], rcx
0x14000b267  test    rbx, rbx
0x14000b26a  jz      short loc_14000B274
0x14000b26c  mov     rcx, rbx
0x14000b26f  call    pSetupCloseKey
0x14000b274  mov     eax, edi
0x14000b276  add     rsp, 78h
0x14000b27a  pop     r15
0x14000b27c  pop     r14
0x14000b27e  pop     rdi
0x14000b27f  pop     rsi
0x14000b280  pop     rbx
0x14000b281  pop     rbp
0x14000b282  retn
```
