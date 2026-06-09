# MessagingService::`scalar deleting destructor'(uint)

- ea: `0x180002fd0`
- end: `0x18000301c`
- name: `??_GMessagingService@@UEAAPEAXI@Z`
- size: `76`
- prototype: `MessagingService *__fastcall(MessagingService *this, char)`
- caller_count: `0`
- callee_count: `3`
- tags: `file_ops, service_task`

## callees

- `0x180002fd0`
- `0x180005d18`
- `0x18000c010`

## import_xrefs

- `msvcrt!??3@YAXPEAX@Z` at `0x180003008`
- `msvcrt!??3@YAXPEAX@Z` at `0x180003008`

## pseudocode

```c
MessagingService *__fastcall MessagingService::`scalar deleting destructor'(MessagingService *this, char a2)
{
  __int64 v4; // rcx

  v4 = *((_QWORD *)this + 24);
  if ( v4 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  ServiceBase::~ServiceBase(this);
  if ( (a2 & 1) != 0 )
    operator delete(this);
  return this;
}

```

## disassembly

```asm
0x180002fd0  mov     [rsp+arg_0], rbx
0x180002fd5  push    rdi
0x180002fd6  sub     rsp, 20h
0x180002fda  mov     rbx, rcx
0x180002fdd  mov     edi, edx
0x180002fdf  mov     rcx, [rcx+0C0h]
0x180002fe6  test    rcx, rcx
0x180002fe9  jz      short loc_180002FF7
0x180002feb  mov     rax, [rcx]
0x180002fee  mov     rax, [rax+10h]
0x180002ff2  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002ff7  mov     rcx, rbx; this
0x180002ffa  call    ??1ServiceBase@@UEAA@XZ; ServiceBase::~ServiceBase(void)
0x180002fff  test    dil, 1
0x180003003  jz      short loc_18000300E
0x180003005  mov     rcx, rbx
0x180003008  call    cs:__imp_??3@YAXPEAX@Z; operator delete(void *)
0x18000300e  mov     rax, rbx
0x180003011  mov     rbx, [rsp+28h+arg_0]
0x180003016  add     rsp, 20h
0x18000301a  pop     rdi
0x18000301b  retn
```
