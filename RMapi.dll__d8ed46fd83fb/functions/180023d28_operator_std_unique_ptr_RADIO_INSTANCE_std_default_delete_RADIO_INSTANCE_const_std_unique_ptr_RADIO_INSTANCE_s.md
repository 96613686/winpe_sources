# operator<(std::unique_ptr<RADIO_INSTANCE,std::default_delete<RADIO_INSTANCE>> const &,std::unique_ptr<RADIO_INSTANCE,std::default_delete<RADIO_INSTANCE>> const &)

- ea: `0x180023d28`
- end: `0x180023dc3`
- name: `??M@YA_NAEBV?$unique_ptr@URADIO_INSTANCE@@U?$default_delete@URADIO_INSTANCE@@@std@@@std@@0@Z`
- size: `155`
- prototype: ``
- caller_count: `4`
- callee_count: `6`
- tags: `broker_com_uri`

## callers

- `0x18000a150`
- `0x18000a358`
- `0x18001acd4`
- `0x18001ae30`

## callees

- `0x180022b3c`
- `0x180023c90`
- `0x180023d28`
- `0x180023dcc`
- `0x180023e30`
- `0x180023e9c`

## pseudocode

```c
char __fastcall operator<(__int64 a1, _QWORD *a2)
{
  __int64 v5; // rdx
  _QWORD *v6; // rdi
  _QWORD *v7; // rbx
  int MediaManagerPriorityByGuid; // esi
  int v9; // eax

  if ( !(unsigned __int8)wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::__private_IsEnabled(`wil::Feature<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::GetImpl'::`2'::impl) )
    return IsRadioInstanceLessThanWithFeatureDisabled(a1, a2);
  v5 = *a2;
  v6 = (_QWORD *)(*a2 + 72LL);
  v7 = (_QWORD *)(*(_QWORD *)a1 + 72LL);
  if ( *v7 == *v6 && *(_QWORD *)(*(_QWORD *)a1 + 80LL) == v6[1] )
    return (unsigned __int8)std::operator<=><wchar_t>(*(_QWORD *)a1 + 8LL, v5 + 8) >> 7;
  MediaManagerPriorityByGuid = GetMediaManagerPriorityByGuid(*(_QWORD *)a1 + 72LL);
  v9 = GetMediaManagerPriorityByGuid(v6);
  if ( MediaManagerPriorityByGuid == v9 )
    return CompareGuids(v7, v6);
  else
    return MediaManagerPriorityByGuid < v9;
}

```

## disassembly

```asm
0x180023d28  mov     [rsp+arg_0], rbx
0x180023d2d  mov     [rsp+arg_8], rsi
0x180023d32  push    rdi
0x180023d33  sub     rsp, 20h
0x180023d37  mov     rbx, rdx
0x180023d3a  mov     rsi, rcx
0x180023d3d  lea     rcx, ?impl@?1??GetImpl@?$Feature@U__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance@@@wil@@CAAEAV?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance@@@details@3@XZ@4V453@A; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance> `wil::Feature<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::GetImpl(void)'::`2'::impl
0x180023d44  call    ?__private_IsEnabled@?$FeatureImpl@U__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance@@@details@wil@@QEAA_NXZ; wil::details::FeatureImpl<__WilFeatureTraits_Feature_RadioManager_Fix_NullRadioInstance>::__private_IsEnabled(void)
0x180023d49  test    al, al
0x180023d4b  jnz     short loc_180023D5A
0x180023d4d  mov     rdx, rbx
0x180023d50  mov     rcx, rsi
0x180023d53  call    IsRadioInstanceLessThanWithFeatureDisabled
0x180023d58  jmp     short loc_180023DB3
0x180023d5a  mov     rdx, [rbx]
0x180023d5d  lea     rdi, [rdx+48h]
0x180023d61  mov     rcx, [rsi]
0x180023d64  lea     rbx, [rcx+48h]
0x180023d68  mov     rax, [rbx]
0x180023d6b  cmp     rax, [rdi]
0x180023d6e  jnz     short loc_180023D8C
0x180023d70  mov     rax, [rbx+8]
0x180023d74  cmp     rax, [rdi+8]
0x180023d78  jnz     short loc_180023D8C
0x180023d7a  add     rdx, 8
0x180023d7e  add     rcx, 8
0x180023d82  call    ??$?__M_WU?$char_traits@_W@std@@V?$allocator@_W@1@@std@@YA?AUstrong_ordering@0@AEBV?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@0@0@Z; std::operator<=><wchar_t>(std::wstring const &,std::wstring const &)
0x180023d87  shr     al, 7
0x180023d8a  jmp     short loc_180023DB3
0x180023d8c  mov     rcx, rbx
0x180023d8f  call    GetMediaManagerPriorityByGuid
0x180023d94  mov     esi, eax
0x180023d96  mov     rcx, rdi
0x180023d99  call    GetMediaManagerPriorityByGuid
0x180023d9e  cmp     esi, eax
0x180023da0  jz      short loc_180023DA7
0x180023da2  setl    al
0x180023da5  jmp     short loc_180023DB3
0x180023da7  mov     rdx, rdi
0x180023daa  mov     rcx, rbx
0x180023dad  call    CompareGuids
0x180023db2  nop
0x180023db3  mov     rbx, [rsp+28h+arg_0]
0x180023db8  mov     rsi, [rsp+28h+arg_8]
0x180023dbd  add     rsp, 20h
0x180023dc1  pop     rdi
0x180023dc2  retn
```
