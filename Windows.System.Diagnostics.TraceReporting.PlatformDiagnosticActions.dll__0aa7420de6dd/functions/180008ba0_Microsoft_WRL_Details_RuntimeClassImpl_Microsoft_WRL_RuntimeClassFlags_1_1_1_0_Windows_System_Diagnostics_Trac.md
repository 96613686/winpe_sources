# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticTraceRuntimeInfo>::Release(void)

- ea: `0x180008ba0`
- end: `0x180008c30`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIPlatformDiagnosticTraceRuntimeInfo@TraceReporting@Diagnostics@System@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `144`
- prototype: `__int64 __fastcall(volatile signed __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008c40`
- `0x180008d10`

## callees

- `0x180008ba0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticTraceRuntimeInfo>::Release(
        volatile signed __int64 *a1)
{
  signed __int64 v1; // rdx
  unsigned __int32 v2; // ebx
  bool v3; // zf
  signed __int64 v4; // rax
  signed __int32 v5; // r8d

  v1 = *((_QWORD *)a1 + 3);
  while ( v1 >= 0 )
  {
    if ( (_DWORD)v1 == 0x7FFFFFFF )
      return 2147483646;
    v2 = v1 - 1;
    v4 = _InterlockedCompareExchange64(a1 + 3, v1 - 1, v1);
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
0x180008ba0  push    rbx
0x180008ba2  sub     rsp, 20h
0x180008ba6  mov     rdx, [rcx+18h]
0x180008baa  mov     r9, rcx
0x180008bad  mov     r10d, 7FFFFFFFh
0x180008bb3  test    rdx, rdx
0x180008bb6  js      short loc_180008BE7
0x180008bb8  cmp     edx, r10d
0x180008bbb  jz      short loc_180008BD1
0x180008bbd  lea     rbx, [rdx-1]
0x180008bc1  mov     rax, rdx
0x180008bc4  lock cmpxchg [rcx+18h], rbx
0x180008bca  mov     rdx, rax
0x180008bcd  jnz     short loc_180008BB3
0x180008bcf  jmp     short loc_180008BF5
0x180008bd1  mov     ebx, 7FFFFFFEh
0x180008bd6  jmp     short loc_180008C28
0x180008bd8  lea     ecx, [r8-1]
0x180008bdc  mov     eax, r8d
0x180008bdf  lock cmpxchg [rdx+rdx+10h], ecx
0x180008be5  jz      short loc_180008BF1
0x180008be7  mov     r8d, [rdx+rdx+10h]
0x180008bec  cmp     r8d, r10d
0x180008bef  jnz     short loc_180008BD8
0x180008bf1  lea     ebx, [r8-1]
0x180008bf5  test    ebx, ebx
0x180008bf7  jnz     short loc_180008C28
0x180008bf9  test    r9, r9
0x180008bfc  jz      short loc_180008C10
0x180008bfe  mov     rax, [r9]
0x180008c01  lea     edx, [rbx+1]
0x180008c04  mov     rcx, r9
0x180008c07  mov     rax, [rax+40h]
0x180008c0b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c10  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008c17  test    rcx, rcx
0x180008c1a  jz      short loc_180008C28
0x180008c1c  mov     rdx, [rcx]
0x180008c1f  mov     rax, [rdx+10h]
0x180008c23  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008c28  mov     eax, ebx
0x180008c2a  add     rsp, 20h
0x180008c2e  pop     rbx
0x180008c2f  retn
```
