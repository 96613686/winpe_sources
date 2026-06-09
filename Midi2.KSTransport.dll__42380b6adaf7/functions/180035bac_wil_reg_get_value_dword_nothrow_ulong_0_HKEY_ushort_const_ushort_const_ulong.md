# wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x180035bac`
- end: `0x180035c05`
- name: `??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18003cd70`

## callees

- `0x180035bac`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180035bee`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180035bee`

## string_xrefs

- `0x180035bd2`: `Software\Microsoft\Windows MIDI Services`

## pseudocode

```c
LSTATUS __fastcall wil::reg::get_value_dword_nothrow<unsigned long,0>(__int64 a1, __int64 a2, __int64 a3, void *a4)
{
  LSTATUS result; // eax
  DWORD v5; // [rsp+60h] [rbp+18h] BYREF
  int v6; // [rsp+64h] [rbp+1Ch]

  v6 = HIDWORD(a3);
  v5 = 4;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"Software\\Microsoft\\Windows MIDI Services",
             L"UseMMCSS",
             0x10u,
             0,
             a4,
             &v5);
  if ( result > 0 )
    return (unsigned __int16)result | 0x80070000;
  return result;
}

```

## disassembly

```asm
0x180035bac  mov     r11, rsp
0x180035baf  mov     [r11+18h], r8
0x180035bb3  sub     rsp, 48h
0x180035bb7  lea     rax, [r11+18h]
0x180035bbb  mov     [rsp+48h+arg_10], 4
0x180035bc3  mov     [r11-18h], rax
0x180035bc7  lea     r8, Value; "UseMMCSS"
0x180035bce  mov     [r11-20h], r9
0x180035bd2  lea     rdx, SubKey; "Software\\Microsoft\\Windows MIDI Servi"...
0x180035bd9  mov     r9d, 10h; dwFlags
0x180035bdf  mov     qword ptr [r11-28h], 0
0x180035be7  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180035bee  call    cs:__imp_RegGetValueW
0x180035bf4  test    eax, eax
0x180035bf6  jle     short loc_180035C00
0x180035bf8  movzx   eax, ax
0x180035bfb  or      eax, 80070000h
0x180035c00  add     rsp, 48h
0x180035c04  retn
```
