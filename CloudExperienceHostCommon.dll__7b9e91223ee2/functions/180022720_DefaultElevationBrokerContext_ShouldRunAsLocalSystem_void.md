# DefaultElevationBrokerContext::ShouldRunAsLocalSystem(void)

- ea: `0x180022720`
- end: `0x180022787`
- name: `?ShouldRunAsLocalSystem@DefaultElevationBrokerContext@@UEAAJXZ`
- size: `103`
- prototype: `_BOOL8 __fastcall(DefaultElevationBrokerContext *this)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180022658`
- `0x180022720`

## import_xrefs

- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180022739`
- `api-ms-win-oobe-notification-l1-1-0!OOBEComplete` at `0x180022739`

## string_xrefs

- `0x180022762`: `Software\Microsoft\Windows\CurrentVersion\CloudExperienceHost\Broker`

## pseudocode

```c
_BOOL8 __fastcall DefaultElevationBrokerContext::ShouldRunAsLocalSystem(DefaultElevationBrokerContext *this)
{
  unsigned int v1; // r9d
  int v3; // [rsp+48h] [rbp+10h] BYREF
  int v4; // [rsp+50h] [rbp+18h] BYREF

  v3 = 0;
  v4 = 0;
  return (!(unsigned int)OOBEComplete(&v3) || v3)
      && ((int)SHRegGetBOOLWithREGSAM(
                 HKEY_LOCAL_MACHINE,
                 L"Software\\Microsoft\\Windows\\CurrentVersion\\CloudExperienceHost\\Broker",
                 L"AlwaysAllowLocalSystem",
                 v1,
                 &v4) < 0
       || !v4);
}

```

## disassembly

```asm
0x180022720  sub     rsp, 38h
0x180022724  lea     rcx, [rsp+38h+arg_8]
0x180022729  mov     [rsp+38h+arg_8], 0
0x180022731  mov     [rsp+38h+arg_10], 0
0x180022739  call    cs:__imp_OOBEComplete
0x18002273f  test    eax, eax
0x180022741  jz      short loc_18002274A
0x180022743  cmp     [rsp+38h+arg_8], 0
0x180022748  jz      short loc_180022779
0x18002274a  lea     rax, [rsp+38h+arg_10]
0x18002274f  mov     rcx, 0FFFFFFFF80000002h; HKEY
0x180022756  lea     r8, aAlwaysallowloc; "AlwaysAllowLocalSystem"
0x18002275d  mov     [rsp+38h+var_18], rax; int *
0x180022762  lea     rdx, aSoftwareMicros_2; "Software\\Microsoft\\Windows\\CurrentVe"...
0x180022769  call    ?SHRegGetBOOLWithREGSAM@@YAJPEAUHKEY__@@PEBG1KPEAH@Z; SHRegGetBOOLWithREGSAM(HKEY__ *,ushort const *,ushort const *,ulong,int *)
0x18002276e  test    eax, eax
0x180022770  js      short loc_18002277D
0x180022772  cmp     [rsp+38h+arg_10], 0
0x180022777  jz      short loc_18002277D
0x180022779  xor     eax, eax
0x18002277b  jmp     short loc_180022782
0x18002277d  mov     eax, 1
0x180022782  add     rsp, 38h
0x180022786  retn
```
