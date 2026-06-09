# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Gaming::IGipControllerWatcher,Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Internal::Gaming::Private::Inproc::ISystemButtonsSingletonPrivate>>::Release(void)

- ea: `0x18000d740`
- end: `0x18000d7d0`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIGipControllerWatcher@Gaming@Internal@Windows@@VFtmBase@23@U?$CloakedIid@UISystemButtonsSingletonPrivate@Inproc@Private@Gaming@Internal@Windows@@@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `144`
- prototype: `__int64 __fastcall(volatile signed __int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d7e0`
- `0x18000d7f0`
- `0x18000d800`
- `0x18000d970`

## callees

- `0x18000d740`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::Internal::Gaming::IGipControllerWatcher,Microsoft::WRL::FtmBase,Microsoft::WRL::CloakedIid<Windows::Internal::Gaming::Private::Inproc::ISystemButtonsSingletonPrivate>>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rdx
  unsigned __int32 v2; // ebx
  bool v3; // zf
  signed __int64 v4; // rax
  signed __int32 v5; // r8d

  v1 = *((_QWORD *)a1 + 8);
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return 2147483646;
    v2 = v1 - 1;
    v4 = _InterlockedCompareExchange64(a1 + 8, v1 - 1, v1);
    v3 = v1 == v4;
    v1 = v4;
    if ( v3 )
      goto LABEL_10;
  }
  do
    v5 = *(_DWORD *)(2 * v1 + 0x10);
  while ( v5 != 0x7FFFFFFF && v5 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v1 + 16), v5 - 1, v5) );
  v2 = v5 - 1;
LABEL_10:
  if ( !v2 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*a1 + 64))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d740  push    rbx
0x18000d742  sub     rsp, 20h
0x18000d746  mov     rdx, [rcx+40h]
0x18000d74a  mov     r9, rcx
0x18000d74d  mov     r10d, 7FFFFFFFh
0x18000d753  test    rdx, rdx
0x18000d756  js      short loc_18000D787
0x18000d758  cmp     edx, r10d
0x18000d75b  jz      short loc_18000D771
0x18000d75d  lea     rbx, [rdx-1]
0x18000d761  mov     rax, rdx
0x18000d764  lock cmpxchg [rcx+40h], rbx
0x18000d76a  mov     rdx, rax
0x18000d76d  jnz     short loc_18000D753
0x18000d76f  jmp     short loc_18000D795
0x18000d771  mov     ebx, 7FFFFFFEh
0x18000d776  jmp     short loc_18000D7C8
0x18000d778  lea     ecx, [r8-1]
0x18000d77c  mov     eax, r8d
0x18000d77f  lock cmpxchg [rdx+rdx+10h], ecx
0x18000d785  jz      short loc_18000D791
0x18000d787  mov     r8d, [rdx+rdx+10h]
0x18000d78c  cmp     r8d, r10d
0x18000d78f  jnz     short loc_18000D778
0x18000d791  lea     ebx, [r8-1]
0x18000d795  test    ebx, ebx
0x18000d797  jnz     short loc_18000D7C8
0x18000d799  test    r9, r9
0x18000d79c  jz      short loc_18000D7B0
0x18000d79e  mov     rax, [r9]
0x18000d7a1  lea     edx, [rbx+1]
0x18000d7a4  mov     rcx, r9
0x18000d7a7  mov     rax, [rax+40h]
0x18000d7ab  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7b0  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000d7b7  test    rcx, rcx
0x18000d7ba  jz      short loc_18000D7C8
0x18000d7bc  mov     rdx, [rcx]
0x18000d7bf  mov     rax, [rdx+10h]
0x18000d7c3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d7c8  mov     eax, ebx
0x18000d7ca  add     rsp, 20h
0x18000d7ce  pop     rbx
0x18000d7cf  retn
```
