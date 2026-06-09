# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x1800042d0`
- end: `0x180004362`
- name: `?Release@?$ActivationFactory@U?$Implements@U?$RuntimeClassFlags@$02@WRL@Microsoft@@UIIncomingCallToastStatics@Calls@ApplicationModel@WindowsInternal@@UINotificationActivationCallback@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `146`
- prototype: ``
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180004370`
- `0x180004380`
- `0x180004450`

## callees

- `0x1800042d0`
- `0x180019010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::RuntimeClassFlags<3>,WindowsInternal::ApplicationModel::Calls::IIncomingCallToastStatics,INotificationActivationCallback>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
        __int64 a1,
        __int64 a2)
{
  __int64 v2; // r9
  __int64 v3; // r8
  unsigned int v4; // edi
  int v5; // ebx

  v2 = 0x7FFFFFFF;
  do
  {
    v3 = *(unsigned int *)(a1 + 44);
    if ( (_DWORD)v3 == 0x7FFFFFFF )
      break;
    a2 = (unsigned int)(v3 - 1);
  }
  while ( (_DWORD)v3 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 44), a2, v3) );
  v4 = v3 - 1;
  v5 = *(_DWORD *)(a1 + 64) & 4;
  if ( (_DWORD)v3 == 1 )
  {
    if ( a1 )
      (*(void (__fastcall **)(__int64, __int64, __int64, __int64))(*(_QWORD *)a1 + 56LL))(a1, 1, v3, 0x7FFFFFFF);
    if ( v5 && Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, __int64, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
        Microsoft::WRL::Details::ModuleBase::module_,
        a2,
        v3,
        v2);
  }
  else if ( !v5 && (_DWORD)v3 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
  {
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *, _QWORD, __int64, __int64))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_ + 16LL))(
      Microsoft::WRL::Details::ModuleBase::module_,
      *(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_,
      v3,
      0x7FFFFFFF);
  }
  return v4;
}

```

## disassembly

```asm
0x1800042d0  mov     [rsp+arg_0], rbx
0x1800042d5  push    rdi
0x1800042d6  sub     rsp, 20h
0x1800042da  mov     r9d, 7FFFFFFFh
0x1800042e0  jmp     short loc_1800042F0
0x1800042e2  lea     edx, [r8-1]
0x1800042e6  mov     eax, r8d
0x1800042e9  lock cmpxchg [rcx+2Ch], edx
0x1800042ee  jz      short loc_1800042F9
0x1800042f0  mov     r8d, [rcx+2Ch]
0x1800042f4  cmp     r8d, r9d
0x1800042f7  jnz     short loc_1800042E2
0x1800042f9  mov     ebx, [rcx+40h]
0x1800042fc  lea     edi, [r8-1]
0x180004300  and     ebx, 4
0x180004303  test    edi, edi
0x180004305  jnz     short loc_180004334
0x180004307  test    rcx, rcx
0x18000430a  jz      short loc_18000431B
0x18000430c  mov     rax, [rcx]
0x18000430f  lea     edx, [rdi+1]
0x180004312  mov     rax, [rax+38h]
0x180004316  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000431b  test    ebx, ebx
0x18000431d  jz      short loc_180004355
0x18000431f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004326  test    rcx, rcx
0x180004329  jz      short loc_180004355
0x18000432b  mov     rax, [rcx]
0x18000432e  mov     rax, [rax+10h]
0x180004332  jmp     short loc_180004350
0x180004334  test    ebx, ebx
0x180004336  jnz     short loc_180004355
0x180004338  cmp     edi, 1
0x18000433b  jnz     short loc_180004355
0x18000433d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180004344  test    rcx, rcx
0x180004347  jz      short loc_180004355
0x180004349  mov     rdx, [rcx]
0x18000434c  mov     rax, [rdx+10h]
0x180004350  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180004355  mov     rbx, [rsp+28h+arg_0]
0x18000435a  mov     eax, edi
0x18000435c  add     rsp, 20h
0x180004360  pop     rdi
0x180004361  retn
```
