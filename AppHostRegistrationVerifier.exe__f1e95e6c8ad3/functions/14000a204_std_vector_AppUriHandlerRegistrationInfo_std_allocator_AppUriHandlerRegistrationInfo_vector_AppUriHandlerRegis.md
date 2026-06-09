# std::vector<AppUriHandlerRegistrationInfo,std::allocator<AppUriHandlerRegistrationInfo>>::~vector<AppUriHandlerRegistrationInfo,std::allocator<AppUriHandlerRegistrationInfo>>(void)

- ea: `0x14000a204`
- end: `0x14000a24e`
- name: `??1?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@QEAA@XZ`
- size: `74`
- prototype: `void __fastcall(AppUriHandlerRegistrationInfo **)`
- caller_count: `2`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x140011555`
- `0x140011b9f`

## callees

- `0x140003cd8`
- `0x140009294`
- `0x14000a204`

## pseudocode

```c
void __fastcall std::vector<AppUriHandlerRegistrationInfo>::~vector<AppUriHandlerRegistrationInfo>(
        AppUriHandlerRegistrationInfo **a1)
{
  AppUriHandlerRegistrationInfo *v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(v2, a1[1]);
    std::_Deallocate<16>(*a1, (a1[2] - *a1) & 0xFFFFFFFFFFFFFFF0uLL);
    *a1 = 0;
    a1[1] = 0;
    a1[2] = 0;
  }
}

```

## disassembly

```asm
0x14000a204  push    rbx
0x14000a206  sub     rsp, 20h
0x14000a20a  mov     rbx, rcx
0x14000a20d  mov     rcx, [rcx]; this
0x14000a210  test    rcx, rcx
0x14000a213  jz      short loc_14000A248
0x14000a215  mov     rdx, [rbx+8]
0x14000a219  call    ??$_Destroy_range@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@YAXPEAUAppUriHandlerRegistrationInfo@@QEAU1@AEAV?$allocator@UAppUriHandlerRegistrationInfo@@@0@@Z; std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(AppUriHandlerRegistrationInfo *,AppUriHandlerRegistrationInfo * const,std::allocator<AppUriHandlerRegistrationInfo> &)
0x14000a21e  mov     rdx, [rbx+10h]
0x14000a222  sub     rdx, [rbx]
0x14000a225  mov     rcx, [rbx]
0x14000a228  and     rdx, 0FFFFFFFFFFFFFFF0h
0x14000a22c  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000a231  mov     qword ptr [rbx], 0
0x14000a238  mov     qword ptr [rbx+8], 0
0x14000a240  mov     qword ptr [rbx+10h], 0
0x14000a248  add     rsp, 20h
0x14000a24c  pop     rbx
0x14000a24d  retn
```
