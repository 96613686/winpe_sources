# Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>(void)

- ea: `0x1800023f0`
- end: `0x180002418`
- name: `??1?$ComPtr@U?$ITypedEventHandler@PEAVGipControllerWatcher@Gaming@Internal@Windows@@PEAVGipSystemButtonEventArgs@234@@Foundation@Windows@@@WRL@Microsoft@@QEAA@XZ`
- size: `40`
- prototype: `void __fastcall(__int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x1800116df`
- `0x18001175d`
- `0x1800117a5`

## callees

- `0x1800023f0`
- `0x180012010`

## pseudocode

```c
void __fastcall Microsoft::WRL::ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>::~ComPtr<Windows::Foundation::ITypedEventHandler<Windows::Internal::Gaming::GipControllerWatcher *,Windows::Internal::Gaming::GipSystemButtonEventArgs *>>(
        __int64 *a1)
{
  __int64 v2; // rcx

  v2 = *a1;
  if ( v2 )
  {
    *a1 = 0;
    (*(void (__fastcall **)(__int64))(*(_QWORD *)v2 + 16LL))(v2);
  }
}

```

## disassembly

```asm
0x1800023f0  sub     rsp, 28h
0x1800023f4  mov     rax, rcx
0x1800023f7  mov     rcx, [rcx]
0x1800023fa  test    rcx, rcx
0x1800023fd  jz      short loc_180002413
0x1800023ff  mov     qword ptr [rax], 0
0x180002406  mov     rax, [rcx]
0x180002409  mov     rax, [rax+10h]
0x18000240d  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180002412  nop
0x180002413  add     rsp, 28h
0x180002417  retn
```
