# CALACDecMFT::CALACDecMFT(void)

- ea: `0x180001ec4`
- end: `0x180001f41`
- name: `??0CALACDecMFT@@QEAA@XZ`
- size: `125`
- prototype: `CALACDecMFT *__fastcall(CALACDecMFT *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: ``

## callers

- `0x180004f84`
- `0x1800050a8`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001f15`
- `api-ms-win-core-synch-l1-1-0!InitializeCriticalSection` at `0x180001f15`

## pseudocode

```c
CALACDecMFT *__fastcall CALACDecMFT::CALACDecMFT(CALACDecMFT *this)
{
  CALACDecMFT *result; // rax

  *((_DWORD *)this + 36) = 2;
  *(_QWORD *)((char *)this + 148) = 0;
  *((_DWORD *)this + 2) = 0;
  *((_QWORD *)this + 2) = 0;
  *((_DWORD *)this + 6) = 0;
  *((_QWORD *)this + 4) = 0;
  *((_QWORD *)this + 5) = 0;
  *((_QWORD *)this + 6) = 0;
  *((_QWORD *)this + 7) = 0;
  *((_QWORD *)this + 8) = 0;
  *((_QWORD *)this + 9) = 0;
  *((_QWORD *)this + 10) = 0;
  *((_QWORD *)this + 11) = 0;
  *((_DWORD *)this + 24) = 0;
  InitializeCriticalSection((LPCRITICAL_SECTION)((char *)this + 104));
  *((_QWORD *)this + 22) = 0;
  *(_QWORD *)this = &CALACDecMFT::`vftable';
  result = this;
  *((_QWORD *)this + 23) = 0;
  return result;
}

```

## disassembly

```asm
0x180001ec4  mov     [rsp+arg_0], rbx
0x180001ec9  push    rdi
0x180001eca  sub     rsp, 20h
0x180001ece  xor     edi, edi
0x180001ed0  mov     dword ptr [rcx+90h], 2
0x180001eda  mov     [rcx+94h], rdi
0x180001ee1  mov     rbx, rcx
0x180001ee4  mov     [rcx+8], edi
0x180001ee7  mov     [rcx+10h], rdi
0x180001eeb  mov     [rcx+18h], edi
0x180001eee  mov     [rcx+20h], rdi
0x180001ef2  mov     [rcx+28h], rdi
0x180001ef6  mov     [rcx+30h], rdi
0x180001efa  mov     [rcx+38h], rdi
0x180001efe  mov     [rcx+40h], rdi
0x180001f02  mov     [rcx+48h], rdi
0x180001f06  mov     [rcx+50h], rdi
0x180001f0a  mov     [rcx+58h], rdi
0x180001f0e  mov     [rcx+60h], edi
0x180001f11  add     rcx, 68h ; 'h'; lpCriticalSection
0x180001f15  call    cs:__imp_InitializeCriticalSection
0x180001f1b  lea     rax, ??_7CALACDecMFT@@6B@; const CALACDecMFT::`vftable'
0x180001f22  mov     [rbx+0B0h], rdi
0x180001f29  mov     [rbx], rax
0x180001f2c  mov     rax, rbx
0x180001f2f  mov     [rbx+0B8h], rdi
0x180001f36  mov     rbx, [rsp+28h+arg_0]
0x180001f3b  add     rsp, 20h
0x180001f3f  pop     rdi
0x180001f40  retn
```
