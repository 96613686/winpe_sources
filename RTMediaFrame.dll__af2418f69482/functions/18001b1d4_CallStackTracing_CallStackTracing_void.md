# CallStackTracing::~CallStackTracing(void)

- ea: `0x18001b1d4`
- end: `0x18001b240`
- name: `??1CallStackTracing@@QEAA@XZ`
- size: `108`
- prototype: `void __fastcall(CallStackTracing *__hidden this)`
- caller_count: `1`
- callee_count: `4`
- tags: ``

## callers

- `0x180051170`

## callees

- `0x18001b1d4`
- `0x18001b250`
- `0x18001b25c`
- `0x1800215a4`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b220`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b220`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001b239`

## pseudocode

```c
void __fastcall CallStackTracing::~CallStackTracing(CallStackTracing *this)
{
  __int64 v2; // rdi
  MF::AsyncAction *v3; // rsi

  *(_QWORD *)this = &CallStackTracing::`vftable';
  CallStackTracing::Cleanup(this);
  v2 = 124;
  v3 = (CallStackTracing *)((char *)this + 2192);
  do
  {
    v3 = (MF::AsyncAction *)((char *)v3 - 16);
    MF::AsyncAction::OnCancel(v3);
    --v2;
  }
  while ( v2 );
  CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>((char *)this + 104);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 56));
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
}

```

## disassembly

```asm
0x18001b1d4  mov     [rsp+arg_0], rbx
0x18001b1d9  mov     [rsp+arg_8], rsi
0x18001b1de  push    rdi
0x18001b1df  sub     rsp, 20h
0x18001b1e3  lea     rax, ??_7CallStackTracing@@6B@; const CallStackTracing::`vftable'
0x18001b1ea  mov     rbx, rcx
0x18001b1ed  mov     [rcx], rax
0x18001b1f0  call    ?Cleanup@CallStackTracing@@IEAAXXZ; CallStackTracing::Cleanup(void)
0x18001b1f5  mov     edi, 7Ch ; '|'
0x18001b1fa  lea     rsi, [rbx+890h]
0x18001b201  sub     rsi, 10h
0x18001b205  mov     rcx, rsi; this
0x18001b208  call    ?OnCancel@AsyncAction@MF@@UEAAXXZ; MF::AsyncAction::OnCancel(void)
0x18001b20d  sub     rdi, 1
0x18001b211  jnz     short loc_18001B201
0x18001b213  lea     rcx, [rbx+68h]
0x18001b217  call    ??1?$CFreeList@VCallStackContextNode@@$0BA@@@UEAA@XZ; CFreeList<CallStackContextNode,16>::~CFreeList<CallStackContextNode,16>(void)
0x18001b21c  lea     rcx, [rbx+38h]; lpCriticalSection
0x18001b220  call    cs:__imp_DeleteCriticalSection
0x18001b226  lea     rcx, [rbx+10h]
0x18001b22a  mov     rbx, [rsp+28h+arg_0]
0x18001b22f  mov     rsi, [rsp+28h+arg_8]
0x18001b234  add     rsp, 20h
0x18001b238  pop     rdi
0x18001b239  jmp     cs:__imp_DeleteCriticalSection
```
