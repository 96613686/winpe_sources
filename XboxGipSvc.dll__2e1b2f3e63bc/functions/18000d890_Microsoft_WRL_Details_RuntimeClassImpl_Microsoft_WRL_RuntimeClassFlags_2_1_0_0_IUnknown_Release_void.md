# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(void)

- ea: `0x18000d890`
- end: `0x18000d8f1`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIUnknown@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `5`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000c5a0`
- `0x18000c790`
- `0x18000cc9c`
- `0x18000da00`
- `0x180010040`

## callees

- `0x18000d890`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IUnknown>::Release(
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
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 24LL))(
        a1,
        1,
        v2,
        0x7FFFFFFF);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(Microsoft::WRL::Details *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                                  + 16LL))(
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
0x18000d890  push    rbx
0x18000d892  sub     rsp, 20h
0x18000d896  mov     r9d, 7FFFFFFFh
0x18000d89c  jmp     short loc_18000D8AC
0x18000d89e  lea     edx, [r8-1]
0x18000d8a2  mov     eax, r8d
0x18000d8a5  lock cmpxchg [rcx+0Ch], edx
0x18000d8aa  jz      short loc_18000D8B5
0x18000d8ac  mov     r8d, [rcx+0Ch]
0x18000d8b0  cmp     r8d, r9d
0x18000d8b3  jnz     short loc_18000D89E
0x18000d8b5  lea     ebx, [r8-1]
0x18000d8b9  test    ebx, ebx
0x18000d8bb  jnz     short loc_18000D8E9
0x18000d8bd  test    rcx, rcx
0x18000d8c0  jz      short loc_18000D8D1
0x18000d8c2  mov     rax, [rcx]
0x18000d8c5  lea     edx, [rbx+1]
0x18000d8c8  mov     rax, [rax+18h]
0x18000d8cc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8d1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000d8d8  test    rcx, rcx
0x18000d8db  jz      short loc_18000D8E9
0x18000d8dd  mov     rdx, [rcx]
0x18000d8e0  mov     rax, [rdx+10h]
0x18000d8e4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d8e9  mov     eax, ebx
0x18000d8eb  add     rsp, 20h
0x18000d8ef  pop     rbx
0x18000d8f0  retn
```
