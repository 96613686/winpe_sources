# CPcmPin::DeleteProcessAudioTimer(void)

- ea: `0x1400839fc`
- end: `0x140083a44`
- name: `?DeleteProcessAudioTimer@CPcmPin@@AEAAXXZ`
- size: `72`
- prototype: `void __fastcall(CPcmPin *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: ``

## callers

- `0x140083430`
- `0x140083540`

## callees

- `0x140005800`
- `0x1400839fc`

## import_xrefs

- `ntoskrnl!ExDeleteTimer` at `0x140083a1a`
- `ntoskrnl!ExDeleteTimer` at `0x140083a1a`

## pseudocode

```c
void __fastcall CPcmPin::DeleteProcessAudioTimer(CPcmPin *this, __int64 a2, __int64 a3)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 32);
  if ( v4 )
  {
    LOBYTE(a3) = 1;
    LOBYTE(a2) = 1;
    if ( (unsigned __int8)ExDeleteTimer(v4, a2, a3, 0) )
      CPcmPin::UnlockTimerDpc(this);
    *((_QWORD *)this + 32) = 0;
  }
}

```

## disassembly

```asm
0x1400839fc  push    rbx
0x1400839fe  sub     rsp, 20h
0x140083a02  mov     rbx, rcx
0x140083a05  mov     rcx, [rcx+100h]
0x140083a0c  test    rcx, rcx
0x140083a0f  jz      short loc_140083A3D
0x140083a11  mov     r8b, 1
0x140083a14  xor     r9d, r9d
0x140083a17  mov     dl, r8b
0x140083a1a  call    cs:__imp_ExDeleteTimer
0x140083a21  nop     dword ptr [rax+rax+00h]
0x140083a26  test    al, al
0x140083a28  jz      short loc_140083A32
0x140083a2a  mov     rcx, rbx; this
0x140083a2d  call    ?UnlockTimerDpc@CPcmPin@@AEAAJXZ; CPcmPin::UnlockTimerDpc(void)
0x140083a32  mov     qword ptr [rbx+100h], 0
0x140083a3d  add     rsp, 20h
0x140083a41  pop     rbx
0x140083a42  retn
```
