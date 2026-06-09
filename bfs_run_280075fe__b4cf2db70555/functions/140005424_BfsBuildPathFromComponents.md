# BfsBuildPathFromComponents

- ea: `0x140005424`
- end: `0x1400055d2`
- name: `BfsBuildPathFromComponents`
- size: `430`
- prototype: ``
- caller_count: `1`
- callee_count: `4`
- tags: `broker_com_uri`

## callers

- `0x1400061a0`

## callees

- `0x140001008`
- `0x140005424`
- `0x140006dcc`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400054da`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400054f4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005515`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005535`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000554e`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400054da`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400054f4`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005515`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005535`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000554e`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005470`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005470`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140005597`
- `ntoskrnl!RtlFreeUnicodeString` at `0x140005597`
- `ntoskrnl!ExAllocatePool2` at `0x14000549a`
- `ntoskrnl!ExAllocatePool2` at `0x14000549a`

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
  __int64 v12; // rcx
  NTSTATUS appended; // ebx
  __int64 v14; // r8
  __int64 v15; // r9
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
    tlgWriteTransfer_EtwWriteTransfer(v12, (unsigned __int8 *)&byte_140016D91, v14, v15, v16, &v20);
  }
  RtlFreeUnicodeString(&Destination);
  return (unsigned int)appended;
}

```

## disassembly

```asm
0x140005424  push    rbp
0x140005426  push    rbx
0x140005427  push    rsi
0x140005428  push    rdi
0x140005429  push    r12
0x14000542b  push    r13
0x14000542d  push    r14
0x14000542f  push    r15
0x140005431  lea     rbp, [rsp-1Fh]
0x140005436  sub     rsp, 98h
0x14000543d  mov     rax, cs:__security_cookie
0x140005444  xor     rax, rsp
0x140005447  mov     [rbp+57h+var_48], rax
0x14000544b  mov     r15, rdx
0x14000544e  mov     rsi, rcx
0x140005451  xorps   xmm0, xmm0
0x140005454  lea     rdx, asc_140016978; "\\"
0x14000545b  xorps   xmm1, xmm1
0x14000545e  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140005462  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x140005466  mov     r12, r9
0x140005469  mov     r14, r8
0x14000546c  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140005470  call    cs:__imp_RtlInitUnicodeString
0x140005477  nop     dword ptr [rax+rax+00h]
0x14000547c  mov     r8, r14
0x14000547f  mov     rdx, r15
0x140005482  mov     rcx, rsi
0x140005485  call    BfsGetPathLength
0x14000548a  movzx   ebx, ax
0x14000548d  mov     ecx, 100h
0x140005492  mov     edx, ebx
0x140005494  mov     r8d, 46736642h
0x14000549a  call    cs:__imp_ExAllocatePool2
0x1400054a1  nop     dword ptr [rax+rax+00h]
0x1400054a6  xor     r13d, r13d
0x1400054a9  test    rax, rax
0x1400054ac  jnz     short loc_1400054B8
0x1400054ae  mov     eax, 0C0000017h
0x1400054b3  jmp     loc_1400055B1
0x1400054b8  mov     rdi, [rsi]
0x1400054bb  xorps   xmm0, xmm0
0x1400054be  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x1400054c2  mov     [rbp+57h+Destination.MaximumLength], bx
0x1400054c6  mov     [rbp+57h+Destination.Buffer], rax
0x1400054ca  jmp     short loc_140005509
0x1400054cc  lea     rdx, [rdi+18h]; Source
0x1400054d0  cmp     [rdx], r13w
0x1400054d4  jbe     short loc_140005506
0x1400054d6  lea     rcx, [rbp+57h+Destination]; Destination
0x1400054da  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400054e1  nop     dword ptr [rax+rax+00h]
0x1400054e6  mov     ebx, eax
0x1400054e8  test    eax, eax
0x1400054ea  js      short loc_140005560
0x1400054ec  lea     rdx, [rbp+57h+DestinationString]; Source
0x1400054f0  lea     rcx, [rbp+57h+Destination]; Destination
0x1400054f4  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400054fb  nop     dword ptr [rax+rax+00h]
0x140005500  mov     ebx, eax
0x140005502  test    eax, eax
0x140005504  js      short loc_140005560
0x140005506  mov     rdi, [rdi]
0x140005509  cmp     rdi, rsi
0x14000550c  jnz     short loc_1400054CC
0x14000550e  mov     rdx, r15; Source
0x140005511  lea     rcx, [rbp+57h+Destination]; Destination
0x140005515  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000551c  nop     dword ptr [rax+rax+00h]
0x140005521  mov     ebx, eax
0x140005523  test    eax, eax
0x140005525  js      short loc_140005560
0x140005527  cmp     [r14], r13w
0x14000552b  jbe     short loc_1400055A5
0x14000552d  lea     rdx, [rbp+57h+DestinationString]; Source
0x140005531  lea     rcx, [rbp+57h+Destination]; Destination
0x140005535  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000553c  nop     dword ptr [rax+rax+00h]
0x140005541  mov     ebx, eax
0x140005543  test    eax, eax
0x140005545  js      short loc_140005560
0x140005547  mov     rdx, r14; Source
0x14000554a  lea     rcx, [rbp+57h+Destination]; Destination
0x14000554e  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005555  nop     dword ptr [rax+rax+00h]
0x14000555a  mov     ebx, eax
0x14000555c  test    eax, eax
0x14000555e  jns     short loc_1400055A5
0x140005560  mov     eax, cs:dword_140019000
0x140005566  cmp     eax, 3
0x140005569  jbe     short loc_140005593
0x14000556b  lea     rax, [rbp+57h+var_A0]
0x14000556f  mov     [rbp+57h+var_58], rax
0x140005573  lea     rax, [rbp+57h+var_78]
0x140005577  mov     [rsp+0D0h+var_A8], rax; PEVENT_DATA_DESCRIPTOR
0x14000557c  lea     rdx, byte_140016D91; int
0x140005583  mov     [rbp+57h+var_A0], ebx
0x140005586  mov     [rbp+57h+var_50], 4
0x14000558e  call    _tlgWriteTransfer_EtwWriteTransfer
0x140005593  lea     rcx, [rbp+57h+Destination]; UnicodeString
0x140005597  call    cs:__imp_RtlFreeUnicodeString
0x14000559e  nop     dword ptr [rax+rax+00h]
0x1400055a3  jmp     short loc_1400055AF
0x1400055a5  movups  xmm0, xmmword ptr [rbp+57h+Destination.Length]
0x1400055a9  movdqu  xmmword ptr [r12], xmm0
0x1400055af  mov     eax, ebx
0x1400055b1  mov     rcx, [rbp+57h+var_48]
0x1400055b5  xor     rcx, rsp; StackCookie
0x1400055b8  call    __security_check_cookie
0x1400055bd  add     rsp, 98h
0x1400055c4  pop     r15
0x1400055c6  pop     r14
0x1400055c8  pop     r13
0x1400055ca  pop     r12
0x1400055cc  pop     rdi
0x1400055cd  pop     rsi
0x1400055ce  pop     rbx
0x1400055cf  pop     rbp
0x1400055d0  retn
```
