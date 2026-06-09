# AppHostRawConfigNavigator::`vector deleting destructor'(uint)

- ea: `0x180008fe0`
- end: `0x18000900f`
- name: `??_EAppHostRawConfigNavigator@@UEAAPEAXI@Z`
- size: `47`
- prototype: `void *__fastcall(AppHostRawConfigNavigator *__hidden this, unsigned int)`
- caller_count: `1`
- callee_count: `3`
- tags: `file_ops, registry_config`

## callers

- `0x180008fd0`

## callees

- `0x1800011d4`
- `0x180008f80`
- `0x180008fe0`

## pseudocode

```c
AppHostRawConfigNavigator *__fastcall AppHostRawConfigNavigator::`vector deleting destructor'(
        AppHostRawConfigNavigator *this,
        char a2)
{
  AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::~AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>();
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008fe0  mov     [rsp+arg_0], rbx
0x180008fe5  push    rdi
0x180008fe6  sub     rsp, 20h
0x180008fea  mov     ebx, edx
0x180008fec  mov     rdi, rcx
0x180008fef  call    ??1?$AppHostNavigatorTemplate@VAppHostRawConfigNavigator@@UIAppHostRawConfigNavigator@@VRawConfigTree@@@@UEAA@XZ; AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>::~AppHostNavigatorTemplate<AppHostRawConfigNavigator,IAppHostRawConfigNavigator,RawConfigTree>(void)
0x180008ff4  test    bl, 1
0x180008ff7  jz      short loc_180009001
0x180008ff9  mov     rcx, rdi; Block
0x180008ffc  call    ??3@YAXPEAX@Z; operator delete(void *)
0x180009001  mov     rbx, [rsp+28h+arg_0]
0x180009006  mov     rax, rdi
0x180009009  add     rsp, 20h
0x18000900d  pop     rdi
0x18000900e  retn
```
