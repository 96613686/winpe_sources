# StateRepository::CacheContextEntry::~CacheContextEntry(void)

- ea: `0x18000e434`
- end: `0x18000e453`
- name: `??1CacheContextEntry@StateRepository@@QEAA@XZ`
- size: `31`
- prototype: `void __fastcall(StateRepository::CacheContextEntry *__hidden this)`
- caller_count: `1`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000e45c`

## callees

- `0x18000be00`
- `0x18000c928`

## pseudocode

```c
void __fastcall StateRepository::CacheContextEntry::~CacheContextEntry(HKEY *this)
{
  Common::AutoHandleCloseHKEY<HKEY__ *>(this[1]);
  wistd::unique_ptr<unsigned short [0],wistd::default_delete<unsigned short [0]>>::reset((void **)this);
}

```

## disassembly

```asm
0x18000e434  push    rbx
0x18000e436  sub     rsp, 20h
0x18000e43a  mov     rbx, rcx
0x18000e43d  mov     rcx, [rcx+8]
0x18000e441  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000e446  mov     rcx, rbx
0x18000e449  add     rsp, 20h
0x18000e44d  pop     rbx
0x18000e44e  jmp     ?reset@?$unique_ptr@$$BY0A@GU?$default_delete@$$BY0A@G@wistd@@@wistd@@QEAAX$$T@Z; wistd::unique_ptr<ushort [0],wistd::default_delete<ushort [0]>>::reset(std::nullptr_t)
```
