# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::Release(void)

- ea: `0x18000a1a0`
- end: `0x18000a201`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIEditionUpgradeBroker@@UIContainerActivationHelper@@UIClipServiceNotificationHelper@@UIFClipNotificationHelper@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x18000a210`
- `0x18000a220`
- `0x18000a230`

## callees

- `0x18000a1a0`
- `0x180027010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IEditionUpgradeBroker,IContainerActivationHelper,IClipServiceNotificationHelper,IFClipNotificationHelper>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 9);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 9, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 56LL))(
        a1,
        1,
        v2,
        0x7FFFFFFF);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
        v2,
        v1);
  }
  return v3;
}

```

## disassembly

```asm
0x18000a1a0  push    rbx
0x18000a1a2  sub     rsp, 20h
0x18000a1a6  mov     r9d, 7FFFFFFFh
0x18000a1ac  jmp     short loc_18000A1BC
0x18000a1ae  lea     edx, [r8-1]
0x18000a1b2  mov     eax, r8d
0x18000a1b5  lock cmpxchg [rcx+24h], edx
0x18000a1ba  jz      short loc_18000A1C5
0x18000a1bc  mov     r8d, [rcx+24h]
0x18000a1c0  cmp     r8d, r9d
0x18000a1c3  jnz     short loc_18000A1AE
0x18000a1c5  lea     ebx, [r8-1]
0x18000a1c9  test    ebx, ebx
0x18000a1cb  jnz     short loc_18000A1F9
0x18000a1cd  test    rcx, rcx
0x18000a1d0  jz      short loc_18000A1E1
0x18000a1d2  mov     rax, [rcx]
0x18000a1d5  lea     edx, [rbx+1]
0x18000a1d8  mov     rax, [rax+38h]
0x18000a1dc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1e1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000a1e8  test    rcx, rcx
0x18000a1eb  jz      short loc_18000A1F9
0x18000a1ed  mov     rdx, [rcx]
0x18000a1f0  mov     rax, [rdx+10h]
0x18000a1f4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000a1f9  mov     eax, ebx
0x18000a1fb  add     rsp, 20h
0x18000a1ff  pop     rbx
0x18000a200  retn
```
