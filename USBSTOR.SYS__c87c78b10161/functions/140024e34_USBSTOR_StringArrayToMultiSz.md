# USBSTOR_StringArrayToMultiSz

- ea: `0x140024e34`
- end: `0x140024fd2`
- name: `USBSTOR_StringArrayToMultiSz`
- size: `414`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `2`
- callee_count: `3`
- tags: ``

## callers

- `0x14001f1c4`
- `0x140023ab8`

## callees

- `0x140010594`
- `0x140010664`
- `0x140024e34`

## import_xrefs

- `ntoskrnl!RtlxAnsiStringToUnicodeSize` at `0x140024ece`
- `ntoskrnl!RtlxAnsiStringToUnicodeSize` at `0x140024ece`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024e9a`
- `ntoskrnl!RtlInitUnicodeString` at `0x140024e9a`
- `ntoskrnl!ExAllocatePool2` at `0x140024f07`
- `ntoskrnl!ExAllocatePool2` at `0x140024f07`
- `ntoskrnl!RtlInitAnsiString` at `0x140024ebb`
- `ntoskrnl!RtlInitAnsiString` at `0x140024f44`
- `ntoskrnl!RtlInitAnsiString` at `0x140024ebb`
- `ntoskrnl!RtlInitAnsiString` at `0x140024f44`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140024f5b`
- `ntoskrnl!RtlAnsiStringToUnicodeString` at `0x140024f5b`

## pseudocode

```c
__int64 __fastcall USBSTOR_StringArrayToMultiSz(PUNICODE_STRING DestinationString, _QWORD *a2)
{
  unsigned __int8 v4; // r14
  USHORT Length; // bx
  USHORT v6; // ax
  WCHAR *Pool2; // rax
  struct _UNICODE_STRING v9; // xmm0
  unsigned __int8 v10; // di
  NTSTATUS v11; // ebx
  struct _UNICODE_STRING v12; // [rsp+30h] [rbp-28h] BYREF
  struct _STRING DestinationStringa; // [rsp+40h] [rbp-18h] BYREF

  DestinationStringa = 0;
  v12 = 0;
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_qq(
      WPP_GLOBAL_Control->AttachedDevice,
      130,
      WPP_354602438fa331ce245c005e63ec86c9_Traceguids,
      DestinationString,
      a2);
  }
  RtlInitUnicodeString(DestinationString, 0);
  v4 = 0;
  if ( *a2 )
  {
    do
    {
      RtlInitAnsiString(&DestinationStringa, (PCSZ)a2[v4]);
      Length = DestinationString->Length;
      ++v4;
      DestinationString->Length = Length + RtlxAnsiStringToUnicodeSize(&DestinationStringa);
    }
    while ( a2[v4] );
  }
  v6 = DestinationString->Length + 2;
  DestinationString->MaximumLength = v6;
  Pool2 = (WCHAR *)ExAllocatePool2(256, v6, 1396788565);
  DestinationString->Buffer = Pool2;
  if ( !Pool2 )
    return 3221225626LL;
  v9 = *DestinationString;
  v10 = 0;
  v11 = 0;
  v12 = v9;
  if ( *a2 )
  {
    do
    {
      RtlInitAnsiString(&DestinationStringa, (PCSZ)a2[v10]);
      v11 = RtlAnsiStringToUnicodeString(&v12, &DestinationStringa, 0);
      if ( v11 < 0 )
        break;
      ++v10;
      v12.MaximumLength += -2 - v12.Length;
      v12.Buffer = (PWSTR)((char *)v12.Buffer + v12.Length + 2);
    }
    while ( a2[v10] );
  }
  if ( WPP_GLOBAL_Control != (PDEVICE_OBJECT)&WPP_GLOBAL_Control
    && (HIDWORD(WPP_GLOBAL_Control->Timer) & 1) != 0
    && BYTE1(WPP_GLOBAL_Control->Timer) >= 4u )
  {
    WPP_SF_(
      (__int64)WPP_GLOBAL_Control->AttachedDevice,
      0x83u,
      (__int64)WPP_354602438fa331ce245c005e63ec86c9_Traceguids);
  }
  return (unsigned int)v11;
}

```

## disassembly

