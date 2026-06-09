# wil::reg::get_value_dword_nothrow<ulong,0>(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x140036378`
- end: `0x1400363ca`
- name: `??$get_value_dword_nothrow@K$0A@@reg@wil@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `82`
- prototype: `LSTATUS __fastcall(__int64, __int64, const WCHAR *, void *)`
- caller_count: `4`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14002fcf0`
- `0x140037100`
- `0x140041a40`
- `0x140046b90`

## callees

- `0x140036378`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400363b3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x1400363b3`

## string_xrefs

- `0x140036393`: `Software\Microsoft\Windows MIDI Services`

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
0x140036378  mov     r11, rsp
0x14003637b  mov     [r11+10h], rdx
0x14003637f  sub     rsp, 48h
0x140036383  lea     rax, [r11+10h]
0x140036387  mov     [rsp+48h+arg_8], 4
0x14003638f  mov     [r11-18h], rax
0x140036393  lea     rdx, aSoftwareMicros_0; "Software\\Microsoft\\Windows MIDI Servi"...
0x14003639a  mov     [r11-20h], r9
0x14003639e  mov     rcx, 0FFFFFFFF80000002h; hkey
0x1400363a5  mov     r9d, 10h; dwFlags
0x1400363ab  mov     qword ptr [r11-28h], 0
0x1400363b3  call    cs:__imp_RegGetValueW
0x1400363b9  test    eax, eax
0x1400363bb  jle     short loc_1400363C5
0x1400363bd  movzx   eax, ax
0x1400363c0  or      eax, 80070000h
0x1400363c5  add     rsp, 48h
0x1400363c9  retn
```
