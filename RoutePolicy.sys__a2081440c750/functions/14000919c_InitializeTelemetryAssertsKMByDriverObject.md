# InitializeTelemetryAssertsKMByDriverObject

- ea: `0x14000919c`
- end: `0x14000929b`
- name: `InitializeTelemetryAssertsKMByDriverObject`
- size: `255`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: ``

## callers

- `0x14001903c`

## callees

- `0x14000919c`
- `0x1400092a4`

## import_xrefs

- `ntoskrnl!IoQueryFullDriverPath` at `0x1400091e8`
- `ntoskrnl!IoQueryFullDriverPath` at `0x1400091e8`
- `ntoskrnl!RtlFreeAnsiString` at `0x140009281`
- `ntoskrnl!RtlFreeAnsiString` at `0x140009281`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140009207`
- `ntoskrnl!RtlUnicodeStringToAnsiString` at `0x140009207`
- `ntoskrnl!RtlInitAnsiString` at `0x14000925d`
- `ntoskrnl!RtlInitAnsiString` at `0x14000925d`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000921b`
- `ntoskrnl!ExFreePoolWithTag` at `0x14000921b`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400091d5`
- `ntoskrnl!RtlInitUnicodeString` at `0x1400091d5`

## pseudocode

```c
__int64 __fastcall InitializeTelemetryAssertsKMByDriverObject(__int64 a1)
{
  __int64 result; // rax
  NTSTATUS v3; // ebx
  __int64 v4; // rcx
  bool v5; // zf
  struct _UNICODE_STRING DestinationString; // [rsp+20h] [rbp-40h] BYREF
  _STRING AnsiString; // [rsp+30h] [rbp-30h] BYREF
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
0x14000919c  mov     [rsp-8+arg_0], rbx
0x1400091a1  push    rbp
0x1400091a2  mov     rbp, rsp
0x1400091a5  sub     rsp, 60h
0x1400091a9  xorps   xmm0, xmm0
0x1400091ac  xorps   xmm1, xmm1
0x1400091af  movups  xmmword ptr [rbp+AnsiString.Length], xmm0
0x1400091b3  mov     rbx, rcx
0x1400091b6  xor     eax, eax
0x1400091b8  movups  xmmword ptr [rbp+DestinationString.Length], xmm1
0x1400091bc  lock xadd cs:g_AssertsOperational, eax
0x1400091c4  test    eax, eax
0x1400091c6  jz      short loc_1400091CF
0x1400091c8  xor     eax, eax
0x1400091ca  jmp     loc_14000928F
0x1400091cf  xor     edx, edx; SourceString
0x1400091d1  lea     rcx, [rbp+DestinationString]; DestinationString
0x1400091d5  call    cs:__imp_RtlInitUnicodeString
0x1400091dc  nop     dword ptr [rax+rax+00h]
0x1400091e1  lea     rdx, [rbp+DestinationString]
0x1400091e5  mov     rcx, rbx
0x1400091e8  call    cs:__imp_IoQueryFullDriverPath
0x1400091ef  nop     dword ptr [rax+rax+00h]
0x1400091f4  test    eax, eax
0x1400091f6  js      loc_14000928F
0x1400091fc  mov     r8b, 1; AllocateDestinationString
0x1400091ff  lea     rdx, [rbp+DestinationString]; SourceString
0x140009203  lea     rcx, [rbp+AnsiString]; DestinationString
0x140009207  call    cs:__imp_RtlUnicodeStringToAnsiString
0x14000920e  nop     dword ptr [rax+rax+00h]
0x140009213  mov     rcx, [rbp+DestinationString.Buffer]; P
0x140009217  xor     edx, edx; Tag
0x140009219  mov     ebx, eax
0x14000921b  call    cs:__imp_ExFreePoolWithTag
0x140009222  nop     dword ptr [rax+rax+00h]
0x140009227  test    ebx, ebx
0x140009229  js      short loc_14000928D
0x14000922b  movzx   edx, [rbp+AnsiString.Length]
0x14000922f  lea     ecx, [rdx-1]
0x140009232  test    ecx, ecx
0x140009234  jz      short loc_14000927D
0x140009236  mov     r8, [rbp+AnsiString.Buffer]
0x14000923a  cmp     byte ptr [rcx+r8], 5Ch ; '\'
0x14000923f  jz      short loc_140009248
0x140009241  add     ecx, 0FFFFFFFFh
0x140009244  jnz     short loc_14000923A
0x140009246  jmp     short loc_14000927D
0x140009248  cmp     ecx, edx
0x14000924a  jz      short loc_14000927D
0x14000924c  lea     edx, [rcx+1]
0x14000924f  xorps   xmm0, xmm0
0x140009252  add     rdx, r8; SourceString
0x140009255  lea     rcx, [rbp+var_20]; DestinationString
0x140009259  movups  xmmword ptr [rbp+var_20.Length], xmm0
0x14000925d  call    cs:__imp_RtlInitAnsiString
0x140009264  nop     dword ptr [rax+rax+00h]
0x140009269  movaps  xmm0, xmmword ptr [rbp+var_20.Length]
0x14000926d  lea     rcx, [rbp+var_10]
0x140009271  movdqa  [rbp+var_10], xmm0
0x140009276  call    InitializeTelemetryAssertsKMWorkerInternal
0x14000927b  mov     ebx, eax
0x14000927d  lea     rcx, [rbp+AnsiString]; AnsiString
0x140009281  call    cs:__imp_RtlFreeAnsiString
0x140009288  nop     dword ptr [rax+rax+00h]
0x14000928d  mov     eax, ebx
0x14000928f  mov     rbx, [rsp+60h+arg_0]
0x140009294  add     rsp, 60h
0x140009298  pop     rbp
0x140009299  retn
```
