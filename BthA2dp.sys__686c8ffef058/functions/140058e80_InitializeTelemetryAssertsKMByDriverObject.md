# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x140058e80`
- end: `0x140058f7c`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `252`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14003c5e0`

## callees

- `0x140058e80`
- `0x140058f84`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140058eff`
- `ntoskrnl!ExFreePoolWithTag` at `0x140058eff`
- `ntoskrnl!RtlInitUnicodeString` at `0x140058eb9`
- `ntoskrnl!RtlInitUnicodeString` at `0x140058eb9`
- `ntoskrnl!RtlFreeAnsiString` at `0x140058f62`
- `ntoskrnl!RtlFreeAnsiString` at `0x140058f62`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140058eeb`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140058eeb`
- `ntoskrnl!RtlInitAnsiString` at `0x140058f3e`
- `ntoskrnl!RtlInitAnsiString` at `0x140058f3e`
- `ntoskrnl!IoQueryFullDriverPath` at `0x140058ecc`
- `ntoskrnl!IoQueryFullDriverPath` at `0x140058ecc`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKMByDriverObject(__int64 a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  __int64 i; // rcx
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _STRING AnsiString; // [rsp+30h] [rbp-30h] BYREF
  struct _STRING v7; // [rsp+40h] [rbp-20h] BYREF
  struct _STRING v8; // [rsp+50h] [rbp-10h] BYREF

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
      for ( i = (unsigned int)AnsiString.Length - 1; (_DWORD)i; i = (unsigned int)(i - 1) )
      {
        if ( AnsiString.Buffer[i] == 92 )
        {
          if ( (_DWORD)i != AnsiString.Length )
          {
            v7 = 0;
            RtlInitAnsiString(&v7, &AnsiString.Buffer[(unsigned int)(i + 1)]);
            v8 = v7;
            v3 = InitializeTelemetryAssertsKMWorkerInternal(&v8);
          }
          break;
        }
      }
      RtlFreeAnsiString(&AnsiString);
    }
    return (unsigned int)v3;
  }
  return result;
}

```

## disassembly

```asm
0x140058e80  mov     [rsp-8+arg_0], rbx
0x140058e85  push    rbp
0x140058e86  mov     rbp, rsp
0x140058e89  sub     rsp, 60h
0x140058e8d  xorps   xmm0, xmm0
0x140058e90  xorps   xmm1, xmm1
0x140058e93  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x140058e97  mov     rbx, rcx
0x140058e9a  xor     eax, eax
0x140058e9c  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x140058ea0  lock xadd cs:g_AssertsOperational, eax
0x140058ea8  test    eax, eax
0x140058eaa  jz      short loc_140058EB3
0x140058eac  xor     eax, eax
0x140058eae  jmp     loc_140058F70
0x140058eb3  xor     edx, edx; SourceString
0x140058eb5  lea     rcx, [rbp+DestinationString]; DestinationString
0x140058eb9  call    cs:__imp_RtlInitUnicodeString
0x140058ec0  nop     dword ptr [rax+rax+00h]
0x140058ec5  lea     rdx, [rbp+DestinationString]
0x140058ec9  mov     rcx, rbx
0x140058ecc  call    cs:__imp_IoQueryFullDriverPath
0x140058ed3  nop     dword ptr [rax+rax+00h]
0x140058ed8  test    eax, eax
0x140058eda  js      loc_140058F70
0x140058ee0  mov     r8b, 1; AllocateDestinationString
0x140058ee3  lea     rdx, [rbp+DestinationString]; SourceString
0x140058ee7  lea     rcx, [rbp+AnsiString]; DestinationString
0x140058eeb  call    cs:__imp_RtlUnicodeStringToAnsiString
0x140058ef2  nop     dword ptr [rax+rax+00h]
0x140058ef7  mov     rcx, [rbp+DestinationString.Buffer]; P
0x140058efb  xor     edx, edx; Tag
0x140058efd  mov     ebx, eax
0x140058eff  call    cs:__imp_ExFreePoolWithTag
0x140058f06  nop     dword ptr [rax+rax+00h]
0x140058f0b  test    ebx, ebx
0x140058f0d  js      short loc_140058F6E
0x140058f0f  movzx   edx, [rbp+AnsiString.Length]
0x140058f13  mov     r8, [rbp+AnsiString.Buffer]
0x140058f17  lea     ecx, [rdx-1]
0x140058f1a  test    ecx, ecx
0x140058f1c  jz      short loc_140058F5E
0x140058f1e  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x140058f23  jz      short loc_140058F29
0x140058f25  dec     ecx
0x140058f27  jmp     short loc_140058F1A
0x140058f29  cmp     ecx, edx
0x140058f2b  jz      short loc_140058F5E
0x140058f2d  lea     edx, [rcx+1]
0x140058f30  xorps   xmm0, xmm0
0x140058f33  add     rdx, r8; SourceString
0x140058f36  lea     rcx, [rbp+var_20]; DestinationString
0x140058f3a  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x140058f3e  call    cs:__imp_RtlInitAnsiString
0x140058f45  nop     dword ptr [rax+rax+00h]
0x140058f4a  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x140058f4e  lea     rcx, [rbp+var_10]
0x140058f52  movdqa  [rbp+var_10], xmm0
0x140058f57  call    InitializeTelemetryAssertsKMWorkerInternal
0x140058f5c  mov     ebx, eax
0x140058f5e  lea     rcx, [rbp+AnsiString]; AnsiString
0x140058f62  call    cs:__imp_RtlFreeAnsiString
0x140058f69  nop     dword ptr [rax+rax+00h]
0x140058f6e  mov     eax, ebx
0x140058f70  mov     rbx, [rsp+60h+arg_0]
0x140058f75  add     rsp, 60h
0x140058f79  pop     rbp
0x140058f7a  retn
```
