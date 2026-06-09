# WlanSyncTaskCommon::Resume(void)

- ea: `0x180031640`
- end: `0x18003166a`
- name: `?Resume@WlanSyncTaskCommon@@UEAAJXZ`
- size: `42`
- prototype: `__int64 __fastcall(WlanSyncTaskCommon *__hidden this)`
- caller_count: `0`
- callee_count: `1`
- tags: `service_task, broker_com_uri`

## callees

- `0x18002477c`

## string_xrefs

- `0x180031649`: `onecoreuap\net\wlan\cloudstore\provider\lib\wlansynctaskcommon.cpp`

## pseudocode

```c
__int64 __fastcall WlanSyncTaskCommon::Resume(WlanSyncTaskCommon *this)
{
  int v2; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]

  wil::details::in1diag3::Return_Hr(
    retaddr,
    (void *)0x17D,
    (unsigned int)"onecoreuap\\net\\wlan\\cloudstore\\provider\\lib\\wlansynctaskcommon.cpp",
    (const char *)0x80004001LL,
    v2);
  return 2147500033LL;
}

```

## disassembly

```asm
0x180031640  sub     rsp, 28h
0x180031644  mov     rcx, [rsp+28h]; this
0x180031649  lea     r8, aOnecoreuapNetW_3; "onecoreuap\\net\\wlan\\cloudstore\\prov"...
0x180031650  mov     r9d, 80004001h; char *
0x180031656  mov     edx, 17Dh; void *
0x18003165b  call    ?Return_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Return_Hr(void *,uint,char const *,long)
0x180031660  mov     eax, 80004001h
0x180031665  add     rsp, 28h
0x180031669  retn
```
