# SmartlockerSmartScreenRegistryIsEnabled

- ea: `0x140033130`
- end: `0x140033193`
- name: `SmartlockerSmartScreenRegistryIsEnabled`
- size: `99`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140023a40`
- `0x140034550`
- `0x140035580`

## callees

- `0x140001450`
- `0x140033130`

## string_xrefs

- `0x140033137`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
_BOOL8 SmartlockerSmartScreenRegistryIsEnabled()
{
  _QWORD v1[2]; // [rsp+20h] [rbp-28h] BYREF
  _QWORD v2[3]; // [rsp+30h] [rbp-18h] BYREF
  __int64 v3; // [rsp+50h] [rbp+8h] BYREF

  v2[0] = 10879140;
  v2[1] = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER";
  v1[0] = 1048590;
  v1[1] = L"ENABLED";
  v3 = 0;
  return (int)AiRegReadQwordValue(0, v2, v1, &v3) >= 0 && v3;
}

```

## disassembly

```asm
0x140033130  mov     r11, rsp
0x140033133  sub     rsp, 48h
0x140033137  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x14003313e  mov     qword ptr [r11-18h], 0A600A4h
0x140033146  mov     [r11-10h], rax
0x14003314a  lea     r9, [r11+8]
0x14003314e  lea     rax, aEnabled; "ENABLED"
0x140033155  mov     qword ptr [r11-28h], 10000Eh
0x14003315d  lea     r8, [r11-28h]
0x140033161  mov     [r11-20h], rax
0x140033165  lea     rdx, [r11-18h]
0x140033169  mov     qword ptr [r11+8], 0
0x140033171  xor     ecx, ecx
0x140033173  call    AiRegReadQwordValue
0x140033178  test    eax, eax
0x14003317a  js      short loc_14003318F
0x14003317c  cmp     [rsp+48h+arg_0], 0
0x140033182  jz      short loc_14003318F
0x140033184  mov     eax, 1
0x140033189  add     rsp, 48h
0x14003318d  retn
0x14003318f  xor     eax, eax
0x140033191  jmp     short loc_140033189
```
