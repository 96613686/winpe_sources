# BamUserSettingsInitialize

- ea: `0x14000ce58`
- end: `0x14000cfc1`
- name: `BamUserSettingsInitialize`
- size: `361`
- prototype: `__int64 __fastcall(_QWORD)`
- caller_count: `1`
- callee_count: `5`
- tags: `reparse_path, authz_impersonation, registry_config, broker_com_uri`

## callers

- `0x140016078`

## callees

- `0x14000ba5c`
- `0x14000cc54`
- `0x14000ce58`
- `0x1400113a0`
- `0x1400113f0`

## import_xrefs

- `ntoskrnl!ZwClose` at `0x14000cf8c`
- `ntoskrnl!ZwClose` at `0x14000cfa1`
- `ntoskrnl!ZwClose` at `0x14000cf8c`
- `ntoskrnl!ZwClose` at `0x14000cfa1`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14000cea0`
- `ntoskrnl!IoOpenDriverRegistryKey` at `0x14000cea0`
- `ntoskrnl!ZwCreateKey` at `0x14000cf09`
- `ntoskrnl!ZwCreateKey` at `0x14000cf09`

## pseudocode

```c
__int64 __fastcall BamUserSettingsInitialize(__int64 a1)
{
  NTSTATUS v1; // ebx
  __int64 v2; // rcx
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+50h] [rbp-30h] BYREF
  ULONG Disposition; // [rsp+98h] [rbp+18h] BYREF
  void *KeyHandle; // [rsp+A0h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+A8h] [rbp+28h]

  Disposition = 0;
  Handle = 0;
  KeyHandle = 0;
  memset(&ObjectAttributes, 0, 44);
  v1 = IoOpenDriverRegistryKey(a1, 1, 4);
  if ( v1 >= 0 )
  {
    ObjectAttributes.RootDirectory = Handle;
    ObjectAttributes.Length = 48;
    ObjectAttributes.ObjectName = (PUNICODE_STRING)&BampUserSettingsKeyName;
    ObjectAttributes.Attributes = 576;
    *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
    v1 = ZwCreateKey(&KeyHandle, 0xF003Fu, &ObjectAttributes, 0, 0, 0, &Disposition);
    if ( v1 >= 0 )
    {
      BampUserSettingsContext = KeyHandle;
      *(_WORD *)((char *)&BampUserSettingsContext + 13) = 0;
      *((_BYTE *)&BampUserSettingsContext + 15) = 0;
      KeyHandle = 0;
      *((_DWORD *)&BampUserSettingsContext + 2) = 0;
      *((_BYTE *)&BampUserSettingsContext + 12) = 1;
      if ( Disposition == 2 )
        BamUserSettingsEnumerateUsers(BampInitializeUsersCallback, 0);
      BampAcquireThrottlingWorkerLock();
      if ( (byte_1400075A8 & 1) == 0 )
      {
        LOBYTE(v2) = 1;
        BampQueueUserSettingsActionItem(v2);
      }
      BampReleaseThrottlingWorkerLock();
      v1 = 0;
    }
  }
  if ( KeyHandle )
    ZwClose(KeyHandle);
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)v1;
}

