# LogAccessDenial(ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *,ushort const *)

- ea: `0x1800105e4`
- end: `0x18001063c`
- name: `?LogAccessDenial@@YAXPEBG0000000@Z`
- size: `88`
- prototype: `void __fastcall(const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *, const unsigned __int16 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `installer_update, broker_com_uri`

## callers

- `0x180013038`

## callees

- `0x1800105e4`
- `0x1800114a4`

## pseudocode

```c
void __fastcall LogAccessDenial(
        const char *a1,
        const char *a2,
        const char *a3,
        const char *a4,
        const unsigned __int16 *a5,
        const unsigned __int16 *a6,
        const unsigned __int16 *a7,
        const unsigned __int16 *a8)
{
  if ( (Microsoft_Windows_WPDClassInstallerEnableBits & 4) != 0 )
    McTemplateU0zzzzzzzzz_EventWriteTransfer(
      (__int64)a1,
      (__int64)a2,
      a1,
      a2,
      a3,
      a4,
      (const char *)a5,
      (const char *)a6,
      (const char *)a7,
      (const char *)a8);
}

```

## disassembly

```asm
0x1800105e4  mov     r11, rsp
0x1800105e7  sub     rsp, 68h
0x1800105eb  test    cs:Microsoft_Windows_WPDClassInstallerEnableBits, 4
0x1800105f2  jz      short loc_180010637
0x1800105f4  mov     rax, [rsp+68h+arg_38]
0x1800105fc  mov     [r11-20h], rax
0x180010600  mov     rax, [rsp+68h+arg_30]
0x180010608  mov     [r11-28h], rax
0x18001060c  mov     rax, [rsp+68h+arg_28]
0x180010614  mov     [r11-30h], rax
0x180010618  mov     rax, [rsp+68h+arg_20]
0x180010620  mov     [r11-38h], rax
0x180010624  mov     [r11-40h], r9
0x180010628  mov     r9, rdx
0x18001062b  mov     [r11-48h], r8
0x18001062f  mov     r8, rcx
0x180010632  call    McTemplateU0zzzzzzzzz_EventWriteTransfer
0x180010637  add     rsp, 68h
0x18001063b  retn
```
