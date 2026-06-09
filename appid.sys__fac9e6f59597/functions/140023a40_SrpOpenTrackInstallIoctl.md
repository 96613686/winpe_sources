# SrpOpenTrackInstallIoctl

- ea: `0x140023a40`
- end: `0x140023bfd`
- name: `SrpOpenTrackInstallIoctl`
- size: `445`
- prototype: `__int64()`
- caller_count: `1`
- callee_count: `9`
- tags: `registry_config, installer_update`

## callers

- `0x140033f50`

## callees

- `0x1400208a0`
- `0x1400211f4`
- `0x140023a40`
- `0x140030ab0`
- `0x1400328b0`
- `0x140032f60`
- `0x140033130`
- `0x140035440`
- `0x140035460`

## import_xrefs

- `ntoskrnl!ObReferenceObjectByHandle` at `0x140023aeb`
- `ntoskrnl!ObReferenceObjectByHandle` at `0x140023aeb`
- `ntoskrnl!ObfDereferenceObject` at `0x140023bde`
- `ntoskrnl!ObfDereferenceObject` at `0x140023bde`
- `ntoskrnl!SeTokenObjectType` at `0x140023b23`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140023b51`
- `ntoskrnl!ObOpenObjectByPointer` at `0x140023b51`
- `ntoskrnl!PsProcessType` at `0x140023abb`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140023b0b`
- `ntoskrnl!PsReferencePrimaryToken` at `0x140023b0b`
- `ntoskrnl!ObCloseHandle` at `0x140023bbb`
- `ntoskrnl!ObCloseHandle` at `0x140023bbb`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140023bcf`
- `ntoskrnl!PsDereferencePrimaryToken` at `0x140023bcf`

## pseudocode

```c
__int64 SrpOpenTrackInstallIoctl()
{
  __int64 Policy; // rax
  __int64 v1; // rbx
  char v2; // di
  PVOID v3; // rdi
  unsigned int v4; // ebx
  PACCESS_TOKEN v5; // rsi
  unsigned int v6; // eax
  _QWORD v8[3]; // [rsp+40h] [rbp-18h] BYREF
  unsigned int v9; // [rsp+80h] [rbp+28h] BYREF
  __int64 v10; // [rsp+88h] [rbp+30h] BYREF
  HANDLE Handle; // [rsp+90h] [rbp+38h] BYREF
  PVOID Object; // [rsp+98h] [rbp+40h] BYREF

  Handle = 0;
  v9 = 0;
  v10 = 0;
  v8[0] = 0;
  if ( (unsigned int)SmartlockerRegistryDisableOverrideIsSet() )
    return 3221225473LL;
  Policy = SrpGetPolicy();
  v1 = Policy;
  if ( Policy && *(int *)(Policy + 176) >= 0 && *(_DWORD *)(*(_QWORD *)(Policy + 184) + 12LL)
    || (v2 = 0, (unsigned int)SmartlockerSmartScreenRegistryIsEnabled()) )
  {
    v2 = 1;
  }
  SrpReleasePolicy(v1);
  if ( !v2 )
    return 3221225473LL;
  Object = 0;
  if ( ObReferenceObjectByHandle((HANDLE)0xFFFFFFFFFFFFFFFFLL, 0x1FFFFFu, (POBJECT_TYPE)PsProcessType, 0, &Object, 0) < 0 )
    return 3221225473LL;
  v3 = Object;
  v4 = -1073741823;
  v5 = PsReferencePrimaryToken((PEPROCESS)Object);
  if ( v5 && ObOpenObjectByPointer(v5, 0x200u, 0, 8u, (POBJECT_TYPE)SeTokenObjectType, 0, &Handle) >= 0 )
  {
    if ( (int)SmartlockerOriginClaimProcessTokenCheck(
                (_DWORD)Handle,
                0,
                0,
                (unsigned int)&v9,
                (__int64)&v10,
                (__int64)v8) >= 0 )
    {
      v6 = AiReferenceProcOriginList(v3, v10, v9);
LABEL_15:
      v4 = v6;
      goto LABEL_16;
    }
    if ( v10 )
    {
      v6 = AiFindAndDuplicateSessionToOriginList(v3);
      goto LABEL_15;
    }
  }
LABEL_16:
  AiFree(v8[0]);
  ObCloseHandle(Handle, 0);
  if ( v5 )
    PsDereferencePrimaryToken(v5);
  ObfDereferenceObject(v3);
  return v4;
}

