# BthGetPolicyRegistryLocation

- ea: `0x140006fa8`
- end: `0x1400070b1`
- name: `BthGetPolicyRegistryLocation`
- size: `265`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140020078`

## callees

- `0x140006fa8`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140007092`
- `ntoskrnl!ExFreePoolWithTag` at `0x140007092`
- `ntoskrnl!ExAllocatePool2` at `0x140007022`
- `ntoskrnl!ExAllocatePool2` at `0x140007022`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000707f`
- `ntoskrnl!RtlInitUnicodeString` at `0x14000707f`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140006fee`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140007067`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140006fee`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140007067`

## string_xrefs

- `0x140006fc8`: `\Registry\Machine\System\CurrentControlSet\Policies\Hardware\Bluetooth`
- `0x14000704a`: `\Registry\Machine\System\CurrentControlSet\Policies\Hardware\Bluetooth`

## pseudocode

```c
__int64 __fastcall BthGetPolicyRegistryLocation(PUNICODE_STRING DestinationString)
{
  __int64 result; // rax
  void *Pool2; // rbx
  int PersistedStateLocation; // edi
  unsigned int v5; // [rsp+58h] [rbp+10h] BYREF

  v5 = 0;
  result = RtlGetPersistedStateLocation(
             L"BluetoothPolicy",
             0,
             L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies\\Hardware\\Bluetooth",
             0,
             0,
             0,
             &v5);
  if ( (int)result >= 0 )
    return 3221225473LL;
  if ( (_DWORD)result == -2147483643 )
  {
    Pool2 = (void *)ExAllocatePool2(64, v5, 1953329250);
    if ( Pool2 )
    {
      PersistedStateLocation = RtlGetPersistedStateLocation(
                                 L"BluetoothPolicy",
                                 0,
                                 L"\\Registry\\Machine\\System\\CurrentControlSet\\Policies\\Hardware\\Bluetooth",
                                 0,
                                 Pool2,
                                 v5,
                                 &v5);
      if ( PersistedStateLocation < 0 )
        ExFreePoolWithTag(Pool2, 0);
      else
        RtlInitUnicodeString(DestinationString, (PCWSTR)Pool2);
      return (unsigned int)PersistedStateLocation;
    }
    else
    {
      return 3221225626LL;
    }
  }
  return result;
}

```

## disassembly

```asm
0x140006fa8  mov     r11, rsp
0x140006fab  mov     [r11+8], rbx
0x140006faf  mov     [r11+18h], rsi
0x140006fb3  push    rdi
0x140006fb4  sub     rsp, 40h
0x140006fb8  lea     rax, [r11+10h]
0x140006fbc  mov     [rsp+48h+arg_8], 0
0x140006fc4  mov     [r11-18h], rax
0x140006fc8  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x140006fcf  mov     rsi, rcx
0x140006fd2  mov     [rsp+48h+var_20], 0
0x140006fda  xor     r9d, r9d
0x140006fdd  mov     qword ptr [r11-28h], 0
0x140006fe5  xor     edx, edx
0x140006fe7  lea     rcx, aBluetoothpolic; "BluetoothPolicy"
0x140006fee  call    cs:__imp_RtlGetPersistedStateLocation
0x140006ff5  nop     dword ptr [rax+rax+00h]
0x140006ffa  test    eax, eax
0x140006ffc  js      short loc_140007008
0x140006ffe  mov     eax, 0C0000001h
0x140007003  jmp     loc_1400070A0
0x140007008  cmp     eax, 80000005h
0x14000700d  jnz     loc_1400070A0
0x140007013  mov     edx, [rsp+48h+arg_8]
0x140007017  mov     ecx, 40h ; '@'
0x14000701c  mov     r8d, 746D7062h
0x140007022  call    cs:__imp_ExAllocatePool2
0x140007029  nop     dword ptr [rax+rax+00h]
0x14000702e  mov     rbx, rax
0x140007031  test    rax, rax
0x140007034  jnz     short loc_14000703D
0x140007036  mov     eax, 0C000009Ah
0x14000703b  jmp     short loc_1400070A0
0x14000703d  lea     rax, [rsp+48h+arg_8]
0x140007042  xor     r9d, r9d
0x140007045  mov     [rsp+48h+var_18], rax
0x14000704a  lea     r8, aRegistryMachin_0; "\\Registry\\Machine\\System\\CurrentCon"...
0x140007051  mov     eax, [rsp+48h+arg_8]
0x140007055  lea     rcx, aBluetoothpolic; "BluetoothPolicy"
0x14000705c  mov     [rsp+48h+var_20], eax
0x140007060  xor     edx, edx
0x140007062  mov     [rsp+48h+var_28], rbx
0x140007067  call    cs:__imp_RtlGetPersistedStateLocation
0x14000706e  nop     dword ptr [rax+rax+00h]
0x140007073  mov     edi, eax
0x140007075  test    eax, eax
0x140007077  js      short loc_14000708D
0x140007079  mov     rdx, rbx; SourceString
0x14000707c  mov     rcx, rsi; DestinationString
0x14000707f  call    cs:__imp_RtlInitUnicodeString
0x140007086  nop     dword ptr [rax+rax+00h]
0x14000708b  jmp     short loc_14000709E
0x14000708d  xor     edx, edx; Tag
0x14000708f  mov     rcx, rbx; P
0x140007092  call    cs:__imp_ExFreePoolWithTag
0x140007099  nop     dword ptr [rax+rax+00h]
0x14000709e  mov     eax, edi
0x1400070a0  mov     rbx, [rsp+48h+arg_0]
0x1400070a5  mov     rsi, [rsp+48h+arg_10]
0x1400070aa  add     rsp, 40h
0x1400070ae  pop     rdi
0x1400070af  retn
```
