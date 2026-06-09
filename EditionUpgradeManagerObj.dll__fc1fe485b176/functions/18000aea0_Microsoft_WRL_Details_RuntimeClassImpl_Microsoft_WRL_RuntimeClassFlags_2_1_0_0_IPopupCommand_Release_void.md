# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::Release(void)

- ea: `0x18000aea0`
- end: `0x18000af01`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$01@WRL@Microsoft@@$00$0A@$0A@UIPopupCommand@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `97`
- prototype: `__int64 __fastcall(volatile signed __int32 *)`
- caller_count: `0`
- callee_count: `2`
- tags: `broker_com_uri`

## callees

- `0x18000aea0`
- `0x180023010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<2>,1,0,0,IPopupCommand>::Release(
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
      (*(void (__fastcall **)(volatile signed __int32 *, __int64, __int64, __int64))(*(_QWORD *)a1 + 48LL))(
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
0x18000aea0  push    rbx
0x18000aea2  sub     rsp, 20h
0x18000aea6  mov     r9d, 7FFFFFFFh
0x18000aeac  jmp     short loc_18000AEBC
0x18000aeae  lea     edx, [r8-1]
0x18000aeb2  mov     eax, r8d
0x18000aeb5  lock cmpxchg [rcx+0Ch], edx
0x18000aeba  jz      short loc_18000AEC5
0x18000aebc  mov     r8d, [rcx+0Ch]
0x18000aec0  cmp     r8d, r9d
0x18000aec3  jnz     short loc_18000AEAE
0x18000aec5  lea     ebx, [r8-1]
0x18000aec9  test    ebx, ebx
0x18000aecb  jnz     short loc_18000AEF9
0x18000aecd  test    rcx, rcx
0x18000aed0  jz      short loc_18000AEE1
0x18000aed2  mov     rax, [rcx]
0x18000aed5  lea     edx, [rbx+1]
0x18000aed8  mov     rax, [rax+30h]
0x18000aedc  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aee1  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000aee8  test    rcx, rcx
0x18000aeeb  jz      short loc_18000AEF9
0x18000aeed  mov     rdx, [rcx]
0x18000aef0  mov     rax, [rdx+10h]
0x18000aef4  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000aef9  mov     eax, ebx
0x18000aefb  add     rsp, 20h
0x18000aeff  pop     rbx
0x18000af00  retn
```
