# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(void)

- ea: `0x180008a30`
- end: `0x180008ac2`
- name: `?Release@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `146`
- prototype: `__int64 __fastcall(__int64, __int64)`
- caller_count: `4`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180006730`
- `0x180008ad0`
- `0x180008ae0`
- `0x180008cc0`

## callees

- `0x180008a30`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::Release(
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
    v3 = *(unsigned int *)(a1 + 68);
    if ( (_DWORD)v3 == 0x7FFFFFFF )
      break;
    a2 = (unsigned int)(v3 - 1);
  }
  while ( (_DWORD)v3 != _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 68), a2, v3) );
  v4 = v3 - 1;
  v5 = *(_DWORD *)(a1 + 88) & 4;
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
0x180008a30  mov     [rsp+arg_0], rbx
0x180008a35  push    rdi
0x180008a36  sub     rsp, 20h
0x180008a3a  mov     r9d, 7FFFFFFFh
0x180008a40  jmp     short loc_180008A50
0x180008a42  lea     edx, [r8-1]
0x180008a46  mov     eax, r8d
0x180008a49  lock cmpxchg [rcx+44h], edx
0x180008a4e  jz      short loc_180008A59
0x180008a50  mov     r8d, [rcx+44h]
0x180008a54  cmp     r8d, r9d
0x180008a57  jnz     short loc_180008A42
0x180008a59  mov     ebx, [rcx+58h]
0x180008a5c  lea     edi, [r8-1]
0x180008a60  and     ebx, 4
0x180008a63  test    edi, edi
0x180008a65  jnz     short loc_180008A94
0x180008a67  test    rcx, rcx
0x180008a6a  jz      short loc_180008A7B
0x180008a6c  mov     rax, [rcx]
0x180008a6f  lea     edx, [rdi+1]
0x180008a72  mov     rax, [rax+38h]
0x180008a76  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008a7b  test    ebx, ebx
0x180008a7d  jz      short loc_180008AB5
0x180008a7f  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008a86  test    rcx, rcx
0x180008a89  jz      short loc_180008AB5
0x180008a8b  mov     rax, [rcx]
0x180008a8e  mov     rax, [rax+10h]
0x180008a92  jmp     short loc_180008AB0
0x180008a94  test    ebx, ebx
0x180008a96  jnz     short loc_180008AB5
0x180008a98  cmp     edi, 1
0x180008a9b  jnz     short loc_180008AB5
0x180008a9d  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008aa4  test    rcx, rcx
0x180008aa7  jz      short loc_180008AB5
0x180008aa9  mov     rdx, [rcx]
0x180008aac  mov     rax, [rdx+10h]
0x180008ab0  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008ab5  mov     rbx, [rsp+28h+arg_0]
0x180008aba  mov     eax, edi
0x180008abc  add     rsp, 20h
0x180008ac0  pop     rdi
0x180008ac1  retn
```
