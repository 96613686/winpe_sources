# EdppSetIntentToken

- ea: `0x14002d07c`
- end: `0x14002d12a`
- name: `EdppSetIntentToken`
- size: `174`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x14002bff0`

## callees

- `0x140005994`
- `0x14002c838`
- `0x14002c944`
- `0x14002d07c`

## import_xrefs

- `ntoskrnl!RtlEqualUnicodeString` at `0x14002d0c8`
- `ntoskrnl!RtlEqualUnicodeString` at `0x14002d0c8`
- `ntoskrnl!ZwClose` at `0x14002d110`
- `ntoskrnl!ZwClose` at `0x14002d110`

## pseudocode

```c
__int64 __fastcall EdppSetIntentToken(__int64 a1, __int64 a2)
{
  int IsCurrentContextAllowed; // ebx
  __int64 v3; // rdx
  UNICODE_STRING String1; // [rsp+30h] [rbp-10h] BYREF
  char v6; // [rsp+60h] [rbp+20h] BYREF
  HANDLE Handle; // [rsp+68h] [rbp+28h] BYREF

  v6 = 0;
  Handle = 0;
  String1 = 0;
  IsCurrentContextAllowed = EdppParseEvaluateData(a1, a2, 136, &String1, &Handle);
  if ( IsCurrentContextAllowed >= 0 )
  {
    if ( RtlEqualUnicodeString(&String1, &EdppPersonalName, 0) )
      goto LABEL_6;
    IsCurrentContextAllowed = EdppIsCurrentContextAllowed(&String1, &v6);
    if ( IsCurrentContextAllowed < 0 )
      goto LABEL_7;
    if ( v6 )
LABEL_6:
      IsCurrentContextAllowed = SrpSetIntentEnterpriseIdToken(Handle, v3, &String1);
    else
      IsCurrentContextAllowed = -1073741790;
  }
LABEL_7:
  if ( Handle )
    ZwClose(Handle);
  return (unsigned int)IsCurrentContextAllowed;
}

```

## disassembly

```asm
0x14002d07c  mov     [rsp-8+arg_0], rbx
0x14002d081  push    rbp
0x14002d082  mov     rbp, rsp
0x14002d085  sub     rsp, 40h
0x14002d089  xorps   xmm0, xmm0
0x14002d08c  mov     [rbp+arg_10], 0
0x14002d090  lea     rax, [rbp+Handle]
0x14002d094  mov     [rbp+Handle], 0
0x14002d09c  lea     r9, [rbp+String1]
0x14002d0a0  mov     [rsp+40h+var_20], rax
0x14002d0a5  mov     r8d, 88h
0x14002d0ab  movups  xmmword ptr [rbp+String1.Length], xmm0
0x14002d0af  call    EdppParseEvaluateData
0x14002d0b4  mov     ebx, eax
0x14002d0b6  test    eax, eax
0x14002d0b8  js      short loc_14002D107
0x14002d0ba  xor     r8d, r8d; CaseInSensitive
0x14002d0bd  lea     rdx, EdppPersonalName; String2
0x14002d0c4  lea     rcx, [rbp+String1]; String1
0x14002d0c8  call    cs:__imp_RtlEqualUnicodeString
0x14002d0cf  nop     dword ptr [rax+rax+00h]
0x14002d0d4  test    al, al
0x14002d0d6  jnz     short loc_14002D0F8
0x14002d0d8  lea     rdx, [rbp+arg_10]
0x14002d0dc  lea     rcx, [rbp+String1]
0x14002d0e0  call    EdppIsCurrentContextAllowed
0x14002d0e5  mov     ebx, eax
0x14002d0e7  test    eax, eax
0x14002d0e9  js      short loc_14002D107
0x14002d0eb  cmp     [rbp+arg_10], 0
0x14002d0ef  jnz     short loc_14002D0F8
0x14002d0f1  mov     ebx, 0C0000022h
0x14002d0f6  jmp     short loc_14002D107
0x14002d0f8  mov     rcx, [rbp+Handle]
0x14002d0fc  lea     r8, [rbp+String1]
0x14002d100  call    SrpSetIntentEnterpriseIdToken
0x14002d105  mov     ebx, eax
0x14002d107  mov     rcx, [rbp+Handle]; Handle
0x14002d10b  test    rcx, rcx
0x14002d10e  jz      short loc_14002D11C
0x14002d110  call    cs:__imp_ZwClose
0x14002d117  nop     dword ptr [rax+rax+00h]
0x14002d11c  mov     eax, ebx
0x14002d11e  mov     rbx, [rsp+40h+arg_0]
0x14002d123  add     rsp, 40h
0x14002d127  pop     rbp
0x14002d128  retn
```
