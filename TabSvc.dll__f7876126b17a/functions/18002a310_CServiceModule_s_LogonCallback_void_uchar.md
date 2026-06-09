# CServiceModule::s_LogonCallback(void *,uchar)

- ea: `0x18002a310`
- end: `0x18002a36f`
- name: `?s_LogonCallback@CServiceModule@@SAXPEAXE@Z`
- size: `95`
- prototype: `void __stdcall(PVOID, BOOLEAN)`
- caller_count: `0`
- callee_count: `5`
- tags: `file_ops, service_task`

## callees

- `0x180010c30`
- `0x18001bc04`
- `0x180028578`
- `0x180028a24`
- `0x18002a310`

## string_xrefs

- `0x18002a32e`: `drivers\tablet\platform\pen\penservice\penservice.cpp`

## pseudocode

```c
void __fastcall CServiceModule::s_LogonCallback(PVOID a1)
{
  const char *v2; // r9
  wil::details::in1diag3 *retaddr; // [rsp+38h] [rbp+0h]

  if ( (unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_Bugfix_59994706>::GetImpl'::`2'::impl) )
    wil::details::in1diag3::_FailFast_Unexpected(
      retaddr,
      (void *)0x7E4,
      (unsigned int)"drivers\\tablet\\platform\\pen\\penservice\\penservice.cpp",
      v2);
  CServiceModule::AddScmEvent(*((CServiceModule **)a1 + 2), 128, 0, *((_DWORD *)a1 + 2), *(struct _SLIST_ENTRY **)a1);
  operator delete(a1, (const struct std::nothrow_t *)0x18);
}

```

## disassembly

```asm
0x18002a310  push    rbx
0x18002a312  sub     rsp, 30h
0x18002a316  mov     rbx, rcx
0x18002a319  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_Bugfix_59994706@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59994706@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706> `wil::Feature<__WilFeatureTraits_Feature_Bugfix_59994706>::GetImpl(void)'::`2'::impl
0x18002a320  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_Bugfix_59994706@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_Bugfix_59994706>::__private_IsEnabled(void)
0x18002a325  test    al, al
0x18002a327  jz      short loc_18002A340
0x18002a329  mov     rcx, [rsp+38h]; this
0x18002a32e  lea     r8, aDriversTabletP_1; "drivers\\tablet\\platform\\pen\\penserv"...
0x18002a335  mov     edx, 7E4h; void *
0x18002a33a  call    ?_FailFast_Unexpected@in1diag3@details@wil@@YAXPEAXIPEBD@Z; wil::details::in1diag3::_FailFast_Unexpected(void *,uint,char const *)
0x18002a340  mov     rax, [rbx]
0x18002a343  xor     r8d, r8d; unsigned int
0x18002a346  mov     r9d, [rbx+8]; unsigned int
0x18002a34a  mov     edx, 80h; unsigned int
0x18002a34f  mov     rcx, [rbx+10h]; this
0x18002a353  mov     [rsp+38h+var_18], rax; void *
0x18002a358  call    ?AddScmEvent@CServiceModule@@QEAAJKKKPEAX@Z; CServiceModule::AddScmEvent(ulong,ulong,ulong,void *)
0x18002a35d  mov     edx, 18h; struct std::nothrow_t *
0x18002a362  mov     rcx, rbx; void *
0x18002a365  add     rsp, 30h
0x18002a369  pop     rbx
0x18002a36a  jmp     ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
```