```asm
0x140024e34  push    rbp
0x140024e36  push    rbx
0x140024e37  push    rsi
0x140024e38  push    rdi
0x140024e39  push    r13
0x140024e3b  push    r14
0x140024e3d  mov     rbp, rsp
0x140024e40  sub     rsp, 58h
0x140024e44  xorps   xmm0, xmm0
0x140024e47  xorps   xmm1, xmm1
0x140024e4a  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x140024e4e  mov     rsi, rdx
0x140024e51  mov     rdi, rcx
0x140024e54  movups  xmmword ptr [rbp+var_28.Length], xmm1
0x140024e58  mov     rcx, cs:WPP_GLOBAL_Control
0x140024e5f  lea     r13, WPP_GLOBAL_Control
0x140024e66  cmp     rcx, r13
0x140024e69  jz      short loc_140024E95
0x140024e6b  mov     eax, [rcx+2Ch]
0x140024e6e  test    al, 1
0x140024e70  jz      short loc_140024E95
0x140024e72  cmp     byte ptr [rcx+29h], 4
0x140024e76  jb      short loc_140024E95
0x140024e78  mov     rcx, [rcx+18h]
0x140024e7c  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140024e83  mov     edx, 82h
0x140024e88  mov     [rsp+58h+var_38], rsi
0x140024e8d  mov     r9, rdi
0x140024e90  call    WPP_SF_qq
0x140024e95  xor     edx, edx; SourceString
0x140024e97  mov     rcx, rdi; DestinationString
0x140024e9a  call    cs:__imp_RtlInitUnicodeString
0x140024ea1  nop     dword ptr [rax+rax+00h]
0x140024ea6  xor     r14b, r14b
0x140024ea9  cmp     qword ptr [rsi], 0
0x140024ead  jz      short loc_140024EEE
0x140024eaf  movzx   edx, r14b
0x140024eb3  lea     rcx, [rbp+DestinationString]; DestinationString
0x140024eb7  mov     rdx, [rsi+rdx*8]; SourceString
0x140024ebb  call    cs:__imp_RtlInitAnsiString
0x140024ec2  nop     dword ptr [rax+rax+00h]
0x140024ec7  movzx   ebx, word ptr [rdi]
0x140024eca  lea     rcx, [rbp+DestinationString]; AnsiString
0x140024ece  call    cs:__imp_RtlxAnsiStringToUnicodeSize
0x140024ed5  nop     dword ptr [rax+rax+00h]
0x140024eda  add     ax, bx
0x140024edd  inc     r14b
0x140024ee0  mov     [rdi], ax
0x140024ee3  movzx   eax, r14b
0x140024ee7  cmp     qword ptr [rsi+rax*8], 0
0x140024eec  jnz     short loc_140024EAF
0x140024eee  movzx   eax, word ptr [rdi]
0x140024ef1  mov     ecx, 100h
0x140024ef6  add     ax, 2
0x140024efa  mov     r8d, 53414D55h
0x140024f00  movzx   edx, ax
0x140024f03  mov     [rdi+2], dx
0x140024f07  call    cs:__imp_ExAllocatePool2
0x140024f0e  nop     dword ptr [rax+rax+00h]
0x140024f13  mov     [rdi+8], rax
0x140024f17  test    rax, rax
0x140024f1a  jnz     short loc_140024F26
0x140024f1c  mov     eax, 0C000009Ah
0x140024f21  jmp     loc_140024FC4
0x140024f26  movups  xmm0, xmmword ptr [rdi]
0x140024f29  xor     dil, dil
0x140024f2c  xor     ebx, ebx
0x140024f2e  movdqu  xmmword ptr [rbp+var_28.Length], xmm0
0x140024f33  cmp     [rsi], rbx
0x140024f36  jz      short loc_140024F94
0x140024f38  movzx   edx, dil
0x140024f3c  lea     rcx, [rbp+DestinationString]; DestinationString
0x140024f40  mov     rdx, [rsi+rdx*8]; SourceString
0x140024f44  call    cs:__imp_RtlInitAnsiString
0x140024f4b  nop     dword ptr [rax+rax+00h]
0x140024f50  xor     r8d, r8d; AllocateDestinationString
0x140024f53  lea     rdx, [rbp+DestinationString]; SourceString
0x140024f57  lea     rcx, [rbp+var_28]; DestinationString
0x140024f5b  call    cs:__imp_RtlAnsiStringToUnicodeString
0x140024f62  nop     dword ptr [rax+rax+00h]
0x140024f67  mov     ebx, eax
0x140024f69  test    eax, eax
0x140024f6b  js      short loc_140024F94
0x140024f6d  movzx   edx, [rbp+var_28.Length]
0x140024f71  mov     ecx, 0FFFEh
0x140024f76  sub     cx, [rbp+var_28.Length]
0x140024f7a  inc     dil
0x140024f7d  add     [rbp+var_28.MaximumLength], cx
0x140024f81  add     rdx, 2
0x140024f85  add     [rbp+var_28.Buffer], rdx
0x140024f89  movzx   ecx, dil
0x140024f8d  cmp     qword ptr [rsi+rcx*8], 0
0x140024f92  jnz     short loc_140024F38
0x140024f94  mov     rcx, cs:WPP_GLOBAL_Control
0x140024f9b  cmp     rcx, r13
0x140024f9e  jz      short loc_140024FC2
0x140024fa0  mov     eax, [rcx+2Ch]
0x140024fa3  test    al, 1
0x140024fa5  jz      short loc_140024FC2
0x140024fa7  cmp     byte ptr [rcx+29h], 4
0x140024fab  jb      short loc_140024FC2
0x140024fad  mov     rcx, [rcx+18h]
0x140024fb1  lea     r8, WPP_354602438fa331ce245c005e63ec86c9_Traceguids
0x140024fb8  mov     edx, 83h
0x140024fbd  call    WPP_SF_
0x140024fc2  mov     eax, ebx
0x140024fc4  add     rsp, 58h
0x140024fc8  pop     r14
0x140024fca  pop     r13
0x140024fcc  pop     rdi
0x140024fcd  pop     rsi
0x140024fce  pop     rbx
0x140024fcf  pop     rbp
0x140024fd0  retn
```
