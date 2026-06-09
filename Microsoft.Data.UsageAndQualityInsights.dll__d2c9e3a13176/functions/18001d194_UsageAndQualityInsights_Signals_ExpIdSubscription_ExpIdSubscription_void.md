# UsageAndQualityInsights::Signals::ExpIdSubscription::ExpIdSubscription(void)

- ea: `0x18001d194`
- end: `0x18001d209`
- name: `??0ExpIdSubscription@Signals@UsageAndQualityInsights@@QEAA@XZ`
- size: `117`
- prototype: `UsageAndQualityInsights::Signals::ExpIdSubscription *__fastcall(UsageAndQualityInsights::Signals::ExpIdSubscription *this)`
- caller_count: `1`
- callee_count: `2`
- tags: `authz_impersonation, service_task, broker_com_uri`

## callers

- `0x18001ab5c`

## callees

- `0x180016628`
- `0x18001d194`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d1dc`
- `api-ms-win-core-com-l1-1-0!CoCreateInstance` at `0x18001d1dc`

## string_xrefs

- `0x18001d1f7`: `onecore\base\usageandqualityinsights\service\lib\signals\expidsubscription.cpp`

## pseudocode

```c
UsageAndQualityInsights::Signals::ExpIdSubscription *__fastcall UsageAndQualityInsights::Signals::ExpIdSubscription::ExpIdSubscription(
        UsageAndQualityInsights::Signals::ExpIdSubscription *this)
{
  HRESULT Instance; // eax
  int ppv; // [rsp+20h] [rbp-18h]
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  *(_QWORD *)this = 0;
  *((_QWORD *)this + 1) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_QWORD *)this + 2) = 0;
  Instance = CoCreateInstance(
               &CLSID_FlightClientAPI,
               0,
               1u,
               &GUID_79588f37_5be1_4a35_b23d_29832257cada,
               (LPVOID *)this + 2);
  if ( Instance < 0 )
    wil::details::in1diag3::Throw_Hr(
      retaddr,
      (void *)0x14,
      (unsigned int)"onecore\\base\\usageandqualityinsights\\service\\lib\\signals\\expidsubscription.cpp",
      (const char *)(unsigned int)Instance,
      ppv);
  return this;
}

```

## disassembly

```asm
0x18001d194  mov     [rsp+arg_0], rcx
0x18001d199  push    rbx
0x18001d19a  sub     rsp, 30h
0x18001d19e  mov     rbx, rcx
0x18001d1a1  mov     qword ptr [rcx], 0
0x18001d1a8  mov     qword ptr [rcx+8], 0
0x18001d1b0  lea     rax, [rcx+10h]
0x18001d1b4  mov     qword ptr [rcx+18h], 0
0x18001d1bc  mov     qword ptr [rax], 0
0x18001d1c3  mov     qword ptr [rsp+38h+ppv], rax; int
0x18001d1c8  lea     r9, _GUID_79588f37_5be1_4a35_b23d_29832257cada; riid
0x18001d1cf  xor     edx, edx; pUnkOuter
0x18001d1d1  lea     r8d, [rdx+1]; dwClsContext
0x18001d1d5  lea     rcx, CLSID_FlightClientAPI; rclsid
0x18001d1dc  call    cs:__imp_CoCreateInstance
0x18001d1e2  mov     rcx, [rsp+38h]; this
0x18001d1e7  test    eax, eax
0x18001d1e9  js      short loc_18001D1F4
0x18001d1eb  mov     rax, rbx
0x18001d1ee  add     rsp, 30h
0x18001d1f2  pop     rbx
0x18001d1f3  retn
0x18001d1f4  mov     r9d, eax; char *
0x18001d1f7  lea     r8, aOnecoreBaseUsa_9; "onecore\\base\\usageandqualityinsights"...
0x18001d1fe  mov     edx, 14h; void *
0x18001d203  call    ?Throw_Hr@in1diag3@details@wil@@YAXPEAXIPEBDJ@Z; wil::details::in1diag3::Throw_Hr(void *,uint,char const *,long)
```
