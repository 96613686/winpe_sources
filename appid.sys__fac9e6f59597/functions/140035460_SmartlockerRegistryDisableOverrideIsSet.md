# SmartlockerRegistryDisableOverrideIsSet

- ea: `0x140035460`
- end: `0x1400354c3`
- name: `SmartlockerRegistryDisableOverrideIsSet`
- size: `99`
- prototype: `_BOOL8()`
- caller_count: `2`
- callee_count: `2`
- tags: `registry_config`

## callers

- `0x140023a40`
- `0x140034550`

## callees

- `0x140001450`
- `0x140035460`

## string_xrefs

- `0x140035467`: `\REGISTRY\MACHINE\System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
_BOOL8 SmartlockerRegistryDisableOverrideIsSet()
{
  struct _UNICODE_STRING v1; // [rsp+20h] [rbp-28h] BYREF
  struct _UNICODE_STRING v2; // [rsp+30h] [rbp-18h] BYREF
  __int64 v3; // [rsp+50h] [rbp+8h] BYREF

  *(_QWORD *)&v2.Length = 10879140;
  v2.Buffer = L"\\REGISTRY\\MACHINE\\System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER";
  *(_QWORD *)&v1.Length = 1179664;
  v1.Buffer = L"DISABLED";
  v3 = 0;
  return (int)AiRegReadQwordValue(0, &v2, &v1, &v3) >= 0 && v3;
}

```

## disassembly

```asm
0x140035460  mov     r11, rsp
0x140035463  sub     rsp, 48h
0x140035467  lea     rax, aRegistryMachin; "\\REGISTRY\\MACHINE\\System\\CurrentCon"...
0x14003546e  mov     qword ptr [r11-18h], 0A600A4h
0x140035476  mov     [r11-10h], rax
0x14003547a  lea     r9, [r11+8]
0x14003547e  lea     rax, aDisabled; "DISABLED"
0x140035485  mov     qword ptr [r11-28h], 120010h
0x14003548d  lea     r8, [r11-28h]
0x140035491  mov     [r11-20h], rax
0x140035495  lea     rdx, [r11-18h]
0x140035499  mov     qword ptr [r11+8], 0
0x1400354a1  xor     ecx, ecx
0x1400354a3  call    AiRegReadQwordValue
0x1400354a8  test    eax, eax
0x1400354aa  js      short loc_1400354BB
0x1400354ac  cmp     [rsp+48h+arg_0], 0
0x1400354b2  jz      short loc_1400354BB
0x1400354b4  mov     eax, 1
0x1400354b9  jmp     short loc_1400354BD
0x1400354bb  xor     eax, eax
0x1400354bd  add     rsp, 48h
0x1400354c1  retn
```
