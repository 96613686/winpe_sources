# BthEnumChildCompare

- ea: `0x14001e034`
- end: `0x14001e15a`
- name: `BthEnumChildCompare`
- size: `294`
- prototype: ``
- caller_count: `3`
- callee_count: `1`
- tags: `broker_com_uri`

## callers

- `0x140002b64`
- `0x14001e1e0`
- `0x14001ec38`

## callees

- `0x14001e034`

## import_xrefs

- `ntoskrnl!RtlCompareUnicodeString` at `0x14001e09f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001e0e6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001e13d`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001e09f`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001e0e6`
- `ntoskrnl!RtlCompareUnicodeString` at `0x14001e13d`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e074`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e088`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e0bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e0cf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e10f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e126`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e074`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e088`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e0bb`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e0cf`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e10f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14001e126`

## pseudocode

```c
int __fastcall BthEnumChildCompare(__int64 a1, __int64 a2)
{
  int v2; // eax
  int result; // eax
  UNICODE_STRING String2; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING DestinationString; // [rsp+30h] [rbp-10h] BYREF

  v2 = *(_DWORD *)(a1 + 1040);
  DestinationString = 0;
  String2 = 0;
  result = v2 - *(_DWORD *)(a2 + 960);
  if ( !result )
  {
    RtlInitUnicodeString(&DestinationString, *(PCWSTR *)(a1 + 56));
    RtlInitUnicodeString(&String2, *(PCWSTR *)(a2 - 24));
    result = RtlCompareUnicodeString(&DestinationString, &String2, 0);
    if ( !result )
    {
      RtlInitUnicodeString(&DestinationString, (PCWSTR)(a1 + 24));
      RtlInitUnicodeString(&String2, (PCWSTR)(a2 - 56));
      result = RtlCompareUnicodeString(&DestinationString, &String2, 0);
      if ( !result )
      {
        result = *(_DWORD *)(a1 + 1072) - *(_DWORD *)(a2 + 992);
        if ( !result )
        {
          RtlInitUnicodeString(&DestinationString, (PCWSTR)(a1 + 1076));
          RtlInitUnicodeString(&String2, (PCWSTR)(a2 + 996));
          return RtlCompareUnicodeString(&DestinationString, &String2, 0);
        }
      }
    }
  }
  return result;
}

```

## disassembly

```asm
0x14001e034  mov     [rsp-8+arg_0], rbx
0x14001e039  mov     [rsp-8+arg_8], rdi
0x14001e03e  push    rbp
0x14001e03f  mov     rbp, rsp
0x14001e042  sub     rsp, 40h
0x14001e046  mov     eax, [rcx+410h]
0x14001e04c  xorps   xmm0, xmm0
0x14001e04f  xorps   xmm1, xmm1
0x14001e052  mov     rbx, rdx
0x14001e055  mov     rdi, rcx
0x14001e058  movups  xmmword ptr [rbp+DestinationString.Length], xmm0
0x14001e05c  movups  xmmword ptr [rbp+String2.Length], xmm1
0x14001e060  sub     eax, [rdx+3C0h]
0x14001e066  jnz     loc_14001E149
0x14001e06c  mov     rdx, [rcx+38h]; SourceString
0x14001e070  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001e074  call    cs:__imp_RtlInitUnicodeString
0x14001e07b  nop     dword ptr [rax+rax+00h]
0x14001e080  mov     rdx, [rbx-18h]; SourceString
0x14001e084  lea     rcx, [rbp+String2]; DestinationString
0x14001e088  call    cs:__imp_RtlInitUnicodeString
0x14001e08f  nop     dword ptr [rax+rax+00h]
0x14001e094  xor     r8d, r8d; CaseInSensitive
0x14001e097  lea     rdx, [rbp+String2]; String2
0x14001e09b  lea     rcx, [rbp+DestinationString]; String1
0x14001e09f  call    cs:__imp_RtlCompareUnicodeString
0x14001e0a6  nop     dword ptr [rax+rax+00h]
0x14001e0ab  test    eax, eax
0x14001e0ad  jnz     loc_14001E149
0x14001e0b3  lea     rdx, [rdi+18h]; SourceString
0x14001e0b7  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001e0bb  call    cs:__imp_RtlInitUnicodeString
0x14001e0c2  nop     dword ptr [rax+rax+00h]
0x14001e0c7  lea     rdx, [rbx-38h]; SourceString
0x14001e0cb  lea     rcx, [rbp+String2]; DestinationString
0x14001e0cf  call    cs:__imp_RtlInitUnicodeString
0x14001e0d6  nop     dword ptr [rax+rax+00h]
0x14001e0db  xor     r8d, r8d; CaseInSensitive
0x14001e0de  lea     rdx, [rbp+String2]; String2
0x14001e0e2  lea     rcx, [rbp+DestinationString]; String1
0x14001e0e6  call    cs:__imp_RtlCompareUnicodeString
0x14001e0ed  nop     dword ptr [rax+rax+00h]
0x14001e0f2  test    eax, eax
0x14001e0f4  jnz     short loc_14001E149
0x14001e0f6  mov     eax, [rdi+430h]
0x14001e0fc  sub     eax, [rbx+3E0h]
0x14001e102  jnz     short loc_14001E149
0x14001e104  lea     rdx, [rdi+434h]; SourceString
0x14001e10b  lea     rcx, [rbp+DestinationString]; DestinationString
0x14001e10f  call    cs:__imp_RtlInitUnicodeString
0x14001e116  nop     dword ptr [rax+rax+00h]
0x14001e11b  lea     rdx, [rbx+3E4h]; SourceString
0x14001e122  lea     rcx, [rbp+String2]; DestinationString
0x14001e126  call    cs:__imp_RtlInitUnicodeString
0x14001e12d  nop     dword ptr [rax+rax+00h]
0x14001e132  xor     r8d, r8d; CaseInSensitive
0x14001e135  lea     rdx, [rbp+String2]; String2
0x14001e139  lea     rcx, [rbp+DestinationString]; String1
0x14001e13d  call    cs:__imp_RtlCompareUnicodeString
0x14001e144  nop     dword ptr [rax+rax+00h]
0x14001e149  mov     rbx, [rsp+40h+arg_0]
0x14001e14e  mov     rdi, [rsp+40h+arg_8]
0x14001e153  add     rsp, 40h
0x14001e157  pop     rbp
0x14001e158  retn
```
