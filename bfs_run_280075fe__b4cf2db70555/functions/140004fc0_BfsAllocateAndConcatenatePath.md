# BfsAllocateAndConcatenatePath

- ea: `0x140004fc0`
- end: `0x140005132`
- name: `BfsAllocateAndConcatenatePath`
- size: `370`
- prototype: `__int64 __fastcall(PCUNICODE_STRING Source, PCUNICODE_STRING)`
- caller_count: `1`
- callee_count: `3`
- tags: ``

## callers

- `0x140009b9c`

## callees

- `0x140001008`
- `0x140004fc0`
- `0x140013730`

## import_xrefs

- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000505c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005097`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400050b0`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x14000505c`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x140005097`
- `ntoskrnl!RtlAppendUnicodeStringToString` at `0x1400050b0`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005003`
- `ntoskrnl!RtlInitUnicodeString` at `0x140005003`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400050ff`
- `ntoskrnl!RtlFreeUnicodeString` at `0x1400050ff`
- `ntoskrnl!ExAllocatePool2` at `0x140005033`
- `ntoskrnl!ExAllocatePool2` at `0x140005033`

## pseudocode

```c
__int64 __fastcall BfsAllocateAndConcatenatePath(
        PCUNICODE_STRING Source,
        PCUNICODE_STRING a2,
        struct _UNICODE_STRING *a3)
{
  __int64 v6; // rcx
  __int64 v7; // r8
  __int64 v8; // r9
  NTSTATUS v9; // ebx
  NTSTATUS appended; // eax
  int v12; // [rsp+20h] [rbp-39h]
  NTSTATUS v13; // [rsp+30h] [rbp-29h] BYREF
  struct _UNICODE_STRING Destination; // [rsp+38h] [rbp-21h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+48h] [rbp-11h] BYREF
  struct _EVENT_DATA_DESCRIPTOR v16; // [rsp+58h] [rbp-1h] BYREF
  NTSTATUS *v17; // [rsp+78h] [rbp+1Fh]
  __int64 v18; // [rsp+80h] [rbp+27h]

  Destination = 0;
  DestinationString = 0;
  RtlInitUnicodeString(&DestinationString, L"\\");
  Destination.MaximumLength = DestinationString.Length + a2->Length + Source->Length;
  Destination.Length = 0;
  Destination.Buffer = (PWSTR)ExAllocatePool2(256, Destination.MaximumLength, 1316185666);
  if ( Destination.Buffer )
  {
    if ( !Source->Length )
      goto LABEL_8;
    appended = RtlAppendUnicodeStringToString(&Destination, Source);
    v9 = appended;
    if ( appended < 0 )
    {
      v6 = (unsigned int)dword_140019000;
      if ( (unsigned int)dword_140019000 <= 3 )
        goto LABEL_12;
      v13 = appended;
      v17 = &v13;
      goto LABEL_11;
    }
    v9 = RtlAppendUnicodeStringToString(&Destination, &DestinationString);
    if ( v9 >= 0 )
    {
LABEL_8:
      v9 = RtlAppendUnicodeStringToString(&Destination, a2);
      if ( v9 >= 0 )
      {
        *a3 = Destination;
        return (unsigned int)v9;
      }
    }
  }
  else
  {
    v9 = -1073741801;
  }
  if ( (unsigned int)dword_140019000 <= 3 )
    goto LABEL_12;
  v17 = &v13;
  v13 = v9;
LABEL_11:
  v18 = 4;
  tlgWriteTransfer_EtwWriteTransfer(v6, (unsigned __int8 *)&byte_140016D91, v7, v8, v12, &v16);
LABEL_12:
  if ( Destination.Buffer )
    RtlFreeUnicodeString(&Destination);
  return (unsigned int)v9;
}

```

## disassembly

