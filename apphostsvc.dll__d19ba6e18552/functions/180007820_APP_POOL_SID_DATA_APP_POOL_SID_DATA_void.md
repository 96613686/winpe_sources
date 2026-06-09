# APP_POOL_SID_DATA::APP_POOL_SID_DATA(void)

- ea: `0x180007820`
- end: `0x180007840`
- name: `??0APP_POOL_SID_DATA@@QEAA@XZ`
- size: `32`
- prototype: `APP_POOL_SID_DATA *__fastcall(APP_POOL_SID_DATA *__hidden this)`
- caller_count: `0`
- callee_count: `0`
- tags: `authz_impersonation`

## import_xrefs

- `iisutil!??0STRU@@QEAA@XZ` at `0x180007829`
- `iisutil!??0STRU@@QEAA@XZ` at `0x180007829`

## pseudocode

```c
APP_POOL_SID_DATA *__fastcall APP_POOL_SID_DATA::APP_POOL_SID_DATA(APP_POOL_SID_DATA *this)
{
  APP_POOL_SID_DATA *result; // rax

  STRU::STRU(this);
  result = this;
  *((_QWORD *)this + 7) = 0;
  return result;
}

```

## disassembly

```asm
0x180007820  push    rbx
0x180007822  sub     rsp, 20h
0x180007826  mov     rbx, rcx
0x180007829  call    cs:__imp_??0STRU@@QEAA@XZ; STRU::STRU(void)
0x18000782f  mov     rax, rbx
0x180007832  mov     qword ptr [rbx+38h], 0
0x18000783a  add     rsp, 20h
0x18000783e  pop     rbx
0x18000783f  retn
```
