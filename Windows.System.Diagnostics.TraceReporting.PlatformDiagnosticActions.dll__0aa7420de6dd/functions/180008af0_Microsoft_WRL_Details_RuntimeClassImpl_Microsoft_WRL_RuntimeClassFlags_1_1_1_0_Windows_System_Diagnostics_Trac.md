# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticTraceInfo>::Release(void)

- ea: `0x180008af0`
- end: `0x180008b80`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$00@WRL@Microsoft@@$00$00$0A@UIPlatformDiagnosticTraceInfo@TraceReporting@Diagnostics@System@Windows@@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `144`
- prototype: `__int64 __fastcall(volatile signed __int64 *)`
- caller_count: `2`
- callee_count: `2`
- tags: `broker_com_uri`

## callers

- `0x180008b90`
- `0x180008cf0`

## callees

- `0x180008af0`
- `0x18000b010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<1>,1,1,0,Windows::System::Diagnostics::TraceReporting::IPlatformDiagnosticTraceInfo>::Release(
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
      (*(void (__fastcall **)(volatile signed __int64 *, __int64))(*a1 + 96))(a1, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v2;
}

```

## disassembly

```asm
0x180008af0  push    rbx
0x180008af2  sub     rsp, 20h
0x180008af6  mov     rdx, [rcx+18h]
0x180008afa  mov     r9, rcx
0x180008afd  mov     r10d, 7FFFFFFFh
0x180008b03  test    rdx, rdx
0x180008b06  js      short loc_180008B37
0x180008b08  cmp     edx, r10d
0x180008b0b  jz      short loc_180008B21
0x180008b0d  lea     rbx, [rdx-1]
0x180008b11  mov     rax, rdx
0x180008b14  lock cmpxchg [rcx+18h], rbx
0x180008b1a  mov     rdx, rax
0x180008b1d  jnz     short loc_180008B03
0x180008b1f  jmp     short loc_180008B45
0x180008b21  mov     ebx, 7FFFFFFEh
0x180008b26  jmp     short loc_180008B78
0x180008b28  lea     ecx, [r8-1]
0x180008b2c  mov     eax, r8d
0x180008b2f  lock cmpxchg [rdx+rdx+10h], ecx
0x180008b35  jz      short loc_180008B41
0x180008b37  mov     r8d, [rdx+rdx+10h]
0x180008b3c  cmp     r8d, r10d
0x180008b3f  jnz     short loc_180008B28
0x180008b41  lea     ebx, [r8-1]
0x180008b45  test    ebx, ebx
0x180008b47  jnz     short loc_180008B78
0x180008b49  test    r9, r9
0x180008b4c  jz      short loc_180008B60
0x180008b4e  mov     rax, [r9]
0x180008b51  lea     edx, [rbx+1]
0x180008b54  mov     rcx, r9
0x180008b57  mov     rax, [rax+60h]
0x180008b5b  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b60  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180008b67  test    rcx, rcx
0x180008b6a  jz      short loc_180008B78
0x180008b6c  mov     rdx, [rcx]
0x180008b6f  mov     rax, [rdx+10h]
0x180008b73  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180008b78  mov     eax, ebx
0x180008b7a  add     rsp, 20h
0x180008b7e  pop     rbx
0x180008b7f  retn
```