```asm
0x140004fc0  push    rbp
0x140004fc2  push    rbx
0x140004fc3  push    rsi
0x140004fc4  push    rdi
0x140004fc5  push    r14
0x140004fc7  lea     rbp, [rsp-37h]
0x140004fcc  sub     rsp, 90h
0x140004fd3  mov     rax, cs:__security_cookie
0x140004fda  xor     rax, rsp
0x140004fdd  mov     [rbp+57h+var_28], rax
0x140004fe1  mov     rdi, rdx
0x140004fe4  mov     rbx, rcx
0x140004fe7  xorps   xmm0, xmm0
0x140004fea  lea     rdx, asc_140016978; "\\"
0x140004ff1  xorps   xmm1, xmm1
0x140004ff4  lea     rcx, [rbp+57h+DestinationString]; DestinationString
0x140004ff8  movups  xmmword ptr [rbp+57h+Destination.Length], xmm0
0x140004ffc  mov     rsi, r8
0x140004fff  movups  xmmword ptr [rbp+57h+DestinationString.Length], xmm1
0x140005003  call    cs:__imp_RtlInitUnicodeString
0x14000500a  nop     dword ptr [rax+rax+00h]
0x14000500f  movzx   ecx, word ptr [rbx]
0x140005012  xor     r14d, r14d
0x140005015  add     cx, [rdi]
0x140005018  mov     r8d, 4E736642h
0x14000501e  add     cx, [rbp+57h+DestinationString.Length]
0x140005022  movzx   edx, cx
0x140005025  mov     ecx, 100h
0x14000502a  mov     [rbp+57h+Destination.MaximumLength], dx
0x14000502e  mov     [rbp+57h+Destination.Length], r14w
0x140005033  call    cs:__imp_ExAllocatePool2
0x14000503a  nop     dword ptr [rax+rax+00h]
0x14000503f  mov     [rbp+57h+Destination.Buffer], rax
0x140005043  test    rax, rax
0x140005046  jnz     short loc_14000504F
0x140005048  mov     ebx, 0C0000017h
0x14000504d  jmp     short loc_1400050C2
0x14000504f  cmp     [rbx], r14w
0x140005053  jbe     short loc_1400050A9
0x140005055  mov     rdx, rbx; Source
0x140005058  lea     rcx, [rbp+57h+Destination]; Destination
0x14000505c  call    cs:__imp_RtlAppendUnicodeStringToString
0x140005063  nop     dword ptr [rax+rax+00h]
0x140005068  mov     ebx, eax
0x14000506a  test    eax, eax
0x14000506c  jns     short loc_14000508F
0x14000506e  mov     ecx, cs:dword_140019000
0x140005074  cmp     ecx, 3
0x140005077  jbe     short loc_1400050F5
0x140005079  mov     [rbp+57h+var_80], eax
0x14000507c  lea     rax, [rbp+57h+var_80]
0x140005080  mov     [rbp+57h+var_38], rax
0x140005084  lea     rax, [rbp+57h+var_58]
0x140005088  mov     [rsp+0B0h+var_88], rax
0x14000508d  jmp     short loc_1400050E1
0x14000508f  lea     rdx, [rbp+57h+DestinationString]; Source
0x140005093  lea     rcx, [rbp+57h+Destination]; Destination
0x140005097  call    cs:__imp_RtlAppendUnicodeStringToString
0x14000509e  nop     dword ptr [rax+rax+00h]
0x1400050a3  mov     ebx, eax
0x1400050a5  test    eax, eax
0x1400050a7  js      short loc_1400050C2
0x1400050a9  mov     rdx, rdi; Source
0x1400050ac  lea     rcx, [rbp+57h+Destination]; Destination
0x1400050b0  call    cs:__imp_RtlAppendUnicodeStringToString
0x1400050b7  nop     dword ptr [rax+rax+00h]
0x1400050bc  mov     ebx, eax
0x1400050be  test    eax, eax
0x1400050c0  jns     short loc_14000510D
0x1400050c2  mov     eax, cs:dword_140019000
0x1400050c8  cmp     eax, 3
0x1400050cb  jbe     short loc_1400050F5
0x1400050cd  lea     rax, [rbp+57h+var_80]
0x1400050d1  mov     [rbp+57h+var_38], rax
0x1400050d5  lea     rax, [rbp+57h+var_58]
0x1400050d9  mov     [rsp+0B0h+var_88], rax; PEVENT_DATA_DESCRIPTOR
0x1400050de  mov     [rbp+57h+var_80], ebx
0x1400050e1  lea     rdx, byte_140016D91; int
0x1400050e8  mov     [rbp+57h+var_30], 4
0x1400050f0  call    _tlgWriteTransfer_EtwWriteTransfer
0x1400050f5  cmp     [rbp+57h+Destination.Buffer], r14
0x1400050f9  jz      short loc_140005115
0x1400050fb  lea     rcx, [rbp+57h+Destination]; UnicodeString
0x1400050ff  call    cs:__imp_RtlFreeUnicodeString
0x140005106  nop     dword ptr [rax+rax+00h]
0x14000510b  jmp     short loc_140005115
0x14000510d  movups  xmm0, xmmword ptr [rbp+57h+Destination.Length]
0x140005111  movdqu  xmmword ptr [rsi], xmm0
0x140005115  mov     eax, ebx
0x140005117  mov     rcx, [rbp+57h+var_28]
0x14000511b  xor     rcx, rsp; StackCookie
0x14000511e  call    __security_check_cookie
0x140005123  add     rsp, 90h
0x14000512a  pop     r14
0x14000512c  pop     rdi
0x14000512d  pop     rsi
0x14000512e  pop     rbx
0x14000512f  pop     rbp
0x140005130  retn
```