```

## disassembly

```asm
0x140023a40  push    rbp
0x140023a42  push    rbx
0x140023a43  push    rsi
0x140023a44  push    rdi
0x140023a45  mov     rbp, rsp
0x140023a48  sub     rsp, 58h
0x140023a4c  mov     [rbp+arg_10], 0
0x140023a54  mov     [rbp+arg_0], 0
0x140023a5b  mov     [rbp+arg_8], 0
0x140023a63  mov     [rbp+var_18], 0
0x140023a6b  call    SmartlockerRegistryDisableOverrideIsSet
0x140023a70  test    eax, eax
0x140023a72  jnz     loc_140023BEE
0x140023a78  call    SrpGetPolicy
0x140023a7d  mov     rbx, rax
0x140023a80  test    rax, rax
0x140023a83  jz      short loc_140023A9B
0x140023a85  cmp     dword ptr [rax+0B0h], 0
0x140023a8c  jl      short loc_140023A9B
0x140023a8e  mov     rcx, [rax+0B8h]
0x140023a95  cmp     dword ptr [rcx+0Ch], 0
0x140023a99  jnz     short loc_140023AA7
0x140023a9b  xor     dil, dil
0x140023a9e  call    SmartlockerSmartScreenRegistryIsEnabled
0x140023aa3  test    eax, eax
0x140023aa5  jz      short loc_140023AAA
0x140023aa7  mov     dil, 1
0x140023aaa  mov     rcx, rbx
0x140023aad  call    SrpReleasePolicy
0x140023ab2  test    dil, dil
0x140023ab5  jz      loc_140023BEE
0x140023abb  mov     r8, cs:__imp_PsProcessType
0x140023ac2  lea     rax, [rbp+arg_18]
0x140023ac6  mov     [rsp+58h+HandleInformation], 0; HandleInformation
0x140023acf  xor     r9d, r9d; AccessMode
0x140023ad2  mov     edx, 1FFFFFh; DesiredAccess
0x140023ad7  mov     [rbp+arg_18], 0
0x140023adf  or      rcx, 0FFFFFFFFFFFFFFFFh; Handle
0x140023ae3  mov     [rsp+58h+Object], rax; Object
0x140023ae8  mov     r8, [r8]; ObjectType
0x140023aeb  call    cs:__imp_ObReferenceObjectByHandle
0x140023af2  nop     dword ptr [rax+rax+00h]
0x140023af7  test    eax, eax
0x140023af9  js      loc_140023BEE
0x140023aff  mov     rdi, [rbp+arg_18]
0x140023b03  mov     ebx, 0C0000001h
0x140023b08  mov     rcx, rdi; Process
0x140023b0b  call    cs:__imp_PsReferencePrimaryToken
0x140023b12  nop     dword ptr [rax+rax+00h]
0x140023b17  mov     rsi, rax
0x140023b1a  test    rax, rax
0x140023b1d  jz      loc_140023BAC
0x140023b23  mov     rcx, cs:__imp_SeTokenObjectType
0x140023b2a  lea     rax, [rbp+arg_10]
0x140023b2e  mov     [rsp+58h+Handle], rax; Handle
0x140023b33  mov     r9d, 8; DesiredAccess
0x140023b39  mov     byte ptr [rsp+58h+HandleInformation], 0; AccessMode
0x140023b3e  xor     r8d, r8d; PassedAccessState
0x140023b41  mov     rdx, [rcx]
0x140023b44  mov     rcx, rsi; Object
0x140023b47  mov     [rsp+58h+Object], rdx; ObjectType
0x140023b4c  mov     edx, 200h; HandleAttributes
0x140023b51  call    cs:__imp_ObOpenObjectByPointer
0x140023b58  nop     dword ptr [rax+rax+00h]
0x140023b5d  test    eax, eax
0x140023b5f  js      short loc_140023BAC
0x140023b61  mov     rcx, [rbp+arg_10]
0x140023b65  lea     rax, [rbp+var_18]
0x140023b69  mov     [rsp+58h+HandleInformation], rax
0x140023b6e  lea     r9, [rbp+arg_0]
0x140023b72  lea     rax, [rbp+arg_8]
0x140023b76  xor     r8d, r8d
0x140023b79  xor     edx, edx
0x140023b7b  mov     [rsp+58h+Object], rax
0x140023b80  call    SmartlockerOriginClaimProcessTokenCheck
0x140023b85  test    eax, eax
0x140023b87  js      short loc_140023B9B
0x140023b89  mov     r8d, [rbp+arg_0]
0x140023b8d  mov     rcx, rdi
0x140023b90  mov     rdx, [rbp+arg_8]
0x140023b94  call    AiReferenceProcOriginList
0x140023b99  jmp     short loc_140023BAA
0x140023b9b  cmp     [rbp+arg_8], 0
0x140023ba0  jz      short loc_140023BAC
0x140023ba2  mov     rcx, rdi
0x140023ba5  call    AiFindAndDuplicateSessionToOriginList
0x140023baa  mov     ebx, eax
0x140023bac  mov     rcx, [rbp+var_18]
0x140023bb0  call    AiFree
0x140023bb5  mov     rcx, [rbp+arg_10]; Handle
0x140023bb9  xor     edx, edx; PreviousMode
0x140023bbb  call    cs:__imp_ObCloseHandle
0x140023bc2  nop     dword ptr [rax+rax+00h]
0x140023bc7  test    rsi, rsi
0x140023bca  jz      short loc_140023BDB
0x140023bcc  mov     rcx, rsi; PrimaryToken
0x140023bcf  call    cs:__imp_PsDereferencePrimaryToken
0x140023bd6  nop     dword ptr [rax+rax+00h]
0x140023bdb  mov     rcx, rdi; Object
0x140023bde  call    cs:__imp_ObfDereferenceObject
0x140023be5  nop     dword ptr [rax+rax+00h]
0x140023bea  mov     eax, ebx
0x140023bec  jmp     short loc_140023BF3
0x140023bee  mov     eax, 0C0000001h
0x140023bf3  add     rsp, 58h
0x140023bf7  pop     rdi
0x140023bf8  pop     rsi
0x140023bf9  pop     rbx
0x140023bfa  pop     rbp
0x140023bfb  retn
```
