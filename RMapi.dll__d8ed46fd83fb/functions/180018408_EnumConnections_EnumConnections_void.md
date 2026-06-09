# EnumConnections::~EnumConnections(void)

- ea: `0x180018408`
- end: `0x180018431`
- name: `??1EnumConnections@@UEAA@XZ`
- size: `41`
- prototype: `void __fastcall(EnumConnections *__hidden this)`
- caller_count: `1`
- callee_count: `1`
- tags: ``

## callers

- `0x1800184d0`

## callees

- `0x1800195ec`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001841e`
- `api-ms-win-core-synch-l1-1-0!DeleteCriticalSection` at `0x18001841e`

## pseudocode

```c
void __fastcall EnumConnections::~EnumConnections(EnumConnections *this)
{
  std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>>::_Tidy((char *)this + 56);
  DeleteCriticalSection((LPCRITICAL_SECTION)((char *)this + 16));
  *((_DWORD *)this + 3) = -1073741823;
}

```

## disassembly

```asm
0x180018408  push    rbx
0x18001840a  sub     rsp, 20h
0x18001840e  mov     rbx, rcx
0x180018411  add     rcx, 38h ; '8'
0x180018415  call    ?_Tidy@?$vector@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@V?$allocator@V?$shared_ptr@UCallerContext@ConnectionPointContainer@@@std@@@2@@std@@AEAAXXZ; std::vector<std::shared_ptr<ConnectionPointContainer::CallerContext>>::_Tidy(void)
0x18001841a  lea     rcx, [rbx+10h]; lpCriticalSection
0x18001841e  call    cs:__imp_DeleteCriticalSection
0x180018424  mov     dword ptr [rbx+0Ch], 0C0000001h
0x18001842b  add     rsp, 20h
0x18001842f  pop     rbx
0x180018430  retn
```
