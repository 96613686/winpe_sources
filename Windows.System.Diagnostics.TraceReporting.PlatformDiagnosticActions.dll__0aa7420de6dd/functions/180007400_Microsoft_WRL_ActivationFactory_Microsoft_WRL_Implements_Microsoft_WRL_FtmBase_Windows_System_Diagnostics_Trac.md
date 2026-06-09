# Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(void)

- ea: `0x180007400`
- end: `0x180007455`
- name: `?AddRef@?$ActivationFactory@U?$Implements@VFtmBase@WRL@Microsoft@@UIPlatformDiagnosticActionsStatics@TraceReporting@Diagnostics@System@Windows@@@WRL@Microsoft@@VNil@Details@23@V4523@$0A@@WRL@Microsoft@@UEAAKXZ`
- size: `85`
- prototype: `__int64 __fastcall(__int64)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180007460`
- `0x180007470`

## callees

- `0x180007400`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::ActivationFactory<Microsoft::WRL::Implements<Microsoft::WRL::FtmBase,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticActionsStatics>,Microsoft::WRL::Details::Nil,Microsoft::WRL::Details::Nil,0>::AddRef(
        __int64 a1)
{
  unsigned int v1; // ebx
  signed __int32 v2; // r8d

  v1 = 0x7FFFFFFF;
  while ( 1 )
  {
    v2 = *(_DWORD *)(a1 + 68);
    if ( v2 == 0x7FFFFFFF )
      break;
    if ( v2 == _InterlockedCompareExchange((volatile signed __int32 *)(a1 + 68), v2 + 1, v2) )
    {
      v1 = v2 + 1;
      break;
    }
  }
  if ( (*(_BYTE *)(a1 + 88) & 4) == 0 && v1 == 2 && Microsoft::WRL::Details::ModuleBase::module_ )
    (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                         + 8LL))(Microsoft::WRL::Details::ModuleBase::module_);
  return v1;
}

```

## disassembly

```asm
0x180007400  push    rbx
0x180007402  sub     rsp, 20h
0x180007406  mov     ebx, 7FFFFFFFh
0x18000740b  jmp     short loc_18000741B
0x18000740d  lea     edx, [r8+1]
0x180007411  mov     eax, r8d
0x180007414  lock cmpxchg [rcx+44h], edx
0x180007419  jz      short loc_180007426
0x18000741b  mov     r8d, [rcx+44h]
0x18000741f  cmp     r8d, ebx
0x180007422  jnz     short loc_18000740D
0x180007424  jmp     short loc_18000742A
0x180007426  lea     ebx, [r8+1]
0x18000742a  test    byte ptr [rcx+58h], 4
0x18000742e  jnz     short loc_18000744D
0x180007430  cmp     ebx, 2
0x180007433  jnz     short loc_18000744D
0x180007435  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x18000743c  test    rcx, rcx
0x18000743f  jz      short loc_18000744D
0x180007441  mov     rdx, [rcx]
0x180007444  mov     rax, [rdx+8]
0x180007448  call    _guard_dispatch_icall$thunk$10345483385596137414
0x18000744d  mov     eax, ebx
0x18000744f  add     rsp, 20h
0x180007453  pop     rbx
0x180007454  retn
```
