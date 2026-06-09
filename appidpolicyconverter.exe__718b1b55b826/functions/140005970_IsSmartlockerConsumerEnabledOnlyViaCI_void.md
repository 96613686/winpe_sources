# IsSmartlockerConsumerEnabledOnlyViaCI(void)

- ea: `0x140005970`
- end: `0x1400059d6`
- name: `?IsSmartlockerConsumerEnabledOnlyViaCI@@YA_NXZ`
- size: `102`
- prototype: `bool(void)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config`

## callers

- `0x14000458c`

## callees

- `0x140005970`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400059ba`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400059ba`

## string_xrefs

- `0x14000599e`: `System\CurrentControlSet\Control\AppID\Configuration\SMARTLOCKER`

## pseudocode

```c
bool IsSmartlockerConsumerEnabledOnlyViaCI(void)
{
  DWORD v1; // [rsp+50h] [rbp+8h] BYREF
  __int64 v2; // [rsp+58h] [rbp+10h] BYREF

  v2 = 0;
  v1 = 8;
  return !RegGetValueW(
            HKEY_LOCAL_MACHINE,
            L"System\\CurrentControlSet\\Control\\AppID\\Configuration\\SMARTLOCKER",
            L"ENABLED",
            0x40u,
            0,
            &v2,
            &v1)
      && v2 == 4;
}

```

## disassembly

```asm
0x140005970  mov     r11, rsp
0x140005973  sub     rsp, 48h
0x140005977  lea     rax, [r11+8]
0x14000597b  mov     qword ptr [r11+10h], 0
0x140005983  mov     [r11-18h], rax
0x140005987  lea     r8, Value; "ENABLED"
0x14000598e  lea     rax, [r11+10h]
0x140005992  mov     [rsp+48h+arg_0], 8
0x14000599a  mov     [r11-20h], rax
0x14000599e  lea     rdx, aSystemCurrentc_1; "System\\CurrentControlSet\\Control\\App"...
0x1400059a5  mov     r9d, 40h ; '@'; dwFlags
0x1400059ab  mov     qword ptr [r11-28h], 0
0x1400059b3  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400059ba  call    cs:__imp_RegGetValueW
0x1400059c0  test    eax, eax
0x1400059c2  jnz     short loc_1400059CF
0x1400059c4  cmp     [rsp+48h+arg_8], 4
0x1400059ca  setz    al
0x1400059cd  jmp     short loc_1400059D1
0x1400059cf  xor     al, al
0x1400059d1  add     rsp, 48h
0x1400059d5  retn
```
