# CMidiXProc::MMCSSUseEnabled(void)

- ea: `0x18000f438`
- end: `0x18000f4d0`
- name: `?MMCSSUseEnabled@CMidiXProc@@SA_NXZ`
- size: `152`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x18000d854`
- `0x18000d8b0`

## callees

- `0x18000f438`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f48b`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x18000f48b`

## string_xrefs

- `0x18000f46f`: `Software\Microsoft\Windows MIDI Services`

## pseudocode

```c
bool CMidiXProc::MMCSSUseEnabled(void)
{
  LSTATUS ValueW; // eax
  bool v1; // sf
  int v2; // eax
  int v4; // [rsp+50h] [rbp+8h] BYREF
  DWORD v5; // [rsp+58h] [rbp+10h] BYREF

  if ( CMidiXProc::m_mmcssSettingRead )
  {
    v2 = CMidiXProc::m_useMMCSS;
  }
  else
  {
    v4 = 0;
    v5 = 4;
    ValueW = RegGetValueW(
               HKEY_LOCAL_MACHINE,
               L"Software\\Microsoft\\Windows MIDI Services",
               L"UseMMCSS",
               0x10u,
               0,
               &v4,
               &v5);
    v1 = ValueW < 0;
    if ( ValueW > 0 )
      v1 = 1;
    v2 = !v1 && v4 != 0;
    CMidiXProc::m_useMMCSS = v2;
    CMidiXProc::m_mmcssSettingRead = 1;
  }
  return v2 != 0;
}

```

## disassembly

```asm
0x18000f438  mov     r11, rsp
0x18000f43b  sub     rsp, 48h
0x18000f43f  cmp     cs:?m_mmcssSettingRead@CMidiXProc@@0HA, 0; int CMidiXProc::m_mmcssSettingRead
0x18000f446  jnz     short loc_18000F4C0
0x18000f448  lea     rax, [r11+10h]
0x18000f44c  mov     [rsp+48h+arg_0], 0
0x18000f454  mov     [r11-18h], rax
0x18000f458  lea     r8, Value; "UseMMCSS"
0x18000f45f  lea     rax, [r11+8]
0x18000f463  mov     [rsp+48h+arg_8], 4
0x18000f46b  mov     [r11-20h], rax
0x18000f46f  lea     rdx, SubKey; "Software\\Microsoft\\Windows MIDI Servi"...
0x18000f476  mov     r9d, 10h; dwFlags
0x18000f47c  mov     qword ptr [r11-28h], 0
0x18000f484  mov     rcx, 0FFFFFFFF80000002h; hkey
0x18000f48b  call    cs:__imp_RegGetValueW
0x18000f491  test    eax, eax
0x18000f493  jle     short loc_18000F49F
0x18000f495  movzx   eax, ax
0x18000f498  or      eax, 80070000h
0x18000f49d  test    eax, eax
0x18000f49f  js      short loc_18000F4AC
0x18000f4a1  xor     eax, eax
0x18000f4a3  cmp     [rsp+48h+arg_0], eax
0x18000f4a7  setnbe  al
0x18000f4aa  jmp     short loc_18000F4AE
0x18000f4ac  xor     eax, eax
0x18000f4ae  mov     cs:?m_useMMCSS@CMidiXProc@@0HA, eax; int CMidiXProc::m_useMMCSS
0x18000f4b4  mov     cs:?m_mmcssSettingRead@CMidiXProc@@0HA, 1; int CMidiXProc::m_mmcssSettingRead
0x18000f4be  jmp     short loc_18000F4C6
0x18000f4c0  mov     eax, cs:?m_useMMCSS@CMidiXProc@@0HA; int CMidiXProc::m_useMMCSS
0x18000f4c6  test    eax, eax
0x18000f4c8  setnz   al
0x18000f4cb  add     rsp, 48h
0x18000f4cf  retn
```
