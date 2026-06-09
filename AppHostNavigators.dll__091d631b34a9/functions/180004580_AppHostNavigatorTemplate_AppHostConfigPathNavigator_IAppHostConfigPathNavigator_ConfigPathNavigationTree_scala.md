# AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::`scalar deleting destructor'(uint)

- ea: `0x180004580`
- end: `0x1800045af`
- name: `??_G?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180004570`

## callees

- `0x1800011d4`
- `0x180004320`
- `0x180004580`

## pseudocode

```c
void *__fastcall AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::`scalar deleting destructor'(
        void *Block,
        char a2)
{
  AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::~AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180004580  mov     [rsp+arg_0], rbx
0x180004585  push    rdi
0x180004586  sub     rsp, 20h
0x18000458a  mov     ebx, edx
0x18000458c  mov     rdi, rcx
0x18000458f  call    ??1?$AppHostNavigatorTemplate@VAppHostConfigPathNavigator@@UIAppHostConfigPathNavigator@@VConfigPathNavigationTree@@@@UEAA@XZ; AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>::~AppHostNavigatorTemplate<AppHostConfigPathNavigator,IAppHostConfigPathNavigator,ConfigPathNavigationTree>(void)
0x180004594  test    bl, 1
0x180004597  jz      short loc_1800045A1
0x180004599  mov     rcx, rdi; Block
0x18000459c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x1800045a1  mov     rbx, [rsp+28h+arg_0]
0x1800045a6  mov     rax, rdi
0x1800045a9  add     rsp, 20h
0x1800045ad  pop     rdi
0x1800045ae  retn
```
