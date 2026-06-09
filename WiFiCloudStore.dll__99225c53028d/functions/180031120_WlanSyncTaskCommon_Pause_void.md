# WlanSyncTaskCommon::Pause(void)

- ea: `0x180031120`
- end: `0x18003114a`
- name: `?Pause@WlanSyncTaskCommon@@UEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(WlanSyncTaskCommon *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002477c`

## string_xrefs

- `0x180031129`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskCommon::Pause(WlanSyncTaskCommon *this)
{
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x178,
    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
    (const char *)0x80004001LL,
    v2);
  return 2147500033LL;
}

```

## disassembly

```asm
0x180031120  sub     rsp, 28h
0x180031124  mov     rcx, [rsp+28h]; this
0x180031129  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180031130  mov     r9d, 80004001h; char *
0x180031136  mov     edx, 178h; void *
0x18003113b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031140  mov     eax, 80004001h
0x180031145  add     rsp, 28h
0x180031149  retn
```
