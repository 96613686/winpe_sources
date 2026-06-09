# UbpmUtilsGetConsumerSid(ushort const *,ulong,void * *,ulong *)

- ea: `0x18002b3a8`
- end: `0x18002b498`
- name: `?UbpmUtilsGetConsumerSid@@YAKPEBGKPEAPEAXPEAK@Z`
- size: `240`
- prototype: `unsigned int __fastcall(PCWSTR SourceString, unsigned int, void **, unsigned int *)`
- caller_count: `2`
- callee_count: `3`
- tags: `authz_impersonation, loader_planting`

## callers

- `0x18002af20`
- `0x18002cae0`

## callees

- `0x18000fbf0`
- `0x1800150c0`
- `0x18002b3a8`

## import_xrefs

- `ntdll!RtlCreateVirtualAccountSid` at `0x18002b400`
- `ntdll!RtlCreateVirtualAccountSid` at `0x18002b433`
- `ntdll!RtlCreateVirtualAccountSid` at `0x18002b400`
- `ntdll!RtlCreateVirtualAccountSid` at `0x18002b433`
- `ntdll!RtlInitUnicodeString` at `0x18002b3e5`
- `ntdll!RtlInitUnicodeString` at `0x18002b3e5`
- `ntdll!RtlNtStatusToDosError` at `0x18002b48a`
- `ntdll!RtlNtStatusToDosError` at `0x18002b48a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b46a`
- `api-ms-win-core-errorhandling-l1-1-0!GetLastError` at `0x18002b46a`

## pseudocode

```c
__int64 __fastcall UbpmUtilsGetConsumerSid(PCWSTR SourceString, __int64 a2, void **a3, unsigned int *a4)
{
  void *v4; // rdi
  unsigned int v7; // ebx
  void *v8; // rax
  NTSTATUS v9; // eax
  unsigned int v10; // ebx
  DWORD LastError; // eax
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-38h] BYREF
  SIZE_T Size; // [rsp+60h] [rbp+8h] BYREF

  v4 = 0;
  LODWORD(Size) = 0;
  v7 = a2;
  DestinationString = 0;
  if ( !SourceString || (unsigned int)(a2 - 80) > 0x1F )
  {
    v10 = 87;
    goto LABEL_8;
  }
  RtlInitUnicodeString(&DestinationString, SourceString);
  if ( (unsigned int)RtlCreateVirtualAccountSid(&DestinationString, v7, 0, &Size) != -1073741789 )
  {
    v10 = 13;
    goto LABEL_8;
  }
  v8 = UbpmAlloc((unsigned int)Size);
  v4 = v8;
  if ( !v8 )
  {
    LastError = GetLastError();
LABEL_10:
    v10 = LastError;
    goto LABEL_8;
  }
  v9 = RtlCreateVirtualAccountSid(&DestinationString, v7, v8, &Size);
  if ( v9 < 0 )
  {
    LastError = RtlNtStatusToDosError(v9);
    goto LABEL_10;
  }
  *a3 = v4;
  v10 = 0;
  v4 = 0;
  if ( a4 )
    *a4 = Size;
LABEL_8:
  UBPM_MIDL_user_free(v4, a2, a3, a4);
  return v10;
}

```

## disassembly

```asm
0x18002b3a8  push    rbx
0x18002b3aa  push    rsi
0x18002b3ab  push    rdi
0x18002b3ac  push    r14
0x18002b3ae  sub     rsp, 38h
0x18002b3b2  xor     edi, edi
0x18002b3b4  xorps   xmm0, xmm0
0x18002b3b7  mov     dword ptr [rsp+58h+Size], edi
0x18002b3bb  mov     rsi, r9
0x18002b3be  mov     r14, r8
0x18002b3c1  mov     ebx, edx
0x18002b3c3  movups  xmmword ptr [rsp+58h+DestinationString.Length], xmm0
0x18002b3c8  test    rcx, rcx
0x18002b3cb  jz      loc_18002B47A
0x18002b3d1  lea     eax, [rdx-50h]
0x18002b3d4  cmp     eax, 1Fh
0x18002b3d7  ja      loc_18002B47A
0x18002b3dd  mov     rdx, rcx; SourceString
0x18002b3e0  lea     rcx, [rsp+58h+DestinationString]; DestinationString
0x18002b3e5  call    cs:__imp_RtlInitUnicodeString
0x18002b3ec  nop     dword ptr [rax+rax+00h]
0x18002b3f1  lea     r9, [rsp+58h+Size]
0x18002b3f6  xor     r8d, r8d
0x18002b3f9  mov     edx, ebx
0x18002b3fb  lea     rcx, [rsp+58h+DestinationString]
0x18002b400  call    cs:__imp_RtlCreateVirtualAccountSid
0x18002b407  nop     dword ptr [rax+rax+00h]
0x18002b40c  cmp     eax, 0C0000023h
0x18002b411  jnz     short loc_18002B481
0x18002b413  mov     ecx, dword ptr [rsp+58h+Size]; Size
0x18002b417  call    ?UbpmAlloc@@YAPEAXK@Z; UbpmAlloc(ulong)
0x18002b41c  mov     rdi, rax
0x18002b41f  test    rax, rax
0x18002b422  jz      short loc_18002B46A
0x18002b424  lea     r9, [rsp+58h+Size]
0x18002b429  mov     r8, rax
0x18002b42c  mov     edx, ebx
0x18002b42e  lea     rcx, [rsp+58h+DestinationString]
0x18002b433  call    cs:__imp_RtlCreateVirtualAccountSid
0x18002b43a  nop     dword ptr [rax+rax+00h]
0x18002b43f  test    eax, eax
0x18002b441  js      short loc_18002B488
0x18002b443  mov     [r14], rdi
0x18002b446  xor     ebx, ebx
0x18002b448  xor     edi, edi
0x18002b44a  test    rsi, rsi
0x18002b44d  jz      short loc_18002B455
0x18002b44f  mov     eax, dword ptr [rsp+58h+Size]
0x18002b453  mov     [rsi], eax
0x18002b455  mov     rcx, rdi
0x18002b458  call    UBPM_MIDL_user_free
0x18002b45d  mov     eax, ebx
0x18002b45f  add     rsp, 38h
0x18002b463  pop     r14
0x18002b465  pop     rdi
0x18002b466  pop     rsi
0x18002b467  pop     rbx
0x18002b468  retn
0x18002b46a  call    cs:__imp_GetLastError
0x18002b471  nop     dword ptr [rax+rax+00h]
0x18002b476  mov     ebx, eax
0x18002b478  jmp     short loc_18002B455
0x18002b47a  mov     ebx, 57h ; 'W'
0x18002b47f  jmp     short loc_18002B455
0x18002b481  mov     ebx, 0Dh
0x18002b486  jmp     short loc_18002B455
0x18002b488  mov     ecx, eax; Status
0x18002b48a  call    cs:__imp_RtlNtStatusToDosError
0x18002b491  nop     dword ptr [rax+rax+00h]
0x18002b496  jmp     short loc_18002B476
```
