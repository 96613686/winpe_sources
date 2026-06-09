# Container::Manager::Agent::Core::_anonymous_namespace_::CrmSystemLowUsageWindowClosedReasonCallback

- ea: `0x1800167d0`
- end: `0x180016859`
- name: `Container::Manager::Agent::Core::_anonymous_namespace_::CrmSystemLowUsageWindowClosedReasonCallback`
- size: `137`
- prototype: ``
- caller_count: `0`
- callee_count: `2`
- tags: `service_task`

## callees

- `0x18000a6e0`
- `0x1800167d0`

## import_xrefs

- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180016815`
- `api-ms-win-core-synch-l1-2-0!WakeByAddressAll` at `0x180016815`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityQueryWindowClosedReasons` at `0x1800167f5`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityQueryWindowClosedReasons` at `0x1800167f5`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFreeWindowClosedReasons` at `0x180016846`
- `ext-ms-win-resourcemanager-crm-l1-2-0!CrmActivityFreeWindowClosedReasons` at `0x180016846`

## string_xrefs

- `0x180016828`: `onecore\base\gendrv\silos\clem\agent\core\lib\core.cpp`

## pseudocode

```c
void __fastcall Container::Manager::Agent::Core::_anonymous_namespace_::CrmSystemLowUsageWindowClosedReasonCallback(
        __int64 a1,
        __int64 a2,
        _DWORD *a3)
{
  int v4; // eax
  int v5; // [rsp+20h] [rbp-8h]
  wil::details::in1diag3 *retaddr; // [rsp+28h] [rbp+0h]
  int v7; // [rsp+40h] [rbp+18h] BYREF
  __int64 v8; // [rsp+48h] [rbp+20h] BYREF

  v7 = 0;
  v8 = 0;
  v4 = CrmActivityQueryWindowClosedReasons(a2, &v8, &v7);
  if ( v4 < 0 )
  {
    wil::details::in1diag3::Log_NtStatus(
      retaddr,
      (void *)0xC8,
      (unsigned int)"onecore\\base\\gendrv\\silos\\clem\\agent\\core\\lib\\core.cpp",
      (const char *)(unsigned int)v4,
      v5);
  }
  else if ( !v7 )
  {
    *a3 = 1;
    WakeByAddressAll(a3);
  }
  if ( v8 )
    CrmActivityFreeWindowClosedReasons();
}

```

## disassembly

```asm
0x1800167d0  mov     rax, rsp
0x1800167d3  push    rbx; int
0x1800167d4  sub     rsp, 20h
0x1800167d8  mov     rbx, r8
0x1800167db  mov     dword ptr [rax+18h], 0
0x1800167e2  mov     rcx, rdx
0x1800167e5  mov     qword ptr [rax+20h], 0
0x1800167ed  lea     r8, [rax+18h]
0x1800167f1  lea     rdx, [rax+20h]
0x1800167f5  call    cs:__imp_CrmActivityQueryWindowClosedReasons
0x1800167fc  nop     dword ptr [rax+rax+00h]
0x180016801  test    eax, eax
0x180016803  js      short loc_180016823
0x180016805  cmp     [rsp+28h+arg_10], 0
0x18001680a  jnz     short loc_18001683C
0x18001680c  mov     rcx, rbx; Address
0x18001680f  mov     dword ptr [rbx], 1
0x180016815  call    cs:__imp_WakeByAddressAll
0x18001681c  nop     dword ptr [rax+rax+00h]
0x180016821  jmp     short loc_18001683C
0x180016823  mov     rcx, [rsp+28h]; this
0x180016828  lea     r8, aOnecoreBaseGen_8; "onecore\\base\\gendrv\\silos\\clem\\age"...
0x18001682f  mov     r9d, eax; char *
0x180016832  mov     edx, 0C8h; void *
0x180016837  call    ?Log_NtStatus@in1diag3@details@wil@@YAJPEAXIPEBDJ@Z; wil::details::in1diag3::Log_NtStatus(void *,uint,char const *,long)
0x18001683c  mov     rcx, [rsp+28h+arg_18]
0x180016841  test    rcx, rcx
0x180016844  jz      short loc_180016852
0x180016846  call    cs:__imp_CrmActivityFreeWindowClosedReasons
0x18001684d  nop     dword ptr [rax+rax+00h]
0x180016852  add     rsp, 20h
0x180016856  pop     rbx
0x180016857  retn
```
