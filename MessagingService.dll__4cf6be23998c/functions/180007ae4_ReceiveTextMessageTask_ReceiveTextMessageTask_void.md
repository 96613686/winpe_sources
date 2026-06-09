# ReceiveTextMessageTask::~ReceiveTextMessageTask(void)

- ea: `0x180007ae4`
- end: `0x180007b44`
- name: `??1ReceiveTextMessageTask@@MEAA@XZ`
- size: `96`
- prototype: `void __fastcall(ReceiveTextMessageTask *__hidden this)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task`

## callers

- `0x180007bb0`
- `0x180007c10`

## callees

- `0x180007ae4`
- `0x18000c010`

## pseudocode

```c
void __fastcall ReceiveTextMessageTask::~ReceiveTextMessageTask(ReceiveTextMessageTask *this)
{
  __int64 v2; // rcx
  __int64 v3; // rcx
  __int64 v4; // rcx

  *(_QWORD *)this = &ReceiveTextMessageTask::`vftable';
  v2 = *((_QWORD *)this + 5);
  if ( v2 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 8LL))(v2);
  v3 = *((_QWORD *)this + 4);
  if ( v3 )
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v3 + 16LL))(v3);
  v4 = *((_QWORD *)this + 3);
  if ( v4 )
  {
    *((_QWORD *)this + 3) = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v4 + 16LL))(v4);
  }
}

```

## disassembly

```asm
0x180007ae4  push    rbx
0x180007ae6  sub     rsp, 20h
0x180007aea  lea     rax, ??_7ReceiveTextMessageTask@@6B@; const ReceiveTextMessageTask::`vftable'
0x180007af1  mov     rbx, rcx
0x180007af4  mov     [rcx], rax
0x180007af7  mov     rcx, [rcx+28h]
0x180007afb  test    rcx, rcx
0x180007afe  jz      short loc_180007B0C
0x180007b00  mov     rax, [rcx]
0x180007b03  mov     rax, [rax+8]
0x180007b07  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b0c  mov     rcx, [rbx+20h]
0x180007b10  test    rcx, rcx
0x180007b13  jz      short loc_180007B21
0x180007b15  mov     rax, [rcx]
0x180007b18  mov     rax, [rax+10h]
0x180007b1c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b21  mov     rcx, [rbx+18h]
0x180007b25  test    rcx, rcx
0x180007b28  jz      short loc_180007B3E
0x180007b2a  mov     qword ptr [rbx+18h], 0
0x180007b32  mov     rax, [rcx]
0x180007b35  mov     rax, [rax+10h]
0x180007b39  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007b3e  add     rsp, 20h
0x180007b42  pop     rbx
0x180007b43  retn
```
