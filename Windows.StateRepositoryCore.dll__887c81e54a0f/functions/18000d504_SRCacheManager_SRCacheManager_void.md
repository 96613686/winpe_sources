# SRCacheManager::~SRCacheManager(void)

- ea: `0x18000d504`
- end: `0x18000d52e`
- name: `??1SRCacheManager@@QEAA@XZ`
- size: `42`
- prototype: `void __fastcall(SRCacheManager *__hidden this)`
- caller_count: `1`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000d534`

## callees

- `0x18000be00`
- `0x18000d504`
- `0x18000e6d8`

## pseudocode

```c
void __fastcall SRCacheManager::~SRCacheManager(SRCacheManager *this)
{
  if ( *((_BYTE *)this + 20) )
    StateRepository::SRCacheContextCacheSingleton::Shutdown();
  Common::AutoHandleCloseHKEY<HKEY__ *>(*((HKEY *)this + 1));
  Common::AutoHandleCloseHKEY<HKEY__ *>(*(HKEY *)this);
}

```

## disassembly

```asm
0x18000d504  push    rbx
0x18000d506  sub     rsp, 20h
0x18000d50a  cmp     byte ptr [rcx+14h], 0
0x18000d50e  mov     rbx, rcx
0x18000d511  jz      short loc_18000D518
0x18000d513  call    ?Shutdown@SRCacheContextCacheSingleton@StateRepository@@SAJXZ; StateRepository::SRCacheContextCacheSingleton::Shutdown(void)
0x18000d518  mov     rcx, [rbx+8]
0x18000d51c  call    ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
0x18000d521  mov     rcx, [rbx]
0x18000d524  add     rsp, 20h
0x18000d528  pop     rbx
0x18000d529  jmp     ??$AutoHandleCloseHKEY@PEAUHKEY__@@@Common@@YAXPEAUHKEY__@@@Z; Common::AutoHandleCloseHKEY<HKEY__ *>(HKEY__ *)
```
