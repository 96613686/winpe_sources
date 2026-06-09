# TOKEN_ENTRY::TOKEN_ENTRY(void)

- ea: `0x1800041a4`
- end: `0x180004216`
- name: `??0TOKEN_ENTRY@@QEAA@XZ`
- size: `114`
- prototype: `TOKEN_ENTRY *__fastcall(TOKEN_ENTRY *__hidden this)`
- caller_count: `2`
- callee_count: `1`
- tags: ``

## callers

- `0x1800043b8`
- `0x180005354`

## callees

- `0x18000421c`

## import_xrefs

- `iisutil!??0CSmallSpinLock@@QEAA@XZ` at `0x1800041e5`
- `iisutil!??0CSmallSpinLock@@QEAA@XZ` at `0x1800041e5`

## pseudocode

```c
TOKEN_ENTRY *__fastcall TOKEN_ENTRY::TOKEN_ENTRY(TOKEN_ENTRY *this)
{
  TOKEN_ENTRY *result; // rax

  *((_DWORD *)this + 3) = 1;
  *(_QWORD *)this = &TOKEN_ENTRY::`vftable';
  *((_QWORD *)this + 2) = 0;
  *((_QWORD *)this + 3) = 0;
  *((_DWORD *)this + 29) = 0;
  TOKEN_KEY::TOKEN_KEY((TOKEN_ENTRY *)((char *)this + 120));
  CSmallSpinLock::CSmallSpinLock((TOKEN_ENTRY *)((char *)this + 248));
  *((_DWORD *)this + 65) &= 0xFFFFFFFC;
  result = this;
  *((_DWORD *)this + 63) = 0;
  *((_DWORD *)this + 64) = 2;
  *((_DWORD *)this + 2) = 1313558356;
  return result;
}

```

## disassembly

```asm
0x1800041a4  push    rbx
0x1800041a6  sub     rsp, 20h
0x1800041aa  lea     rax, ??_7TOKEN_ENTRY@@6B@; const TOKEN_ENTRY::`vftable'
0x1800041b1  mov     dword ptr [rcx+0Ch], 1
0x1800041b8  mov     [rcx], rax
0x1800041bb  mov     rbx, rcx
0x1800041be  mov     qword ptr [rcx+10h], 0
0x1800041c6  mov     qword ptr [rcx+18h], 0
0x1800041ce  mov     dword ptr [rcx+74h], 0
0x1800041d5  add     rcx, 78h ; 'x'; this
0x1800041d9  call    ??0TOKEN_KEY@@QEAA@XZ; TOKEN_KEY::TOKEN_KEY(void)
0x1800041de  lea     rcx, [rbx+0F8h]
0x1800041e5  call    cs:__imp_??0CSmallSpinLock@@QEAA@XZ; CSmallSpinLock::CSmallSpinLock(void)
0x1800041eb  and     dword ptr [rbx+104h], 0FFFFFFFCh
0x1800041f2  mov     rax, rbx
0x1800041f5  mov     dword ptr [rbx+0FCh], 0
0x1800041ff  mov     dword ptr [rbx+100h], 2
0x180004209  mov     dword ptr [rbx+8], 4E4B4F54h
0x180004210  add     rsp, 20h
0x180004214  pop     rbx
0x180004215  retn
```
