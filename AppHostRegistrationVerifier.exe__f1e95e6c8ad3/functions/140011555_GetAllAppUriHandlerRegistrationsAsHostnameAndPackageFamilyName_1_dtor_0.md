# _GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$0

- ea: `0x140011555`
- end: `0x140011584`
- name: `_GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor$0`
- size: `47`
- prototype: `void __fastcall(__int64, __int64)`
- caller_count: `0`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callees

- `0x14000a204`
- `0x140011555`

## pseudocode

```c
void __fastcall GetAllAppUriHandlerRegistrationsAsHostnameAndPackageFamilyName_::_1_::dtor_0(__int64 a1, __int64 a2)
{
  if ( (*(_DWORD *)(a2 + 152) & 1) != 0 )
  {
    *(_DWORD *)(a2 + 152) &= ~1u;
    std::vector<AppUriHandlerRegistrationInfo>::~vector<AppUriHandlerRegistrationInfo>(*(AppUriHandlerRegistrationInfo ***)(a2 + 288));
  }
}

```

## disassembly

```asm
0x140011555  push    rbp
0x140011557  sub     rsp, 20h
0x14001155b  mov     rbp, rdx
0x14001155e  mov     eax, [rbp+98h]
0x140011564  and     eax, 1
0x140011567  test    eax, eax
0x140011569  jz      short loc_14001157E
0x14001156b  and     dword ptr [rbp+98h], 0FFFFFFFEh
0x140011572  mov     rcx, [rbp+120h]
0x140011579  call    ??1?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@QEAA@XZ; std::vector<AppUriHandlerRegistrationInfo>::~vector<AppUriHandlerRegistrationInfo>(void)
0x14001157e  add     rsp, 20h
0x140011582  pop     rbp
0x140011583  retn
```
