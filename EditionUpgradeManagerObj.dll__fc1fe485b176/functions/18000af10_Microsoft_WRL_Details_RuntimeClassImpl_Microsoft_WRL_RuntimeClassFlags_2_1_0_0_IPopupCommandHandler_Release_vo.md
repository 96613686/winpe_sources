# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommandHandler>::Release(void)

- ea: `0x18000af10`
- end: `0x18000af71`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPopupCommandHandler@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `1`
- callee_count: `2`
- tags: `loader_planting, broker_com_uri`

## callers

- `0x18000eec4`

## callees

- `0x18000af10`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommandHandler>::Release(
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
0x18000af10  push    rbx
0x18000af12  sub     rsp, 20h
0x18000af16  mov     r9d, 7FFFFFFFh
0x18000af1c  jmp     short loc_18000AF2C
0x18000af1e  lea     edx, [r8-1]
0x18000af22  mov     eax, r8d
0x18000af25  lock cmpxchg [rcx+0Ch], edx
0x18000af2a  jz      short loc_18000AF35
0x18000af2c  mov     r8d, [rcx+0Ch]
0x18000af30  cmp     r8d, r9d
0x18000af33  jnz     short loc_18000AF1E
0x18000af35  lea     ebx, [r8-1]
0x18000af39  test    ebx, ebx
0x18000af3b  jnz     short loc_18000AF69
0x18000af3d  test    rcx, rcx
0x18000af40  jz      short loc_18000AF51
0x18000af42  mov     rax, [rcx]
0x18000af45  lea     edx, [rbx+1]
0x18000af48  mov     rax, [rax+20h]
0x18000af4c  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af51  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000af58  test    rcx, rcx
0x18000af5b  jz      short loc_18000AF69
0x18000af5d  mov     rdx, [rcx]
0x18000af60  mov     rax, [rdx+10h]
0x18000af64  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000af69  mov     eax, ebx
0x18000af6b  add     rsp, 20h
0x18000af6f  pop     rbx
0x18000af70  retn
```
