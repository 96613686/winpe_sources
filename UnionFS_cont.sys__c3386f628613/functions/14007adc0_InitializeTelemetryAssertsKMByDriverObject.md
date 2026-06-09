# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x14007adc0`
- end: `0x14007aebf`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14000701c`

## callees

- `0x14007adc0`
- `0x14007aec8`

## import_xrefs

- `ntoskrnl!RtlFreeAnsiString` at `0x14007aea5`
- `ntoskrnl!RtlFreeAnsiString` at `0x14007aea5`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ae3f`
- `ntoskrnl!ExFreePoolWithTag` at `0x14007ae3f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007adf9`
- `ntoskrnl!RtlInitUnicodeString` at `0x14007adf9`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14007ae0c`
- `ntoskrnl!IoQueryFullDriverPath` at `0x14007ae0c`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14007ae2b`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x14007ae2b`
- `ntoskrnl!RtlInitAnsiString` at `0x14007ae81`
- `ntoskrnl!RtlInitAnsiString` at `0x14007ae81`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKMByDriverObject(__int64 a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  __int64 v4; // rcx
  bool v5; // zf
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  struct _STRING AnsiString; // [rsp+30h] [rbp-30h] BYREF
  struct _STRING v8; // [rsp+40h] [rbp-20h] BYREF
  struct _STRING v9; // [rsp+50h] [rbp-10h] BYREF

  AnsiString = 0;
  DestinationString = 0;
  if ( _InterlockedExchangeAdd(&g_AssertsOperational, 0) )
    return 0;
  RtlInitUnicodeString(&DestinationString, 0);
  result = IoQueryFullDriverPath(a1, &DestinationString);
  if ( (int)result >= 0 )
  {
    v3 = RtlUnicodeStringToAnsiString(&AnsiString, &DestinationString, 1u);
    ExFreePoolWithTag(DestinationString.Buffer, 0);
    if ( v3 >= 0 )
    {
      v4 = (unsigned int)AnsiString.Length - 1;
      if ( AnsiString.Length != 1 )
      {
        while ( AnsiString.Buffer[v4] != 92 )
        {
          v5 = (_DWORD)v4 == 1;
          v4 = (unsigned int)(v4 - 1);
          if ( v5 )
            goto LABEL_11;
        }
        if ( (_DWORD)v4 != AnsiString.Length )
        {
          v8 = 0;
          RtlInitAnsiString(&v8, &AnsiString.Buffer[(unsigned int)(v4 + 1)]);
          v9 = v8;
          v3 = InitializeTelemetryAssertsKMWorkerInternal(&v9);
        }
      }
LABEL_11:
      RtlFreeAnsiString(&AnsiString);
    }
    return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x14007adc0  mov     [rsp-8+arg_0], rbx
0x14007adc5  push    rbp
0x14007adc6  mov     rbp, rsp
0x14007adc9  sub     rsp, 60h
0x14007adcd  xorps   xmm0, xmm0
0x14007add0  xorps   xmm1, xmm1
0x14007add3  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x14007add7  mov     rbx, rcx
0x14007adda  xor     eax, eax
0x14007addc  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x14007ade0  lock xadd cs:g_AssertsOperational, eax
0x14007ade8  test    eax, eax
0x14007adea  jz      short loc_14007ADF3
0x14007adec  xor     eax, eax
0x14007adee  jmp     loc_14007AEB3
0x14007adf3  xor     edx, edx; SourceString
0x14007adf5  lea     rcx, [rbp+DestinationString]; DestinationString
0x14007adf9  call    cs:__imp_RtlInitUnicodeString
0x14007ae00  nop     dword ptr [rax+rax+00h]
0x14007ae05  lea     rdx, [rbp+DestinationString]
0x14007ae09  mov     rcx, rbx
0x14007ae0c  call    cs:__imp_IoQueryFullDriverPath
0x14007ae13  nop     dword ptr [rax+rax+00h]
0x14007ae18  test    eax, eax
0x14007ae1a  js      loc_14007AEB3
0x14007ae20  mov     r8b, 1; AllocateDestinationString
0x14007ae23  lea     rdx, [rbp+DestinationString]; SourceString
0x14007ae27  lea     rcx, [rbp+AnsiString]; DestinationString
0x14007ae2b  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14007ae32  nop     dword ptr [rax+rax+00h]
0x14007ae37  mov     rcx, [rbp+DestinationString.Buffer]; P
0x14007ae3b  xor     edx, edx; Tag
0x14007ae3d  mov     ebx, eax
0x14007ae3f  call    cs:__imp_ExFreePoolWithTag
0x14007ae46  nop     dword ptr [rax+rax+00h]
0x14007ae4b  test    ebx, ebx
0x14007ae4d  js      short loc_14007AEB1
0x14007ae4f  movzx   edx, [rbp+AnsiString.Length]
0x14007ae53  lea     ecx, [rdx-1]
0x14007ae56  test    ecx, ecx
0x14007ae58  jz      short loc_14007AEA1
0x14007ae5a  mov     r8, [rbp+AnsiString.Buffer]
0x14007ae5e  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x14007ae63  jz      short loc_14007AE6C
0x14007ae65  add     ecx, 0FFFFFFFFh
0x14007ae68  jnz     short loc_14007AE5E
0x14007ae6a  jmp     short loc_14007AEA1
0x14007ae6c  cmp     ecx, edx
0x14007ae6e  jz      short loc_14007AEA1
0x14007ae70  lea     edx, [rcx+1]
0x14007ae73  xorps   xmm0, xmm0
0x14007ae76  add     rdx, r8; SourceString
0x14007ae79  lea     rcx, [rbp+var_20]; DestinationString
0x14007ae7d  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14007ae81  call    cs:__imp_RtlInitAnsiString
0x14007ae88  nop     dword ptr [rax+rax+00h]
0x14007ae8d  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x14007ae91  lea     rcx, [rbp+var_10]
0x14007ae95  movdqa  [rbp+var_10], xmm0
0x14007ae9a  call    InitializeTelemetryAssertsKMWorkerInternal
0x14007ae9f  mov     ebx, eax
0x14007aea1  lea     rcx, [rbp+AnsiString]; AnsiString
0x14007aea5  call    cs:__imp_RtlFreeAnsiString
0x14007aeac  nop     dword ptr [rax+rax+00h]
0x14007aeb1  mov     eax, ebx
0x14007aeb3  mov     rbx, [rsp+60h+arg_0]
0x14007aeb8  add     rsp, 60h
0x14007aebc  pop     rbp
0x14007aebd  retn
```
