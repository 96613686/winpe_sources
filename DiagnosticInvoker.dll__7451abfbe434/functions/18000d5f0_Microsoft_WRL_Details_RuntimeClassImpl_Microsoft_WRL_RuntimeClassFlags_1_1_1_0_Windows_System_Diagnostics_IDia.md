# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticInvoker,Windows::System::Diagnostics::IDiagnosticInvoker2,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x18000d5f0`
- end: `0x18000d680`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIDiagnosticInvoker@Diagnostics@System@Windows@@UIDiagnosticInvoker2@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `144`
- prototype: `__int64 __fastcall(volatile signed __int64 *)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x18000d690`
- `0x18000d6a0`
- `0x18000d6b0`
- `0x18000d8a0`

## callees

- `0x18000d5f0`
- `0x180011010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::IDiagnosticInvoker,Windows::System::Diagnostics::IDiagnosticInvoker2,Microsoft::WRL::FtmBase>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rdx
  unsigned __int32 v2; // ebx
  bool v3; // zf
  signed __int64 v4; // rax
  signed __int32 v5; // r8d

  v1 = *((_QWORD *)a1 + 8);
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return 2147483646;
    v2 = v1 - 1;
    v4 = _InterlockedCompareExchange64(a1 + 8, v1 - 1, v1);
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
      (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*a1 + 56))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x18000d5f0  push    rbx
0x18000d5f2  sub     rsp, 20h
0x18000d5f6  mov     rdx, [rcx+40h]
0x18000d5fa  mov     r9, rcx
0x18000d5fd  mov     r10d, 7FFFFFFFh
0x18000d603  test    rdx, rdx
0x18000d606  js      short loc_18000D637
0x18000d608  cmp     edx, r10d
0x18000d60b  jz      short loc_18000D621
0x18000d60d  lea     rbx, [rdx-1]
0x18000d611  mov     rax, rdx
0x18000d614  lock cmpxchg [rcx+40h], rbx
0x18000d61a  mov     rdx, rax
0x18000d61d  jnz     short loc_18000D603
0x18000d61f  jmp     short loc_18000D645
0x18000d621  mov     ebx, 7FFFFFFEh
0x18000d626  jmp     short loc_18000D678
0x18000d628  lea     ecx, [r8-1]
0x18000d62c  mov     eax, r8d
0x18000d62f  lock cmpxchg [rdx+rdx+10h], ecx
0x18000d635  jz      short loc_18000D641
0x18000d637  mov     r8d, [rdx+rdx+10h]
0x18000d63c  cmp     r8d, r10d
0x18000d63f  jnz     short loc_18000D628
0x18000d641  lea     ebx, [r8-1]
0x18000d645  test    ebx, ebx
0x18000d647  jnz     short loc_18000D678
0x18000d649  test    r9, r9
0x18000d64c  jz      short loc_18000D660
0x18000d64e  mov     rax, [r9]
0x18000d651  lea     edx, [rbx+1]
0x18000d654  mov     rcx, r9
0x18000d657  mov     rax, [rax+38h]
0x18000d65b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d660  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000d667  test    rcx, rcx
0x18000d66a  jz      short loc_18000D678
0x18000d66c  mov     rdx, [rcx]
0x18000d66f  mov     rax, [rdx+10h]
0x18000d673  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000d678  mov     eax, ebx
0x18000d67a  add     rsp, 20h
0x18000d67e  pop     rbx
0x18000d67f  retn
```
