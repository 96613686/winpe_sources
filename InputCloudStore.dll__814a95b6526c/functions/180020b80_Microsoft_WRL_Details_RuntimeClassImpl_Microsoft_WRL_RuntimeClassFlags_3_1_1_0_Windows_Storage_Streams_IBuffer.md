# Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release(void)

- ea: `0x180020b80`
- end: `0x180020bf8`
- name: `?Release@?$RuntimeClassImpl@U?$RuntimeClassFlags@$02@WRL@Microsoft@@$00$00$0A@UIBuffer@Streams@Storage@Windows@@UIBufferByteAccess@567@VFtmBase@23@@Details@WRL@Microsoft@@UEAAKXZ`
- size: `120`
- prototype: ``
- caller_count: `5`
- callee_count: `3`
- tags: `broker_com_uri`

## callers

- `0x18000cce8`
- `0x180020c00`
- `0x180020c10`
- `0x180020c20`
- `0x180020c70`

## callees

- `0x180008ea4`
- `0x180020b80`
- `0x180031010`

## pseudocode

```c
__int64 __fastcall Microsoft::WRL::Details::RuntimeClassImpl<Microsoft::WRL::RuntimeClassFlags<3>,1,1,0,Windows::Storage::Streams::IBuffer,Windows::Storage::Streams::IBufferByteAccess,Microsoft::WRL::FtmBase>::Release(
        __int64 a1,
        volatile int *a2)
{
  signed __int64 v2; // rax
  __int64 v3; // r10
  unsigned int v4; // ebx
  signed __int64 v5; // rtt

  v2 = *(_QWORD *)(a1 + 64);
  v3 = a1;
  while ( v2 >= 0 )
  {
    if ( (_DWORD)v2 == 0x7FFFFFFF )
      return 2147483646;
    v4 = v2 - 1;
    v5 = v2;
    v2 = _InterlockedCompareExchange64((volatile signed __int64 *)(a1 + 64), v2 - 1, v2);
    if ( v5 == v2 )
      goto LABEL_8;
  }
  v4 = Microsoft::WRL::Details::SafeUnknownDecrementReference((Microsoft::WRL::Details *)(2 * v2 + 16), a2);
LABEL_8:
  if ( !v4 )
  {
    if ( v3 )
      (*(void (__fastcall **)(__int64, __int64))(*(_QWORD *)v3 + 72LL))(v3, 1);
    if ( Microsoft::WRL::Details::ModuleBase::module_ )
      (*(void (__fastcall **)(struct Microsoft::WRL::Details::ModuleBase *))(*(_QWORD *)Microsoft::WRL::Details::ModuleBase::module_
                                                                           + 16LL))(Microsoft::WRL::Details::ModuleBase::module_);
  }
  return v4;
}

```

## disassembly

```asm
0x180020b80  push    rbx
0x180020b82  sub     rsp, 20h
0x180020b86  mov     rax, [rcx+40h]
0x180020b8a  mov     r10, rcx
0x180020b8d  test    rax, rax
0x180020b90  js      short loc_180020BAE
0x180020b92  cmp     eax, 7FFFFFFFh
0x180020b97  jz      short loc_180020BA7
0x180020b99  lea     rbx, [rax-1]
0x180020b9d  lock cmpxchg [rcx+40h], rbx
0x180020ba3  jnz     short loc_180020B8D
0x180020ba5  jmp     short loc_180020BBD
0x180020ba7  mov     ebx, 7FFFFFFEh
0x180020bac  jmp     short loc_180020BF0
0x180020bae  lea     rcx, ds:10h[rax*2]; this
0x180020bb6  call    ?SafeUnknownDecrementReference@Details@WRL@Microsoft@@YAKAECJ@Z; Microsoft::WRL::Details::SafeUnknownDecrementReference(long volatile &)
0x180020bbb  mov     ebx, eax
0x180020bbd  test    ebx, ebx
0x180020bbf  jnz     short loc_180020BF0
0x180020bc1  test    r10, r10
0x180020bc4  jz      short loc_180020BD8
0x180020bc6  mov     rcx, [r10]
0x180020bc9  lea     edx, [rbx+1]
0x180020bcc  mov     rax, [rcx+48h]
0x180020bd0  mov     rcx, r10
0x180020bd3  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bd8  mov     rcx, cs:?module_@ModuleBase@Details@WRL@Microsoft@@2PEAV1234@EA; Microsoft::WRL::Details::ModuleBase * Microsoft::WRL::Details::ModuleBase::module_
0x180020bdf  test    rcx, rcx
0x180020be2  jz      short loc_180020BF0
0x180020be4  mov     rax, [rcx]
0x180020be7  mov     rax, [rax+10h]
0x180020beb  call    _guard_dispatch_icall$thunk$10345483385596137414
0x180020bf0  mov     eax, ebx
0x180020bf2  add     rsp, 20h
0x180020bf6  pop     rbx
0x180020bf7  retn
```
