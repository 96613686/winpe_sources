# CrashEventData::Free(void)

- ea: `0x180004f1c`
- end: `0x180004f9a`
- name: `?Free@CrashEventData@@QEAAXXZ`
- size: `126`
- prototype: `void __fastcall(CrashEventData *__hidden this)`
- caller_count: `6`
- callee_count: `1`
- tags: `authz_impersonation`

## callers

- `0x180002770`
- `0x180002a88`
- `0x1800036f0`
- `0x1800038cc`
- `0x180003ac8`
- `0x180005020`

## callees

- `0x180004f1c`

## import_xrefs

- `KERNEL32!HeapFree` at `0x180004f3f`
- `KERNEL32!HeapFree` at `0x180004f63`
- `KERNEL32!HeapFree` at `0x180004f3f`
- `KERNEL32!HeapFree` at `0x180004f63`
- `KERNEL32!GetProcessHeap` at `0x180004f31`
- `KERNEL32!GetProcessHeap` at `0x180004f55`
- `KERNEL32!GetProcessHeap` at `0x180004f31`
- `KERNEL32!GetProcessHeap` at `0x180004f55`
- `ADVAPI32!FreeSid` at `0x180004f7a`
- `ADVAPI32!FreeSid` at `0x180004f7a`

## pseudocode

```c
void __fastcall CrashEventData::Free(CrashEventData *this)
{
  void *v1; // rdi
  HANDLE ProcessHeap; // rax
  void *v4; // rdi
  HANDLE v5; // rax
  void *v6; // rcx

  v1 = *(void **)this;
  if ( *(_QWORD *)this )
  {
    ProcessHeap = GetProcessHeap();
    HeapFree(ProcessHeap, 0, v1);
    *(_QWORD *)this = 0;
  }
  v4 = (void *)*((_QWORD *)this + 1);
  if ( v4 )
  {
    v5 = GetProcessHeap();
    HeapFree(v5, 0, v4);
    *((_QWORD *)this + 1) = 0;
  }
  v6 = (void *)*((_QWORD *)this + 3);
  if ( v6 )
    FreeSid(v6);
  *((_DWORD *)this + 8) = 0;
  *((_QWORD *)this + 2) = 0;
}

```

## disassembly

```asm
0x180004f1c  mov     [rsp+arg_0], rbx
0x180004f21  push    rdi
0x180004f22  sub     rsp, 20h
0x180004f26  mov     rdi, [rcx]
0x180004f29  mov     rbx, rcx
0x180004f2c  test    rdi, rdi
0x180004f2f  jz      short loc_180004F4C
0x180004f31  call    cs:__imp_GetProcessHeap
0x180004f37  mov     r8, rdi; lpMem
0x180004f3a  xor     edx, edx; dwFlags
0x180004f3c  mov     rcx, rax; hHeap
0x180004f3f  call    cs:__imp_HeapFree
0x180004f45  mov     qword ptr [rbx], 0
0x180004f4c  mov     rdi, [rbx+8]
0x180004f50  test    rdi, rdi
0x180004f53  jz      short loc_180004F71
0x180004f55  call    cs:__imp_GetProcessHeap
0x180004f5b  mov     r8, rdi; lpMem
0x180004f5e  xor     edx, edx; dwFlags
0x180004f60  mov     rcx, rax; hHeap
0x180004f63  call    cs:__imp_HeapFree
0x180004f69  mov     qword ptr [rbx+8], 0
0x180004f71  mov     rcx, [rbx+18h]; pSid
0x180004f75  test    rcx, rcx
0x180004f78  jz      short loc_180004F80
0x180004f7a  call    cs:__imp_FreeSid
0x180004f80  mov     dword ptr [rbx+20h], 0
0x180004f87  mov     qword ptr [rbx+10h], 0
0x180004f8f  mov     rbx, [rsp+28h+arg_0]
0x180004f94  add     rsp, 20h
0x180004f98  pop     rdi
0x180004f99  retn
```
