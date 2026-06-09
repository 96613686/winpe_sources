# Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x180003ec0`
- end: `0x180003f52`
- name: `?Release@?$ActivationFactory@UISecurityMitigationsBrokerStatics@Internal@Windows@@VNil@Details@WRL@Microsoft@@V4567@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `146`
- prototype: ``
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180003f60`
- `0x180003f70`

## callees

- `0x180003ec0`
- `0x180007010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Windows::Internal::ISecurityMitigationsBrokerStatics,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
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
    v3 = *(unsigned int *)(a1 + 20);
    if ( (_DWORD)v3 == 0x7FFFFFFF )
      break;
    a2 = (unsigned int)(v3 - 1);
  }
  while ( (_DWORD)v3 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 20), a2, v3) );
  v4 = v3 - 1;
  v5 = *(_DWORD *)(a1 + 40) & 4;
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
0x180003ec0  mov     [rsp+arg_0], rbx
0x180003ec5  push    rdi
0x180003ec6  sub     rsp, 20h
0x180003eca  mov     r9d, 7FFFFFFFh
0x180003ed0  jmp     short loc_180003EE0
0x180003ed2  lea     edx, [r8-1]
0x180003ed6  mov     eax, r8d
0x180003ed9  lock cmpxchg [rcx+14h], edx
0x180003ede  jz      short loc_180003EE9
0x180003ee0  mov     r8d, [rcx+14h]
0x180003ee4  cmp     r8d, r9d
0x180003ee7  jnz     short loc_180003ED2
0x180003ee9  mov     ebx, [rcx+28h]
0x180003eec  lea     edi, [r8-1]
0x180003ef0  and     ebx, 4
0x180003ef3  test    edi, edi
0x180003ef5  jnz     short loc_180003F24
0x180003ef7  test    rcx, rcx
0x180003efa  jz      short loc_180003F0B
0x180003efc  mov     rax, [rcx]
0x180003eff  lea     edx, [rdi+1]
0x180003f02  mov     rax, [rax+38h]
0x180003f06  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f0b  test    ebx, ebx
0x180003f0d  jz      short loc_180003F45
0x180003f0f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003f16  test    rcx, rcx
0x180003f19  jz      short loc_180003F45
0x180003f1b  mov     rax, [rcx]
0x180003f1e  mov     rax, [rax+10h]
0x180003f22  jmp     short loc_180003F40
0x180003f24  test    ebx, ebx
0x180003f26  jnz     short loc_180003F45
0x180003f28  cmp     edi, 1
0x180003f2b  jnz     short loc_180003F45
0x180003f2d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180003f34  test    rcx, rcx
0x180003f37  jz      short loc_180003F45
0x180003f39  mov     rdx, [rcx]
0x180003f3c  mov     rax, [rdx+10h]
0x180003f40  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180003f45  mov     rbx, [rsp+28h+arg_0]
0x180003f4a  mov     eax, edi
0x180003f4c  add     rsp, 20h
0x180003f50  pop     rdi
0x180003f51  retn
```
