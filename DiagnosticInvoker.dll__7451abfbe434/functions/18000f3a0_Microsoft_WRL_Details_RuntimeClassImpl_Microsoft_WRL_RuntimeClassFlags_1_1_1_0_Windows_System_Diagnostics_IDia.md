# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticActionResult,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x18000f3a0`
- end: `0x18000f430`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIDiagnosticActionResult@Diagnostics@System@Windows@@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `144`
- prototype: `__int64 __fastcall(volatile signed __int64 *)`
- caller_count: `3`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000f440`
- `0x18000f450`
- `0x18000f460`

## callees

- `0x18000f3a0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticActionResult,Microsoft::WRL::FtmBase>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rdx
  unsigned __int32 v2; // ebx
  bool v3; // zf
  signed __int64 v4; // rax
  signed __int32 v5; // r8d

  v1 = *((_QWORD *)a1 + 7);
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return 2147483646;
    v2 = v1 - 1;
    v4 = _InterlockedCompareExchange64(a1 + 7, v1 - 1, v1);
    v3 = v1 == v4;
    v1 = v4;
    if ( v3 )
      goto LABEL_10;
  }
  do
    v5 = *(_DWORD *)(2 * v1 + 0x10);
  while ( v5 != 0x7FFFFFFF && v5 != _InterlockedCompareExchange((volatile signed __int32 *)(2 * v1 + 16), v5 - 1, v5) );
  v2 = v5 - 1;
LABEL_10:
  if ( !v2 )
  {
    if ( a1 )
      (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*a1 + 64))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18000f3a0  push    rbx
0x18000f3a2  sub     rsp, 20h
0x18000f3a6  mov     rdx, [rcx+38h]
0x18000f3aa  mov     r9, rcx
0x18000f3ad  mov     r10d, 7FFFFFFFh
0x18000f3b3  test    rdx, rdx
0x18000f3b6  js      short loc_18000F3E7
0x18000f3b8  cmp     edx, r10d
0x18000f3bb  jz      short loc_18000F3D1
0x18000f3bd  lea     rbx, [rdx-1]
0x18000f3c1  mov     rax, rdx
0x18000f3c4  lock cmpxchg [rcx+38h], rbx
0x18000f3ca  mov     rdx, rax
0x18000f3cd  jnz     short loc_18000F3B3
0x18000f3cf  jmp     short loc_18000F3F5
0x18000f3d1  mov     ebx, 7FFFFFFEh
0x18000f3d6  jmp     short loc_18000F428
0x18000f3d8  lea     ecx, [r8-1]
0x18000f3dc  mov     eax, r8d
0x18000f3df  lock cmpxchg [rdx+rdx+10h], ecx
0x18000f3e5  jz      short loc_18000F3F1
0x18000f3e7  mov     r8d, [rdx+rdx+10h]
0x18000f3ec  cmp     r8d, r10d
0x18000f3ef  jnz     short loc_18000F3D8
0x18000f3f1  lea     ebx, [r8-1]
0x18000f3f5  test    ebx, ebx
0x18000f3f7  jnz     short loc_18000F428
0x18000f3f9  test    r9, r9
0x18000f3fc  jz      short loc_18000F410
0x18000f3fe  mov     rax, [r9]
0x18000f401  lea     edx, [rbx+1]
0x18000f404  mov     rcx, r9
0x18000f407  mov     rax, [rax+40h]
0x18000f40b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f410  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000f417  test    rcx, rcx
0x18000f41a  jz      short loc_18000F428
0x18000f41c  mov     rdx, [rcx]
0x18000f41f  mov     rax, [rdx+10h]
0x18000f423  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000f428  mov     eax, ebx
0x18000f42a  add     rsp, 20h
0x18000f42e  pop     rbx
0x18000f42f  retn
```
