# tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>::Release(void)

- ea: `0x180075880`
- end: `0x1800758b8`
- name: `?Release@?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@AEAAKXZ`
- size: `56`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, installer_update, broker_com_uri`

## callers

- `0x180073e0c`
- `0x18007405c`
- `0x180077950`

## callees

- `0x180073ea8`
- `0x180075880`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800758a5`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x1800758a5`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 70);
  if ( !v2 )
  {
    tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>::~merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>();
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x180075880  mov     [rsp+arg_0], rbx
0x180075885  push    rdi
0x180075886  sub     rsp, 20h
0x18007588a  mov     rdi, rcx
0x18007588d  or      ebx, 0FFFFFFFFh
0x180075890  lock xadd [rcx+118h], ebx
0x180075898  sub     ebx, 1
0x18007589b  jnz     short loc_1800758AB
0x18007589d  call    ??1?$merged_data@U_tip_SpellerDictionaryUpdate@SpellerTip@@U12@@details@tip2@@QEAA@XZ; tip2::details::merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>::~merged_data<SpellerTip::_tip_SpellerDictionaryUpdate,SpellerTip::_tip_SpellerDictionaryUpdate>(void)
0x1800758a2  mov     rcx, rdi; pv
0x1800758a5  call    cs:__imp_CoTaskMemFree
0x1800758ab  mov     eax, ebx
0x1800758ad  mov     rbx, [rsp+28h+arg_0]
0x1800758b2  add     rsp, 20h
0x1800758b6  pop     rdi
0x1800758b7  retn
```
