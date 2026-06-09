# tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(void)

- ea: `0x18001a180`
- end: `0x18001a1fc`
- name: `?Release@?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@AEAAKXZ`
- size: `124`
- prototype: `__int64 __fastcall(LPVOID pv)`
- caller_count: `7`
- callee_count: `4`
- tags: `service_task, broker_com_uri`

## callers

- `0x1800193c0`
- `0x1800193d0`
- `0x180019c40`
- `0x180052c90`
- `0x180053610`
- `0x1800583b0`
- `0x18005bc90`

## callees

- `0x180008600`
- `0x180010910`
- `0x180010e80`
- `0x18001a180`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1e4`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18001a1e4`

## pseudocode

```c
__int64 __fastcall tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::Release(
        volatile signed __int32 *pv)
{
  unsigned __int32 v2; // ebx

  v2 = _InterlockedDecrement(pv + 74);
  if ( !v2 )
  {
    *(_QWORD *)pv = &tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::`vftable';
    if ( *((_QWORD *)pv + 30) && (pv[7] & 1) == 0 )
      tip2::details::shared_data<0,0,0>::complete_helper((__int64)(pv + 2), 4u);
    std::wstring::_Tidy_deallocate((__int64)(pv + 66));
    tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>((__int64)(pv + 2));
    CoTaskMemFree((LPVOID)pv);
  }
  return v2;
}

```

## disassembly

```asm
0x18001a180  mov     [rsp+arg_8], rbx
0x18001a185  push    rdi
0x18001a186  sub     rsp, 20h
0x18001a18a  mov     rdi, rcx
0x18001a18d  mov     ebx, 0FFFFFFFFh
0x18001a192  lock xadd [rcx+128h], ebx
0x18001a19a  sub     ebx, 1
0x18001a19d  jnz     short loc_18001A1EF
0x18001a19f  lea     rax, ??_7?$merged_data@U_tip_SessionWrapperCreateAsyncTest@AIFabricTipTest@@U12@@details@tip2@@6B@; const tip2::details::merged_data<AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest,AIFabricTipTest::_tip_SessionWrapperCreateAsyncTest>::`vftable'
0x18001a1a6  mov     [rsp+28h+arg_0], rsi
0x18001a1ab  mov     [rcx], rax
0x18001a1ae  cmp     qword ptr [rcx+0F0h], 0
0x18001a1b6  jz      short loc_18001A1CC
0x18001a1b8  test    byte ptr [rcx+1Ch], 1
0x18001a1bc  jnz     short loc_18001A1CC
0x18001a1be  mov     edx, 4
0x18001a1c3  add     rcx, 8
0x18001a1c7  call    ?complete_helper@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAAXW4TestQueryOptions@@@Z; tip2::details::shared_data<0,0,0>::complete_helper(TestQueryOptions)
0x18001a1cc  lea     rcx, [rdi+108h]
0x18001a1d3  call    ?_Tidy_deallocate@?$basic_string@_WU?$char_traits@_W@std@@V?$allocator@_W@2@@std@@AEAAXXZ; std::wstring::_Tidy_deallocate(void)
0x18001a1d8  lea     rcx, [rdi+8]
0x18001a1dc  call    ??1?$shared_data@$0A@$0A@$0A@@details@tip2@@QEAA@XZ; tip2::details::shared_data<0,0,0>::~shared_data<0,0,0>(void)
0x18001a1e1  mov     rcx, rdi; pv
0x18001a1e4  call    cs:__imp_CoTaskMemFree
0x18001a1ea  mov     rsi, [rsp+28h+arg_0]
0x18001a1ef  mov     eax, ebx
0x18001a1f1  mov     rbx, [rsp+28h+arg_8]
0x18001a1f6  add     rsp, 20h
0x18001a1fa  pop     rdi
0x18001a1fb  retn
```
