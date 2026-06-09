# KeepTaskRunning(void)

- ea: `0x1400076b8`
- end: `0x140007715`
- name: `?KeepTaskRunning@@YA_NXZ`
- size: `93`
- prototype: `bool(void)`
- caller_count: `2`
- callee_count: `0`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000a628`
- `0x14000c7b0`

## import_xrefs

- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140007702`
- `api-ms-win-core-registry-l1-1-0!RegGetValueW` at `0x140007702`

## string_xrefs

- `0x1400076cf`: `KeepTaskUp`
- `0x1400076e6`: `Software\Microsoft\WcmSvc\WiFiNetworkManager\Config`

## pseudocode

```c
bool KeepTaskRunning(void)
{
  int v1; // [rsp+50h] [rbp+8h] BYREF
  DWORD v2; // [rsp+58h] [rbp+10h] BYREF

  v1 = 0;
  v2 = 4;
  RegGetValueW(
    HKEY_LOCAL_MACHINE,
    L"Software\\Microsoft\\WcmSvc\\WiFiNetworkManager\\Config",
    L"KeepTaskUp",
    0x10u,
    0,
    &v1,
    &v2);
  return v1 == 1;
}

```

## disassembly

```asm
0x1400076b8  mov     r11, rsp
0x1400076bb  sub     rsp, 48h
0x1400076bf  lea     rax, [r11+10h]
0x1400076c3  mov     [rsp+48h+arg_0], 0
0x1400076cb  mov     [r11-18h], rax
0x1400076cf  lea     r8, Value; "KeepTaskUp"
0x1400076d6  lea     rax, [r11+8]
0x1400076da  mov     [rsp+48h+arg_8], 4
0x1400076e2  mov     [r11-20h], rax
0x1400076e6  lea     rdx, SubKey; "Software\\Microsoft\\WcmSvc\\WiFiNetwor"...
0x1400076ed  mov     r9d, 10h; dwFlags
0x1400076f3  mov     qword ptr [r11-28h], 0
0x1400076fb  mov     rcx, 0FFFFFFFF80000002h; hkey
0x140007702  call    cs:__imp_RegGetValueW
0x140007708  cmp     [rsp+48h+arg_0], 1
0x14000770d  setz    al
0x140007710  add     rsp, 48h
0x140007714  retn
```
