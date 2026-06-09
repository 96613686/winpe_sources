# AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::`vector deleting destructor'(uint)

- ea: `0x180002270`
- end: `0x18000229f`
- name: `??_E?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180002260`

## callees

- `0x1800011d4`
- `0x1800020f0`
- `0x180002270`

## pseudocode

```c
void *__fastcall AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::`vector deleting destructor'(
        void *Block,
        char a2)
{
  AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::~AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180002270  mov     [rsp+arg_0], rbx
0x180002275  push    rdi
0x180002276  sub     rsp, 20h
0x18000227a  mov     ebx, edx
0x18000227c  mov     rdi, rcx
0x18000227f  call    ??1?$AppHostNavigatorTemplate@VAppHostConfigLocationsNavigator@@UIAppHostConfigLocationsNavigator@@VConfigLocationsTree@@@@UEAA@XZ; AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>::~AppHostNavigatorTemplate<AppHostConfigLocationsNavigator,IAppHostConfigLocationsNavigator,ConfigLocationsTree>(void)
0x180002284  test    bl, 1
0x180002287  jz      short loc_180002291
0x180002289  mov     rcx, rdi; Block
0x18000228c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180002291  mov     rbx, [rsp+28h+arg_0]
0x180002296  mov     rax, rdi
0x180002299  add     rsp, 20h
0x18000229d  pop     rdi
0x18000229e  retn
```
