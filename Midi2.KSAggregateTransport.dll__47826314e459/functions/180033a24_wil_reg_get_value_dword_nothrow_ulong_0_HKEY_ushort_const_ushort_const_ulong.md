# wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180033a24`
- end: `0x180033a76`
- name: `??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `82`
- prototype: ``
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003bf70`
- `0x18005836c`

## callees

- `0x180033a24`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033a5f`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180033a5f`

## string_xrefs

- `0x180033a3f`: `Software\Microsoft\Windows MIDI Services`

## pseudocode

```c
LSTATUS __fastcall wil::reg::get_value_dword_nothrow<unsigned long,0>(
        __int64 a1,
        __int64 a2,
        const WCHAR *a3,
        void *a4)
{
  LSTATUS result; // eax
  DWORD v5; // [rsp+58h] [rbp+10h] BYREF
  int v6; // [rsp+5Ch] [rbp+14h]

  v6 = HIDWORD(a2);
  v5 = 4;
  result = RegGetValueW(HKEY_LOCAL_MACHINE, L"Software\\Microsoft\\Windows MIDI Services", a3, 0x10u, 0, a4, &v5);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180033a24  mov     r11, rsp
0x180033a27  mov     [r11+10h], rdx
0x180033a2b  sub     rsp, 48h
0x180033a2f  lea     rax, [r11+10h]
0x180033a33  mov     [rsp+48h+arg_8], 4
0x180033a3b  mov     [r11-18h], rax
0x180033a3f  lea     rdx, SubKey; "Software\\Microsoft\\Windows MIDI Servi"...
0x180033a46  mov     [r11-20h], r9
0x180033a4a  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180033a51  mov     r9d, 10h; dwFlags
0x180033a57  mov     qword ptr [r11-28h], 0
0x180033a5f  call    cs:__imp_RegGetValueW
0x180033a65  test    eax, eax
0x180033a67  jle     short loc_180033A71
0x180033a69  movzx   eax, ax
0x180033a6c  or      eax, 80070000h
0x180033a71  add     rsp, 48h
0x180033a75  retn
```
