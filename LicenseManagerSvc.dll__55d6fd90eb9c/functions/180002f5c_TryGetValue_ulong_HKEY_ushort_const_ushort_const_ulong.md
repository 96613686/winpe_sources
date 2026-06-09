# TryGetValue<ulong>(HKEY__ *,ushort const *,ushort const *,ulong &)

- ea: `0x180002f5c`
- end: `0x180002fd0`
- name: `??$TryGetValue@K@@YA_NPEAUHKEY__@@PEBG1AEAK@Z`
- size: `116`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, service_task, installer_update, broker_com_uri`

## callers

- `0x18000cc78`

## callees

- `0x180002f5c`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002fa3`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x180002fa3`

## string_xrefs

- `0x180002f95`: `SOFTWARE\Microsoft\Windows\CurrentVersion\InstallService\Configuration`

## pseudocode

```c
char __fastcall TryGetValue<unsigned long>(__int64 a1, __int64 a2, const WCHAR *a3, _DWORD *a4)
{
  LSTATUS ValueW; // eax
  bool v6; // sf
  __int64 v8; // [rsp+50h] [rbp+8h] BYREF
  DWORD v9; // [rsp+58h] [rbp+10h] BYREF
  int v10; // [rsp+5Ch] [rbp+14h]

  v10 = HIDWORD(a2);
  v8 = a1;
  v9 = 4;
  ValueW = RegGetValueW(
             HKEY_LOCAL_MACHINE,
             L"SOFTWARE\\Microsoft\\Windows\\CurrentVersion\\InstallService\\Configuration",
             a3,
             0x18u,
             0,
             &v8,
             &v9);
  v6 = ValueW < 0;
  if ( ValueW > 0 )
    v6 = 1;
  if ( v6 )
    return 0;
  *a4 = v8;
  return 1;
}

```

## disassembly

```asm
0x180002f5c  mov     r11, rsp
0x180002f5f  mov     [r11+10h], rdx
0x180002f63  mov     [r11+8], rcx
0x180002f67  push    rbx
0x180002f68  sub     rsp, 40h
0x180002f6c  mov     rbx, r9
0x180002f6f  mov     [rsp+48h+arg_8], 4
0x180002f77  lea     rax, [r11+10h]
0x180002f7b  mov     [r11-18h], rax
0x180002f7f  lea     rax, [r11+8]
0x180002f83  mov     [r11-20h], rax
0x180002f87  mov     qword ptr [r11-28h], 0
0x180002f8f  mov     r9d, 18h; dwFlags
0x180002f95  lea     rdx, SubKey
0x180002f9c  mov     rcx, 0FFFFFFFF80000002h; hkey
0x180002fa3  call    cs:__imp_RegGetValueW
0x180002fa9  test    eax, eax
0x180002fab  jle     short loc_180002FB7
0x180002fad  movzx   eax, ax
0x180002fb0  or      eax, 80070000h
0x180002fb5  test    eax, eax
0x180002fb7  jns     short loc_180002FBD
0x180002fb9  xor     al, al
0x180002fbb  jmp     short loc_180002FC9
0x180002fbd  mov     eax, dword ptr [rsp+48h+arg_0]
0x180002fc1  mov     [rbx], eax
0x180002fc3  mov     al, 1
0x180002fc5  jmp     short loc_180002FC9
0x180002fc7  xor     al, al
0x180002fc9  add     rsp, 40h
0x180002fcd  pop     rbx
0x180002fce  retn
```
