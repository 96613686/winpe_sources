# TaskHelper::~TaskHelper(void)

- ea: `0x140006150`
- end: `0x14000618a`
- name: `??1TaskHelper@@QEAA@XZ`
- size: `58`
- prototype: `void __fastcall(TaskHelper *__hidden this)`
- caller_count: `8`
- callee_count: `1`
- tags: `registry_config, service_task, broker_com_uri`

## callers

- `0x14000f2a4`
- `0x1400100e0`
- `0x140010ac0`
- `0x140010ce8`
- `0x140018ab0`
- `0x140018c33`
- `0x140018c69`
- `0x140018cb1`

## callees

- `0x140005cac`

## pseudocode

```c
void __fastcall TaskHelper::~TaskHelper(TaskHelper *this)
{
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)this + 4);
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)this + 3);
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)this + 2);
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)this + 1);
  wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>((__int64 *)this);
}

```

## disassembly

```asm
0x140006150  push    rbx
0x140006152  sub     rsp, 20h
0x140006156  mov     rbx, rcx
0x140006159  add     rcx, 20h ; ' '
0x14000615d  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140006162  lea     rcx, [rbx+18h]
0x140006166  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x14000616b  lea     rcx, [rbx+10h]
0x14000616f  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x140006174  lea     rcx, [rbx+8]
0x140006178  call    ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
0x14000617d  mov     rcx, rbx
0x140006180  add     rsp, 20h
0x140006184  pop     rbx
0x140006185  jmp     ??1?$com_ptr_t@UIPrincipal@@Uerr_exception_policy@wil@@@wil@@QEAA@XZ; wil::com_ptr_t<IPrincipal,wil::err_exception_policy>::~com_ptr_t<IPrincipal,wil::err_exception_policy>(void)
```
