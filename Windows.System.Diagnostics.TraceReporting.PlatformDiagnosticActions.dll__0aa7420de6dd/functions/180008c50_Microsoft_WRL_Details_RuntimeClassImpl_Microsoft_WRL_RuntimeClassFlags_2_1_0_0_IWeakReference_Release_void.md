# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(void)

- ea: `0x180008c50`
- end: `0x180008cb1`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIWeakReference@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x1800071d0`
- `0x1800072a0`
- `0x1800072f0`

## callees

- `0x180008c50`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IWeakReference>::Release(
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
0x180008c50  push    rbx
0x180008c52  sub     rsp, 20h
0x180008c56  mov     r9d, 7FFFFFFFh
0x180008c5c  jmp     short loc_180008C6C
0x180008c5e  lea     edx, [r8-1]
0x180008c62  mov     eax, r8d
0x180008c65  lock cmpxchg [rcx+0Ch], edx
0x180008c6a  jz      short loc_180008C75
0x180008c6c  mov     r8d, [rcx+0Ch]
0x180008c70  cmp     r8d, r9d
0x180008c73  jnz     short loc_180008C5E
0x180008c75  lea     ebx, [r8-1]
0x180008c79  test    ebx, ebx
0x180008c7b  jnz     short loc_180008CA9
0x180008c7d  test    rcx, rcx
0x180008c80  jz      short loc_180008C91
0x180008c82  mov     rax, [rcx]
0x180008c85  lea     edx, [rbx+1]
0x180008c88  mov     rax, [rax+20h]
0x180008c8c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c91  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008c98  test    rcx, rcx
0x180008c9b  jz      short loc_180008CA9
0x180008c9d  mov     rdx, [rcx]
0x180008ca0  mov     rax, [rdx+10h]
0x180008ca4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ca9  mov     eax, ebx
0x180008cab  add     rsp, 20h
0x180008caf  pop     rbx
0x180008cb0  retn
```
