# tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>::Release(void)

- ea: `0x180075840`
- end: `0x180075878`
- name: `?Release@?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180073df0`
- `0x180074028`
- `0x180077928`

## callees

- `0x180073e78`
- `0x180075840`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075865`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x180075865`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>::~merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180075840  mov     [rsp+arg_0], rbx
0x180075845  push    rdi
0x180075846  sub     rsp, 20h
0x18007584a  mov     rdi, rcx
0x18007584d  or      ebx, 0FFFFFFFFh
0x180075850  lock xadd [rcx+118h], ebx
0x180075858  sub     ebx, 1
0x18007585b  jnz     short loc_18007586B
0x18007585d  call    ??1?$merged_data@U_tip_FluencyDictionaryUpdate@SpellerTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>::~merged_data<SpellerTip::_tip_FluencyDictionaryUpdate,SpellerTip::_tip_FluencyDictionaryUpdate>(void)
0x180075862  mov     rcx, rdi; pv
0x180075865  call    cs:__imp_CoTaskMemFree
0x18007586b  mov     eax, ebx
0x18007586d  mov     rbx, [rsp+28h+arg_0]
0x180075872  add     rsp, 20h
0x180075876  pop     rdi
0x180075877  retn
```
