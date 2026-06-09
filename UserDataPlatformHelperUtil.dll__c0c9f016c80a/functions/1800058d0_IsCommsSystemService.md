# IsCommsSystemService

- ea: `0x1800058d0`
- end: `0x18000596d`
- name: `IsCommsSystemService`
- size: `157`
- prototype: `_BOOL8()`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x1800054b0`

## callees

- `0x1800058d0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005926`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180005926`

## pseudocode

```c
_BOOL8 IsCommsSystemService()
{
  LSTATUS ValueW; // eax
  bool v1; // sf
  BOOL v2; // eax
  BOOL v4; // [rsp+50h] [rbp+8h] BYREF
  DWORD v5; // [rsp+58h] [rbp+10h] BYREF

  if ( dword_180011290 == -1 )
  {
    v4 = 0;
    v5 = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Unified Store",
               L"UseLegacyDBLocation",
               0x20000018u,
               0,
               &v4,
               &v5);
    v1 = ValueW < 0;
    if ( ValueW > 0 )
      v1 = 1;
    v2 = !v1 && v4;
    v4 = v2;
    dword_180011290 = v2;
    _mm_mfence();
  }
  return dword_180011290 > 0;
}

```

## disassembly

```asm
0x1800058d0  mov     r11, rsp
0x1800058d3  sub     rsp, 48h
0x1800058d7  mov     eax, cs:dword_180011290
0x1800058dd  nop
0x1800058de  cmp     eax, 0FFFFFFFFh
0x1800058e1  jnz     short loc_18000595A
0x1800058e3  lea     rax, [r11+10h]
0x1800058e7  mov     [rsp+48h+arg_0], 0
0x1800058ef  mov     [r11-18h], rax
0x1800058f3  lea     r8, Value; "UseLegacyDBLocation"
0x1800058fa  lea     rax, [r11+8]
0x1800058fe  mov     [rsp+48h+arg_8], 4
0x180005906  mov     [r11-20h], rax
0x18000590a  lea     rdx, SubKey; "Software\\Microsoft\\Unified Store"
0x180005911  mov     r9d, 20000018h; dwFlags
0x180005917  mov     qword ptr [r11-28h], 0
0x18000591f  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180005926  call    cs:__imp_RegGetValueW
0x18000592c  test    eax, eax
0x18000592e  jle     short loc_18000593A
0x180005930  movzx   eax, ax
0x180005933  or      eax, 80070000h
0x180005938  test    eax, eax
0x18000593a  js      short loc_18000594A
0x18000593c  cmp     [rsp+48h+arg_0], 0
0x180005941  jbe     short loc_18000594A
0x180005943  mov     eax, 1
0x180005948  jmp     short loc_18000594C
0x18000594a  xor     eax, eax
0x18000594c  mov     [rsp+48h+arg_0], eax
0x180005950  nop
0x180005951  mov     cs:dword_180011290, eax
0x180005957  mfence
0x18000595a  mov     ecx, cs:dword_180011290
0x180005960  xor     eax, eax
0x180005962  test    ecx, ecx
0x180005964  nop
0x180005965  setnle  al
0x180005968  add     rsp, 48h
0x18000596c  retn
```
