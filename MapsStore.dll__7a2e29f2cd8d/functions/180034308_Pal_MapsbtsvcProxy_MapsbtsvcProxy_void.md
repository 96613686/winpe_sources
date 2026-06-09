# Pal::MapsbtsvcProxy::~MapsbtsvcProxy(void)

- ea: `0x180034308`
- end: `0x18003433d`
- name: `??1MapsbtsvcProxy@Pal@@EEAA@XZ`
- size: `53`
- prototype: `void __fastcall(Pal::MapsbtsvcProxy *__hidden this)`
- caller_count: `2`
- callee_count: `0`
- tags: `service_task`

## callers

- `0x180034850`
- `0x180096fd0`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x180034336`
- `mapsbtsvc!MapsBackgroundTransferService_FreeJob` at `0x18003431f`
- `mapsbtsvc!MapsBackgroundTransferService_FreeJob` at `0x18003431f`

## pseudocode

```c
void __fastcall Pal::MapsbtsvcProxy::~MapsbtsvcProxy(Pal::MapsbtsvcProxy *this)
{
  *(_QWORD *)this = &Pal::MapsbtsvcProxy::`vftable';
  MapsBackgroundTransferService_FreeJob(*((void **)this + 6));
  *((_QWORD *)this + 6) = 0;
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 8));
}

```

## disassembly

```asm
0x180034308  push    rbx
0x18003430a  sub     rsp, 20h
0x18003430e  mov     rbx, rcx
0x180034311  lea     rax, ??_7MapsbtsvcProxy@Pal@@6B@; const Pal::MapsbtsvcProxy::`vftable'
0x180034318  mov     [rcx], rax
0x18003431b  mov     rcx, [rcx+30h]
0x18003431f  call    cs:__imp_?MapsBackgroundTransferService_FreeJob@@YAXPEAX@Z; MapsBackgroundTransferService_FreeJob(void *)
0x180034325  mov     qword ptr [rbx+30h], 0
0x18003432d  lea     rcx, [rbx+8]
0x180034331  add     rsp, 20h
0x180034335  pop     rbx
0x180034336  jmp     cs:__imp_DeleteCriticalSection
```
