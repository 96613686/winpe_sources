# AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::`scalar deleting destructor'(uint)

- ea: `0x180006a50`
- end: `0x180006a7f`
- name: `??_G?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@UEAAPEAXI@Z`
- size: `47`
- prototype: `__int64 __fastcall(void *Block)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180006a40`

## callees

- `0x1800011d4`
- `0x1800069e4`
- `0x180006a50`

## pseudocode

```c
void *__fastcall AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::`scalar deleting destructor'(
        void *Block,
        char a2)
{
  AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::~AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>();
  if ( (a2 & 1) != 0 )
    operator delete(Block);
  return Block;
}

```

## disassembly

```asm
0x180006a50  mov     [rsp+arg_0], rbx
0x180006a55  push    rdi
0x180006a56  sub     rsp, 20h
0x180006a5a  mov     ebx, edx
0x180006a5c  mov     rdi, rcx
0x180006a5f  call    ??1?$AppHostNavigatorTemplate@VAppHostMergedConfigNavigator@@UIAppHostMergedConfigNavigator@@VMergedConfigTree@@@@UEAA@XZ; AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>::~AppHostNavigatorTemplate<AppHostMergedConfigNavigator,IAppHostMergedConfigNavigator,MergedConfigTree>(void)
0x180006a64  test    bl, 1
0x180006a67  jz      short loc_180006A71
0x180006a69  mov     rcx, rdi; Block
0x180006a6c  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180006a71  mov     rbx, [rsp+28h+arg_0]
0x180006a76  mov     rax, rdi
0x180006a79  add     rsp, 20h
0x180006a7d  pop     rdi
0x180006a7e  retn
```
