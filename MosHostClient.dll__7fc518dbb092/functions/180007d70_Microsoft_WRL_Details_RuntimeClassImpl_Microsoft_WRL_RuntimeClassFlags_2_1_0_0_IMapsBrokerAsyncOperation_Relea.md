# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(void)

- ea: `0x180007d70`
- end: `0x180007dd1`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIMapsBrokerAsyncOperation@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007fc0`
- `0x180008fb0`
- `0x180009f30`
- `0x18000a3f0`
- `0x18000bdb0`

## callees

- `0x180007d70`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IMapsBrokerAsyncOperation>::Release(
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
0x180007d70  push    rbx
0x180007d72  sub     rsp, 20h
0x180007d76  mov     r9d, 7FFFFFFFh
0x180007d7c  jmp     short loc_180007D8C
0x180007d7e  lea     edx, [r8-1]
0x180007d82  mov     eax, r8d
0x180007d85  lock cmpxchg [rcx+0Ch], edx
0x180007d8a  jz      short loc_180007D95
0x180007d8c  mov     r8d, [rcx+0Ch]
0x180007d90  cmp     r8d, r9d
0x180007d93  jnz     short loc_180007D7E
0x180007d95  lea     ebx, [r8-1]
0x180007d99  test    ebx, ebx
0x180007d9b  jnz     short loc_180007DC9
0x180007d9d  test    rcx, rcx
0x180007da0  jz      short loc_180007DB1
0x180007da2  mov     rax, [rcx]
0x180007da5  lea     edx, [rbx+1]
0x180007da8  mov     rax, [rax+38h]
0x180007dac  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007db1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007db8  test    rcx, rcx
0x180007dbb  jz      short loc_180007DC9
0x180007dbd  mov     rdx, [rcx]
0x180007dc0  mov     rax, [rdx+10h]
0x180007dc4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007dc9  mov     eax, ebx
0x180007dcb  add     rsp, 20h
0x180007dcf  pop     rbx
0x180007dd0  retn
```
