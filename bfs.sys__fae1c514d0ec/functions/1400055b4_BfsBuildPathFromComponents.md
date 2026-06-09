# BfsBuildPathFromComponents

- ea: `0x1400055b4`
- end: `0x140005762`
- name: `BfsBuildPathFromComponents`
- size: `430`
- prototype: `__int64 __fastcall(__int64 **, const UNICODE_STRING *, const UNICODE_STRING *, struct _UNICODE_STRING *)`
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x140006330`

## callees

- `0x140001008`
- `0x1400055b4`
- `0x140006f5c`
- `0x140013860`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000566a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005684`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400056a5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400056c5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400056de`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000566a`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005684`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400056a5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400056c5`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400056de`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005600`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005600`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140005727`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140005727`
- `ntoskrnl!ExAllocatePool2` at `0x14000562a`
- `ntoskrnl!ExAllocatePool2` at `0x14000562a`

## pseudocode

```c
__int64 __fastcall BfsBuildPathFromComponents(
        __int64 **a1,
        const UNICODE_STRING *a2,
        const UNICODE_STRING *a3,
        struct _UNICODE_STRING *a4)
{
  USHORT PathLength; // bx
  WCHAR *Pool2; // rax
  __int64 *v11; // rdi
  int v12; // ecx
  NTSTATUS appended; // ebx
  int v14; // r8d
  int v15; // r9d
  int v16; // [rsp+20h] [rbp-59h]
  NTSTATUS v17; // [rsp+30h] [rbp-49h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+38h] [rbp-41h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-31h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v20; // [rsp+58h] [rbp-21h] BYREF
  NTSTATUS *v21; // [rsp+78h] [rbp-1h]
  __int64 v22; // [rsp+80h] [rbp+7h]