```

## disassembly

```asm
0x14000ce58  mov     [rsp-8+arg_0], rbx
0x14000ce5d  push    rbp
0x14000ce5e  mov     rbp, rsp
0x14000ce61  sub     rsp, 80h
0x14000ce68  xorps   xmm0, xmm0
0x14000ce6b  mov     [rbp+arg_8], 0
0x14000ce72  xor     eax, eax
0x14000ce74  xor     r9d, r9d
0x14000ce77  mov     [rbp+Handle], rax
0x14000ce7b  mov     [rbp+KeyHandle], rax
0x14000ce7f  lea     rax, [rbp+Handle]
0x14000ce83  movups  xmmword ptr [rbp+ObjectAttributes.ObjectName], xmm0
0x14000ce87  lea     edx, [r9+1]
0x14000ce8b  mov     [rsp+80h+Class], rax
0x14000ce90  lea     r8d, [r9+4]
0x14000ce94  movups  xmmword ptr [rbp+ObjectAttributes.Length], xmm0
0x14000ce98  movups  xmmword ptr [rbp+ObjectAttributes+1Ch], xmm0
0x14000ce9c  movups  [rbp+var_40], xmm0
0x14000cea0  call    cs:__imp_IoOpenDriverRegistryKey
0x14000cea7  nop     dword ptr [rax+rax+00h]
0x14000ceac  mov     ebx, eax
0x14000ceae  test    eax, eax
0x14000ceb0  js      loc_14000CF83
0x14000ceb6  mov     rax, [rbp+Handle]
0x14000ceba  lea     r8, [rbp+ObjectAttributes]; ObjectAttributes
0x14000cebe  mov     [rbp+ObjectAttributes.RootDirectory], rax
0x14000cec2  lea     rcx, [rbp+KeyHandle]; KeyHandle
0x14000cec6  lea     rax, BampUserSettingsKeyName
0x14000cecd  mov     [rbp+ObjectAttributes.Length], 30h ; '0'
0x14000ced4  mov     [rbp+ObjectAttributes.ObjectName], rax
0x14000ced8  xorps   xmm0, xmm0
0x14000cedb  lea     rax, [rbp+arg_8]
0x14000cedf  mov     [rbp+ObjectAttributes.Attributes], 240h
0x14000cee6  mov     [rsp+80h+Disposition], rax; Disposition
0x14000ceeb  xor     r9d, r9d; TitleIndex
0x14000ceee  mov     [rsp+80h+CreateOptions], 0; CreateOptions
0x14000cef6  mov     edx, 0F003Fh; DesiredAccess
0x14000cefb  mov     [rsp+80h+Class], 0; Class
0x14000cf04  movdqu  xmmword ptr [rbp+ObjectAttributes.SecurityDescriptor], xmm0
0x14000cf09  call    cs:__imp_ZwCreateKey
0x14000cf10  nop     dword ptr [rax+rax+00h]
0x14000cf15  mov     ebx, eax
0x14000cf17  test    eax, eax
0x14000cf19  js      short loc_14000CF83
0x14000cf1b  cmp     [rbp+arg_8], 2
0x14000cf1f  mov     rax, [rbp+KeyHandle]
0x14000cf23  mov     qword ptr cs:BampUserSettingsContext, rax
0x14000cf2a  movzx   eax, word ptr [rbp+var_40+0Dh]
0x14000cf2e  mov     word ptr cs:BampUserSettingsContext+0Dh, ax
0x14000cf35  mov     al, byte ptr [rbp+var_40+0Fh]
0x14000cf38  mov     byte ptr cs:BampUserSettingsContext+0Fh, al
0x14000cf3e  mov     [rbp+KeyHandle], 0
0x14000cf46  mov     dword ptr cs:BampUserSettingsContext+8, 0
0x14000cf50  mov     byte ptr cs:BampUserSettingsContext+0Ch, 1
0x14000cf57  jnz     short loc_14000CF67
0x14000cf59  xor     edx, edx
0x14000cf5b  lea     rcx, BampInitializeUsersCallback
0x14000cf62  call    BamUserSettingsEnumerateUsers
0x14000cf67  call    BampAcquireThrottlingWorkerLock
0x14000cf6c  test    cs:byte_1400075A8, 1
0x14000cf73  jnz     short loc_14000CF7C
0x14000cf75  mov     cl, 1
0x14000cf77  call    BampQueueUserSettingsActionItem
0x14000cf7c  call    BampReleaseThrottlingWorkerLock
0x14000cf81  xor     ebx, ebx
0x14000cf83  mov     rcx, [rbp+KeyHandle]; Handle
0x14000cf87  test    rcx, rcx
0x14000cf8a  jz      short loc_14000CF98
0x14000cf8c  call    cs:__imp_ZwClose
0x14000cf93  nop     dword ptr [rax+rax+00h]
0x14000cf98  mov     rcx, [rbp+Handle]; Handle
0x14000cf9c  test    rcx, rcx
0x14000cf9f  jz      short loc_14000CFAD
0x14000cfa1  call    cs:__imp_ZwClose
0x14000cfa8  nop     dword ptr [rax+rax+00h]
0x14000cfad  mov     eax, ebx
0x14000cfaf  mov     rbx, [rsp+80h+arg_0]
0x14000cfb7  add     rsp, 80h
0x14000cfbe  pop     rbp
0x14000cfbf  retn
```
