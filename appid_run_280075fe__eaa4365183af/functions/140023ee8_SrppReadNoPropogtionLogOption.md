# SrppReadNoPropogtionLogOption

- ea: `0x140023ee8`
- end: `0x140023f4d`
- name: `SrppReadNoPropogtionLogOption`
- size: `101`
- prototype: ``
- caller_count: `1`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x1400387a4`

## callees

- `0x140023ee8`
- `0x1400293ac`

## string_xrefs

- `0x140023ef1`: `\Registry\Machine\System\CurrentControlSet\Control\AppID\Configuration\EventSuppression`

## pseudocode

```c
__int64 __fastcall SrppReadNoPropogtionLogOption(__int64 a1)
{
  __int64 result; // rax
  _QWORD v2[2]; // [rsp+20h] [rbp-20h] BYREF
  _QWORD v3[2]; // [rsp+30h] [rbp-10h] BYREF
  unsigned int v4; // [rsp+50h] [rbp+10h] BYREF

  v3[0] = 11534510;
  v3[1] = L"\\Registry\\Machine\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\EventSuppression";
  v2[0] = 3014700;
  v2[1] = L"NoPropogationLogOption";
  v4 = 0;
  dword_140019728 = 0;
  result = AiRegReadDwordValue(a1, v3, v2, &v4);
  if ( (int)result >= 0 )
  {
    result = v4;
    dword_140019728 = v4;
  }
  return result;
}

```

## disassembly

```asm
0x140023ee8  push    rbp
0x140023eea  mov     rbp, rsp
0x140023eed  sub     rsp, 40h
0x140023ef1  lea     rax, aRegistryMachin_5; "\\Registry\\Machine\\System\\CurrentCon"...
0x140023ef8  mov     [rbp+var_10], 0B000AEh
0x140023f00  mov     [rbp+var_8], rax
0x140023f04  lea     r9, [rbp+arg_0]
0x140023f08  lea     rax, aNopropogationl; "NoPropogationLogOption"
0x140023f0f  mov     [rbp+var_20], 2E002Ch
0x140023f17  lea     r8, [rbp+var_20]
0x140023f1b  mov     [rbp+var_18], rax
0x140023f1f  lea     rdx, [rbp+var_10]
0x140023f23  mov     [rbp+arg_0], 0
0x140023f2a  mov     cs:dword_140019728, 0
0x140023f34  call    AiRegReadDwordValue
0x140023f39  test    eax, eax
0x140023f3b  js      short loc_140023F46
0x140023f3d  mov     eax, [rbp+arg_0]
0x140023f40  mov     cs:dword_140019728, eax
0x140023f46  add     rsp, 40h
0x140023f4a  pop     rbp
0x140023f4b  retn
```
