# wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(CJobCompleteNotifier *)

- ea: `0x14002b148`
- end: `0x14002b165`
- name: `?reset@?$unique_ptr@VCJobCompleteNotifier@@U?$default_delete@VCJobCompleteNotifier@@@wistd@@@wistd@@QEAAXPEAVCJobCompleteNotifier@@@Z`
- size: `29`
- prototype: `__int64 __fastcall(_QWORD, _QWORD)`
- caller_count: `30`
- callee_count: `2`
- tags: `file_ops, broker_com_uri`

## callers

- `0x14002afb4`
- `0x14002c514`
- `0x14002c7dc`
- `0x14002cb2c`
- `0x14002ce2c`
- `0x14002d0e0`
- `0x14002d3b4`
- `0x14002d660`
- `0x14002d934`
- `0x14002dc1c`
- `0x14002de30`
- `0x14002e080`
- `0x14002e5f0`
- `0x14002e79c`
- `0x1400541b8`
- `0x140055990`
- `0x14005aebc`
- `0x14005bd8c`
- `0x14008fd6c`
- `0x140090550`
- `0x140092200`
- `0x14009e4a0`
- `0x1400a1390`
- `0x1400a2b64`
- `0x1400a4f84`
- `0x1400a8210`
- `0x1400a9804`
- `0x1400a98dc`
- `0x1400a9dc0`
- `0x1400cd040`

## callees

- `0x14000c940`
- `0x14002b148`

## pseudocode

```c
void __fastcall wistd::unique_ptr<CJobCompleteNotifier,wistd::default_delete<CJobCompleteNotifier>>::reset(
        _QWORD **a1,
        _QWORD *a2)
{
  _QWORD *v2; // rax

  v2 = *a1;
  *a1 = a2;
  if ( v2 )
    operator delete(v2);
}

```

## disassembly

```asm
0x14002b148  sub     rsp, 28h
0x14002b14c  mov     rax, [rcx]
0x14002b14f  mov     [rcx], rdx
0x14002b152  test    rax, rax
0x14002b155  jz      short loc_14002B15F
0x14002b157  mov     rcx, rax; void *
0x14002b15a  call    ??3@YAXPEAX@Z; operator delete(void *)
0x14002b15f  add     rsp, 28h
0x14002b163  retn
```
