# _dynamic_initializer_for__c_modelPackageMarker__

- ea: `0x180002100`
- end: `0x18000213a`
- name: `_dynamic_initializer_for__c_modelPackageMarker__`
- size: `58`
- prototype: `int()`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x180012f10`
- `0x180018598`

## string_xrefs

- `0x180002104`: `com.microsoft.windows.workload.models`

## pseudocode

```c
int dynamic_initializer_for__c_modelPackageMarker__()
{
  _QWORD v1[3]; // [rsp+20h] [rbp-18h] BYREF

  v1[1] = 37;
  v1[0] = L"com.microsoft.windows.workload.models";
  winrt::hstring::hstring(&qword_18002E880, v1);
  return atexit((void (__cdecl *)())dynamic_atexit_destructor_for__c_modelPackageMarker__);
}

```

## disassembly

```asm
0x180002100  sub     rsp, 38h
0x180002104  lea     rax, aComMicrosoftWi; "com.microsoft.windows.workload.models"
0x18000210b  mov     [rsp+38h+var_10], 25h ; '%'
0x180002114  lea     rdx, [rsp+38h+var_18]
0x180002119  mov     [rsp+38h+var_18], rax
0x18000211e  lea     rcx, qword_18002E880
0x180002125  call    ??0hstring@winrt@@QEAA@AEBV?$basic_string_view@_WU?$char_traits@_W@std@@@std@@@Z; winrt::hstring::hstring(std::wstring_view const &)
0x18000212a  lea     rcx, _dynamic_atexit_destructor_for__c_modelPackageMarker__
0x180002131  add     rsp, 38h
0x180002135  jmp     atexit
```
