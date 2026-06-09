# AutoTimeUpdate::AutoTimeUpdate(std::shared_ptr<Settings> const &)

- ea: `0x18000c300`
- end: `0x18000c37b`
- name: `??0AutoTimeUpdate@@AEAA@AEBV?$shared_ptr@VSettings@@@std@@@Z`
- size: `123`
- prototype: `_DWORD *__fastcall(_DWORD *)`
- caller_count: `1`
- callee_count: `4`
- tags: `registry_config, installer_update`

## callers

- `0x18000c3c8`

## callees

- `0x180001270`
- `0x1800012f0`
- `0x180004e68`
- `0x18000c300`

## pseudocode

```c
_DWORD *__fastcall AutoTimeUpdate::AutoTimeUpdate(_DWORD *a1)
{
  *a1 = 2012;
  std::shared_ptr<Settings>::shared_ptr<Settings>(a1 + 2);
  if ( (unsigned int)dword_18001C010 > 4 && (unsigned __int8)tlgKeywordOn(&dword_18001C010, 256) )
    _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),&long _tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,unsigned int,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(
      (__int64)&dword_18001C010,
      (__int64)&word_180016C2E,
      0);
  return a1;
}

```

## disassembly

```asm
0x18000c300  push    rbx
0x18000c302  sub     rsp, 30h
0x18000c306  mov     dword ptr [rcx], 7DCh
0x18000c30c  mov     rbx, rcx
0x18000c30f  add     rcx, 8
0x18000c313  call    ??0?$shared_ptr@VSettings@@@std@@QEAA@AEBV01@@Z; std::shared_ptr<Settings>::shared_ptr<Settings>(std::shared_ptr<Settings> const &)
0x18000c318  mov     edx, cs:dword_18001C010
0x18000c31e  cmp     edx, 4
0x18000c321  jbe     short loc_18000C372
0x18000c323  mov     edx, 100h
0x18000c328  lea     rcx, dword_18001C010
0x18000c32f  call    _tlgKeywordOn
0x18000c334  test    al, al
0x18000c336  jz      short loc_18000C372
0x18000c338  mov     eax, [rbx]
0x18000c33a  lea     rcx, dword_18001C010
0x18000c341  mov     [rsp+38h+arg_0], eax
0x18000c345  xor     r8d, r8d
0x18000c348  mov     rax, [rbx+8]
0x18000c34c  mov     edx, [rax]
0x18000c34e  lea     rax, [rsp+38h+arg_0]
0x18000c353  mov     [rsp+38h+var_10], rax
0x18000c358  lea     rax, [rsp+38h+arg_10]
0x18000c35d  mov     [rsp+38h+arg_10], edx
0x18000c361  lea     rdx, word_180016C2E
0x18000c368  mov     [rsp+38h+var_18], rax
0x18000c36d  call    ??$Write@U?$_tlgWrapperByVal@$03@@U1@@?$_tlgWriteTemplate@$$A6AJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2IPEAU_EVENT_DATA_DESCRIPTOR@@@Z$1?_tlgWriteTransfer_EventWriteTransfer@@YAJ0122I3@ZPEBU2@PEBU2@@@SAJPEBU_tlgProvider_t@@PEBXPEBU_GUID@@2AEBU?$_tlgWrapperByVal@$03@@3@Z; _tlgWriteTemplate<long (_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),&_tlgWriteTransfer_EventWriteTransfer(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,uint,_EVENT_DATA_DESCRIPTOR *),_GUID const *,_GUID const *>::Write<_tlgWrapperByVal<4>,_tlgWrapperByVal<4>>(_tlgProvider_t const *,void const *,_GUID const *,_GUID const *,_tlgWrapperByVal<4> const &,_tlgWrapperByVal<4> const &)
0x18000c372  mov     rax, rbx
0x18000c375  add     rsp, 30h
0x18000c379  pop     rbx
0x18000c37a  retn
```
