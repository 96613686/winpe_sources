# SmartlockerEnabledAsPerPolicyConverter

- ea: `0x1400230a8`
- end: `0x140023109`
- name: `SmartlockerEnabledAsPerPolicyConverter`
- size: `97`
- prototype: `_BOOL8 __fastcall(__int64)`
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140035580`

## callees

- `0x1400230a8`
- `0x1400293ac`

## string_xrefs

- `0x1400230b1`: `\Registry\Machine\System\CurrentControlSet\Control\Srp\GP\`

## pseudocode

```c
_BOOL8 __fastcall SmartlockerEnabledAsPerPolicyConverter(__int64 a1)
{
  struct _UNICODE_STRING v2; // [rsp+20h] [rbp-20h] BYREF
  struct _UNICODE_STRING v3; // [rsp+30h] [rbp-10h] BYREF
  int v4; // [rsp+50h] [rbp+10h] BYREF

  *(_QWORD *)&v3.Length = 7733364;
  v3.Buffer = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\Srp\\GP\\";
  *(_QWORD *)&v2.Length = 3014700;
  v2.Buffer = L"LastSmartlockerEnabled";
  v4 = 0;
  return (int)AiRegReadDwordValue(a1, &v3, &v2, &v4) >= 0 && v4;
}

```

## disassembly

```asm
0x1400230a8  push    rbp
0x1400230aa  mov     rbp, rsp
0x1400230ad  sub     rsp, 40h
0x1400230b1  lea     rax, aRegistryMachin_9; "\\Registry\\Machine\\System\\CurrentCon"...
0x1400230b8  mov     [rbp+var_10], 760074h
0x1400230c0  mov     [rbp+var_8], rax
0x1400230c4  lea     r9, [rbp+arg_0]
0x1400230c8  lea     rax, aLastsmartlocke; "LastSmartlockerEnabled"
0x1400230cf  mov     [rbp+var_20], 2E002Ch
0x1400230d7  lea     r8, [rbp+var_20]
0x1400230db  mov     [rbp+var_18], rax
0x1400230df  lea     rdx, [rbp+var_10]
0x1400230e3  mov     [rbp+arg_0], 0
0x1400230ea  call    AiRegReadDwordValue
0x1400230ef  test    eax, eax
0x1400230f1  js      short loc_140023100
0x1400230f3  cmp     [rbp+arg_0], 0
0x1400230f7  jz      short loc_140023100
0x1400230f9  mov     eax, 1
0x1400230fe  jmp     short loc_140023102
0x140023100  xor     eax, eax
0x140023102  add     rsp, 40h
0x140023106  pop     rbp
0x140023107  retn
```
