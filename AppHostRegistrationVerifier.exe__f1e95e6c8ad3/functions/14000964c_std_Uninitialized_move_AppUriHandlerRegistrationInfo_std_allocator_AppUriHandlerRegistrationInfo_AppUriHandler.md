# std::_Uninitialized_move<AppUriHandlerRegistrationInfo *,std::allocator<AppUriHandlerRegistrationInfo>>(AppUriHandlerRegistrationInfo * const,AppUriHandlerRegistrationInfo * const,AppUriHandlerRegistrationInfo *,std::allocator<AppUriHandlerRegistrationInfo> &)

- ea: `0x14000964c`
- end: `0x14000969e`
- name: `??$_Uninitialized_move@PEAUAppUriHandlerRegistrationInfo@@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@YAPEAUAppUriHandlerRegistrationInfo@@QEAU1@0PEAU1@AEAV?$allocator@UAppUriHandlerRegistrationInfo@@@0@@Z`
- size: `82`
- prototype: `AppUriHandlerRegistrationInfo *__fastcall(__int64, __int64, AppUriHandlerRegistrationInfo *, __int64)`
- caller_count: `1`
- callee_count: `3`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1400092ec`

## callees

- `0x140009294`
- `0x1400092cc`
- `0x14000964c`

## pseudocode

```c
AppUriHandlerRegistrationInfo *__fastcall std::_Uninitialized_move<AppUriHandlerRegistrationInfo *>(
        __int64 a1,
        __int64 a2,
        AppUriHandlerRegistrationInfo *a3,
        __int64 a4)
{
  AppUriHandlerRegistrationInfo *v4; // rbx
  __int64 v5; // r10
  __int64 v6; // r10
  __int64 v7; // r11
  AppUriHandlerRegistrationInfo *v9; // [rsp+20h] [rbp-28h] BYREF
  AppUriHandlerRegistrationInfo *v10; // [rsp+28h] [rbp-20h]
  __int64 v11; // [rsp+30h] [rbp-18h]

  v11 = a4;
  v4 = a3;
  v9 = a3;
  v10 = a3;
  v5 = a1;
  if ( a1 != a2 )
  {
    do
    {
      std::_Uninitialized_backout_al<std::allocator<AppUriHandlerRegistrationInfo>>::_Emplace_back<AppUriHandlerRegistrationInfo>(
        (__int64)&v9,
        v5);
      v5 = v6 + 16;
    }
    while ( v5 != v7 );
    v4 = v10;
  }
  std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(v4, v4);
  return v4;
}

```

## disassembly

```asm
0x14000964c  push    rbx
0x14000964e  sub     rsp, 40h
0x140009652  mov     [rsp+48h+var_18], r9
0x140009657  mov     rbx, r8
0x14000965a  mov     [rsp+48h+var_28], rbx
0x14000965f  mov     r11, rdx
0x140009662  mov     [rsp+48h+var_20], rbx
0x140009667  mov     r10, rcx
0x14000966a  cmp     rcx, rdx
0x14000966d  jz      short loc_14000968A
0x14000966f  mov     rdx, r10
0x140009672  lea     rcx, [rsp+48h+var_28]
0x140009677  call    ??$_Emplace_back@UAppUriHandlerRegistrationInfo@@@?$_Uninitialized_backout_al@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@QEAAX$$QEAUAppUriHandlerRegistrationInfo@@@Z; std::_Uninitialized_backout_al<std::allocator<AppUriHandlerRegistrationInfo>>::_Emplace_back<AppUriHandlerRegistrationInfo>(AppUriHandlerRegistrationInfo &&)
0x14000967c  add     r10, 10h
0x140009680  cmp     r10, r11
0x140009683  jnz     short loc_14000966F
0x140009685  mov     rbx, [rsp+48h+var_20]
0x14000968a  mov     rdx, rbx
0x14000968d  mov     rcx, rbx; this
0x140009690  call    ??$_Destroy_range@V?$allocator@UAppUriHandlerRegistrationInfo@@@std@@@std@@YAXPEAUAppUriHandlerRegistrationInfo@@QEAU1@AEAV?$allocator@UAppUriHandlerRegistrationInfo@@@0@@Z; std::_Destroy_range<std::allocator<AppUriHandlerRegistrationInfo>>(AppUriHandlerRegistrationInfo *,AppUriHandlerRegistrationInfo * const,std::allocator<AppUriHandlerRegistrationInfo> &)
0x140009695  mov     rax, rbx
0x140009698  add     rsp, 40h
0x14000969c  pop     rbx
0x14000969d  retn
```
