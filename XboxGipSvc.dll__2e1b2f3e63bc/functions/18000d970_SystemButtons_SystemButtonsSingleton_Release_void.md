# SystemButtons::SystemButtonsSingleton::Release(void)

- ea: `0x18000d970`
- end: `0x18000d9bd`
- name: `?Release@SystemButtonsSingleton@SystemButtons@@UEAAKXZ`
- size: `77`
- prototype: `__int64 __fastcall(SystemButtons::SystemButtonsSingleton *this)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c860`
- `0x18000d9d0`
- `0x18000d9e0`
- `0x18000d9f0`
- `0x18000dd6c`

## callees

- `0x18000d740`
- `0x18000d970`

## import_xrefs

- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9aa`
- `api-ms-win-core-synch-l1-1-0!LeaveCriticalSection` at `0x18000d9aa`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d980`
- `api-ms-win-core-synch-l1-1-0!EnterCriticalSection` at `0x18000d980`

## pseudocode

```c
__int64 __fastcall SystemButtons::SystemButtonsSingleton::Release(SystemButtons::SystemButtonsSingleton *this)
{
  __int64 v2; // rax

  EnterCriticalSection(&SystemButtons::singletonInstaceLock);
  v2 = *((_QWORD *)this + 8);
  if ( v2 < 0 )
    LODWORD(v2) = *(_DWORD *)(2 * v2 + 0x10);
  if ( (_DWORD)v2 == 1 )
    SystemButtons::g_instance = 0;
  LeaveCriticalSection(&SystemButtons::singletonInstaceLock);
  return Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Gaming::IGipControllerWatcher,Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Internal::Gaming::Private::Inproc::ISystemButtonsSingletonPrivate>>::Release((volatile signed __int64 *)this);
}

```

## disassembly

```asm
0x18000d970  push    rbx
0x18000d972  sub     rsp, 20h
0x18000d976  mov     rbx, rcx
0x18000d979  lea     rcx, ?singletonInstaceLock@SystemButtons@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x18000d980  call    cs:__imp_EnterCriticalSection
0x18000d986  mov     rax, [rbx+40h]
0x18000d98a  test    rax, rax
0x18000d98d  jns     short loc_18000D993
0x18000d98f  mov     eax, [rax+rax+10h]
0x18000d993  cmp     eax, 1
0x18000d996  jnz     short loc_18000D9A3
0x18000d998  mov     cs:?g_instance@SystemButtons@@3PEAVSystemButtonsSingleton@1@EA, 0; SystemButtons::SystemButtonsSingleton * SystemButtons::g_instance
0x18000d9a3  lea     rcx, ?singletonInstaceLock@SystemButtons@@3VCriticalSection@Wrappers@WRL@Microsoft@@A; lpCriticalSection
0x18000d9aa  call    cs:__imp_LeaveCriticalSection
0x18000d9b0  mov     rcx, rbx
0x18000d9b3  add     rsp, 20h
0x18000d9b7  pop     rbx
0x18000d9b8  jmp     ?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIGipControllerWatcher@Gaming@Internal@Windows@@VFtmBase@23@U?$CloakedIid@UISystemButtonsSingletonPrivate@Inproc@Private@Gaming@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ; Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Gaming::IGipControllerWatcher,Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Internal::Gaming::Private::Inproc::ISystemButtonsSingletonPrivate>>::Release(void)
```
