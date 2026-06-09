# ipx::mtf::CoreUIThreadSync::~CoreUIThreadSync(void)

- ea: `0x180023628`
- end: `0x1800236c5`
- name: `??1CoreUIThreadSync@mtf@ipx@@QEAA@XZ`
- size: `157`
- prototype: `void __fastcall(ipx::mtf::CoreUIThreadSync *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x18001f3ac`
- `0x18002d909`

## callees

- `0x180023628`
- `0x18002f010`

## pseudocode

```c
// Hidden C++ exception states: #wind=2
void __fastcall ipx::mtf::CoreUIThreadSync::~CoreUIThreadSync(ipx::mtf::CoreUIThreadSync *this, __int64 a2)
{
  __int64 v3; // rcx
  __int64 v4; // rcx
  __int64 v5; // rcx
  ipx::mtf::CoreUIThreadSync *v6; // rcx

  v3 = *((_QWORD *)this + 4);
  if ( v3 )
  {
    a2 = *((_QWORD *)this + 5);
    if ( a2 )
      (*(void (__fastcall **)(__int64, __int64, __int64))(*(_QWORD *)v3 + 160LL))(v3, a2, 1);
  }
  *((_QWORD *)this + 5) = 0;
  v4 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  v5 = *((_QWORD *)this + 4);
  *((_QWORD *)this + 4) = 0;
  if ( v5 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v5 + 16LL))(v5);
  v6 = (ipx::mtf::CoreUIThreadSync *)*((_QWORD *)this + 3);
  if ( v6 )
  {
    LOBYTE(a2) = v6 != this;
    (*(void (__fastcall **)(ipx::mtf::CoreUIThreadSync *, __int64))(*(_QWORD *)v6 + 32LL))(v6, a2);
    *((_QWORD *)this + 3) = 0;
  }
}

```

## disassembly

```asm
0x180023628  push    rbx
0x18002362a  sub     rsp, 20h
0x18002362e  mov     rbx, rcx
0x180023631  mov     rcx, [rcx+20h]
0x180023635  test    rcx, rcx
0x180023638  jz      short loc_180023658
0x18002363a  mov     rdx, [rbx+28h]
0x18002363e  test    rdx, rdx
0x180023641  jz      short loc_180023658
0x180023643  mov     rax, [rcx]
0x180023646  mov     r8d, 1
0x18002364c  mov     rax, [rax+0A0h]
0x180023653  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180023658  mov     qword ptr [rbx+28h], 0
0x180023660  mov     rcx, [rbx+20h]
0x180023664  mov     qword ptr [rbx+20h], 0
0x18002366c  test    rcx, rcx
0x18002366f  jz      short loc_18002367E
0x180023671  mov     rax, [rcx]
0x180023674  mov     rax, [rax+10h]
0x180023678  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002367d  nop
0x18002367e  mov     rcx, [rbx+20h]
0x180023682  mov     qword ptr [rbx+20h], 0
0x18002368a  test    rcx, rcx
0x18002368d  jz      short loc_18002369C
0x18002368f  mov     rax, [rcx]
0x180023692  mov     rax, [rax+10h]
0x180023696  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18002369b  nop
0x18002369c  mov     rcx, [rbx+18h]
0x1800236a0  test    rcx, rcx
0x1800236a3  jz      short loc_1800236BF
0x1800236a5  mov     rax, [rcx]
0x1800236a8  cmp     rcx, rbx
0x1800236ab  setnz   dl
0x1800236ae  mov     rax, [rax+20h]
0x1800236b2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800236b7  mov     qword ptr [rbx+18h], 0
0x1800236bf  add     rsp, 20h
0x1800236c3  pop     rbx
0x1800236c4  retn
```
