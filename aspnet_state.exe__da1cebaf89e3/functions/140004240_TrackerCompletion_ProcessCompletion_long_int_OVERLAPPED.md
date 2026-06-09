# TrackerCompletion::ProcessCompletion(long,int,_OVERLAPPED *)

- ea: `0x140004240`
- end: `0x140004275`
- name: `?ProcessCompletion@TrackerCompletion@@UEAAJJHPEAU_OVERLAPPED@@@Z`
- size: `53`
- prototype: `__int64 __fastcall(Tracker **this, unsigned int, int, struct _OVERLAPPED *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x140004108`
- `0x140006590`

## pseudocode

```c
__int64 __fastcall TrackerCompletion::ProcessCompletion(
        Tracker **this,
        unsigned int a2,
        int a3,
        struct _OVERLAPPED *a4)
{
  unsigned int v5; // ebx

  v5 = Tracker::ProcessCompletion(this[7], a2, a3, a4);
  (*((void (__fastcall **)(Tracker **))*this + 2))(this);
  return v5;
}

```

## disassembly

```asm
0x140004240  mov     [rsp+arg_0], rbx
0x140004245  push    rdi
0x140004246  sub     rsp, 20h
0x14000424a  mov     rdi, rcx
0x14000424d  mov     rcx, [rcx+38h]; this
0x140004251  call    ?ProcessCompletion@Tracker@@QEAAJJHPEAU_OVERLAPPED@@@Z; Tracker::ProcessCompletion(long,int,_OVERLAPPED *)
0x140004256  mov     rdx, [rdi]
0x140004259  mov     ebx, eax
0x14000425b  mov     rcx, rdi
0x14000425e  mov     rax, [rdx+10h]
0x140004262  call    cs:__guard_dispatch_icall_fptr
0x140004268  mov     eax, ebx
0x14000426a  mov     rbx, [rsp+28h+arg_0]
0x14000426f  add     rsp, 20h
0x140004273  pop     rdi
0x140004274  retn
```
