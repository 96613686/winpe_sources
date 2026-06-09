# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x1800070b0`
- end: `0x180007142`
- name: `?Release@?$ActivationFactory@VNil@Details@WRL@Microsoft@@V1234@V1234@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `146`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `6`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180005f80`
- `0x1800073b0`
- `0x1800074f0`
- `0x180007630`
- `0x180007770`
- `0x1800078b0`

## callees

- `0x1800070b0`
- `0x180012010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
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
    v3 = *(unsigned int *)(a1 + 12);
    if ( (_DWORD)v3 == 0x7FFFFFFF )
      break;
    a2 = (unsigned int)(v3 - 1);
  }
  while ( (_DWORD)v3 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 12), a2, v3) );
  v4 = v3 - 1;
  v5 = *(_DWORD *)(a1 + 32) & 4;
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
0x1800070b0  mov     [rsp+arg_0], rbx
0x1800070b5  push    rdi
0x1800070b6  sub     rsp, 20h
0x1800070ba  mov     r9d, 7FFFFFFFh
0x1800070c0  jmp     short loc_1800070D0
0x1800070c2  lea     edx, [r8-1]
0x1800070c6  mov     eax, r8d
0x1800070c9  lock cmpxchg [rcx+0Ch], edx
0x1800070ce  jz      short loc_1800070D9
0x1800070d0  mov     r8d, [rcx+0Ch]
0x1800070d4  cmp     r8d, r9d
0x1800070d7  jnz     short loc_1800070C2
0x1800070d9  mov     ebx, [rcx+20h]
0x1800070dc  lea     edi, [r8-1]
0x1800070e0  and     ebx, 4
0x1800070e3  test    edi, edi
0x1800070e5  jnz     short loc_180007114
0x1800070e7  test    rcx, rcx
0x1800070ea  jz      short loc_1800070FB
0x1800070ec  mov     rax, [rcx]
0x1800070ef  lea     edx, [rdi+1]
0x1800070f2  mov     rax, [rax+38h]
0x1800070f6  call    _guard_dispatch_icall$thunk$10345483385596137414
0x1800070fb  test    ebx, ebx
0x1800070fd  jz      short loc_180007135
0x1800070ff  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007106  test    rcx, rcx
0x180007109  jz      short loc_180007135
0x18000710b  mov     rax, [rcx]
0x18000710e  mov     rax, [rax+10h]
0x180007112  jmp     short loc_180007130
0x180007114  test    ebx, ebx
0x180007116  jnz     short loc_180007135
0x180007118  cmp     edi, 1
0x18000711b  jnz     short loc_180007135
0x18000711d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180007124  test    rcx, rcx
0x180007127  jz      short loc_180007135
0x180007129  mov     rdx, [rcx]
0x18000712c  mov     rax, [rdx+10h]
0x180007130  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180007135  mov     rbx, [rsp+28h+arg_0]
0x18000713a  mov     eax, edi
0x18000713c  add     rsp, 20h
0x180007140  pop     rdi
0x180007141  retn
```
