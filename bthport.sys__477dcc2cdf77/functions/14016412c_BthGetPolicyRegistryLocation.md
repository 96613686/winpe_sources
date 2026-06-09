# BthGetPolicyRegistryLocation

- ea: `0x14016412c`
- end: `0x140164235`
- name: `BthGetPolicyRegistryLocation`
- size: `265`
- prototype: `__int64 __fastcall(PUNICODE_STRING DestinationString)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x140164520`

## callees

- `0x14016412c`

## import_xrefs

- `ntoskrnl!ExFreePoolWithTag` at `0x140164216`
- `ntoskrnl!ExFreePoolWithTag` at `0x140164216`
- `ntoskrnl!ExAllocatePool2` at `0x1401641a6`
- `ntoskrnl!ExAllocatePool2` at `0x1401641a6`
- `ntoskrnl!RtlInitUnicodeString` at `0x140164203`
- `ntoskrnl!RtlInitUnicodeString` at `0x140164203`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140164172`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1401641eb`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x140164172`
- `ntoskrnl!RtlGetPersistedStateLocation` at `0x1401641eb`

## string_xrefs

- `0x14016414c`: `\Registry\Machine\System\CurrentControlSet\Policies\Hardware\Bluetooth`
- `0x1401641ce`: `\Registry\Machine\System\CurrentControlSet\Policies\Hardware\Bluetooth`

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
0x14016412c  mov     r11, rsp
0x14016412f  mov     [r11+8], rbx
0x140164133  mov     [r11+18h], rsi
0x140164137  push    rdi
0x140164138  sub     rsp, 40h
0x14016413c  lea     rax, [r11+10h]
0x140164140  mov     [rsp+48h+arg_8], 0
0x140164148  mov     [r11-18h], rax
0x14016414c  lea     r8, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x140164153  mov     rsi, rcx
0x140164156  mov     [rsp+48h+var_20], 0
0x14016415e  xor     r9d, r9d
0x140164161  mov     qword ptr [r11-28h], 0
0x140164169  xor     edx, edx
0x14016416b  lea     rcx, aBluetoothpolic; "BluetoothPolicy"
0x140164172  call    cs:__imp_RtlGetPersistedStateLocation
0x140164179  nop     dword ptr [rax+rax+00h]
0x14016417e  test    eax, eax
0x140164180  js      short loc_14016418C
0x140164182  mov     eax, 0C0000001h
0x140164187  jmp     loc_140164224
0x14016418c  cmp     eax, 80000005h
0x140164191  jnz     loc_140164224
0x140164197  mov     edx, [rsp+48h+arg_8]
0x14016419b  mov     ecx, 40h ; '@'
0x1401641a0  mov     r8d, 746D7062h
0x1401641a6  call    cs:__imp_ExAllocatePool2
0x1401641ad  nop     dword ptr [rax+rax+00h]
0x1401641b2  mov     rbx, rax
0x1401641b5  test    rax, rax
0x1401641b8  jnz     short loc_1401641C1
0x1401641ba  mov     eax, 0C000009Ah
0x1401641bf  jmp     short loc_140164224
0x1401641c1  lea     rax, [rsp+48h+arg_8]
0x1401641c6  xor     r9d, r9d
0x1401641c9  mov     [rsp+48h+var_18], rax
0x1401641ce  lea     r8, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x1401641d5  mov     eax, [rsp+48h+arg_8]
0x1401641d9  lea     rcx, aBluetoothpolic; "BluetoothPolicy"
0x1401641e0  mov     [rsp+48h+var_20], eax
0x1401641e4  xor     edx, edx
0x1401641e6  mov     [rsp+48h+var_28], rbx
0x1401641eb  call    cs:__imp_RtlGetPersistedStateLocation
0x1401641f2  nop     dword ptr [rax+rax+00h]
0x1401641f7  mov     edi, eax
0x1401641f9  test    eax, eax
0x1401641fb  js      short loc_140164211
0x1401641fd  mov     rdx, rbx; SourceString
0x140164200  mov     rcx, rsi; DestinationString
0x140164203  call    cs:__imp_RtlInitUnicodeString
0x14016420a  nop     dword ptr [rax+rax+00h]
0x14016420f  jmp     short loc_140164222
0x140164211  xor     edx, edx; Tag
0x140164213  mov     rcx, rbx; P
0x140164216  call    cs:__imp_ExFreePoolWithTag
0x14016421d  nop     dword ptr [rax+rax+00h]
0x140164222  mov     eax, edi
0x140164224  mov     rbx, [rsp+48h+arg_0]
0x140164229  mov     rsi, [rsp+48h+arg_10]
0x14016422e  add     rsp, 40h
0x140164232  pop     rdi
0x140164233  retn
```
