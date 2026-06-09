# std::vector<AppUriHandlerRegistrationInfo,std::allocator<AppUriHandlerRegistrationInfo>>::_Reallocation_guard::~_Reallocation_guard(void)

- ea: `0x14000a474`
- end: `0x14000a4a8`
- name: `??1_Reallocation_guard@?$vector@UAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@QEAA@XZ`
- size: `52`
- prototype: `void __fastcall(__int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400092ec`

## callees

- `0x140003cd8`
- `0x140009294`
- `0x14000a474`

## pseudocode

```c
void __fastcall std::vector<AppUriHandlerRegistrationInfo>::_Reallocation_guard::~_Reallocation_guard(__int64 a1)
{
  if ( *(_QWORD *)(a1 + 8) )
  {
    std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(
      *(AppUriHandlerRegistrationInfo **)(a1 + 24),
      *(AppUriHandlerRegistrationInfo **)(a1 + 32));
    std::_Deallocate<16>(*(_QWORD **)(a1 + 8), 16LL * *(_QWORD *)(a1 + 16));
  }
}

```

## disassembly

```asm
0x14000a474  push    rbx
0x14000a476  sub     rsp, 20h
0x14000a47a  cmp     qword ptr [rcx+8], 0
0x14000a47f  mov     rbx, rcx
0x14000a482  jz      short loc_14000A4A2
0x14000a484  mov     rdx, [rcx+20h]
0x14000a488  mov     rcx, [rcx+18h]; this
0x14000a48c  call    ??$_Destroy_range@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@YAXPEAUAppUriHandlerRegistrationInfo@@QEAU1@AEAV?$allocator@UAppUriHandlerRegistrationInfo@@@0@@Z; std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(AppUriHandlerRegistrationInfo *,AppUriHandlerRegistrationInfo * const,std::allocator<AppUriHandlerRegistrationInfo> &)
0x14000a491  mov     rdx, [rbx+10h]
0x14000a495  mov     rcx, [rbx+8]
0x14000a499  shl     rdx, 4
0x14000a49d  call    ??$_Deallocate@$0BA@@std@@YAXPEAX_K@Z; std::_Deallocate<16>(void *,unsigned __int64)
0x14000a4a2  add     rsp, 20h
0x14000a4a6  pop     rbx
0x14000a4a7  retn
```
