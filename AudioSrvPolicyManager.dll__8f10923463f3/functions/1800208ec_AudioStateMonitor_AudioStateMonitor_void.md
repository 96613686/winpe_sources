# AudioStateMonitor::~AudioStateMonitor(void)

- ea: `0x1800208ec`
- end: `0x180020966`
- name: `??1AudioStateMonitor@@QEAA@XZ`
- size: `122`
- prototype: `void __fastcall(AudioStateMonitor *__hidden this)`
- caller_count: `5`
- callee_count: `2`
- tags: `file_ops, service_task, broker_com_uri`

## callers

- `0x180020784`
- `0x1800207bc`
- `0x18002080c`
- `0x180024594`
- `0x18002bdbc`

## callees

- `0x1800208ec`
- `0x180031e00`

## import_xrefs

- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002094a`
- `api-ms-win-core-com-l1-1-0!CoTaskMemFree` at `0x18002094a`

## pseudocode

```c
void __fastcall AudioStateMonitor::~AudioStateMonitor(AudioStateMonitor *this)
{
  void *v2; // rcx
  void *v3; // rcx
  void *v4; // rcx
  void *v5; // rcx

  v2 = (void *)*((_QWORD *)this + 3);
  *((_QWORD *)this + 3) = 0;
  if ( v2 )
    operator delete(v2, (const struct std::nothrow_t *)4);
  v3 = (void *)*((_QWORD *)this + 2);
  if ( v3 )
    CoTaskMemFree(v3);
  v4 = (void *)*((_QWORD *)this + 1);
  *((_QWORD *)this + 1) = 0;
  if ( v4 )
    operator delete(v4, (const struct std::nothrow_t *)4);
  v5 = *(void **)this;
  *(_QWORD *)this = 0;
  if ( v5 )
    operator delete(v5, (const struct std::nothrow_t *)4);
}

```

## disassembly

```asm
0x1800208ec  mov     [rsp+arg_0], rbx
0x1800208f1  push    rsi
0x1800208f2  sub     rsp, 20h
0x1800208f6  mov     rbx, rcx
0x1800208f9  mov     esi, 4
0x1800208fe  mov     rcx, [rcx+18h]; void *
0x180020902  mov     qword ptr [rbx+18h], 0
0x18002090a  test    rcx, rcx
0x18002090d  jz      short loc_180020916
0x18002090f  mov     edx, esi; struct std::nothrow_t *
0x180020911  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020916  mov     rcx, [rbx+10h]; pv
0x18002091a  test    rcx, rcx
0x18002091d  jnz     short loc_18002094A
0x18002091f  mov     rcx, [rbx+8]; void *
0x180020923  mov     qword ptr [rbx+8], 0
0x18002092b  test    rcx, rcx
0x18002092e  jnz     short loc_180020952
0x180020930  mov     rcx, [rbx]; void *
0x180020933  mov     qword ptr [rbx], 0
0x18002093a  test    rcx, rcx
0x18002093d  jnz     short loc_18002095C
0x18002093f  mov     rbx, [rsp+28h+arg_0]
0x180020944  add     rsp, 20h
0x180020948  pop     rsi
0x180020949  retn
0x18002094a  call    cs:__imp_CoTaskMemFree
0x180020950  jmp     short loc_18002091F
0x180020952  mov     rdx, rsi; struct std::nothrow_t *
0x180020955  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x18002095a  jmp     short loc_180020930
0x18002095c  mov     rdx, rsi; struct std::nothrow_t *
0x18002095f  call    ??3@YAXPEAXAEBUnothrow_t@std@@@Z; operator delete(void *,std::nothrow_t const &)
0x180020964  jmp     short loc_18002093F
```
