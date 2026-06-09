# SHRegGetDWORD(HKEY__ *,ushort const *,ushort const *,ulong *)

- ea: `0x18001c0a4`
- end: `0x18001c0fd`
- name: `?SHRegGetDWORD@@YAJPEAUHKEY__@@PEBG1PEAK@Z`
- size: `89`
- prototype: `__int64 __fastcall(HKEY, const unsigned __int16 *, const unsigned __int16 *, unsigned int *)`
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task`

## callers

- `0x18001b1c8`

## callees

- `0x18001c0a4`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c0e6`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18001c0e6`

## string_xrefs

- `0x18001c0ca`: `SYSTEM\CurrentControlSet\Services\diagsvc\Settings`

## pseudocode

```c
LSTATUS __fastcall SHRegGetDWORD(HKEY a1, const unsigned __int16 *a2, const unsigned __int16 *a3, unsigned int *a4)
{
  LSTATUS result; // eax
  DWORD v5; // [rsp+60h] [rbp+18h] BYREF
  int v6; // [rsp+64h] [rbp+1Ch]

  v6 = HIDWORD(a3);
  v5 = 4;
  result = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SYSTEM\\CurrentControlSet\\Services\\diagsvc\\Settings",
             L"RequestCount",
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
0x18001c0a4  mov     r11, rsp
0x18001c0a7  mov     [r11+18h], r8
0x18001c0ab  sub     rsp, 48h
0x18001c0af  lea     rax, [r11+18h]
0x18001c0b3  mov     [rsp+48h+arg_10], 4
0x18001c0bb  mov     [r11-18h], rax
0x18001c0bf  lea     r8, aRequestcount; "RequestCount"
0x18001c0c6  mov     [r11-20h], r9
0x18001c0ca  lea     rdx, aSystemCurrentc; "SYSTEM\\CurrentControlSet\\Services\\di"...
0x18001c0d1  mov     r9d, 10h; dwFlags
0x18001c0d7  mov     qword ptr [r11-28h], 0
0x18001c0df  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18001c0e6  call    cs:__imp_RegGetValueW
0x18001c0ec  test    eax, eax
0x18001c0ee  jle     short loc_18001C0F8
0x18001c0f0  movzx   eax, ax
0x18001c0f3  or      eax, 80070000h
0x18001c0f8  add     rsp, 48h
0x18001c0fc  retn
```
