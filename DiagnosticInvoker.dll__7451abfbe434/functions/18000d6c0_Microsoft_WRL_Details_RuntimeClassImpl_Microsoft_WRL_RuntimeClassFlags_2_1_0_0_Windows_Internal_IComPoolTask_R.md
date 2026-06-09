# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)

- ea: `0x18000d6c0`
- end: `0x18000d721`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x180008700`
- `0x180008748`
- `0x18000ee84`

## callees

- `0x18000d6c0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(
        volatile signed __int32 *a1)
{
  __int64 v1; // r9
  __int64 v2; // r8
  unsigned int v3; // ebx

  v1 = 0x7FFFFFFF;
  do
    v2 = *((unsigned int *)a1 + 3);
  while ( (_DWORD)v2 != 0x7FFFFFFF && (_DWORD)v2 != _InterlockedCompareExchange(a1 + 3, v2 - 1, v2) );
  v3 = v2 - 1;
  if ( (_DWORD)v2 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 32LL))(
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
0x18000d6c0  push    rbx
0x18000d6c2  sub     rsp, 20h
0x18000d6c6  mov     r9d, 7FFFFFFFh
0x18000d6cc  jmp     short loc_18000D6DC
0x18000d6ce  lea     edx, [r8-1]
0x18000d6d2  mov     eax, r8d
0x18000d6d5  lock cmpxchg [rcx+0Ch], edx
0x18000d6da  jz      short loc_18000D6E5
0x18000d6dc  mov     r8d, [rcx+0Ch]
0x18000d6e0  cmp     r8d, r9d
0x18000d6e3  jnz     short loc_18000D6CE
0x18000d6e5  lea     ebx, [r8-1]
0x18000d6e9  test    ebx, ebx
0x18000d6eb  jnz     short loc_18000D719
0x18000d6ed  test    rcx, rcx
0x18000d6f0  jz      short loc_18000D701
0x18000d6f2  mov     rax, [rcx]
0x18000d6f5  lea     edx, [rbx+1]
0x18000d6f8  mov     rax, [rax+20h]
0x18000d6fc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d701  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000d708  test    rcx, rcx
0x18000d70b  jz      short loc_18000D719
0x18000d70d  mov     rdx, [rcx]
0x18000d710  mov     rax, [rdx+10h]
0x18000d714  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d719  mov     eax, ebx
0x18000d71b  add     rsp, 20h
0x18000d71f  pop     rbx
0x18000d720  retn
```
