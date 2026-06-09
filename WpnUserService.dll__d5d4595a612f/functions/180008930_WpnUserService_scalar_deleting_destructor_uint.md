# WpnUserService::`scalar deleting destructor'(uint)

- ea: `0x180008930`
- end: `0x180008964`
- name: `??_GWpnUserService@@UEAAPEAXI@Z`
- size: `52`
- prototype: `WpnUserService *__fastcall(WpnUserService *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180002f90`
- `0x180008654`
- `0x180008930`

## pseudocode

```c
WpnUserService *__fastcall WpnUserService::`scalar deleting destructor'(WpnUserService *this, char a2)
{
  WpnUserService::~WpnUserService(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180008930  mov     [rsp+arg_0], rbx
0x180008935  push    rdi
0x180008936  sub     rsp, 20h
0x18000893a  mov     ebx, edx
0x18000893c  mov     rdi, rcx
0x18000893f  call    ??1WpnUserService@@UEAA@XZ; WpnUserService::~WpnUserService(void)
0x180008944  test    bl, 1
0x180008947  jz      short loc_180008956
0x180008949  mov     edx, 0F0h; unsigned __int64
0x18000894e  mov     rcx, rdi; void *
0x180008951  call    ??3@YAXPEAX_K@Z; operator delete(void *,unsigned __int64)
0x180008956  mov     rbx, [rsp+28h+arg_0]
0x18000895b  mov     rax, rdi
0x18000895e  add     rsp, 20h
0x180008962  pop     rdi
0x180008963  retn
```