  Destination = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\");
  PathLength = BfsGetPathLength(a1, a2, a3);
  Pool2 = (WCHAR *)ExAllocatePool2(256, PathLength, 1181967938);
  if ( !Pool2 )
    return 3221225495LL;
  v11 = *a1;
  *(_QWORD *)&Destination.Length = 0;
  Destination.MaximumLength = PathLength;
  Destination.Buffer = Pool2;
  while ( v11 != (__int64 *)a1 )
  {
    if ( *((_WORD *)v11 + 12) )
    {
      appended = RtlAppendUnicodeStringToString(&Destination, (PCUNICODE_STRING)(v11 + 3));
      if ( appended < 0 )
        goto LABEL_13;
      appended = RtlAppendUnicodeStringToString(&Destination, &DestinationString);
      if ( appended < 0 )
        goto LABEL_13;
    }
    v11 = (__int64 *)*v11;
  }
  appended = RtlAppendUnicodeStringToString(&Destination, a2);
  if ( appended >= 0 )
  {
    if ( !a3->Length
      || (appended = RtlAppendUnicodeStringToString(&Destination, &DestinationString), appended >= 0)
      && (appended = RtlAppendUnicodeStringToString(&Destination, a3), appended >= 0) )
    {
      *a4 = Destination;
      return (unsigned int)appended;
    }
  }
LABEL_13:
  if ( (unsigned int)dword_140019000 > 3 )
  {
    v21 = &v17;
    v17 = appended;
    v22 = 4;
    tlgWriteTransfer_EtwWriteTransfer(v12, (int)&byte_140016D91, v14, v15, v16, &v20);
  }
  RtlFreeUnicodeString(&Destination);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x1400055b4  push    rbp
0x1400055b6  push    rbx
0x1400055b7  push    rsi
0x1400055b8  push    rdi
0x1400055b9  push    r12
0x1400055bb  push    r13
0x1400055bd  push    r14
0x1400055bf  push    r15
0x1400055c1  lea     rbp, [rsp-1Fh]
0x1400055c6  sub     rsp, 98h
0x1400055cd  mov     rax, cs:__security_cookie
0x1400055d4  xor     rax, rsp
0x1400055d7  mov     [rbp+57h+var_48], rax
0x1400055db  mov     r15, rdx
0x1400055de  mov     rsi, rcx
0x1400055e1  xorps   xmm0, xmm0
0x1400055e4  lea     rdx, asc_140016968; "\\"
0x1400055eb  xorps   xmm1, xmm1
0x1400055ee  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x1400055f2  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x1400055f6  mov     r12, r9
0x1400055f9  mov     r14, r8
0x1400055fc  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140005600  call    cs:__imp_RtlInitUnicodeString
0x140005607  nop     dword ptr [rax+rax+00h]
0x14000560c  mov     r8, r14
0x14000560f  mov     rdx, r15
0x140005612  mov     rcx, rsi
0x140005615  call    BfsGetPathLength
0x14000561a  movzx   ebx, ax
0x14000561d  mov     ecx, 100h
0x140005622  mov     edx, ebx
0x140005624  mov     r8d, 46736642h
0x14000562a  call    cs:__imp_ExAllocatePool2
0x140005631  nop     dword ptr [rax+rax+00h]
0x140005636  xor     r13d, r13d
0x140005639  test    rax, rax
0x14000563c  jnz     short loc_140005648
0x14000563e  mov     eax, 0C0000017h
0x140005643  jmp     loc_140005741
0x140005648  mov     rdi, [rsi]
0x14000564b  xorps   xmm0, xmm0
0x14000564e  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x140005652  mov     [rbp+57h+Destination.MaximumLength], bx
0x140005656  mov     [rbp+57h+Destination.Buffer], rax
0x14000565a  jmp     short loc_140005699
0x14000565c  lea     rdx, [rdi+18h]; Source
0x140005660  cmp     [rdx], r13w
0x140005664  jbe     short loc_140005696
0x140005666  lea     rcx, [rbp+57h+Destination]; Destination
0x14000566a  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005671  nop     dword ptr [rax+rax+00h]
0x140005676  mov     ebx, eax
0x140005678  test    eax, eax
0x14000567a  js      short loc_1400056F0
0x14000567c  lea     rdx, [rbp+57h+DestinationString]; Source
0x140005680  lea     rcx, [rbp+57h+Destination]; Destination
0x140005684  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000568b  nop     dword ptr [rax+rax+00h]
0x140005690  mov     ebx, eax
0x140005692  test    eax, eax
0x140005694  js      short loc_1400056F0
0x140005696  mov     rdi, [rdi]
0x140005699  cmp     rdi, rsi
0x14000569c  jnz     short loc_14000565C
0x14000569e  mov     rdx, r15; Source
0x1400056a1  lea     rcx, [rbp+57h+Destination]; Destination
0x1400056a5  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400056ac  nop     dword ptr [rax+rax+00h]
0x1400056b1  mov     ebx, eax
0x1400056b3  test    eax, eax
0x1400056b5  js      short loc_1400056F0
0x1400056b7  cmp     [r14], r13w
0x1400056bb  jbe     short loc_140005735
0x1400056bd  lea     rdx, [rbp+57h+DestinationString]; Source
0x1400056c1  lea     rcx, [rbp+57h+Destination]; Destination
0x1400056c5  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400056cc  nop     dword ptr [rax+rax+00h]
0x1400056d1  mov     ebx, eax
0x1400056d3  test    eax, eax
0x1400056d5  js      short loc_1400056F0
0x1400056d7  mov     rdx, r14; Source
0x1400056da  lea     rcx, [rbp+57h+Destination]; Destination
0x1400056de  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400056e5  nop     dword ptr [rax+rax+00h]
0x1400056ea  mov     ebx, eax
0x1400056ec  test    eax, eax
0x1400056ee  jns     short loc_140005735
0x1400056f0  mov     eax, cs:dword_140019000
0x1400056f6  cmp     eax, 3
0x1400056f9  jbe     short loc_140005723
0x1400056fb  lea     rax, [rbp+57h+var_A0]
0x1400056ff  mov     [rbp+57h+var_58], rax
0x140005703  lea     rax, [rbp+57h+var_78]
0x140005707  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x14000570c  lea     rdx, byte_140016D91; int
0x140005713  mov     [rbp+57h+var_A0], ebx
0x140005716  mov     [rbp+57h+var_50], 4
0x14000571e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005723  lea     rcx, [rbp+57h+Destination]; UnicodeString
0x140005727  call    cs:__imp_RtlFreeUnicodeString
0x14000572e  nop     dword ptr [rax+rax+00h]
0x140005733  jmp     short loc_14000573F
0x140005735  movups  xmm0, xmmword ptr [rbp+57h+Destination.Length]
0x140005739  movdqu  xmmword ptr [r12], xmm0
0x14000573f  mov     eax, ebx
0x140005741  mov     rcx, [rbp+57h+var_48]
0x140005745  xor     rcx, rsp; StackCookie
0x140005748  call    __security_check_cookie
0x14000574d  add     rsp, 98h
0x140005754  pop     r15
0x140005756  pop     r14
0x140005758  pop     r13
0x14000575a  pop     r12
0x14000575c  pop     rdi
0x14000575d  pop     rsi
0x14000575e  pop     rbx
0x14000575f  pop     rbp
0x140005760  retn
```
