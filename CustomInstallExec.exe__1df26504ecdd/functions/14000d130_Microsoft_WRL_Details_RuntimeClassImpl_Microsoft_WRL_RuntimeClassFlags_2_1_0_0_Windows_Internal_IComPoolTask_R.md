# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,Windows::Internal::IComPoolTask>::Release(void)

- ea: `0x14000d130`
- end: `0x14000d191`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIComPoolTask@Internal@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `service_task, broker_com_uri`

## callers

- `0x14000becc`
- `0x14000bf88`

## callees

- `0x14000d130`
- `0x14000f010`

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
0x14000d130  push    rbx
0x14000d132  sub     rsp, 20h
0x14000d136  mov     r9d, 7FFFFFFFh
0x14000d13c  jmp     short loc_14000D14C
0x14000d13e  lea     edx, [r8-1]
0x14000d142  mov     eax, r8d
0x14000d145  lock cmpxchg [rcx+0Ch], edx
0x14000d14a  jz      short loc_14000D155
0x14000d14c  mov     r8d, [rcx+0Ch]
0x14000d150  cmp     r8d, r9d
0x14000d153  jnz     short loc_14000D13E
0x14000d155  lea     ebx, [r8-1]
0x14000d159  test    ebx, ebx
0x14000d15b  jnz     short loc_14000D189
0x14000d15d  test    rcx, rcx
0x14000d160  jz      short loc_14000D171
0x14000d162  mov     rax, [rcx]
0x14000d165  lea     edx, [rbx+1]
0x14000d168  mov     rax, [rax+20h]
0x14000d16c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d171  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x14000d178  test    rcx, rcx
0x14000d17b  jz      short loc_14000D189
0x14000d17d  mov     rdx, [rcx]
0x14000d180  mov     rax, [rdx+10h]
0x14000d184  call    _guard_dispatch_icall$thunk$10345483385596137414
0x14000d189  mov     eax, ebx
0x14000d18b  add     rsp, 20h
0x14000d18f  pop     rbx
0x14000d190  retn
```
