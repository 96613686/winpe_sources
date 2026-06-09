# AiGetTokens

- ea: `0x140035250`
- end: `0x140035434`
- name: `AiGetTokens`
- size: `484`
- prototype: ``
- caller_count: `2`
- callee_count: `3`
- tags: `reparse_path, authz_impersonation, broker_com_uri`

## callers

- `0x14002cd1c`
- `0x1400373b0`

## callees

- `0x1400274ac`
- `0x140027504`
- `0x140035250`

## import_xrefs

- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400352dc`
- `ntoskrnl!ZwOpenProcessTokenEx` at `0x1400352dc`
- `ntoskrnl!SeGetLogonSessionToken` at `0x1400353a0`
- `ntoskrnl!SeGetLogonSessionToken` at `0x1400353a0`
- `ntoskrnl!ZwOpenProcess` at `0x1400352ba`
- `ntoskrnl!ZwOpenProcess` at `0x1400352ba`
- `ntoskrnl!ZwQueryInformationToken` at `0x140035334`
- `ntoskrnl!ZwQueryInformationToken` at `0x140035334`
- `ntoskrnl!ZwClose` at `0x1400352f3`
- `ntoskrnl!ZwClose` at `0x1400353f5`
- `ntoskrnl!ZwClose` at `0x14003540e`
- `ntoskrnl!ZwClose` at `0x1400352f3`
- `ntoskrnl!ZwClose` at `0x1400353f5`
- `ntoskrnl!ZwClose` at `0x14003540e`

## pseudocode

```c
__int64 __fastcall AiGetTokens(void *a1, void **a2, _QWORD *a3)
{
  NTSTATUS IsTokenElevated; // ebx
  NTSTATUS v6; // eax
  char v7; // di
  HANDLE v8; // rax
  HANDLE v9; // rsi
  HANDLE v10; // rdi
  ULONG ReturnLength; // [rsp+30h] [rbp-29h] BYREF
  void *TokenHandle; // [rsp+38h] [rbp-21h] BYREF
  HANDLE Handle; // [rsp+40h] [rbp-19h] BYREF
  struct _CLIENT_ID ClientId; // [rsp+48h] [rbp-11h] BYREF
  struct _OBJECT_ATTRIBUTES ObjectAttributes; // [rsp+58h] [rbp-1h] BYREF
  char v17; // [rsp+C0h] [rbp+67h] BYREF
  void *ProcessHandle; // [rsp+D8h] [rbp+7Fh] BYREF

  ClientId.UniqueProcess = a1;
  TokenHandle = 0;
  v17 = 0;
  Handle = 0;
  ProcessHandle = 0;
  ObjectAttributes.RootDirectory = 0;
  ObjectAttributes.ObjectName = 0;
  ClientId.UniqueThread = 0;
  *(_OWORD *)&ObjectAttributes.SecurityDescriptor = 0;
  *(_QWORD *)&ObjectAttributes.Length = 48;
  *(_QWORD *)&ObjectAttributes.Attributes = 512;
  IsTokenElevated = ZwOpenProcess(&ProcessHandle, 0x400u, &ObjectAttributes, &ClientId);
  if ( IsTokenElevated >= 0 )
    IsTokenElevated = ZwOpenProcessTokenEx(ProcessHandle, 0, 0x200u, &TokenHandle);
  if ( ProcessHandle )
    ZwClose(ProcessHandle);
  if ( IsTokenElevated >= 0 )
  {
    if ( !a3 )
    {
LABEL_23:
      IsTokenElevated = 0;
      *a2 = TokenHandle;
      TokenHandle = 0;
      goto LABEL_24;
    }
    ReturnLength = 0;
    LODWORD(ProcessHandle) = 0;
    v6 = ZwQueryInformationToken(TokenHandle, TokenIsRestricted, &ProcessHandle, 4u, &ReturnLength);
    IsTokenElevated = v6;
    if ( v6 >= 0 && (_DWORD)ProcessHandle )
    {
      v7 = 1;
    }
    else
    {
      v7 = 0;
      if ( v6 < 0 )
        goto LABEL_24;
    }
    if ( !DisableExeLinkedTokenLookup )
    {
      IsTokenElevated = AiIsTokenElevated(TokenHandle, &v17);
      if ( IsTokenElevated < 0 )
        goto LABEL_24;
      if ( !v17 )
        IsTokenElevated = AiGetLinkedTokenHandle(TokenHandle, &Handle);
    }
    if ( !v7
      || IsTokenElevated >= 0
      || (IsTokenElevated = SeGetLogonSessionToken(TokenHandle, 0, &Handle), (int)(IsTokenElevated + 0x80000000) < 0)
      || IsTokenElevated == -1073741700 )
    {
      v8 = Handle;
      if ( Handle )
        Handle = 0;
      else
        v8 = TokenHandle;
      *a3 = v8;
      goto LABEL_23;
    }
  }
LABEL_24:
  v9 = TokenHandle;
  v10 = Handle;
  if ( TokenHandle )
    ZwClose(TokenHandle);
  if ( v10 && v10 != v9 )
    ZwClose(v10);
  return (unsigned int)IsTokenElevated;
}

