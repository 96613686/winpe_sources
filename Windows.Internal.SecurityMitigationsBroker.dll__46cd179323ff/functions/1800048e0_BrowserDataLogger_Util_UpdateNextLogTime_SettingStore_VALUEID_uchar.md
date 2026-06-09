# BrowserDataLogger::Util::UpdateNextLogTime(SettingStore::VALUEID<uchar *>)

- ea: `0x1800048e0`
- end: `0x180004939`
- name: `?UpdateNextLogTime@Util@BrowserDataLogger@@CA_KU?$VALUEID@PEAE@SettingStore@@@Z`
- size: `89`
- prototype: ``
- caller_count: `1`
- callee_count: `1`
- tags: `registry_config, installer_update`

## callers

- `0x18000448c`

## callees

- `0x180004828`

## import_xrefs

- `iertutil!__imp_SetValue` at `0x180004925`
- `iertutil!__imp_SetValue` at `0x180004925`

## pseudocode

```c
unsigned __int64 __fastcall BrowserDataLogger::Util::UpdateNextLogTime(__int64 a1)
{
  unsigned __int64 v2; // rdi
  __int64 v4; // [rsp+48h] [rbp+10h] BYREF

  v2 = BrowserDataLogger::Util::GetCurrentTimeInMs() + 21600000;
  v4 = 10000 * v2;
  SetValue(a1, 2, 5, &v4, 8);
  return v2;
}

```

## disassembly

```asm
0x1800048e0  mov     [rsp+arg_0], rbx
0x1800048e5  push    rdi
0x1800048e6  sub     rsp, 30h
0x1800048ea  mov     rbx, rcx
0x1800048ed  call    ?GetCurrentTimeInMs@Util@BrowserDataLogger@@CA_KXZ; BrowserDataLogger::Util::GetCurrentTimeInMs(void)
0x1800048f2  mov     edx, 2
0x1800048f7  mov     [rsp+38h+var_18], 8
0x1800048ff  lea     r9, [rsp+38h+arg_8]
0x180004904  lea     rdi, [rax+1499700h]
0x18000490b  imul    rcx, rdi, 2710h
0x180004912  lea     r8d, [rdx+3]
0x180004916  mov     dword ptr [rsp+38h+arg_8], ecx
0x18000491a  shr     rcx, 20h
0x18000491e  mov     dword ptr [rsp+38h+arg_8+4], ecx
0x180004922  mov     rcx, rbx
0x180004925  call    cs:__imp_SetValue
0x18000492b  mov     rbx, [rsp+38h+arg_0]
0x180004930  mov     rax, rdi
0x180004933  add     rsp, 30h
0x180004937  pop     rdi
0x180004938  retn
```
