# tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::operator->(void)

- ea: `0x18000b5bc`
- end: `0x18000b5f1`
- name: `??C?$tip_test@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@tip2@@QEAA?AV?$test_data_control@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@1@XZ`
- size: `53`
- prototype: `__int64 *__fastcall(__int64, __int64 *)`
- caller_count: `1`
- callee_count: `3`
- tags: `installer_update`

## callers

- `0x18000b6f0`

## callees

- `0x18000b5bc`
- `0x18000d114`
- `0x18000d550`

## pseudocode

```c
__int64 *__fastcall tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::operator->(
        __int64 a1,
        __int64 *a2)
{
  __int64 *v3; // rax
  __int64 v4; // rcx

  v3 = (__int64 *)tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::ensure_data();
  v4 = *v3;
  *a2 = *v3;
  if ( v4 )
    _InterlockedIncrement((volatile signed __int32 *)(v4 + 296));
  tip2::details::shared_data<0,0,0>::begin_update(*a2 + 8);
  return a2;
}

```

## disassembly

```asm
0x18000b5bc  push    rbx
0x18000b5be  sub     rsp, 20h
0x18000b5c2  mov     rbx, rdx
0x18000b5c5  call    ?ensure_data@?$tip_test@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@@tip2@@AEBAAEAV?$com_ptr_t@V?$merged_data@U_tip_HumanPresenceAccessChangedTest@@U1@@details@tip2@@Uerr_returncode_policy@wil@@@wil@@XZ; tip2::tip_test<tip2::details::merged_data<_tip_HumanPresenceAccessChangedTest,_tip_HumanPresenceAccessChangedTest>>::ensure_data(void)
0x18000b5ca  mov     rcx, [rax]
0x18000b5cd  mov     [rbx], rcx
0x18000b5d0  test    rcx, rcx
0x18000b5d3  jz      short loc_18000B5DC
0x18000b5d5  lock inc dword ptr [rcx+128h]
0x18000b5dc  mov     rcx, [rbx]
0x18000b5df  add     rcx, 8
0x18000b5e3  call    ?begin_update@?$shared_data@$0A@$0A@$0A@@details@tip2@@AEAA_NXZ; tip2::details::shared_data<0,0,0>::begin_update(void)
0x18000b5e8  mov     rax, rbx
0x18000b5eb  add     rsp, 20h
0x18000b5ef  pop     rbx
0x18000b5f0  retn
```