```

## disassembly

```asm
0x140035250  mov     [rsp-8+arg_8], rbx
0x140035255  push    rbp
0x140035256  push    rsi
0x140035257  push    rdi
0x140035258  push    r14
0x14003525a  push    r15
0x14003525c  lea     rbp, [rsp-37h]
0x140035261  sub     rsp, 90h
0x140035268  xor     r15d, r15d
0x14003526b  mov     [rbp+57h+ClientId.UniqueProcess], rcx
0x14003526f  mov     rsi, r8
0x140035272  mov     [rbp+57h+TokenHandle], r15
0x140035276  mov     r14, rdx
0x140035279  mov     [rbp+57h+arg_0], r15b
0x14003527d  xorps   xmm0, xmm0
0x140035280  mov     [rbp+57h+Handle], r15
0x140035284  lea     r8, [rbp+57h+ObjectAttributes]; ObjectAttributes
0x140035288  mov     [rbp+57h+ProcessHandle], r15
0x14003528c  mov     edx, 400h; DesiredAccess
0x140035291  mov     [rbp+57h+ObjectAttributes.RootDirectory], r15
0x140035295  lea     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x140035299  mov     [rbp+57h+ObjectAttributes.ObjectName], r15
0x14003529d  lea     r9, [rbp+57h+ClientId]; ClientId
0x1400352a1  mov     [rbp+57h+ClientId.UniqueThread], r15
0x1400352a5  movdqu  xmmword ptr [rbp+57h+ObjectAttributes.SecurityDescriptor], xmm0
0x1400352aa  mov     qword ptr [rbp+57h+ObjectAttributes.Length], 30h ; '0'
0x1400352b2  mov     qword ptr [rbp+57h+ObjectAttributes.Attributes], 200h
0x1400352ba  call    cs:__imp_ZwOpenProcess
0x1400352c1  nop     dword ptr [rax+rax+00h]
0x1400352c6  mov     ebx, eax
0x1400352c8  test    eax, eax
0x1400352ca  js      short loc_1400352EA
0x1400352cc  mov     rcx, [rbp+57h+ProcessHandle]; ProcessHandle
0x1400352d0  lea     r9, [rbp+57h+TokenHandle]; TokenHandle
0x1400352d4  xor     edx, edx; DesiredAccess
0x1400352d6  mov     r8d, 200h; HandleAttributes
0x1400352dc  call    cs:__imp_ZwOpenProcessTokenEx
0x1400352e3  nop     dword ptr [rax+rax+00h]
0x1400352e8  mov     ebx, eax
0x1400352ea  mov     rcx, [rbp+57h+ProcessHandle]; Handle
0x1400352ee  test    rcx, rcx
0x1400352f1  jz      short loc_1400352FF
0x1400352f3  call    cs:__imp_ZwClose
0x1400352fa  nop     dword ptr [rax+rax+00h]
0x1400352ff  test    ebx, ebx
0x140035301  js      loc_1400353E5
0x140035307  test    rsi, rsi
0x14003530a  jz      loc_1400353D7
0x140035310  mov     rcx, [rbp+57h+TokenHandle]; TokenHandle
0x140035314  lea     rax, [rbp+57h+var_80]
0x140035318  mov     r9d, 4; TokenInformationLength
0x14003531e  mov     [rsp+0B0h+ReturnLength], rax; ReturnLength
0x140035323  lea     r8, [rbp+57h+ProcessHandle]; TokenInformation
0x140035327  mov     [rbp+57h+var_80], r15d
0x14003532b  mov     edx, 28h ; '('; TokenInformationClass
0x140035330  mov     dword ptr [rbp+57h+ProcessHandle], r15d
0x140035334  call    cs:__imp_ZwQueryInformationToken
0x14003533b  nop     dword ptr [rax+rax+00h]
0x140035340  mov     ebx, eax
0x140035342  test    eax, eax
0x140035344  js      short loc_140035351
0x140035346  cmp     dword ptr [rbp+57h+ProcessHandle], r15d
0x14003534a  jz      short loc_140035351
0x14003534c  mov     dil, 1
0x14003534f  jmp     short loc_14003535C
0x140035351  xor     dil, dil
0x140035354  test    eax, eax
0x140035356  js      loc_1400353E5
0x14003535c  cmp     cs:DisableExeLinkedTokenLookup, r15b
0x140035363  jnz     short loc_14003538D
0x140035365  mov     rcx, [rbp+57h+TokenHandle]
0x140035369  lea     rdx, [rbp+57h+arg_0]
0x14003536d  call    AiIsTokenElevated
0x140035372  mov     ebx, eax
0x140035374  test    eax, eax
0x140035376  js      short loc_1400353E5
0x140035378  cmp     [rbp+57h+arg_0], r15b
0x14003537c  jnz     short loc_14003538D
0x14003537e  mov     rcx, [rbp+57h+TokenHandle]
0x140035382  lea     rdx, [rbp+57h+Handle]
0x140035386  call    AiGetLinkedTokenHandle
0x14003538b  mov     ebx, eax
0x14003538d  test    dil, dil
0x140035390  jz      short loc_1400353C1
0x140035392  test    ebx, ebx
0x140035394  jns     short loc_1400353C1
0x140035396  mov     rcx, [rbp+57h+TokenHandle]
0x14003539a  lea     r8, [rbp+57h+Handle]
0x14003539e  xor     edx, edx
0x1400353a0  call    cs:__imp_SeGetLogonSessionToken
0x1400353a7  nop     dword ptr [rax+rax+00h]
0x1400353ac  mov     ecx, 80000000h
0x1400353b1  mov     ebx, eax
0x1400353b3  add     eax, ecx
0x1400353b5  test    ecx, eax
0x1400353b7  jnz     short loc_1400353C1
0x1400353b9  cmp     ebx, 0C000007Ch
0x1400353bf  jnz     short loc_1400353E5
0x1400353c1  mov     rax, [rbp+57h+Handle]
0x1400353c5  test    rax, rax
0x1400353c8  jz      short loc_1400353D0
0x1400353ca  mov     [rbp+57h+Handle], r15
0x1400353ce  jmp     short loc_1400353D4
0x1400353d0  mov     rax, [rbp+57h+TokenHandle]
0x1400353d4  mov     [rsi], rax
0x1400353d7  mov     rax, [rbp+57h+TokenHandle]
0x1400353db  mov     ebx, r15d
0x1400353de  mov     [r14], rax
0x1400353e1  mov     [rbp+57h+TokenHandle], r15
0x1400353e5  mov     rsi, [rbp+57h+TokenHandle]
0x1400353e9  mov     rdi, [rbp+57h+Handle]
0x1400353ed  test    rsi, rsi
0x1400353f0  jz      short loc_140035401
0x1400353f2  mov     rcx, rsi; Handle
0x1400353f5  call    cs:__imp_ZwClose
0x1400353fc  nop     dword ptr [rax+rax+00h]
0x140035401  test    rdi, rdi
0x140035404  jz      short loc_14003541A
0x140035406  cmp     rdi, rsi
0x140035409  jz      short loc_14003541A
0x14003540b  mov     rcx, rdi; Handle
0x14003540e  call    cs:__imp_ZwClose
0x140035415  nop     dword ptr [rax+rax+00h]
0x14003541a  mov     eax, ebx
0x14003541c  mov     rbx, [rsp+0B0h+arg_8]
0x140035424  add     rsp, 90h
0x14003542b  pop     r15
0x14003542d  pop     r14
0x14003542f  pop     rdi
0x140035430  pop     rsi
0x140035431  pop     rbp
0x140035432  retn
```
